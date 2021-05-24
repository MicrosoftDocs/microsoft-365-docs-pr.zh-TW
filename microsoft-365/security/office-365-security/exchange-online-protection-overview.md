---
title: Exchange Online Protection (EOP) 一覽表
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解 Exchange Online Protection (EOP) 可協助保護您的內部部署電子郵件組織，以進行獨立和混合式環境。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce90f1429e2c54f413ae54172a6d2f663ef6a358
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624717"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="38812-103">Exchange Online Protection 概觀</span><span class="sxs-lookup"><span data-stu-id="38812-103">Exchange Online Protection overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="38812-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="38812-104">**Applies to**</span></span>
- [<span data-ttu-id="38812-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="38812-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="38812-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="38812-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="38812-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38812-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="38812-108">Exchange Online Protection (EOP) 是雲端架構篩選服務，可協助您的組織抵禦垃圾郵件、惡意程式碼和其他電子郵件威脅。</span><span class="sxs-lookup"><span data-stu-id="38812-108">Exchange Online Protection (EOP) is the cloud-based filtering service that helps protect your organization against spam, malware, and other email threats.</span></span> <span data-ttu-id="38812-109">EOP 包含 Exchange Online 信箱的所有 Microsoft 365 組織。</span><span class="sxs-lookup"><span data-stu-id="38812-109">EOP is included in all Microsoft 365 organizations with Exchange Online mailboxes.</span></span>

<span data-ttu-id="38812-110">本文的其餘部分將說明 EOP 的運作方式。</span><span class="sxs-lookup"><span data-stu-id="38812-110">The rest of this article explains how EOP works.</span></span>

> [!NOTE]
> <span data-ttu-id="38812-111">您也可以自行提供 EOP，以保護內部部署信箱和混合式環境，以保護內部部署 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="38812-111">EOP is also available by itself to protect on-premises mailboxes and in hybrid environments to protect on-premises Exchange mailboxes.</span></span> <span data-ttu-id="38812-112">如需詳細資訊，請參閱[獨立 Exchange Online Protection](/exchange/standalone-eop/standaonline-eop)。</span><span class="sxs-lookup"><span data-stu-id="38812-112">For more information, see [Standalone Exchange Online Protection](/exchange/standalone-eop/standaonline-eop).</span></span>

## <a name="how-eop-works"></a><span data-ttu-id="38812-113">EOP 的運作方式</span><span class="sxs-lookup"><span data-stu-id="38812-113">How EOP works</span></span>

<span data-ttu-id="38812-114">若要了解 EOP 的運作方式，查看它如何處理傳入電子郵件很有幫助：</span><span class="sxs-lookup"><span data-stu-id="38812-114">To understand how EOP works, it helps to see how it processes incoming email:</span></span>

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="來自網際網路的電子郵件的圖形，或從客戶對 EOP 及透過連線、反惡意程式碼、郵件流程規則---原則篩選和內容篩選的電子郵件，在垃圾郵件或隔離或使用者郵件傳遞的最後一開始之前。":::

- <span data-ttu-id="38812-116">當傳入郵件進入 EOP 時，它最初會透過連線篩選來檢查寄件者的信譽。</span><span class="sxs-lookup"><span data-stu-id="38812-116">When an incoming message enters EOP, it initially passes through connection filtering, which checks the sender's reputation.</span></span> <span data-ttu-id="38812-117">大部分的垃圾郵件會在此點停止，並由 EOP 拒絕。</span><span class="sxs-lookup"><span data-stu-id="38812-117">The majority of spam is stopped at this point and rejected by EOP.</span></span> <span data-ttu-id="38812-118">如需詳細資訊，請參閱[設定連線篩選](configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="38812-118">For more information, see [Configure connection filtering](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="38812-119">然後檢查郵件是否有惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="38812-119">Then the message is inspected for malware.</span></span> <span data-ttu-id="38812-120">如果在郵件中找到惡意程式碼或附件 (s) 郵件會路由傳送至僅限系統管理員的隔離存放區。</span><span class="sxs-lookup"><span data-stu-id="38812-120">If malware is found in the message or the attachment(s) the message is routed to an admin only quarantine store.</span></span> <span data-ttu-id="38812-121">若要深入瞭解惡意程式碼保護，請參閱 [EOP 中的反惡意程式碼保護](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="38812-121">To learn more about malware protection, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

- <span data-ttu-id="38812-122">郵件會繼續透過原則篩選，其評估來源為自訂郵件流程規則 (也稱為從範本建立或強制執行的傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="38812-122">Messages continue through policy filtering, where they are evaluated against custom mail flow rules (also known as transport rules) that you create or enforce from a template.</span></span> <span data-ttu-id="38812-123">例如，您可能有一個規則，會在特定寄件者的郵件送達時，傳送通知給管理員。</span><span class="sxs-lookup"><span data-stu-id="38812-123">For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender.</span></span> <span data-ttu-id="38812-124">資料遺失防護 (DLP) 檢查也會在這一點 (Exchange Enterprise CAL 搭配服務) 。</span><span class="sxs-lookup"><span data-stu-id="38812-124">Data loss prevention (DLP) checks also happen at this point (Exchange Enterprise CAL with Services).</span></span>

- <span data-ttu-id="38812-125">接下來，郵件會經由反垃圾郵件篩選，其中郵件會檢查垃圾郵件、網路釣魚或大量電子郵件。</span><span class="sxs-lookup"><span data-stu-id="38812-125">Next, the message passes through anti-spam filtering where the message is check for spam, phishing, or bulk email.</span></span> <span data-ttu-id="38812-126">偵測到的郵件可傳送至隔離區，或是使用者的垃圾郵件資料夾，以及其他選項。</span><span class="sxs-lookup"><span data-stu-id="38812-126">Detected messages can be sent to quarantine, or a user's Junk Email folder, among other options.</span></span> <span data-ttu-id="38812-127">如需詳細資訊，請參閱 [設定反垃圾郵件原則](configure-your-spam-filter-policies.md) 及 [設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="38812-127">For more information see [Configure anti-spam policies](configure-your-spam-filter-policies.md) and [Configure anti-phishing policies](configure-anti-phishing-policies-eop.md).</span></span>

<span data-ttu-id="38812-128">所有傳遞這些保護層的郵件都會順利傳送給收件者。</span><span class="sxs-lookup"><span data-stu-id="38812-128">Any message that passes all of these protection layers successfully is delivered to the recipient.</span></span>

<span data-ttu-id="38812-129">如需詳細資訊，請參閱 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="38812-129">For more information, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a><span data-ttu-id="38812-130">EOP 內部部署電子郵件組織的計畫及功能</span><span class="sxs-lookup"><span data-stu-id="38812-130">EOP plans and features for on-premises email organizations</span></span>

<span data-ttu-id="38812-131">以下是可用的 EOP 訂閱方案：</span><span class="sxs-lookup"><span data-stu-id="38812-131">The available EOP subscription plans are:</span></span>

- <span data-ttu-id="38812-132">**獨立 EOP**：您可以註冊 EOP 以保護內部部署的電子郵件組織。</span><span class="sxs-lookup"><span data-stu-id="38812-132">**EOP standalone**: You enroll in EOP to protect your on-premises email organization.</span></span>

- <span data-ttu-id="38812-133">**Exchange Online 中的 EOP 功能**：任何包括 Exchange Online (獨立的訂閱，或是 Microsoft 365) 的一部分，都使用 EOP 來保護您的 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="38812-133">**EOP features in Exchange Online**: Any subscription that includes Exchange Online (standalone or as part of Microsoft 365) uses EOP to protect your Exchange Online mailboxes.</span></span>

- <span data-ttu-id="38812-134">**Exchange Enterprise CAL (含服務)**：如果您有內部部署的 Exchange 組織，且您已購買額外的 Exchange Enterprise CAL (含服務) 授權，EOP 會包含在服務中。</span><span class="sxs-lookup"><span data-stu-id="38812-134">**Exchange Enterprise CAL with Services**: If you have an on-premises Exchange organization where you've purchased additional Exchange Enterprise CAL with Services licenses, EOP is part of the included services.</span></span>

<span data-ttu-id="38812-135">如需所有 EOP 訂閱方案之需求、重要限制和功能可用性的相關資訊，請參閱 [Exchange Online Protection 服務描述](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="38812-135">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection service description](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="38812-136">如果您有包含 Exchange Online 信箱的 Microsoft 365 或 Office 365 訂閱，則您有 EOP。</span><span class="sxs-lookup"><span data-stu-id="38812-136">If you have a Microsoft 365 or Office 365 subscription that includes Exchange Online mailboxes, you have EOP.</span></span> <span data-ttu-id="38812-137">如需在您的訂閱中設定 EOP 安全性功能的步驟，以及新增的安全性 Microsoft Defender for Office 365 訂閱中的資訊，可為您提供，請參閱[防禦威脅](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="38812-137">For steps to set up EOP security features in your subscription, and information on the added security a Microsoft Defender for Office 365 subscription can give you, see [protect against threats](protect-against-threats.md).</span></span> <span data-ttu-id="38812-138">建議您在[EOP 和 Microsoft Defender Office 365 的安全性設定](recommended-settings-for-eop-and-office365.md)中，找到設定的 EOP 功能設定。</span><span class="sxs-lookup"><span data-stu-id="38812-138">The recommended settings for EOP feature for setup can be found in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="setting-up-eop-for-on-premises-email-organizations"></a><span data-ttu-id="38812-139">設定內部部署電子郵件組織的 EOP</span><span class="sxs-lookup"><span data-stu-id="38812-139">Setting up EOP for on-premises email organizations</span></span>

<span data-ttu-id="38812-p108">設定 EOP 可以很簡單，對於具有一些符合性規則的小型組織來說，更是如此。不過，如果您的組織是具有多個網域、自訂符合性規則或混合郵件流程的大型組織，則在進行設定時可能需要更加詳盡的規劃及更多的時間。</span><span class="sxs-lookup"><span data-stu-id="38812-p108">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>

<span data-ttu-id="38812-142">如果已購買 EOP，請參閱[設定 EOP 服務](/exchange/standalone-eop/set-up-your-eop-service)，以確保完成所有必要的 EOP 設定步驟，來保護郵件環境。</span><span class="sxs-lookup"><span data-stu-id="38812-142">If you've already purchased EOP, see [Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span>

### <a name="eop-datacenters"></a><span data-ttu-id="38812-143">EOP 資料中心</span><span class="sxs-lookup"><span data-stu-id="38812-143">EOP datacenters</span></span>

<span data-ttu-id="38812-144">EOP 會在用於提供最佳可用性的全球資料中心網路上執行。</span><span class="sxs-lookup"><span data-stu-id="38812-144">EOP runs on a worldwide network of datacenters that are designed to provide the best availability.</span></span> <span data-ttu-id="38812-145">例如，如果資料中心變成無法使用，則會將電子郵件自動路由傳送至其他資料中心，而不會中斷服務。</span><span class="sxs-lookup"><span data-stu-id="38812-145">For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service.</span></span> <span data-ttu-id="38812-146">每個資料中心的伺服器都會以您的名義接收郵件，提供組織和網際網路之間的分隔區，從而減少伺服器的負載。</span><span class="sxs-lookup"><span data-stu-id="38812-146">Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the internet, thereby reducing load on your servers.</span></span> <span data-ttu-id="38812-147">透過這個高可用性的網路，Microsoft 可以確保電子郵件及時送達您的組織。</span><span class="sxs-lookup"><span data-stu-id="38812-147">Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span>

<span data-ttu-id="38812-p110">EOP 會在資料中心之間執行負載平衡，但只在一個區域內。如果您佈建在一個區域中，則會以該區域的郵件路由來處理您的所有郵件。下列清單顯示 EOP 資料中心的地區郵件路由運作方式：</span><span class="sxs-lookup"><span data-stu-id="38812-p110">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>

- <span data-ttu-id="38812-151">在歐洲、中東和非洲 (EMEA)，所有 Exchange Online 信箱都位於 EMEA 資料中心，且所有郵件都透過 EMEA 資料中心傳送供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="38812-151">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>
- <span data-ttu-id="38812-152">在亞太地區 (APAC)，所有 Exchange Online 信箱都位於 APAC 資料中心，且郵件目前透過 APAC 資料中心傳送供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="38812-152">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>
- <span data-ttu-id="38812-153">在美洲，服務會發佈于下列位置：</span><span class="sxs-lookup"><span data-stu-id="38812-153">In the Americas, services are distributed in the following locations:</span></span>
  - <span data-ttu-id="38812-154">南美洲： Exchange Online 信箱位於巴西和智利的資料中心內。</span><span class="sxs-lookup"><span data-stu-id="38812-154">South America: Exchange Online mailboxes are located in datacenters in Brazil and Chile.</span></span> <span data-ttu-id="38812-155">所有郵件都會透過本機資料中心進行路由傳送，以供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="38812-155">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="38812-156">隔離的郵件會儲存在租使用者所在的資料中心。</span><span class="sxs-lookup"><span data-stu-id="38812-156">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>
  - <span data-ttu-id="38812-157">加拿大： Exchange Online 信箱位於加拿大的資料中心內。</span><span class="sxs-lookup"><span data-stu-id="38812-157">Canada: Exchange Online mailboxes are located in datacenters in Canada.</span></span> <span data-ttu-id="38812-158">所有郵件都會透過本機資料中心進行路由傳送，以供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="38812-158">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="38812-159">隔離的郵件會儲存在租使用者所在的資料中心。</span><span class="sxs-lookup"><span data-stu-id="38812-159">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>
  - <span data-ttu-id="38812-160">美國： Exchange Online 信箱位於美國資料中心。</span><span class="sxs-lookup"><span data-stu-id="38812-160">United States: Exchange Online mailboxes are located in U.S. datacenters.</span></span> <span data-ttu-id="38812-161">所有郵件都會透過本機資料中心進行路由傳送，以供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="38812-161">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="38812-162">隔離的郵件會儲存在租使用者所在的資料中心。</span><span class="sxs-lookup"><span data-stu-id="38812-162">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>
- <span data-ttu-id="38812-163">至於政府社群雲端 (GCC)，所有 Exchange Online 信箱都位於美國資料中心，且所有郵件都透過美國資料中心傳送供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="38812-163">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>

## <a name="eop-help-for-admins"></a><span data-ttu-id="38812-164">EOP 系統管理員的協助</span><span class="sxs-lookup"><span data-stu-id="38812-164">EOP Help for admins</span></span>

<span data-ttu-id="38812-165">適用於 EOP 系統管理員的幫助內容由下列頂層類別組成：</span><span class="sxs-lookup"><span data-stu-id="38812-165">The Help content for EOP administrators consists of the following top-level categories:</span></span>

- <span data-ttu-id="38812-166">為[Office 365 系統管理員設定 EOP，Day 1，為 microsoft defender 設定](protect-against-threats.md)EOP 保護和偵測工具，以供 Office 365 的 microsoft defender 核心。</span><span class="sxs-lookup"><span data-stu-id="38812-166">[Configure EOP, Day 1, for Microsoft Defender for Office 365 admins](protect-against-threats.md): Configuring EOP protection and detection tools at the core of Microsoft Defender for Office 365.</span></span>

- <span data-ttu-id="38812-167">[EOP 功能](eop-features.md)：提供一份 EOP 中可用的功能清單。</span><span class="sxs-lookup"><span data-stu-id="38812-167">[EOP features](eop-features.md): Provides a list of features that are available in EOP.</span></span>

- <span data-ttu-id="38812-168">[設定 EOP 服務](/exchange/standalone-eop/set-up-your-eop-service)：提供 EOP 服務的設定步驟，以及其他資訊的連結。</span><span class="sxs-lookup"><span data-stu-id="38812-168">[Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service): Provides steps for setting up your EOP service, and links to additional information.</span></span>

- <span data-ttu-id="38812-169">[從 Google Postini、Barracuda Spam and Virus Firewall 或 Cisco IronPort 切換到 EOP](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)：說明從其他電子郵件保護產品切換到 EOP 的程序。</span><span class="sxs-lookup"><span data-stu-id="38812-169">[Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Describes the process for switching to EOP from another email protection product.</span></span>

- <span data-ttu-id="38812-170">[管理獨立 EOP 中的](/exchange/standalone-eop/manage-recipients-in-eop)收件者：說明如何管理獨立 EOP 中的郵件使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="38812-170">[Manage recipients in standalone EOP](/exchange/standalone-eop/manage-recipients-in-eop): Describes how to manage mail users and groups in standalone EOP.</span></span>

- <span data-ttu-id="38812-171">[EOP 中的郵件流程](mail-flow-in-eop.md)：說明如何使用連接器來設定自訂郵件流程案例、如何管理與服務相關的網域，以及如何啟用目錄架構邊緣封鎖 (DBEB) 功能。</span><span class="sxs-lookup"><span data-stu-id="38812-171">[Mail flow in EOP](mail-flow-in-eop.md): Describes how to configure custom mail flow scenarios using connectors, how to manage domains associated with the service, and how to enable the Directory Based Edge Blocking (DBEB) feature.</span></span>

- <span data-ttu-id="38812-172">[EOP 和 Microsoft Defender for Office 365 security 的建議設定](recommended-settings-for-eop-and-office365.md)：說明在您設定和布建服務之後的建議配置設定和考慮。</span><span class="sxs-lookup"><span data-stu-id="38812-172">[Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md): Describes recommended configuration settings and considerations for after you set up and provision your service.</span></span>

- <span data-ttu-id="38812-173">[在 Exchange Online 中審核報告](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)：說明如何使用審核報告追蹤服務的設定變更。</span><span class="sxs-lookup"><span data-stu-id="38812-173">[Auditing reports in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports): Describes how to use auditing reports to track configuration changes to the service.</span></span>

- <span data-ttu-id="38812-174">[EOP 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)：說明垃圾郵件篩選和惡意程式碼篩選，並示範如何自訂以符合組織的需求。</span><span class="sxs-lookup"><span data-stu-id="38812-174">[Anti-spam and anti-malware protection in EOP](anti-spam-and-anti-malware-protection.md): Describes spam filtering and malware filtering and shows how to customize them to best meet the needs of your organization.</span></span> <span data-ttu-id="38812-175">此外，還說明系統管理員和使用者可以對隔離郵件執行的工作。</span><span class="sxs-lookup"><span data-stu-id="38812-175">Also describes tasks that administrators and end users can perform on quarantined messages.</span></span>

- <span data-ttu-id="38812-176">[Exchange Online Protection 的報告與訊息追蹤](reporting-and-message-trace-in-exchange-online-protection.md)：說明可用的報告和疑難排解工具。</span><span class="sxs-lookup"><span data-stu-id="38812-176">[Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Describes the reports and troubleshooting tools that are available.</span></span>

- <span data-ttu-id="38812-177">[Exchange admin center in Exchange Online](/exchange/exchange-admin-center)或[Exchange 系統管理中心在獨立 EOP 中](/exchange/standalone-eop/exchange-admin-center-eop)：說明如何存取及流覽 Exchange 系統管理中心 (EAC) 管理介面，以便管理相關的 EOP 功能。</span><span class="sxs-lookup"><span data-stu-id="38812-177">[Exchange admin center in Exchange Online](/exchange/exchange-admin-center) or [Exchange admin center in standalone EOP](/exchange/standalone-eop/exchange-admin-center-eop): Describes how to access and navigate through the Exchange admin center (EAC) management interface in order to manage related EOP features.</span></span>

- <span data-ttu-id="38812-178">[Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell)：提供遠端 PowerShell 的相關資訊，讓您可以從命令列管理 EOP 服務。</span><span class="sxs-lookup"><span data-stu-id="38812-178">[Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell): Provides information about remote PowerShell, which lets you manage your EOP service from the command line.</span></span>

- <span data-ttu-id="38812-179">[EOP 幫助和支援](help-and-support-for-eop.md) 提供有關取得幫助和技術支援的資訊。</span><span class="sxs-lookup"><span data-stu-id="38812-179">[Help and support for EOP](help-and-support-for-eop.md) Provides information about obtaining help and technical support.</span></span>