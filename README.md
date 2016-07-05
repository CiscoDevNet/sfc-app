# Service Function Chaining (v0.1)

SFC is an application designed and implemented to run on top of ODL to create and deploy service chains using the NSH protocol as defined in draft-ietf-sfc-nsh (https://datatracker.ietf.org/doc/draft-ietf-sfc-nsh/). The functionality was first introduced into ODL Helium release with additional functionality added in Lithium, Beryllium, and Boron releases. 

# Development Team:

* Keith Burns (krb@cisco.com)
* Jim Guichard (jguichar@cisco.com)
* Martin Sunal (msunal@cisco.com)

## Application Overview:

Service Function Chaining provides the ability to define an ordered list of network services (e.g. firewalls, load balancers). These service are then "stitched" together in the network to create a service chain. This project provides the infrastructure (chaining logic, APIs) needed for ODL to provision a service chain in the network and an end-user application for defining such chains.

![SFC Project Overview](https://github.com/CiscoDevNet/sfc-app/blob/master/images/sfc_project_overview.png)

The service chaining service within ODL performs the following tasks:
* Receives information about a service chain and/or service path to be constructed via northbound APIs
* Information about available services and service forwarders/classifiers are contained in the node datastore
* Constructs service paths that are rendered into the network through multiple southbound protocols

![SFC ODL Components](https://github.com/CiscoDevNet/sfc-app/blob/master/images/sfc_odl_components.png)

## SFC GUI
The SFC application can be access using the RESTCONF NB APIs. An SFC GUI is provided with the ODL code distribution. 
The tabs across the top bar support a number of different SFC functions such as adding service function forwarders, service functions, creating service chains, and rendering service function paths.

### SFC Service Function Forwarders
Service function forwarders (SFF) may be added through the SFC GUI or directly through the RESTCONF APIs. 

![SFC Service Function Forwarders](https://github.com/CiscoDevNet/sfc-app/blob/master/images/sfc_sff.png)

### SFC Service Functions
Service functions (SF) may be added with an indication of which SFF they are attached.

![SFC Service Functions](https://github.com/CiscoDevNet/sfc-app/blob/master/images/sfc_sf.png)

### SFC Service Chains
The SFC application may be used to create abstract service function chains.

![SFC Service Chains](https://github.com/CiscoDevNet/sfc-app/blob/master/images/sfc_sc.png)

### SFC Service Function Paths / Rendered Service Paths
Service function chains may be rendered into the network through various SB protocols and an NSH path-id plus relevant index is auto generated. 

![SFC Service Chains](https://github.com/CiscoDevNet/sfc-app/blob/master/images/sfc_sfprsp.png)

## SFC Information:

IETF [SFC WG Charter](https://datatracker.ietf.org/wg/sfc/charter/)

IETF [SFC WG Documents](https://datatracker.ietf.org/wg/sfc/documents/)


Configuration:

Full details of the SFC implementation in ODL may be found here:
https://wiki.opendaylight.org/view/Service_Function_Chaining:Main