---
title: 使用 Exchange Online Protection 保護內部部署的信箱
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/1/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
description: 即使您打算將部分或所有信箱裝載在內部部署，您仍然可以使用 Exchange Online Protection (EOP) 保護信箱。 若要設定連接器，您的帳戶必須是全域管理員或 Exchange 公司管理員（組織管理角色群組）。 如需 Office 365 權限與 Exchange 權限之關係的相關資訊，請參閱由 21Vianet 營運的 Office 365 中指派系統管理員角色。 如果您的 Exchange 信箱均為內部部署，請遵循以下步驟以設定 EOP 服務。
ms.openlocfilehash: 5d60e762b46f6f6f9228fb21ea6450e015ed9d93
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634445"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a><span data-ttu-id="03baf-106">使用 Exchange Online Protection 保護內部部署的信箱</span><span class="sxs-lookup"><span data-stu-id="03baf-106">Protect on-premises mailboxes with Exchange Online Protection</span></span>

> [!NOTE]
> <span data-ttu-id="03baf-107">本文僅適用於中國 21Vianet 所營運的 Office 365。</span><span class="sxs-lookup"><span data-stu-id="03baf-107">This article applies only to Office 365 operated by 21Vianet in China.</span></span>

<span data-ttu-id="03baf-108">即使您打算將部分或所有信箱裝載在內部部署，您仍然可以使用 Exchange Online Protection (EOP) 保護信箱。</span><span class="sxs-lookup"><span data-stu-id="03baf-108">Even if you plan to host some or all of your mailboxes on-premises, you can still protect the mailboxes with Exchange Online Protection (EOP).</span></span> <span data-ttu-id="03baf-109">若要設定連接器，您的帳戶必須是全域管理員或 Exchange 公司管理員（組織管理角色群組）。</span><span class="sxs-lookup"><span data-stu-id="03baf-109">To configure connectors, your account must be a global admin, or an Exchange Company Administrator (the Organization Management role group).</span></span> <span data-ttu-id="03baf-110">如需 Office 365 權限與 Exchange 權限之關係的相關資訊，請參閱[由 21Vianet 營運的 Office 365 中指派系統管理員角色](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?&view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="03baf-110">For information about how Office 365 permissions relate to Exchange permissions, see [Assigning admin roles in Office 365 operated by 21Vianet](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?&view=o365-21vianet).</span></span> <span data-ttu-id="03baf-111">如果您的 Exchange 信箱均為內部部署，請遵循以下步驟以設定 EOP 服務。</span><span class="sxs-lookup"><span data-stu-id="03baf-111">If all of your Exchange mailboxes are on-premise, follow these steps to set up your EOP service.</span></span>

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="03baf-112">步驟 1：使用 Microsoft 365 系統管理中心新增及確認您的網域</span><span class="sxs-lookup"><span data-stu-id="03baf-112">Step 1: Use the Microsoft 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="03baf-113">在 Microsoft 365 系統管理中心中，瀏覽至 [設定] 將您的網域新增至服務。</span><span class="sxs-lookup"><span data-stu-id="03baf-113">In the Microsoft 365 admin center, navigate to Setup to add your domain to the service.</span></span>

2. <span data-ttu-id="03baf-114">請遵循入口網站的步驟，將適用的 DNS 記錄新增到 DNS 主機提供者，以便驗證網域擁有權。</span><span class="sxs-lookup"><span data-stu-id="03baf-114">Follow the steps in the portal to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span>

> [!TIP]
> <span data-ttu-id="03baf-115">當您新增網域至此服務並設定 DNS 時，[新增網域和使用者至 21Vianet 營運的 Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?&view=o365-21vianet) (部分機器翻譯) 和 [管理您的 DNS 記錄時建立 Office 365 的 DNS 記錄](https://docs.microsoft.com/office365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?&view=o365-21vianet) (部分機器翻譯)，是有用的參考資源。</span><span class="sxs-lookup"><span data-stu-id="03baf-115">[Add your domain and users to Office 365 operated by 21Vianet](https://docs.microsoft.com/office365/admin/setup/add-domain?&view=o365-21vianet) and [Create DNS records for Office 365 when you manage your DNS records](https://docs.microsoft.com/office365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?&view=o365-21vianet) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span>

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a><span data-ttu-id="03baf-116">步驟 2：新增收件者和設定網域類型</span><span class="sxs-lookup"><span data-stu-id="03baf-116">Step 2: Add recipients and configure the domain type</span></span>

<span data-ttu-id="03baf-117">在設定您的郵件來進出 EOP 服務之前，建議您將收件者新增至服務。</span><span class="sxs-lookup"><span data-stu-id="03baf-117">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service.</span></span> <span data-ttu-id="03baf-118">有許多種作法，請參閱＜[管理 EOP 中的郵件使用者](manage-mail-users-in-eop.md)＞。</span><span class="sxs-lookup"><span data-stu-id="03baf-118">There are several ways in which you can do this, as documented in [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="03baf-119">另外，如果您要啟用目錄架構邊緣封鎖 (DBEB)，以便在服務內新增收件者之後強制驗證收件者，則必須將網域類型設為「授權」。</span><span class="sxs-lookup"><span data-stu-id="03baf-119">Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative.</span></span> <span data-ttu-id="03baf-120">如需 DBEB 的相關資訊，請參閱[使用目錄架構邊緣封鎖以拒絕傳送至無效收件者的郵件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="03baf-120">For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="03baf-121">步驟 3：使用 EAC 來設定郵件流程</span><span class="sxs-lookup"><span data-stu-id="03baf-121">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="03baf-122">在 Exchange 系統管理中心 (EAC) 內建立連接器，來啟用 EOP 與您內部部署郵件伺服器之間的郵件流程。</span><span class="sxs-lookup"><span data-stu-id="03baf-122">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers.</span></span> <span data-ttu-id="03baf-123">如需詳細指示，請參閱 [使用 Office 365 中的連接器設定郵件流程](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="03baf-123">For detailed instructions, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

 <span data-ttu-id="03baf-124">如何才能了解此工作是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="03baf-124">How do you know this task worked?</span></span>

 <span data-ttu-id="03baf-125">請參閱[驗證 Office 365 連接器以測試郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="03baf-125">See [Test mail flow by validating your Office 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

## <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="03baf-126">步驟 4：允許輸入連接埠 25 SMTP 存取</span><span class="sxs-lookup"><span data-stu-id="03baf-126">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="03baf-127">設定連接器之後，請等待 72 小時以允許傳播 DNS 記錄更新。</span><span class="sxs-lookup"><span data-stu-id="03baf-127">After you configured connectors, wait 72 hours to allow propagation of your DNS-record updates.</span></span> <span data-ttu-id="03baf-128">接著限制防火牆或郵件伺服器上的輸入連接埠 25 SMTP 流量，以僅接受來自 EOP 資料中心的郵件 (尤其是來自[ Office 365 URL 和 IP 位址範圍所列 IP 位址的郵件)。](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)(部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="03baf-128">Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [URLs and IP address ranges for Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span></span> <span data-ttu-id="03baf-129">這會限制您可接收的輸入郵件範圍，以保護內部部署環境的安全。</span><span class="sxs-lookup"><span data-stu-id="03baf-129">This protects your on-premises environment by limiting the scope of inbound messages you can receive.</span></span> <span data-ttu-id="03baf-130">此外，若您在郵件伺服器上進行設定，以控制允許連線執行郵件轉送的 IP 位址，請一併更新這些設定。</span><span class="sxs-lookup"><span data-stu-id="03baf-130">Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>

> [!TIP]
> <span data-ttu-id="03baf-p106">將 SMTP 伺服器的連線時間設定設為超過 60 秒。此設定適用於大部分情況，例如在傳送具有大型附件的郵件時可稍許延遲。</span><span class="sxs-lookup"><span data-stu-id="03baf-p106">Configure settings on the SMTP server with a connection time out of 60 seconds. This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for instance.</span></span>

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="03baf-133">步驟5：確定垃圾郵件路由傳送至每個使用者的 [垃圾郵件] 資料夾</span><span class="sxs-lookup"><span data-stu-id="03baf-133">Step 5: Ensure that spam is routed to each user's Junk Email folder</span></span>

<span data-ttu-id="03baf-134">為了確保垃圾電子郵件正確地路由傳送至每個使用者的 [垃圾郵件] 資料夾，您必須執行幾個設定步驟。</span><span class="sxs-lookup"><span data-stu-id="03baf-134">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps.</span></span> <span data-ttu-id="03baf-135">[設定獨立 EOP 中的步驟，將垃圾郵件傳遞至混合式環境中的 [垃圾郵件] 資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="03baf-135">The steps are provided in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="03baf-136">如果不要將郵件移至每個使用者的 [垃圾郵件] 資料夾，您可以在 Exchange 系統管理中心編輯內容篩選原則，以選擇其他動作。</span><span class="sxs-lookup"><span data-stu-id="03baf-136">If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="03baf-137">如需詳細資訊，請參閱[在 Office 365 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="03baf-137">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="03baf-138">步驟 6：使用 Microsoft 365 系統管理中心將您的 MX 記錄指向 EOP</span><span class="sxs-lookup"><span data-stu-id="03baf-138">Step 6: Use the Microsoft 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="03baf-139">請遵循 Office 365 網域設定步驟來更新網域的 MX 記錄，以讓輸入電子郵件經過 EOP。</span><span class="sxs-lookup"><span data-stu-id="03baf-139">Follow the Office 365 domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP.</span></span> <span data-ttu-id="03baf-140">如需詳細資訊，您可以再次參考[管理 DNS 記錄時為 Office 365 建立 DNS 記錄](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="03baf-140">For more information, you can again reference [Create DNS records for Office 365 when you manage your DNS records](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="03baf-141">如何才能了解此工作是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="03baf-141">How do you know this task worked?</span></span>

 <span data-ttu-id="03baf-142">請參閱[驗證 Office 365 連接器以測試郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="03baf-142">See [Test mail flow by validating your Office 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

<span data-ttu-id="03baf-p109">到目前為止，您已確定有正確設定的輸出內部部署連接器可用來進行服務傳遞，並已確認 MX 記錄是指向 EOP。現在您可以選擇執行下列其他測試，以確認服務能夠成功將電子郵件傳遞至您的內部部署環境：</span><span class="sxs-lookup"><span data-stu-id="03baf-p109">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>

- <span data-ttu-id="03baf-145">在 Remote Connectivity Analyzer 中，按一下 **[Office 365]** 索引標籤，然後執行位於 **[網際網路電子郵件測試]** 底下的 **[輸入 SMTP 電子郵件]** 測試。</span><span class="sxs-lookup"><span data-stu-id="03baf-145">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span></span>

- <span data-ttu-id="03baf-p110">從任何其網域符合您新增至此服務之網域的 Web 式電子郵件帳戶，傳送電子郵件給您組織中的郵件收件者。使用 Microsoft Outlook 或其他電子郵件用戶端，確認郵件已傳遞至內部部署信箱。</span><span class="sxs-lookup"><span data-stu-id="03baf-p110">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>

- <span data-ttu-id="03baf-148">如果您想要執行輸出電子郵件測試，可以從組織中的使用者傳送電子郵件到 Web 式電子郵件帳戶，再確認郵件是否已收到。</span><span class="sxs-lookup"><span data-stu-id="03baf-148">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a><span data-ttu-id="03baf-149">較不常見：具有內部部署和雲端信箱的混合式設定</span><span class="sxs-lookup"><span data-stu-id="03baf-149">Less common: A hybrid setup with mailboxes on-premises and in the cloud</span></span>

<span data-ttu-id="03baf-150">如果您擁有 Exchange 信箱內部部署和 Exchange Online 中一個或多個雲端信箱，則您具有*混合式*設定。</span><span class="sxs-lookup"><span data-stu-id="03baf-150">If you have Exchange mailboxes on-premises and one or more mailboxes in the cloud in Exchange Online, you have a *hybrid* setup.</span></span> <span data-ttu-id="03baf-151">在混合式設定中，例如空閒/忙碌行事曆共用和郵件路由等功能可在您的內部部署和雲端環境中共同作業。</span><span class="sxs-lookup"><span data-stu-id="03baf-151">In a hybrid setup, features such as free/busy calendar sharing and mail routing work together in your on-premises and cloud environments.</span></span> <span data-ttu-id="03baf-152">將信箱移轉到 Exchange Online 時，可能會啟用混合式設定。</span><span class="sxs-lookup"><span data-stu-id="03baf-152">You might have a hybrid setup in place while you transition mailboxes to Exchange Online.</span></span> <span data-ttu-id="03baf-153">混合式環境的設定不同於 EOP 獨立防護。</span><span class="sxs-lookup"><span data-stu-id="03baf-153">A hybrid environment is set up differently than EOP standalone protection.</span></span>

<span data-ttu-id="03baf-154">您可以選擇混合式案例，以利用雲端式電子郵件給大部分員工使用。</span><span class="sxs-lookup"><span data-stu-id="03baf-154">You might choose a hybrid scenario to take advantage of cloud-based email for most of your employees.</span></span> <span data-ttu-id="03baf-155">您可以在執行這項作業的同時，將部分信箱裝載在內部部署；例如，針對法務部門。</span><span class="sxs-lookup"><span data-stu-id="03baf-155">You can do this while also hosting some mailboxes on-premises; for example, for your legal department.</span></span>

<span data-ttu-id="03baf-156">混合式設定可能會很複雜，但也有許多優點。</span><span class="sxs-lookup"><span data-stu-id="03baf-156">A hybrid setup can be complex, but it has many benefits.</span></span> <span data-ttu-id="03baf-157">若要深入了解如何使用 Exchange 設定混合式案例，請參閱 [Exchange Server 混合式部署](https://docs.microsoft.com/Exchange/exchange-hybrid) (部分機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="03baf-157">To learn more about setting up hybrid scenarios with Exchange, see [Exchange Server hybrid deployments](https://docs.microsoft.com/Exchange/exchange-hybrid).</span></span>
