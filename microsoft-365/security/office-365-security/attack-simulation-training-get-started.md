---
title: 開始使用攻擊模擬訓練
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解如何使用攻擊模擬訓練，在其 Microsoft 365 E5 或 Microsoft Defender 中對 Office 365 計畫2組織執行模擬網路釣魚和密碼攻擊。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1fa10d0d29b76d1631dd349d255b6c386557b5b8
ms.sourcegitcommit: 2266c2da090bc9a6dc1e01dea07f26901d20d57b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53222667"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="90bbd-103">開始使用攻擊模擬訓練</span><span class="sxs-lookup"><span data-stu-id="90bbd-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="90bbd-104">**適用** 于 [Office 365 方案2的 Microsoft Defender](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="90bbd-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="90bbd-105">如果您的組織有 Microsoft 365 E5 或 Microsoft Defender 用於 Office 365 計畫2（包括[威脅調查和回應功能](office-365-ti.md)），您可以使用 Microsoft 365 Defender 入口網站中的攻擊模擬訓練，在您的組織中執行實際的攻擊案例。</span><span class="sxs-lookup"><span data-stu-id="90bbd-105">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft 365 Defender portal to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="90bbd-106">這些模擬的攻擊可協助您找出並找出有漏洞的使用者，而真實的攻擊會影響您的下一行。</span><span class="sxs-lookup"><span data-stu-id="90bbd-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="90bbd-107">若要深入瞭解，請閱讀本文。</span><span class="sxs-lookup"><span data-stu-id="90bbd-107">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="90bbd-108">攻擊模擬訓練會取代[Microsoft Defender 中 Office 365 的攻擊模擬器中](attack-simulator.md)所述的舊攻擊模擬器 v1 經驗。</span><span class="sxs-lookup"><span data-stu-id="90bbd-108">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="90bbd-109">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="90bbd-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="90bbd-110">若要開啟 Microsoft 365 Defender 入口網站，請前往 <https://security.microsoft.com>。</span><span class="sxs-lookup"><span data-stu-id="90bbd-110">To open the Microsoft 365 Defender portal, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="90bbd-111">攻擊模擬訓練可在 **電子郵件和協同** 作業的 \> **攻擊模擬訓練** 中取得。</span><span class="sxs-lookup"><span data-stu-id="90bbd-111">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="90bbd-112">若要直接進入攻擊模擬訓練，請開啟 <https://security.microsoft.com/attacksimulator> 。</span><span class="sxs-lookup"><span data-stu-id="90bbd-112">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="90bbd-113">如需不同 Microsoft 365 訂閱中的攻擊模擬訓練可用性的相關資訊，請參閱[Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="90bbd-113">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="90bbd-114">您必須在 Microsoft 365 Defender 入口網站或 Azure Active Directory 中指派許可權，才能執行本文中的程式。</span><span class="sxs-lookup"><span data-stu-id="90bbd-114">You need to be assigned permissions in the Microsoft 365 Defender portal or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="90bbd-115">具體說來，您必須是 **組織管理**、 **安全性管理員** 或下列其中一個角色的成員：</span><span class="sxs-lookup"><span data-stu-id="90bbd-115">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="90bbd-116">**攻擊模擬器管理員**：建立及管理攻擊類比活動的所有層面。</span><span class="sxs-lookup"><span data-stu-id="90bbd-116">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="90bbd-117">**攻擊模擬器的「負載作者**」：建立系統管理員可以稍後再啟動的攻擊負載。</span><span class="sxs-lookup"><span data-stu-id="90bbd-117">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="90bbd-118">如需詳細資訊，請參閱 Microsoft 365 Defender 入口網站或系統[管理員角色](../../admin/add-users/about-admin-roles.md)[中的許可權](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="90bbd-118">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="90bbd-119">攻擊模擬訓練沒有對應的 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="90bbd-119">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="90bbd-120">攻擊類比和訓練相關資料會與其他客戶資料一起儲存，以供 Microsoft 365 服務使用。</span><span class="sxs-lookup"><span data-stu-id="90bbd-120">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="90bbd-121">如需詳細資訊，請參閱[Microsoft 365 資料位置](../../enterprise/o365-data-locations.md)。</span><span class="sxs-lookup"><span data-stu-id="90bbd-121">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="90bbd-122">可在下列地區取得攻擊模擬： <、APC、EUR、IND、CAN、澳大利亞、FRA、GBR、JPN、KOR、BRA、LAM 及 CHE。</span><span class="sxs-lookup"><span data-stu-id="90bbd-122">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, KOR, BRA, LAM and CHE.</span></span>

- <span data-ttu-id="90bbd-123">在 15 2021 年6月為止，GCC 中提供攻擊模擬訓練。</span><span class="sxs-lookup"><span data-stu-id="90bbd-123">As of June 15 2021, Attack simulation training is available in GCC.</span></span> <span data-ttu-id="90bbd-124">如果您的組織已 Office 365 G5 GCC 或 Microsoft Defender for Office 365 (Plan 2) ，您可以使用 Microsoft 365 Defender 入口網站中的攻擊模擬訓練訓練，在組織中執行實際的攻擊案例，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="90bbd-124">If your organization has Office 365 G5 GCC or Microsoft Defender for Office 365 (Plan 2) for Government, you can use Attack simulation training in the Microsoft 365 Defender portal to run realistic attack scenarios in your organization as described in this article.</span></span> <span data-ttu-id="90bbd-125">GCC 高或 DoD 環境中尚未提供攻擊模擬訓練。</span><span class="sxs-lookup"><span data-stu-id="90bbd-125">Attack simulation training is not yet available in GCC High or DoD environments.</span></span>

> [!NOTE]
> <span data-ttu-id="90bbd-126">攻擊模擬訓練為 E3 客戶提供一項功能的子集，以作為試用版。</span><span class="sxs-lookup"><span data-stu-id="90bbd-126">Attack simulation training offers a subset of capabilities to E3 customers as a trial.</span></span> <span data-ttu-id="90bbd-127">試用版產品包含使用認證收集負載的功能，以及可選取「ISA 網路釣魚」或「大量市場網路釣魚」訓練經驗的功能。</span><span class="sxs-lookup"><span data-stu-id="90bbd-127">The trial offering contains the ability to use a Credential Harvest payload and the ability to select 'ISA Phishing' or 'Mass Market Phishing' training experiences.</span></span> <span data-ttu-id="90bbd-128">其他功能都不是 E3 試用版產品的一部分。</span><span class="sxs-lookup"><span data-stu-id="90bbd-128">No other capabilities are part of the E3 trial offering.</span></span>

## <a name="simulations"></a><span data-ttu-id="90bbd-129">類比</span><span class="sxs-lookup"><span data-stu-id="90bbd-129">Simulations</span></span>

<span data-ttu-id="90bbd-130">*網路釣魚* 是一種常見的電子郵件攻擊術語，可嘗試竊取看似來自合法或信任寄件者的郵件中的機密資訊。</span><span class="sxs-lookup"><span data-stu-id="90bbd-130">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="90bbd-131">*網路釣魚* 是指我們歸類為 _社交工程_ 的技術子集的一部分。</span><span class="sxs-lookup"><span data-stu-id="90bbd-131">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="90bbd-132">在攻擊模擬訓練中，有多種類型的社交工程技術可供使用：</span><span class="sxs-lookup"><span data-stu-id="90bbd-132">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="90bbd-133">**認證收集**：攻擊者會傳送包含 URL 的郵件給收件者。</span><span class="sxs-lookup"><span data-stu-id="90bbd-133">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="90bbd-134">當收件者按一下 URL 時，會進入網站，其中通常會顯示對話方塊，詢問使用者輸入使用者的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="90bbd-134">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="90bbd-135">通常，目的頁面會有主題代表已知的網站，以便在使用者中建立信任。</span><span class="sxs-lookup"><span data-stu-id="90bbd-135">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="90bbd-136">**惡意程式碼附件**：攻擊者會傳送包含附件的郵件給收件者。</span><span class="sxs-lookup"><span data-stu-id="90bbd-136">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="90bbd-137">當收件者開啟附件時，會 (任何程式碼，例如，在使用者的裝置上執行宏) ，以協助攻擊者安裝其他程式碼或進一步 entrench 自己。</span><span class="sxs-lookup"><span data-stu-id="90bbd-137">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="90bbd-138">**附件中的連結**：這是認證搜集的混合。</span><span class="sxs-lookup"><span data-stu-id="90bbd-138">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="90bbd-139">攻擊者會傳送包含附件內之 URL 的郵件給收件者。</span><span class="sxs-lookup"><span data-stu-id="90bbd-139">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="90bbd-140">當收件者開啟附件並按一下 URL 時，他們會進入網站，其中通常會顯示對話方塊，詢問使用者輸入使用者的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="90bbd-140">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="90bbd-141">通常，目的頁面會有主題代表已知的網站，以便在使用者中建立信任。</span><span class="sxs-lookup"><span data-stu-id="90bbd-141">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="90bbd-142">**惡意程式碼連結**：攻擊者會傳送收件者一封郵件，其中包含已知檔案共用 (網站上附件的連結，例如，SharePoint 線上或 Dropbox) 。</span><span class="sxs-lookup"><span data-stu-id="90bbd-142">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="90bbd-143">當收件者按一下 URL 時，附件隨即開啟，並隨意執行程式碼 (例如，在使用者的裝置上執行宏) ，以協助攻擊者安裝其他程式碼或進行進一步的 entrench。</span><span class="sxs-lookup"><span data-stu-id="90bbd-143">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="90bbd-144">**磁片磁碟機-依 url**：攻擊者會傳送包含 url 的郵件給收件者。</span><span class="sxs-lookup"><span data-stu-id="90bbd-144">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="90bbd-145">當收件者按一下 URL 時，會進入嘗試執行背景代碼的網站。</span><span class="sxs-lookup"><span data-stu-id="90bbd-145">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="90bbd-146">此背景程式碼會嘗試收集收件者的相關資訊，或在其裝置上部署任意程式碼。</span><span class="sxs-lookup"><span data-stu-id="90bbd-146">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="90bbd-147">通常，目的地網站是眾所周知的網站，已遭到損害或眾所周知的網站複本。</span><span class="sxs-lookup"><span data-stu-id="90bbd-147">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="90bbd-148">熟悉此網站可協助說服使用者可安全地按一下連結。</span><span class="sxs-lookup"><span data-stu-id="90bbd-148">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="90bbd-149">此技術也稱為「 _watering 洞」攻擊_。</span><span class="sxs-lookup"><span data-stu-id="90bbd-149">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="90bbd-150">在網路釣魚活動中使用 URL 之前，請先檢查支援的網頁瀏覽器中模擬之網路釣魚 URL 的可用性。</span><span class="sxs-lookup"><span data-stu-id="90bbd-150">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="90bbd-151">雖然我們與許多 URL 信譽廠商合作，以無條件允許這些類比 URLs，但我們並不一定 (如 Google 保管庫流覽) 等完整覆蓋。</span><span class="sxs-lookup"><span data-stu-id="90bbd-151">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="90bbd-152">大部分廠商都會提供指引，讓您無條件允許特定 URLs (例如， <https://support.google.com/chrome/a/answer/7532419>) 。</span><span class="sxs-lookup"><span data-stu-id="90bbd-152">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="90bbd-153">下列清單說明攻擊模擬訓練所用的 URLs：</span><span class="sxs-lookup"><span data-stu-id="90bbd-153">The URLs that are used by Attack simulation training are described in the following list:</span></span>

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a><span data-ttu-id="90bbd-154">建立模擬</span><span class="sxs-lookup"><span data-stu-id="90bbd-154">Create a simulation</span></span>

<span data-ttu-id="90bbd-155">如需如何建立及傳送新模擬的逐步指示，請參閱 [模擬網路釣魚攻擊](attack-simulation-training.md)。</span><span class="sxs-lookup"><span data-stu-id="90bbd-155">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="90bbd-156">建立有效載荷</span><span class="sxs-lookup"><span data-stu-id="90bbd-156">Create a payload</span></span>

<span data-ttu-id="90bbd-157">如需如何建立用於類比的負載的逐步指示，請參閱 [建立攻擊模擬訓練的自訂負載](attack-simulation-training-payloads.md)。</span><span class="sxs-lookup"><span data-stu-id="90bbd-157">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="90bbd-158">取得洞察力</span><span class="sxs-lookup"><span data-stu-id="90bbd-158">Gaining insights</span></span>

<span data-ttu-id="90bbd-159">如需如何透過報告取得深入瞭解的逐步指示，請參閱 [透過攻擊模擬訓練取得深入](attack-simulation-training-insights.md)瞭解。</span><span class="sxs-lookup"><span data-stu-id="90bbd-159">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="90bbd-160">攻擊模擬程式使用保管庫 Office 365 的 Defender 中的連結，以安全地追蹤傳送至網路釣魚活動收件者的負載郵件中之 URL 的資料，即使保管庫連結原則中的 [**不要追蹤使用者點擊**] 設定也是一樣。</span><span class="sxs-lookup"><span data-stu-id="90bbd-160">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>
