---
title: What's new? 
description: Learn about the new features for and improvements to SQL Server on Azure Virtual Machines.
author: MashaMSFT
ms.author: mathoma
ms.reviewer: randolphwest
ms.date: 02/10/2023
ms.service: virtual-machines-sql
ms.subservice: service-overview
ms.topic: reference
ms.custom: ignite-2022
tags: azure-service-management
---
# What's new with SQL Server on Azure Virtual Machines?

[!INCLUDE[appliesto-sqlvm](../../includes/appliesto-sqlvm.md)]

When you deploy an Azure virtual machine (VM) with SQL Server installed on it, either manually, or through a built-in image, you can use Azure features to improve your experience. This article summarizes the documentation changes associated with new features and improvements in the recent releases of [SQL Server on Azure Virtual Machines (VMs)](https://azure.microsoft.com/services/virtual-machines/sql-server/). To learn more about SQL Server on Azure VMs, see the [overview](sql-server-on-azure-vm-iaas-what-is-overview.md). 


## February 2023 

| Changes | Details |
| --- | --- |
| **Enable Azure AD for SQL Server** | We've published a guide to help you enable Azure AD authentication for your SQL Server VM. Review [Configure Azure AD](configure-azure-ad-authentication-for-sql-vm.md) to learn more. | 


## January 2023

| Changes | Details |
| --- | --- |
| **Extend your multi-subnet AG to multiple regions** | Extend an existing multi-subnet availability group, either on Azure virtual machines, or on-premises, to another region in Azure. To learn more, review [Multi-subnet availability group in multiple regions](availability-group-manually-configure-multi-subnet-multiple-regions.md). | 


## 2022

| Changes | Details |
| --- | --- |
| **Troubleshoot SQL IaaS agent extension** | We've added an article to help you troubleshoot and address some known issues with the SQL Server IaaS agent extension. To learn more, read [Troubleshoot known issues](sql-agent-extension-troubleshoot-known-issues.md). |
| **Configure AG from Azure portal** | There is a new experience to deploy an Always On availability group to multiple subnets by using the Azure portal. The new availability group deployment method replaces the previous deployment through the SQL virtual machines resource. This feature is currently in preview. To learn more, review [Configure availability group through the Azure portal](availability-group-azure-portal-configure.md). | 
| **Azure AD authentication** | It's now possible to configure Azure Active Directory (Azure AD) authentication to your SQL Server 2022 on Azure VM by using the Azure portal. This feature is currently in preview. To get started, review [Azure AD with SQL Server VMs](security-considerations-best-practices.md#azure-ad-authentication-preview). | 
| **Least privilege permission model for SQL IaaS Agent extension** | There is a new permissions model available for the SQL Server IaaS Agent extension that grants the least privileged permission for each feature used by the extension. To learn more, review [SQL IaaS agent extension permissions](sql-server-iaas-agent-extension-automate-management.md#permissions-models). | 
| **Confidential VMs** | SQL Server on Azure VMs has added support to deploy to [SQL Server on Azure confidential VMs](sql-vm-create-confidential-vm-how-to.md). To get started, review the [Quickstart: Deploy SQL Server to an Azure confidential VM](sql-vm-create-portal-quickstart.md?tabs=confidential-vm). 
| **Azure CLI for SQL best practices assessment**| It's now possible to configure the [SQL best practices assessment](sql-assessment-for-sql-vm.md) feature using the Azure CLI. |
| **Configure tempdb from Azure portal** | It's now possible to configure your `tempdb` settings, such as the number of files, initial size, and autogrowth ratio for an existing SQL Server instance by using the Azure portal. See [manage SQL Server VM from portal](manage-sql-vm-portal.md#storage) to learn more. |
| **SDK-style SQL projects**| Use [Microsoft.Build.Sql](https://www.nuget.org/packages/Microsoft.Build.Sql) for SDK-style SQL projects in the SQL Database Projects extension in Azure Data Studio or VS Code. This feature is currently in preview. To learn more, see [SDK-style SQL projects](/sql/azure-data-studio/extensions/sql-database-project-extension-sdk-style-projects). |
| **Ebdsv5-series** | The new [Ebdsv5-series](/azure/virtual-machines/ebdsv5-ebsv5-series#ebdsv5-series) provides the highest I/O throughput-to-vCore ratio in Azure along with a memory-to-vCore ratio of 8. This series offers the best price-performance for SQL Server workloads on Azure VMs. Consider this series first for most SQL Server workloads. To learn more, see the updates in [VM sizes](performance-guidelines-best-practices-vm-size.md). |
| **Security best practices** | The [SQL Server VM security best practices](security-considerations-best-practices.md) have been rewritten and refreshed! |
| **Migrate with distributed AG** | It's now possible to migrate your database(s) from a [standalone instance](../../migration-guides/virtual-machines/sql-server-distributed-availability-group-migrate-standalone-instance.md) of SQL Server or an [entire availability group](../../migration-guides/virtual-machines/sql-server-distributed-availability-group-migrate-ag.md) over to SQL Server on Azure VMs using a distributed availability group! See the [prerequisites](../../migration-guides/virtual-machines/sql-server-distributed-availability-group-migrate-prerequisites.md) to get started. |

## 2021

| Changes | Details |
| --- | --- |
| **Deployment configuration improvements** | It's now possible to configure the following options when deploying your SQL Server VM from an Azure Marketplace image: System database location, number of `tempdb` data files, collation, max degree of parallelism, min and max server memory settings, and optimize for ad hoc workloads. Review [Deploy SQL Server VM](create-sql-vm-portal.md) to learn more. | 
| **Automated backup improvements** | The possible maximum automated backup retention period has changed from 30 days to 90, and you're now able to choose a specific container within the storage account. Review [automated backup](automated-backup.md) to learn more.  | 
| **Tempdb configuration** | You can now modify `tempdb` settings directly from the [SQL virtual machines](manage-sql-vm-portal.md) blade in the Azure portal, such as increasing the size, and adding data files. |
| **Eliminate need for HADR Azure Load Balancer or DNN** | Deploy your SQL Server VMs to multiple subnets to eliminate the dependency on the Azure Load Balancer or distributed network name (DNN) to route traffic to your high availability / disaster recovery (HADR) solution! See the [multi-subnet availability group](availability-group-manually-configure-prerequisites-tutorial-multi-subnet.md) tutorial, or [prepare SQL Server VM for FCI](failover-cluster-instance-prepare-vm.md#subnets) article to learn more. | 
| **SQL Assessment** | It's now possible to assess the health of your SQL Server VM in the Azure portal using [SQL Assessment](sql-assessment-for-sql-vm.md) to surface recommendations that improve performance, and identify missing best practices configurations. This feature is currently in preview. |
| **SQL IaaS extension now supports Ubuntu** | Support has been added to [register](../linux/sql-iaas-agent-extension-register-vm-linux.md) your SQL Server VM running on Ubuntu Linux with the [SQL Server IaaS Extension](../linux/sql-server-iaas-agent-extension-linux.md) for limited functionality. | 
| **SQL IaaS extension full mode no longer requires restart** | Restarting the SQL Server service is no longer necessary when registering your SQL Server VM with the [SQL IaaS Agent extension](sql-server-iaas-agent-extension-automate-management.md) in [full mode](sql-agent-extension-manually-register-single-vm.md#full-mode)! | 
| **Repair SQL Server IaaS extension in portal** | It's now possible to verify the status of your SQL Server IaaS Agent extension directly from the Azure portal, and [repair](sql-agent-extension-manually-register-single-vm.md#repair-extension) it, if necessary. | 
| **Security enhancements in the Azure portal** | Once you've enabled [Microsoft Defender for SQL](/azure/security-center/defender-for-sql-usage), you can view Security Center recommendations in the [SQL virtual machines resource in the Azure portal](manage-sql-vm-portal.md#security-center). | 
| **HADR content refresh** | We've refreshed and enhanced our high availability and disaster recovery (HADR) content! There's now an [Overview of the Windows Server Failover Cluster](hadr-windows-server-failover-cluster-overview.md), as well as a consolidated [how-to configure quorum](hadr-cluster-quorum-configure-how-to.md) for SQL Server VMs.  Additionally, we've enhanced the [cluster best practices](hadr-cluster-best-practices.md) with more comprehensive setting recommendations adopted to the cloud.| 
| **Migrate high availability to VM** | Azure Migrate brings support to lift and shift your entire high availability solution to SQL Server on Azure VMs! Bring your [availability group](../../migration-guides/virtual-machines/sql-server-availability-group-to-sql-on-azure-vm.md) or your [failover cluster instance](../../migration-guides/virtual-machines/sql-server-failover-cluster-instance-to-sql-on-azure-vm.md) to SQL Server VMs using Azure Migrate today! 
| **Performance best practices refresh** | We've rewritten, refreshed, and updated the performance best practices documentation, splitting one article into a series that contains: [a checklist](performance-guidelines-best-practices-checklist.md), [VM size guidance](performance-guidelines-best-practices-vm-size.md), [Storage guidance](performance-guidelines-best-practices-storage.md), and [collecting baseline instructions](performance-guidelines-best-practices-collect-baseline.md). |

## 2020

| Changes | Details |
| --- | --- |
| **Azure Government support** | It's now possible to register SQL Server virtual machines with the SQL IaaS Agent extension for virtual machines hosted in the [Azure Government](https://azure.microsoft.com/global-infrastructure/government/) cloud. | 
| **Azure SQL family** | SQL Server on Azure Virtual Machines is now a part of the [Azure SQL family of products](../../azure-sql-iaas-vs-paas-what-is-overview.md). Check out our [new look](../index.yml)! Nothing has changed in the product, but the documentation aims to make the Azure SQL product decision easier. | 
| **Distributed network name (DNN)** | SQL Server 2019 on Windows Server 2016+ is now previewing support for routing traffic to your failover cluster instance (FCI) by using a [distributed network name](./failover-cluster-instance-distributed-network-name-dnn-configure.md) rather than using Azure Load Balancer. This support simplifies and streamlines connecting to your high-availability (HA) solution in Azure. | 
| **FCI with Azure shared disks** | It's now possible to deploy your [failover cluster instance (FCI)](failover-cluster-instance-overview.md) by using [Azure shared disks](failover-cluster-instance-azure-shared-disks-manually-configure.md). |
| **Reorganized FCI docs** | The documentation around [failover cluster instances with SQL Server on Azure VMs](failover-cluster-instance-overview.md) has been rewritten and reorganized for clarity. We've separated some of the configuration content, like the [cluster configuration best practices](hadr-cluster-best-practices.md), how to prepare a [virtual machine for a SQL Server FCI](failover-cluster-instance-prepare-vm.md), and how to configure [Azure Load Balancer](./availability-group-vnn-azure-load-balancer-configure.md). | 
| **Migrate log to ultra disk** | Learn how you can [migrate your log file to an ultra disk](storage-migrate-to-ultradisk.md) to leverage high performance and low latency. | 
| **Create availability group using Azure PowerShell** | It's now possible to simplify the creation of an availability group by using [Azure PowerShell](availability-group-az-commandline-configure.md) as well as the Azure CLI. | 
| **Configure availability group in portal** | It's now possible to [configure your availability group via the Azure portal](availability-group-azure-portal-configure.md). This feature is currently in preview and being deployed so if your desired region is unavailable, check back soon. | 
| **Automatic extension registration** | You can now enable the [Automatic registration](sql-agent-extension-automatic-registration-all-vms.md) feature to automatically register all SQL Server VMs already deployed to your subscription with the [SQL IaaS Agent extension](sql-server-iaas-agent-extension-automate-management.md). This applies to all existing VMs, and will also automatically register all SQL Server VMs added in the future.   | 
| **DNN for availability group** | You can now configure a [distributed network name (DNN) listener)](availability-group-distributed-network-name-dnn-listener-configure.md) for SQL Server 2019 CU8 and later to replace the traditional [VNN listener](availability-group-overview.md#connectivity), negating the need for an Azure Load Balancer.   | 




## Additional resources

**Windows VMs**:

* [Overview of SQL Server on a Windows VM](sql-server-on-azure-vm-iaas-what-is-overview.md)
* [Provision SQL Server on a Windows VM](create-sql-vm-portal.md)
* [Migration guide: SQL Server to SQL Server on Azure Virtual Machines](../../migration-guides/virtual-machines/sql-server-to-sql-on-azure-vm-individual-databases-guide.md)
* [High availability and disaster recovery for SQL Server on Azure Virtual Machines](business-continuity-high-availability-disaster-recovery-hadr-overview.md)
* [Performance best practices for SQL Server on Azure Virtual Machines](./performance-guidelines-best-practices-checklist.md)
* [Application patterns and development strategies for SQL Server on Azure Virtual Machines](application-patterns-development-strategies.md)

**Linux VMs**:

* [Overview of SQL Server on a Linux VM](../linux/sql-server-on-linux-vm-what-is-iaas-overview.md)
* [Provision SQL Server on a Linux virtual machine](../linux/sql-vm-create-portal-quickstart.md)
* [FAQ (Linux)](../linux/frequently-asked-questions-faq.yml)
* [SQL Server on Linux documentation](/sql/linux/sql-server-linux-overview)
