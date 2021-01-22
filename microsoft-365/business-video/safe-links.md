---
title: 管理安全連結
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
description: 瞭解如何管理安全連結以保護企業不受惡意網站攻擊。
ms.openlocfilehash: 1f5b3f61871e8d231029156631031dbb0ef4f2f5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928015"
---
# <a name="manage-safe-links"></a><span data-ttu-id="48f97-103">管理安全連結</span><span class="sxs-lookup"><span data-stu-id="48f97-103">Manage Safe Links</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

<span data-ttu-id="48f97-104">Microsoft Defender for Office 365 ， formerly called Microsoft 365 ATP， or Advanced Threat Protection， help protect your business against malicious sites when people click links in Office apps.</span><span class="sxs-lookup"><span data-stu-id="48f97-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against malicious sites when people click links in Office apps.</span></span>

## <a name="try-it"></a><span data-ttu-id="48f97-105">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="48f97-105">Try it!</span></span>

1. <span data-ttu-id="48f97-106">請前往系統 [管理中心，](https://admin.microsoft.com)**然後選取設定**。</span><span class="sxs-lookup"><span data-stu-id="48f97-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="48f97-107">向下卷卷 **來增加進一步威脅的保護**。</span><span class="sxs-lookup"><span data-stu-id="48f97-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="48f97-108">選取 **查看**、 **管理**，然後 **選取 ATP 安全連結**。</span><span class="sxs-lookup"><span data-stu-id="48f97-108">Select **View**, **Manage**,and then **ATP Safe Links**.</span></span>
1. <span data-ttu-id="48f97-109">在 **適用于整個組織的** 原則下，選擇 **預設原則，** 然後 **選取編輯圖示** 。</span><span class="sxs-lookup"><span data-stu-id="48f97-109">Under **Policies that apply to the entire organization**, choose the **Default** policy, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="48f97-110">輸入要封鎖的 URL。</span><span class="sxs-lookup"><span data-stu-id="48f97-110">Enter a URL that you want to block.</span></span>
1. <span data-ttu-id="48f97-111">選取 **在 Office 應用程式、iOS** 和 Android 版 Office 中使用安全連結;選取 **[不要追蹤使用者按一下安全連結時進行追蹤**;然後選取 **[不允許使用者按一下原始** URL 的安全連結。</span><span class="sxs-lookup"><span data-stu-id="48f97-111">Select **Use safe links in Office apps, Office for iOS and Android**; select **Do not track when users click safe links**; and select **Do not let users click through safe links to original URL**.</span></span> <span data-ttu-id="48f97-112">如果您設定預設策略，可能已經選取這些設定了。</span><span class="sxs-lookup"><span data-stu-id="48f97-112">These might already be selected if you set up the default policy.</span></span> <span data-ttu-id="48f97-113">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="48f97-113">Select **Save**.</span></span>
1. <span data-ttu-id="48f97-114">在 **適用于特定收件者的規則** 下，選擇建議 **的安全連結規則**，然後選取 **編輯** 圖示。</span><span class="sxs-lookup"><span data-stu-id="48f97-114">Under **Policies that apply to specific recipients**, choose **Recommended safe links rule**, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="48f97-115">選取 **設定**、向下標籤、輸入您不要檢查的 URL，然後選取 **新增圖示。**</span><span class="sxs-lookup"><span data-stu-id="48f97-115">Select **settings**, scroll down, enter the URL that you do not want to be checked, and then select the **Add** icon.</span></span>
1. <span data-ttu-id="48f97-116">選取 **已申請**，然後選取您的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="48f97-116">Select **applied to**, and then select your domain name.</span></span> <span data-ttu-id="48f97-117">選取您想要將規則應用至的其他網域。</span><span class="sxs-lookup"><span data-stu-id="48f97-117">Select any additional domains that you want the rule applied to.</span></span> <span data-ttu-id="48f97-118">選取 **新增**、**確定\*\*\*\*，然後** 儲存。</span><span class="sxs-lookup"><span data-stu-id="48f97-118">Select **add**, **OK**, and then **Save**.</span></span>

<span data-ttu-id="48f97-119">ATP 安全連結現在已進行設置。</span><span class="sxs-lookup"><span data-stu-id="48f97-119">ATP Safe Links are now configured.</span></span> <span data-ttu-id="48f97-120">請允許最多 30 分鐘，變更才能生效。</span><span class="sxs-lookup"><span data-stu-id="48f97-120">Allow up to 30 minutes for your changes to take effect.</span></span>

<span data-ttu-id="48f97-121">當使用者收到包含連結的電子郵件時，會掃描連結。</span><span class="sxs-lookup"><span data-stu-id="48f97-121">When a user receives an email with links, the links will be scanned.</span></span> <span data-ttu-id="48f97-122">如果連結是安全的，您可以按一下連結。</span><span class="sxs-lookup"><span data-stu-id="48f97-122">If the links are deemed safe, they'll be clickable.</span></span> <span data-ttu-id="48f97-123">不過，如果連結位於封鎖清單上，使用者會看到一則訊息，指出該連結已被封鎖。</span><span class="sxs-lookup"><span data-stu-id="48f97-123">However, if the link is on the blocked list, users will see a message that it's been blocked.</span></span>