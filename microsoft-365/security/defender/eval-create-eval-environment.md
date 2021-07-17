---
title: 建立 Microsoft 365 Defender 評估環境。 啟動或啟用試用授權，並繼續使用 Microsoft Defender for Identity (MDI) 。
description: 啟用試用授權以設定 Microsoft 365 Defender 試用實驗室或試驗環境。 然後，設定 Microsoft Defender 身分識別 (MDI) 和所有其他 M365D 評估。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 05/19/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: 04f7a746788ebcf67525020515cdc7bb20c41bb6
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457873"
---
# <a name="create-the-microsoft-365-defender-evaluation-environment"></a><span data-ttu-id="2fe38-105">建立 Microsoft 365 Defender 評估環境</span><span class="sxs-lookup"><span data-stu-id="2fe38-105">Create the Microsoft 365 Defender Evaluation Environment</span></span>

<span data-ttu-id="2fe38-106">在評估的下一個步驟中，有兩種常見的方式。</span><span class="sxs-lookup"><span data-stu-id="2fe38-106">There are two common ways to do this next step in evaluation.</span></span> <span data-ttu-id="2fe38-107">本檔假設您已有實際執行 M365 租使用者，並將啟動 E5 試用授權，以評估 *目前環境中的* M365 Defender。</span><span class="sxs-lookup"><span data-stu-id="2fe38-107">This document assumes you already have a production M365 tenant, and will activate E5 trial licenses to evaluate M365 Defender in *the current environment*.</span></span> <span data-ttu-id="2fe38-108">就地評估功能可讓您在評估期限過後，使用購買授權來保留任何安全性方法。</span><span class="sxs-lookup"><span data-stu-id="2fe38-108">An in-place evaluation will let you keep any security methods with the purchase of licenses after the evaluation period.</span></span>

<span data-ttu-id="2fe38-109">第二個是針對評估目的[設定 Microsoft 365 Defender 試用實驗室環境](setup-m365deval.md)。</span><span class="sxs-lookup"><span data-stu-id="2fe38-109">The second is to  [Set up your Microsoft 365 Defender trial lab environment](setup-m365deval.md) for the purpose of evaluation.</span></span> <span data-ttu-id="2fe38-110">它可能不會有許多來自公司的實際信號，因此請注意這一點。</span><span class="sxs-lookup"><span data-stu-id="2fe38-110">It may not have many real signals from the business, so be aware of that caveat.</span></span>

## <a name="to-activate-e5-trial-licenses-to-evaluate-microsoft-365-defender"></a><span data-ttu-id="2fe38-111">啟用 E5 試用授權以評估 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2fe38-111">To activate E5 trial licenses to evaluate Microsoft 365 Defender</span></span> 
1. <span data-ttu-id="2fe38-112">登入您現有的 M365 租使用者管理入口網站。</span><span class="sxs-lookup"><span data-stu-id="2fe38-112">Log on to your existing M365 tenant administration portal.</span></span>
2. <span data-ttu-id="2fe38-113">從流覽功能表中選取 [ *購買服務* ]。</span><span class="sxs-lookup"><span data-stu-id="2fe38-113">Select *Purchase Services* from the navigation menu.</span></span>
3. <span data-ttu-id="2fe38-114">向下滾動至 [ *Office 365* ] 區段，然後選取 [Office 365 E5 授權] 底下的 [詳細資料] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="2fe38-114">Scroll down to the *Office 365* section and select "Details" button under Office 365 E5 license.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Office 365 區段有一個按一下 [詳細資料] 按鈕。":::

4. <span data-ttu-id="2fe38-116">選取 [ *開始免費試用* ] 連結。</span><span class="sxs-lookup"><span data-stu-id="2fe38-116">Select *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="按一下「開始免費試用 ' ($35 費) 。":::

5. <span data-ttu-id="2fe38-118">確認您的要求，然後按一下 [ *立即試用* ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="2fe38-118">Confirm your request and click *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="在「請參閱，請 buttong，確認您的訂單」 (面板中有一個「Try Now」，以供25位使用者) 的月 Office 365 E5 試用版使用。":::

## <a name="next-steps"></a><span data-ttu-id="2fe38-120">後續步驟</span><span class="sxs-lookup"><span data-stu-id="2fe38-120">Next steps</span></span>
[<span data-ttu-id="2fe38-121">啟用身分識別的 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2fe38-121">Enable Microsoft 365 for Identity</span></span>](eval-defender-identity-overview.md)

<span data-ttu-id="2fe38-122">回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述</span><span class="sxs-lookup"><span data-stu-id="2fe38-122">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>