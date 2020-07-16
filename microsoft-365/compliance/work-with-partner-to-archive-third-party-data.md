---
title: 與合作夥伴配合以封存第三方資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何設定自訂連接器，以從資料來源（例如 Salesforce 交談、Yahoo Messenger 或 Yammer）匯入協力廠商資料。
ms.openlocfilehash: c3b824909ae1243e2dd1f12b799e53d00d9615ca
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126652"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="86573-103">與合作夥伴配合以封存第三方資料</span><span class="sxs-lookup"><span data-stu-id="86573-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="86573-104">您可以與 Microsoft 合作夥伴合作，匯入協力廠商資料來源中的資料，並將其封存至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="86573-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="86573-105">協力廠商可為您提供自訂連接器，以設定為從協力廠商資料來源提取專案（定期），然後匯入這些專案。</span><span class="sxs-lookup"><span data-stu-id="86573-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="86573-106">夥伴連接器會將專案的內容從資料來源轉換成電子郵件訊息格式，然後將專案儲存在信箱中。</span><span class="sxs-lookup"><span data-stu-id="86573-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="86573-107">匯入協力廠商資料後，您可以將 Microsoft 365 規範功能（例如訴訟暫止、內容搜尋、In-Place 封存、審核和 Microsoft 365 保留原則）套用至此資料。</span><span class="sxs-lookup"><span data-stu-id="86573-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>
  
<span data-ttu-id="86573-108">以下是與 Microsoft 合作夥伴合作以匯入協力廠商資料所需的程式和步驟。</span><span class="sxs-lookup"><span data-stu-id="86573-108">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="86573-109">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="86573-109">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="86573-110">步驟2：建立並設定協力廠商資料信箱</span><span class="sxs-lookup"><span data-stu-id="86573-110">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="86573-111">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="86573-111">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="86573-112">步驟 4：提供資訊給合作夥伴</span><span class="sxs-lookup"><span data-stu-id="86573-112">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="86573-113">步驟5：在 Azure Active Directory 中註冊協力廠商資料連線器</span><span class="sxs-lookup"><span data-stu-id="86573-113">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="86573-114">協力廠商資料匯入程序的運作方式</span><span class="sxs-lookup"><span data-stu-id="86573-114">How the third-party data import process works</span></span>

