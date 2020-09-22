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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 系統管理員可以瞭解在 Exchange Online Protection (EOP) 中設定郵件流程及路由的選項。
ms.openlocfilehash: e1c821e3de8dd7dd18c192522bd18fd32a395dca
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200700"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="98e63-103">EOP 中的郵件流程</span><span class="sxs-lookup"><span data-stu-id="98e63-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="98e63-104">在具有 Exchange Online 信箱的 Microsoft 365 組織中，或獨立 Exchange Online Protection (EOP) 組織沒有 Exchange Online 信箱，所有傳送給您組織的郵件都會透過 EOP 傳遞，然後您的工作者才能看到它們。</span><span class="sxs-lookup"><span data-stu-id="98e63-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="98e63-105">您可以選擇如何路由傳送至您的工作人員收件匣的郵件，並透過 EOP 進行處理。</span><span class="sxs-lookup"><span data-stu-id="98e63-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="98e63-106">使用郵件和郵件存取選項</span><span class="sxs-lookup"><span data-stu-id="98e63-106">Working with messages and message access options</span></span>

<span data-ttu-id="98e63-107">EOP 提供郵件路由傳送方式的彈性。</span><span class="sxs-lookup"><span data-stu-id="98e63-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="98e63-108">下列主題說明郵件流程處理序中的步驟。</span><span class="sxs-lookup"><span data-stu-id="98e63-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="98e63-109">[使用目錄架構邊緣封鎖以拒絕傳送至無效收件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 者的郵件描述目錄型 Edge 封鎖功能，可讓您拒絕服務網路周邊上無效收件者的郵件。</span><span class="sxs-lookup"><span data-stu-id="98e63-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="98e63-110">[在 EOP 中查看或編輯受管理的網域](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 說明如何管理與 EOP 服務相關聯的網域。</span><span class="sxs-lookup"><span data-stu-id="98e63-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="98e63-111">如果您新增子網域至組織，則 EOP 服務也可以協助您管理這些子網域。</span><span class="sxs-lookup"><span data-stu-id="98e63-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="98e63-112">若要深入瞭解子域，請參閱 [啟用 Exchange Online 中子域的郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。</span><span class="sxs-lookup"><span data-stu-id="98e63-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="98e63-113">[使用連接器來設定郵件流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 介紹連接器，並說明如何使用這些連接器來自訂郵件路由。</span><span class="sxs-lookup"><span data-stu-id="98e63-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="98e63-114">案例包括確保與合作夥伴組織進行安全通訊及設定智慧主機。</span><span class="sxs-lookup"><span data-stu-id="98e63-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="98e63-115">[針對連接器的增強篩選](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 說明如何在 EOP 之前，先將郵件路由傳送至服務或裝置，以設定連接器。</span><span class="sxs-lookup"><span data-stu-id="98e63-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="98e63-116">在獨立 EOP 組織中，您必須執行一些設定步驟，以確保垃圾郵件可正確路由傳送至每位使用者的垃圾郵件資料夾。</span><span class="sxs-lookup"><span data-stu-id="98e63-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="98e63-117">在 [設定獨立 EOP 將垃圾郵件傳送至混合式環境中的 [垃圾郵件] 資料夾](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)時，會加以詳述。</span><span class="sxs-lookup"><span data-stu-id="98e63-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="98e63-118">如果您不想要將郵件移至每個使用者的垃圾郵件資料夾，您可以編輯反垃圾郵件原則 (也稱為「內容篩選原則」) ，以選擇另一個動作。</span><span class="sxs-lookup"><span data-stu-id="98e63-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="98e63-119">如需詳細資訊，請參閱[設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="98e63-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="98e63-120">驗證郵件流程</span><span class="sxs-lookup"><span data-stu-id="98e63-120">Verify mail flow</span></span>

<span data-ttu-id="98e63-p106">若要驗證 EOP 設定是否正確運作，包括連接器組態，請參閱[設定 EOP 服務](set-up-your-eop-service.md)中的「如何知道這是否正常運作？」一節。</span><span class="sxs-lookup"><span data-stu-id="98e63-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="98e63-123">[測試郵件流程：透過驗證 Microsoft 365 連接器](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) 提供測試郵件流程設定正確的指示。</span><span class="sxs-lookup"><span data-stu-id="98e63-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
