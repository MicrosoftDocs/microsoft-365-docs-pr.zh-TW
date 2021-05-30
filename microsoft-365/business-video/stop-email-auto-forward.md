---
title: 停止自動轉寄電子郵件
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: 瞭解如何建立郵件流程規則以避免盜竊專有資訊，以停止自動轉寄電子郵件。
ms.openlocfilehash: 82e4c80b0edc501889e0fc4dc28f1ec1ad703568
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706471"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="91d5c-103">停止電子郵件自動轉寄</span><span class="sxs-lookup"><span data-stu-id="91d5c-103">Stop email auto-forward</span></span>

## <a name="watch-stop-auto-forwarding-emails"></a><span data-ttu-id="91d5c-104">觀賞：停止自動轉送電子郵件</span><span class="sxs-lookup"><span data-stu-id="91d5c-104">Watch: Stop auto-forwarding emails</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="91d5c-105">如果駭客取得使用者信箱的存取權，他們就可以將使用者的電子郵件自動轉寄到外部地址，並竊取專有資訊。</span><span class="sxs-lookup"><span data-stu-id="91d5c-105">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="91d5c-106">您可以建立郵件流程規則來停止這種情況。</span><span class="sxs-lookup"><span data-stu-id="91d5c-106">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="91d5c-107">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="91d5c-107">Try it!</span></span>

1. <span data-ttu-id="91d5c-108">從 Microsoft 365 系統管理中心，選取 [ **Exchange**，**郵件流程**]，然後在 [**規則**] 索引標籤上，選取加號，然後選擇 [**建立新規則**]。</span><span class="sxs-lookup"><span data-stu-id="91d5c-108">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="91d5c-109">選取 [ **更多選項**]。</span><span class="sxs-lookup"><span data-stu-id="91d5c-109">Select **More options**.</span></span> <span data-ttu-id="91d5c-110">為您的新規則命名。</span><span class="sxs-lookup"><span data-stu-id="91d5c-110">Name your new rule.</span></span>
1. <span data-ttu-id="91d5c-111">然後開啟下拉清單以套用 **此規則如果** 是，請選取 **寄件者**，然後 **是外部內部**。</span><span class="sxs-lookup"><span data-stu-id="91d5c-111">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="91d5c-112">選取 **組織內**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="91d5c-112">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="91d5c-113">選擇 [ **新增條件**]，開啟下拉式清單，選取 **郵件** 內容，然後 **加入郵件類型**。</span><span class="sxs-lookup"><span data-stu-id="91d5c-113">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="91d5c-114">開啟 [ **選取郵件類型** ] 下拉式清單，選擇 [ **自動轉寄**]，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="91d5c-114">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="91d5c-115">開啟 [ **執行下列** 下拉式清單]，選取 [ **封鎖郵件**]，然後 **拒絕郵件，並包含說明**。</span><span class="sxs-lookup"><span data-stu-id="91d5c-115">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="91d5c-116">輸入您的說明的訊息文字，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="91d5c-116">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="91d5c-117">向下並選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="91d5c-117">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="91d5c-118">您的規則已經建立，駭客也無法再自動轉寄郵件。</span><span class="sxs-lookup"><span data-stu-id="91d5c-118">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="91d5c-119">相關內容</span><span class="sxs-lookup"><span data-stu-id="91d5c-119">Related content</span></span>

<span data-ttu-id="91d5c-120">[為使用者新增其他電子郵件別名](../admin/email/add-another-email-alias-for-a-user.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="91d5c-120">[Add another email alias for a user](../admin/email/add-another-email-alias-for-a-user.md) (article)\</span></span>
<span data-ttu-id="91d5c-121">[在 Microsoft 365 中設定電子郵件轉寄](../admin/email/configure-email-forwarding.md) (文章)</span><span class="sxs-lookup"><span data-stu-id="91d5c-121">[Configure email forwarding in Microsoft 365](../admin/email/configure-email-forwarding.md) (article)\</span></span>
<span data-ttu-id="91d5c-122">[尋找並修正電子郵件傳遞問題，以 Office 365 商務系統管理員](/exchange/troubleshoot/email-delivery/email-delivery-issues) (文章) </span><span class="sxs-lookup"><span data-stu-id="91d5c-122">[Find and fix email delivery issues as an Office 365 for business admin](/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>