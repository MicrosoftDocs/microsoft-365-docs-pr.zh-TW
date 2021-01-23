---
title: 防止資料外洩
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
description: 瞭解如何管理設定資料遺失防護原則。
ms.openlocfilehash: e963cf85fee887b6e91c6e54b00aaa9e5174e3b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927955"
---
# <a name="prevent-data-loss-with-dlp"></a><span data-ttu-id="0d9f0-103">使用 DLP 防止資料遺失</span><span class="sxs-lookup"><span data-stu-id="0d9f0-103">Prevent data loss with DLP</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

<span data-ttu-id="0d9f0-104">資料遺失防護原則可協助識別及保護您公司的機密資訊，例如社會安全號碼或醫療記錄。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-104">Data loss prevention policies help identify and protect your business's sensitive information, such as Social Security numbers or medical records.</span></span> 

## <a name="try-it"></a><span data-ttu-id="0d9f0-105">試試看吧！</span><span class="sxs-lookup"><span data-stu-id="0d9f0-105">Try it!</span></span>

1. <span data-ttu-id="0d9f0-106">若要開始，請移至系統 [管理中心](https://admin.microsoft.com)，然後選取 [ **安裝**]。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-106">To get started, go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="0d9f0-107">向下滾動以 **設定資料遺失防護**，然後選取 [ **查看**]，然後再進行 **管理**。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-107">Scroll down to **Set up data loss prevention**, and then select **View**, and then **Manage**.</span></span>
1. <span data-ttu-id="0d9f0-108">若要編輯原則，請選取它，然後選擇 [ **編輯原則**]，然後選取要變更的專案。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-108">To edit a policy, select it, choose **Edit policy**, then select what to change.</span></span> <span data-ttu-id="0d9f0-109">例如，選取 [變更掃描的 **位置** ]。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-109">For example, select **Locations** to change what gets scanned.</span></span>
1. <span data-ttu-id="0d9f0-110">若要啟用對 Microsoft 團隊內容的掃描，請開啟切換切換到 [ **開啟** ] 位置，然後選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-110">To enable scanning for content in Microsoft Teams, turn the toggle switch to the **On** position, and then select **Save**.</span></span>
1. <span data-ttu-id="0d9f0-111">若要編輯原則設定，請選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-111">To edit policy settings, select **Edit**.</span></span>
1. <span data-ttu-id="0d9f0-112">您必須設定個別的規則，套用至偵測到的少量機密內容。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-112">You'll need to set separate rules that apply to small and large amounts of sensitive content detected.</span></span> <span data-ttu-id="0d9f0-113">擴充低音量規則。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-113">Expand your low volume rule.</span></span> <span data-ttu-id="0d9f0-114">選擇 [ **編輯規則**]。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-114">Choose **Edit rule**.</span></span>
1. <span data-ttu-id="0d9f0-115">請複查您的設定，並視需要加以調整。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-115">Review your settings and adjust them as needed.</span></span> <span data-ttu-id="0d9f0-116">例如，您可以選擇 **自訂電子郵件文字** 和 **自訂原則提示文字**。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-116">For example, you can choose to **Customize the email text** and **Customize the policy tip text**.</span></span> <span data-ttu-id="0d9f0-117">選取 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-117">Select **Save**.</span></span>
1. <span data-ttu-id="0d9f0-118">針對高容量規則重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-118">Repeat for the high volume rule.</span></span> <span data-ttu-id="0d9f0-119">選取 [ **儲存**]，然後 **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-119">Select **Save**, and then **Close**.</span></span>
1. <span data-ttu-id="0d9f0-120">若要建立新原則，請選取 [ **建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-120">To create a new policy, select **Create a policy**.</span></span>
1. <span data-ttu-id="0d9f0-121">您可以建立自訂原則或從範本開始。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-121">You can create a custom policy or start with a template.</span></span> <span data-ttu-id="0d9f0-122">例如，若要建立 HIPAA 原則，請選取 [ **醫學與健康** 情況範本]，然後選取 [ **美國健康情況保險業法案 (HIPAA])**。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-122">For example, to create a HIPAA policy, select the **Medical and health** template, and then select **U.S. Health Insurance Act (HIPAA)**.</span></span> <span data-ttu-id="0d9f0-123">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-123">Select **Next**.</span></span>
1. <span data-ttu-id="0d9f0-124">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-124">Enter a name and description for your policy.</span></span> <span data-ttu-id="0d9f0-125">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-125">Select **Next**.</span></span>
1. <span data-ttu-id="0d9f0-126">選擇要掃描的位置。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-126">Choose the locations to scan.</span></span> <span data-ttu-id="0d9f0-127">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-127">Select **Next**.</span></span>
1. <span data-ttu-id="0d9f0-128">選擇您要保護的內容類型。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-128">Choose the type of content you want protected.</span></span> <span data-ttu-id="0d9f0-129">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-129">Select **Next**.</span></span>
1. <span data-ttu-id="0d9f0-130">選擇偵測到敏感資訊時所要執行的動作。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-130">Choose what you want to happen if sensitive information is detected.</span></span> <span data-ttu-id="0d9f0-131">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-131">Select **Next**.</span></span>
1. <span data-ttu-id="0d9f0-132">自訂您的存取權和覆寫許可權。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-132">Customize your access and override permissions.</span></span> <span data-ttu-id="0d9f0-133">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-133">Select **Next**.</span></span>
1. <span data-ttu-id="0d9f0-134">選擇您想要原則生效的時間。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-134">Choose when you want the policy to take effect.</span></span> <span data-ttu-id="0d9f0-135">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-135">Select **Next**.</span></span>
1. <span data-ttu-id="0d9f0-136">請複查您的設定，然後選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-136">Review your settings, and select **Create**.</span></span> <span data-ttu-id="0d9f0-137">當原則生效後，包含所述敏感資訊的電子郵件將會遭到封鎖，而且嘗試傳送該資訊的寄件者會看到警告訊息。</span><span class="sxs-lookup"><span data-stu-id="0d9f0-137">After your policy takes effect, email that contains the described sensitive information will be blocked, and the sender who attempted to send that information will see a warning message.</span></span>