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
https://www.elastic.co/guide/en/elasticsearch/reference/8.11/append-processor.html 

<img width="872" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/a6cc1592-1009-4db9-8fc8-db3d5d92a392">
<img width="1959" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/c0fd1b95-b51a-4dc6-b7e9-c0155893bef4">

Index Lifecycle Management
Start by navigating to the ILM page. Under Stack Management, click Index Lifecycle Policies."ILP"
In the previous lab, you found that the metrics-apm.app.petclinic-default data stream uses the metrics-apm.app_metrics-default_policy. Search for this policy.
<img width="1960" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/cc61fec4-8e1e-444b-9262-abff4f5d1a6e">
If you click on the number under Linked indices, you will see all the backing indices using this policy—basically petclinic and APM server.
<img width="1812" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/efa235fe-6430-41b8-a428-e38bc61279be">
Default life cycle policy metrics-apm.app_metrics-default_policy. Click on the name of the policy to edit it and open the Advanced settings of the Hot phase to see its current settings.
 <img width="1973" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/6e9940ea-6c95-4e9e-ae8d-e090af8d0115">
You should see that a rollover is set when the index is 30 days old or any primary shard reaches 50 gigabytes. We are far from these two conditions. That's why you saw only one index in the previous lab
