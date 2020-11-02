---

copyright:
  years: 2020
lastupdated: "2020-07-17"

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

# Configuring backup
{: #configuring-backup}

{{site.data.keyword.backup_full}} can be configured for backing up hypervisors and virtual machines either on Windows or Linux&reg; operating systems. The backup can be encrypted, compressed, and duplicated. For more details on backing up your system, see [Getting started with {{site.data.keyword.backup_notm}}](/docs/Backup?topic=Backup-getting-started).
{: shortdesc}

All of the virtual machines are stored on NFS storage, and [thin provisioning](https://docs.citrix.com/en-us/tech-zone/design/reference-architectures/image-management.html#choosing-the-right-provisioning-model){: external} can be used while creating the virtual machines by using machine catalogs. Snapshots can be manually created, or they can be scheduled at hourly, daily, or weekly intervals. For more information on scheduling snapshots and receiving notifications, see [Managing Snapshots](/docs/FileStorage?topic=FileStorage-managingSnapshots).
