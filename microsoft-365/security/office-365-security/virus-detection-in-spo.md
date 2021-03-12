---
title: SharePoint Online、OneDrive 和 Microsoft 團隊中內建的病毒防護
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ba3d19c6b04b93d9b1089540b7483d8b2e7246c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727496"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="2f818-103">SharePoint Online、OneDrive 和 Microsoft 團隊中內建的病毒防護</span><span class="sxs-lookup"><span data-stu-id="2f818-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2f818-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="2f818-104">**Applies to**</span></span>
- [<span data-ttu-id="2f818-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2f818-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2f818-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="2f818-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="2f818-107">Microsoft 365 使用常見的病毒偵測引擎，掃描使用者上傳至 SharePoint 線上、OneDrive 和 Microsoft 小組的檔案。</span><span class="sxs-lookup"><span data-stu-id="2f818-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="2f818-108">這種保護包含在 SharePoint 線上、OneDrive 和 Microsoft 小組的所有訂閱中。</span><span class="sxs-lookup"><span data-stu-id="2f818-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f818-109">內建的防病毒功能是一種協助包含病毒的方式。</span><span class="sxs-lookup"><span data-stu-id="2f818-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="2f818-110">它們不是用來防禦您環境中惡意程式碼的單一防禦點。</span><span class="sxs-lookup"><span data-stu-id="2f818-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="2f818-111">我們鼓勵所有客戶調查和執行各層的反惡意程式碼保護，並套用最佳作法，以保護其企業基礎結構。</span><span class="sxs-lookup"><span data-stu-id="2f818-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="2f818-112">如需策略及最佳作法的詳細資訊，請參閱 [安全性藍圖](security-roadmap.md)。</span><span class="sxs-lookup"><span data-stu-id="2f818-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="2f818-113">將感染的檔案上傳至 SharePoint 線上時，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="2f818-113">What happens if an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="2f818-114">Microsoft 365 病毒偵測引擎會以非同步方式執行 (獨立于 SharePoint 線上中的檔案上傳) 。</span><span class="sxs-lookup"><span data-stu-id="2f818-114">The Microsoft 365 virus detection engine runs asynchronously (independent from file uploads) within SharePoint Online.</span></span> <span data-ttu-id="2f818-115">**不會自動掃描所有** 檔案。</span><span class="sxs-lookup"><span data-stu-id="2f818-115">**All files are not automatically scanned**.</span></span> <span data-ttu-id="2f818-116">啟發式決定要掃描的檔案。</span><span class="sxs-lookup"><span data-stu-id="2f818-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="2f818-117">當找到檔案包含病毒時，就會標示該檔案。</span><span class="sxs-lookup"><span data-stu-id="2f818-117">When a file is found to contain a virus, the file is flagged.</span></span> <span data-ttu-id="2f818-118">在4月2018，我們已移除已掃描檔案的 25 MB 限制。</span><span class="sxs-lookup"><span data-stu-id="2f818-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="2f818-119">會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="2f818-119">Here's what happens:</span></span>

1. <span data-ttu-id="2f818-120">使用者將檔案上傳到線上 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="2f818-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="2f818-121">SharePoint 線上，成為病毒掃描程式的一部分，稍後會判斷檔案是否符合掃描的準則。</span><span class="sxs-lookup"><span data-stu-id="2f818-121">SharePoint Online, as part of its virus scanning processes, later determines if the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="2f818-122">如果檔案符合掃描的準則，病毒偵測引擎便會掃描檔案。</span><span class="sxs-lookup"><span data-stu-id="2f818-122">If the file meets the criteria for a scan, the virus detection engine scans the file.</span></span>
4. <span data-ttu-id="2f818-123">如果在掃描的檔案內找到病毒，病毒引擎便會將檔案上的屬性設定為表示感染的檔案。</span><span class="sxs-lookup"><span data-stu-id="2f818-123">If a virus is found within the scanned file, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="2f818-124">當使用者嘗試使用瀏覽器下載感染的檔案時，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="2f818-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="2f818-125">如果檔案遭到感染，使用者就無法使用瀏覽器從 SharePoint 線上下載檔案。</span><span class="sxs-lookup"><span data-stu-id="2f818-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="2f818-126">會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="2f818-126">Here's what happens:</span></span>

1. <span data-ttu-id="2f818-127">使用者開啟網頁瀏覽器，並嘗試從 SharePoint 的線上下載感染的檔案。</span><span class="sxs-lookup"><span data-stu-id="2f818-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="2f818-128">使用者會得到偵測到病毒的警告。</span><span class="sxs-lookup"><span data-stu-id="2f818-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="2f818-129">根據預設，使用者可以選擇下載檔案，並嘗試使用自身裝置上的反病毒軟體來清除該檔。</span><span class="sxs-lookup"><span data-stu-id="2f818-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="2f818-130">系統管理員可以在 SharePoint 線上 PowerShell 的 [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)指令程式上使用 *DisallowInfectedFileDownload* 參數，以防止使用者在未感染的檔案中下載感染的檔案，即使在反病毒警告視窗中也是一樣。</span><span class="sxs-lookup"><span data-stu-id="2f818-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="2f818-131">如需相關指示，請參閱 [使用 SharePoint 線上 PowerShell 以避免使用者下載惡意](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)檔案。</span><span class="sxs-lookup"><span data-stu-id="2f818-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="2f818-132">一旦您啟用 *DisallowInfectedFileDownload* 參數，就會完全封鎖使用者和系統管理員對偵測到的/封鎖檔案的存取。</span><span class="sxs-lookup"><span data-stu-id="2f818-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="2f818-133">OneDrive 同步處理用戶端嘗試同步處理已感染的檔案時，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="2f818-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="2f818-134">OneDrive 同步處理用戶端將不會下載含有病毒的檔案。</span><span class="sxs-lookup"><span data-stu-id="2f818-134">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="2f818-135">同步處理用戶端會顯示無法同步處理檔案的通知。</span><span class="sxs-lookup"><span data-stu-id="2f818-135">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="2f818-136">使用 Microsoft Defender for Office 365 的延伸功能</span><span class="sxs-lookup"><span data-stu-id="2f818-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="2f818-137">包含 [Microsoft Defender For Office 365](office-365-atp.md) 的 microsoft 365 組織，包含在其訂閱中或以附加元件形式購買，可為 SharePoint、OneDrive 和 Microsoft 團隊啟用安全附件，以增強報表與保護。</span><span class="sxs-lookup"><span data-stu-id="2f818-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](office-365-atp.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="2f818-138">如需詳細資訊，請參閱 [SharePoint、OneDrive 和 Microsoft 小組的安全附件](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="2f818-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="2f818-139">相關文章</span><span class="sxs-lookup"><span data-stu-id="2f818-139">Related Articles</span></span>

[<span data-ttu-id="2f818-140">Microsoft 365 中的惡意程式碼和勒索軟體防護</span><span class="sxs-lookup"><span data-stu-id="2f818-140">Malware and ransomware protection in Microsoft 365</span></span>](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="2f818-141">如需 SharePoint 線上、OneDrive 和 Microsoft 小組的防病毒相關資訊，請參閱 [防範威脅](protect-against-threats.md) 及 [開啟 SharePoint、OneDrive 及 Microsoft 小組的安全附件](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="2f818-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
