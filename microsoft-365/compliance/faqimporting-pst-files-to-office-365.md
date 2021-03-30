---
title: 匯入 PST 檔案的常見問題集
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
ms.custom: seo-marvel-apr2020
description: 本文包含一些常見問題的解答，系統管理員會使用 Office 365 匯入服務，將 PST 檔案匯入 PST 檔案至 Microsoft 365。
ms.openlocfilehash: d775e7cadb71e47cc916a064386971ecd3d08afc
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408632"
---
# <a name="faq-about-importing-pst-files"></a><span data-ttu-id="a8fb8-103">匯入 PST 檔案的常見問題集</span><span class="sxs-lookup"><span data-stu-id="a8fb8-103">FAQ about importing PST files</span></span>

<span data-ttu-id="a8fb8-104">**本文適用于系統管理員。您是否要將 PST 檔案匯入您自己的信箱？請參閱 [從 Outlook .pst 檔案匯入電子郵件、連絡人及行事曆](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-104">**This article is for administrators. Do you want to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span></span>

<span data-ttu-id="a8fb8-105">以下是一些有關使用 Office 365 Import Service 將 PST 檔案大量匯入 Microsoft 365 信箱的常見問題。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-105">Here are some frequently asked questions about using the Office 365 Import Service to bulk-import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="a8fb8-106">如需如何匯入 PST 檔案的詳細資訊，請參閱 [將 pst 檔案匯入至 Office 365 的概述](./importing-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-106">For more information about how to import PST files, see [Overview of importing PST files to Office 365](./importing-pst-files-to-office-365.md).</span></span>
  
## <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="a8fb8-107">使用網路上傳來匯入 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="a8fb8-107">Using network upload to import PST files</span></span>

<span data-ttu-id="a8fb8-108">如需逐步指示，請參閱 [使用網路上傳將 PST 檔案匯入 Office 365](use-network-upload-to-import-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-108">For step-by-step instructions, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
  
 <span data-ttu-id="a8fb8-109">**必須具備哪些權限才能在 Office365 匯入服務中建立匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-109">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="a8fb8-110">您必須在 Exchange Online 中獲派信箱匯入匯出角色，才能將 PST 檔案匯入 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-110">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="a8fb8-111">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-111">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="a8fb8-112">You can add the Mailbox Import Export role to the Organization Management role group.</span><span class="sxs-lookup"><span data-stu-id="a8fb8-112">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="a8fb8-113">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span><span class="sxs-lookup"><span data-stu-id="a8fb8-113">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="a8fb8-114">如需詳細資訊，請參閱[管理 Exchange Online 中的角色](/Exchange/permissions-exo/role-groups)之＜新增角色至角色群組＞或＜建立角色群組＞一節。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-114">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups).</span></span>
  
<span data-ttu-id="a8fb8-115">此外，若要在安全性與合規性中心建立匯入工作，必須符合以下其中一個條件：</span><span class="sxs-lookup"><span data-stu-id="a8fb8-115">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="a8fb8-116">您必須在 Exchange Online 中獲派郵件收件者角色。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-116">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="a8fb8-117">根據預設，這個角色會指派給組織管理及收件者管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-117">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="a8fb8-118">或者</span><span class="sxs-lookup"><span data-stu-id="a8fb8-118">Or</span></span>
    
- <span data-ttu-id="a8fb8-119">您必須是組織中的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-119">You have to be a global administrator in your organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="a8fb8-120">建議您在 Exchange Online 中建立新的角色群組，專門用來將 PST 檔案匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-120">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="a8fb8-121">若要獲得匯入 PST 檔案所需的最低權限等級，請將信箱匯入匯出及郵件收件者角色指派到新的角色群組，然後新增成員。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-121">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="a8fb8-122">**哪些地區提供網路上傳服務？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-122">**Where is network upload available?**</span></span>
  
<span data-ttu-id="a8fb8-p105">網路上傳的服務範圍目前包括這些地區：美國、加拿大、巴西、英國、法國、德國、瑞士、挪威、歐洲、印度、東亞、東南亞、日本、南韓、澳洲和阿拉伯聯合大公國 (UAE)。我們會盡快在更多地區提供網路上傳服務。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-p105">Network upload is currently available in these regions: United States, Canada, Brazil, the United Kingdom, France, Germany, Switzerland, Norway, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, Australia, and United Arab Emirates (UAE). Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="a8fb8-125">**使用網路上傳匯入 PST 檔案的費用為何？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-125">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="a8fb8-126">Using network upload to import PST files is free.</span><span class="sxs-lookup"><span data-stu-id="a8fb8-126">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="a8fb8-127">這也表示 PST 檔案從 Azure 儲存體區域刪除之後，Microsoft 365 系統管理中心內完整匯入工作的檔案清單中就不會顯示這些檔案。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-127">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Microsoft 365 admin center.</span></span> <span data-ttu-id="a8fb8-128">即使匯入工作仍然列在 **[將資料匯入 Office 365]** 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-128">Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="a8fb8-129">**哪些版本的 PST 檔案格式支援匯入 Office 365？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-129">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="a8fb8-130">有兩個版本的 PST 檔案格式支援此作業：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-130">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="a8fb8-131">我們建議您使用 Unicode PST 檔案格式來匯入檔案。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-131">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="a8fb8-132">不過，使用 ANSI PST 檔案格式的檔案 (例如，使用雙位元組字元集 (DBCS) 語言的檔案) 也可以匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-132">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="a8fb8-133">如需有關匯入 ANSI PST 檔案的詳細資訊，請參閱 [使用網路上傳將組織的 PST 檔案匯入 Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)中的步驟4。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-133">For more information about importing ANSI PST files, see Step 4 in [Use network upload to import your organization's PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="a8fb8-134">此外，Outlook 2007 和更新版本的 PST 檔案也可以匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-134">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="a8fb8-135">**將我的 PST 檔案上傳到 Azure 儲存體區域之後，這些檔案會在 Azure 中保留多久的時間才會遭到刪除？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-135">**After I upload my PST files to the Azure Storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="a8fb8-136">使用網路上傳方法匯入 PST 檔案，會將這些檔案上傳到名為 `ingestiondata` 的 Azure Blob 容器。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-136">When you use the network upload method to import PST files, you upload them to an Azure blob container named `ingestiondata`.</span></span> <span data-ttu-id="a8fb8-137">如果安全性與合規性中心的 [匯入 PST 檔案] 頁面目前沒有進行中的匯入工作，則 Azure 中 `ingestiondata` 容器內的所有 PST 檔案都會在最近的匯入工作於安全性與合規性中心建立完成的後 30 天刪除。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-137">If there are no import jobs in progress on the **Import PST files** page in the Security & Compliance Center), then all PST files in the `ingestiondata` container in Azure are deleted 30 days after the most recent import job was created in the Security & Compliance Center.</span></span> <span data-ttu-id="a8fb8-138">這也表示您必須在 PST 檔案上傳到 Azure 的 30 天內，在安全性與合規性中心建立新的匯入工作 (如網路上傳指示中的步驟 5 所述)。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-138">That also means you have to create a new import job in the Security & Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="a8fb8-139">這也表示 PST 檔案從 Azure 儲存體區域刪除之後，安全性與合規性中心內完整匯入工作的檔案清單中就不會顯示這些檔案。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-139">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="a8fb8-140">即使匯入工作仍然列在安全性與合規性中心的 [匯入 PST 檔案] 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-140">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="a8fb8-141">**需要多久的時間才能將 PST 檔案匯入信箱？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-141">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="a8fb8-142">這取決於您的網路容量，但將每 TB 的資料上傳到貴組織的 Azure 儲存體區域通常需要幾個小時的時間。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-142">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure Storage area for your organization.</span></span> <span data-ttu-id="a8fb8-143">將 PST 檔案複製到 Azure 儲存體區域之後，系統會以每天至少 24 GB 的速率將 PST 檔案匯入至 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-143">After the PST files are copied to the Azure Storage area, a PST file is imported to a Microsoft 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="a8fb8-144">如果這樣的速率不符您的需求，建議您嘗試其他方法將電子郵件資料移轉到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-144">If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365.</span></span> <span data-ttu-id="a8fb8-145">如需詳細資訊，請參閱＜[將多個電子郵件帳戶移轉到 Office 365 的方法](/Exchange/mailbox-migration/mailbox-migration)＞。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-145">For more information, see [Ways to migrate multiple email accounts to Office 365](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="a8fb8-146">如果不同的 PST 檔案需匯入到不同的目標信箱，匯入程序會同時進行；換句話說，系統會同時匯入每個 PST/信箱組合。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-146">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="a8fb8-147">同樣地，如果多個 PST 檔案匯入到相同的信箱，則會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-147">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="a8fb8-148">PST 匯入處理程序如何處理重複的電子郵件項目?</span><span class="sxs-lookup"><span data-stu-id="a8fb8-148">**How does the PST import process handle duplicate email items?**</span></span>

<span data-ttu-id="a8fb8-149">PST 匯入處理程序會檢查重複的項目，如果目標資料夾、目標信箱或目標封存中已有相同項目，則不會將資料從 PST 檔案複製到信箱或封存。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-149">The PST import process checks for duplicate items and doesn't copy the items from a PST file to the mailbox or archive if a matching item exists in the target folder in the target mailbox or target archive.</span></span> <span data-ttu-id="a8fb8-150">如果您重新匯入同一個 PST 檔案，並指定與前一個匯入工作指定之資料夾不同的目標資料夾 (使用 PST 匯入對應檔案中的 TargetRootFolder 屬性)，則 PST 檔案中的所有項目將會重新匯入。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-150">If you reimport the same PST file and specify a different target folder (using the TargetRootFolder property in the PST import mapping file) than the one you specified in a previous import job, all items in the PST file will be reimported.</span></span>

 <span data-ttu-id="a8fb8-151">**匯入 PST 檔案時，是否有郵件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-151">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="a8fb8-152">是。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-152">Yes.</span></span> <span data-ttu-id="a8fb8-153">若 PST 檔案包含大於 150 MB 的信箱專案，則會在匯入程式期間略過此專案，且不會匯入。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-153">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped and not imported during the import process.</span></span> <span data-ttu-id="a8fb8-154">不會匯入大於 150 MB 的專案，因為 150 MB 是 Exchange Online 中的郵件大小限制。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-154">Items larger than 150 MB aren't imported because 150 MB is the message size limit in Exchange Online.</span></span> <span data-ttu-id="a8fb8-155">如需詳細資訊，請參閱 [Exchange Online 中的郵件限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits)。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-155">For more information, see [Message limits in Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits).</span></span>
  
 <span data-ttu-id="a8fb8-156">**PST 檔案匯入 Microsoft 365 信箱時是否會保留訊息屬性 (例如訊息的傳送或接收時間、收件者清單、和其他屬性)？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-156">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to a Microsoft 365 mailbox?**</span></span>
  
<span data-ttu-id="a8fb8-157">是。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-157">Yes.</span></span> <span data-ttu-id="a8fb8-158">匯入程序不會變更任何原始的訊息中繼資料。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-158">The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="a8fb8-159">**針對我要匯入至信箱的 PST 檔案，其資料夾階層數是否有上限？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-159">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="a8fb8-p115">是。您無法匯入具有 300 或更多巢狀資料夾階層的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-p115">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="a8fb8-162">**我是否可以使用網路上傳將 PST 檔案匯入 Office 365 中的非作用中的信箱？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-162">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="a8fb8-163">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-163">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="a8fb8-164">**我是否可以使用網路上傳將 PST 檔案匯入 Exchange 混合式部署中的線上封存信箱？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-164">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="a8fb8-165">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-165">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="a8fb8-166">**我是否可以使用網路上傳方式將 PST 檔匯入 Exchange Online 的公用資料夾？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-166">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="a8fb8-167">否，您無法將 PST 檔案匯入公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-167">No, you can't import PST files to public folders.</span></span>
  
## <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="a8fb8-168">使用磁碟機寄送來匯入 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="a8fb8-168">Using drive shipping to import PST files</span></span>

<span data-ttu-id="a8fb8-169">如需逐步指示，請參閱 [使用磁片磁碟機運送將 PST 檔案匯入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-169">For step-by-step instructions, see [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).</span></span>
  
 <span data-ttu-id="a8fb8-170">**必須具備哪些權限才能在 Office365 匯入服務中建立匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-170">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="a8fb8-171">您必須獲派信箱匯入匯出角色，才能將 PST 檔案匯入 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-171">You have to be assigned the Mailbox Import Export role to import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="a8fb8-172">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-172">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="a8fb8-173">You can add the Mailbox Import Export role to the Organization Management role group.</span><span class="sxs-lookup"><span data-stu-id="a8fb8-173">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="a8fb8-174">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span><span class="sxs-lookup"><span data-stu-id="a8fb8-174">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="a8fb8-175">如需詳細資訊，請參閱[管理 Exchange Online 中的角色](/Exchange/permissions-exo/role-groups)之＜新增角色至角色群組＞或＜建立角色群組＞一節。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-175">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](/Exchange/permissions-exo/role-groups).</span></span>
  
<span data-ttu-id="a8fb8-176">此外，若要在安全性與合規性中心建立匯入工作，必須符合以下其中一個條件：</span><span class="sxs-lookup"><span data-stu-id="a8fb8-176">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="a8fb8-177">您必須在 Exchange Online 中獲派郵件收件者角色。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-177">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="a8fb8-178">根據預設，這個角色會指派給組織管理及收件者管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-178">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="a8fb8-179">或者</span><span class="sxs-lookup"><span data-stu-id="a8fb8-179">Or</span></span>
    
- <span data-ttu-id="a8fb8-180">您必須是組織中的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-180">You have to be a global administrator in your organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="a8fb8-181">建議您在 Exchange Online 中建立新的角色群組，專門用來將 PST 檔案匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-181">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="a8fb8-182">若要獲得匯入 PST 檔案所需的最低權限等級，請將信箱匯入匯出及郵件收件者角色指派到新的角色群組，然後新增成員。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-182">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="a8fb8-183">**哪些地區提供磁碟機寄送服務？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-183">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="a8fb8-184">磁碟機寄送的服務範圍目前包括美國、加拿大、巴西、英國、歐洲、印度、東亞、東南亞、日本、大韓民國和澳洲。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-184">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="a8fb8-185">我們會盡快在更多地區提供磁碟機寄送服務。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-185">Drive shipping will be available in more regions soon.</span></span>

> [!NOTE]
> <span data-ttu-id="a8fb8-186">目前在德國和瑞士不開放使用磁碟機寄送匯入 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-186">At this time, drive shipping to import PST files is not available in Germany and Switzerland.</span></span> <span data-ttu-id="a8fb8-187">當這些國家/地區開放磁碟機寄送時，將會更新此常見問題。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-187">This FAQ will be updated when drive shipping is available in these countries.</span></span>
  
 <span data-ttu-id="a8fb8-188">**有哪些商業授權合約支援磁碟機寄送？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-188">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="a8fb8-189">Microsoft Enterprise Agreement (EA) 提供將 PST 檔案匯入至 Microsoft 365 的磁碟機寄送服務。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-189">Drive shipping to import PST files to Microsoft 365 is available through a Microsoft Enterprise Agreement (EA).</span></span> <span data-ttu-id="a8fb8-190">Microsoft Products and Services Agreement (MPSA) 則沒有提供磁碟機寄送。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-190">Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="a8fb8-191">**使用磁碟機寄送將 PST 檔案匯入至 Microsoft 365 的費用為何？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-191">**What is the pricing for using drive shipping to import PST files to Microsoft 365?**</span></span>
  
<span data-ttu-id="a8fb8-192">使用磁碟機寄送將 PST 檔案匯入至 Microsoft 365 信箱的費用為每 GB 的資料 $2 美元。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-192">The cost to use drive shipping to import PST files to Microsoft 365 mailboxes is $2 USD per GB of data.</span></span> <span data-ttu-id="a8fb8-193">例如，假設您寄送的硬碟含有 1,000 GB (即 1 TB) 的 PST 檔案，則費用為 $2,000 美元。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-193">For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD.</span></span> <span data-ttu-id="a8fb8-194">您可以與夥伴合作來支付匯入費用。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-194">You can work with a partner to pay the import fee.</span></span> <span data-ttu-id="a8fb8-195">如需有關尋找合作夥伴的資訊，請參閱[尋找您的 Microsoft 365 合作夥伴或轉售商](../admin/manage/find-your-partner-or-reseller.md)。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-195">For information about finding a partner, see [Find your Microsoft partner or reseller](../admin/manage/find-your-partner-or-reseller.md).</span></span>
  
 <span data-ttu-id="a8fb8-196">**哪些類型的硬碟支援磁碟機寄送？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-196">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="a8fb8-197">只有2.5 寸的固態硬碟 (Ssd) 或 3.5 2.5/III 的 SATA II/III 內部硬碟可搭配 Office 365 匯入服務使用。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-197">Only 2.5-inch solid-state drives (SSDs) or 2.5-inch or 3.5-inch SATA II/III internal hard drives are supported for use with the Office 365 Import service.</span></span> <span data-ttu-id="a8fb8-198">您可以使用最多 10 TB 的硬碟。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-198">You can use hard drives up to 10 TB.</span></span> <span data-ttu-id="a8fb8-199">匯入作業時，只會處理硬碟上的第一個資料磁碟區。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-199">For import jobs, only the first data volume on the hard drive will be processed.</span></span> <span data-ttu-id="a8fb8-200">資料磁碟區必須為 NTFS 格式。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-200">The data volume must be formatted with NTFS.</span></span> <span data-ttu-id="a8fb8-201">將資料複製到硬碟時，您可以使用2.5 寸 SSD 或 2.5-寸或 3.5-寸的 SATA II/III 連接器直接連接，也可以使用外部的「2.5-寸 SSD」或「2.5-寸」或「3.5-寸 SATA II/III」 USB 配接器，將其附加到外部磁片。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-201">When copying data to a hard drive, you can attach it directly using a 2.5-inch SSD or 2.5-inch or 3.5-inch SATA II/III connector or you can attach it externally using an external 2.5-inch SSD or 2.5-inch or 3.5-inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a8fb8-202">Office 365 匯入服務不支援隨附內建 USB 轉接頭的外接式硬碟。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-202">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service.</span></span> <span data-ttu-id="a8fb8-203">此外，位於外部硬碟外殼內的碟無法使用。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-203">Additionally, the disk inside the casing of an external hard drive can't be used.</span></span> <span data-ttu-id="a8fb8-204">請不要使用外接式硬碟。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-204">Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="a8fb8-205">**可以寄送幾個硬碟來進行單一匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-205">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="a8fb8-206">最多可以寄送 10 個硬碟來進行單一匯入工作。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-206">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="a8fb8-207">**寄送硬碟之後，需要多久的時間才會送達 Microsoft 資料中心？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-207">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="a8fb8-p125">這取決於幾個要素，例如您與 Microsoft 資料中心之間的距離，以及您使用什麼類型的運送選項來寄送硬碟 (例如，隔天送達、兩日送達或陸地運送)。大多數貨運公司提供追蹤號碼，讓您可以追蹤運送狀態。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-p125">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="a8fb8-210">**硬碟送達 Microsoft 資料中心後，需要多久的時間才能將我的 PST 檔案上傳到 Azure？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-210">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="a8fb8-211">當您在 Microsoft 資料中心接收到硬碟後，需要7到10個工作日才能將 PST 檔案上傳至組織的 Azure 存放區。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-211">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Azure Storage area for your organization.</span></span> <span data-ttu-id="a8fb8-212">PST 檔案會上傳到名為 `ingestiondata` 的 Azure Blob 容器。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-212">The PST files will be uploaded to an Azure blob container named `ingestiondata`.</span></span>
  
 <span data-ttu-id="a8fb8-213">**需要多久的時間才能將 PST 檔案匯入信箱？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-213">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="a8fb8-214">PST 檔案上傳到 Azure 儲存體區域之後，Microsoft 365 會以安全的方式分析 PST 檔案中的資料，以識別 PST 檔案所含項目的存留期和各種訊息類型。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-214">After the PST files are uploaded to the Azure Storage area, Microsoft 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="a8fb8-215">這項分析程序完成後，您就可以選擇匯入 PST 檔案中的所有資料，或設定篩選器來控制要匯入的資料。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-215">When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported.</span></span> <span data-ttu-id="a8fb8-216">開始匯入工作之後，PST 會以每天至少 24 GB 的速率匯入至 Microsoft 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-216">After you start the import job, a PST file is imported to a Microsoft 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="a8fb8-217">如果這樣的速率不符您的需求，建議您嘗試其他方法將電子郵件資料匯入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-217">If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365.</span></span> <span data-ttu-id="a8fb8-218">如需詳細資訊，請參閱＜[將多個電子郵件帳戶移轉到 Office 365 的方法](/Exchange/mailbox-migration/mailbox-migration)＞。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-218">For more information, see [Ways to migrate multiple email accounts to Office 365](/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="a8fb8-219">如果不同的 PST 檔案需匯入到不同的目標信箱，匯入程序會同時進行；換句話說，系統會同時匯入每個 PST/信箱組合。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-219">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="a8fb8-220">同樣地，如果多個 PST 檔案匯入到相同的信箱，則會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-220">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="a8fb8-221">**Microsoft 將我的 PST 檔案上傳到 Azure 之後，這些檔案會在 Azure 中保留多久的時間才會刪除？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-221">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="a8fb8-222">貴組織的 Azure 儲存體位置 (儲存在名為 `ingestiondata` 的 Blob 容器) 中的所有 PST 檔案，會在最新的匯入工作於安全性與合規性中心的 [匯入 PST 檔案] 頁面上建立完成的 30 天後遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-222">All PST files in the Azure Storage location for your organization (in blob container named `ingestiondata`), are deleted 30 days after the most recent import job was created on the **Import PST files** page in the Security & Compliance Center.</span></span> 
  
<span data-ttu-id="a8fb8-223">這也表示 PST 檔案從 Azure 儲存體區域刪除之後，安全性與合規性中心內完整匯入工作的檔案清單中就不會顯示這些檔案。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-223">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="a8fb8-224">即使匯入工作仍然列在安全性與合規性中心的 [匯入 PST 檔案] 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-224">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="a8fb8-225">**哪些版本的 PST 檔案格式支援匯入至 Microsoft 365？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-225">**What version of the PST file format is supported for importing to Microsoft 365?**</span></span>
  
<span data-ttu-id="a8fb8-226">有兩個版本的 PST 檔案格式支援此作業：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-226">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="a8fb8-227">我們建議您使用 Unicode PST 檔案格式來匯入檔案。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-227">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="a8fb8-228">不過，使用 ANSI PST 檔案格式的檔案 (例如，使用雙位元組字元集 (DBCS) 語言的檔案) 也可以匯入至 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-228">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Microsoft 365.</span></span> <span data-ttu-id="a8fb8-229">如需有關匯入 ANSI PST 檔案的詳細資訊，請參閱 [使用磁片磁碟機運送將 PST 檔案匯入至 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步驟3。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-229">For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="a8fb8-230">此外，Outlook 2007 和更新版本的 PST 檔案也可以匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-230">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="a8fb8-231">**匯入 PST 檔案時，是否有郵件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-231">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="a8fb8-232">是。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-232">Yes.</span></span> <span data-ttu-id="a8fb8-233">若 PST 檔案包含大於 150 MB 的信箱專案，則會在匯入程式期間略過此專案，且不會匯入。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-233">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped and not imported during the import process.</span></span> <span data-ttu-id="a8fb8-234">不會匯入大於 150 MB 的專案，因為 150 MB 是 Exchange Online 中的郵件大小限制。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-234">Items larger than 150 MB aren't imported because 150 MB is the message size limit in Exchange Online.</span></span> <span data-ttu-id="a8fb8-235">如需詳細資訊，請參閱 [Exchange Online 中的郵件限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits)。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-235">For more information, see [Message limits in Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits).</span></span>
  
  <span data-ttu-id="a8fb8-236">PST 匯入處理程序如何處理重複的電子郵件項目?</span><span class="sxs-lookup"><span data-stu-id="a8fb8-236">**How does the PST import process handle duplicate email items?**</span></span>

<span data-ttu-id="a8fb8-237">PST 匯入處理程序會檢查重複的項目，如果目標資料夾、目標信箱或目標封存中已有相同項目，則不會將資料從 PST 檔案複製到信箱或封存。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-237">The PST import process checks for duplicate items and doesn't copy the items from a PST file to the mailbox or archive if a matching item exists in the target folder in the target mailbox or target archive.</span></span> <span data-ttu-id="a8fb8-238">如果您重新匯入同一個 PST 檔案，並指定與前一個匯入工作指定之資料夾不同的目標資料夾 (使用 PST 匯入對應檔案中的 TargetRootFolder 屬性)，則 PST 檔案中的所有項目將會重新匯入。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-238">If you reimport the same PST file and specify a different target folder (using the TargetRootFolder property in the PST import mapping file) than the one you specified in a previous import job, all items in the PST file will be reimported.</span></span>

 <span data-ttu-id="a8fb8-239">**PST 檔案匯入 Microsoft 365 信箱時是否會保留訊息屬性 (例如訊息的傳送或接收時間、收件者清單、和其他屬性)？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-239">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to a Microsoft 365 mailbox?**</span></span>
  
<span data-ttu-id="a8fb8-240">是。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-240">Yes.</span></span> <span data-ttu-id="a8fb8-241">匯入程序不會變更任何原始的訊息中繼資料</span><span class="sxs-lookup"><span data-stu-id="a8fb8-241">The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="a8fb8-242">**針對我要匯入至信箱的 PST 檔案，其資料夾階層數是否有上限？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-242">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="a8fb8-p134">是。您無法匯入具有 300 或更多巢狀資料夾階層的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-p134">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="a8fb8-245">**我是否可以使用磁碟機寄送將 PST 檔案匯入至 Microsoft 365 中的非作用中的信箱？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-245">**Can I use drive shipping to import PST files to an inactive mailbox in Microsoft 365?**</span></span>
  
<span data-ttu-id="a8fb8-246">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-246">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="a8fb8-247">**我是否可以使用磁碟機寄送將 PST 檔案匯入 Exchange 混合式部署中的線上封存信箱？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-247">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="a8fb8-248">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-248">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="a8fb8-249">**我是否可以使用磁碟機寄送方式將 PST 檔案匯入 Exchange Online 的公用資料夾？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-249">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="a8fb8-250">否，您無法將 PST 檔案匯入公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-250">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="a8fb8-251">**Microsoft 是否可以先將硬碟清空再寄回給我？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-251">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="a8fb8-p135">否，Microsoft 無法先將硬碟清空再寄回給客戶。硬碟會以 Microsoft 當初收到的狀態寄回給您。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-p135">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="a8fb8-254">**Microsoft 是否可以先將硬碟銷毀再寄回給我？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-254">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="a8fb8-p136">否，Microsoft 不能破壞您的硬碟。硬碟會以 Microsoft 當初收到的狀態寄回給您。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-p136">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="a8fb8-257">**哪些快遞服務支援將硬碟寄回客戶？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-257">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="a8fb8-p137">如果您是位於美國或歐洲地區的客戶，Microsoft 會使用 FedEx 將硬碟寄回給您。針對所有其他區域，Microsoft 則會使用 DHL。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-p137">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="a8fb8-260">**將硬碟寄回需要多少費用？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-260">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="a8fb8-p138">實際的寄回費用取決於您將硬碟寄出的所在地區與 Microsoft 資料中心之間的距離。Microsoft 會從您的 FedEx 或 DHL 帳戶收取硬碟寄回費用。寄回費用需由您自行承擔。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-p138">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="a8fb8-264">**我是否能使用自訂運送服務 (例如 FedEx 自訂運送) 將我的硬碟寄給 Microsoft？**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-264">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="a8fb8-265">是。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-265">Yes.</span></span>
  
 <span data-ttu-id="a8fb8-266">**If I have to ship my hard drive to another country, is there anything I need to do?**</span><span class="sxs-lookup"><span data-stu-id="a8fb8-266">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="a8fb8-267">The hard drive that you ship to Microsoft might have to cross international borders.</span><span class="sxs-lookup"><span data-stu-id="a8fb8-267">The hard drive that you ship to Microsoft might have to cross international borders.</span></span> <span data-ttu-id="a8fb8-268">如果是的話，您負責確定要匯入和/或匯出的硬碟及其資料，依照適用的法律。</span><span class="sxs-lookup"><span data-stu-id="a8fb8-268">If so, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws.</span></span> <span data-ttu-id="a8fb8-269">Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center.</span><span class="sxs-lookup"><span data-stu-id="a8fb8-269">Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center.</span></span> <span data-ttu-id="a8fb8-270">This will help to ensure that it reaches Microsoft in a timely manner.</span><span class="sxs-lookup"><span data-stu-id="a8fb8-270">This will help to ensure that it reaches Microsoft in a timely manner.</span></span>