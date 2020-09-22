---
title: SharePoint Online 中的病毒偵測
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 深入瞭解 SharePoint 線上如何在使用者上傳的檔案中偵測病毒，並防止使用者下載或同步處理檔案。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8c65db566f165939d72429bcd61b7d0a880814e0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196508"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="b5a0a-103">SharePoint 線上、OneDrive 和 Microsoft 小組中的病毒偵測</span><span class="sxs-lookup"><span data-stu-id="b5a0a-103">Virus detection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b5a0a-104">Microsoft 365 可以偵測使用者上傳至 SharePoint 線上、OneDrive 和 Microsoft 小組的檔案，以協助保護您的環境免受惡意軟體的攻擊。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="b5a0a-105">檔案在上傳後可能會進行病毒掃描。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="b5a0a-106">若發現檔案遭到感染，則會設定屬性，讓使用者無法下載或同步處理檔案。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b5a0a-107">SharePoint Online 中的這些防病毒功能是一種包含病毒的方式。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="b5a0a-108">它們不是用來防禦您環境中惡意程式碼的單一防禦點。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="b5a0a-109">我們鼓勵所有客戶在不同的層級評估和執行反惡意軟體防護，並套用最佳作法，以保護您的企業基礎結構。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="b5a0a-110">如需策略及最佳作法的詳細資訊，請參閱 [安全性藍圖](security-roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="b5a0a-111">將感染的檔案上傳至 SharePoint 線上時，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="b5a0a-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="b5a0a-112">Microsoft 365 使用常見的病毒偵測引擎。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="b5a0a-113">在線上 SharePoint 中，引擎會以非同步方式執行，並在上載檔案之後掃描檔案。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="b5a0a-114">試探法是用來判斷要掃描的檔案。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="b5a0a-115">當找到檔案包含病毒時，會加以標記，使其無法再次下載。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="b5a0a-116">在4月2018，我們已移除已掃描檔案的 25 MB 限制。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="b5a0a-117">會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="b5a0a-117">Here's what happens:</span></span>

1. <span data-ttu-id="b5a0a-118">使用者將檔案上傳到線上 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="b5a0a-119">SharePoint 線上決定檔是否符合掃描的準則。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="b5a0a-120">病毒偵測引擎會掃描檔案。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="b5a0a-121">如果找到病毒，病毒引擎便會將檔案上的屬性設定為指出其受到感染。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="b5a0a-122">當使用者嘗試使用瀏覽器下載感染的檔案時，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="b5a0a-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="b5a0a-123">如果檔案遭到感染，使用者就無法使用瀏覽器從 SharePoint 線上下載檔案。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="b5a0a-124">會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="b5a0a-124">Here's what happens:</span></span>

1. <span data-ttu-id="b5a0a-125">使用者開啟網頁瀏覽器，並嘗試從 SharePoint 的線上下載感染的檔案。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="b5a0a-126">使用者會得到偵測到病毒的警告。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="b5a0a-127">使用者可選擇下載該檔案，並嘗試使用自己的防毒軟體來清除該檔案。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
>
> <span data-ttu-id="b5a0a-128">您可以在 SharePoint 線上 PowerShell 的[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)指令程式上使用*DisallowInfectedFileDownload*參數，以防止使用者下載染毒的檔案，即使是在 [反病毒警告] 視窗中也是一樣。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>
>
> <span data-ttu-id="b5a0a-129">此外，請記住，只要您啟用 *DisallowInfectedFileDownload* 參數，就會完全封鎖使用者和系統管理員對偵測到的/封鎖檔案的存取。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-129">Also keep in mind, that as soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completly blocked for users and administrators.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="b5a0a-130">OneDrive 同步處理用戶端嘗試同步處理已感染的檔案時，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="b5a0a-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="b5a0a-131">使用者與新的 OneDrive 同步處理用戶端同步處理檔案 ( # A0) 或先前 OneDrive 的 Business sync 用戶端 ( # A1) ，如果檔案包含病毒，則同步處理用戶端將不會下載該檔。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-131">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="b5a0a-132">同步處理用戶端會顯示無法同步處理檔案的通知。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-atp"></a><span data-ttu-id="b5a0a-133">使用 Office 365 ATP 的延伸功能</span><span class="sxs-lookup"><span data-stu-id="b5a0a-133">Extended capabilities with Office 365 ATP</span></span>

<span data-ttu-id="b5a0a-134">已啟用 Office 365 ATP for Sharepoint、OneDrive 及 Microsoft 團隊的客戶 & 會 [開啟 SharePoint、OneDrive 和](turn-on-atp-for-spo-odb-and-teams.md) microsoft 團隊的 atp，以管理用於 AV 和 ATP 偵測的隔離檔。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-134">Customers who enabled Office 365 ATP for Sharepoint, OneDrive, and Microsoft Teams [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) are able to use the Security & Compliance Center to manage quarantined files for AV and ATP detections.</span></span> <span data-ttu-id="b5a0a-135">[僅 ATP：使用安全性 & 規範中心管理隔離](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)的檔案。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-135">[ATP Only: Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="more-information"></a><span data-ttu-id="b5a0a-136">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b5a0a-136">More information</span></span>

<span data-ttu-id="b5a0a-137">如需如何設定線上防病毒 SharePoint 的相關資訊，請參閱 [防範威脅](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) 及 [開啟 ATP 的 SharePoint、OneDrive 和 Microsoft 團隊](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) 。</span><span class="sxs-lookup"><span data-stu-id="b5a0a-137">See [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) for more information on how to configure SharePoint Online antivirus.</span></span>


