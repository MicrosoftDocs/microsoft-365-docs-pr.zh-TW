---
title: 在 Microsoft 365 的安全性中心分析使用者
description: 在 Microsoft 365 安全中心分析使用者
keywords: 安全性，惡意程式碼，Microsoft 365，M365，security center，monitor，report，identity，data，裝置，應用程式，事件，分析，回應
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 1fb5a4eee41384ef1afc9b46e5bf538344718fe9
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939727"
---
# <a name="analyze-users-in-microsoft-365-security-center"></a><span data-ttu-id="b652a-104">在 Microsoft 365 的安全性中心分析使用者</span><span class="sxs-lookup"><span data-stu-id="b652a-104">Analyze users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b652a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b652a-105">**Applies to:**</span></span>

- <span data-ttu-id="b652a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b652a-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b652a-107">您的部分事件分析可以包含使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b652a-107">Part of your incident analysis can include user accounts.</span></span> <span data-ttu-id="b652a-108">從事件的 [ **使用者** ] 索引標籤開始， **& 警示 >** *事件* **> 使用者**。</span><span class="sxs-lookup"><span data-stu-id="b652a-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="事件的使用者頁面範例":::

<span data-ttu-id="b652a-110">若要快速摘要瞭解事件的使用者帳戶，請選取使用者帳戶名稱旁邊的核取記號。</span><span class="sxs-lookup"><span data-stu-id="b652a-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="b652a-111">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="b652a-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 安全中心內事件之使用者帳戶摘要窗格的範例":::

<span data-ttu-id="b652a-113">您可以從這裡選取 [ **移至使用者] 頁面** ，以查看使用者帳戶的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b652a-113">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="b652a-114">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="b652a-114">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 安全中心內事件的使用者帳戶頁面範例":::

<span data-ttu-id="b652a-116">您也可以在 [ **使用者** ] 頁面上選取清單中的使用者帳戶名稱，以查看此頁面。</span><span class="sxs-lookup"><span data-stu-id="b652a-116">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="b652a-117">Microsoft 365 的「安全性中心」使用者頁面會結合 Microsoft Defender for Endpoint、Microsoft Defender 身分識別及 Microsoft Cloud App Security (的資訊，取決於您) 的授權。</span><span class="sxs-lookup"><span data-stu-id="b652a-117">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="b652a-118">此頁面顯示使用者帳戶安全風險的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="b652a-118">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="b652a-119">這包括協助評估風險及最近的事件，以及對使用者整體風險所帶來的警示。</span><span class="sxs-lookup"><span data-stu-id="b652a-119">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="b652a-120">您可以從這個頁面執行下列其他動作：</span><span class="sxs-lookup"><span data-stu-id="b652a-120">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="b652a-121">將使用者帳戶標示為已遭破壞</span><span class="sxs-lookup"><span data-stu-id="b652a-121">Mark the user account as compromised</span></span>
- <span data-ttu-id="b652a-122">需要使用者重新登入</span><span class="sxs-lookup"><span data-stu-id="b652a-122">Require the user to sign in again</span></span>
- <span data-ttu-id="b652a-123">暫停使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="b652a-123">Suspend the user account</span></span>
- <span data-ttu-id="b652a-124">請參閱 Azure Active Directory (Azure AD) 使用者帳戶設定</span><span class="sxs-lookup"><span data-stu-id="b652a-124">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="b652a-125">查看使用者帳戶所擁有的檔案</span><span class="sxs-lookup"><span data-stu-id="b652a-125">View the files owned by the user account</span></span>
- <span data-ttu-id="b652a-126">查看與此使用者共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="b652a-126">View files shared with this user.</span></span> 

<span data-ttu-id="b652a-127">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="b652a-127">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 安全性中心內事件之使用者帳戶的動作範例":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a><span data-ttu-id="b652a-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="b652a-129">Related topics</span></span>

- [<span data-ttu-id="b652a-130">事件概觀</span><span class="sxs-lookup"><span data-stu-id="b652a-130">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b652a-131">設定事件優先順序</span><span class="sxs-lookup"><span data-stu-id="b652a-131">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="b652a-132">管理事件</span><span class="sxs-lookup"><span data-stu-id="b652a-132">Manage incidents</span></span>](manage-incidents.md)