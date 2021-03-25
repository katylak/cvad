---

copyright:
  years: 2020
lastupdated: "2021-03-25"

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
{:beta: .beta}
{:table: .aria-labeledby="caption"}

# Getting started with Citrix Virtual Apps and Desktops for IBM Cloud
{: #getting-started-tutorial}

Use {{site.data.keyword.cvad_full_notm}} to create a dedicated {{site.data.keyword.cvad_short}} service environment at any of our global data centers.
{:shortdesc}

## Before you begin
{: #before-you-begin-getting-started}
Before you begin, review the following information.

* Want to learn more about {{site.data.keyword.cvad_full_notm}} and how it works? To learn more, see [About {{site.data.keyword.cvad_full_notm}}](/docs/cvad?topic=cvad-about-citrix-virtual-apps-and-desktops). 
* Review the supported products and versions in the [Product compatibility guide](/docs/cvad?topic=cvad-product-compatibility-guide).

You must have either an active trial or paid subscription to Citrix Cloud. To learn more or to create an account, see [Citrix Cloud](https://onboarding.cloud.com/){: external}.
{: important}

After you review this information, you are ready to get started. To begin, you need to complete the following prerequisites.
1. Sign up for an {{site.data.keyword.cloud_notm}} account
2. Add {{site.data.keyword.cloud_notm}} classic infrastructure API key
3. Verify Citrix and operating system entitlements
4. Set up network connectivity for logging on to {{site.data.keyword.cloud_notm}}
5. Enable VLAN spanning or VRF on your account
6. Set up user permissions in IAM

## Step 1. Sign up for an {{site.data.keyword.cloud_notm}} account
{: #sign-up-IBM-Cloud-account}

To order and use {{site.data.keyword.cloud_notm}} services, you need to sign up for an {{site.data.keyword.cloud_notm}} account. Billing information is associated with your {{site.data.keyword.cloud_notm}} account and the cost of the physical and virtual infrastructure and the resulting licenses are charged to your account. For more information about signing up, see [Signing up for {{site.data.keyword.cloud_notm}}](/docs/account?topic=account-account-getting-started#signup).

## Step 2. Add {{site.data.keyword.cloud_notm}} classic infrastructure API key
{: #classic-api-key}

You need to add a classic infrastructure API key to your {{site.data.keyword.cloud_notm}} account. For more information about creating or managing API keys, see [Managing classic infrastructure API keys](/docs/account?topic=account-classic_keys).

## Step 3. Verify Citrix and operating system entitlements
{: #verify-Citrix-OS-entitlements}

Verify that you have the Citrix Virtual Apps and Desktops service license available for the wanted environment size under the _Licensing_ section of [Citrix Cloud](http://citrix.cloud.com){: external}. During the provisioning process in the {{site.data.keyword.cloud_notm}} catalog, {{site.data.keyword.cloud_notm}} captures your Citrix account credentials and validates with Citrix Cloud before completing the provisioning process. You also need to verify that you have server or desktop licenses, along with any additional third-party licenses, depending on the applications that you intend to use.

## Step 4. Set up network connectivity for logging on to {{site.data.keyword.cloud_notm}}
{: #set-up-network-connectivity}

All of the resources that are provisioned through this solution are in a private network space with security groups attached wherever needed. The IP addresses are internal to IBM, so you need to use a separate VPN account for logging on to hypervisors and creating the virtual machine images. For more information about enabling VPN access and setting the password, see [Getting started with {{site.data.keyword.cloud_notm}} Virtual Private Networking](/docs/iaas-vpn?topic=iaas-vpn-getting-started). After you enable your VPN access and set the password, download the [VPN client](/docs/iaas-vpn?topic=iaas-vpn-standalone-vpn-clients). You then have access to the private network where your resources are provisioned.

## Step 5. Enable VLAN spanning or VRF on your {{site.data.keyword.cloud_notm}} account
{: #enable-vlan-spanning}

To enable VLAN spanning, complete the following steps:
1. Log in to the {{site.data.keyword.cloud_notm}} console by using your unique credentials. 
2. Select **Menu icon ![Menu icon](../../icons/icon_hamburger.svg) > Classic Infrastructure > Network > IP Management > VLANs**. 
3. Click **VLAN Spanning** and select _Enable_. 

To enable VRF, see [Enabling VRF](/docs/account?topic=account-vrf-service-endpoint#vrf). 

## Step 6. Set up user permissions in IAM
{: #set-up-user-permissions}

To provision {{site.data.keyword.cvad_full_notm}}, classic infrastructure users need to have the following permissions selected: 

| Category | Permission/Action |
| -------- | ---------- |
| Account | <br>- Add/Upgrade Storage (StorageLayer) <br>- Add Server <br>- Cancel Server <br>- Add/Upgrade Services <br>- Cancel Services <br>- Add/Upgrade Cloud Instances <br>- View Event Log |
| Devices | Select all |
| Network | Add Compute with Public Network Port |
| Services | Storage Manage |
{: caption="Table 1. Required user permissions to provision" caption-side="top"}

To access and update the classic infrastructure permissions, complete the following steps:

1. In the {{site.data.keyword.cloud_notm}} console, go to **Manage > Access (IAM)** and select **Users**. 
2. Select the user's name that you want to update access for, and click **Classic infrastructure**. 
3. If the user is a _Basic User_, you need to add the permission sets as shown in Table 1. 

For more information, see [Managing classic infrastructure access](/docs/account?topic=account-mngclassicinfra).

## Next steps
{: #getting-started-next-steps}

After you have reviewed and completed these prerequisites, you are ready to provision {{site.data.keyword.cvad_full_notm}}. For more information, see [Provisioning {{site.data.keyword.cvad_full_notm}}](/docs/cvad?topic=cvad-provisioning-cvad).
