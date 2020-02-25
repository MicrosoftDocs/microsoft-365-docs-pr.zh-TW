---
title: 解決共用信箱的問題
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: 如果您遇到問題的共用信箱，請嘗試這些解決方案。
ms.openlocfilehash: b45c2eefa8cb4fb5fa34808223efbc1f0023161d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251673"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="f4eda-103">解決共用信箱的問題</span><span class="sxs-lookup"><span data-stu-id="f4eda-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="f4eda-104">如果您看到錯誤訊息建立或使用共用的信箱時，請嘗試這些可能的解決方案。</span><span class="sxs-lookup"><span data-stu-id="f4eda-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="f4eda-105">建立共用信箱時發生錯誤</span><span class="sxs-lookup"><span data-stu-id="f4eda-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="f4eda-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="f4eda-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="f4eda-107">如果您看到錯誤訊息、 **proxy 位址"smtp: <共用的信箱名稱\>」 已經正在使用的 proxy 位址或 LegacyExchangeDN 「\<命名> 」。請選擇其他 proxy 位址**，就表示您想要提供共用的信箱已在使用的名稱。</span><span class="sxs-lookup"><span data-stu-id="f4eda-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="f4eda-108">舉例來說，假設您想將共用信箱命名為 info@domain1 和 info@domain2。</span><span class="sxs-lookup"><span data-stu-id="f4eda-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="f4eda-109">方法有兩種：</span><span class="sxs-lookup"><span data-stu-id="f4eda-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="f4eda-110">使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f4eda-110">Use Windows PowerShell.</span></span> <span data-ttu-id="f4eda-111">如需相關指示，請參閱此部落格文章：[在 Office 365 中建立別名相同但網域不同的共用信箱](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="f4eda-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains in Office 365](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="f4eda-112">指定的名稱，第二個共用的信箱不同從開始到避開這個錯誤。</span><span class="sxs-lookup"><span data-stu-id="f4eda-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="f4eda-113">然後在系統管理中心中，請重新共用的信箱命名為您想要。</span><span class="sxs-lookup"><span data-stu-id="f4eda-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="f4eda-114">關於使用共用的信箱時不會察覺傳送權限錯誤</span><span class="sxs-lookup"><span data-stu-id="f4eda-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="f4eda-115">如果您建立共用的信箱，然後再嘗試從它來傳送郵件，您可能收到這：</span><span class="sxs-lookup"><span data-stu-id="f4eda-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="f4eda-116">**無法傳送此郵件。您沒有代表指定使用者將郵件傳送的權限。**</span><span class="sxs-lookup"><span data-stu-id="f4eda-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="f4eda-117">Office 365 遇到的複寫延遲問題時，就會出現此訊息。</span><span class="sxs-lookup"><span data-stu-id="f4eda-117">This message appears when Office 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="f4eda-118">它應移至離開一小時或，當您新的共用的信箱 （或新增的使用者） 的資訊複製所有我們的資料中心。</span><span class="sxs-lookup"><span data-stu-id="f4eda-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="f4eda-119">請稍候一小時，然後再試一次傳送訊息。</span><span class="sxs-lookup"><span data-stu-id="f4eda-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f4eda-120">相關文章</span><span class="sxs-lookup"><span data-stu-id="f4eda-120">Related articles</span></span>

[<span data-ttu-id="f4eda-121">關於共用信箱</span><span class="sxs-lookup"><span data-stu-id="f4eda-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="f4eda-122">建立共用信箱</span><span class="sxs-lookup"><span data-stu-id="f4eda-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="f4eda-123">設定共用信箱</span><span class="sxs-lookup"><span data-stu-id="f4eda-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="f4eda-124">將使用者信箱轉換為共用信箱</span><span class="sxs-lookup"><span data-stu-id="f4eda-124">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="f4eda-125">從共用信箱中移除授權</span><span class="sxs-lookup"><span data-stu-id="f4eda-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

