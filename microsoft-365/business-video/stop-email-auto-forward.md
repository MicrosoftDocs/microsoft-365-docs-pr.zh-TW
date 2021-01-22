---
title: 停止自動轉寄電子郵件
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 瞭解如何停止自動轉轉電子郵件。
ms.openlocfilehash: ebbe37ab5c4a60c6ac4b6ebf8877247199460fa1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925883"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="52caa-103">停止自動轉轉電子郵件</span><span class="sxs-lookup"><span data-stu-id="52caa-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="52caa-104">如果駭客取得使用者信箱的存取權，駭客就可以自動將使用者的電子郵件轉會到外部地址，並竊取專利資訊。</span><span class="sxs-lookup"><span data-stu-id="52caa-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="52caa-105">您可以建立郵件流程規則來停止此程式。</span><span class="sxs-lookup"><span data-stu-id="52caa-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="52caa-106">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="52caa-106">Try it!</span></span>

1. <span data-ttu-id="52caa-107">從 Microsoft 365 系統管理中心，選取 **Exchange、** 郵件流程，然後選取規則上的加號，然後選擇建立 **新規則**。</span><span class="sxs-lookup"><span data-stu-id="52caa-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="52caa-108">選取 **更多選項**。</span><span class="sxs-lookup"><span data-stu-id="52caa-108">Select **More options**.</span></span> <span data-ttu-id="52caa-109">命名您的新規則。</span><span class="sxs-lookup"><span data-stu-id="52caa-109">Name your new rule.</span></span>
1. <span data-ttu-id="52caa-110">然後，開啟下拉式清單，以在選取寄件者，然後是外部內部時 **，適用此規則**。</span><span class="sxs-lookup"><span data-stu-id="52caa-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="52caa-111">選取 **組織內部，\*\*\*\*然後確定**。</span><span class="sxs-lookup"><span data-stu-id="52caa-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="52caa-112">選擇 **新增條件**、開啟下拉式清單、 **選取郵件** 內容，然後 **包含訊息類型**。</span><span class="sxs-lookup"><span data-stu-id="52caa-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="52caa-113">開啟選取 **訊息類型** 下拉式選檔，選擇自動 **轉送**，然後選擇 **確定**。</span><span class="sxs-lookup"><span data-stu-id="52caa-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="52caa-114">開啟執行 **下列下拉** 式清單，選取 **封鎖** 訊息，然後拒絕 **訊息並包含說明**。</span><span class="sxs-lookup"><span data-stu-id="52caa-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="52caa-115">輸入訊息文字以做為說明， **然後選取確定**。</span><span class="sxs-lookup"><span data-stu-id="52caa-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="52caa-116">卷到底部 **，然後選取** 儲存。</span><span class="sxs-lookup"><span data-stu-id="52caa-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="52caa-117">您的規則已建立完成，駭客將無法再自動轉轉郵件。</span><span class="sxs-lookup"><span data-stu-id="52caa-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>