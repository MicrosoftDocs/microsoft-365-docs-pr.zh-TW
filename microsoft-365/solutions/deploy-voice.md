---
title: 在 Microsoft 365 中部署語音
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-voice
- M365-voice
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: 瞭解如何為您的組織選擇及部署正確的小組語音解決方案。
ms.openlocfilehash: b5dda0ed3d9310c3c43052b9bac4996802e0ed2f
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580890"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="4c5cf-103">規劃及部署小組語音解決方案</span><span class="sxs-lookup"><span data-stu-id="4c5cf-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="4c5cf-104">小組語音方案可讓您組織中的人員撥打組織內部和外部的電話。</span><span class="sxs-lookup"><span data-stu-id="4c5cf-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="4c5cf-105">完整的語音解決方案是由小組、Microsoft 電話系統和選項群組成，可供您選擇用來連接到公用交換電話網路 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="4c5cf-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![團隊語音方案概述](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="4c5cf-107">電話系統為您的組織提供完整的私人分支 Exchange (PBX) 功能。</span><span class="sxs-lookup"><span data-stu-id="4c5cf-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="4c5cf-108">您組織中的使用者之間的呼叫（不論其地理位置為何），都是在電話系統內部進行處理，因此會在這些內部通話中移除長途成本。</span><span class="sxs-lookup"><span data-stu-id="4c5cf-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="4c5cf-109">將電話系統連線到公用交換電話網路 (PSTN) 後，您的小組使用者也可以撥打組織外部通話。</span><span class="sxs-lookup"><span data-stu-id="4c5cf-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="4c5cf-110">此方案指南可協助您：</span><span class="sxs-lookup"><span data-stu-id="4c5cf-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="4c5cf-111">選擇適合貴組織的語音解決方案</span><span class="sxs-lookup"><span data-stu-id="4c5cf-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="4c5cf-112">部署您選取的語音解決方案</span><span class="sxs-lookup"><span data-stu-id="4c5cf-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="4c5cf-113">請遵循下列步驟來選擇、規劃及設定語音方案：</span><span class="sxs-lookup"><span data-stu-id="4c5cf-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![選擇您的語音解決方案](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="4c5cf-115">選擇您的語音解決方案</span><span class="sxs-lookup"><span data-stu-id="4c5cf-115">Choose your voice solution</span></span>](https://docs.microsoft.com/MicrosoftTeams/cloud-voice-landing-page?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

2. [<span data-ttu-id="4c5cf-116">設定電話系統</span><span class="sxs-lookup"><span data-stu-id="4c5cf-116">Set up Phone System</span></span>](https://docs.microsoft.com/microsoftteams/setting-up-your-phone-system?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

3. <span data-ttu-id="4c5cf-117">透過選擇下列其中一項或其組合，設定 PSTN 連線：</span><span class="sxs-lookup"><span data-stu-id="4c5cf-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="4c5cf-118">[呼叫方案](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) -microsoft 的所有雲端解決方案，使用 MICROSOFT 作為 PSTN 載體</span><span class="sxs-lookup"><span data-stu-id="4c5cf-118">[Calling Plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="4c5cf-119">[直接路由](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) -使用直接路由將您自己的 PSTN 電信公司連接至小組</span><span class="sxs-lookup"><span data-stu-id="4c5cf-119">[Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="4c5cf-120">此外，您可能會想要瞭解如何將大型的多國公司遷移至 [Contoso 案例研究](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)中的「小組語音方案」。</span><span class="sxs-lookup"><span data-stu-id="4c5cf-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span></span>

<span data-ttu-id="4c5cf-121">如需必要授權的相關資訊，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="4c5cf-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="4c5cf-122">小組附加元件授權</span><span class="sxs-lookup"><span data-stu-id="4c5cf-122">Teams add-on licenses</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

- [<span data-ttu-id="4c5cf-123">直接路由授權需求</span><span class="sxs-lookup"><span data-stu-id="4c5cf-123">Direct Routing licensing requirements</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)
