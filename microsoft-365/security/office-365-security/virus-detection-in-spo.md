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
ms.openlocfilehash: 6a47f52a30f90d7a19cc01dc9e14eb9b534ec244
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034947"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="0526f-103">SharePoint Online 中的病毒偵測</span><span class="sxs-lookup"><span data-stu-id="0526f-103">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="0526f-104">Microsoft 365 可以偵測使用者上傳至 SharePoint 線上之檔案中的病毒，以協助保護您的環境免受惡意軟體的攻擊。</span><span class="sxs-lookup"><span data-stu-id="0526f-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="0526f-105">檔案在上傳後可能會進行病毒掃描。</span><span class="sxs-lookup"><span data-stu-id="0526f-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="0526f-106">若發現檔案遭到感染，則會設定屬性，讓使用者無法下載或同步處理檔案。</span><span class="sxs-lookup"><span data-stu-id="0526f-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0526f-107">SharePoint Online 中的這些防病毒功能是一種包含病毒的方式。</span><span class="sxs-lookup"><span data-stu-id="0526f-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="0526f-108">它們不是用來防禦您環境中惡意程式碼的單一防禦點。</span><span class="sxs-lookup"><span data-stu-id="0526f-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="0526f-109">我們鼓勵所有客戶在不同的層級評估和執行反惡意軟體防護，並套用最佳作法，以保護您的企業基礎結構。</span><span class="sxs-lookup"><span data-stu-id="0526f-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="0526f-110">如需策略及最佳作法的詳細資訊，請參閱[安全性藍圖](security-roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="0526f-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="0526f-111">將感染的檔案上傳至 SharePoint 線上時，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="0526f-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="0526f-112">Microsoft 365 使用常見的病毒偵測引擎。</span><span class="sxs-lookup"><span data-stu-id="0526f-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="0526f-113">在線上 SharePoint 中，引擎會以非同步方式執行，並在上載檔案之後掃描檔案。</span><span class="sxs-lookup"><span data-stu-id="0526f-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="0526f-114">試探法是用來判斷要掃描的檔案。</span><span class="sxs-lookup"><span data-stu-id="0526f-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="0526f-115">當找到檔案包含病毒時，會加以標記，使其無法再次下載。</span><span class="sxs-lookup"><span data-stu-id="0526f-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="0526f-116">在4月2018，我們已移除已掃描檔案的 25 MB 限制。</span><span class="sxs-lookup"><span data-stu-id="0526f-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="0526f-117">會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="0526f-117">Here's what happens:</span></span>

1. <span data-ttu-id="0526f-118">使用者將檔案上傳到線上 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="0526f-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="0526f-119">SharePoint 線上決定檔是否符合掃描的準則。</span><span class="sxs-lookup"><span data-stu-id="0526f-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="0526f-120">病毒偵測引擎會掃描檔案。</span><span class="sxs-lookup"><span data-stu-id="0526f-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="0526f-121">如果找到病毒，病毒引擎便會將檔案上的屬性設定為指出其受到感染。</span><span class="sxs-lookup"><span data-stu-id="0526f-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="0526f-122">當使用者嘗試使用瀏覽器下載感染的檔案時，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="0526f-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="0526f-123">如果檔案遭到感染，使用者就無法使用瀏覽器從 SharePoint 線上下載檔案。</span><span class="sxs-lookup"><span data-stu-id="0526f-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="0526f-124">會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="0526f-124">Here's what happens:</span></span>

1. <span data-ttu-id="0526f-125">使用者開啟網頁瀏覽器，並嘗試從 SharePoint 的線上下載感染的檔案。</span><span class="sxs-lookup"><span data-stu-id="0526f-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="0526f-126">使用者會得到偵測到病毒的警告。</span><span class="sxs-lookup"><span data-stu-id="0526f-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="0526f-127">使用者可選擇下載該檔案，並嘗試使用自己的防毒軟體來清除該檔案。</span><span class="sxs-lookup"><span data-stu-id="0526f-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
> <span data-ttu-id="0526f-128">您可以在 SharePoint 線上 PowerShell 的[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)指令程式上使用*DisallowInfectedFileDownload*參數，以防止使用者下載染毒的檔案，即使是在 [反病毒警告] 視窗中也是一樣。</span><span class="sxs-lookup"><span data-stu-id="0526f-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="0526f-129">OneDrive 同步處理用戶端嘗試同步處理已感染的檔案時，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="0526f-129">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="0526f-130">使用者是否要使用新的 OneDrive 同步處理用戶端（OneDrive.exe）或 OneDrive 舊版的 Business sync 用戶端（Groove）同步處理檔案，如果檔案包含病毒，同步處理用戶端將不會下載該檔案。</span><span class="sxs-lookup"><span data-stu-id="0526f-130">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="0526f-131">同步處理用戶端會顯示無法同步處理檔案的通知。</span><span class="sxs-lookup"><span data-stu-id="0526f-131">The sync client will display a notification that the file can't be synced.</span></span>
