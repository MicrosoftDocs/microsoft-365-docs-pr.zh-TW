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
# <a name="faq-about-importing-pst-files-to-office-365"></a><span data-ttu-id="f261e-103">有关将 PST 文件导入 Office 365 的常见问题解答</span><span class="sxs-lookup"><span data-stu-id="f261e-103">FAQ about importing PST files to Office 365</span></span>

<span data-ttu-id="f261e-104">**本文是为管理员。是否要将 PST 文件导入您自己的邮箱？请参阅[从 Outlook .pst 文件导入电子邮件、联系人和日历](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span><span class="sxs-lookup"><span data-stu-id="f261e-104">**This article is for administrators. Do you want to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span></span>
   
<span data-ttu-id="f261e-105">以下是有关使用 Office 365 导入服务将 PST 文件批量导入 Office 365 邮箱的一些常见问题。</span><span class="sxs-lookup"><span data-stu-id="f261e-105">Here are some frequently asked questions about using the Office 365 Import Service to bulk-import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="f261e-106">有关如何导入 PST 文件的详细信息，请参阅将[PST 文件导入 Office 365 的概述。](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)</span><span class="sxs-lookup"><span data-stu-id="f261e-106">For more information about how to import PST files, see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).</span></span>
  
## <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="f261e-107">使用网络上传导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="f261e-107">Using network upload to import PST files</span></span>

