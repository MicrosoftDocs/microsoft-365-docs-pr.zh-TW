---
title: 与合作伙伴合作，在 Office 365 中存档第三方数据
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 您的组织可以与 Microsoft 合作伙伴合作，设置自定义连接器，以便从数据源（如 Salesforce Chatter、Yahoo Messenger 或 Yammer）导入第三方数据。 这使您可以在 Office 365 中存档来自第三方数据源的数据，以便您可以使用 Office 365 合规性功能（如法律保留、内容搜索和保留策略）来管理组织第三方数据的治理。
ms.openlocfilehash: a22b4226efb582969072bbd92149080cca9b749c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077633"
---
# <a name="work-with-a-partner-to-archive-third-party-data-in-office-365"></a><span data-ttu-id="753d2-104">与合作伙伴合作，在 Office 365 中存档第三方数据</span><span class="sxs-lookup"><span data-stu-id="753d2-104">Work with a partner to archive third-party data in Office 365</span></span>

<span data-ttu-id="753d2-105">您可以与 Microsoft 合作伙伴合作，将数据从第三方数据源导入 Office 365 并将其存档。</span><span class="sxs-lookup"><span data-stu-id="753d2-105">You can work with a Microsoft Partner to import and archive data from a third-party data source to Office 365.</span></span> <span data-ttu-id="753d2-106">合作伙伴可以为您提供一个自定义连接器，该连接器配置为从第三方数据源中提取项目（定期），然后将这些项目导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="753d2-106">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items to Office 365.</span></span> <span data-ttu-id="753d2-107">合作伙伴连接器将项目的内容从数据源转换为电子邮件格式，然后将项目存储在 Office 365 中的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="753d2-107">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes in Office 365.</span></span> <span data-ttu-id="753d2-108">导入第三方数据后，您可以将 Office 365 合规性功能（如诉讼保留、内容搜索、就地存档、审核和 Office 365 保留策略）应用于此数据。</span><span class="sxs-lookup"><span data-stu-id="753d2-108">After third-party data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies to this data.</span></span>
  
<span data-ttu-id="753d2-109">以下是与 Microsoft 合作伙伴合作将第三方数据导入 Office 365 的过程和必要步骤的概述。</span><span class="sxs-lookup"><span data-stu-id="753d2-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data to Office 365.</span></span>

