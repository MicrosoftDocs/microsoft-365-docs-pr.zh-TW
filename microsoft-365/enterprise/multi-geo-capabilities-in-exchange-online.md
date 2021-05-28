---
title: Exchange 多地理位置
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: 深入瞭解 Exchange Online 中的多地理位置功能，例如功能限制和信箱位置。
ms.openlocfilehash: 4c8f873039cd14251931125f5af2c04b7cbfe719
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694302"
---
# <a name="multi-geo-capabilities-in-exchange-online"></a><span data-ttu-id="fbfcf-103">Exchange Online 中的多地理位置功能</span><span class="sxs-lookup"><span data-stu-id="fbfcf-103">Multi-Geo Capabilities in Exchange Online</span></span>

<span data-ttu-id="fbfcf-104">在多地理位置環境中，您可以以每個使用者為基礎選取 Exchange Online 信箱內容 (待用資料) 的位置。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-104">In a multi-geo environment, you can select the location of Exchange Online mailbox content (data at rest) on a per-user basis.</span></span>

<span data-ttu-id="fbfcf-105">您可以透過以下方式，將信箱在衛星地理位置：</span><span class="sxs-lookup"><span data-stu-id="fbfcf-105">You can place mailboxes in satellite geo locations by:</span></span>

- <span data-ttu-id="fbfcf-106">直接在衛星地理位置中建立新的 Exchange Online 信箱。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-106">Creating a new Exchange Online mailbox directly in a satellite geo location.</span></span>

- <span data-ttu-id="fbfcf-107">藉由變更使用者的慣用資料位置，將現有的 Exchange Online 信箱移至衛星地理位置。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-107">Moving an existing Exchange Online mailbox to a satellite geo location by changing the user's preferred data location.</span></span>

- <span data-ttu-id="fbfcf-108">從內部部署 Exchange 組織直接將信箱上線至衛星地理位置。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-108">Onboarding a mailbox from an on-premises Exchange organization directly into a satellite geo location.</span></span>

## <a name="mailbox-placement-and-moves"></a><span data-ttu-id="fbfcf-109">信箱放置及移動</span><span class="sxs-lookup"><span data-stu-id="fbfcf-109">Mailbox placement and moves</span></span>

<span data-ttu-id="fbfcf-110">在 Microsoft 完成必要的多地理位置組態步驟之後，Exchange Online 會採用 Azure AD 中使用者物件上的 **PreferredDataLocation** 屬性。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-110">After Microsoft completes the prerequisite multi-geo configuration steps, Exchange Online will honor the **PreferredDataLocation** attribute on user objects in Azure AD.</span></span>

<span data-ttu-id="fbfcf-111">Exchange Online 會從 Azure AD 將 **PreferredDataLocation** 屬性同步處理到 Exchange Online 目錄服務中的 **MailboxRegion** 屬性。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-111">Exchange Online synchronizes the **PreferredDataLocation** property from Azure AD into the **MailboxRegion** property in the Exchange Online directory service.</span></span> <span data-ttu-id="fbfcf-112">**MailboxRegion** 的值決定將放置使用者信箱和任何相關聯封存信箱所在的地理位置。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-112">The value of **MailboxRegion** determines the geo location where user mailboxes and any associated archive mailboxes will be placed.</span></span> <span data-ttu-id="fbfcf-113">您無法將使用者的主要信箱和封存信箱設定位於不同地理位置。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-113">It is not possible to configure a user's primary mailbox and archive mailboxes to reside in different geo locations.</span></span> <span data-ttu-id="fbfcf-114">每個使用者物件只能設定單一地理位置。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-114">Only one geo location may be configured per user object.</span></span>

- <span data-ttu-id="fbfcf-115">在具有現有信箱的使用者上設定 **PreferredDataLocation** 時，信箱將會放在重新配置佇列，並且會自動移至指定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-115">When **PreferredDataLocation** is configured on a user with an existing mailbox, the mailbox will be put into a relocation queue and automatically moved to the specified geo location.</span></span>

- <span data-ttu-id="fbfcf-116">在沒有現有信箱的使用者上設定 **PreferredDataLocation** 時，當您佈建信箱，會將信箱佈建到指定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-116">When **PreferredDataLocation** is configured on a user without an existing mailbox, when you provision the mailbox, it will be provisioned into the specified geo location.</span></span>

- <span data-ttu-id="fbfcf-117">未對使用者指定 **PreferredDataLocation** 時，當您佈建信箱，就會在中心地理位置佈建信箱。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-117">When **PreferredDataLocation** is not specified on a user, when you provision the mailbox, it will be provisioned in the central geo location.</span></span>

- <span data-ttu-id="fbfcf-118">如果 **PreferredDataLocation** 程式碼不正確 (例如，為 NAN，而不是) ，將會在中央地理位置中布建信箱。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-118">If the **PreferredDataLocation** code is incorrect (e.g. a typo of NAN instead of NAM), the mailbox will be provisioned in the central geo location.</span></span>

