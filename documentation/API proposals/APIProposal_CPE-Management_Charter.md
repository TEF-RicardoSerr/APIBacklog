| **Field** | Description |
| --- | --- |
| API family name | CPE Management |
| API family owner | Charter Communications |
| API family summary | Service enabling API for customer premises equipment (CPE) management. |
||**Terms:** <br>  - `Service Site`: A physical location serviced by an internet service provider. <br> - `Device`: Hardware supplied by a service provider (CPE) to enable network access to a subscriber at a `Service Site`.  <br> - `Isolated Network`: One or more networks available on a `Device` that are logically separated and do not support inter-network communication between WiFi clients (`Home Devices`). |
||**High-Level Scope** <br> - Reboot one or more `Devices` (scheduled and immediate). <br> - List, create, modify, or delete WiFi `Isolated Networks` on one or more `Devices`. |
|| **B2C Scope:** The subscriber uses the API to manage their own `Device` supplied by a service provider, for example, through [Home Assistant](https://www.home-assistant.io/). <br><br> - List or modify their main WiFi `Isolated Network`. <br> - List, create, modify, or delete one or more secondary WiFi `Isolated Networks` for guest or IoT `Home Devices`. <br> - Reboot their `Device` to recover from a faulty network state.
|| **B2B2C Scope:** A subscriber delegates limited authorization to manage a secondary guest `Isolated Network` to a short-term rental app for guest stays. <br><br> - Create temporary `Isolated Networks` for rental guests. <br> - Automatic removal of `Isolated Networks` using an expiration period. <br> - Assign guest networks to a subscriber's "default" `Device`, allowing the subscriber to benefit from the functionality without granting access to `Service Site` or `Device` resources. |
||**B2B2B2C Scope 1:** A business with several properties (e.g., long-term rentals, hotels) using their service provider's `Devices` delegates authorization to manage the `Devices` and `Isolated Networks` to a third-party IT company. The property owner is the subscriber of the internet services, not the individual tenants. <br><br> - List the various `Service Sites`, if consent is granted by the property owners, including the location address through _additional_ consent to reconcile data sets when `Service Site` counts range from 100 to 10,000+. <br> - List the `Devices` at each `Service Site`, if consent is granted by the property owners, including the hardware address through _additional_ consent to reconcile data sets when `Device` counts range from 100 to 10,000+. <br> - Reboot `Devices` to recover from a faulty network state. <br> - List, create, modify, or delete primary and secondary `Isolated Networks`. <br> - Deploy the same `Isolated Network` to multiple `Devices` for coverage in common areas. |
||**B2B2B2C Scope 2:** The same scenario as the previous, except the tenants are the internet subscriber. <br><br> - Mirror the previous use cases, but require consent from _each and every_ tenant through granular OAuth scopes. <br> - Set a `description` on resources, allowing tenants to label their `Devices` as an alternative to exposing hardware addresses when multiple `Devices` are present. |
|| [!IMPORTANT] <br> When designing this API, it was intended that third-parties must provide a justification during API client registration to request scopes for sensitive information, such as `Service Site` location addresses or `Device` hardware addresses, due to their protected status by many governments. A short-term rental app would be unlikely to have the ability to request those scopes from a subscriber in order to protect the subscriber's privacy against apps that request excessive permissions for data collection purposes. |
| Technical viability | This API requires remote management of CPE `Devices` for all management features (e.g., TR-069, TR-369, OVSDB, SNMP, etc.).<br> This API definition is agnostic to the network isolation technique (e.g., separate Layer 3 networks, VLANs, OpenFlow, etc.). |
| Commercial viability | **TR-069:** [RUCKUS Networks](https://www.ruckusnetworks.com/) (commercial cloud), [prpl](https://prplfoundation.org/) (open source `Device` firmware)<br>**OVSDB:** [Plume](https://www.opensync.io/) (commercial cloud), [OpenSync](https://github.com/plume-design/opensync) (partially open source `Device` firmware with commercial modules by Plume) |
| YAML code available? | YES - [yaml - GitHub](https://github.com/caubut-charter/WorkingGroups/blob/feat/api-proposal-cpe-mgmt/APIBacklog/documentation/SupportingDocuments/others/cpe-management-api.yaml) - [yaml - Swagger Editor](https://editor.swagger.io/?url=https://raw.githubusercontent.com/caubut-charter/WorkingGroups/feat/api-proposal-cpe-mgmt/APIBacklog/documentation/SupportingDocuments/others/cpe-management-api.yaml) - [slides - GitHub](https://github.com/caubut-charter/WorkingGroups/blob/feat/api-proposal-cpe-mgmt/APIBacklog/documentation/SupportingDocuments/others/cpe-management-api.pptx) <br> |
| Validated in lab/productive environments? | YES - Field deployed on the production network using a UAT cloud with a production launch slated for the end of Q2. |
| Validated with real customers? | In-progress for **B2B2B2C Scope 1 & 2** with Charter, 1x API client, and 1x subscriber that has 30,000 properties.  Some of the properties have the property owner as the subscriber and others the tenant is the subscriber.  Charter is actively looking for a **B2B2C** API client partner. |
| Validated with operators? | Liberty Global, Vodafone, VodafoneZiggo, Charter, CableLabs |
| Supporters in API Backlog Working Group | Liberty Global, Vodafone, VodafoneZiggo, Charter, CableLabs |