[<span data-ttu-id="753d2-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="753d2-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="753d2-111">Step 2: Create and configure a third-party data mailbox in Office 365</span><span class="sxs-lookup"><span data-stu-id="753d2-111">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="753d2-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="753d2-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="753d2-113">步驟 4：提供資訊給合作夥伴</span><span class="sxs-lookup"><span data-stu-id="753d2-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="753d2-114">步骤 5：在 Azure 活动目录中注册第三方数据连接器</span><span class="sxs-lookup"><span data-stu-id="753d2-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="753d2-115">協力廠商資料匯入程序的運作方式</span><span class="sxs-lookup"><span data-stu-id="753d2-115">How the third-party data import process works</span></span>

<span data-ttu-id="753d2-116">下图和说明说明了第三方数据导入过程在与合作伙伴合作时的工作原理。</span><span class="sxs-lookup"><span data-stu-id="753d2-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![協力廠商資料匯入程序的運作方式](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="753d2-118">客户与其选择的合作伙伴合作，配置一个连接器，该连接器将从第三方数据源中提取项目，然后将这些项目导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="753d2-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="753d2-119">合作伙伴连接器通过第三方 API（按计划或按配置）连接到第三方数据源，并从数据源中提取项目。</span><span class="sxs-lookup"><span data-stu-id="753d2-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="753d2-120">協力廠商連接器會將項目的內容轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="753d2-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="753d2-121">有关消息格式架构的说明，请参阅[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="753d2-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="753d2-122">合作伙伴连接器通过已知终结点使用 Exchange Web 服务 （EWS） 连接到 Office 365 中的 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="753d2-122">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="753d2-p104">項目是匯入至特定使用者的信箱或「全部擷取」協力廠商資料信箱。項目匯入至特定使用者信箱還是協力廠商資料信箱，是根據下列準則：</span><span class="sxs-lookup"><span data-stu-id="753d2-p104">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="753d2-125">a.</span><span class="sxs-lookup"><span data-stu-id="753d2-125">a.</span></span> <span data-ttu-id="753d2-126">**具有对应于 Office 365 用户帐户的用户 ID 的项目：** 如果合作伙伴连接器可以将第三方数据源中项的用户 ID 映射到 Office 365 中的特定用户 ID，则该项目将复制到用户的"可恢复项目"文件夹中**的"清除"** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="753d2-126">**Items that have a user ID that corresponds to an Office 365 user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="753d2-127">使用者無法存取 [清除] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="753d2-127">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="753d2-128">但是，您可以使用 Office 365 电子数据展示工具在"清除"文件夹中搜索项目。</span><span class="sxs-lookup"><span data-stu-id="753d2-128">However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="753d2-129">b.</span><span class="sxs-lookup"><span data-stu-id="753d2-129">b.</span></span> <span data-ttu-id="753d2-130">**没有与 Office 365 用户帐户对应的用户 ID 的项目：** 如果合作伙伴连接器无法将项目的用户 ID 映射到 Office 365 中的特定用户 ID，则该项目将复制到第三方数据邮箱的**收件箱**文件夹。</span><span class="sxs-lookup"><span data-stu-id="753d2-130">**Items that don't have a user ID that corresponds to an Office 365 user account:** If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="753d2-131">將項目匯入至收件匣可讓您或組織中的某個人登入協力廠商信箱來檢視和管理這些項目，並查看是否需要在協力廠商連接器組態中進行任何調整。</span><span class="sxs-lookup"><span data-stu-id="753d2-131">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="753d2-132">步驟 1：尋找協力廠商資料合作夥伴</span><span class="sxs-lookup"><span data-stu-id="753d2-132">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="753d2-133">在 Office 365 中存档第三方数据的一个关键组件是查找并与其合作的 Microsoft 合作伙伴，该合作伙伴专门捕获来自第三方数据源的数据并将其导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="753d2-133">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="753d2-134">导入数据后，可以将其与组织的其他 Microsoft 数据一起存档和保存，例如来自 Exchange 的电子邮件和来自 SharePoint 和 OneDrive 的业务文档。</span><span class="sxs-lookup"><span data-stu-id="753d2-134">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="753d2-135">合作伙伴创建一个连接器，从组织的第三方数据源（如黑莓、Facebook、Google+、汤森路透、Twitter 和 YouTube）中提取数据，并将这些数据传递到 Office 365 API，该 API 将项目导入到 Exchange 邮箱（作为电子邮件。</span><span class="sxs-lookup"><span data-stu-id="753d2-135">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="753d2-136">以下部分列出了参与 Office 365 中存档第三方数据的计划的 Microsoft 合作伙伴（以及他们支持的第三方数据源）。</span><span class="sxs-lookup"><span data-stu-id="753d2-136">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="753d2-137">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="753d2-137">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="753d2-138">存档社交</span><span class="sxs-lookup"><span data-stu-id="753d2-138">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="753d2-139">格洛巴内</span><span class="sxs-lookup"><span data-stu-id="753d2-139">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="753d2-140">OpenText</span><span class="sxs-lookup"><span data-stu-id="753d2-140">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="753d2-141">斯马什</span><span class="sxs-lookup"><span data-stu-id="753d2-141">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="753d2-142">韦尔巴</span><span class="sxs-lookup"><span data-stu-id="753d2-142">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="753d2-143">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="753d2-143">17a-4 LLC</span></span>

<span data-ttu-id="753d2-144">[17a-4 LLC](https://www.17a-4.com)支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="753d2-144">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="753d2-145">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="753d2-145">BlackBerry</span></span>
    
- <span data-ttu-id="753d2-146">Bloomberg 資料流</span><span class="sxs-lookup"><span data-stu-id="753d2-146">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="753d2-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="753d2-147">Cisco Jabber</span></span>
    
- <span data-ttu-id="753d2-148">事实集</span><span class="sxs-lookup"><span data-stu-id="753d2-148">FactSet</span></span>
    
- <span data-ttu-id="753d2-149">嘻哈聊天</span><span class="sxs-lookup"><span data-stu-id="753d2-149">HipChat</span></span>
    
- <span data-ttu-id="753d2-150">投资边缘</span><span class="sxs-lookup"><span data-stu-id="753d2-150">InvestEdge</span></span>
    
- <span data-ttu-id="753d2-151">现场人员</span><span class="sxs-lookup"><span data-stu-id="753d2-151">LivePerson</span></span>
    
- <span data-ttu-id="753d2-152">MessageLabs 資料流</span><span class="sxs-lookup"><span data-stu-id="753d2-152">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="753d2-153">OpenText</span><span class="sxs-lookup"><span data-stu-id="753d2-153">OpenText</span></span>
    
- <span data-ttu-id="753d2-154">Oracle/ATG 'click-to-call' 即時說明</span><span class="sxs-lookup"><span data-stu-id="753d2-154">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="753d2-155">樞紐分析 IMTRADER</span><span class="sxs-lookup"><span data-stu-id="753d2-155">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="753d2-156">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="753d2-156">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="753d2-157">心对齐</span><span class="sxs-lookup"><span data-stu-id="753d2-157">MindAlign</span></span>
    
- <span data-ttu-id="753d2-158">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="753d2-158">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="753d2-159">商務用 Skype (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="753d2-159">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="753d2-160">商務用 Skype Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="753d2-160">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="753d2-161">SQL 資料庫</span><span class="sxs-lookup"><span data-stu-id="753d2-161">SQL Databases</span></span>
    
- <span data-ttu-id="753d2-162">斯夸克</span><span class="sxs-lookup"><span data-stu-id="753d2-162">Squawker</span></span>
    
- <span data-ttu-id="753d2-163">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="753d2-163">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="753d2-164">存档社交</span><span class="sxs-lookup"><span data-stu-id="753d2-164">ArchiveSocial</span></span>

<span data-ttu-id="753d2-165">[存档社交](https://www.archivesocial.com)支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="753d2-165">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="753d2-166">Facebook</span><span class="sxs-lookup"><span data-stu-id="753d2-166">Facebook</span></span>
    
- <span data-ttu-id="753d2-167">Flickr</span><span class="sxs-lookup"><span data-stu-id="753d2-167">Flickr</span></span>
    
- <span data-ttu-id="753d2-168">因斯塔格拉姆</span><span class="sxs-lookup"><span data-stu-id="753d2-168">Instagram</span></span>
    
- <span data-ttu-id="753d2-169">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="753d2-169">LinkedIn</span></span>
    
- <span data-ttu-id="753d2-170">兴趣</span><span class="sxs-lookup"><span data-stu-id="753d2-170">Pinterest</span></span>
    
- <span data-ttu-id="753d2-171">Twitter</span><span class="sxs-lookup"><span data-stu-id="753d2-171">Twitter</span></span>
    
- <span data-ttu-id="753d2-172">Youtube</span><span class="sxs-lookup"><span data-stu-id="753d2-172">YouTube</span></span>
    
- <span data-ttu-id="753d2-173">维梅奥</span><span class="sxs-lookup"><span data-stu-id="753d2-173">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="753d2-174">格洛巴内</span><span class="sxs-lookup"><span data-stu-id="753d2-174">Globanet</span></span>

<span data-ttu-id="753d2-175">[Globanet](https://www.globanet.com)支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="753d2-175">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="753d2-176">含樞紐分析用戶端的 AOL</span><span class="sxs-lookup"><span data-stu-id="753d2-176">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="753d2-177">BlackBerry Call Logs (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="753d2-177">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="753d2-178">BlackBerry Messenger (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="753d2-178">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="753d2-179">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="753d2-179">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="753d2-180">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="753d2-180">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="753d2-181">Bloomberg Chat</span><span class="sxs-lookup"><span data-stu-id="753d2-181">Bloomberg Chat</span></span>
    
- <span data-ttu-id="753d2-182">Bloomberg 郵件</span><span class="sxs-lookup"><span data-stu-id="753d2-182">Bloomberg Mail</span></span>
    
- <span data-ttu-id="753d2-183">Box</span><span class="sxs-lookup"><span data-stu-id="753d2-183">Box</span></span>
    
- <span data-ttu-id="753d2-184">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="753d2-184">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="753d2-185">思科&amp;IM 状态服务器（v10、v10.5.1 SU1、v11.0、v11.5 SU2）</span><span class="sxs-lookup"><span data-stu-id="753d2-185">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="753d2-186">思科 Webex 团队</span><span class="sxs-lookup"><span data-stu-id="753d2-186">Cisco Webex Teams</span></span>

- <span data-ttu-id="753d2-187">Citrix&amp;工作区共享文件</span><span class="sxs-lookup"><span data-stu-id="753d2-187">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="753d2-188">人群通</span><span class="sxs-lookup"><span data-stu-id="753d2-188">CrowdCompass</span></span>

- <span data-ttu-id="753d2-189">自定义分隔的文本文件</span><span class="sxs-lookup"><span data-stu-id="753d2-189">Custom-delimited text files</span></span>
    
- <span data-ttu-id="753d2-190">自訂 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="753d2-190">Custom XML files</span></span>
    
- <span data-ttu-id="753d2-191">脸谱（页面）</span><span class="sxs-lookup"><span data-stu-id="753d2-191">Facebook (Pages)</span></span>
    
- <span data-ttu-id="753d2-192">事实集</span><span class="sxs-lookup"><span data-stu-id="753d2-192">Factset</span></span>
    
- <span data-ttu-id="753d2-193">FXConnect</span><span class="sxs-lookup"><span data-stu-id="753d2-193">FXConnect</span></span>
    
- <span data-ttu-id="753d2-194">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="753d2-194">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="753d2-195">摇摆</span><span class="sxs-lookup"><span data-stu-id="753d2-195">Jive</span></span>
    
- <span data-ttu-id="753d2-196">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="753d2-196">Macgregor XIP</span></span>

- <span data-ttu-id="753d2-197">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="753d2-197">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="753d2-198">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="753d2-198">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="753d2-199">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="753d2-199">Microsoft Teams</span></span>
       
- <span data-ttu-id="753d2-200">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="753d2-200">Microsoft Yammer</span></span>
    
- <span data-ttu-id="753d2-201">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="753d2-201">Mobile Guard</span></span>
    
- <span data-ttu-id="753d2-202">樞紐</span><span class="sxs-lookup"><span data-stu-id="753d2-202">Pivot</span></span>
    
- <span data-ttu-id="753d2-203">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="753d2-203">Salesforce Chatter</span></span>

- <span data-ttu-id="753d2-204">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="753d2-204">Skype for Business Online</span></span>
    
- <span data-ttu-id="753d2-205">商務用 Skype 2007 版 R2 - 2016 (內部部署)</span><span class="sxs-lookup"><span data-stu-id="753d2-205">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="753d2-206">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="753d2-206">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="753d2-207">交响乐</span><span class="sxs-lookup"><span data-stu-id="753d2-207">Symphony</span></span>
    
- <span data-ttu-id="753d2-208">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="753d2-208">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="753d2-209">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="753d2-209">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="753d2-210">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="753d2-210">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="753d2-211">Twitter</span><span class="sxs-lookup"><span data-stu-id="753d2-211">Twitter</span></span>
    
- <span data-ttu-id="753d2-212">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="753d2-212">UBS Chat</span></span>
    
- <span data-ttu-id="753d2-213">Youtube</span><span class="sxs-lookup"><span data-stu-id="753d2-213">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="753d2-214">OpenText</span><span class="sxs-lookup"><span data-stu-id="753d2-214">OpenText</span></span>

<span data-ttu-id="753d2-215">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="753d2-215">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="753d2-216">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="753d2-216">Axs Encrypted</span></span>
    
- <span data-ttu-id="753d2-217">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="753d2-217">Axs Exchange</span></span>
    
- <span data-ttu-id="753d2-218">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="753d2-218">Axs Local Archive</span></span>
    
- <span data-ttu-id="753d2-219">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="753d2-219">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="753d2-220">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="753d2-220">Axs Signed</span></span>
    
- <span data-ttu-id="753d2-221">彭博</span><span class="sxs-lookup"><span data-stu-id="753d2-221">Bloomberg</span></span>
    
- <span data-ttu-id="753d2-222">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="753d2-222">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="753d2-223">斯马什</span><span class="sxs-lookup"><span data-stu-id="753d2-223">Smarsh</span></span>

<span data-ttu-id="753d2-224">[Smarsh](https://www.smarsh.com)支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="753d2-224">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="753d2-225">目的</span><span class="sxs-lookup"><span data-stu-id="753d2-225">AIM</span></span>
    
- <span data-ttu-id="753d2-226">American Idol</span><span class="sxs-lookup"><span data-stu-id="753d2-226">American Idol</span></span>
    
- <span data-ttu-id="753d2-227">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="753d2-227">Apple Juice</span></span>
    
- <span data-ttu-id="753d2-228">含樞紐分析用戶端的 AOL</span><span class="sxs-lookup"><span data-stu-id="753d2-228">AOL with Pivot client</span></span>
    
- <span data-ttu-id="753d2-229">阿瑞斯</span><span class="sxs-lookup"><span data-stu-id="753d2-229">Ares</span></span>
    
- <span data-ttu-id="753d2-230">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-230">Bazaar Voice</span></span>
    
- <span data-ttu-id="753d2-231">Bear Share</span><span class="sxs-lookup"><span data-stu-id="753d2-231">Bear Share</span></span>
    
- <span data-ttu-id="753d2-232">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="753d2-232">Bit Torrent</span></span>
    
- <span data-ttu-id="753d2-233">BlackBerry Call Logs (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="753d2-233">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="753d2-234">BlackBerry Messenger (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="753d2-234">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="753d2-235">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="753d2-235">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="753d2-236">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="753d2-236">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="753d2-237">Bloomberg 郵件</span><span class="sxs-lookup"><span data-stu-id="753d2-237">Bloomberg Mail</span></span>
    
- <span data-ttu-id="753d2-238">细胞信托</span><span class="sxs-lookup"><span data-stu-id="753d2-238">CellTrust</span></span>
    
- <span data-ttu-id="753d2-239">Chat Import</span><span class="sxs-lookup"><span data-stu-id="753d2-239">Chat Import</span></span>
    
- <span data-ttu-id="753d2-240">Chat Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="753d2-240">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="753d2-241">颤 振</span><span class="sxs-lookup"><span data-stu-id="753d2-241">Chatter</span></span>
    
- <span data-ttu-id="753d2-242">思科&amp;IM 状态服务器（v9.0.1、v9.1、v9.1.1 SU1、v10、v10.5.1 SU1）</span><span class="sxs-lookup"><span data-stu-id="753d2-242">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="753d2-243">Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="753d2-243">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="753d2-244">Collaboration Import</span><span class="sxs-lookup"><span data-stu-id="753d2-244">Collaboration Import</span></span>
    
- <span data-ttu-id="753d2-245">Collaboration Real Time Logging</span><span class="sxs-lookup"><span data-stu-id="753d2-245">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="753d2-246">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="753d2-246">Direct Connect</span></span>
    
- <span data-ttu-id="753d2-247">Facebook</span><span class="sxs-lookup"><span data-stu-id="753d2-247">Facebook</span></span>
    
- <span data-ttu-id="753d2-248">事实集</span><span class="sxs-lookup"><span data-stu-id="753d2-248">FactSet</span></span>
    
- <span data-ttu-id="753d2-249">FastTrack</span><span class="sxs-lookup"><span data-stu-id="753d2-249">FastTrack</span></span>
    
- <span data-ttu-id="753d2-250">努格泰拉</span><span class="sxs-lookup"><span data-stu-id="753d2-250">Gnutella</span></span>
    
- <span data-ttu-id="753d2-251">谷歌+</span><span class="sxs-lookup"><span data-stu-id="753d2-251">Google+</span></span>
    
- <span data-ttu-id="753d2-252">转到MyPC</span><span class="sxs-lookup"><span data-stu-id="753d2-252">GoToMyPC</span></span>
    
- <span data-ttu-id="753d2-253">霍普斯特</span><span class="sxs-lookup"><span data-stu-id="753d2-253">Hopster</span></span>
    
- <span data-ttu-id="753d2-254">胡伯康奈斯</span><span class="sxs-lookup"><span data-stu-id="753d2-254">HubConnex</span></span>
    
- <span data-ttu-id="753d2-255">IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)</span><span class="sxs-lookup"><span data-stu-id="753d2-255">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="753d2-256">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="753d2-256">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="753d2-257">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="753d2-257">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="753d2-258">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="753d2-258">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="753d2-259">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="753d2-259">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="753d2-260">IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)</span><span class="sxs-lookup"><span data-stu-id="753d2-260">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="753d2-261">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="753d2-261">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="753d2-262">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="753d2-262">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="753d2-263">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="753d2-263">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="753d2-264">ICE/黄色夹克</span><span class="sxs-lookup"><span data-stu-id="753d2-264">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="753d2-265">IM Import</span><span class="sxs-lookup"><span data-stu-id="753d2-265">IM Import</span></span>
    
- <span data-ttu-id="753d2-266">IM Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="753d2-266">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="753d2-267">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="753d2-267">Indii Messenger</span></span>
    
- <span data-ttu-id="753d2-268">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="753d2-268">Instant Bloomberg</span></span>
    
- <span data-ttu-id="753d2-269">Irc</span><span class="sxs-lookup"><span data-stu-id="753d2-269">IRC</span></span>
    
- <span data-ttu-id="753d2-270">摇摆</span><span class="sxs-lookup"><span data-stu-id="753d2-270">Jive</span></span>
    
- <span data-ttu-id="753d2-271">Jive 6 Real Time Logging (v6、v7)</span><span class="sxs-lookup"><span data-stu-id="753d2-271">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="753d2-272">Jive Import</span><span class="sxs-lookup"><span data-stu-id="753d2-272">Jive Import</span></span>
    
- <span data-ttu-id="753d2-273">Jxta</span><span class="sxs-lookup"><span data-stu-id="753d2-273">JXTA</span></span>
    
- <span data-ttu-id="753d2-274">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="753d2-274">LinkedIn</span></span>
    
- <span data-ttu-id="753d2-275">Microsoft Lync (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="753d2-275">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="753d2-276">MFTP</span><span class="sxs-lookup"><span data-stu-id="753d2-276">MFTP</span></span>
    
- <span data-ttu-id="753d2-277">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-277">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="753d2-278">Microsoft SharePoint (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="753d2-278">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="753d2-279">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="753d2-279">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="753d2-280">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="753d2-280">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="753d2-281">心对齐</span><span class="sxs-lookup"><span data-stu-id="753d2-281">MindAlign</span></span>
    
- <span data-ttu-id="753d2-282">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="753d2-282">Mobile Guard</span></span>
    
- <span data-ttu-id="753d2-283">Msn</span><span class="sxs-lookup"><span data-stu-id="753d2-283">MSN</span></span>
    
- <span data-ttu-id="753d2-284">My Space</span><span class="sxs-lookup"><span data-stu-id="753d2-284">My Space</span></span>
    
- <span data-ttu-id="753d2-285">近地天体网络</span><span class="sxs-lookup"><span data-stu-id="753d2-285">NEONetwork</span></span>
    
- <span data-ttu-id="753d2-286">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="753d2-286">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="753d2-287">Office 365 Shared IM</span><span class="sxs-lookup"><span data-stu-id="753d2-287">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="753d2-288">兴趣</span><span class="sxs-lookup"><span data-stu-id="753d2-288">Pinterest</span></span>
    
- <span data-ttu-id="753d2-289">樞紐</span><span class="sxs-lookup"><span data-stu-id="753d2-289">Pivot</span></span>
    
- <span data-ttu-id="753d2-290">Qq</span><span class="sxs-lookup"><span data-stu-id="753d2-290">QQ</span></span>
    
- <span data-ttu-id="753d2-291">商務用 Skype 2015</span><span class="sxs-lookup"><span data-stu-id="753d2-291">Skype for Business 2015</span></span>
    
- <span data-ttu-id="753d2-292">软埃瑟</span><span class="sxs-lookup"><span data-stu-id="753d2-292">SoftEther</span></span>
    
- <span data-ttu-id="753d2-293">交响乐</span><span class="sxs-lookup"><span data-stu-id="753d2-293">Symphony</span></span>
    
- <span data-ttu-id="753d2-294">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="753d2-294">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="753d2-295">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="753d2-295">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="753d2-296">Tor</span><span class="sxs-lookup"><span data-stu-id="753d2-296">Tor</span></span>
    
- <span data-ttu-id="753d2-297">TTT</span><span class="sxs-lookup"><span data-stu-id="753d2-297">TTT</span></span>
    
- <span data-ttu-id="753d2-298">Twitter</span><span class="sxs-lookup"><span data-stu-id="753d2-298">Twitter</span></span>
    
- <span data-ttu-id="753d2-299">温MX</span><span class="sxs-lookup"><span data-stu-id="753d2-299">WinMX</span></span>
    
- <span data-ttu-id="753d2-300">温尼</span><span class="sxs-lookup"><span data-stu-id="753d2-300">Winny</span></span>
    
- <span data-ttu-id="753d2-301">雅虎</span><span class="sxs-lookup"><span data-stu-id="753d2-301">Yahoo</span></span>
    
- <span data-ttu-id="753d2-302">Yammer</span><span class="sxs-lookup"><span data-stu-id="753d2-302">Yammer</span></span>
    
- <span data-ttu-id="753d2-303">Youtube</span><span class="sxs-lookup"><span data-stu-id="753d2-303">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="753d2-304">韦尔巴</span><span class="sxs-lookup"><span data-stu-id="753d2-304">Verba</span></span>

<span data-ttu-id="753d2-305">[Verba](https://www.verba.com)支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="753d2-305">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="753d2-306">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="753d2-306">Avaya Aura Video</span></span>
    
- <span data-ttu-id="753d2-307">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-307">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="753d2-308">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="753d2-308">Avtec Radio</span></span>
    
- <span data-ttu-id="753d2-309">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="753d2-309">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="753d2-310">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="753d2-310">BroadSoft Video</span></span>
    
- <span data-ttu-id="753d2-311">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-311">BroadSoft Voice</span></span>
    
- <span data-ttu-id="753d2-312">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-312">Centile Voice</span></span>
    
- <span data-ttu-id="753d2-313">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="753d2-313">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="753d2-314">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="753d2-314">Cisco UC Video</span></span>
    
- <span data-ttu-id="753d2-315">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-315">Cisco UC Voice</span></span>
    
- <span data-ttu-id="753d2-316">思科 UCCX/UCCE 视频</span><span class="sxs-lookup"><span data-stu-id="753d2-316">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="753d2-317">思科 UCCX/UCCE 语音</span><span class="sxs-lookup"><span data-stu-id="753d2-317">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="753d2-318">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="753d2-318">ESChat Radio</span></span>
    
- <span data-ttu-id="753d2-319">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="753d2-319">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="753d2-320">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-320">IP Trade Voice</span></span>
    
- <span data-ttu-id="753d2-321">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="753d2-321">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="753d2-322">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="753d2-322">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="753d2-323">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="753d2-323">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="753d2-324">Oracle / Acme Packet Session Border Controller Video</span><span class="sxs-lookup"><span data-stu-id="753d2-324">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="753d2-325">Oracle / Acme Packet Session Border Controller Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-325">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="753d2-326">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-326">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="753d2-327">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="753d2-327">SIPREC Video</span></span>
    
-  <span data-ttu-id="753d2-328">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-328">SIPREC Voice</span></span> 
    
- <span data-ttu-id="753d2-329">商務用 Skype/Lync IM</span><span class="sxs-lookup"><span data-stu-id="753d2-329">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="753d2-330">商務用 Skype/Lync Video</span><span class="sxs-lookup"><span data-stu-id="753d2-330">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="753d2-331">商務用 Skype/Lync Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-331">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="753d2-332">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-332">Speakerbus Voice</span></span>
    
- <span data-ttu-id="753d2-333">Standard SIP/H.323 Video</span><span class="sxs-lookup"><span data-stu-id="753d2-333">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="753d2-334">Standard SIP/H.323 Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-334">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="753d2-335">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="753d2-335">Truphone Voice</span></span>
    
- <span data-ttu-id="753d2-336">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="753d2-336">TwistedPair Radio</span></span>
    
- <span data-ttu-id="753d2-337">Windows Desktop Computer Screen</span><span class="sxs-lookup"><span data-stu-id="753d2-337">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="753d2-338">步驟 2：在 Office 365 中建立及設定協力廠商資料信箱</span><span class="sxs-lookup"><span data-stu-id="753d2-338">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="753d2-339">以下是创建和配置用于将数据导入 Office 365 的第三方数据邮箱的步骤。</span><span class="sxs-lookup"><span data-stu-id="753d2-339">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="753d2-340">如前所述，如果合作伙伴连接器无法将该项目的用户 ID 映射到 Office 365 用户帐户，则项目将导入此邮箱。</span><span class="sxs-lookup"><span data-stu-id="753d2-340">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="753d2-341">**在 Microsoft 365 管理中心完成这些任务**</span><span class="sxs-lookup"><span data-stu-id="753d2-341">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="753d2-342">在 Office 365 中创建用户帐户，并为其分配 Exchange 在线计划 2 许可证;请参阅[将用户添加到 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098)。</span><span class="sxs-lookup"><span data-stu-id="753d2-342">Create a user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="753d2-343">需要计划 2 许可证才能将邮箱置于诉讼保留状态或启用具有无限存储配额的存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="753d2-343">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="753d2-344">将第三方数据邮箱的用户帐户添加到 Office 365 中的**Exchange 管理员**管理员角色;请参阅[在 Office 365 中分配管理员角色。](https://go.microsoft.com/fwlink/p/?LinkId=532393)</span><span class="sxs-lookup"><span data-stu-id="753d2-344">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="753d2-345">請寫下此使用者帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="753d2-345">Write down the credentials for this user account.</span></span> <span data-ttu-id="753d2-346">您需要將它們提供給您的合作夥伴 (如步驟 4 中所述)。</span><span class="sxs-lookup"><span data-stu-id="753d2-346">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="753d2-347">**在 Exchange 管理中心完成这些任务**</span><span class="sxs-lookup"><span data-stu-id="753d2-347">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="753d2-348">从组织中的通讯簿和其他地址列表中隐藏第三方数据邮箱;请参阅[管理用户邮箱](https://go.microsoft.com/fwlink/p/?LinkId=616058)。</span><span class="sxs-lookup"><span data-stu-id="753d2-348">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="753d2-349">或者，您可以运行以下 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="753d2-349">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="753d2-350">将"**完全访问"** 权限分配给第三方数据邮箱，以便管理员或合规性官可以在 Outlook 桌面客户端中打开第三方数据邮箱;请参阅[管理收件人的权限。](https://go.microsoft.com/fwlink/p/?LinkId=692104)</span><span class="sxs-lookup"><span data-stu-id="753d2-350">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="753d2-351">为第三方数据邮箱启用以下与合规性相关的 Office 365 功能：</span><span class="sxs-lookup"><span data-stu-id="753d2-351">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="753d2-352">启用存档邮箱;请参阅[启用存档邮箱](enable-archive-mailboxes.md)和[启用无限制存档](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="753d2-352">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="753d2-353">这样，您就可以通过设置将第三方数据项目移动到存档邮箱的存档策略来释放主邮箱中的存储空间。</span><span class="sxs-lookup"><span data-stu-id="753d2-353">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="753d2-354">这为您提供了第三方数据的无限存储空间。</span><span class="sxs-lookup"><span data-stu-id="753d2-354">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="753d2-355">將協力廠商資料信箱處於 [訴訟暫止] 狀態。</span><span class="sxs-lookup"><span data-stu-id="753d2-355">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="753d2-356">您还可以在安全和合规性中心应用 Office 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="753d2-356">You can also apply an Office 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="753d2-357">将此邮箱置于保留状态将保留第三方数据项目（无限期或指定持续时间），并防止从邮箱中清除它们。</span><span class="sxs-lookup"><span data-stu-id="753d2-357">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="753d2-358">请参阅以下主题之一：</span><span class="sxs-lookup"><span data-stu-id="753d2-358">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="753d2-359">將信箱設定為訴訟資料暫留狀態</span><span class="sxs-lookup"><span data-stu-id="753d2-359">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="753d2-360">Office 365 中的保留策略概述</span><span class="sxs-lookup"><span data-stu-id="753d2-360">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
       
    
    - <span data-ttu-id="753d2-361">为所有者、代理和管理员访问第三方数据邮箱启用邮箱审核日志记录;请参阅[在 Office 365 中启用邮箱审核。](enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="753d2-361">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="753d2-362">这允许您审核有权访问第三方数据邮箱的任何用户执行的所有活动。</span><span class="sxs-lookup"><span data-stu-id="753d2-362">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="753d2-363">步驟 3：設定協力廠商資料的使用者信箱</span><span class="sxs-lookup"><span data-stu-id="753d2-363">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="753d2-364">下一步是設定使用者信箱以支援協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="753d2-364">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="753d2-365">使用 Exchange 管理中心或使用相应的 Windows PowerShell cmdlet 完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="753d2-365">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="753d2-366">为每个用户启用存档邮箱;请参阅[启用存档邮箱](enable-archive-mailboxes.md)和[启用无限制存档](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="753d2-366">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="753d2-367">将用户邮箱置于诉讼保留状态或应用 Office 365 保留策略;请参阅以下主题之一：</span><span class="sxs-lookup"><span data-stu-id="753d2-367">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="753d2-368">將信箱設定為訴訟資料暫留狀態</span><span class="sxs-lookup"><span data-stu-id="753d2-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="753d2-369">Office 365 中的保留策略概述</span><span class="sxs-lookup"><span data-stu-id="753d2-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="753d2-370">如先前所述，將信箱置於保留狀態時，您可以設定從協力廠商資料來源保留項目多久的持續時間，或者您可以選擇無限期地保留項目。</span><span class="sxs-lookup"><span data-stu-id="753d2-370">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="753d2-371">步驟 4：提供資訊給合作夥伴</span><span class="sxs-lookup"><span data-stu-id="753d2-371">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="753d2-372">最後一個步驟是讓您的合作夥伴具有下列資訊，讓他們可以設定連接器以連接到您的 Office 365 組織，將資料匯入至使用者信箱和協力廠商資料信箱。</span><span class="sxs-lookup"><span data-stu-id="753d2-372">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="753d2-373">用于连接到 Office 365 中的 Azure 服务的终结点：</span><span class="sxs-lookup"><span data-stu-id="753d2-373">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="753d2-374">您在步骤 2 中创建的第三方数据邮箱的登录凭据（Office 365 用户 ID 和密码）。</span><span class="sxs-lookup"><span data-stu-id="753d2-374">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="753d2-375">協力廠商連接器需要這些認證才能存取項目以及將其匯入至使用者信箱和協力廠商資料信箱。</span><span class="sxs-lookup"><span data-stu-id="753d2-375">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="753d2-376">步骤 5：在 Azure 活动目录中注册第三方数据连接器</span><span class="sxs-lookup"><span data-stu-id="753d2-376">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="753d2-377">从 2018 年 9 月 30 日开始，Office 365 中的 Azure 服务将开始使用 Exchange Online 中的现代身份验证来验证尝试连接到 Office 365 组织以导入数据的第三方数据连接器。</span><span class="sxs-lookup"><span data-stu-id="753d2-377">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data.</span></span> <span data-ttu-id="753d2-378">进行此更改的原因是，现代身份验证比当前方法提供了更多的安全性，该方法基于使用前面描述的终结点连接到 Azure 服务的白名单第三方连接器。</span><span class="sxs-lookup"><span data-stu-id="753d2-378">The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="753d2-379">要使第三方数据连接器能够使用新的新式身份验证方法连接到 Office 365，Office 365 组织的管理员必须同意在 Azure 活动目录中将连接器注册为受信任的服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="753d2-379">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="753d2-380">这是通过接受权限请求来允许连接器访问 Azure 活动目录中的组织数据来实现的。</span><span class="sxs-lookup"><span data-stu-id="753d2-380">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="753d2-381">接受此请求后，第三方数据连接器将作为企业应用程序添加到 Azure 活动目录，并表示为服务主体。</span><span class="sxs-lookup"><span data-stu-id="753d2-381">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="753d2-382">有关同意过程的详细信息，请参阅[租户管理员同意](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent)。</span><span class="sxs-lookup"><span data-stu-id="753d2-382">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/en-us/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="753d2-383">以下是访问和接受注册连接器的请求的步骤：</span><span class="sxs-lookup"><span data-stu-id="753d2-383">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="753d2-384">转到[此页面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)并使用 Office 365 全局管理员的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="753d2-384">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="753d2-385">将显示以下对话框。</span><span class="sxs-lookup"><span data-stu-id="753d2-385">The following dialog box is displayed.</span></span> <span data-ttu-id="753d2-386">您可以展开分卡以查看将分配给连接器的权限。</span><span class="sxs-lookup"><span data-stu-id="753d2-386">You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/><span data-ttu-id="753d2-387">![将显示权限请求对话框](media/O365-ThirdPartyDataConnector-OptIn1.png)</span><span class="sxs-lookup"><span data-stu-id="753d2-387">![The permissions request dialog is displayed](media/O365-ThirdPartyDataConnector-OptIn1.png)</span></span>
2. <span data-ttu-id="753d2-388">按一下 [接受]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="753d2-388">Click **Accept**.</span></span>

<span data-ttu-id="753d2-389">接受请求后，将显示[Azure 门户。](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="753d2-389">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="753d2-390">要查看组织的应用程序列表，请单击**Azure 活动目录** > **企业应用程序**。</span><span class="sxs-lookup"><span data-stu-id="753d2-390">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="753d2-391">Office 365 第三方数据连接器列**在"企业"应用程序**边栏选项卡上。</span><span class="sxs-lookup"><span data-stu-id="753d2-391">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="753d2-392">2018 年 9 月 30 日之后，如果不在 Azure 活动目录中注册第三方数据连接器，则第三方数据将不再导入到组织中的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="753d2-392">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="753d2-393">请注意，现有的第三方数据连接器（2018 年 9 月 30 日之前创建的数据连接器）也必须按照步骤 5 中的步骤在 Azure 活动目录中注册。</span><span class="sxs-lookup"><span data-stu-id="753d2-393">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="753d2-394">撤销对第三方数据连接器的同意</span><span class="sxs-lookup"><span data-stu-id="753d2-394">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="753d2-395">组织同意在 Azure 活动目录中注册第三方数据连接器的权限请求后，您的组织可以随时撤消该同意。</span><span class="sxs-lookup"><span data-stu-id="753d2-395">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="753d2-396">但是，撤销连接器的同意意味着来自第三方数据源的数据将不再导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="753d2-396">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="753d2-397">要撤销对第三方数据连接器的同意，可以使用 Azure 门户中的**企业应用程序**边栏选项卡删除应用程序（通过删除相应的服务主体），或使用[在](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal)Office 365 PowerShell 中删除 MsolService 主体。</span><span class="sxs-lookup"><span data-stu-id="753d2-397">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="753d2-398">您还可以在 Azure 活动目录 PowerShell[中使用"删除 AzureADServiceCcd"](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal)</span><span class="sxs-lookup"><span data-stu-id="753d2-398">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="753d2-399">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="753d2-399">More information</span></span>

- <span data-ttu-id="753d2-400">如先前所述，協力廠商資料來源的項目是匯入至 Exchange 信箱做為電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="753d2-400">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="753d2-401">合作伙伴连接器使用 Office 365 API 所需的架构导入项目。</span><span class="sxs-lookup"><span data-stu-id="753d2-401">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="753d2-402">下表說明協力廠商資料來源的項目在匯入至 Exchange 信箱當做為電子郵件之後的郵件屬性。</span><span class="sxs-lookup"><span data-stu-id="753d2-402">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="753d2-403">表格也會指出郵件屬性是否為必要的。</span><span class="sxs-lookup"><span data-stu-id="753d2-403">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="753d2-404">必須填入必要屬性。</span><span class="sxs-lookup"><span data-stu-id="753d2-404">Mandatory properties must be populated.</span></span> <span data-ttu-id="753d2-405">如果项目缺少必填属性，则不会将其导入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="753d2-405">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="753d2-406">导入过程返回一条错误消息，解释为何未导入项以及缺少哪个属性。</span><span class="sxs-lookup"><span data-stu-id="753d2-406">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="753d2-407">**郵件屬性**</span><span class="sxs-lookup"><span data-stu-id="753d2-407">**Message property**</span></span>|<span data-ttu-id="753d2-408">**强制性？**</span><span class="sxs-lookup"><span data-stu-id="753d2-408">**Mandatory?**</span></span>|<span data-ttu-id="753d2-409">**描述**</span><span class="sxs-lookup"><span data-stu-id="753d2-409">**Description**</span></span>|<span data-ttu-id="753d2-410">**範例值**</span><span class="sxs-lookup"><span data-stu-id="753d2-410">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="753d2-411">**FROM**</span><span class="sxs-lookup"><span data-stu-id="753d2-411">**FROM**</span></span> <br/> |<span data-ttu-id="753d2-412">是</span><span class="sxs-lookup"><span data-stu-id="753d2-412">Yes</span></span>  <br/> |<span data-ttu-id="753d2-413">最初在協力廠商資料來源中建立或傳送項目的使用者。</span><span class="sxs-lookup"><span data-stu-id="753d2-413">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="753d2-414">合作伙伴连接器尝试将用户 ID 从源项（例如 Twitter 句柄）映射到所有用户（FROM 和 TO 字段中的用户）的 Office 365 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="753d2-414">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="753d2-415">郵件副本會匯入至每個參與者的信箱。</span><span class="sxs-lookup"><span data-stu-id="753d2-415">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="753d2-416">如果项目的参与者都不能映射到 Office 365 用户帐户，则该项目将导入 Office 365 中的第三方存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="753d2-416">If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="753d2-417">标识为项目发件人的参与者必须在要导入到的 Office 365 组织中具有活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="753d2-417">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to.</span></span> <span data-ttu-id="753d2-418">如果寄件者沒有作用中的信箱，則會傳回下列錯誤︰</span><span class="sxs-lookup"><span data-stu-id="753d2-418">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="753d2-419">**TO**</span><span class="sxs-lookup"><span data-stu-id="753d2-419">**TO**</span></span> <br/> |<span data-ttu-id="753d2-420">是</span><span class="sxs-lookup"><span data-stu-id="753d2-420">Yes</span></span>  <br/> |<span data-ttu-id="753d2-421">接收項目的使用者，如果適用於資料來源中的項目。</span><span class="sxs-lookup"><span data-stu-id="753d2-421">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="753d2-422">**主题**</span><span class="sxs-lookup"><span data-stu-id="753d2-422">**SUBJECT**</span></span> <br/> |<span data-ttu-id="753d2-423">否</span><span class="sxs-lookup"><span data-stu-id="753d2-423">No</span></span>  <br/> |<span data-ttu-id="753d2-424">來源項目的主旨。</span><span class="sxs-lookup"><span data-stu-id="753d2-424">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="753d2-425">**日期**</span><span class="sxs-lookup"><span data-stu-id="753d2-425">**DATE**</span></span> <br/> |<span data-ttu-id="753d2-426">是</span><span class="sxs-lookup"><span data-stu-id="753d2-426">Yes</span></span>  <br/> |<span data-ttu-id="753d2-427">项目最初创建或在客户数据源中过帐的日期。</span><span class="sxs-lookup"><span data-stu-id="753d2-427">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="753d2-428">例如，Twitter 消息被推特的日期。</span><span class="sxs-lookup"><span data-stu-id="753d2-428">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="753d2-429">**身体**</span><span class="sxs-lookup"><span data-stu-id="753d2-429">**BODY**</span></span> <br/> |<span data-ttu-id="753d2-430">否</span><span class="sxs-lookup"><span data-stu-id="753d2-430">No</span></span>  <br/> |<span data-ttu-id="753d2-431">訊息或文章的內容。</span><span class="sxs-lookup"><span data-stu-id="753d2-431">The contents of the message or post.</span></span> <span data-ttu-id="753d2-432">對於某些資料來源，這個屬性的內容可能與 **SUBJECT** 屬性的內容相同。</span><span class="sxs-lookup"><span data-stu-id="753d2-432">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="753d2-433">在导入过程中，合作伙伴连接器尝试尽可能保持内容源的完全保真度。</span><span class="sxs-lookup"><span data-stu-id="753d2-433">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="753d2-434">如果可能的話，來源項目的內文中的檔案、圖形或其他內容會包含在此屬性中。</span><span class="sxs-lookup"><span data-stu-id="753d2-434">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="753d2-435">否則，來源項目的內容會包含在 **ATTACHMENT** 屬性。</span><span class="sxs-lookup"><span data-stu-id="753d2-435">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="753d2-436">此属性的内容取决于合作伙伴连接器和源平台的功能。</span><span class="sxs-lookup"><span data-stu-id="753d2-436">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="753d2-437">**附件**</span><span class="sxs-lookup"><span data-stu-id="753d2-437">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="753d2-438">否</span><span class="sxs-lookup"><span data-stu-id="753d2-438">No</span></span>  <br/> |<span data-ttu-id="753d2-439">如果数据源中的项目（如 Twitter 中的推文或即时消息对话）中的项目具有附加文件或包含图像，则合作伙伴连接将首先尝试在**BODY**属性中包含附件。</span><span class="sxs-lookup"><span data-stu-id="753d2-439">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="753d2-440">如果这是不可能的，则将其添加到 [ 附件 ] 属性中。</span><span class="sxs-lookup"><span data-stu-id="753d2-440">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="753d2-441">其他附件範例包括 Facebook 的「讚」、內容來源的中繼資料和訊息或文章的回應。</span><span class="sxs-lookup"><span data-stu-id="753d2-441">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="753d2-442">**消息类**</span><span class="sxs-lookup"><span data-stu-id="753d2-442">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="753d2-443">是</span><span class="sxs-lookup"><span data-stu-id="753d2-443">Yes</span></span>  <br/> | <span data-ttu-id="753d2-444">這是多重值屬性，由合作夥伴連接器建立並填入。</span><span class="sxs-lookup"><span data-stu-id="753d2-444">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="753d2-445">此属性的格式为`IPM.NOTE.Source.Event`。</span><span class="sxs-lookup"><span data-stu-id="753d2-445">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="753d2-446">（此属性必须以`IPM.NOTE`开头。</span><span class="sxs-lookup"><span data-stu-id="753d2-446">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="753d2-447">此格式与消息类的`IPM.NOTE.X`格式类似。此属性包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="753d2-447">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="753d2-448">`Source`： 指示第三方数据源;例如，推特、脸谱或黑莓。</span><span class="sxs-lookup"><span data-stu-id="753d2-448">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="753d2-449">`Event`： 指示在生成物料的第三方数据源中执行的活动类型;例如，推特的推文或Facebook上的帖子。</span><span class="sxs-lookup"><span data-stu-id="753d2-449">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="753d2-450">事件特定于数据源。</span><span class="sxs-lookup"><span data-stu-id="753d2-450">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="753d2-451">此屬性的其中一個用途是要根據項目產生來源位置的資料來源或根據事件類型，篩選特定項目。</span><span class="sxs-lookup"><span data-stu-id="753d2-451">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="753d2-452">例如，在 eDiscovery 搜尋中，您可以建立搜尋查詢來尋找特定使用者所張貼的所有推文。</span><span class="sxs-lookup"><span data-stu-id="753d2-452">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="753d2-453">当项目成功导入 Office 365 中的邮箱时，唯一标识符将作为 HTTP 响应的一部分返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="753d2-453">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="753d2-454">此标识符称为`x-IngestionCorrelationID`，合作伙伴可用于后续故障排除目的，以便端到端跟踪物料。</span><span class="sxs-lookup"><span data-stu-id="753d2-454">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="753d2-455">建議夥伴擷取這項資訊並加以記錄。</span><span class="sxs-lookup"><span data-stu-id="753d2-455">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="753d2-456">以下是顯示此識別碼之 HTTP 回應的範例：</span><span class="sxs-lookup"><span data-stu-id="753d2-456">Here's an example of an HTTP response showing this identifier:</span></span>

    ```
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```
 
- <span data-ttu-id="753d2-457">您可以使用安全和合规性中心中的内容搜索工具搜索从第三方数据源导入 Office 365 中的邮箱的项目。</span><span class="sxs-lookup"><span data-stu-id="753d2-457">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="753d2-458">要专门搜索这些导入的项目，可以在内容搜索的关键字框中使用以下消息属性值对。</span><span class="sxs-lookup"><span data-stu-id="753d2-458">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="753d2-459">**`kind:externaldata`**：使用此属性值对搜索所有第三方数据类型。</span><span class="sxs-lookup"><span data-stu-id="753d2-459">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="753d2-460">例如，要搜索从第三方数据源导入并在导入项的 Subject 属性中包含单词"contoso"的项目，请使用关键字查询`kind:externaldata AND subject:contoso`。</span><span class="sxs-lookup"><span data-stu-id="753d2-460">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="753d2-461">**`itemclass:ipm.externaldata.<third-party data type>`**：使用此属性值对仅搜索指定类型的第三方数据。</span><span class="sxs-lookup"><span data-stu-id="753d2-461">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="753d2-462">例如，要仅搜索"主题"属性中包含单词"contoso"的 Facebook 数据，请使用关键字查询`itemclass:ipm.externaldata.Facebook* AND subject:contoso`。</span><span class="sxs-lookup"><span data-stu-id="753d2-462">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="753d2-463">有关用于`itemclass`该属性的第三方数据类型的完整值列表，请参阅[使用内容搜索搜索已导入 Office 365 的第三方数据](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="753d2-463">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="753d2-464">如需有關使用內容搜尋和建立關鍵字搜尋查詢的詳細資訊，請參閱︰</span><span class="sxs-lookup"><span data-stu-id="753d2-464">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="753d2-465">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="753d2-465">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="753d2-466">內容搜尋的關鍵字查詢與搜尋條件</span><span class="sxs-lookup"><span data-stu-id="753d2-466">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
