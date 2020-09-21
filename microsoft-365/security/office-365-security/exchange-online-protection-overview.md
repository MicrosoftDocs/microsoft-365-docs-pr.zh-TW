---
title: Exchange Online Protection (EOP) 概述
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解 Exchange Online Protection (EOP) 如何協助保護您的內部部署電子郵件組織，以進行獨立和混合式環境。
ms.openlocfilehash: b546b60e242d7f4f7fd4c4550bb61b94052ff4d1
ms.sourcegitcommit: eb905c5b4d7e71fc930a207357295b0160c4f065
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2020
ms.locfileid: "48137010"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="1b445-103">Exchange Online Protection 概觀</span><span class="sxs-lookup"><span data-stu-id="1b445-103">Exchange Online Protection overview</span></span>

<span data-ttu-id="1b445-104">Exchange Online Protection (EOP) 是雲端架構篩選服務，可協助您的組織抵禦垃圾郵件和惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="1b445-104">Exchange Online Protection (EOP) is the cloud-based filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="1b445-105">EOP 包含 Exchange Online 信箱的所有 Microsoft 365 組織。</span><span class="sxs-lookup"><span data-stu-id="1b445-105">EOP is included in all Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="1b445-106">不過，下列內部部署案例也提供 EOP：</span><span class="sxs-lookup"><span data-stu-id="1b445-106">However, EOP is also available in the following on-premises scenarios:</span></span>

- <span data-ttu-id="1b445-107">**在獨立案例中**：EOP 會為您的內部部署、Exchange 組織，或任何其他內部部署 SMTP 電子郵件解決方案，提供雲端式電子郵件保護。</span><span class="sxs-lookup"><span data-stu-id="1b445-107">**In a standalone scenario**: EOP provides cloud-based email protection for your on-premises Exchange organization or for any other on-premises SMTP email solution.</span></span>

- <span data-ttu-id="1b445-108">**在混合式部署中**：當您混合使用內部部署和雲端信箱時，可以設定 EOP 來保護您的電子郵件環境，並控制郵件路由傳送。</span><span class="sxs-lookup"><span data-stu-id="1b445-108">**In a hybrid deployment**: EOP can be configured to protect your email environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span>

<span data-ttu-id="1b445-109">在這些案例中，EOP 可以簡化電子郵件環境的管理，並減輕維護內部部署硬體和軟體帶來的許多負擔。</span><span class="sxs-lookup"><span data-stu-id="1b445-109">In these scenarios, EOP can simplify the management of your email environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>

<span data-ttu-id="1b445-110">本主題的其餘部分將說明 EOP 在獨立和混合環境中的運作方式。</span><span class="sxs-lookup"><span data-stu-id="1b445-110">The rest of this topic explains how EOP works in standalone and hybrid environments.</span></span>

## <a name="how-eop-works"></a><span data-ttu-id="1b445-111">EOP 的運作方式</span><span class="sxs-lookup"><span data-stu-id="1b445-111">How EOP works</span></span>

<span data-ttu-id="1b445-112">若要了解 EOP 的運作方式，查看它如何處理傳入電子郵件很有幫助：</span><span class="sxs-lookup"><span data-stu-id="1b445-112">To understand how EOP works, it helps to see how it processes incoming email:</span></span>

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="從網際網路或客戶意見傳送至 EOP 的電子郵件圖形，以及透過連線、反惡意程式碼、郵件流程規則-反惡意程式碼、規則-反惡意程式碼，以及內容篩選的電子郵件，在垃圾郵件或隔離區或使用者郵件傳遞的最後一個之前。":::

- <span data-ttu-id="1b445-114">當傳入郵件進入 EOP 時，它最初會透過連線篩選來檢查寄件者的信譽。</span><span class="sxs-lookup"><span data-stu-id="1b445-114">When an incoming message enters EOP, it initially passes through connection filtering, which checks the sender's reputation.</span></span> <span data-ttu-id="1b445-115">大部分的垃圾郵件會在此點停止，並由 EOP 拒絕。</span><span class="sxs-lookup"><span data-stu-id="1b445-115">The majority of spam is stopped at this point and rejected by EOP.</span></span> <span data-ttu-id="1b445-116">如需詳細資訊，請參閱[設定連線篩選](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-connection-filter-policy?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="1b445-116">For more information, see [Configure connection filtering](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-connection-filter-policy?view=o365-worldwide).</span></span>

