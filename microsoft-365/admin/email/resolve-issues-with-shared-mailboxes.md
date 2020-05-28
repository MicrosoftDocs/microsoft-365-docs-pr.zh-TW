---
title: 解決共用信箱的問題
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 如果您遇到共用信箱的問題，請嘗試這些解決方案。
ms.openlocfilehash: 5d6de9ac66b11f0e50b259cdca0b1bb50b8326ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400013"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="902fc-103">解決共用信箱的問題</span><span class="sxs-lookup"><span data-stu-id="902fc-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="902fc-104">如果您在建立或使用共用信箱時看到錯誤訊息，請嘗試這些可能的解決方案。</span><span class="sxs-lookup"><span data-stu-id="902fc-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="902fc-105">建立共用信箱時發生錯誤</span><span class="sxs-lookup"><span data-stu-id="902fc-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="902fc-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="902fc-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="902fc-107">如果您看到錯誤訊息，**表示 proxy 位址 "smtp： <共用信箱名稱 \> " 已由 "" 的 proxy 位址或 LegacyExchangeDN 使用 \<name> 。請選擇另一個 proxy 位址**，這表示您嘗試將已在使用中的名稱提供給共用信箱。</span><span class="sxs-lookup"><span data-stu-id="902fc-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="902fc-108">舉例來說，假設您想將共用信箱命名為 info@domain1 和 info@domain2。</span><span class="sxs-lookup"><span data-stu-id="902fc-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="902fc-109">方法有兩種：</span><span class="sxs-lookup"><span data-stu-id="902fc-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="902fc-110">使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="902fc-110">Use Windows PowerShell.</span></span> <span data-ttu-id="902fc-111">如需相關指示，請參閱這篇博客文章：[在不同的網域建立具有相同別名的共用信箱](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="902fc-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="902fc-112">將第二個共用信箱命名為不同于「開始」以避免錯誤的地方。</span><span class="sxs-lookup"><span data-stu-id="902fc-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="902fc-113">然後在系統管理中心，將共用信箱重新命名為您想要的內容。</span><span class="sxs-lookup"><span data-stu-id="902fc-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="902fc-114">使用共用信箱時，未具備傳送許可權的錯誤</span><span class="sxs-lookup"><span data-stu-id="902fc-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="902fc-115">如果您建立了共用信箱，然後嘗試從該信箱傳送郵件，您可能會收到下列訊息：</span><span class="sxs-lookup"><span data-stu-id="902fc-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="902fc-116">**無法傳送此郵件。您沒有代表指定使用者傳送郵件的許可權。**</span><span class="sxs-lookup"><span data-stu-id="902fc-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="902fc-117">當 Microsoft 365 遇到複寫延遲問題時，就會出現此訊息。</span><span class="sxs-lookup"><span data-stu-id="902fc-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="902fc-118">當您在所有的資料中心之間複寫新共用信箱（或新增使用者）的相關資訊時，它應該會在一小時內消失。</span><span class="sxs-lookup"><span data-stu-id="902fc-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="902fc-119">請等候一小時後再試一次，再傳送一封郵件。</span><span class="sxs-lookup"><span data-stu-id="902fc-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="902fc-120">相關文章</span><span class="sxs-lookup"><span data-stu-id="902fc-120">Related articles</span></span>

[<span data-ttu-id="902fc-121">關於共用信箱</span><span class="sxs-lookup"><span data-stu-id="902fc-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="902fc-122">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="902fc-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="902fc-123">設定共用信箱</span><span class="sxs-lookup"><span data-stu-id="902fc-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="902fc-124">將使用者信箱轉換為共用信箱</span><span class="sxs-lookup"><span data-stu-id="902fc-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="902fc-125">從共用信箱中移除授權</span><span class="sxs-lookup"><span data-stu-id="902fc-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

