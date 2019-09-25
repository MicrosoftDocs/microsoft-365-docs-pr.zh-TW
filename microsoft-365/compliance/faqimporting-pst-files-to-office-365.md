---
title: 有关将 PST 文件导入 Office 365 的常见问题解答
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: '对于管理员有关使用 Office 365 导入服务将组织 PST 文件导入 Office 365 邮箱的常见问题。 '
ms.openlocfilehash: 632b82a99f1be5d38db3fb50a4b2b4d7a6369186
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077030"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a>有关将 PST 文件导入 Office 365 的常见问题解答

**本文是为管理员。是否要将 PST 文件导入您自己的邮箱？请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
以下是有关使用 Office 365 导入服务将 PST 文件批量导入 Office 365 邮箱的一些常见问题。 有关如何导入 PST 文件的详细信息，请参阅将[PST 文件导入 Office 365 的概述。](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)
  
## <a name="using-network-upload-to-import-pst-files"></a>使用网络上传导入 PST 文件

有关分步说明，请参阅[使用网络上载将 PST 文件导入 Office 365](use-network-upload-to-import-pst-files.md)。
  
 **在 Office 365 导入服务中创建导入作业需要哪些权限？**
  
您必须在 Exchange 联机中分配邮箱导入导出角色才能将 PST 文件导入 Office 365 邮箱。 默认情况下，此角色不会分配给 Exchange 联机中的任何角色组。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. 有关详细信息，请参阅[Exchange 联机管理角色组中](https://go.microsoft.com/fwlink/p/?LinkId=730688)的"将角色添加到角色组"或"创建角色组"部分。
  
此外，要在安全&合规中心创建导入作业，以下必须为 true：
  
- 您必须在"联机交换"中分配邮件收件人角色。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    或
    
- 您必须是 Office 365 组织的全局管理员。
    
> [!TIP]
> 请考虑在 Exchange Online 中创建新的角色组，该角色组专门用于将 PST 文件导入 Office 365。 对于导入 PST 文件所需的最低权限级别，将邮箱导入导入和邮件收件人角色分配给新角色组，然后添加成员。 
  
 **网络上传在哪里可用？**
  
网络上传目前在美国、加拿大、巴西、英国、法国、欧洲、印度、东亚、东南亚、日本、大韩民国和澳大利亚提供。 Network upload will be available in more regions soon.
  
 **What is the pricing for importing PST files by using network upload?**
  
Using network upload to import PST files is free.
  
这也意味着，从 Azure 存储区域中删除 PST 文件后，这些文件将不再显示在 Microsoft 365 管理中心已完成导入作业的文件列表中。 尽管导入作业可能仍列在 Office **365 的"导入数据"** 页上，但当您查看较旧的导入作业的详细信息时，PST 文件列表可能为空。 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. 但是，使用 ANSI PST 文件格式的文件（如使用双字节字符集 （DBCS） 的语言的文件）也可以导入 Office 365。 有关导入 ANSI PST 文件的详细信息，请参阅使用网络上载中的步骤 4[将组织的 PST 文件导入 Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)。
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **将 PST 文件上载到 Azure 存储区域后，这些文件在删除之前在 Azure 中保留多长时间？**
  
使用网络上载方法导入 PST 文件时，会将它们上载到**名为"引入数据**"的 Azure blob 容器。 如果安全&合规性**中心的"导入"** 页上没有正在进行的导入作业，则 Azure 中的**引入数据**容器中的所有 PST 文件都将在"安全&中创建最新导入作业 30 天后删除合规中心。 这也意味着您必须在将 PST 文件上载到 Azure 后的 30 天内，在安全&合规性中心（在网络上载说明中的步骤 5 中所述）中创建新的导入作业。 
  
这也意味着，从 Azure 存储区域中删除 PST 文件后，这些文件将不再显示在安全&合规性中心已完成导入作业的文件列表中。 尽管导入作业可能仍列在"安全&合规性中心"**的"导入"** 页上，但当您查看较旧的导入作业的详细信息时，PST 文件列表可能为空。 
  
 **将 PST 文件导入邮箱需要多长时间？**
  
It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization. 将 PST 文件复制到 Azure 存储区域后，PST 文件将以每天至少 24 GB 的速率导入 Office 365 邮箱。 如果此速率不符合您的需要，您可以考虑其他方法将电子邮件数据迁移到 Office 365。 有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法。](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. 同样，如果将多个 PST 文件导入同一邮箱，则它们将同时导入。
  
 **Is there a message size limit when importing PST files?**
  
是。 如果 PST 文件包含大于 150 MB 的邮箱项目，则该项目将在导入过程中跳过。
  
 **将 PST 文件导入 Office 365 邮箱时，邮件属性（如邮件发送或接收时）是否保留收件人列表和其他属性？**
  
是。 原始消息元数据在导入过程中不会更改。
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use network upload to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available. 
  
 **Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **我可以使用网络上传将 PST 文件导入联机交换中的公用文件夹？**
  
否，不能将 PST 文件导入公用文件夹。
  
## <a name="using-drive-shipping-to-import-pst-files"></a>使用驱动器传送导入 PST 文件

有关分步说明，请参阅[使用驱动器传送将 PST 文件导入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)。
  
 **在 Office 365 导入服务中创建导入作业需要哪些权限？**
  
您必须分配邮箱导入导出角色才能将 PST 文件导入 Office 365 邮箱。 默认情况下，此角色不会分配给 Exchange 联机中的任何角色组。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. 有关详细信息，请参阅[Exchange 联机管理角色组中](https://go.microsoft.com/fwlink/p/?LinkId=730688)的"将角色添加到角色组"或"创建角色组"部分。
  
此外，要在安全&合规中心创建导入作业，以下必须为 true：
  
- 您必须在"联机交换"中分配邮件收件人角色。 By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    或
    
- 您必须是 Office 365 组织的全局管理员。
    
> [!TIP]
> 请考虑在 Exchange Online 中创建新的角色组，该角色组专门用于将 PST 文件导入 Office 365。 对于导入 PST 文件所需的最低权限级别，将邮箱导入导入和邮件收件人角色分配给新角色组，然后添加成员。 
  
 **驱动器运输在哪里可用？**
  
驱动器运输目前在美国、加拿大、巴西、英国、欧洲、印度、东亚、东南亚、日本、大韩民国和澳大利亚提供。 Drive shipping will be available in more regions soon.
  
 **What commercial licensing agreements support drive shipping?**
  
通过 Microsoft 企业协议 （EA） 提供将 PST 文件导入 Office 365 的驱动器传送。 驱动器发货无法通过 Microsoft 产品和服务协议 （MPSA） 获得。
  
 **使用驱动器传送将 PST 文件导入 Office 365 的定价是多少？**
  
The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. 有关查找合作伙伴的信息，请参阅查找[Office 365 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。
  
 **What kind of hard drives are supported for drive shipping?**
  
仅支持 2.5 英寸固态驱动器 （SSD） 或 2.5 或 3.5 英寸 SATA II/III 内部硬盘驱动器，以便与 Office 365 导入服务一起使用。 You can use hard drives up to 10 TB. 对于导入作业，将仅处理硬盘上的第一个数据卷。 The data volume must be formatted with NTFS. 将数据复制到硬盘时，可以使用 2.5 英寸 SSD 或 2.5 或 3.5 英寸 SATA II/III 连接器直接连接数据，也可以使用外部 2.5 英寸 SSD 或 2.5 英寸或 3.5 英寸 SATA II/III USB 适配器将其外部连接。
  
> [!IMPORTANT]
> Office 365 导入服务不支持内置 USB 适配器附带的外部硬盘驱动器。 Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives. 
  
 **How many hard drives can I ship for a single import job?**
  
You can ship a maximum of 10 hard drives for a single import job.
  
 **After I ship my hard drive, how long does it take to get to the Microsoft data center?**
  
That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.
  
 **我的硬盘到达 Microsoft 数据中心后，需要多长时间才能将我的 PST 文件上载到 Azure？**
  
在 Microsoft 数据中心收到硬盘后，需要 7 到 10 个工作日才能将 PST 文件上载到组织的 Microsoft Azure 存储区域。 PST 文件将上载到名为**引入数据的**Azure blob 容器。 
  
 **将 PST 文件导入邮箱需要多长时间？**
  
PST 文件上载到 Azure 存储区域后，Office 365 将分析 PST 文件中的数据（以安全可靠的方式），以标识 PST 文件中包括的项目和不同消息类型的年龄。 完成此分析后，您可以选择导入 PST 文件中的所有数据，或将筛选器设置为控制导入的数据。 启动导入作业后，PST 文件以每天至少 24 GB 的速率导入 Office 365 邮箱。 如果此速率不符合您的需要，您可以考虑其他方法将电子邮件数据导入 Office 365。 有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法。](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)
  
If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously. 同样，如果将多个 PST 文件导入同一邮箱，则它们将同时导入。
  
 **Microsoft 将我的 PST 文件上载到 Azure 后，这些文件在删除之前在 Azure 中保留多长时间？**
  
组织的 Azure 存储位置中的所有 PST 文件（在名为**引入数据的**blob 容器中）都将在安全&合规性**中心的"导入"** 页上创建最新导入作业 30 天后删除。 
  
这也意味着，从 Azure 存储区域中删除 PST 文件后，这些文件将不再显示在安全&合规性中心已完成导入作业的文件列表中。 尽管导入作业可能仍列在"安全&合规性中心"**的"导入"** 页上，但当您查看较旧的导入作业的详细信息时，PST 文件列表可能为空。 
  
 **What version of the PST file format is supported for importing to Office 365?**
  
There are two versions of the PST file format: ANSI and Unicode. We recommend importing files that use the Unicode PST file format. 但是，使用 ANSI PST 文件格式的文件（如使用双字节字符集 （DBCS） 的语言的文件）也可以导入 Office 365。 有关导入 ANSI PST 文件的详细信息，请参阅[使用驱动器传送中的步骤 3 将 PST 文件导入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)。
  
Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.
  
 **Is there a message size limit when importing PST files?**
  
是。 如果 PST 文件包含大于 150 MB 的邮箱项目，则该项目将在导入过程中跳过。
  
 **将 PST 文件导入 Office 365 邮箱时，邮件属性（如邮件发送或接收时）是否保留收件人列表和其他属性？**
  
是。 原始消息元数据在导入过程中不会更改
  
 **Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**
  
Yes. You can't import a PST file that has 300 or more levels of nested folders.
  
 **Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**
  
Yes, this capability is now available.
  
 **Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**
  
Yes, this capability is now available. 
  
 **我可以使用驱动器传送将 PST 文件导入联机交换中的公用文件夹？**
  
否，不能将 PST 文件导入公用文件夹。
  
 **Can Microsoft wipe my hard drive before they ship it back to me?**
  
No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **微软可以粉碎我的硬盘，而不是把它运回给我吗？**
  
No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.
  
 **退货运输支持哪些快递服务？**
  
If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.
  
 **退货运费是多少？**
  
Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.
  
 **我可以使用自定义快递运输服务（如联邦快递定制运输）将硬盘运送到微软吗？**
  
是。
  
 **If I have to ship my hard drive to another country, is there anything I need to do?**
  
The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.
