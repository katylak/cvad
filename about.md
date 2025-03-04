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
{:beta: .beta}
{:important: .important}
{:table: .aria-labeledby="caption"}

# About Citrix Virtual Apps and Desktops for IBM Cloud
{: #about-citrix-virtual-apps-and-desktops}

{{site.data.keyword.cvad_full}} is a streamlined process for experienced administrators and service providers to create a dedicated Citrix Virtual Apps and Desktops (CVAD) service environment at one of our global data centers. This solution provides flexibility, control, and saves you time in building out your virtual apps and desktops solution. If you’ve invested in virtual desktop infrastructure (VDI), you understand the complexity of hosting and managing VDI entirely on-premises. The offering is purposefully built for a better VDI experience in the cloud.

The solution is integrated with the CVAD service deployment model, which shifts the management of core components to Citrix so you can focus on managing your applications and desktops. {{site.data.keyword.cloud_notm}} creates the Citrix Cloud Connectors and other compute, networking, and storage components that are required to host your applications and desktops and connects the {{site.data.keyword.cloud_notm}} resource location to Citrix Cloud. You manage the infrastructure components after provisioning, including the Active Directory and Virtual Delivery Agents (VDAs).

## Provisioning Citrix Virtual Apps and Desktops on Classic Infrastructure option
{: #cvad-classic-provisioning-options}

 You can provision Citrix Hypervisor on Bare Metal servers or VMWare. For more information about provisioning on Classic infrastructure, see [Provisioning Citrix Virtual Apps and Desktops on IBM Cloud Classic infrastructure](/docs/cvad?topic=cvad-provisioning-cvad-classic).

![Architecture diagram.](images/CitrixArchDiagram.svg){: caption="Figure 1. {{site.data.keyword.cvad_full_notm}} Classic architecture diagram" caption-side="bottom"}

## Provisioning Citrix Virtual Apps and Desktops on Virtual Private Cloud option
{: #cvad-vpc-provisioning-options}

CVAD VPC is a Beta feature available for evaluation and testing purposes.
{: beta}

You can provision CVAD on Virtual Private Cloud. For more information about provisioning on Classic infrastructure, see [Provisioning Citrix Virtual Apps and Desktops on Virtual Private Cloud](/docs/cvad?topic=cvad-provisioning-cvad-gen2).

![Architecture diagram.](images/cvad-vpc-arch.png){: caption="Figure 2. {{site.data.keyword.cvad_full_notm}} VPC architecture diagram" caption-side="bottom"}

## Related information
{: #cvad-related-info}

For more information about Citrix Virtual Apps and Desktops service, see [Citrix documentation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops-service){: external}.
