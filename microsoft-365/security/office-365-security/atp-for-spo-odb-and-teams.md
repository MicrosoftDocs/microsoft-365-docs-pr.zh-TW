---
title: 適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
description: 瞭解 Office 365 的高級威脅防護，以瞭解 SharePoint Online 中的檔案、商務 OneDrive 商務和 Microsoft 團隊。
ms.openlocfilehash: 90e84f0a4393e5097fb59b93693862a21d6d9f2f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44031445"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="4310a-103">適用於 SharePoint、OneDrive 及 Microsoft Teams 的 ATP</span><span class="sxs-lookup"><span data-stu-id="4310a-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="4310a-104">概述適用於 SharePoint、OneDrive 及 Microsoft Teams 的 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="4310a-104">Overview of Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="4310a-105">人們經常使用 SharePoint、OneDrive 和 Microsoft Teams 來共用檔案及共同作業。</span><span class="sxs-lookup"><span data-stu-id="4310a-105">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="4310a-106">有了 [Office 365 進階威脅防護](office-365-atp.md) (ATP)，您的組織可以更安全地進行共同作業。</span><span class="sxs-lookup"><span data-stu-id="4310a-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner.</span></span> <span data-ttu-id="4310a-107">ATP 可協助偵測及封鎖小組網站和文件庫中被視為惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="4310a-107">ATP helps detect and block files that are identified as malicious in team sites and document libraries.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="4310a-108">運作方式</span><span class="sxs-lookup"><span data-stu-id="4310a-108">How it works</span></span>

<span data-ttu-id="4310a-109">當 SharePoint Online、商務用 OneDrive 和 Microsoft Teams 中的檔案被認定為「惡意」時，ATP 會直接與檔案存放區整合來鎖定該檔案。</span><span class="sxs-lookup"><span data-stu-id="4310a-109">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file.</span></span> <span data-ttu-id="4310a-110">下列影像顯示文件庫中偵測到的惡意檔案範例。</span><span class="sxs-lookup"><span data-stu-id="4310a-110">The following image shows an example of a malicious file detected in a library.</span></span>