<span data-ttu-id="fbfcf-119">**注意**：多地理位置功能和商務用 Skype Online 區域裝載的會議都使用使用者物件上的 **PreferredDataLocation** 屬性來尋找服務。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-119">**Note**: Multi-geo capabilities and Skype for Business Online regionally hosted meetings both use the **PreferredDataLocation** property on user objects to locate services.</span></span> <span data-ttu-id="fbfcf-120">如果您在使用者物件上為區域裝載的會議設定 **PreferredDataLocation** 值，這些使用者的信箱將會於 Microsoft 365 租用戶上啟用多地理位置後，自動移到指定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-120">If you configure **PreferredDataLocation** values on user objects for regionally hosted meetings, the mailbox for those users will be automatically moved to the specified geo location after multi-geo is enabled on the Microsoft 365 tenant.</span></span>

## <a name="feature-limitations-for-multi-geo-in-exchange-online"></a><span data-ttu-id="fbfcf-121">Exchange Online 中的多地理位置功能限制</span><span class="sxs-lookup"><span data-stu-id="fbfcf-121">Feature limitations for multi-geo in Exchange Online</span></span>

- <span data-ttu-id="fbfcf-122">Exchange 系統管理中心 (EAC) 中提供的安全性與合規性功能 (例如，稽核與電子文件探索)，在多地理位置組織中無法使用。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-122">Security and compliance features (for example, auditing and eDiscovery) that are available in the Exchange admin center (EAC) aren't available in multi-geo organizations.</span></span> <span data-ttu-id="fbfcf-123">相反地，您必須使用 [Microsoft 365 安全性與合規性中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)來設定安全性與合規性功能。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-123">Instead, you need to use the [Microsoft 365 Security & Compliance Center](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) to configure security and compliance features.</span></span>

- <span data-ttu-id="fbfcf-124">Mac 版 Outlook 使用者在您將他們的信箱移動到新地理位置時，可能會暫時無法存取其線上封存資料夾。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-124">Outlook for Mac users may experience a temporary loss of access to their Online Archive folder while you move their mailbox to a new geo location.</span></span> <span data-ttu-id="fbfcf-125">當使用者的主要信箱和封存信箱位於不同地理位置時，會發生此情況，因為跨地理位置信箱移動可能在不同的時間完成。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-125">This condition occurs when the user's the primary and archive mailboxes are in different geo locations, because cross-geo mailbox moves may complete at different times.</span></span>

- <span data-ttu-id="fbfcf-126">使用者無法在 Outlook 網頁版 (先前稱為 Outlook Web App 或 OWA) 中跨地理位置共用 *信箱資料夾*。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-126">Users can't share *mailbox folders* across geo locations in Outlook on the web (formerly known as Outlook Web App or OWA).</span></span> <span data-ttu-id="fbfcf-127">例如，歐盟的使用者無法使用 Outlook 網頁版來開啟位於美國信箱中的共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-127">For example, a user in the European Union can't use Outlook on the web to open a shared folder in a mailbox that's located in the United States.</span></span> <span data-ttu-id="fbfcf-128">不過，如同[在另一個瀏覽器視窗中，使用 Outlook Web App 開啟另一個人的信箱](https://support.office.com/article/A909AD30-E413-40B5-A487-0EA70B763081#__toc372210362)中所述，Outlook 網頁版使用者可以使用不同的瀏覽器視窗來開啟不同地理位置的其他信箱。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-128">However, Outlook on the Web users can open *other mailboxes* in different geo locations by using a separate browser window as described in [Open another person's mailbox in a separate browser window in Outlook Web App](https://support.office.com/article/A909AD30-E413-40B5-A487-0EA70B763081#__toc372210362).</span></span>

  <span data-ttu-id="fbfcf-129">**注意**：Windows 上的 Outlook 中支援跨地理位置信箱資料夾共用。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-129">**Note**: Cross-geo mailbox folder sharing is supported in Outlook on Windows.</span></span>

- <span data-ttu-id="fbfcf-130">多地理位置組織中支援公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-130">Public folders are supported in multi-geo organizations.</span></span> <span data-ttu-id="fbfcf-131">不過，公用資料夾必須保持在中央地理位置。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-131">However, the public folders must remain in the central geo location.</span></span> <span data-ttu-id="fbfcf-132">您無法將公用資料夾移動至衛星地理位置。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-132">You can't move public folders to satellite geo locations.</span></span>

- <span data-ttu-id="fbfcf-133">在地理位置環境中，不支援跨地理位置信箱稽核。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-133">In a multi-geo environment, cross-geo mailbox auditing is not supported.</span></span> <span data-ttu-id="fbfcf-134">例如，如果指派給使用者的權限可以存取不同地理位置的共用信箱，則該使用者執行的信箱動作不會記錄在共用信箱的信箱稽核記錄中。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-134">For example, if a user is assigned permissions to access a shared mailbox in a different geo location, mailbox actions performed by that user are not logged in the mailbox audit log of the shared mailbox.</span></span> <span data-ttu-id="fbfcf-135">如需詳細資訊，請參閱[管理信箱稽核](../compliance/enable-mailbox-auditing.md?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="fbfcf-135">For more information, see [Manage mailbox auditing](../compliance/enable-mailbox-auditing.md?view=o365-worldwide).</span></span>
