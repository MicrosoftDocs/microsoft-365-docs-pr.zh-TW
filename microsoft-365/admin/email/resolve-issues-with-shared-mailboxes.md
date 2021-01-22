---
title: 解決共用信箱的問題
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: 如果您在使用共用信箱時遇到問題，請嘗試這些解決方案。
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926483"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="79838-103">解決共用信箱的問題</span><span class="sxs-lookup"><span data-stu-id="79838-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="79838-104">如果您在建立或使用共用信箱時看到錯誤訊息，請嘗試這些可能的解決方案。</span><span class="sxs-lookup"><span data-stu-id="79838-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="79838-105">建立共用信箱時發生錯誤</span><span class="sxs-lookup"><span data-stu-id="79838-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="79838-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="79838-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="79838-107">如果您看到錯誤訊息，表示 Proxy 位址 "smtp：<共用信箱名稱" 已由 " "的 Proxy 位址 **\> 或 LegacyExchangeDN \<name> 使用。請選擇另一個 Proxy 位址**，這表示您嘗試為共用信箱提供已在使用中的名稱。</span><span class="sxs-lookup"><span data-stu-id="79838-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="79838-108">舉例來說，假設您想將共用信箱命名為 info@domain1 和 info@domain2。</span><span class="sxs-lookup"><span data-stu-id="79838-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="79838-109">方法有兩種：</span><span class="sxs-lookup"><span data-stu-id="79838-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="79838-110">使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="79838-110">Use Windows PowerShell.</span></span> <span data-ttu-id="79838-111">請參閱此部落格文章以參閱指示：在不同的網域建立別名 [相同的共用信箱](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="79838-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="79838-112">將第二個共用信箱命名為與一開始不同的名稱以擺脫錯誤。</span><span class="sxs-lookup"><span data-stu-id="79838-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="79838-113">然後在系統管理中心，將共用信箱重新命名為您想要的名稱。</span><span class="sxs-lookup"><span data-stu-id="79838-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="79838-114">使用共用信箱時沒有傳送許可權的錯誤</span><span class="sxs-lookup"><span data-stu-id="79838-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="79838-115">如果您建立了共用信箱，然後嘗試從共用信箱傳送郵件，您可能會收到以下訊息：</span><span class="sxs-lookup"><span data-stu-id="79838-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="79838-116">**無法送出此郵件。您沒有代表指定使用者傳送郵件的許可權。**</span><span class="sxs-lookup"><span data-stu-id="79838-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="79838-117">當 Microsoft 365 發生複寫延遲問題時，會出現這則訊息。</span><span class="sxs-lookup"><span data-stu-id="79838-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="79838-118">當您的新共用信箱資訊已複製 (或新增的使用者) 複製至我們所有資料中心時，一小時左右應該會消失。</span><span class="sxs-lookup"><span data-stu-id="79838-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="79838-119">請等候一個小時，然後再試一次以傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="79838-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="79838-120">相關文章</span><span class="sxs-lookup"><span data-stu-id="79838-120">Related articles</span></span>

[<span data-ttu-id="79838-121">關於共用信箱</span><span class="sxs-lookup"><span data-stu-id="79838-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="79838-122">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="79838-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="79838-123">設定共用信箱</span><span class="sxs-lookup"><span data-stu-id="79838-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="79838-124">將使用者信箱轉換為共用信箱</span><span class="sxs-lookup"><span data-stu-id="79838-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="79838-125">從共用信箱中移除授權</span><span class="sxs-lookup"><span data-stu-id="79838-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

