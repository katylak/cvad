---

copyright:
  years: 2020, 2021, 2022
lastupdated: "2022-02-28"

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
{:beta: .beta}
{:table: .aria-labeledby="caption"}

# Provisioning Citrix Virtual Apps and Desktops on Virtual Private Cloud
{: #provisioning-cvad-vpc}

CVAD VPC is a Beta feature available for evaluation and testing purposes.
{: beta}

Use this task to provision your {{site.data.keyword.cvad_full}} solution on {{site.data.keyword.IBM}} Virtual Private Cloud. This task corresponds to the provisioning form you see when you select the **VPC** tile from the Citrix Virtual Apps and Desktops for {{site.data.keyword.cloud}} page. Provisioning uses Schematics to provision your resources. For more information about Schematics, see [Schematics, IBM Cloud’s deployment manager](https://cloud.ibm.com/schematics/overview).

## What is provisioned
{: #what-is-provisioned-vpc}

When you provision the standard infrastructure VPC {{site.data.keyword.cvad_full_notm}}, you receive the following components in each zone:

*   1 x VPC (if VPC name not specified)
*   1 x /24 Subnet (256 IPs)
*   1 x Public Gateway
*   1 x Active Directory VSI
*   2 x Cloud Connector VSIs
*   Custom Image VSI (optional)
*   4 Security Groups (5 if Custom Image VSI deployed)
      *  Active Directory and Cloud Connector VSIs)
      *  VDA VSIs
      *  Master Image Prep VSI (VSI deployed during Citrix Machine Catalog creation)
      *  Custom Image VSI (optional)

{{site.data.keyword.cvad_full_notm}} solutions on VPC do not require additional configuration for monitoring, storage, networking or high availability.

All of the servers and virtual desktops are provisioned in the {{site.data.keyword.IBM}} private network.
{: note}

More technical information is available in the [readme file](https://github.ibm.com/workload-eng-services/cvad-vpc-tf/blob/master/README.md). 

## Before you begin
{: #before-you-begin-provisioning-cvad-vpc}

You can provision {{site.data.keyword.cvad_full}} through the {{site.data.keyword.cloud_notm}} catalog and then manage the workloads through the Citrix Cloud Management console.
{: shortdesc}

Before you begin, review the following prerequisites.
1. Review and complete the prerequisites found in [Getting started with {{site.data.keyword.cvad_full_notm}}](/docs/cvad?topic=cvad-getting-started-tutorial).
2. You must have either an active trial or paid subscription to Citrix Cloud. To learn more or to create an account, see [Citrix Cloud](https://onboarding.cloud.com/){: external}.
3. You must have a Citrix API client and password pair. Download the client ID and Secret. For more information about creating the key pair, see [Create an API client](https://developer.cloud.com/getting-started){: external}
4. Log in to the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/catalog){: external} by using your unique credentials. 
5. Create an {{site.data.keyword.cloud_notm}} [API key](https://cloud.ibm.com/iam/apikeys) in the IAM dashboard before you create an order. Retrieve and verify your credentials before proceeding. 
6. In the **Compute** section, locate the **Citrix Digital Workspace Solutions** section and select **Citrix Virtual Apps and Desktops**.

To provision {{site.data.keyword.cvad_full_notm}}, you enter the following information.

## Step 1 - Citrix connectivity
{: #citrix-connectivity-vpc}

1.  Enter your Citrix credentials.
    *  Citrix customer ID - This ID is your Citrix customer ID. For more information about locating your ID, see this Citrix [Getting started](https://developer.cloud.com/getting-started/docs/overview#customer-id){: external} information. If you need to create a new account ID, see [How to Create a New Citrix Account ID/Org ID](https://support.citrix.com/article/CTX106671){: external}. 
    *  Citrix API client ID - Enter your Citrix API client ID information. For more information about creating the key pair, see [Create an API client](https://developer.cloud.com/getting-started){: external} from the Citrix Developer site. 
    *  Citrix API client secret - Enter your Citrix API client secret key. 

2.  Select **Validate** to validate your credentials. You must have valid credentials to create an order.

3.  Enter the resource location for each zone. The resource location is the name given for the location of resources. It is not an identifier for {{site.data.keyword.cloud_notm}} data centers.

## Step 2 - Active Directory topology 
{: #active-directory-vpc}

Select your Active Directory topology. You have two options: 
* **IBM Cloud** - Deploy a new Active Directory controller on {{site.data.keyword.cloud_notm}}.
* **Extended** - You use an existing Active Directory and deploy a Domain Controller on {{site.data.keyword.cloud_notm}}.

## Step 3 - Virtual server instance configuration
{: #server-configuration-vpc}

All of your virtual server instances are configured identically based on your selections. Specify the:

* Resource Group - The {{site.data.keyword.cloud_notm}} resource group for your account. You can only select an existing resource group, you cannot create a new one.
* API key - Your API key
* Location  - The region and zones for this deployment 
* SSH key - Your SSH key.

## Step 4 - Infrastructure details
{: #infrastructure-details-vpc}

1.  Specify the size of your infrastructure in each zone.  
2.  Select whether to use a custom image for the virtual server instances.
3.  Select the custom image operating system.
4.  Select the custom image virtual server profile to use to provision your virtual server instances in post provisioning.
5.  Select an existing VPC to use or create a new VPC.

## Next steps
{: #next-steps-provisioning-cvad-vpc}

When the components are provisioned, you are directed to the Schematics where you can view the resources that are being provisioned. 

After the {{site.data.keyword.cvad_full_notm}} components are provisioned, you need to complete a few post-provisioning steps to get you up and running. For more information, see [Post-provisioning steps for CVAD on VPC](/docs/cvad?topic=cvad-post-provisioning-cvad-vpc).
