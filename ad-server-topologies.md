---

copyright:
  years: 2020
lastupdated: "2020-09-10"

keywords:

subcollection: cvad

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:external: target="_blank" .external}
{:pre: .pre}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:table: .aria-labeledby="caption"}


# Active Directory server topologies 

_Content originally comes after Step 2. (Optional) Provision virtual server instance for management

## Option 1 - Active Directory installed on IBM Cloud

If you choose to install the Active Directory as your primary domain controller in {{site.data.keyword.cloud_notm}}, no further configuration is required. The Cloud Connectors are joined to the Active Directory server domain and are configured to communicate with Citrix Cloud. You might have to create users with the necessary privileges. You can also create bulk users in Active Directory. For more information, see this step-by-step guide on how to [Create bulk users in Active Directory](https://activedirectorypro.com/create-bulk-users-active-directory/){: external}.

## Option 2 - Active Directory installed on-premises
{: #active-directory-installed-on-premises}

### Establish network connectivity
If you choose to install the Active Directory server on-premises, you must establish network connectivity between {{site.data.keyword.cloud_notm}} and your on-premises location. You can set up network connectivity by using any of the gateway appliances available in {{site.data.keyword.cloud_notm}}. For more information, visit the **About** section in the [Gateway Appliance {{site.data.keyword.cloud_notm}} catalog page](https://cloud.ibm.com/gen1/infrastructure/provision/gateway){: external}. 

When you order a gateway appliance from {{site.data.keyword.cloud_notm}}, make sure that the data center and backend VLAN for these network devices correspond to the same data center and VLAN where your other services are already provisioned. See [View network details](/docs/cvad?topic=cvad-post-provisioning-cvad#view-network-details).
{: important}

After you've provisioned your gateway appliance, complete the configuration of these devices and then validate the network connectivity between {{site.data.keyword.cloud_notm}} and your on-premises location before configuring the Active Directory server.

### Domain join Cloud Connectors with Active Directory server
After you've established network connectivity between {{site.data.keyword.cloud_notm}} and your on-premises location, you can domain join the Cloud Connectors with the Active Directory server. Run the Cloud Connector registration scripts so that the connectors are added to the resource location. 

The Cloud Connector power shell scripts are available in `C:\postscript`.

_Option still in progress by dev_

## Option 3 - Active Directory installed on {{site.data.keyword.cloud_notm}} as a secondary controller
{: #active-directory-ibm-cloud-secondary-controller}

### Establish network connectivity
If you choose to install the Active Directory server on {{site.data.keyword.cloud_notm}} as a secondary controller, you must establish network connectivity between {{site.data.keyword.cloud_notm}} and your on-premises location. You can set up network connectivity by using any of the gateway appliances available in {{site.data.keyword.cloud_notm}}. For more information, visit the **About** section in the [Gateway Appliance {{site.data.keyword.cloud_notm}} catalog page](https://cloud.ibm.com/gen1/infrastructure/provision/gateway){: external}. 

When you order a gateway appliance from {{site.data.keyword.cloud_notm}}, make sure that the data center and backend VLAN for these network devices correspond to the same data center and VLAN where your other services are already provisioned. See [View network details](/docs/cvad?topic=cvad-post-provisioning-cvad#view-network-details).
{: important}

After you've provisioned your gateway appliance, complete the configuration of these devices and then validate the network connectivity between {{site.data.keyword.cloud_notm}} and your on-premises location before configuring the Active Directory server.

### Install domain controller and join secondary controller
A Windows virtual server instance is provisioned in the same VLAN and network as your other servers. Complete the following steps to install the domain controller and join the secondary controller:
  1. Install ADDS domain controller on this Windows server and join the secondary controller with your on-premises domain. 
  2. Domain join your Cloud Connectors, and then run the Cloud Connector registration scripts, which adds the connectors to the resource location.

The Cloud Connector power shell scripts are available in `C:\postscript`.  

_Option still in progress by dev_