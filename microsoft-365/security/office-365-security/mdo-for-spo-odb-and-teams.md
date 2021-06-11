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
description: 瞭解適用于 SharePoint Online、商務用 OneDrive 及 Microsoft Teams 中檔案的 Microsoft Defender Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a74a75f12a758b9b116a3f752624df38f338d0d1
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878217"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="6b22f-103">適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件</span><span class="sxs-lookup"><span data-stu-id="6b22f-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6b22f-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="6b22f-104">**Applies to**</span></span>
- [<span data-ttu-id="6b22f-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="6b22f-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6b22f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b22f-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6b22f-107">在[Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md)中 SharePoint、OneDrive 和 Microsoft Teams 的安全附件，針對[在 Microsoft 365 中常見的病毒偵測引擎](virus-detection-in-spo.md)，在上載時已掃描的檔案，提供其他層級的保護。</span><span class="sxs-lookup"><span data-stu-id="6b22f-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="6b22f-108">SharePoint、OneDrive 及 Microsoft Teams 的安全附件，可協助偵測並封鎖在小組網站和文件庫中識別為惡意的現有檔案。</span><span class="sxs-lookup"><span data-stu-id="6b22f-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="6b22f-109">預設不會啟用 SharePoint、OneDrive 及 Microsoft Teams 的安全附件。</span><span class="sxs-lookup"><span data-stu-id="6b22f-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="6b22f-110">若要將其開啟，請參閱[開啟安全附件以取得 SharePoint、OneDrive 及 Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="6b22f-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="6b22f-111">SharePoint、OneDrive 及 Microsoft Teams 的安全附件的運作方式</span><span class="sxs-lookup"><span data-stu-id="6b22f-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="6b22f-112">啟用 SharePoint、OneDrive 和 Microsoft Teams 的安全附件，並將檔案識別為惡意時，會使用與檔案存放區的直接整合，鎖定檔案。</span><span class="sxs-lookup"><span data-stu-id="6b22f-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="6b22f-113">下列影像顯示文件庫中偵測到的惡意檔案範例。</span><span class="sxs-lookup"><span data-stu-id="6b22f-113">The following image shows an example of a malicious file detected in a library.</span></span>

![商務用 OneDrive 中的檔案，偵測到其中一個是惡意檔案](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="6b22f-115">雖然封鎖的檔案仍然會列在文件庫和 web、行動裝置或桌面應用程式中，但無法開啟、複製、移動或共用檔案。</span><span class="sxs-lookup"><span data-stu-id="6b22f-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="6b22f-116">但可刪除封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="6b22f-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="6b22f-117">以下是在行動裝置上封鎖的檔案外觀的範例：</span><span class="sxs-lookup"><span data-stu-id="6b22f-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![透過 OneDrive 行動應用程式從商務用 OneDrive 中刪除封鎖的檔案](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="6b22f-119">根據預設，使用者可以下載封鎖的檔案。</span><span class="sxs-lookup"><span data-stu-id="6b22f-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="6b22f-120">以下是在行動裝置上下載封鎖的檔案的外觀：</span><span class="sxs-lookup"><span data-stu-id="6b22f-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![在商務用 OneDrive 中下載封鎖的檔案](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="6b22f-122">SharePoint線上系統管理員可以防止使用者下載惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="6b22f-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="6b22f-123">如需相關指示，請參閱[使用 SharePoint 線上 PowerShell 以避免使用者下載惡意](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)檔案。</span><span class="sxs-lookup"><span data-stu-id="6b22f-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="6b22f-124">若要深入了解當檔案被偵測為惡意檔案時的使用者體驗，請參閱[在 SharePoint Online、OneDrive 或 Microsoft Teams 中找到惡意檔案時該怎麼做](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。</span><span class="sxs-lookup"><span data-stu-id="6b22f-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="6b22f-125">查看 SharePoint、OneDrive 及 Microsoft Teams 的安全附件所偵測到之惡意檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6b22f-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="6b22f-126">SharePoint、OneDrive 及 Microsoft Teams 的安全附件所識別為惡意的檔案，會顯示[Microsoft Defender for Office 365](view-reports-for-mdo.md)及[Explorer (和即時偵測) ](threat-explorer.md)中的報告。</span><span class="sxs-lookup"><span data-stu-id="6b22f-126">Files that are identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams will show up in [reports for Microsoft Defender for Office 365](view-reports-for-mdo.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="6b22f-127">從2018年5月的 SharePoint、OneDrive 及 Microsoft Teams 的安全附件，將檔案識別為惡意檔時，也會在隔離區中使用該檔案。</span><span class="sxs-lookup"><span data-stu-id="6b22f-127">As of May 2018, when a file is identified as malicious by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, the file is also available in quarantine.</span></span> <span data-ttu-id="6b22f-128">如需詳細資訊，請參閱[使用 Microsoft 365 defender 入口網站管理 Office 365 的 defender 中的隔離](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)檔案。</span><span class="sxs-lookup"><span data-stu-id="6b22f-128">For more information, see [Use the Microsoft 365 Defender portal to manage quarantined files in Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="6b22f-129">請記住下列重點</span><span class="sxs-lookup"><span data-stu-id="6b22f-129">Keep these points in mind</span></span>

- <span data-ttu-id="6b22f-130">Office 365 的 Defender 不會掃描 SharePoint Online、商務用 OneDrive 或 Microsoft Teams 中的每一個檔案。</span><span class="sxs-lookup"><span data-stu-id="6b22f-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="6b22f-131">這是原本設計的做法。</span><span class="sxs-lookup"><span data-stu-id="6b22f-131">This is by design.</span></span> <span data-ttu-id="6b22f-132">檔會以非同步方式掃描。</span><span class="sxs-lookup"><span data-stu-id="6b22f-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="6b22f-133">此程式會使用共用和來賓活動事件，以及智慧試探法和威脅信號，識別惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="6b22f-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="6b22f-134">請確認您的 SharePoint 網站已設定為使用[新式體驗](/sharepoint/guide-to-sharepoint-modern-experience)。</span><span class="sxs-lookup"><span data-stu-id="6b22f-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="6b22f-135">Office 365 防護的 Defender 會套用是否使用新式經驗或傳統模式;不過，只有在新式的體驗中，才可使用已封鎖檔案的視覺指示器。</span><span class="sxs-lookup"><span data-stu-id="6b22f-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="6b22f-136">SharePoint、OneDrive 和 Microsoft Teams 的安全附件是組織整體威脅防護策略的一部分，其中包括 Exchange Online Protection (EOP) 中的反垃圾郵件和反惡意程式碼保護，以及 Office 365 的 Microsoft Defender 中的安全連結和安全附件。</span><span class="sxs-lookup"><span data-stu-id="6b22f-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="6b22f-137">若要深入了解，請參閱[防範 Office 365 中的威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="6b22f-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
