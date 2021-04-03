---
title: 建立全公司的簽章
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: 瞭解如何建立全公司的電子郵件簽名。
ms.openlocfilehash: a1a85826be2a799b56cf3d06b6416778470a116f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578948"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="cc236-103">建立全公司的電子郵件簽名</span><span class="sxs-lookup"><span data-stu-id="cc236-103">Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="cc236-104">全公司的電子郵件簽章會出現在組織中人員所傳送的每封電子郵件上。</span><span class="sxs-lookup"><span data-stu-id="cc236-104">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="cc236-105">您可以使用它來顯示重要的詳細資料，如公司連絡人資訊或法律免責聲明。</span><span class="sxs-lookup"><span data-stu-id="cc236-105">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="cc236-106">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="cc236-106">Try it!</span></span>

1. <span data-ttu-id="cc236-107">在 Microsoft 365 admin center 中，選取 [ **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="cc236-107">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="cc236-108">選取 [ **郵件流程**]。</span><span class="sxs-lookup"><span data-stu-id="cc236-108">Select **Mail flow**.</span></span>
1. <span data-ttu-id="cc236-109">選取 [ **新增 +**]，然後選取 [套用 **免責聲明**]。</span><span class="sxs-lookup"><span data-stu-id="cc236-109">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="cc236-110">在 [ **新增規則** ] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="cc236-110">On the **New rule** page:</span></span>
    1. <span data-ttu-id="cc236-111">輸入規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="cc236-111">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="cc236-112">從 [套用 **此規則的原則** ] 下拉式清單中，選取 [套用 **到所有郵件**]。</span><span class="sxs-lookup"><span data-stu-id="cc236-112">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="cc236-113">在 [ **執行下列** 下拉式清單] 中，確認 [ **附加免責聲明** ] 顯示。</span><span class="sxs-lookup"><span data-stu-id="cc236-113">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="cc236-114">在頁面右側，選取 [ **輸入文字**]，然後在 [ **指定免責聲明** ] 文字方塊中輸入您的電子郵件簽名文字。</span><span class="sxs-lookup"><span data-stu-id="cc236-114">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="cc236-115">您可以使用 HTML 格式化文字，以改善簽章的外觀。</span><span class="sxs-lookup"><span data-stu-id="cc236-115">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="cc236-116">如果您想要在您的簽章中顯示影像，您必須為該圖像使用公開可用的 URL。</span><span class="sxs-lookup"><span data-stu-id="cc236-116">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="cc236-117">流覽至網頁上的圖像，以滑鼠右鍵按一下，然後選取 [ **複製圖像位址**]。</span><span class="sxs-lookup"><span data-stu-id="cc236-117">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="cc236-118">在 [ **指定免責聲明** ] 文字方塊中貼上位址。</span><span class="sxs-lookup"><span data-stu-id="cc236-118">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="cc236-119">選取 **[確定]**，然後向下滾動。</span><span class="sxs-lookup"><span data-stu-id="cc236-119">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="cc236-120">若要確定簽章是否使用加密的電子郵件，請新增「回退」選項。</span><span class="sxs-lookup"><span data-stu-id="cc236-120">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="cc236-121">在頁面右側，選擇 [ **選取其中一項**]，選擇 [ **環繞**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="cc236-121">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="cc236-122">向下滾動並保持模式設定為 [ **強制執行**]，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="cc236-122">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="cc236-123">隨即會顯示警告訊息。</span><span class="sxs-lookup"><span data-stu-id="cc236-123">A warning message will appear.</span></span> <span data-ttu-id="cc236-124">選取 **[是]** ，將規則套用至所有未來郵件。</span><span class="sxs-lookup"><span data-stu-id="cc236-124">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="cc236-125">已建立您的簽名。</span><span class="sxs-lookup"><span data-stu-id="cc236-125">Your signature has been created.</span></span> <span data-ttu-id="cc236-126">當您傳送下一個電子郵件時，您將看不到您剛剛建立的簽章，但是電子郵件收件者會看到該簽章。</span><span class="sxs-lookup"><span data-stu-id="cc236-126">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>