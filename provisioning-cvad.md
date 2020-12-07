---

copyright:
  years: 2020
lastupdated: "2020-12-07"

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

# Provisioning Citrix Virtual Apps and Desktops for IBM Cloud
{: #provisioning-cvad}

## Provisioning a {{site.data.keyword.cvad_short}} service
{: #provisioning-cvad-cloud-catalog}

When you provision {{site.data.keyword.cvad_full_notm}}, you receive the following components:
* Citrix Hypervisors. You get to choose the configuration and quantity of bare metal servers during the ordering process.
* 3 x Cloud Connectors on public virtual server instances with Windows 2019 OS.
* 1 x Active Directory server on a public virtual server instance with Windows 2016 OS.
* 1 x DHCP server on a public virtual server instance with CentOS to dynamically allocate IPs to the virtual machines.
* 1 x proxy server on a public virtual server instance with CentOS to allow access to the internet for both Cloud Connectors and desktops.
* File Storage with the capacity that you choose during the ordering process.
* Primary and portable subnets on a VLAN. 

All of the servers and virtual desktops are provisioned in IBM's private network and are fully secured.
{: note}

## Before you begin
{: #before-you-begin-provisioning-cvad}

You can provision {{site.data.keyword.cvad_full}} through the {{site.data.keyword.cloud_notm}} catalog and then manage the workloads through the Citrix Cloud management console.
{: shortdesc}

Before you begin, review the following prerequisites.
1. Review and complete the prerequisites found in [Getting started with {{site.data.keyword.cvad_full_notm}}](/docs/cvad?topic=cvad-getting-started-tutorial).
2. You must have either an active trial or paid subscription to Citrix Cloud. To learn more or to create an account, see [Citrix Cloud](https://onboarding.cloud.com/){: external}.
3. You must have a Citrix API client and password pair. Download the client ID and Secret. For more information about creating the key pair, see [Create an API client](https://developer.cloud.com/getting-started){: external}
4. Log in to the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog){: external}  by using your unique credentials. 
5. In the **Compute** section, locate the **Citrix Digital Workspace Solutions** section and select **Citrix Virtual Apps and Desktops**.

To provision {{site.data.keyword.cvad_full_notm}}, you need to enter the following information.

### Citrix connectivity
{: #citrix-connectivity}

After you provide your Citrix credentials, make sure to select **Validate** to verify your connectivity.
{: note}

| Field     | Details     |
| --------- | ----------- |
| Citrix customer ID | This ID is your Citrix customer ID. For more information about locating your ID, see this Citrix [Getting started](https://developer.cloud.com/getting-started/docs/overview#customer-id){: external} information. If you need to create a new account ID, see [How to Create a New Citrix Account ID/Org ID](https://support.citrix.com/article/CTX106671){: external}. |
| Citrix API client ID | Enter your Citrix API client ID information. For more information about creating the key pair, see [Create an API client](https://developer.cloud.com/getting-started){: external} from the Citrix Developer site. |
| Citrix API client secret | Enter your Citrix API client secret key. |
| Resource location | This Citrix resource location must be in the same geographic location as your selected {{site.data.keyword.cloud_notm}} data center. You can either create a resource location or use an existing one. The **Use existing** resource location option is only available after your account is validated. If you create a resource location, you must follow [Citrix naming restrictions](https://docs.citrix.com/en-us/citrix-cloud/citrix-cloud-resource-locations/resource-locations.html#naming-restrictions){: external}. Be aware that there are [resource location limits](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops-service/limits.html#resource-location-limits){: external}. |
| Hostname for Cloud Connector | These fields are optional for naming the Cloud Connector virtual machines. You can edit the names or keep the pre-populated defaults. If you edit the names, you must follow [Microsoft naming conventions](https://support.microsoft.com/en-us/help/909264/naming-conventions-in-active-directory-for-computers-domains-sites-and){: external}. |
| Cloud Connector and Active Directory domain name | The domain name is applied to both the Cloud Connectors and the Active Directory. You must follow [Microsoft naming conventions](https://support.microsoft.com/en-us/help/909264/naming-conventions-in-active-directory-for-computers-domains-sites-and){: external}. |
| Active Directory safe mode password | The password must meet the following password complexity requirements: <br> Cannot contain the user's account name or parts of the user's full name that exceed two consecutive characters <br> Must be at least 7 characters in length <br> Must contain characters from three of the following four categories: <br>- English uppercase characters (A through Z) <br>- English lowercase characters (a through z) <br>- Base 10 digits (0 - 9) <br>- Non-alphabetic characters (for example, !, $, #, %) |
{: caption="Table 1. Citrix connectivity details" caption-side="top"}

### Workload requirements
{: #workload-requirements}

Your bare metal server hardware and configuration recommendations are based on your workload requirements.   

| Field     | Details     |
| --------- | ----------- |
| Hosted-Shared Apps and Desktops | Deliver an application or desktop experience from multi-session OS machines to multiple, simultaneously connected users. |
| Server Virtual Desktop Infrastructure | Deliver a desktop experience from a server OS for a single user. |
| Desktop Virtual Desktop Infrastructure | Deliver a pooled or dedicated desktop experience from single-session OS machines. |
{: caption="Table 2. Workload requirements options" caption-side="top"}

When you select your workload requirements, you need to select how many of each type of user who needs to be supported. For more information about the user types, see the following table.

| Field    | Details    |
| -------- | ---------- |
| Task Worker | Uses a light workload and runs fewer applications that are not resource-intensive. Starts and stops applications less frequently. |
| Knowledge Worker | Uses multiple applications in well-balanced intensive workloads. |
| Power User | Uses resource-intensive applications, such as graphics or software development applications. |
{: caption="Table 3. Workload user types" caption-side="top"}

### Bare metal server configuration
{: #server-configuration}

All of your bare metal servers are configured identically based on your selections.
{: note}

| Field     | Details     |
| --------- | ----------- |
| Hostname root and domain | Your hostname and domain are saved in the server operating system and are used to identify servers. |
| Location  | The data center location must match the geography of your Citrix resource location. |
| Image | An image is the deployed operating system for your servers. |
| Profile | Consider selecting from the recommended server profiles, which are based on provided workload sizings by using Citrix best practices. You can select the **All servers** tab to choose from more supported server profiles. |
{: caption="Table 4. Server configuration details" caption-side="top"}

### File storage
{: #file-storage}

| Field     | Details     |
| --------- | ----------- |
| Size      | You can enter a file storage size 20 - 12,000 GB. |
| Snapshot space | Select how much snapshot space you want for your file storage volume. For more information about snapshots, see [Snapshots](/docs/FileStorage?topic=FileStorage-snapshots). |
| IOPS tier | By default, the IOPS tier is 4 IOPS/GB, which is designed for higher-intensity workloads. These workloads are typically characterized by having a high percentage of data active at any time. |
{: caption="Table 5. File storage details" caption-side="top"}

## Next steps
{: #next-steps-provisioning-cvad}

After you provision {{site.data.keyword.cvad_full_notm}}, you need to complete a few post-provisioning steps to get you up and running. For more information, see [Post-provisioning steps for Citrix Hypervisor](/docs/cvad?topic=cvad-post-provisioning-cvad).
