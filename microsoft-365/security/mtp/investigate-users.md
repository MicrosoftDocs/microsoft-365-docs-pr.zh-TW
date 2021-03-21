---
title: 在 Microsoft 365 安全性中心調查使用者
description: 調查 Microsoft 365 security center 中的使用者
keywords: 安全性，惡意程式碼，Microsoft 365，M365，security center，monitor，report，identity，data，裝置，應用程式
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 32c496a212e038d649fdc9880c8ac829ee4a5337
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927228"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="ab587-104">在 Microsoft 365 安全性中心調查使用者</span><span class="sxs-lookup"><span data-stu-id="ab587-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="ab587-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="ab587-105">**Applies to:**</span></span>

- <span data-ttu-id="ab587-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ab587-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ab587-107">在調查過程中，您可能會發現使用者已遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="ab587-107">As part of your investigation, you might find that a user has been compromised.</span></span>

<span data-ttu-id="ab587-108">Microsoft 365 的「安全性中心」使用者頁面會結合 Microsoft Defender for Endpoint、Microsoft Defender 身分識別及 Microsoft Cloud App Security (的資訊，取決於您) 的授權。</span><span class="sxs-lookup"><span data-stu-id="ab587-108">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> <span data-ttu-id="ab587-109">此頁面是調查使用者和潛在事件的理想開始位置。</span><span class="sxs-lookup"><span data-stu-id="ab587-109">This page is the ideal starting place for investigating users and potential incidents.</span></span>
<span data-ttu-id="ab587-110">![使用者頁面](../../media/m3d-userpage.png)</span><span class="sxs-lookup"><span data-stu-id="ab587-110">![User page](../../media/m3d-userpage.png)</span></span>

<span data-ttu-id="ab587-111">此頁面顯示使用者安全性風險的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="ab587-111">This page shows information specific to the security risk of a user.</span></span> <span data-ttu-id="ab587-112">這包括有助於評估風險的分數、最近的事件及警示，也就是對使用者整體風險的貢獻等等。</span><span class="sxs-lookup"><span data-stu-id="ab587-112">This includes a score that helps assess risk, recent events and alerts that contributed to the overall risk of the user, and more.</span></span>

<span data-ttu-id="ab587-113">您可以從 Microsoft 365 安全性中心的多個區域存取此頁面。</span><span class="sxs-lookup"><span data-stu-id="ab587-113">You can access this page from multiple areas in the Microsoft 365 security center.</span></span> <span data-ttu-id="ab587-114">您可以從 [ **使用者** ] 索引標籤中的特定事件存取此頁面。有些警示可能包含使用者為特定的受影響資產。</span><span class="sxs-lookup"><span data-stu-id="ab587-114">You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset.</span></span> <span data-ttu-id="ab587-115">您也可以搜尋使用者。</span><span class="sxs-lookup"><span data-stu-id="ab587-115">You can also search for users.</span></span>  

<span data-ttu-id="ab587-116">深入瞭解如何 [在此 Cloud App Security 教學課程中](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them)調查使用者和潛在風險。</span><span class="sxs-lookup"><span data-stu-id="ab587-116">Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ab587-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="ab587-117">Related topics</span></span>

- [<span data-ttu-id="ab587-118">事件概觀</span><span class="sxs-lookup"><span data-stu-id="ab587-118">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="ab587-119">設定事件優先順序</span><span class="sxs-lookup"><span data-stu-id="ab587-119">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="ab587-120">管理事件</span><span class="sxs-lookup"><span data-stu-id="ab587-120">Manage incidents</span></span>](manage-incidents.md)