<span data-ttu-id="f261e-108">有关分步说明，请参阅[使用网络上载将 PST 文件导入 Office 365](use-network-upload-to-import-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="f261e-108">For step-by-step instructions, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
  
 <span data-ttu-id="f261e-109">**在 Office 365 导入服务中创建导入作业需要哪些权限？**</span><span class="sxs-lookup"><span data-stu-id="f261e-109">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="f261e-110">您必须在 Exchange 联机中分配邮箱导入导出角色才能将 PST 文件导入 Office 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="f261e-110">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="f261e-111">默认情况下，此角色不会分配给 Exchange 联机中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="f261e-111">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="f261e-112">You can add the Mailbox Import Export role to the Organization Management role group.</span><span class="sxs-lookup"><span data-stu-id="f261e-112">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="f261e-113">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span><span class="sxs-lookup"><span data-stu-id="f261e-113">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="f261e-114">有关详细信息，请参阅[Exchange 联机管理角色组中](https://go.microsoft.com/fwlink/p/?LinkId=730688)的"将角色添加到角色组"或"创建角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="f261e-114">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="f261e-115">此外，要在安全&合规中心创建导入作业，以下必须为 true：</span><span class="sxs-lookup"><span data-stu-id="f261e-115">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="f261e-116">您必须在"联机交换"中分配邮件收件人角色。</span><span class="sxs-lookup"><span data-stu-id="f261e-116">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="f261e-117">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span><span class="sxs-lookup"><span data-stu-id="f261e-117">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="f261e-118">或</span><span class="sxs-lookup"><span data-stu-id="f261e-118">Or</span></span>
    
- <span data-ttu-id="f261e-119">您必须是 Office 365 组织的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="f261e-119">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="f261e-120">请考虑在 Exchange Online 中创建新的角色组，该角色组专门用于将 PST 文件导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f261e-120">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="f261e-121">对于导入 PST 文件所需的最低权限级别，将邮箱导入导入和邮件收件人角色分配给新角色组，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="f261e-121">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="f261e-122">**网络上传在哪里可用？**</span><span class="sxs-lookup"><span data-stu-id="f261e-122">**Where is network upload available?**</span></span>
  
<span data-ttu-id="f261e-123">网络上传目前在美国、加拿大、巴西、英国、法国、欧洲、印度、东亚、东南亚、日本、大韩民国和澳大利亚提供。</span><span class="sxs-lookup"><span data-stu-id="f261e-123">Network upload is currently available in the United States, Canada, Brazil, the United Kingdom, France, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="f261e-124">Network upload will be available in more regions soon.</span><span class="sxs-lookup"><span data-stu-id="f261e-124">Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="f261e-125">**What is the pricing for importing PST files by using network upload?**</span><span class="sxs-lookup"><span data-stu-id="f261e-125">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="f261e-126">Using network upload to import PST files is free.</span><span class="sxs-lookup"><span data-stu-id="f261e-126">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="f261e-127">这也意味着，从 Azure 存储区域中删除 PST 文件后，这些文件将不再显示在 Microsoft 365 管理中心已完成导入作业的文件列表中。</span><span class="sxs-lookup"><span data-stu-id="f261e-127">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f261e-128">尽管导入作业可能仍列在 Office **365 的"导入数据"** 页上，但当您查看较旧的导入作业的详细信息时，PST 文件列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="f261e-128">Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="f261e-129">**What version of the PST file format is supported for importing to Office 365?**</span><span class="sxs-lookup"><span data-stu-id="f261e-129">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="f261e-130">There are two versions of the PST file format: ANSI and Unicode.</span><span class="sxs-lookup"><span data-stu-id="f261e-130">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="f261e-131">We recommend importing files that use the Unicode PST file format.</span><span class="sxs-lookup"><span data-stu-id="f261e-131">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="f261e-132">但是，使用 ANSI PST 文件格式的文件（如使用双字节字符集 （DBCS） 的语言的文件）也可以导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f261e-132">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="f261e-133">有关导入 ANSI PST 文件的详细信息，请参阅使用网络上载中的步骤 4[将组织的 PST 文件导入 Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)。</span><span class="sxs-lookup"><span data-stu-id="f261e-133">For more information about importing ANSI PST files, see Step 4 in [Use network upload to import your organization's PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="f261e-134">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span><span class="sxs-lookup"><span data-stu-id="f261e-134">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="f261e-135">**将 PST 文件上载到 Azure 存储区域后，这些文件在删除之前在 Azure 中保留多长时间？**</span><span class="sxs-lookup"><span data-stu-id="f261e-135">**After I upload my PST files to the Azure storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="f261e-136">使用网络上载方法导入 PST 文件时，会将它们上载到**名为"引入数据**"的 Azure blob 容器。</span><span class="sxs-lookup"><span data-stu-id="f261e-136">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**.</span></span> <span data-ttu-id="f261e-137">如果安全&合规性**中心的"导入"** 页上没有正在进行的导入作业，则 Azure 中的**引入数据**容器中的所有 PST 文件都将在"安全&中创建最新导入作业 30 天后删除合规中心。</span><span class="sxs-lookup"><span data-stu-id="f261e-137">If there are no import jobs in progress on the **Import** page in the Security & Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security & Compliance Center.</span></span> <span data-ttu-id="f261e-138">这也意味着您必须在将 PST 文件上载到 Azure 后的 30 天内，在安全&合规性中心（在网络上载说明中的步骤 5 中所述）中创建新的导入作业。</span><span class="sxs-lookup"><span data-stu-id="f261e-138">That also means you have to create a new import job in the Security & Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="f261e-139">这也意味着，从 Azure 存储区域中删除 PST 文件后，这些文件将不再显示在安全&合规性中心已完成导入作业的文件列表中。</span><span class="sxs-lookup"><span data-stu-id="f261e-139">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="f261e-140">尽管导入作业可能仍列在"安全&合规性中心"**的"导入"** 页上，但当您查看较旧的导入作业的详细信息时，PST 文件列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="f261e-140">Although an import job might still be listed on the **Import** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="f261e-141">**将 PST 文件导入邮箱需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="f261e-141">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="f261e-142">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization.</span><span class="sxs-lookup"><span data-stu-id="f261e-142">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure storage area for your organization.</span></span> <span data-ttu-id="f261e-143">将 PST 文件复制到 Azure 存储区域后，PST 文件将以每天至少 24 GB 的速率导入 Office 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="f261e-143">After the PST files are copied to the Azure storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="f261e-144">如果此速率不符合您的需要，您可以考虑其他方法将电子邮件数据迁移到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f261e-144">If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365.</span></span> <span data-ttu-id="f261e-145">有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法。](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)</span><span class="sxs-lookup"><span data-stu-id="f261e-145">For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="f261e-146">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span><span class="sxs-lookup"><span data-stu-id="f261e-146">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="f261e-147">同样，如果将多个 PST 文件导入同一邮箱，则它们将同时导入。</span><span class="sxs-lookup"><span data-stu-id="f261e-147">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="f261e-148">**Is there a message size limit when importing PST files?**</span><span class="sxs-lookup"><span data-stu-id="f261e-148">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="f261e-149">是。</span><span class="sxs-lookup"><span data-stu-id="f261e-149">Yes.</span></span> <span data-ttu-id="f261e-150">如果 PST 文件包含大于 150 MB 的邮箱项目，则该项目将在导入过程中跳过。</span><span class="sxs-lookup"><span data-stu-id="f261e-150">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="f261e-151">**将 PST 文件导入 Office 365 邮箱时，邮件属性（如邮件发送或接收时）是否保留收件人列表和其他属性？**</span><span class="sxs-lookup"><span data-stu-id="f261e-151">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="f261e-152">是。</span><span class="sxs-lookup"><span data-stu-id="f261e-152">Yes.</span></span> <span data-ttu-id="f261e-153">原始消息元数据在导入过程中不会更改。</span><span class="sxs-lookup"><span data-stu-id="f261e-153">The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="f261e-154">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span><span class="sxs-lookup"><span data-stu-id="f261e-154">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="f261e-p114">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span><span class="sxs-lookup"><span data-stu-id="f261e-p114">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="f261e-157">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span><span class="sxs-lookup"><span data-stu-id="f261e-157">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="f261e-158">Yes, this capability is now available. </span><span class="sxs-lookup"><span data-stu-id="f261e-158">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="f261e-159">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span><span class="sxs-lookup"><span data-stu-id="f261e-159">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="f261e-160">Yes, this capability is now available. </span><span class="sxs-lookup"><span data-stu-id="f261e-160">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="f261e-161">**我可以使用网络上传将 PST 文件导入联机交换中的公用文件夹？**</span><span class="sxs-lookup"><span data-stu-id="f261e-161">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="f261e-162">否，不能将 PST 文件导入公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="f261e-162">No, you can't import PST files to public folders.</span></span>
  
## <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="f261e-163">使用驱动器传送导入 PST 文件</span><span class="sxs-lookup"><span data-stu-id="f261e-163">Using drive shipping to import PST files</span></span>

<span data-ttu-id="f261e-164">有关分步说明，请参阅[使用驱动器传送将 PST 文件导入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="f261e-164">For step-by-step instructions, see [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).</span></span>
  
 <span data-ttu-id="f261e-165">**在 Office 365 导入服务中创建导入作业需要哪些权限？**</span><span class="sxs-lookup"><span data-stu-id="f261e-165">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="f261e-166">您必须分配邮箱导入导出角色才能将 PST 文件导入 Office 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="f261e-166">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="f261e-167">默认情况下，此角色不会分配给 Exchange 联机中的任何角色组。</span><span class="sxs-lookup"><span data-stu-id="f261e-167">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="f261e-168">You can add the Mailbox Import Export role to the Organization Management role group.</span><span class="sxs-lookup"><span data-stu-id="f261e-168">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="f261e-169">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span><span class="sxs-lookup"><span data-stu-id="f261e-169">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="f261e-170">有关详细信息，请参阅[Exchange 联机管理角色组中](https://go.microsoft.com/fwlink/p/?LinkId=730688)的"将角色添加到角色组"或"创建角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="f261e-170">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="f261e-171">此外，要在安全&合规中心创建导入作业，以下必须为 true：</span><span class="sxs-lookup"><span data-stu-id="f261e-171">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="f261e-172">您必须在"联机交换"中分配邮件收件人角色。</span><span class="sxs-lookup"><span data-stu-id="f261e-172">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="f261e-173">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span><span class="sxs-lookup"><span data-stu-id="f261e-173">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="f261e-174">或</span><span class="sxs-lookup"><span data-stu-id="f261e-174">Or</span></span>
    
- <span data-ttu-id="f261e-175">您必须是 Office 365 组织的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="f261e-175">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="f261e-176">请考虑在 Exchange Online 中创建新的角色组，该角色组专门用于将 PST 文件导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f261e-176">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="f261e-177">对于导入 PST 文件所需的最低权限级别，将邮箱导入导入和邮件收件人角色分配给新角色组，然后添加成员。</span><span class="sxs-lookup"><span data-stu-id="f261e-177">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="f261e-178">**驱动器运输在哪里可用？**</span><span class="sxs-lookup"><span data-stu-id="f261e-178">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="f261e-179">驱动器运输目前在美国、加拿大、巴西、英国、欧洲、印度、东亚、东南亚、日本、大韩民国和澳大利亚提供。</span><span class="sxs-lookup"><span data-stu-id="f261e-179">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="f261e-180">Drive shipping will be available in more regions soon.</span><span class="sxs-lookup"><span data-stu-id="f261e-180">Drive shipping will be available in more regions soon.</span></span>
  
 <span data-ttu-id="f261e-181">**What commercial licensing agreements support drive shipping?**</span><span class="sxs-lookup"><span data-stu-id="f261e-181">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="f261e-182">通过 Microsoft 企业协议 （EA） 提供将 PST 文件导入 Office 365 的驱动器传送。</span><span class="sxs-lookup"><span data-stu-id="f261e-182">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA).</span></span> <span data-ttu-id="f261e-183">驱动器发货无法通过 Microsoft 产品和服务协议 （MPSA） 获得。</span><span class="sxs-lookup"><span data-stu-id="f261e-183">Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="f261e-184">**使用驱动器传送将 PST 文件导入 Office 365 的定价是多少？**</span><span class="sxs-lookup"><span data-stu-id="f261e-184">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="f261e-185">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data.</span><span class="sxs-lookup"><span data-stu-id="f261e-185">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data.</span></span> <span data-ttu-id="f261e-186">For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD.</span><span class="sxs-lookup"><span data-stu-id="f261e-186">For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD.</span></span> <span data-ttu-id="f261e-187">You can work with a partner to pay the import fee.</span><span class="sxs-lookup"><span data-stu-id="f261e-187">You can work with a partner to pay the import fee.</span></span> <span data-ttu-id="f261e-188">有关查找合作伙伴的信息，请参阅查找[Office 365 合作伙伴或经销商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="f261e-188">For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="f261e-189">**What kind of hard drives are supported for drive shipping?**</span><span class="sxs-lookup"><span data-stu-id="f261e-189">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="f261e-190">仅支持 2.5 英寸固态驱动器 （SSD） 或 2.5 或 3.5 英寸 SATA II/III 内部硬盘驱动器，以便与 Office 365 导入服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="f261e-190">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service.</span></span> <span data-ttu-id="f261e-191">You can use hard drives up to 10 TB.</span><span class="sxs-lookup"><span data-stu-id="f261e-191">You can use hard drives up to 10 TB.</span></span> <span data-ttu-id="f261e-192">对于导入作业，将仅处理硬盘上的第一个数据卷。</span><span class="sxs-lookup"><span data-stu-id="f261e-192">For import jobs, only the first data volume on the hard drive will be processed.</span></span> <span data-ttu-id="f261e-193">The data volume must be formatted with NTFS.</span><span class="sxs-lookup"><span data-stu-id="f261e-193">The data volume must be formatted with NTFS.</span></span> <span data-ttu-id="f261e-194">将数据复制到硬盘时，可以使用 2.5 英寸 SSD 或 2.5 或 3.5 英寸 SATA II/III 连接器直接连接数据，也可以使用外部 2.5 英寸 SSD 或 2.5 英寸或 3.5 英寸 SATA II/III USB 适配器将其外部连接。</span><span class="sxs-lookup"><span data-stu-id="f261e-194">When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f261e-195">Office 365 导入服务不支持内置 USB 适配器附带的外部硬盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="f261e-195">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service.</span></span> <span data-ttu-id="f261e-196">Additionally, the disk inside the casing of an external hard drive can't be used.</span><span class="sxs-lookup"><span data-stu-id="f261e-196">Additionally, the disk inside the casing of an external hard drive can't be used.</span></span> <span data-ttu-id="f261e-197">Please don't ship external hard drives.</span><span class="sxs-lookup"><span data-stu-id="f261e-197">Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="f261e-198">**How many hard drives can I ship for a single import job?**</span><span class="sxs-lookup"><span data-stu-id="f261e-198">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="f261e-199">You can ship a maximum of 10 hard drives for a single import job.</span><span class="sxs-lookup"><span data-stu-id="f261e-199">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="f261e-200">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span><span class="sxs-lookup"><span data-stu-id="f261e-200">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="f261e-p123">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span><span class="sxs-lookup"><span data-stu-id="f261e-p123">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="f261e-203">**我的硬盘到达 Microsoft 数据中心后，需要多长时间才能将我的 PST 文件上载到 Azure？**</span><span class="sxs-lookup"><span data-stu-id="f261e-203">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="f261e-204">在 Microsoft 数据中心收到硬盘后，需要 7 到 10 个工作日才能将 PST 文件上载到组织的 Microsoft Azure 存储区域。</span><span class="sxs-lookup"><span data-stu-id="f261e-204">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Microsoft Azure storage area for your organization.</span></span> <span data-ttu-id="f261e-205">PST 文件将上载到名为**引入数据的**Azure blob 容器。</span><span class="sxs-lookup"><span data-stu-id="f261e-205">The PST files will be uploaded to a Azure blob container named **ingestiondata**.</span></span> 
  
 <span data-ttu-id="f261e-206">**将 PST 文件导入邮箱需要多长时间？**</span><span class="sxs-lookup"><span data-stu-id="f261e-206">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="f261e-207">PST 文件上载到 Azure 存储区域后，Office 365 将分析 PST 文件中的数据（以安全可靠的方式），以标识 PST 文件中包括的项目和不同消息类型的年龄。</span><span class="sxs-lookup"><span data-stu-id="f261e-207">After the PST files are uploaded to the Azure storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="f261e-208">完成此分析后，您可以选择导入 PST 文件中的所有数据，或将筛选器设置为控制导入的数据。</span><span class="sxs-lookup"><span data-stu-id="f261e-208">When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported.</span></span> <span data-ttu-id="f261e-209">启动导入作业后，PST 文件以每天至少 24 GB 的速率导入 Office 365 邮箱。</span><span class="sxs-lookup"><span data-stu-id="f261e-209">After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="f261e-210">如果此速率不符合您的需要，您可以考虑其他方法将电子邮件数据导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f261e-210">If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365.</span></span> <span data-ttu-id="f261e-211">有关详细信息，请参阅[将多个电子邮件帐户迁移到 Office 365 的方法。](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)</span><span class="sxs-lookup"><span data-stu-id="f261e-211">For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="f261e-212">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span><span class="sxs-lookup"><span data-stu-id="f261e-212">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="f261e-213">同样，如果将多个 PST 文件导入同一邮箱，则它们将同时导入。</span><span class="sxs-lookup"><span data-stu-id="f261e-213">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="f261e-214">**Microsoft 将我的 PST 文件上载到 Azure 后，这些文件在删除之前在 Azure 中保留多长时间？**</span><span class="sxs-lookup"><span data-stu-id="f261e-214">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="f261e-215">组织的 Azure 存储位置中的所有 PST 文件（在名为**引入数据的**blob 容器中）都将在安全&合规性**中心的"导入"** 页上创建最新导入作业 30 天后删除。</span><span class="sxs-lookup"><span data-stu-id="f261e-215">All PST files in the Azure storage location for your organization (in blob container named **ingestiondata** ), are deleted 30 days after the most recent import job was created on the **Import** page in the Security & Compliance Center.</span></span> 
  
<span data-ttu-id="f261e-216">这也意味着，从 Azure 存储区域中删除 PST 文件后，这些文件将不再显示在安全&合规性中心已完成导入作业的文件列表中。</span><span class="sxs-lookup"><span data-stu-id="f261e-216">This also means that after PST files are deleted from the Azure storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="f261e-217">尽管导入作业可能仍列在"安全&合规性中心"**的"导入"** 页上，但当您查看较旧的导入作业的详细信息时，PST 文件列表可能为空。</span><span class="sxs-lookup"><span data-stu-id="f261e-217">Although an import job might still be listed on the **Import** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="f261e-218">**What version of the PST file format is supported for importing to Office 365?**</span><span class="sxs-lookup"><span data-stu-id="f261e-218">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="f261e-219">There are two versions of the PST file format: ANSI and Unicode.</span><span class="sxs-lookup"><span data-stu-id="f261e-219">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="f261e-220">We recommend importing files that use the Unicode PST file format.</span><span class="sxs-lookup"><span data-stu-id="f261e-220">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="f261e-221">但是，使用 ANSI PST 文件格式的文件（如使用双字节字符集 （DBCS） 的语言的文件）也可以导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="f261e-221">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="f261e-222">有关导入 ANSI PST 文件的详细信息，请参阅[使用驱动器传送中的步骤 3 将 PST 文件导入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)。</span><span class="sxs-lookup"><span data-stu-id="f261e-222">For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="f261e-223">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span><span class="sxs-lookup"><span data-stu-id="f261e-223">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="f261e-224">**Is there a message size limit when importing PST files?**</span><span class="sxs-lookup"><span data-stu-id="f261e-224">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="f261e-225">是。</span><span class="sxs-lookup"><span data-stu-id="f261e-225">Yes.</span></span> <span data-ttu-id="f261e-226">如果 PST 文件包含大于 150 MB 的邮箱项目，则该项目将在导入过程中跳过。</span><span class="sxs-lookup"><span data-stu-id="f261e-226">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="f261e-227">**将 PST 文件导入 Office 365 邮箱时，邮件属性（如邮件发送或接收时）是否保留收件人列表和其他属性？**</span><span class="sxs-lookup"><span data-stu-id="f261e-227">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="f261e-228">是。</span><span class="sxs-lookup"><span data-stu-id="f261e-228">Yes.</span></span> <span data-ttu-id="f261e-229">原始消息元数据在导入过程中不会更改</span><span class="sxs-lookup"><span data-stu-id="f261e-229">The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="f261e-230">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span><span class="sxs-lookup"><span data-stu-id="f261e-230">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="f261e-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span><span class="sxs-lookup"><span data-stu-id="f261e-p131">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="f261e-233">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span><span class="sxs-lookup"><span data-stu-id="f261e-233">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="f261e-234">Yes, this capability is now available.</span><span class="sxs-lookup"><span data-stu-id="f261e-234">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="f261e-235">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span><span class="sxs-lookup"><span data-stu-id="f261e-235">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="f261e-236">Yes, this capability is now available. </span><span class="sxs-lookup"><span data-stu-id="f261e-236">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="f261e-237">**我可以使用驱动器传送将 PST 文件导入联机交换中的公用文件夹？**</span><span class="sxs-lookup"><span data-stu-id="f261e-237">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="f261e-238">否，不能将 PST 文件导入公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="f261e-238">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="f261e-239">**Can Microsoft wipe my hard drive before they ship it back to me?**</span><span class="sxs-lookup"><span data-stu-id="f261e-239">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="f261e-p132">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f261e-p132">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="f261e-242">**微软可以粉碎我的硬盘，而不是把它运回给我吗？**</span><span class="sxs-lookup"><span data-stu-id="f261e-242">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="f261e-p133">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f261e-p133">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="f261e-245">**退货运输支持哪些快递服务？**</span><span class="sxs-lookup"><span data-stu-id="f261e-245">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="f261e-p134">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span><span class="sxs-lookup"><span data-stu-id="f261e-p134">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="f261e-248">**退货运费是多少？**</span><span class="sxs-lookup"><span data-stu-id="f261e-248">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="f261e-p135">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span><span class="sxs-lookup"><span data-stu-id="f261e-p135">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="f261e-252">**我可以使用自定义快递运输服务（如联邦快递定制运输）将硬盘运送到微软吗？**</span><span class="sxs-lookup"><span data-stu-id="f261e-252">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="f261e-253">是。</span><span class="sxs-lookup"><span data-stu-id="f261e-253">Yes.</span></span>
  
 <span data-ttu-id="f261e-254">**If I have to ship my hard drive to another country, is there anything I need to do?**</span><span class="sxs-lookup"><span data-stu-id="f261e-254">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="f261e-p136">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span><span class="sxs-lookup"><span data-stu-id="f261e-p136">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
