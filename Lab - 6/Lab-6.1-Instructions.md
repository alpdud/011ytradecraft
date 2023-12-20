Analyze your APM data and manage costs with storage explorer. For example, analyze the storage footprint of each of your services to see which are producing large amounts of data—​then change the sample rate of a service to lower the amount of data ingested. Or, expand the time filter to visualize data trends over time so that you can better forecast and prepare for future storage needs.


<img width="1959" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/83e29e9c-b355-414e-93ab-1462be1fcfea">
<img width="1740" alt="image" src="https://github.com/alpdud/011ytradecraft/assets/116056587/30a1ccfc-a330-40e9-a6e6-23dc843800a3">
The service statistics table provides detailed information on each service:

A list of service environments.
The sampling rate. This value is calculated by dividing the number of sampled transactions by total throughput. It might differ from the configured sampling rate for two reasons: with head-based sampling, the initial service makes the sampling decision, and with tail-based sampling, granular policies allow you to set multiple sample rates.
The estimated size on disk. This storage size includes both primary and replica shards and is calculated by prorating the total size of your indices by the service’s document count divided by the total number of documents.
Number of transactions, spans, errors, and metrics — doc count and size on disk.
