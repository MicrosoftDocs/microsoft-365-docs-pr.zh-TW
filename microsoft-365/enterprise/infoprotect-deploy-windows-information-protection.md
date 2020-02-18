---
title: 步驟 4： 設定 Windows 資訊保護
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Microsoft 365 中的 Windows 資訊保護並且進行部署。
ms.openlocfilehash: 655ff33c3fd1bba822937618d801db76b7881977
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067160"
---
# <a name="step-4-configure-windows-information-protection"></a><span data-ttu-id="6f018-103">步驟 4： 設定 Windows 資訊保護</span><span class="sxs-lookup"><span data-stu-id="6f018-103">Step 4: Configure Windows Information Protection</span></span>

<span data-ttu-id="6f018-104">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="6f018-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![階段 6：資訊保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="6f018-106">當更多的個人裝置用於工作時，應用程式和裝置外洩組織私密資料的風險就會增加。</span><span class="sxs-lookup"><span data-stu-id="6f018-106">With more personal devices being used for work, there’s increased risk for apps and devices to leak private organization data.</span></span> <span data-ttu-id="6f018-107">例如，有員工不經意地將未來產品行銷計劃的圖片傳送到社交媒體網站，或者將包含高度機密資訊的檔案儲存到他們的公用雲端儲存區。</span><span class="sxs-lookup"><span data-stu-id="6f018-107">For example, an employee inadvertently sends a picture of a marketing plan for a future product to a social media site or saves a file containing highly confidential information to their public cloud storage.</span></span> 

<span data-ttu-id="6f018-108">Windows 資訊保護 (WIP) 可協助保護 Windows 10 裝置上的此類資料外洩。</span><span class="sxs-lookup"><span data-stu-id="6f018-108">Windows Information Protection (WIP) helps protect against these types of data leakage on Windows 10 devices.</span></span> <span data-ttu-id="6f018-109">如需詳細資訊，請參閱[使用 WIP 保護您的企業資料](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)</span><span class="sxs-lookup"><span data-stu-id="6f018-109">For more information, see [Protect your enterprise data using WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span>

<span data-ttu-id="6f018-110">在 Microsoft 365 企業版中，WIP 是 Windows 10 企業版和 Microsoft Intune 的組合，隨附於您的訂閱。</span><span class="sxs-lookup"><span data-stu-id="6f018-110">In Microsoft 365 Enterprise, WIP is a combination of Windows 10 Enterprise and Microsoft Intune, which is included with your subscription.</span></span> 

<span data-ttu-id="6f018-111">若要在貴組織中使用 Microsoft 365 企業版部署 WIP：</span><span class="sxs-lookup"><span data-stu-id="6f018-111">To deploy WIP in your organization with Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="6f018-112">在 Intune 中註冊您的 Windows 裝置。</span><span class="sxs-lookup"><span data-stu-id="6f018-112">Enroll your Windows devices in Intune.</span></span> <span data-ttu-id="6f018-113">您應該在[階段 5：行動裝置管理](mobility-infrastructure.md)中完成這項作業。</span><span class="sxs-lookup"><span data-stu-id="6f018-113">You should have done this in [Phase 5: Mobile Device Management](mobility-infrastructure.md).</span></span>
2. <span data-ttu-id="6f018-114">建立[適用於 WIP 的 Intune 原則](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)</span><span class="sxs-lookup"><span data-stu-id="6f018-114">Create an [Intune policy for WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).</span></span>
  - <span data-ttu-id="6f018-115">請確定您已填寫受保護的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="6f018-115">Ensure that you have filled out your Protected apps list.</span></span>
  - <span data-ttu-id="6f018-116">選擇您的 WIP 保護等級。</span><span class="sxs-lookup"><span data-stu-id="6f018-116">Choose your WIP protection level.</span></span>

<span data-ttu-id="6f018-117">您也可以搭配使用 WIP 和 [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm)。</span><span class="sxs-lookup"><span data-stu-id="6f018-117">You can also use WIP with [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm).</span></span> 

<span data-ttu-id="6f018-118">如需詳細資訊，請參閱 [WIP 最佳做法]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip)</span><span class="sxs-lookup"><span data-stu-id="6f018-118">See [WIP best practices]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) for more information.</span></span>

<span data-ttu-id="6f018-119">作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step4)。</span><span class="sxs-lookup"><span data-stu-id="6f018-119">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step4) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="6f018-120">下一步</span><span class="sxs-lookup"><span data-stu-id="6f018-120">Next step</span></span>

|||
|:-------|:-----|
|![步驟 5](../media/stepnumbers/Step5.png)|[<span data-ttu-id="6f018-122">設定 Office 365 資料外洩防護</span><span class="sxs-lookup"><span data-stu-id="6f018-122">Configure Office 365 Data Loss Prevention</span></span>](infoprotect-data-loss-prevention.md)|


