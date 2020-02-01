---
title: EOP 中的郵件流程
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: 若為 Exchange Online Protection (EOP) 客戶，傳送到貴組織的所有郵件會先通過 EOP，您的背景工作才會看見這些郵件。不論透過 Exchange Online 在雲端託管所有的信箱，或將信箱託管於內部部署環境 (稱為獨立案例)，或者繼續利用現有的基礎結構，您都可以在即將通過 EOP 進行處理的郵件路由傳送到您的背景工作收件匣之前，先選擇如何路由傳送這些郵件。
ms.openlocfilehash: dfd4457dcdd036798add5ad9611c3246db22d018
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599060"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="1a0fa-104">EOP 中的郵件流程</span><span class="sxs-lookup"><span data-stu-id="1a0fa-104">Mail flow in EOP</span></span>

<span data-ttu-id="1a0fa-p102">若為 Exchange Online Protection (EOP) 客戶，傳送到貴組織的所有郵件會先通過 EOP，您的背景工作才會看見這些郵件。不論透過 Exchange Online 在雲端託管所有的信箱，或將信箱託管於內部部署環境 (稱為獨立案例)，或者繼續利用現有的基礎結構，您都可以在即將通過 EOP 進行處理的郵件路由傳送到您的背景工作收件匣之前，先選擇如何路由傳送這些郵件。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-p102">As an Exchange Online Protection (EOP) customer, all messages sent to your organization pass through EOP before your workers see them. Whether you host all of your mailboxes in the cloud with Exchange Online, or you host your mailboxes on premises (called a standalone scenario), perhaps to continue taking advantage of your existing infrastructure, you have options about how to route messages that will pass through EOP for processing before they are routed to your worker inboxes.</span></span>

<span data-ttu-id="1a0fa-p103">您可以設定自訂郵件路由，使您的郵件傳遞方式符合業務需求。例如，您可以透過原則篩選裝置傳遞所有的輸出郵件。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-p103">You may want to configure custom mail routing to conform your messaging to a business requirement. For instance, you can pass all of your outbound mail through a policy-filtering appliance.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="1a0fa-109">使用郵件和郵件存取選項</span><span class="sxs-lookup"><span data-stu-id="1a0fa-109">Working with messages and message access options</span></span>

<span data-ttu-id="1a0fa-110">EOP 對您的郵件路由傳送方式提供了很大的彈性。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-110">EOP offers a lot of flexibility in how your messages are routed.</span></span> <span data-ttu-id="1a0fa-111">下列主題說明郵件流程處理序中的步驟。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-111">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="1a0fa-112">[使用目錄架構邊緣封鎖以拒絕郵件傳送至無效收件者](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)說明目錄架構邊緣封鎖功能可讓您拒絕服務周邊網路處無效收件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-112">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="1a0fa-113">[檢視] 或 [Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)說明如何管理與您的 EOP 服務相關聯的網域。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-113">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="1a0fa-114">如果您新增子網域至組織，則 EOP 服務也可以協助您管理這些子網域。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-114">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="1a0fa-115">深入了解在[啟用郵件流程子網域的 Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)的子網域。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-115">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="1a0fa-p106">[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)簡介連接器並說明如何使用 EOP 連結器自訂郵件路由。案例包括確保與合作夥伴組織進行安全通訊及設定智慧主機。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-p106">[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing. Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="1a0fa-118">若要確保垃圾電子郵件才能正確路由至每位使用者的垃圾郵件] 資料夾，您必須執行幾個設定步驟。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-118">To ensure that junk email is routed correctly to each user's junk-email folder, you must perform a couple configuration steps.</span></span> <span data-ttu-id="1a0fa-119">詳細說明這些[確定垃圾郵件會路由傳送至每位使用者的垃圾郵件] 資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-119">These are detailed in [Ensure that spam is routed to each user's Junk Email folder](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="1a0fa-120">如果您不想要將郵件移至每位使用者的垃圾郵件] 資料夾，您可以藉由編輯您的內容篩選原則，在 Exchange 系統管理中心選擇另一個巨集指令。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-120">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="1a0fa-121">如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-121">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="1a0fa-122">驗證郵件流程</span><span class="sxs-lookup"><span data-stu-id="1a0fa-122">Verify mail flow</span></span>

<span data-ttu-id="1a0fa-p108">若要驗證 EOP 設定是否正確運作，包括連接器組態，請參閱[設定 EOP 服務](set-up-your-eop-service.md)中的「如何知道這是否正常運作？」一節。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-p108">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="1a0fa-125">[Test mail flow 藉由驗證您 Office 365 連接器來](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)提供指示測試郵件流程設定正確。</span><span class="sxs-lookup"><span data-stu-id="1a0fa-125">[Test mail flow by validating your Office 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
