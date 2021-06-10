---
title: EOP 中的郵件流程
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解在 Exchange Online Protection (EOP) 中設定郵件流程及路由的選項。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9636025796aee1ba2027edff38a16f131974134f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842491"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="36a8b-103">EOP 中的郵件流程</span><span class="sxs-lookup"><span data-stu-id="36a8b-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="36a8b-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="36a8b-104">**Applies to**</span></span>
- [<span data-ttu-id="36a8b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="36a8b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="36a8b-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="36a8b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="36a8b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36a8b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="36a8b-108">在具有 Exchange Online 信箱的 Microsoft 365 組織，或獨立 Exchange Online Protection (EOP) 組織若未 Exchange Online 信箱，所有傳送給您組織的郵件都會透過 EOP，再讓工作者看到這些郵件。</span><span class="sxs-lookup"><span data-stu-id="36a8b-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="36a8b-109">您可以選擇如何路由傳送至您的工作人員收件匣的郵件，並透過 EOP 進行處理。</span><span class="sxs-lookup"><span data-stu-id="36a8b-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="36a8b-110">使用郵件和郵件存取選項</span><span class="sxs-lookup"><span data-stu-id="36a8b-110">Working with messages and message access options</span></span>

<span data-ttu-id="36a8b-111">EOP 提供郵件路由傳送方式的彈性。</span><span class="sxs-lookup"><span data-stu-id="36a8b-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="36a8b-112">下列主題說明郵件流程處理序中的步驟。</span><span class="sxs-lookup"><span data-stu-id="36a8b-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="36a8b-113">[使用目錄架構邊緣封鎖以拒絕傳送至無效收件](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 者的郵件描述目錄型 Edge 封鎖功能，可讓您拒絕服務網路周邊上無效收件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="36a8b-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="36a8b-114">[View or edit 公認的網域 IN EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 說明如何管理與 EOP 服務相關聯的網域。</span><span class="sxs-lookup"><span data-stu-id="36a8b-114">[View or edit accepted domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="36a8b-115">如果您新增子網域至組織，則 EOP 服務也可以協助您管理這些子網域。</span><span class="sxs-lookup"><span data-stu-id="36a8b-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="36a8b-116">若要深入瞭解子域，請參閱[啟用 Exchange Online 中子域的郵件流程](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。</span><span class="sxs-lookup"><span data-stu-id="36a8b-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="36a8b-117">[使用連接器來設定郵件流程](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 介紹連接器，並說明如何使用這些連接器來自訂郵件路由。</span><span class="sxs-lookup"><span data-stu-id="36a8b-117">[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="36a8b-118">案例包括確保與合作夥伴組織進行安全通訊及設定智慧主機。</span><span class="sxs-lookup"><span data-stu-id="36a8b-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="36a8b-119">[針對連接器的增強篩選](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 說明如何在 EOP 之前，先將郵件路由傳送至服務或裝置，以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="36a8b-119">[Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="36a8b-120">在 EOP 會保護內部部署 Exchange 信箱的混合式環境中，您必須在內部部署 Exchange 中設定郵件流程規則 (又稱為傳輸規則) 以轉譯 EOP 垃圾郵件篩選裁決，這樣垃圾郵件規則才可以將郵件移至 [垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="36a8b-120">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="36a8b-121">如需詳細資訊，請參閱[設定 EOP 以將垃圾郵件傳送到混合式環境中的垃圾郵件資料夾](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。</span><span class="sxs-lookup"><span data-stu-id="36a8b-121">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span> <span data-ttu-id="36a8b-122">如果您不想要將郵件移至每個使用者的 [垃圾郵件] 資料夾，您可以編輯反垃圾郵件原則 (也稱為內容篩選原則) ，以選擇另一個動作。</span><span class="sxs-lookup"><span data-stu-id="36a8b-122">If you don't  want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="36a8b-123">如需詳細資訊，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="36a8b-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="36a8b-124">驗證郵件流程</span><span class="sxs-lookup"><span data-stu-id="36a8b-124">Verify mail flow</span></span>

<span data-ttu-id="36a8b-p106">若要驗證 EOP 設定是否正確運作，包括連接器組態，請參閱[設定 EOP 服務](/exchange/standalone-eop/set-up-your-eop-service)中的「如何知道這是否正常運作？」一節。</span><span class="sxs-lookup"><span data-stu-id="36a8b-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service).</span></span>

<span data-ttu-id="36a8b-127">[測試郵件流程：透過驗證 Microsoft 365 連接器](/exchange/mail-flow-best-practices/test-mail-flow)提供測試郵件流程是否設定正確的指示。</span><span class="sxs-lookup"><span data-stu-id="36a8b-127">[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
