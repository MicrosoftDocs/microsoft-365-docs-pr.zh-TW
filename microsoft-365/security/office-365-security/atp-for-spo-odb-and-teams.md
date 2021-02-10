---
title: 適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 深入瞭解 Microsoft Defender for Office 365，以瞭解 SharePoint Online 中的檔案、商務 OneDrive，以及 Microsoft 團隊。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 640867cb38dab650bca990fe36c0b7cea7f6a0d8
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175724"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="9733e-103">適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件</span><span class="sxs-lookup"><span data-stu-id="9733e-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9733e-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="9733e-104">**Applies to**</span></span>
- [<span data-ttu-id="9733e-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="9733e-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="9733e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9733e-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="9733e-107">[Microsoft Defender For Office 365](office-365-atp.md)中 SharePoint、OneDrive 和 Microsoft 小組的安全附件，為[microsoft 365 中的常見病毒偵測引擎](virus-detection-in-spo.md)，針對在上傳時已掃描的檔案，提供額外的保護層級。</span><span class="sxs-lookup"><span data-stu-id="9733e-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="9733e-108">SharePoint、OneDrive 和 Microsoft 團隊的安全附件可協助偵測和封鎖在小組網站和文件庫中識別為惡意的現有檔案。</span><span class="sxs-lookup"><span data-stu-id="9733e-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="9733e-109">預設不會啟用 SharePoint、OneDrive 和 Microsoft 小組的安全附件。</span><span class="sxs-lookup"><span data-stu-id="9733e-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="9733e-110">若要將其開啟，請參閱 [開啟安全附件的 SharePoint、OneDrive 和 Microsoft 團隊](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="9733e-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="9733e-111">SharePoint、OneDrive 和 Microsoft 小組的安全附件的運作方式</span><span class="sxs-lookup"><span data-stu-id="9733e-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="9733e-112">啟用 SharePoint、OneDrive 和 Microsoft 小組的安全附件，並將檔案識別為惡意時，會使用直接整合與檔案存放區來鎖定檔案。</span><span class="sxs-lookup"><span data-stu-id="9733e-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="9733e-113">下列影像顯示文件庫中偵測到的惡意檔案範例。</span><span class="sxs-lookup"><span data-stu-id="9733e-113">The following image shows an example of a malicious file detected in a library.</span></span>

![商務用 OneDrive 中的檔案，偵測到其中一個是惡意檔案](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="9733e-115">雖然封鎖的檔案仍然會列在文件庫和 web、行動裝置或桌面應用程式中，但無法開啟、複製、移動或共用檔案。</span><span class="sxs-lookup"><span data-stu-id="9733e-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="9733e-116">但可刪除封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="9733e-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="9733e-117">以下是在行動裝置上封鎖的檔案外觀的範例：</span><span class="sxs-lookup"><span data-stu-id="9733e-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![透過 OneDrive 行動應用程式從商務用 OneDrive 中刪除封鎖的檔案](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="9733e-119">根據預設，使用者可以下載封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="9733e-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="9733e-120">以下是在行動裝置上下載封鎖的檔案的外觀：</span><span class="sxs-lookup"><span data-stu-id="9733e-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![在商務用 OneDrive 中下載封鎖的檔案](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="9733e-122">SharePoint Online admins 可防止使用者下載惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="9733e-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="9733e-123">如需相關指示，請參閱 [使用 SharePoint 線上 PowerShell 以避免使用者下載惡意](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)檔案。</span><span class="sxs-lookup"><span data-stu-id="9733e-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="9733e-124">若要深入了解當檔案被偵測為惡意檔案時的使用者體驗，請參閱[在 SharePoint Online、OneDrive 或 Microsoft Teams 中找到惡意檔案時該怎麼做](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。</span><span class="sxs-lookup"><span data-stu-id="9733e-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="9733e-125">查看 SharePoint、OneDrive 和 Microsoft 小組安全附件所偵測到之惡意檔案的相關資訊</span><span class="sxs-lookup"><span data-stu-id="9733e-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="9733e-126">Microsoft Defender for Office 365 所識別為惡意的檔案，會顯示 [Microsoft defender For office 365](view-reports-for-atp.md) 及 [Explorer (和即時偵測) ](threat-explorer.md)中的報告。</span><span class="sxs-lookup"><span data-stu-id="9733e-126">Files that are identified as malicious by Microsoft Defender for Office 365 will show up in [reports for Microsoft Defender for Office 365](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="9733e-127">從5月2018，當檔案被 Microsoft Defender for Office 365 識別為惡意檔時，檔案也會存在於隔離區中。</span><span class="sxs-lookup"><span data-stu-id="9733e-127">As of May 2018, when a file is identified as malicious by Microsoft Defender for Office 365, the file is also available in quarantine.</span></span> <span data-ttu-id="9733e-128">如需詳細資訊，請參閱 [使用安全性 & 合規性中心管理隔離](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)的檔案。</span><span class="sxs-lookup"><span data-stu-id="9733e-128">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="9733e-129">請記住下列重點</span><span class="sxs-lookup"><span data-stu-id="9733e-129">Keep these points in mind</span></span>

- <span data-ttu-id="9733e-130">Office 365 的 Defender 不會掃描 SharePoint Online、商務 OneDrive 或 Microsoft 團隊中的每一個檔案。</span><span class="sxs-lookup"><span data-stu-id="9733e-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="9733e-131">這是原本設計的做法。</span><span class="sxs-lookup"><span data-stu-id="9733e-131">This is by design.</span></span> <span data-ttu-id="9733e-132">檔會以非同步方式掃描。</span><span class="sxs-lookup"><span data-stu-id="9733e-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="9733e-133">此程式會使用共用和來賓活動事件，以及智慧試探法和威脅信號，識別惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="9733e-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="9733e-134">請確認您的 SharePoint 網站已設定為使用[新式體驗](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)。</span><span class="sxs-lookup"><span data-stu-id="9733e-134">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="9733e-135">Office 365 的 Defender 防護會套用是否使用新式經驗或傳統模式;不過，只有在新式的體驗中，才可使用已封鎖檔案的視覺指示器。</span><span class="sxs-lookup"><span data-stu-id="9733e-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="9733e-136">SharePoint、OneDrive 和 Microsoft 團隊的安全附件是組織整體威脅防護策略的一部分，其中包括 Exchange Online Protection (EOP) 中的反垃圾郵件和反惡意程式碼保護，以及 Microsoft Defender for Office 365 中的安全連結和安全附件。</span><span class="sxs-lookup"><span data-stu-id="9733e-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="9733e-137">若要深入了解，請參閱[防範 Office 365 中的威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="9733e-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
