---

copyright:
  years: 2020
lastupdated: "2020-12-10"

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

# Post-provisioning steps for Citrix Hypervisor
{: #post-provisioning-cvad}

After you provision your {{site.data.keyword.cvad_full}} (CVAD) with the Citrix Hypervisor (formerly known as XenServer), complete the following tasks:

1. Verify status of provisioned servers and view network and storage details
2. (Optional) Provision virtual server instance for management
3. Access the Citrix Hypervisor
4. Create resource pools
5. Access the Active Directory, Cloud Connectors, DHCP, and proxy server
6. Create master image of virtual machine

## Step 1. Verify status of provisioned servers and view network and storage details
{: #check-health-of-installed-servers}

1. Log in to the [{{site.data.keyword.cloud_notm}} console](https://cloud.ibm.com/){: external}. 
2. Navigate to **Menu icon ![Menu icon](../icons/icon_hamburger.svg) > Classic Infrastructure > Device List** to check the status of your servers and view your network and storage information. Make sure that provisioning is complete before proceeding. 

### Verify provisioned servers
{: #verify-provisioned-servers}

Your CVAD servers are provisioned with two tags: `CVAD` and `Resource location name`. The resource location name is the name that you provided during the ordering process. To verify that your servers are provisioned, you can query the servers in your account by filtering for them using these tags in the **Device List** page.

### View network details
{: #view-network-details}

After you filter for your server by using the appropriate tags, select your device. In the **Network details** section of your selected device, you can access your network information. 

You must use this network information when you establish network connectivity, order more servers, or order more network capacity. 
{: important}

### View storage details
{: #view-storage-details}

Complete the following steps to identify and view your File Storage details.
 
1. In the {{site.data.keyword.cloud_notm}} console, navigate to **Menu icon ![Menu icon](../icons/icon_hamburger.svg) > Classic Infrastructure > File Storage**.
2. Your File Storage has the `CVAD` and `Resource location name` tags in the _Notes_ field. 

## Step 2. (Optional) Provision virtual server instance for management
{: #provision-vsi-for-management}

Optionally, you can provision a virtual server instance with a Windows operating system to manage your {{site.data.keyword.cvad_full_notm}}. You can use a jump box to start a Remote Desktop session to access the Active Directory server and Citrix Cloud Connectors. The jump box is also needed to start the XenCenter management interface. You can order a Windows virtual server instance through the [{{site.data.keyword.cloud_notm}} catalog](https://cloud.ibm.com/gen1/infrastructure/provision/vs?cm_sp=Cloud-Product-_-OnPageNav-IBMCloudPlatform_IBMVirtualMachines-_-VSI_Prod_Midpage){: external}.

You must provision the virtual server instance with the same [network details](/docs/cvad?topic=cvad-post-provisioning-cvad#view-network-details) as the other service components that are attached to the resource location.
{: important}

## Step 3. Access the Citrix Hypervisor
{: #access-citrix-hypervisor}

Download the XenCenter software from [Citrix downloads](https://www.citrix.com/downloads/citrix-hypervisor/){: external} on the machine that you use to connect to your bare metal servers.

## Step 4. Create resource pools
{: #create-resource-pools}

You can run your hypervisors in pools. If you have both server VDA workloads and desktop VDA workloads, create a separate pool for each workload so that they are hosted in different pools. For more information, see [Hosts and resource pools](https://docs.citrix.com/en-us/citrix-hypervisor/hosts-pools.html){: external}.

If you ordered only one bare metal server, the storage is attached and mounted on the server. If you ordered multiple bare metal servers, the storage is attached on only one server, which is tagged as `master`. You can query your master node by filtering your device list with the tags `master` and `<your resource location name>`. This is the master node in your resource pool. Create a resource pool with this node as master, and then add all other bare metal servers to this pool. The storage is then mounted on the remaining nodes. For more details, see [Requirements for creating resource pools](https://docs.citrix.com/en-us/citrix-hypervisor/hosts-pools.html#requirements-for-creating-resource-pools){: external}.


## Step 5. Access the Active Directory, Cloud Connectors, DHCP, and proxy server
{: #access-connectors-dhcp-proxy-server}

The Active Directory and Cloud Connectors can be accessed through a Remote Desktop session. DHCP and the proxy server can be accessed by an SSH client.

## Step 6. Create master image of virtual machine
{: #create-virtual-machine}

The master image for virtual machines can be created through XenCenter. Add the proxy server settings on your master image. The settings can be copied from the Cloud Connector server. 

Individual virtual machine performance varies depending on workload.  However, in order to take advantage of optimizations that might result in improved performance, you can use the [Citrix Optimizer](https://support.citrix.com/article/CTX224676){: external} as well as this [tool for Windows 10](https://techcommunity.microsoft.com/t5/windows-virtual-desktop/windows-virtual-desktop-optimization-tool-now-available/m-p/1558614){: external}.
{: tip} 

## Next steps
{: #next-steps-post-provisioning}

After you've completed these post-provisioning steps, you are now ready to install your Virtual Delivery Agent (VDA) on your virtual machine. For more information on installing the VDA, machine creation scripts, and delivery groups for desktops, see the [Citrix documentation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops-service/install-configure.html#install-vdas-register-resources){: external}.

You can then perform your management tasks in the [Citrix Cloud Portal](http://citrix.cloud.com){: external}.