- <span data-ttu-id="1b445-117">然後檢查郵件是否有惡意程式碼的跡象。</span><span class="sxs-lookup"><span data-stu-id="1b445-117">Then the message is inspected for signs of malware.</span></span> <span data-ttu-id="1b445-118">如果在郵件中找到惡意程式碼或附件 (s) 郵件會路由傳送至僅限系統管理員的隔離存放區。</span><span class="sxs-lookup"><span data-stu-id="1b445-118">If malware is found in the message or the attachment(s) the message is routed to an admin only quarantine store.</span></span> <span data-ttu-id="1b445-119">您可以在 [這裡](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide)深入瞭解如何設定反惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="1b445-119">You can learn more about configuring anti-malware [here](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span></span>

- <span data-ttu-id="1b445-120">郵件會繼續透過原則篩選，其評估來源為自訂郵件流程規則 (也稱為從範本建立或強制執行的傳輸規則) 。</span><span class="sxs-lookup"><span data-stu-id="1b445-120">Messages continue through policy filtering, where they are evaluated against custom mail flow rules (also known as transport rules) that you create or enforce from a template.</span></span> <span data-ttu-id="1b445-121">例如，您可能有一個規則，會在特定寄件者的郵件送達時，傳送通知給管理員。</span><span class="sxs-lookup"><span data-stu-id="1b445-121">For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender.</span></span> <span data-ttu-id="1b445-122">資料遺失防護 (DLP) 檢查也會在此 (Exchange Enterprise CAL with Services) 時發生。</span><span class="sxs-lookup"><span data-stu-id="1b445-122">Data loss prevention (DLP) checks also happen at this point (Exchange Enterprise CAL with Services).</span></span>

- <span data-ttu-id="1b445-123">接下來，郵件會透過內容篩選 (也稱為反垃圾郵件) 。</span><span class="sxs-lookup"><span data-stu-id="1b445-123">Next, the message passes through content filtering (also known as Anti-spam).</span></span> <span data-ttu-id="1b445-124">此篩選器決定是垃圾郵件 *或網路釣魚網路* 的訊息，可以傳送至隔離區，或是傳送至使用者的垃圾郵件資料夾，以及其他選項。</span><span class="sxs-lookup"><span data-stu-id="1b445-124">A message that this filter determines to be spam *or phish* can be sent to quarantine, or a user's Junk Email folder, among other options.</span></span> <span data-ttu-id="1b445-125">如需詳細資訊，請參閱 [設定反垃圾郵件原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide) 及 [設定反網路釣魚原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-phishing-policies-eop?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="1b445-125">For more information see [Configure anti-spam policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide) and [Configure anti-phishing policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-phishing-policies-eop?view=o365-worldwide).</span></span>

<span data-ttu-id="1b445-126">所有傳遞這些保護層的郵件都會順利傳送給收件者。</span><span class="sxs-lookup"><span data-stu-id="1b445-126">Any message that passes all of these protection layers successfully is delivered to the recipient.</span></span>

<span data-ttu-id="1b445-127">如需詳細資訊，請參閱 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="1b445-127">For more information, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a><span data-ttu-id="1b445-128">EOP 內部部署電子郵件組織的計畫及功能</span><span class="sxs-lookup"><span data-stu-id="1b445-128">EOP plans and features for on-premises email organizations</span></span>

<span data-ttu-id="1b445-129">以下是可用的 EOP 訂閱方案：</span><span class="sxs-lookup"><span data-stu-id="1b445-129">The available EOP subscription plans are:</span></span>

- <span data-ttu-id="1b445-130">**獨立 EOP**：您可以註冊 EOP 以保護內部部署的電子郵件組織。</span><span class="sxs-lookup"><span data-stu-id="1b445-130">**EOP standalone**: You enroll in EOP to protect your on-premises email organization.</span></span>

- <span data-ttu-id="1b445-131">**Exchange online 中的 EOP 功能**：包含 exchange online (獨立的任何訂閱，或 Microsoft 365 的一部分) 使用 EOP 來保護您的 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="1b445-131">**EOP features in Exchange Online**: Any subscription that includes Exchange Online (standalone or as part of Microsoft 365) uses EOP to protect your Exchange Online mailboxes.</span></span>

- <span data-ttu-id="1b445-132">\*\*Exchange Enterprise CAL (含服務) \*\*：如果您有內部部署的 Exchange 組織，且您已購買額外的 Exchange Enterprise CAL (含服務) 授權，EOP 會包含在服務中。</span><span class="sxs-lookup"><span data-stu-id="1b445-132">**Exchange Enterprise CAL with Services**: If you have an on-premises Exchange organization where you've purchased additional Exchange Enterprise CAL with Services licenses, EOP is part of the included services.</span></span>

<span data-ttu-id="1b445-133">如需所有 EOP 訂閱方案之需求、重要限制和功能可用性的相關資訊，請參閱 [Exchange Online Protection 服務描述](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="1b445-133">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection service description](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

## <a name="setting-up-eop-for-on-premises-email-organizations"></a><span data-ttu-id="1b445-134">設定內部部署電子郵件組織的 EOP</span><span class="sxs-lookup"><span data-stu-id="1b445-134">Setting up EOP for on-premises email organizations</span></span>

<span data-ttu-id="1b445-p106">設定 EOP 可以很簡單，對於具有一些符合性規則的小型組織來說，更是如此。不過，如果您的組織是具有多個網域、自訂符合性規則或混合郵件流程的大型組織，則在進行設定時可能需要更加詳盡的規劃及更多的時間。</span><span class="sxs-lookup"><span data-stu-id="1b445-p106">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>

<span data-ttu-id="1b445-137">如果已購買 EOP，請參閱[設定 EOP 服務](set-up-your-eop-service.md)，以確保完成所有必要的 EOP 設定步驟，來保護郵件環境。</span><span class="sxs-lookup"><span data-stu-id="1b445-137">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span>

### <a name="eop-datacenters"></a><span data-ttu-id="1b445-138">EOP 資料中心</span><span class="sxs-lookup"><span data-stu-id="1b445-138">EOP datacenters</span></span>

<span data-ttu-id="1b445-139">EOP 會在用於提供最佳可用性的全球資料中心網路上執行。</span><span class="sxs-lookup"><span data-stu-id="1b445-139">EOP runs on a worldwide network of datacenters that are designed to provide the best availability.</span></span> <span data-ttu-id="1b445-140">例如，如果資料中心變成無法使用，則會將電子郵件自動路由傳送至其他資料中心，而不會中斷服務。</span><span class="sxs-lookup"><span data-stu-id="1b445-140">For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service.</span></span> <span data-ttu-id="1b445-141">每個資料中心的伺服器都會以您的名義接收郵件，提供組織和網際網路之間的分隔區，從而減少伺服器的負載。</span><span class="sxs-lookup"><span data-stu-id="1b445-141">Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the internet, thereby reducing load on your servers.</span></span> <span data-ttu-id="1b445-142">透過這個高可用性的網路，Microsoft 可以確保電子郵件及時送達您的組織。</span><span class="sxs-lookup"><span data-stu-id="1b445-142">Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span>

<span data-ttu-id="1b445-p108">EOP 會在資料中心之間執行負載平衡，但只在一個區域內。如果您佈建在一個區域中，則會以該區域的郵件路由來處理您的所有郵件。下列清單顯示 EOP 資料中心的地區郵件路由運作方式：</span><span class="sxs-lookup"><span data-stu-id="1b445-p108">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>

- <span data-ttu-id="1b445-146">在歐洲、中東和非洲 (EMEA)，所有 Exchange Online 信箱都位於 EMEA 資料中心，且所有郵件都透過 EMEA 資料中心傳送供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="1b445-146">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>

- <span data-ttu-id="1b445-147">在亞太地區 (APAC)，所有 Exchange Online 信箱都位於 APAC 資料中心，且郵件目前透過 APAC 資料中心傳送供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="1b445-147">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>

- <span data-ttu-id="1b445-148">在美洲，服務會發佈于下列位置：</span><span class="sxs-lookup"><span data-stu-id="1b445-148">In the Americas, services are distributed in the following locations:</span></span>

  - <span data-ttu-id="1b445-149">南美洲： Exchange Online 信箱位於巴西和智利的資料中心。</span><span class="sxs-lookup"><span data-stu-id="1b445-149">South America: Exchange Online mailboxes are located in datacenters in Brazil and Chile.</span></span> <span data-ttu-id="1b445-150">所有郵件都會透過本機資料中心進行路由傳送，以供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="1b445-150">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="1b445-151">隔離的郵件會儲存在租使用者所在的資料中心。</span><span class="sxs-lookup"><span data-stu-id="1b445-151">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

  - <span data-ttu-id="1b445-152">加拿大： Exchange Online 信箱位於加拿大的資料中心內。</span><span class="sxs-lookup"><span data-stu-id="1b445-152">Canada: Exchange Online mailboxes are located in datacenters in Canada.</span></span> <span data-ttu-id="1b445-153">所有郵件都會透過本機資料中心進行路由傳送，以供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="1b445-153">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="1b445-154">隔離的郵件會儲存在租使用者所在的資料中心。</span><span class="sxs-lookup"><span data-stu-id="1b445-154">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

  - <span data-ttu-id="1b445-155">美國： Exchange Online 信箱位於美國資料中心。</span><span class="sxs-lookup"><span data-stu-id="1b445-155">United States: Exchange Online mailboxes are located in U.S. datacenters.</span></span> <span data-ttu-id="1b445-156">所有郵件都會透過本機資料中心進行路由傳送，以供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="1b445-156">All messages are routed through local datacenters for EOP filtering.</span></span> <span data-ttu-id="1b445-157">隔離的郵件會儲存在租使用者所在的資料中心。</span><span class="sxs-lookup"><span data-stu-id="1b445-157">Quarantined messages are stored in the datacenter where the tenant is located.</span></span>

- <span data-ttu-id="1b445-158">至於政府社群雲端 (GCC)，所有 Exchange Online 信箱都位於美國資料中心，且所有郵件都透過美國資料中心傳送供 EOP 篩選。</span><span class="sxs-lookup"><span data-stu-id="1b445-158">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>

## <a name="eop-help-for-admins"></a><span data-ttu-id="1b445-159">EOP 系統管理員的協助</span><span class="sxs-lookup"><span data-stu-id="1b445-159">EOP Help for admins</span></span>

<span data-ttu-id="1b445-160">適用於 EOP 系統管理員的幫助內容由下列頂層類別組成：</span><span class="sxs-lookup"><span data-stu-id="1b445-160">The Help content for EOP administrators consists of the following top-level categories:</span></span>

- <span data-ttu-id="1b445-161">[設定 EOP，Day 1，For office 365 ATP admins：設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide)Office 365 高級威脅防護核心的 EOP 保護和偵測工具。</span><span class="sxs-lookup"><span data-stu-id="1b445-161">[Configure EOP, Day 1, for Office 365 ATP admins](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide): Configuring EOP protection and detection tools at the core of Office 365 Advanced Threat Protection.</span></span>

- <span data-ttu-id="1b445-162">[EOP 功能](eop-features.md)：提供一份 EOP 中可用的功能清單。</span><span class="sxs-lookup"><span data-stu-id="1b445-162">[EOP features](eop-features.md): Provides a list of features that are available in EOP.</span></span>

- <span data-ttu-id="1b445-163">[設定 EOP 服務](set-up-your-eop-service.md)：提供 EOP 服務的設定步驟，以及其他資訊的連結。</span><span class="sxs-lookup"><span data-stu-id="1b445-163">[Set up your EOP service](set-up-your-eop-service.md): Provides steps for setting up your EOP service, and links to additional information.</span></span>

- <span data-ttu-id="1b445-164">[從 Google Postini、Barracuda Spam and Virus Firewall 或 Cisco IronPort 切換到 EOP](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)：說明從其他電子郵件保護產品切換到 EOP 的程序。</span><span class="sxs-lookup"><span data-stu-id="1b445-164">[Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Describes the process for switching to EOP from another email protection product.</span></span>

- <span data-ttu-id="1b445-165">[管理獨立 EOP 中的](manage-recipients-in-eop.md)收件者：說明如何管理 EOP 中的郵件使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="1b445-165">[Manage recipients in standalone EOP](manage-recipients-in-eop.md): Describes how to manage mail users and groups in EOP.</span></span>

- <span data-ttu-id="1b445-166">[EOP 中的郵件流程](mail-flow-in-eop.md)：說明如何使用連接器來設定自訂郵件流程案例、如何管理與服務相關的網域，以及如何啟用目錄架構邊緣封鎖 (DBEB) 功能。</span><span class="sxs-lookup"><span data-stu-id="1b445-166">[Mail flow in EOP](mail-flow-in-eop.md): Describes how to configure custom mail flow scenarios using connectors, how to manage domains associated with the service, and how to enable the Directory Based Edge Blocking (DBEB) feature.</span></span>

- <span data-ttu-id="1b445-167">[設定 EOP 的最佳作法](best-practices-for-configuring-eop.md)：說明在您設定和佈建服務之後的建議組態設定和考量。</span><span class="sxs-lookup"><span data-stu-id="1b445-167">[Best practices for configuring EOP](best-practices-for-configuring-eop.md): Describes recommended configuration settings and considerations for after you set up and provision your service.</span></span>

- <span data-ttu-id="1b445-168">[獨立 EOP 中的審計報告](auditing-reports-in-eop.md)：說明如何使用審核報告追蹤對服務的設定變更。</span><span class="sxs-lookup"><span data-stu-id="1b445-168">[Auditing reports in standalone EOP](auditing-reports-in-eop.md): Describes how to use auditing reports to track configuration changes to the service.</span></span>

- <span data-ttu-id="1b445-169">[EOP 中的反垃圾郵件和反惡意程式碼保護](anti-spam-and-anti-malware-protection.md)：說明垃圾郵件篩選和惡意程式碼篩選，並示範如何自訂以符合組織的需求。</span><span class="sxs-lookup"><span data-stu-id="1b445-169">[Anti-spam and anti-malware protection in EOP](anti-spam-and-anti-malware-protection.md): Describes spam filtering and malware filtering and shows how to customize them to best meet the needs of your organization.</span></span> <span data-ttu-id="1b445-170">此外，還說明系統管理員和使用者可以對隔離郵件執行的工作。</span><span class="sxs-lookup"><span data-stu-id="1b445-170">Also describes tasks that administrators and end users can perform on quarantined messages.</span></span>

- <span data-ttu-id="1b445-171">[Exchange Online Protection 的報告與訊息追蹤](reporting-and-message-trace-in-exchange-online-protection.md)：說明可用的報告和疑難排解工具。</span><span class="sxs-lookup"><span data-stu-id="1b445-171">[Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Describes the reports and troubleshooting tools that are available.</span></span>

- <span data-ttu-id="1b445-172">[Exchange admin center in 獨立 EOP](exchange-admin-center-in-exchange-online-protection-eop.md)：說明如何存取和流覽 Exchange 系統管理中心 (EAC) 管理介面，以便管理 EOP 服務。</span><span class="sxs-lookup"><span data-stu-id="1b445-172">[Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md): Describes how to access and navigate through the Exchange admin center (EAC) management interface in order to manage your EOP service.</span></span>

- <span data-ttu-id="1b445-173">[Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell)：提供遠端 PowerShell 的相關資訊，讓您可以從命令列管理 EOP 服務。</span><span class="sxs-lookup"><span data-stu-id="1b445-173">[Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): Provides information about remote PowerShell, which lets you manage your EOP service from the command line.</span></span>

- <span data-ttu-id="1b445-174">[EOP 幫助和支援](help-and-support-for-eop.md) 提供有關取得幫助和技術支援的資訊。</span><span class="sxs-lookup"><span data-stu-id="1b445-174">[Help and support for EOP](help-and-support-for-eop.md) Provides information about obtaining help and technical support.</span></span>