<span data-ttu-id="86573-115">下列圖例和描述說明協力廠商資料匯入程式在使用合作夥伴時的運作方式。</span><span class="sxs-lookup"><span data-stu-id="86573-115">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![協力廠商資料匯入程序的運作方式](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="86573-117">客戶可以使用其選擇的合作夥伴，設定將從協力廠商資料來源提取專案的連接器，然後將這些專案匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="86573-117">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>
    
2. <span data-ttu-id="86573-118">夥伴連接器會透過協力廠商 API （根據排程或設定的基礎）連線至協力廠商資料來源，並從資料來源提取專案。</span><span class="sxs-lookup"><span data-stu-id="86573-118">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="86573-119">協力廠商連接器會將項目的內容轉換為電子郵件訊息格式。</span><span class="sxs-lookup"><span data-stu-id="86573-119">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="86573-120">請參閱[More information](#more-information)一節以取得郵件格式架構的描述。</span><span class="sxs-lookup"><span data-stu-id="86573-120">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="86573-121">夥伴連接器會透過已知端點透過 Exchange Web 服務（EWS），連接至 Microsoft 365 中的 Azure 服務。</span><span class="sxs-lookup"><span data-stu-id="86573-121">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="86573-p103">項目是匯入至特定使用者的信箱或「全部擷取」協力廠商資料信箱。項目匯入至特定使用者信箱還是協力廠商資料信箱，是根據下列準則：</span><span class="sxs-lookup"><span data-stu-id="86573-p103">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
   1. <span data-ttu-id="86573-124">**具有對應至使用者帳戶之使用者識別碼的專案：** 如果夥伴連接器可將協力廠商資料來源中專案的使用者識別碼對應至 Office 365 中的特定使用者識別碼，該專案會複製到使用者的 [可復原的專案] 資料夾中的 [**清除**] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="86573-124">**Items that have a user ID that corresponds to an user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="86573-125">使用者無法存取 [清除] 資料夾中的項目。</span><span class="sxs-lookup"><span data-stu-id="86573-125">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="86573-126">不過，您可以使用 eDiscovery 工具來搜尋 [清除] 資料夾中的專案。</span><span class="sxs-lookup"><span data-stu-id="86573-126">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>
    
   1. <span data-ttu-id="86573-127">**沒有對應至使用者帳戶的使用者識別碼的專案：** 如果 partner connector 無法將專案的使用者識別碼對應至特定的使用者識別碼，該專案會複製到協力廠商資料信箱的 [**收件**匣] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="86573-127">**Items that don't have a user ID that corresponds to an user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="86573-128">將項目匯入至收件匣可讓您或組織中的某個人登入協力廠商信箱來檢視和管理這些項目，並查看是否需要在協力廠商連接器組態中進行任何調整。</span><span class="sxs-lookup"><span data-stu-id="86573-128">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="86573-129">步驟 1：尋找協力廠商資料合作夥伴</span><span class="sxs-lookup"><span data-stu-id="86573-129">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="86573-130">在 Microsoft 365 中封存協力廠商資料的主要元件，是尋找和使用專用於從協力廠商資料來源捕獲資料，並將資料匯入 Office 365 的 Microsoft 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="86573-130">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="86573-131">在匯入資料之後，可以將其封存及保留，以及組織的其他 Microsoft 資料，例如來自 Exchange 的電子郵件，以及來自 SharePoint 和 OneDrive 商務的檔。</span><span class="sxs-lookup"><span data-stu-id="86573-131">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="86573-132">合作夥伴會建立從您組織的協力廠商資料來源（例如 BlackBerry、Facebook、Google +、Thomson Reuters、Twitter 及 YouTube）提取資料的連接器，並將該資料傳遞到以電子郵件形式將專案匯入 Exchange 信箱的 Office 365 API。</span><span class="sxs-lookup"><span data-stu-id="86573-132">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="86573-133">下列各節列出參與程式以在 Office 365 中封存協力廠商資料的 Microsoft 合作夥伴（和其所支援的協力廠商資料來源）。</span><span class="sxs-lookup"><span data-stu-id="86573-133">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="86573-134">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="86573-134">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="86573-135">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="86573-135">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="86573-136">Globanet</span><span class="sxs-lookup"><span data-stu-id="86573-136">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="86573-137">OpenText</span><span class="sxs-lookup"><span data-stu-id="86573-137">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="86573-138">Smarsh</span><span class="sxs-lookup"><span data-stu-id="86573-138">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="86573-139">Verba</span><span class="sxs-lookup"><span data-stu-id="86573-139">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="86573-140">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="86573-140">17a-4 LLC</span></span>

<span data-ttu-id="86573-141">[17A-4 LLC](https://www.17a-4.com)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="86573-141">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="86573-142">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="86573-142">BlackBerry</span></span>
    
- <span data-ttu-id="86573-143">Bloomberg 資料流</span><span class="sxs-lookup"><span data-stu-id="86573-143">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="86573-144">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="86573-144">Cisco Jabber</span></span>
    
- <span data-ttu-id="86573-145">FactSet</span><span class="sxs-lookup"><span data-stu-id="86573-145">FactSet</span></span>
    
- <span data-ttu-id="86573-146">HipChat</span><span class="sxs-lookup"><span data-stu-id="86573-146">HipChat</span></span>
    
- <span data-ttu-id="86573-147">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="86573-147">InvestEdge</span></span>
    
- <span data-ttu-id="86573-148">LivePerson</span><span class="sxs-lookup"><span data-stu-id="86573-148">LivePerson</span></span>
    
- <span data-ttu-id="86573-149">MessageLabs 資料流</span><span class="sxs-lookup"><span data-stu-id="86573-149">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="86573-150">OpenText</span><span class="sxs-lookup"><span data-stu-id="86573-150">OpenText</span></span>
    
- <span data-ttu-id="86573-151">Oracle/ATG 'click-to-call' 即時說明</span><span class="sxs-lookup"><span data-stu-id="86573-151">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="86573-152">樞紐分析 IMTRADER</span><span class="sxs-lookup"><span data-stu-id="86573-152">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="86573-153">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="86573-153">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="86573-154">MindAlign</span><span class="sxs-lookup"><span data-stu-id="86573-154">MindAlign</span></span>
    
- <span data-ttu-id="86573-155">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="86573-155">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="86573-156">商務用 Skype (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="86573-156">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="86573-157">商務用 Skype Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="86573-157">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="86573-158">SQL 資料庫</span><span class="sxs-lookup"><span data-stu-id="86573-158">SQL Databases</span></span>
    
- <span data-ttu-id="86573-159">Squawker</span><span class="sxs-lookup"><span data-stu-id="86573-159">Squawker</span></span>
    
- <span data-ttu-id="86573-160">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="86573-160">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="86573-161">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="86573-161">ArchiveSocial</span></span>

<span data-ttu-id="86573-162">[ArchiveSocial](https://www.archivesocial.com)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="86573-162">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="86573-163">Facebook</span><span class="sxs-lookup"><span data-stu-id="86573-163">Facebook</span></span>
    
- <span data-ttu-id="86573-164">Flickr</span><span class="sxs-lookup"><span data-stu-id="86573-164">Flickr</span></span>
    
- <span data-ttu-id="86573-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="86573-165">Instagram</span></span>
    
- <span data-ttu-id="86573-166">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="86573-166">LinkedIn</span></span>
    
- <span data-ttu-id="86573-167">Pinterest</span><span class="sxs-lookup"><span data-stu-id="86573-167">Pinterest</span></span>
    
- <span data-ttu-id="86573-168">Twitter</span><span class="sxs-lookup"><span data-stu-id="86573-168">Twitter</span></span>
    
- <span data-ttu-id="86573-169">YouTube</span><span class="sxs-lookup"><span data-stu-id="86573-169">YouTube</span></span>
    
- <span data-ttu-id="86573-170">Vimeo</span><span class="sxs-lookup"><span data-stu-id="86573-170">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="86573-171">Globanet</span><span class="sxs-lookup"><span data-stu-id="86573-171">Globanet</span></span>

<span data-ttu-id="86573-172">[Globanet](https://www.globanet.com)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="86573-172">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="86573-173">含樞紐分析用戶端的 AOL</span><span class="sxs-lookup"><span data-stu-id="86573-173">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="86573-174">BlackBerry Call Logs (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="86573-174">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="86573-175">BlackBerry Messenger (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="86573-175">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="86573-176">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="86573-176">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="86573-177">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="86573-177">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="86573-178">Bloomberg Chat</span><span class="sxs-lookup"><span data-stu-id="86573-178">Bloomberg Chat</span></span>
    
- <span data-ttu-id="86573-179">Bloomberg 郵件</span><span class="sxs-lookup"><span data-stu-id="86573-179">Bloomberg Mail</span></span>
    
- <span data-ttu-id="86573-180">Box</span><span class="sxs-lookup"><span data-stu-id="86573-180">Box</span></span>
    
- <span data-ttu-id="86573-181">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="86573-181">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="86573-182">Cisco IM &amp; 顯示伺服器（v10，v v10.5.1 SU1，v 11.0，v 11.5 SU2）</span><span class="sxs-lookup"><span data-stu-id="86573-182">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="86573-183">Cisco Webex 小組</span><span class="sxs-lookup"><span data-stu-id="86573-183">Cisco Webex Teams</span></span>

- <span data-ttu-id="86573-184">Citrix 工作區 &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="86573-184">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="86573-185">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="86573-185">CrowdCompass</span></span>

- <span data-ttu-id="86573-186">自訂分隔的文字檔</span><span class="sxs-lookup"><span data-stu-id="86573-186">Custom-delimited text files</span></span>
    
- <span data-ttu-id="86573-187">自訂 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="86573-187">Custom XML files</span></span>
    
- <span data-ttu-id="86573-188">Facebook （頁面）</span><span class="sxs-lookup"><span data-stu-id="86573-188">Facebook (Pages)</span></span>
    
- <span data-ttu-id="86573-189">Factset</span><span class="sxs-lookup"><span data-stu-id="86573-189">Factset</span></span>
    
- <span data-ttu-id="86573-190">FXConnect</span><span class="sxs-lookup"><span data-stu-id="86573-190">FXConnect</span></span>
    
- <span data-ttu-id="86573-191">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="86573-191">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="86573-192">搖擺</span><span class="sxs-lookup"><span data-stu-id="86573-192">Jive</span></span>
    
- <span data-ttu-id="86573-193">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="86573-193">Macgregor XIP</span></span>

- <span data-ttu-id="86573-194">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="86573-194">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="86573-195">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="86573-195">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="86573-196">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86573-196">Microsoft Teams</span></span>
       
- <span data-ttu-id="86573-197">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="86573-197">Microsoft Yammer</span></span>
    
- <span data-ttu-id="86573-198">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="86573-198">Mobile Guard</span></span>
    
- <span data-ttu-id="86573-199">樞紐</span><span class="sxs-lookup"><span data-stu-id="86573-199">Pivot</span></span>
    
- <span data-ttu-id="86573-200">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="86573-200">Salesforce Chatter</span></span>

- <span data-ttu-id="86573-201">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="86573-201">Skype for Business Online</span></span>
    
- <span data-ttu-id="86573-202">商務用 Skype 2007 版 R2 - 2016 (內部部署)</span><span class="sxs-lookup"><span data-stu-id="86573-202">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="86573-203">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="86573-203">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="86573-204">交響樂</span><span class="sxs-lookup"><span data-stu-id="86573-204">Symphony</span></span>
    
- <span data-ttu-id="86573-205">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="86573-205">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="86573-206">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="86573-206">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="86573-207">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="86573-207">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="86573-208">Twitter</span><span class="sxs-lookup"><span data-stu-id="86573-208">Twitter</span></span>
    
- <span data-ttu-id="86573-209">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="86573-209">UBS Chat</span></span>
    
- <span data-ttu-id="86573-210">YouTube</span><span class="sxs-lookup"><span data-stu-id="86573-210">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="86573-211">OpenText</span><span class="sxs-lookup"><span data-stu-id="86573-211">OpenText</span></span>

<span data-ttu-id="86573-212">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="86573-212">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="86573-213">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="86573-213">Axs Encrypted</span></span>
    
- <span data-ttu-id="86573-214">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="86573-214">Axs Exchange</span></span>
    
- <span data-ttu-id="86573-215">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="86573-215">Axs Local Archive</span></span>
    
- <span data-ttu-id="86573-216">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="86573-216">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="86573-217">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="86573-217">Axs Signed</span></span>
    
- <span data-ttu-id="86573-218">彭博</span><span class="sxs-lookup"><span data-stu-id="86573-218">Bloomberg</span></span>
    
- <span data-ttu-id="86573-219">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="86573-219">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="86573-220">Smarsh</span><span class="sxs-lookup"><span data-stu-id="86573-220">Smarsh</span></span>

<span data-ttu-id="86573-221">[Smarsh](https://www.smarsh.com)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="86573-221">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="86573-222">目的</span><span class="sxs-lookup"><span data-stu-id="86573-222">AIM</span></span>
    
- <span data-ttu-id="86573-223">American Idol</span><span class="sxs-lookup"><span data-stu-id="86573-223">American Idol</span></span>
    
- <span data-ttu-id="86573-224">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="86573-224">Apple Juice</span></span>
    
- <span data-ttu-id="86573-225">含樞紐分析用戶端的 AOL</span><span class="sxs-lookup"><span data-stu-id="86573-225">AOL with Pivot client</span></span>
    
- <span data-ttu-id="86573-226">阿瑞斯</span><span class="sxs-lookup"><span data-stu-id="86573-226">Ares</span></span>
    
- <span data-ttu-id="86573-227">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="86573-227">Bazaar Voice</span></span>
    
- <span data-ttu-id="86573-228">Bear Share</span><span class="sxs-lookup"><span data-stu-id="86573-228">Bear Share</span></span>
    
- <span data-ttu-id="86573-229">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="86573-229">Bit Torrent</span></span>
    
- <span data-ttu-id="86573-230">BlackBerry Call Logs (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="86573-230">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="86573-231">BlackBerry Messenger (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="86573-231">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="86573-232">BlackBerry PIN (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="86573-232">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="86573-233">BlackBerry SMS (v5、v10、v12)</span><span class="sxs-lookup"><span data-stu-id="86573-233">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="86573-234">Bloomberg 郵件</span><span class="sxs-lookup"><span data-stu-id="86573-234">Bloomberg Mail</span></span>
    
- <span data-ttu-id="86573-235">CellTrust</span><span class="sxs-lookup"><span data-stu-id="86573-235">CellTrust</span></span>
    
- <span data-ttu-id="86573-236">Chat Import</span><span class="sxs-lookup"><span data-stu-id="86573-236">Chat Import</span></span>
    
- <span data-ttu-id="86573-237">Chat Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="86573-237">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="86573-238">顫 振</span><span class="sxs-lookup"><span data-stu-id="86573-238">Chatter</span></span>
    
- <span data-ttu-id="86573-239">Cisco IM &amp; 顯示伺服器（v 9.0.1、v 9.1、v 9.1.1 SU1、v10、v v10.5.1 SU1）</span><span class="sxs-lookup"><span data-stu-id="86573-239">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="86573-240">Cisco Unified Presence Server (v8.6.3、v8.6.4、v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="86573-240">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="86573-241">Collaboration Import</span><span class="sxs-lookup"><span data-stu-id="86573-241">Collaboration Import</span></span>
    
- <span data-ttu-id="86573-242">Collaboration Real Time Logging</span><span class="sxs-lookup"><span data-stu-id="86573-242">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="86573-243">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="86573-243">Direct Connect</span></span>
    
- <span data-ttu-id="86573-244">Facebook</span><span class="sxs-lookup"><span data-stu-id="86573-244">Facebook</span></span>
    
- <span data-ttu-id="86573-245">FactSet</span><span class="sxs-lookup"><span data-stu-id="86573-245">FactSet</span></span>
    
- <span data-ttu-id="86573-246">FastTrack</span><span class="sxs-lookup"><span data-stu-id="86573-246">FastTrack</span></span>
    
- <span data-ttu-id="86573-247">Gnutella</span><span class="sxs-lookup"><span data-stu-id="86573-247">Gnutella</span></span>
    
- <span data-ttu-id="86573-248">Google +</span><span class="sxs-lookup"><span data-stu-id="86573-248">Google+</span></span>
    
- <span data-ttu-id="86573-249">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="86573-249">GoToMyPC</span></span>
    
- <span data-ttu-id="86573-250">Hopster</span><span class="sxs-lookup"><span data-stu-id="86573-250">Hopster</span></span>
    
- <span data-ttu-id="86573-251">HubConnex</span><span class="sxs-lookup"><span data-stu-id="86573-251">HubConnex</span></span>
    
- <span data-ttu-id="86573-252">IBM Connections (v3.0.1、v4.0、v4.5、v4.5 CR3、v5)</span><span class="sxs-lookup"><span data-stu-id="86573-252">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="86573-253">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="86573-253">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="86573-254">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="86573-254">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="86573-255">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="86573-255">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="86573-256">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="86573-256">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="86573-257">IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)</span><span class="sxs-lookup"><span data-stu-id="86573-257">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="86573-258">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="86573-258">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="86573-259">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="86573-259">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="86573-260">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="86573-260">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="86573-261">冰/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="86573-261">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="86573-262">IM Import</span><span class="sxs-lookup"><span data-stu-id="86573-262">IM Import</span></span>
    
- <span data-ttu-id="86573-263">IM Real Time Logging and Policy</span><span class="sxs-lookup"><span data-stu-id="86573-263">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="86573-264">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="86573-264">Indii Messenger</span></span>
    
- <span data-ttu-id="86573-265">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="86573-265">Instant Bloomberg</span></span>
    
- <span data-ttu-id="86573-266">Irc</span><span class="sxs-lookup"><span data-stu-id="86573-266">IRC</span></span>
    
- <span data-ttu-id="86573-267">搖擺</span><span class="sxs-lookup"><span data-stu-id="86573-267">Jive</span></span>
    
- <span data-ttu-id="86573-268">Jive 6 Real Time Logging (v6、v7)</span><span class="sxs-lookup"><span data-stu-id="86573-268">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="86573-269">Jive Import</span><span class="sxs-lookup"><span data-stu-id="86573-269">Jive Import</span></span>
    
- <span data-ttu-id="86573-270">Jxta</span><span class="sxs-lookup"><span data-stu-id="86573-270">JXTA</span></span>
    
- <span data-ttu-id="86573-271">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="86573-271">LinkedIn</span></span>
    
- <span data-ttu-id="86573-272">Microsoft Lync (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="86573-272">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="86573-273">MFTP</span><span class="sxs-lookup"><span data-stu-id="86573-273">MFTP</span></span>
    
- <span data-ttu-id="86573-274">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="86573-274">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="86573-275">Microsoft SharePoint (2010、2013)</span><span class="sxs-lookup"><span data-stu-id="86573-275">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="86573-276">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="86573-276">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="86573-277">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="86573-277">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="86573-278">MindAlign</span><span class="sxs-lookup"><span data-stu-id="86573-278">MindAlign</span></span>
    
- <span data-ttu-id="86573-279">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="86573-279">Mobile Guard</span></span>
    
- <span data-ttu-id="86573-280">Msn</span><span class="sxs-lookup"><span data-stu-id="86573-280">MSN</span></span>
    
- <span data-ttu-id="86573-281">My Space</span><span class="sxs-lookup"><span data-stu-id="86573-281">My Space</span></span>
    
- <span data-ttu-id="86573-282">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="86573-282">NEONetwork</span></span>
    
- <span data-ttu-id="86573-283">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="86573-283">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="86573-284">Office 365 Shared IM</span><span class="sxs-lookup"><span data-stu-id="86573-284">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="86573-285">Pinterest</span><span class="sxs-lookup"><span data-stu-id="86573-285">Pinterest</span></span>
    
- <span data-ttu-id="86573-286">樞紐</span><span class="sxs-lookup"><span data-stu-id="86573-286">Pivot</span></span>
    
- <span data-ttu-id="86573-287">Qq</span><span class="sxs-lookup"><span data-stu-id="86573-287">QQ</span></span>
    
- <span data-ttu-id="86573-288">商務用 Skype 2015</span><span class="sxs-lookup"><span data-stu-id="86573-288">Skype for Business 2015</span></span>
    
- <span data-ttu-id="86573-289">SoftEther</span><span class="sxs-lookup"><span data-stu-id="86573-289">SoftEther</span></span>
    
- <span data-ttu-id="86573-290">交響樂</span><span class="sxs-lookup"><span data-stu-id="86573-290">Symphony</span></span>
    
- <span data-ttu-id="86573-291">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="86573-291">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="86573-292">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="86573-292">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="86573-293">Tor</span><span class="sxs-lookup"><span data-stu-id="86573-293">Tor</span></span>
    
- <span data-ttu-id="86573-294">TTT</span><span class="sxs-lookup"><span data-stu-id="86573-294">TTT</span></span>
    
- <span data-ttu-id="86573-295">Twitter</span><span class="sxs-lookup"><span data-stu-id="86573-295">Twitter</span></span>
    
- <span data-ttu-id="86573-296">WinMX</span><span class="sxs-lookup"><span data-stu-id="86573-296">WinMX</span></span>
    
- <span data-ttu-id="86573-297">Winny</span><span class="sxs-lookup"><span data-stu-id="86573-297">Winny</span></span>
    
- <span data-ttu-id="86573-298">雅虎</span><span class="sxs-lookup"><span data-stu-id="86573-298">Yahoo</span></span>
    
- <span data-ttu-id="86573-299">Yammer</span><span class="sxs-lookup"><span data-stu-id="86573-299">Yammer</span></span>
    
- <span data-ttu-id="86573-300">YouTube</span><span class="sxs-lookup"><span data-stu-id="86573-300">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="86573-301">Verba</span><span class="sxs-lookup"><span data-stu-id="86573-301">Verba</span></span>

<span data-ttu-id="86573-302">[Verba](https://www.verba.com)支援下列協力廠商資料來源：</span><span class="sxs-lookup"><span data-stu-id="86573-302">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="86573-303">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="86573-303">Avaya Aura Video</span></span>
    
- <span data-ttu-id="86573-304">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="86573-304">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="86573-305">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="86573-305">Avtec Radio</span></span>
    
- <span data-ttu-id="86573-306">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="86573-306">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="86573-307">BroadSoft Video</span><span class="sxs-lookup"><span data-stu-id="86573-307">BroadSoft Video</span></span>
    
- <span data-ttu-id="86573-308">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="86573-308">BroadSoft Voice</span></span>
    
- <span data-ttu-id="86573-309">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="86573-309">Centile Voice</span></span>
    
- <span data-ttu-id="86573-310">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="86573-310">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="86573-311">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="86573-311">Cisco UC Video</span></span>
    
- <span data-ttu-id="86573-312">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="86573-312">Cisco UC Voice</span></span>
    
- <span data-ttu-id="86573-313">Cisco UCCX/UCCE 影片</span><span class="sxs-lookup"><span data-stu-id="86573-313">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="86573-314">Cisco UCCX/UCCE 語音</span><span class="sxs-lookup"><span data-stu-id="86573-314">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="86573-315">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="86573-315">ESChat Radio</span></span>
    
- <span data-ttu-id="86573-316">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="86573-316">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="86573-317">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="86573-317">IP Trade Voice</span></span>
    
- <span data-ttu-id="86573-318">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="86573-318">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="86573-319">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="86573-319">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="86573-320">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="86573-320">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="86573-321">Oracle / Acme Packet Session Border Controller Video</span><span class="sxs-lookup"><span data-stu-id="86573-321">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="86573-322">Oracle / Acme Packet Session Border Controller Voice</span><span class="sxs-lookup"><span data-stu-id="86573-322">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="86573-323">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="86573-323">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="86573-324">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="86573-324">SIPREC Video</span></span>
    
-  <span data-ttu-id="86573-325">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="86573-325">SIPREC Voice</span></span> 
    
- <span data-ttu-id="86573-326">商務用 Skype/Lync IM</span><span class="sxs-lookup"><span data-stu-id="86573-326">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="86573-327">商務用 Skype/Lync Video</span><span class="sxs-lookup"><span data-stu-id="86573-327">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="86573-328">商務用 Skype/Lync Voice</span><span class="sxs-lookup"><span data-stu-id="86573-328">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="86573-329">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="86573-329">Speakerbus Voice</span></span>
    
- <span data-ttu-id="86573-330">Standard SIP/H.323 Video</span><span class="sxs-lookup"><span data-stu-id="86573-330">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="86573-331">Standard SIP/H.323 Voice</span><span class="sxs-lookup"><span data-stu-id="86573-331">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="86573-332">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="86573-332">Truphone Voice</span></span>
    
- <span data-ttu-id="86573-333">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="86573-333">TwistedPair Radio</span></span>
    
- <span data-ttu-id="86573-334">Windows Desktop Computer Screen</span><span class="sxs-lookup"><span data-stu-id="86573-334">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="86573-335">步驟 2：在 Office 365 中建立及設定協力廠商資料信箱</span><span class="sxs-lookup"><span data-stu-id="86573-335">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="86573-336">以下是建立及設定協力廠商資料信箱以將資料匯入 Office 365 的步驟。</span><span class="sxs-lookup"><span data-stu-id="86573-336">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="86573-337">如先前所述，如果夥伴連接器無法將專案的使用者識別碼對應至使用者帳戶，便會將專案匯入此信箱。</span><span class="sxs-lookup"><span data-stu-id="86573-337">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an user account.</span></span>
  
 <span data-ttu-id="86573-338">**在 Microsoft 365 系統管理中心完成這些工作**</span><span class="sxs-lookup"><span data-stu-id="86573-338">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="86573-339">建立使用者帳戶並指派 Exchange Online Plan 2 授權;請參閱[將使用者新增至 Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098)。</span><span class="sxs-lookup"><span data-stu-id="86573-339">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="86573-340">若要將信箱設為訴訟暫止或啟用具有無限儲存配額的封存信箱，則需要 Plan 2 授權。</span><span class="sxs-lookup"><span data-stu-id="86573-340">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="86573-341">將協力廠商資料信箱的使用者帳戶新增至 Office 365 中的**Exchange 管理員系統管理員**角色。請參閱[在 Office 365 中指派系統管理員角色](https://go.microsoft.com/fwlink/p/?LinkId=532393)。</span><span class="sxs-lookup"><span data-stu-id="86573-341">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="86573-342">請寫下此使用者帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="86573-342">Write down the credentials for this user account.</span></span> <span data-ttu-id="86573-343">您需要將它們提供給您的合作夥伴 (如步驟 4 中所述)。</span><span class="sxs-lookup"><span data-stu-id="86573-343">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="86573-344">**在 Exchange 系統管理中心完成這些工作**</span><span class="sxs-lookup"><span data-stu-id="86573-344">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="86573-345">從組織中的通訊錄和其他通訊清單中隱藏協力廠商資料信箱;請參閱[管理使用者信箱](https://go.microsoft.com/fwlink/p/?LinkId=616058)。</span><span class="sxs-lookup"><span data-stu-id="86573-345">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="86573-346">或者，您也可以執行下列 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="86573-346">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="86573-347">指派協力廠商資料信箱的**FullAccess**許可權，讓系統管理員或合規性監察官可以在 Outlook 桌面用戶端中開啟協力廠商資料信箱。請參閱管理收件者[的許可權](https://go.microsoft.com/fwlink/p/?LinkId=692104)。</span><span class="sxs-lookup"><span data-stu-id="86573-347">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="86573-348">針對協力廠商資料信箱啟用下列與規範相關的功能：</span><span class="sxs-lookup"><span data-stu-id="86573-348">Enable the following compliance-related features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="86573-349">啟用封存信箱;請參閱[啟用封存信箱](enable-archive-mailboxes.md)及[啟用無限](enable-unlimited-archiving.md)封存。</span><span class="sxs-lookup"><span data-stu-id="86573-349">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="86573-350">這可讓您透過設定將協力廠商資料項目目移至封存信箱的封存原則，以釋放主要信箱中的儲存空間。</span><span class="sxs-lookup"><span data-stu-id="86573-350">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="86573-351">這可讓您在協力廠商資料上使用無限制的儲存體。</span><span class="sxs-lookup"><span data-stu-id="86573-351">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="86573-352">將協力廠商資料信箱處於 [訴訟暫止] 狀態。</span><span class="sxs-lookup"><span data-stu-id="86573-352">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="86573-353">您也可以在安全性與合規性中心套用 Microsoft 365 保留原則。</span><span class="sxs-lookup"><span data-stu-id="86573-353">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="86573-354">保留此信箱會保留協力廠商資料項目（無限期或在指定期間內），並防止其從信箱中清除。</span><span class="sxs-lookup"><span data-stu-id="86573-354">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="86573-355">請參閱下列其中一個主題：</span><span class="sxs-lookup"><span data-stu-id="86573-355">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="86573-356">將信箱設定為訴訟資料暫留狀態</span><span class="sxs-lookup"><span data-stu-id="86573-356">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="86573-357">深入瞭解保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="86573-357">Learn about retention policies and retention labels</span></span>](retention.md)
    
    - <span data-ttu-id="86573-358">針對協力廠商資料信箱的擁有者、委派及系統管理存取啟用信箱審計記錄;請參閱[啟用信箱審核](enable-mailbox-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="86573-358">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="86573-359">這可讓您審核任何可存取協力廠商資料信箱之使用者執行的所有活動。</span><span class="sxs-lookup"><span data-stu-id="86573-359">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="86573-360">步驟 3：設定協力廠商資料的使用者信箱</span><span class="sxs-lookup"><span data-stu-id="86573-360">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="86573-361">下一步是設定使用者信箱以支援協力廠商資料。</span><span class="sxs-lookup"><span data-stu-id="86573-361">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="86573-362">使用 Exchange 系統管理中心或使用對應的 Windows PowerShell Cmdlet，完成這些工作。</span><span class="sxs-lookup"><span data-stu-id="86573-362">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="86573-363">為每位使用者啟用封存信箱;請參閱[啟用封存信箱](enable-archive-mailboxes.md)及[啟用無限](enable-unlimited-archiving.md)封存。</span><span class="sxs-lookup"><span data-stu-id="86573-363">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="86573-364">將使用者信箱設為訴訟暫止，或套用 Microsoft 365 保留原則;請參閱下列其中一個主題：</span><span class="sxs-lookup"><span data-stu-id="86573-364">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="86573-365">將信箱設定為訴訟資料暫留狀態</span><span class="sxs-lookup"><span data-stu-id="86573-365">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="86573-366">深入瞭解保留原則和保留標籤</span><span class="sxs-lookup"><span data-stu-id="86573-366">Learn about retention policies and retention labels</span></span>](retention.md)
    
    <span data-ttu-id="86573-367">如先前所述，將信箱置於保留狀態時，您可以設定從協力廠商資料來源保留項目多久的持續時間，或者您可以選擇無限期地保留項目。</span><span class="sxs-lookup"><span data-stu-id="86573-367">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="86573-368">步驟 4：提供資訊給合作夥伴</span><span class="sxs-lookup"><span data-stu-id="86573-368">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="86573-369">最後一個步驟是向您的合作夥伴提供下列資訊，讓他們可以設定連接器，以連線至您的組織，將資料匯入至使用者信箱和協力廠商資料信箱。</span><span class="sxs-lookup"><span data-stu-id="86573-369">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="86573-370">用來連線至 Office 365 中之 Azure 服務的端點：</span><span class="sxs-lookup"><span data-stu-id="86573-370">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="86573-371">您在步驟2中建立之協力廠商資料信箱的登入認證（Microsoft 365 使用者識別碼和密碼）。</span><span class="sxs-lookup"><span data-stu-id="86573-371">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="86573-372">協力廠商連接器需要這些認證才能存取項目以及將其匯入至使用者信箱和協力廠商資料信箱。</span><span class="sxs-lookup"><span data-stu-id="86573-372">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="86573-373">步驟5：在 Azure Active Directory 中註冊協力廠商資料連線器</span><span class="sxs-lookup"><span data-stu-id="86573-373">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="86573-374">從2018年9月30日起，Office 365 中的 Azure 服務會開始使用 Exchange Online 中的新式驗證，以驗證嘗試連線至組織以匯入資料的協力廠商資料連線器。</span><span class="sxs-lookup"><span data-stu-id="86573-374">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="86573-375">這種變更的原因是，新式驗證提供的安全性高於目前的方法，這是根據使用先前所述端點連線至 Azure 服務之協力廠商連接器的允許清單。</span><span class="sxs-lookup"><span data-stu-id="86573-375">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="86573-376">若要讓協力廠商資料連線器使用全新的新式驗證方法來連線至 Office 365，您組織中的系統管理員必須同意在 Azure Active Directory 中將連接器註冊為受信任的服務應用程式。</span><span class="sxs-lookup"><span data-stu-id="86573-376">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="86573-377">若要允許連接器在 Azure Active Directory 中存取組織的資料，請接受許可權要求，以進行這項操作。</span><span class="sxs-lookup"><span data-stu-id="86573-377">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="86573-378">在您接受此要求之後，協力廠商資料連線器會新增為 Azure Active Directory 中的企業應用程式，並表示為服務主體。</span><span class="sxs-lookup"><span data-stu-id="86573-378">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="86573-379">如需同意程式的詳細資訊，請參閱[租使用者管理員同意](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent)。</span><span class="sxs-lookup"><span data-stu-id="86573-379">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="86573-380">以下是存取及接受註冊連接器要求的步驟：</span><span class="sxs-lookup"><span data-stu-id="86573-380">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="86573-381">移[至此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，並使用全域管理員的認證登入。</span><span class="sxs-lookup"><span data-stu-id="86573-381">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="86573-382">隨即顯示下列對話方塊。</span><span class="sxs-lookup"><span data-stu-id="86573-382">The following dialog box is displayed.</span></span> <span data-ttu-id="86573-383">您可以展開 carets，以複查將指派給連接器的許可權。</span><span class="sxs-lookup"><span data-stu-id="86573-383">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![顯示 [許可權要求] 對話方塊](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="86573-385">按一下 [接受]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="86573-385">Click **Accept**.</span></span>

<span data-ttu-id="86573-386">在您接受要求之後，就會顯示[Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="86573-386">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="86573-387">若要查看組織的應用程式清單，請按一下 [ **Azure Active Directory**  >  **企業應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="86573-387">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="86573-388">Office 365 協力廠商資料連線器會列在**企業應用程式**blade 上。</span><span class="sxs-lookup"><span data-stu-id="86573-388">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86573-389">在2018年9月30日之後，如果您未在 Azure Active Directory 中註冊協力廠商資料連線器，協力廠商資料將無法再匯入您組織中的信箱。</span><span class="sxs-lookup"><span data-stu-id="86573-389">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="86573-390">請注意，在 Azure Active Directory 中建立的協力廠商資料連線器（在2018年9月30日之前所建立），必須先在 Azure Active Directory 中註冊，請遵循步驟5中的程式。</span><span class="sxs-lookup"><span data-stu-id="86573-390">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="86573-391">撤銷協力廠商資料連線器的同意</span><span class="sxs-lookup"><span data-stu-id="86573-391">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="86573-392">在您的組織 consents 至許可權要求後，若要在 Azure Active Directory 中註冊協力廠商資料連線器，您的組織可以隨時撤銷該同意。</span><span class="sxs-lookup"><span data-stu-id="86573-392">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="86573-393">不過，撤銷連接器的同意表示將不再將協力廠商資料來源的資料匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="86573-393">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="86573-394">若要撤銷協力廠商資料連線器的同意，您可以使用 Azure 入口網站中的**Enterprise** application blade，或是使用 Office 365 PowerShell 中的 [[移除-new-msolserviceprincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) ]，從 azure Active Directory 中刪除應用程式（透過刪除對應的服務主體）。</span><span class="sxs-lookup"><span data-stu-id="86573-394">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="86573-395">您也可以在 Azure Active Directory PowerShell 中使用[Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86573-395">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="86573-396">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="86573-396">More information</span></span>

- <span data-ttu-id="86573-397">如先前所述，協力廠商資料來源的項目是匯入至 Exchange 信箱做為電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="86573-397">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="86573-398">夥伴連接器會使用 Office 365 API 所需的架構，匯入專案。</span><span class="sxs-lookup"><span data-stu-id="86573-398">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="86573-399">下表說明協力廠商資料來源的項目在匯入至 Exchange 信箱當做為電子郵件之後的郵件屬性。</span><span class="sxs-lookup"><span data-stu-id="86573-399">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="86573-400">表格也會指出郵件屬性是否為必要的。</span><span class="sxs-lookup"><span data-stu-id="86573-400">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="86573-401">必須填入必要屬性。</span><span class="sxs-lookup"><span data-stu-id="86573-401">Mandatory properties must be populated.</span></span> <span data-ttu-id="86573-402">如果專案缺少強制的屬性，則不會將它匯入至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="86573-402">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="86573-403">匯入程式會傳回一則錯誤訊息，說明未匯入專案的原因，以及遺漏的屬性。</span><span class="sxs-lookup"><span data-stu-id="86573-403">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>
    
    |<span data-ttu-id="86573-404">**郵件屬性**</span><span class="sxs-lookup"><span data-stu-id="86573-404">**Message property**</span></span>|<span data-ttu-id="86573-405">**強制性？**</span><span class="sxs-lookup"><span data-stu-id="86573-405">**Mandatory?**</span></span>|<span data-ttu-id="86573-406">**描述**</span><span class="sxs-lookup"><span data-stu-id="86573-406">**Description**</span></span>|<span data-ttu-id="86573-407">**範例值**</span><span class="sxs-lookup"><span data-stu-id="86573-407">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="86573-408">**FROM**</span><span class="sxs-lookup"><span data-stu-id="86573-408">**FROM**</span></span> <br/> |<span data-ttu-id="86573-409">是</span><span class="sxs-lookup"><span data-stu-id="86573-409">Yes</span></span>  <br/> |<span data-ttu-id="86573-410">最初在協力廠商資料來源中建立或傳送項目的使用者。</span><span class="sxs-lookup"><span data-stu-id="86573-410">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="86573-411">夥伴連接器會嘗試將使用者識別碼從來源專案（例如 Twitter 控制碼）對應至所有參與者（[寄件者] 和 [至] 欄位中的使用者）的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="86573-411">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to an user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="86573-412">郵件副本會匯入至每個參與者的信箱。</span><span class="sxs-lookup"><span data-stu-id="86573-412">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="86573-413">如果無法將專案的任何參與者對應至使用者帳戶，該專案就會匯入至 Office 365 中的協力廠商封存信箱。</span><span class="sxs-lookup"><span data-stu-id="86573-413">If none of the participants from the item can be mapped to an user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="86573-414">識別為專案之寄件者的參與者必須在組織中有一個使用中的信箱，且該專案要匯入到該組織中。</span><span class="sxs-lookup"><span data-stu-id="86573-414">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="86573-415">如果寄件者沒有作用中的信箱，則會傳回下列錯誤︰</span><span class="sxs-lookup"><span data-stu-id="86573-415">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="86573-416">**TO**</span><span class="sxs-lookup"><span data-stu-id="86573-416">**TO**</span></span> <br/> |<span data-ttu-id="86573-417">是</span><span class="sxs-lookup"><span data-stu-id="86573-417">Yes</span></span>  <br/> |<span data-ttu-id="86573-418">接收項目的使用者，如果適用於資料來源中的項目。</span><span class="sxs-lookup"><span data-stu-id="86573-418">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="86573-419">**主題**</span><span class="sxs-lookup"><span data-stu-id="86573-419">**SUBJECT**</span></span> <br/> |<span data-ttu-id="86573-420">否</span><span class="sxs-lookup"><span data-stu-id="86573-420">No</span></span>  <br/> |<span data-ttu-id="86573-421">來源項目的主旨。</span><span class="sxs-lookup"><span data-stu-id="86573-421">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="86573-422">**日期**</span><span class="sxs-lookup"><span data-stu-id="86573-422">**DATE**</span></span> <br/> |<span data-ttu-id="86573-423">是</span><span class="sxs-lookup"><span data-stu-id="86573-423">Yes</span></span>  <br/> |<span data-ttu-id="86573-424">在客戶資料來源中，最初建立或張貼專案的日期。</span><span class="sxs-lookup"><span data-stu-id="86573-424">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="86573-425">例如，Twitter 郵件的日期日期。</span><span class="sxs-lookup"><span data-stu-id="86573-425">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="86573-426">**身體**</span><span class="sxs-lookup"><span data-stu-id="86573-426">**BODY**</span></span> <br/> |<span data-ttu-id="86573-427">否</span><span class="sxs-lookup"><span data-stu-id="86573-427">No</span></span>  <br/> |<span data-ttu-id="86573-428">訊息或文章的內容。</span><span class="sxs-lookup"><span data-stu-id="86573-428">The contents of the message or post.</span></span> <span data-ttu-id="86573-429">對於某些資料來源，這個屬性的內容可能與 **SUBJECT** 屬性的內容相同。</span><span class="sxs-lookup"><span data-stu-id="86573-429">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="86573-430">在匯入程式期間，協力廠商連接器會嘗試盡可能從內容來源保持完全保真。</span><span class="sxs-lookup"><span data-stu-id="86573-430">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="86573-431">如果可能的話，來源項目的內文中的檔案、圖形或其他內容會包含在此屬性中。</span><span class="sxs-lookup"><span data-stu-id="86573-431">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="86573-432">否則，來源項目的內容會包含在 **ATTACHMENT** 屬性。</span><span class="sxs-lookup"><span data-stu-id="86573-432">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="86573-433">此屬性的內容取決於夥伴連接器和來源平臺的功能。</span><span class="sxs-lookup"><span data-stu-id="86573-433">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="86573-434">**附件**</span><span class="sxs-lookup"><span data-stu-id="86573-434">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="86573-435">否</span><span class="sxs-lookup"><span data-stu-id="86573-435">No</span></span>  <br/> |<span data-ttu-id="86573-436">如果資料來源中的專案（例如 Twitter 或立即訊息交談中的 tweet）具有附加的檔案或包括影像，則協力廠商連線會先嘗試在**BODY**屬性中包含附件。</span><span class="sxs-lookup"><span data-stu-id="86573-436">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="86573-437">如果無法這樣做，它會新增至 \* \* 附件 \* \* 屬性。</span><span class="sxs-lookup"><span data-stu-id="86573-437">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="86573-438">其他附件範例包括 Facebook 的「讚」、內容來源的中繼資料和訊息或文章的回應。</span><span class="sxs-lookup"><span data-stu-id="86573-438">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="86573-439">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="86573-439">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="86573-440">是</span><span class="sxs-lookup"><span data-stu-id="86573-440">Yes</span></span>  <br/> | <span data-ttu-id="86573-441">這是多重值屬性，由合作夥伴連接器建立並填入。</span><span class="sxs-lookup"><span data-stu-id="86573-441">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="86573-442">此屬性的格式為 `IPM.NOTE.Source.Event` 。</span><span class="sxs-lookup"><span data-stu-id="86573-442">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="86573-443">（此屬性必須以開頭 `IPM.NOTE` 。</span><span class="sxs-lookup"><span data-stu-id="86573-443">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="86573-444">這種格式與郵件類別的格式類似 `IPM.NOTE.X` 。）此屬性包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="86573-444">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="86573-445">`Source`：指出協力廠商資料來源;例如，Twitter、Facebook 或 BlackBerry。</span><span class="sxs-lookup"><span data-stu-id="86573-445">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="86573-446">`Event`：指出在產生專案的協力廠商資料來源中所執行的活動類型。例如，在 Twitter 中的 tweet 或在 Facebook 中的文章。</span><span class="sxs-lookup"><span data-stu-id="86573-446">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="86573-447">事件是資料來源特有的。</span><span class="sxs-lookup"><span data-stu-id="86573-447">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="86573-448">此屬性的其中一個用途是要根據項目產生來源位置的資料來源或根據事件類型，篩選特定項目。</span><span class="sxs-lookup"><span data-stu-id="86573-448">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="86573-449">例如，在 eDiscovery 搜尋中，您可以建立搜尋查詢來尋找特定使用者所張貼的所有推文。</span><span class="sxs-lookup"><span data-stu-id="86573-449">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="86573-450">當專案順利匯入至 Office 365 中的信箱時，會將唯一識別碼傳回回來電者做為 HTTP 回應的一部分。</span><span class="sxs-lookup"><span data-stu-id="86573-450">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="86573-451">這個識別碼（稱為 `x-IngestionCorrelationID` ）可以用於後續疑難排解，供合作夥伴進行專案的端對端追蹤。</span><span class="sxs-lookup"><span data-stu-id="86573-451">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="86573-452">建議夥伴擷取這項資訊並加以記錄。</span><span class="sxs-lookup"><span data-stu-id="86573-452">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="86573-453">以下是顯示此識別碼之 HTTP 回應的範例：</span><span class="sxs-lookup"><span data-stu-id="86573-453">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="86573-454">您可以使用安全性與合規性中心的內容搜尋工具，搜尋從協力廠商資料來源匯入信箱的專案。</span><span class="sxs-lookup"><span data-stu-id="86573-454">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="86573-455">若要特別針對這些匯入的專案進行搜尋，您可以在內容搜尋的關鍵字方塊中使用下列郵件屬性-值對。</span><span class="sxs-lookup"><span data-stu-id="86573-455">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="86573-456">**`kind:externaldata`**：使用此屬性-值對可搜尋所有協力廠商資料類型。</span><span class="sxs-lookup"><span data-stu-id="86573-456">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="86573-457">例如，若要搜尋從協力廠商資料來源匯入的專案，並在匯入專案的 Subject 屬性中包含 "contoso" 一詞，您可以使用關鍵字查詢 `kind:externaldata AND subject:contoso` 。</span><span class="sxs-lookup"><span data-stu-id="86573-457">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="86573-458">**`itemclass:ipm.externaldata.<third-party data type>`**：使用此屬性-值對只搜尋協力廠商資料的指定類型。</span><span class="sxs-lookup"><span data-stu-id="86573-458">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="86573-459">例如，若要在 Subject 屬性中只搜尋包含 "contoso" 一詞的 Facebook 資料，您可以使用關鍵字查詢 `itemclass:ipm.externaldata.Facebook* AND subject:contoso` 。</span><span class="sxs-lookup"><span data-stu-id="86573-459">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="86573-460">如需用於屬性的協力廠商資料類型的完整值清單 `itemclass` ，請參閱[使用內容搜尋搜尋協力廠商資料已匯入至 Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)。</span><span class="sxs-lookup"><span data-stu-id="86573-460">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>
    
   <span data-ttu-id="86573-461">如需有關使用內容搜尋和建立關鍵字搜尋查詢的詳細資訊，請參閱︰</span><span class="sxs-lookup"><span data-stu-id="86573-461">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="86573-462">Office 365 中的內容搜尋</span><span class="sxs-lookup"><span data-stu-id="86573-462">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="86573-463">內容搜尋的關鍵字查詢與搜尋條件</span><span class="sxs-lookup"><span data-stu-id="86573-463">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
