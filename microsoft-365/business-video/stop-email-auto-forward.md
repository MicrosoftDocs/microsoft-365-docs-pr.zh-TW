---
title: 停止自動轉送電子郵件
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何停止自動轉送電子郵件。
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701733"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="ce8a1-103">停止電子郵件自動轉寄</span><span class="sxs-lookup"><span data-stu-id="ce8a1-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="ce8a1-104">如果駭客取得使用者信箱的存取權，他們就可以將使用者的電子郵件自動轉寄到外部地址，並竊取專有資訊。</span><span class="sxs-lookup"><span data-stu-id="ce8a1-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="ce8a1-105">您可以建立郵件流程規則來停止這種情況。</span><span class="sxs-lookup"><span data-stu-id="ce8a1-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="ce8a1-106">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="ce8a1-106">Try it!</span></span>

1. <span data-ttu-id="ce8a1-107">在 Microsoft 365 系統管理中心中，選取 [ **Exchange**]、[ **郵件流程**]，然後在 [ **規則** ] 索引標籤上，選取加號，然後選擇 [ **建立新規則**]。</span><span class="sxs-lookup"><span data-stu-id="ce8a1-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="ce8a1-108">選取 [ **更多選項**]。</span><span class="sxs-lookup"><span data-stu-id="ce8a1-108">Select **More options**.</span></span> <span data-ttu-id="ce8a1-109">為您的新規則命名。</span><span class="sxs-lookup"><span data-stu-id="ce8a1-109">Name your new rule.</span></span>
1. <span data-ttu-id="ce8a1-110">然後開啟下拉清單以套用 **此規則如果** 是，請選取 **寄件者**，然後 **是外部內部**。</span><span class="sxs-lookup"><span data-stu-id="ce8a1-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="ce8a1-111">選取 **組織內**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ce8a1-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="ce8a1-112">選擇 [ **新增條件**]，開啟下拉式清單，選取 **郵件** 內容，然後 **加入郵件類型**。</span><span class="sxs-lookup"><span data-stu-id="ce8a1-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="ce8a1-113">開啟 [ **選取郵件類型** ] 下拉式清單，選擇 [ **自動轉寄**]，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ce8a1-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="ce8a1-114">開啟 [ **執行下列** 下拉式清單]，選取 [ **封鎖郵件**]，然後 **拒絕郵件，並包含說明**。</span><span class="sxs-lookup"><span data-stu-id="ce8a1-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="ce8a1-115">輸入您的說明的訊息文字，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ce8a1-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="ce8a1-116">向下並選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="ce8a1-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="ce8a1-117">您的規則已經建立，駭客也無法再自動轉寄郵件。</span><span class="sxs-lookup"><span data-stu-id="ce8a1-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>