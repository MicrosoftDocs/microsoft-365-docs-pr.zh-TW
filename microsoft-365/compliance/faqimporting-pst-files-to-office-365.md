---
title: 將 PST 檔案匯入 Office 365 的常見問題
f1.keywords:
- NOCSH
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
description: '有關使用 Office 365 Import Service 將組織的 PST 檔案匯入 Office 365 信箱之系統管理員的常見問題。 '
ms.openlocfilehash: 31df33ffe2c69478f0304bd27b49254995d8b89c
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634431"
---
# <a name="faq-about-importing-pst-files-to-office-365"></a><span data-ttu-id="0e6a8-103">將 PST 檔案匯入 Office 365 的常見問題</span><span class="sxs-lookup"><span data-stu-id="0e6a8-103">FAQ about importing PST files to Office 365</span></span>

<span data-ttu-id="0e6a8-104">**本文適用于系統管理員。您是否要將 PST 檔案匯入您自己的信箱？請參閱[從 Outlook .pst 檔案匯入電子郵件、連絡人及行事曆](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span><span class="sxs-lookup"><span data-stu-id="0e6a8-104">**This article is for administrators. Do you want to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|</span></span>
   
<span data-ttu-id="0e6a8-105">以下是一些有關使用 Office 365 Import Service 將 PST 檔案大量匯入 Office 365 信箱的常見問題。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-105">Here are some frequently asked questions about using the Office 365 Import Service to bulk-import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="0e6a8-106">如需如何匯入 PST 檔案的詳細資訊，請參閱[將 pst 檔案匯入至 Office 365 的概述](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84)。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-106">For more information about how to import PST files, see [Overview of importing PST files to Office 365](https://support.office.com/article/ba688e0a-0fcb-4bd7-8e57-2b669564ea84).</span></span>
  
## <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="0e6a8-107">使用網路上傳來匯入 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="0e6a8-107">Using network upload to import PST files</span></span>

<span data-ttu-id="0e6a8-108">如需逐步指示，請參閱[使用網路上傳將 PST 檔案匯入 Office 365](use-network-upload-to-import-pst-files.md)。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-108">For step-by-step instructions, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
  
 <span data-ttu-id="0e6a8-109">**必須具備哪些權限才能在 Office365 匯入服務中建立匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-109">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="0e6a8-110">您必須在 Exchange Online 中獲派信箱匯入匯出角色，才能將 PST 檔案匯入 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-110">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="0e6a8-111">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-111">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="0e6a8-112">You can add the Mailbox Import Export role to the Organization Management role group.</span><span class="sxs-lookup"><span data-stu-id="0e6a8-112">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="0e6a8-113">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span><span class="sxs-lookup"><span data-stu-id="0e6a8-113">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="0e6a8-114">如需詳細資訊，請參閱[管理 Exchange Online 中的角色](https://go.microsoft.com/fwlink/p/?LinkId=730688)之＜新增角色至角色群組＞或＜建立角色群組＞一節。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-114">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="0e6a8-115">此外，若要在安全性與合規性中心建立匯入工作，必須符合以下其中一個條件：</span><span class="sxs-lookup"><span data-stu-id="0e6a8-115">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="0e6a8-116">您必須在 Exchange Online 中獲派郵件收件者角色。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-116">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="0e6a8-117">根據預設，這個角色會指派給組織管理及收件者管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-117">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="0e6a8-118">或</span><span class="sxs-lookup"><span data-stu-id="0e6a8-118">Or</span></span>
    
- <span data-ttu-id="0e6a8-119">您必須是您 Office365 組織中的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-119">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="0e6a8-120">建議您在 Exchange Online 中建立新的角色群組，專門用來將 PST 檔案匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-120">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="0e6a8-121">若要獲得匯入 PST 檔案所需的最低權限等級，請將信箱匯入匯出及郵件收件者角色指派到新的角色群組，然後新增成員。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-121">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="0e6a8-122">**哪些地區提供網路上傳服務？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-122">**Where is network upload available?**</span></span>
  
<span data-ttu-id="0e6a8-123">下列地區目前提供網路上傳：美國、加拿大、巴西、英國、法國、歐洲、印度、東亞洲、東南亞、日本、韓國和澳大利亞。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-123">Network upload is currently available in these regions: United States, Canada, Brazil, the United Kingdom, France, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="0e6a8-124">Network upload will be available in more regions soon.</span><span class="sxs-lookup"><span data-stu-id="0e6a8-124">Network upload will be available in more regions soon.</span></span>

> [!NOTE]
> <span data-ttu-id="0e6a8-125">目前無法在德國和瑞士使用網路上傳 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-125">At this time, network upload of PST files is not available in Germany and Switzerland.</span></span> <span data-ttu-id="0e6a8-126">當這些國家/地區開放使用網路上傳時，將會更新此常見問題。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-126">This FAQ will be updated when network upload is available in these countries.</span></span>
  
 <span data-ttu-id="0e6a8-127">**使用網路上傳匯入 PST 檔案的費用為何？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-127">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="0e6a8-128">Using network upload to import PST files is free.</span><span class="sxs-lookup"><span data-stu-id="0e6a8-128">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="0e6a8-129">這也表示 PST 檔案從 Azure 儲存體區域刪除之後，Microsoft 365 系統管理中心內完整匯入工作的檔案清單中就不會顯示這些檔案。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-129">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0e6a8-130">即使匯入工作仍然列在 **[將資料匯入 Office 365]** 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-130">Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="0e6a8-131">**哪些版本的 PST 檔案格式支援匯入 Office 365？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-131">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="0e6a8-132">有兩個版本的 PST 檔案格式支援此作業：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-132">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="0e6a8-133">我們建議您使用 Unicode PST 檔案格式來匯入檔案。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-133">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="0e6a8-134">不過，使用 ANSI PST 檔案格式的檔案 (例如，使用雙位元組字元集 (DBCS) 語言的檔案) 也可以匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-134">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="0e6a8-135">如需有關匯入 ANSI PST 檔案的詳細資訊，請參閱[使用網路上傳將組織的 PST 檔案匯入 Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)中的步驟4。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-135">For more information about importing ANSI PST files, see Step 4 in [Use network upload to import your organization's PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="0e6a8-136">此外，Outlook 2007 和更新版本的 PST 檔案也可以匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-136">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="0e6a8-137">**將我的 PST 檔案上傳到 Azure 儲存體區域之後，這些檔案會在 Azure 中保留多久的時間才會遭到刪除？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-137">**After I upload my PST files to the Azure Storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="0e6a8-138">使用網路上傳方法來匯入 PST 檔案會將這些檔案上傳到名為 **ingestiondata** 的 Azure Blob 容器。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-138">When you use the network upload method to import PST files, you upload them to an Azure blob container named **ingestiondata**.</span></span> <span data-ttu-id="0e6a8-139">如果安全性與合規性中心的 [匯入 PST 檔案]\*\*\*\* 頁面目前沒有進行中的匯入工作，則 Azure 中 **ingestiondata** 容器內的所有 PST 檔案都會在最近的匯入工作於安全性與合規性中心建立完成的後 30 天刪除。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-139">If there are no import jobs in progress on the **Import PST files** page in the Security & Compliance Center), then all PST files in the **ingestiondata** container in Azure are deleted 30 days after the most recent import job was created in the Security & Compliance Center.</span></span> <span data-ttu-id="0e6a8-140">這也表示您必須在 PST 檔案上傳到 Azure 的 30 天內，在安全性與合規性中心建立新的匯入工作 (如網路上傳指示中的步驟 5 所述)。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-140">That also means you have to create a new import job in the Security & Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="0e6a8-141">這也表示 PST 檔案從 Azure 儲存體區域刪除之後，安全性與合規性中心內完整匯入工作的檔案清單中就不會顯示這些檔案。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-141">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="0e6a8-142">即使匯入工作仍然列在安全性與合規性中心的 [匯入 PST 檔案]\*\*\*\* 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-142">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="0e6a8-143">**需要多久的時間才能將 PST 檔案匯入信箱？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-143">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="0e6a8-144">這取決於您的網路容量，但將每 TB 的資料上傳到貴組織的 Azure 儲存體區域通常需要幾個小時的時間。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-144">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure Storage area for your organization.</span></span> <span data-ttu-id="0e6a8-145">將 PST 檔案複製到 Azure 儲存體區域之後，系統會以每天至少 24 GB 的速率將 PST 檔案匯入到 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-145">After the PST files are copied to the Azure Storage area, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="0e6a8-146">如果這樣的速率不符您的需求，建議您嘗試其他方法將電子郵件資料移轉到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-146">If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365.</span></span> <span data-ttu-id="0e6a8-147">如需詳細資訊，請參閱＜[將多個電子郵件帳戶移轉到 Office 365 的方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)＞。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-147">For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="0e6a8-148">如果不同的 PST 檔案需匯入到不同的目標信箱，匯入程序會同時進行；換句話說，系統會同時匯入每個 PST/信箱組合。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-148">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="0e6a8-149">同樣地，如果多個 PST 檔案匯入到相同的信箱，則會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-149">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="0e6a8-150">**匯入 PST 檔案時，是否有郵件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-150">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="0e6a8-151">是。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-151">Yes.</span></span> <span data-ttu-id="0e6a8-152">如果 PST 檔案包含大於 150 MB 的信箱項目，該項目會在匯入程序執行時略過。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-152">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="0e6a8-153">**PST 檔案匯入 Office 365 信箱時是否會保留訊息內容 (例如訊息的傳送或接收時間、收件者清單等等)？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-153">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="0e6a8-154">是。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-154">Yes.</span></span> <span data-ttu-id="0e6a8-155">匯入程序不會變更任何原始的訊息中繼資料。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-155">The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="0e6a8-156">**針對我要匯入至信箱的 PST 檔案，其資料夾階層數是否有上限？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-156">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="0e6a8-p115">是。您無法匯入具有 300 或更多巢狀資料夾階層的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-p115">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="0e6a8-159">**我是否可以使用網路上傳將 PST 檔案匯入 Office 365 中的非作用中的信箱？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-159">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="0e6a8-160">Yes, this capability is now available. </span><span class="sxs-lookup"><span data-stu-id="0e6a8-160">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="0e6a8-161">**我是否可以使用網路上傳將 PST 檔案匯入 Exchange 混合式部署中的線上封存信箱？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-161">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="0e6a8-162">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-162">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="0e6a8-163">**我是否可以使用網路上傳方式將 PST 檔匯入 Exchange Online 的公用資料夾？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-163">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="0e6a8-164">否，您無法將 PST 檔案匯入公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-164">No, you can't import PST files to public folders.</span></span>
  
## <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="0e6a8-165">使用磁碟機寄送來匯入 PST 檔案</span><span class="sxs-lookup"><span data-stu-id="0e6a8-165">Using drive shipping to import PST files</span></span>

<span data-ttu-id="0e6a8-166">如需逐步指示，請參閱[使用磁片磁碟機運送將 PST 檔案匯入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-166">For step-by-step instructions, see [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).</span></span>
  
 <span data-ttu-id="0e6a8-167">**必須具備哪些權限才能在 Office365 匯入服務中建立匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-167">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="0e6a8-168">您必須獲派信箱匯入匯出角色才能將 PST 檔案匯入 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-168">You have to be assigned the Mailbox Import Export role to import PST files to Office 365 mailboxes.</span></span> <span data-ttu-id="0e6a8-169">依預設，此角色不會指派給 Exchange Online 內的任何角色群組。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-169">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="0e6a8-170">You can add the Mailbox Import Export role to the Organization Management role group.</span><span class="sxs-lookup"><span data-stu-id="0e6a8-170">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="0e6a8-171">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span><span class="sxs-lookup"><span data-stu-id="0e6a8-171">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="0e6a8-172">如需詳細資訊，請參閱[管理 Exchange Online 中的角色](https://go.microsoft.com/fwlink/p/?LinkId=730688)之＜新增角色至角色群組＞或＜建立角色群組＞一節。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-172">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="0e6a8-173">此外，若要在安全性與合規性中心建立匯入工作，必須符合以下其中一個條件：</span><span class="sxs-lookup"><span data-stu-id="0e6a8-173">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="0e6a8-174">您必須在 Exchange Online 中獲派郵件收件者角色。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-174">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="0e6a8-175">根據預設，這個角色會指派給組織管理及收件者管理角色群組。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-175">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="0e6a8-176">或</span><span class="sxs-lookup"><span data-stu-id="0e6a8-176">Or</span></span>
    
- <span data-ttu-id="0e6a8-177">您必須是您 Office365 組織中的全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-177">You have to be a global administrator in your Office 365 organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="0e6a8-178">建議您在 Exchange Online 中建立新的角色群組，專門用來將 PST 檔案匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-178">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="0e6a8-179">若要獲得匯入 PST 檔案所需的最低權限等級，請將信箱匯入匯出及郵件收件者角色指派到新的角色群組，然後新增成員。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-179">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="0e6a8-180">**哪些地區提供磁碟機寄送服務？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-180">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="0e6a8-181">磁碟機寄送的服務範圍目前包括美國、加拿大、巴西、英國、歐洲、印度、東亞、東南亞、日本、大韓民國和澳洲。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-181">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="0e6a8-182">我們會盡快在更多地區提供磁碟機寄送服務。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-182">Drive shipping will be available in more regions soon.</span></span>

> [!NOTE]
> <span data-ttu-id="0e6a8-183">目前在德國和瑞士不開放使用磁碟機寄送匯入 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-183">At this time, drive shipping to import PST files is not available in Germany and Switzerland.</span></span> <span data-ttu-id="0e6a8-184">當這些國家/地區開放磁碟機寄送時，將會更新此常見問題。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-184">This FAQ will be updated when drive shipping is available in these countries.</span></span>
  
 <span data-ttu-id="0e6a8-185">**有哪些商業授權合約支援磁碟機寄送？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-185">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="0e6a8-186">Microsoft Enterprise Agreement (EA) 提供將 PST 檔案匯入 Office 365 的磁碟機寄送服務。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-186">Drive shipping to import PST files to Office 365 is available through a Microsoft Enterprise Agreement (EA).</span></span> <span data-ttu-id="0e6a8-187">Microsoft Products and Services Agreement (MPSA) 則沒有提供磁碟機寄送。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-187">Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="0e6a8-188">**使用磁碟機寄送將 PST 檔案匯入 Office 365 的費用為何？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-188">**What is the pricing for using drive shipping to import PST files to Office 365?**</span></span>
  
<span data-ttu-id="0e6a8-189">使用磁碟機寄送將 PST 檔案匯入 Office 365 信箱的費用為每 GB 的資料 $2 美元。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-189">The cost to use drive shipping to import PST files to Office 365 mailboxes is $2 USD per GB of data.</span></span> <span data-ttu-id="0e6a8-190">例如，假設您寄送的硬碟含有 1,000 GB (即 1 TB) 的 PST 檔案，則費用為 $2,000 美元。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-190">For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD.</span></span> <span data-ttu-id="0e6a8-191">您可以與夥伴合作來支付匯入費用。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-191">You can work with a partner to pay the import fee.</span></span> <span data-ttu-id="0e6a8-192">如需有關尋找合作夥伴的資訊，請參閱[尋找您的 Office 365 合作夥伴或轉售商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-192">For information about finding a partner, see [Find your Office 365 partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="0e6a8-193">**哪些類型的硬碟支援磁碟機寄送？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-193">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="0e6a8-194">Office 365 匯入服務只支援使用 2.5 吋固態硬碟 (SSD)，或是 2.5 吋或 3.5 吋 SATA II/III 內接式硬碟。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-194">Only 2.5 inch solid-state drives (SSDs) or 2.5 or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service.</span></span> <span data-ttu-id="0e6a8-195">您可以使用最多 10 TB 的硬碟。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-195">You can use hard drives up to 10 TB.</span></span> <span data-ttu-id="0e6a8-196">匯入作業時，只會處理硬碟上的第一個資料磁碟區。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-196">For import jobs, only the first data volume on the hard drive will be processed.</span></span> <span data-ttu-id="0e6a8-197">資料磁碟區必須為 NTFS 格式。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-197">The data volume must be formatted with NTFS.</span></span> <span data-ttu-id="0e6a8-198">若要將資料複製到硬碟，您可以直接使用 2.5 吋 SSD 或是 2.5 吋或 3.5 吋 SATA II/III 連接器進行連接，或者使用外接式 2.5 吋 SSD 或是 2.5 吋或 3.5 吋 SATA II/III USB 轉接頭進行外接。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-198">When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0e6a8-199">Office 365 匯入服務不支援隨附內建 USB 轉接頭的外接式硬碟。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-199">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service.</span></span> <span data-ttu-id="0e6a8-200">此外，位於外部硬碟外殼內的碟無法使用。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-200">Additionally, the disk inside the casing of an external hard drive can't be used.</span></span> <span data-ttu-id="0e6a8-201">請不要使用外接式硬碟。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-201">Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="0e6a8-202">**可以寄送幾個硬碟來進行單一匯入工作？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-202">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="0e6a8-203">最多可以寄送 10 個硬碟來進行單一匯入工作。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-203">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="0e6a8-204">**寄送硬碟之後，需要多久的時間才會送達 Microsoft 資料中心？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-204">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="0e6a8-p125">這取決於幾個要素，例如您與 Microsoft 資料中心之間的距離，以及您使用什麼類型的運送選項來寄送硬碟 (例如，隔天送達、兩日送達或陸地運送)。大多數貨運公司提供追蹤號碼，讓您可以追蹤運送狀態。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-p125">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="0e6a8-207">**硬碟送達 Microsoft 資料中心後，需要多久的時間才能將我的 PST 檔案上傳到 Azure？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-207">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="0e6a8-208">當您在 Microsoft 資料中心接收到硬碟後，需要7到10個工作日才能將 PST 檔案上傳至組織的 Azure 存放區。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-208">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Azure Storage area for your organization.</span></span> <span data-ttu-id="0e6a8-209">PST 檔案會上傳至名為**ingestiondata**的 Azure blob 容器。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-209">The PST files will be uploaded to an Azure blob container named **ingestiondata**.</span></span> 
  
 <span data-ttu-id="0e6a8-210">**需要多久的時間才能將 PST 檔案匯入信箱？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-210">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="0e6a8-211">PST 檔案上傳到 Azure 儲存體區域之後，Office 365 會以安全的方式分析 PST 檔案中的資料，來識別 PST 檔案所含項目的保存時間和各種訊息類型。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-211">After the PST files are uploaded to the Azure Storage area, Office 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="0e6a8-212">這項分析程序完成後，您就可以選擇匯入 PST 檔案中的所有資料，或設定篩選器來控制要匯入的資料。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-212">When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported.</span></span> <span data-ttu-id="0e6a8-213">始匯入工作之後，PST 會以每天至少 24 GB 的速率匯入到 Office 365 信箱。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-213">After you start the import job, a PST file is imported to an Office 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="0e6a8-214">如果這樣的速率不符您的需求，建議您嘗試其他方法將電子郵件資料匯入到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-214">If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365.</span></span> <span data-ttu-id="0e6a8-215">如需詳細資訊，請參閱＜[將多個電子郵件帳戶移轉到 Office 365 的方法](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842)＞。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-215">For more information, see [Ways to migrate multiple email accounts to Office 365](https://support.office.com/article/ways-to-migrate-multiple-email-accounts-to-office-365-0a4913fe-60fb-498f-9155-a86516418842).</span></span>
  
<span data-ttu-id="0e6a8-216">如果不同的 PST 檔案需匯入到不同的目標信箱，匯入程序會同時進行；換句話說，系統會同時匯入每個 PST/信箱組合。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-216">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="0e6a8-217">同樣地，如果多個 PST 檔案匯入到相同的信箱，則會同時匯入。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-217">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="0e6a8-218">**Microsoft 將我的 PST 檔案上傳到 Azure 之後，這些檔案會在 Azure 中保留多久的時間才會刪除？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-218">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="0e6a8-219">在 [安全性 & 合規性中心的 [匯**入 PST**檔案] 頁面上建立最近的匯入工作30天之後，會刪除您組織之 Azure 儲存體位置中的所有 PST 檔案（在 blob 容器中稱為**ingestiondata**）。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-219">All PST files in the Azure Storage location for your organization (in blob container named **ingestiondata**), are deleted 30 days after the most recent import job was created on the **Import PST files** page in the Security & Compliance Center.</span></span> 
  
<span data-ttu-id="0e6a8-220">這也表示 PST 檔案從 Azure 儲存體區域刪除之後，安全性與合規性中心內完整匯入工作的檔案清單中就不會顯示這些檔案。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-220">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="0e6a8-221">即使匯入工作仍然列在安全性與合規性中心的 [匯入 PST 檔案]\*\*\*\* 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-221">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="0e6a8-222">**哪些版本的 PST 檔案格式支援匯入 Office 365？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-222">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="0e6a8-223">有兩個版本的 PST 檔案格式支援此作業：ANSI 和 Unicode。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-223">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="0e6a8-224">我們建議您使用 Unicode PST 檔案格式來匯入檔案。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-224">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="0e6a8-225">不過，使用 ANSI PST 檔案格式的檔案 (例如，使用雙位元組字元集 (DBCS) 語言的檔案) 也可以匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-225">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="0e6a8-226">如需有關匯入 ANSI PST 檔案的詳細資訊，請參閱[使用磁片磁碟機運送將 PST 檔案匯入至 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步驟3。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-226">For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="0e6a8-227">此外，Outlook 2007 和更新版本的 PST 檔案也可以匯入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-227">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="0e6a8-228">**匯入 PST 檔案時，是否有郵件大小限制？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-228">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="0e6a8-229">是。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-229">Yes.</span></span> <span data-ttu-id="0e6a8-230">如果 PST 檔案包含大於 150 MB 的信箱項目，該項目會在匯入程序執行時略過。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-230">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="0e6a8-231">**PST 檔案匯入 Office 365 信箱時是否會保留訊息內容 (例如訊息的傳送或接收時間、收件者清單等等)？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-231">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to an Office 365 mailbox?**</span></span>
  
<span data-ttu-id="0e6a8-232">是。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-232">Yes.</span></span> <span data-ttu-id="0e6a8-233">匯入程序不會變更任何原始的訊息中繼資料</span><span class="sxs-lookup"><span data-stu-id="0e6a8-233">The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="0e6a8-234">**針對我要匯入至信箱的 PST 檔案，其資料夾階層數是否有上限？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-234">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="0e6a8-p133">是。您無法匯入具有 300 或更多巢狀資料夾階層的 PST 檔案。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-p133">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="0e6a8-237">**我是否可以使用磁碟機寄送將 PST 檔案匯入 Office 365 中的非作用中的信箱？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-237">**Can I use drive shipping to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="0e6a8-238">Yes, this capability is now available.</span><span class="sxs-lookup"><span data-stu-id="0e6a8-238">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="0e6a8-239">**我是否可以使用磁碟機寄送將 PST 檔案匯入 Exchange 混合式部署中的線上封存信箱？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-239">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="0e6a8-240">是，我們現已推出這項功能。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-240">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="0e6a8-241">**我是否可以使用磁碟機寄送方式將 PST 檔案匯入 Exchange Online 的公用資料夾？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-241">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="0e6a8-242">否，您無法將 PST 檔案匯入公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-242">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="0e6a8-243">**Microsoft 是否可以先將硬碟清空再寄回給我？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-243">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="0e6a8-p134">否，Microsoft 無法先將硬碟清空再寄回給客戶。硬碟會以 Microsoft 當初收到的狀態寄回給您。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-p134">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="0e6a8-246">**Microsoft 是否可以先將硬碟銷毀再寄回給我？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-246">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="0e6a8-p135">否，Microsoft 不能破壞您的硬碟。硬碟會以 Microsoft 當初收到的狀態寄回給您。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-p135">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="0e6a8-249">**哪些快遞服務支援將硬碟寄回客戶？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-249">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="0e6a8-p136">如果您是位於美國或歐洲地區的客戶，Microsoft 會使用 FedEx 將硬碟寄回給您。針對所有其他區域，Microsoft 則會使用 DHL。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-p136">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="0e6a8-252">**將硬碟寄回需要多少費用？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-252">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="0e6a8-p137">實際的寄回費用取決於您將硬碟寄出的所在地區與 Microsoft 資料中心之間的距離。Microsoft 會從您的 FedEx 或 DHL 帳戶收取硬碟寄回費用。寄回費用需由您自行承擔。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-p137">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="0e6a8-256">**我是否能使用自訂運送服務 (例如 FedEx 自訂運送) 將我的硬碟寄給 Microsoft？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-256">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="0e6a8-257">是。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-257">Yes.</span></span>
  
 <span data-ttu-id="0e6a8-258">**如果我需要將硬碟寄到其他國家/地區，我需要採取什麼動作嗎？**</span><span class="sxs-lookup"><span data-stu-id="0e6a8-258">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="0e6a8-p138">您寄給 Microsoft 的硬碟可能會跨國際邊界。在這種情況下，您必須負責確保硬碟和當中的資料可依據相關法律進口和/或出口。寄送硬碟之前，請與您的顧問確認磁碟機和當中的資料可以合法地寄到指定的 Microsoft 資料中心，以確保 Microsoft 能夠及時收到您的硬碟。</span><span class="sxs-lookup"><span data-stu-id="0e6a8-p138">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
