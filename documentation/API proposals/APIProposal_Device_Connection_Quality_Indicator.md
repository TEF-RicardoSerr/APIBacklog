| **Field** | Description | 
| ---- | ----- |
| API family name |Device Connection Quality Indicator |
| API family owner | Deutsche Telekom (Noel Wirzius)|
| API summary | The API enables App Developers to get insights about the network status of a defined mobile device. For this the API will return an indicator which is bundeling information about the device network status such as availibilty, open datavolume, congjestion, historical congjestion or the connecitvity status (2G, 3G, 4G, 5G). The API service will also alert the consumers when an indicator changes. This API would be useful for applications that optimize user experience based on the connecitvity status of a defined device.|
| Technical viability | The type of ndata required for this API can be categorized into 4 groups as listed below <br>1\.	User data <br>2\.	Network Data <br>3\.	Historical data <br>4\. Device Data <br> <br> The following inputs are suggested as a first scope for the indicator:  <br> - Device Avalibilty (https://github.com/camaraproject/DeviceStatus/tree/release-0.5.0-rc) <br> - Network Insights ( https://github.com/camaraproject/WorkingGroups/blob/main/APIBacklog/documentation/SupportingDocuments/API%20proposals/APIproposal_NetworkInsights_Verizon.md) <br> - connection standard (2g,3g,4g,5g) <br> - Remaining datavolume of the contract <br> - Speed limitations of the contract|
| Commercial viability | This API was requested by different content providers. It helps them to set up the right content quality in their applications.|
| YAML code available? | NO. |
| Validated in lab/productive environments? | NO|
| Validated with operators? | NO |
| Supporters in API Backlog Working Group | Deutsche Telekom Vodafone |
