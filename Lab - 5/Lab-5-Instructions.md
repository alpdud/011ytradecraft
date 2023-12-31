# Lab 6 Data Streams & Lifecycle Management
Start by looking at all the data streams created for you. Navigate to Stack Management, click Index Management, and finally open the Data Streams tab
<img width="1978" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/8cfedfda-773d-4c75-b670-7b08c27a16bb">
You will see a list of all the data streams created from the various integrations you used during this course.
Next, let's open the stream created by the APM integration. Which data stream is it?
<img width="1972" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/dc56c623-ab00-4d23-8f76-b9e0bb1988e5">
Click on the number of indices to explore the backing indices of this data stream. 
Fruther explore corrosponding data stream property - understand health/Index Lifecycle policy/Index Template being used
<img width="1958" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/3c5ce637-1ad7-45c5-bd64-928d189229ab">
<img width="1957" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/5e9ccb94-8e1d-49ac-88a7-197cdc352190">
Further check component template attached to the index template
<img width="1809" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/195f670c-954b-4a51-9583-71503709e0ba">
Check index mapping for each field within document 
<img width="1955" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/54086e63-2670-4e86-9d83-b1701cef20e8">
Elastic Agent integration data streams ship with a default ingest pipeline that preprocesses and enriches data before indexing. Starting in version 8.4, all default ingest pipelines call a non-existent and non-versioned "@custom" ingest pipeline. If left uncreated, this pipeline has no effect on your data. However, if added to a data stream and customized, this pipeline can be used for custom data processing, adding fields, sanitizing data, and more.



<img width="254" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/17537fee-193c-403a-b0a8-8c6fe3beb93d">

https://www.elastic.co/guide/en/elasticsearch/reference/8.11/processors.html

<img width="872" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/a6cc1592-1009-4db9-8fc8-db3d5d92a392">
<img width="1959" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/c0fd1b95-b51a-4dc6-b7e9-c0155893bef4"> 

The reroute processor allows to route a document to another target index or data stream.This processor can use both static values or reference fields from the document to determine the dataset and namespace components of the new target. 

<img width="887" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/4359b5db-050f-4c30-8a41-a3d12002d904">
https://www.elastic.co/guide/en/elasticsearch/reference/current/reroute-processor.html
https://www.elastic.co/guide/en/fleet/8.11/data-streams.html#data-streams-naming-scheme 



Index Lifecycle Management
Start by navigating to the ILM page. Under Stack Management, click Index Lifecycle Policies."ILP"
In the previous lab, you found that the metrics-apm.app.petclinic-default data stream uses the metrics-apm.app_metrics-default_policy. Search for this policy.
<img width="1960" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/cc61fec4-8e1e-444b-9262-abff4f5d1a6e">
If you click on the number under Linked indices, you will see all the backing indices using this policy—basically petclinic and APM server.
<img width="1812" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/efa235fe-6430-41b8-a428-e38bc61279be">
Default life cycle policy metrics-apm.app_metrics-default_policy. Click on the name of the policy to edit it and open the Advanced settings of the Hot phase to see its current settings.
 <img width="1973" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/6e9940ea-6c95-4e9e-ae8d-e090af8d0115">
You should see that a rollover is set when the index is 30 days old or any primary shard reaches 50 gigabytes. We are far from these two conditions. That's why you saw only one index in the previous lab

Edit the hot phase to trigger a rollover after 2 minutes only.
<img width="667" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/57a0379b-f07c-4314-8105-a19fbb659867">


Next, enable the warm phase and move data into this phase after 0 days. This will force your indices into the warm phase right after the rollover. Set the number of replicas to zero to save some space.

<img width="686" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/5a71fdb3-05b0-4a80-9437-3de153f9d46a">

Finally, delete the indices that are older than 1 hour from rollover.


<img width="677" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/338615c1-bcc0-432d-b5b9-d17e6a55a58a">

Save the policy.

From the Kibana main menu access Dev Tools and use Console to run the following command, which sets the poll interval for lifecycle policies to 30 seconds:

PUT _cluster/settings
{
  "persistent": {
    "indices.lifecycle.poll_interval": "30s"
  }
}
 <img width="673" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/8ea49241-a0d1-4793-ae3a-95a7b0d63ee9">



Note: this is far too low for production. The default of 10 minutes is generally acceptable.


Navigate to Index Management, and filter the indices to visualize the backing indices of the data stream. You can use the following query:

Search for "metrics-apm.app.petclinic-default"

<img width="1802" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/3b6e9e2a-09b2-4c89-b476-20889d1cca1c">


Wait a bit before hitting the Reload indices button. After a few minutes, you should see that a new backing index has been automatically created.

Open the latest index, and you should see that its current phase is Hot.

<img width="1817" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/2fb11ca7-c5fe-42ae-bb06-0da38ccd96c1">


If you open the other indices that are not the current one, you should see that they are in the Warm phase. After 1 hour, you will eventually see those indices disappear.
