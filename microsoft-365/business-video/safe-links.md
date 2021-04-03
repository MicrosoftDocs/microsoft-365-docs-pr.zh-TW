---
title: 管理安全連結
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
description: 瞭解如何管理安全連結，以保護您的公司免受惡意網站的攻擊。
ms.openlocfilehash: ce0c1ba6e4099b6eaf4ec974938170020b8a5892
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580627"
---
# <a name="manage-safe-links"></a><span data-ttu-id="63d99-103">管理安全連結</span><span class="sxs-lookup"><span data-stu-id="63d99-103">Manage Safe Links</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

<span data-ttu-id="63d99-104">Microsoft Defender for Office 365 （以前稱為 Microsoft 365 ATP 或「高級威脅防護」）可協助您在使用者按一下 Office app 中的連結時，防範惡意網站。</span><span class="sxs-lookup"><span data-stu-id="63d99-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against malicious sites when people click links in Office apps.</span></span>

## <a name="try-it"></a><span data-ttu-id="63d99-105">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="63d99-105">Try it!</span></span>

1. <span data-ttu-id="63d99-106">移至 [系統 [管理中心](https://admin.microsoft.com)]，然後選取 [ **安裝**]。</span><span class="sxs-lookup"><span data-stu-id="63d99-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="63d99-107">向右下展開以 **提升高級威脅的防護**。</span><span class="sxs-lookup"><span data-stu-id="63d99-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="63d99-108">選取 [ **View**， **Manage**，然後 **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="63d99-108">Select **View**, **Manage**,and then **ATP Safe Links**.</span></span>
1. <span data-ttu-id="63d99-109">在 [ **適用于整個組織的原則**] 底下，選擇 [ **預設** 原則]，然後選取 [ **編輯** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="63d99-109">Under **Policies that apply to the entire organization**, choose the **Default** policy, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="63d99-110">輸入您要封鎖的 URL。</span><span class="sxs-lookup"><span data-stu-id="63d99-110">Enter a URL that you want to block.</span></span>
1. <span data-ttu-id="63d99-111">選取 [ **使用 office 應用程式、office for iOS 和 Android 中的安全連結**];選取 [ **當使用者按一下安全連結時請勿追蹤**]，並選取 [ **不要讓使用者按一下 [安全連結至原始 URL**]。</span><span class="sxs-lookup"><span data-stu-id="63d99-111">Select **Use safe links in Office apps, Office for iOS and Android**; select **Do not track when users click safe links**; and select **Do not let users click through safe links to original URL**.</span></span> <span data-ttu-id="63d99-112">如果您設定預設原則，這些可能已經被選取。</span><span class="sxs-lookup"><span data-stu-id="63d99-112">These might already be selected if you set up the default policy.</span></span> <span data-ttu-id="63d99-113">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="63d99-113">Select **Save**.</span></span>
1. <span data-ttu-id="63d99-114">在 [套用至特定收件者 **的原則**] 底下，選擇 [ **建議的安全連結規則**]，然後選取 [ **編輯** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="63d99-114">Under **Policies that apply to specific recipients**, choose **Recommended safe links rule**, and then select the **Edit** icon.</span></span>
1. <span data-ttu-id="63d99-115">選取 [ **設定**]，向下移動，輸入您不想要檢查的 URL，然後選取 [ **新增** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="63d99-115">Select **settings**, scroll down, enter the URL that you do not want to be checked, and then select the **Add** icon.</span></span>
1. <span data-ttu-id="63d99-116">選取 [套用 **于**]，然後選取您的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="63d99-116">Select **applied to**, and then select your domain name.</span></span> <span data-ttu-id="63d99-117">選取您要套用規則的任何其他網域。</span><span class="sxs-lookup"><span data-stu-id="63d99-117">Select any additional domains that you want the rule applied to.</span></span> <span data-ttu-id="63d99-118">選取[新增 **]、[確定]**，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="63d99-118">Select **add**, **OK**, and then **Save**.</span></span>

<span data-ttu-id="63d99-119">現在已設定 ATP 安全連結。</span><span class="sxs-lookup"><span data-stu-id="63d99-119">ATP Safe Links are now configured.</span></span> <span data-ttu-id="63d99-120">允許最多30分鐘的變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="63d99-120">Allow up to 30 minutes for your changes to take effect.</span></span>

<span data-ttu-id="63d99-121">當使用者收到具有連結的電子郵件時，將會掃描連結。</span><span class="sxs-lookup"><span data-stu-id="63d99-121">When a user receives an email with links, the links will be scanned.</span></span> <span data-ttu-id="63d99-122">如果連結是安全的，它們會是可按一下的。</span><span class="sxs-lookup"><span data-stu-id="63d99-122">If the links are deemed safe, they'll be clickable.</span></span> <span data-ttu-id="63d99-123">不過，如果連結位於封鎖的清單中，使用者就會看到已封鎖的郵件。</span><span class="sxs-lookup"><span data-stu-id="63d99-123">However, if the link is on the blocked list, users will see a message that it's been blocked.</span></span>