![商務用 OneDrive 中的檔案，偵測到其中一個是惡意檔案](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="4310a-112">雖然封鎖的檔案仍會列在文件庫和網頁、行動裝置或桌面應用程式中，但您無法開啟、複製、移動或共用封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="4310a-112">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared.</span></span> <span data-ttu-id="4310a-113">不過，您可以刪除封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="4310a-113">People can, however, delete a blocked file.</span></span> <span data-ttu-id="4310a-114">以下範例是使用者行動裝置上呈現的樣子：</span><span class="sxs-lookup"><span data-stu-id="4310a-114">Here's an example of what that looks like on a user's mobile device:</span></span>

![透過 OneDrive 行動應用程式從商務用 OneDrive 中刪除封鎖的檔案](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="4310a-116">根據 Microsoft 365 的設定方式，使用者可能會或可能無法下載封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="4310a-116">Depending on how Microsoft 365 is configured, people might or might not have the ability to download a blocked file.</span></span> <span data-ttu-id="4310a-117">以下是在使用者行動裝置上下載封鎖檔案的畫面：</span><span class="sxs-lookup"><span data-stu-id="4310a-117">Here's what downloading a blocked file looks like on a user's mobile device:</span></span>

![在商務用 OneDrive 中下載封鎖的檔案](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="4310a-119">若要深入了解，請參閱[為 SharePoint、OneDrive 和 Microsoft Teams 開啟 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4310a-119">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="4310a-120">請記住下列重點</span><span class="sxs-lookup"><span data-stu-id="4310a-120">Keep these points in mind</span></span>

- <span data-ttu-id="4310a-121">ATP 不會掃描 SharePoint Online、商務用 OneDrive 或 Microsoft Teams 中的每個單一檔案。</span><span class="sxs-lookup"><span data-stu-id="4310a-121">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="4310a-122">原先的設計就是如此。</span><span class="sxs-lookup"><span data-stu-id="4310a-122">This is by design.</span></span> <span data-ttu-id="4310a-123">檔案會以非同步的方式進行掃描，其程序會使用共用及訪客活動事件，以及智慧試探法和威脅信號來識別惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="4310a-123">Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="4310a-124">請確認您的 SharePoint 網站已設定為使用[新式體驗](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)。</span><span class="sxs-lookup"><span data-stu-id="4310a-124">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="4310a-125">當檔案被識別為惡意並且遭到封鎖時，人們可以在新式體驗中看到此動作已發生，但在傳統檢視中看不到。</span><span class="sxs-lookup"><span data-stu-id="4310a-125">When a file is identified as malicious and blocked, people can see that this has occurred in the Modern experience, but not the Classic view.</span></span> <span data-ttu-id="4310a-126">使用新式體驗或傳統檢視都可套用 ATP 保護；不過，指出檔案遭到封鎖的視覺指示器只會在新式體驗中提供。</span><span class="sxs-lookup"><span data-stu-id="4310a-126">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are present only in the Modern experience.</span></span>

- <span data-ttu-id="4310a-127">在 SharePoint Online、商務用 OneDrive 或 Microsoft Teams 中識別為惡意的檔案會顯示在 [Office 365 進階威脅防護的報告](view-reports-for-atp.md)和 [Explorer (與即時偵測)](threat-explorer.md) 中。</span><span class="sxs-lookup"><span data-stu-id="4310a-127">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

- <span data-ttu-id="4310a-128">ATP 是組織整體威脅防護戰略的一部分，其中包括反垃圾郵件和反惡意程式碼防護，以及安全連結和安全附件。</span><span class="sxs-lookup"><span data-stu-id="4310a-128">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments.</span></span> <span data-ttu-id="4310a-129">若要深入了解，請參閱[防範 Office 365 中的威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="4310a-129">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="4310a-130">SharePoint Online 系統管理員可以決定是否要讓使用者下載偵測為惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="4310a-130">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious.</span></span> <span data-ttu-id="4310a-131">方法是使用 DisallowInfectedFileDownload 參數執行 Set-SPOTenant PowerShell Cmdlet (請參閱[開啟適用於 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md))。</span><span class="sxs-lookup"><span data-stu-id="4310a-131">This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="4310a-132">ATP 在 SharePoint Online、商務用 OneDrive 和 Microsoft Teams 中的隔離功能</span><span class="sxs-lookup"><span data-stu-id="4310a-132">Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="4310a-133">自 2018 年的 5 月底起，安全性 &amp; 合規性中心的[隔離](quarantine-email-messages.md)功能已延伸至適用於 SharePoint Online、商務用 OneDrive 和 Microsoft Teams 的 ATP。</span><span class="sxs-lookup"><span data-stu-id="4310a-133">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="4310a-134">當 SharePoint Online、商務用 OneDrive 或 Microsoft Teams 中的檔案被識別為惡意時，ATP 除了會防止檔案開啟或共用之外，該檔案也會包含在隔離項目清單中。</span><span class="sxs-lookup"><span data-stu-id="4310a-134">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items.</span></span> <span data-ttu-id="4310a-135">（在&amp;安全性與合規性中心，移至「**威脅管理** \> 」**查看** \> **隔離**及篩選檔案。） **Files**</span><span class="sxs-lookup"><span data-stu-id="4310a-135">(In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for **Files**.)</span></span>

<span data-ttu-id="4310a-136">如果您屬於組織的 Microsoft 365 商務安全小組，而且在[安全性&amp;與合規性中心內指派](permissions-in-the-security-and-compliance-center.md)必要的許可權，您可以從隔離區下載、發行、報告和刪除因 ATP 所偵測為惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="4310a-136">If you're part of your organization's Microsoft 365 for business security team and have the necessary [permissions assigned in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>

- <span data-ttu-id="4310a-137">針對 SharePoint、OneDrive 或 Microsoft Teams，**釋放和報告**檔案會移除各別小組網站或文件庫中檔案上的 ATP 封鎖。</span><span class="sxs-lookup"><span data-stu-id="4310a-137">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams.</span></span> <span data-ttu-id="4310a-138">然後使用者就能開啟、共用和下載該檔案。</span><span class="sxs-lookup"><span data-stu-id="4310a-138">Users are then able to open, share, and download the file.</span></span> <span data-ttu-id="4310a-139">此外，當您選取 [將報告傳送到 Microsoft]\*\*\*\* 選項時，該檔案就會以誤判的形式來報告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="4310a-139">And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span>

- <span data-ttu-id="4310a-140">**刪除檔案**會將檔案從隔離區中移除；不過，檔案仍無法開啟或共用。</span><span class="sxs-lookup"><span data-stu-id="4310a-140">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared.</span></span> <span data-ttu-id="4310a-141">您也必須在其各自的文件庫或小組網站中刪除檔案 (SharePoint Online、商務用 OneDrive 或 Microsoft Teams)。</span><span class="sxs-lookup"><span data-stu-id="4310a-141">The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span>

- <span data-ttu-id="4310a-142">**下載檔案**可讓您下載檔案，並分析是否有任何誤判。</span><span class="sxs-lookup"><span data-stu-id="4310a-142">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4310a-143">後續步驟</span><span class="sxs-lookup"><span data-stu-id="4310a-143">Next steps</span></span>

 - [<span data-ttu-id="4310a-144">開啟適用於 SharePoint、OneDrive 及 Microsoft Teams 的 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="4310a-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)

 - [<span data-ttu-id="4310a-145">檢視在 SharePoint、OneDrive 或 Microsoft Teams 中偵測到的惡意檔案資訊</span><span class="sxs-lookup"><span data-stu-id="4310a-145">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

