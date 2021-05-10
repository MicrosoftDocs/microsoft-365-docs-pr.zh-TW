---
title: 在 Microsoft 365 安全性中心調查使用者
description: 調查 Microsoft 365 security center 中的使用者
keywords: security，malware，Microsoft 365，M365，security center，monitor，report，identity，data，裝置，應用程式，事件，分析，回應
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
ms.openlocfilehash: c03e4d5bd94eb6105ffab91c6dad2b74d7159dde
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300058"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a><span data-ttu-id="38160-104">在 Microsoft 365 安全性中心調查使用者</span><span class="sxs-lookup"><span data-stu-id="38160-104">Investigate users in Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="38160-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="38160-105">**Applies to:**</span></span>

- <span data-ttu-id="38160-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38160-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="38160-107">您的一部分事件調查可以包含使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="38160-107">Part of your incident investigation can include user accounts.</span></span> <span data-ttu-id="38160-108">從事件的 [ **使用者** ] 索引標籤開始， **& 警示 >** *事件* **> 使用者**。</span><span class="sxs-lookup"><span data-stu-id="38160-108">Start with the **Users** tab for an incident from **Incidents & alerts >** *incident* **> Users**.</span></span> 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="事件的使用者頁面範例":::

<span data-ttu-id="38160-110">若要快速摘要瞭解事件的使用者帳戶，請選取使用者帳戶名稱旁邊的核取記號。</span><span class="sxs-lookup"><span data-stu-id="38160-110">To get a quick summary of a user account for the incident, select the check mark next to the user account name.</span></span> <span data-ttu-id="38160-111">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="38160-111">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Microsoft 365 security center 中事件之使用者帳戶摘要窗格的範例":::

> [!NOTE]
> <span data-ttu-id="38160-113">[使用者] 頁面會顯示 Azure Active Directory (AD) 組織和群組，協助您瞭解與使用者相關聯的群組和許可權。</span><span class="sxs-lookup"><span data-stu-id="38160-113">The User page shows Azure Active Directory (AD) organization as well as groups, helping you understand the groups and permissions associated with a user.</span></span>

<span data-ttu-id="38160-114">在此 [飛出] 頁面中，您可以查看使用者威脅資訊，包括任何目前的事件、作用中的警示、風險層級，以及使用者曝光、帳戶、裝置等等。</span><span class="sxs-lookup"><span data-stu-id="38160-114">In this fly-out page, you can review user threat information, including any current incidents, active alerts, and risk level as well as user exposure, accounts, devices, and more.</span></span>

<span data-ttu-id="38160-115">此外，您可以直接在 Microsoft 365 的安全性中心採取行動，以處理已遭破壞的使用者，確認使用者已遭到破壞或要求他們重新登入。</span><span class="sxs-lookup"><span data-stu-id="38160-115">In addition, you can take action directly in the Microsoft 365 security center to address a compromised user, confirming the user is compromised or requiring them to sign in again.</span></span>

<span data-ttu-id="38160-116">您可以從這裡選取 [ **移至使用者] 頁面** ，以查看使用者帳戶的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="38160-116">From here, you can select **Go to user page** to see the details of a user account.</span></span> <span data-ttu-id="38160-117">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="38160-117">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Microsoft 365 security center 中事件的使用者帳戶頁面範例":::

<span data-ttu-id="38160-119">您也可以在 [ **使用者** ] 頁面上選取清單中的使用者帳戶名稱，以查看此頁面。</span><span class="sxs-lookup"><span data-stu-id="38160-119">You can also see this page by selecting the name of the user account from the list on the **Users** page.</span></span>

<span data-ttu-id="38160-120">Microsoft 365 的安全性中心使用者頁面會結合 microsoft defender for Endpoint、microsoft defender 身分識別及 Microsoft Cloud App Security (的資訊，視您擁有) 的授權而定。</span><span class="sxs-lookup"><span data-stu-id="38160-120">The Microsoft 365 security center user page combines information from Microsoft Defender for Endpoint, Microsoft Defender for Identity, and Microsoft Cloud App Security (depending on what licenses you have).</span></span> 

<span data-ttu-id="38160-121">此頁面顯示使用者帳戶安全風險的特定資訊。</span><span class="sxs-lookup"><span data-stu-id="38160-121">This page shows information specific to the security risk of a user account.</span></span> <span data-ttu-id="38160-122">這包括協助評估風險及最近的事件，以及對使用者整體風險所帶來的警示。</span><span class="sxs-lookup"><span data-stu-id="38160-122">This includes a score that helps assess risk and recent events and alerts that contributed to the overall risk of the user.</span></span>

<span data-ttu-id="38160-123">您可以從這個頁面執行下列其他動作：</span><span class="sxs-lookup"><span data-stu-id="38160-123">From this page, you can do these additional actions:</span></span> 

- <span data-ttu-id="38160-124">將使用者帳戶標示為已遭破壞</span><span class="sxs-lookup"><span data-stu-id="38160-124">Mark the user account as compromised</span></span>
- <span data-ttu-id="38160-125">需要使用者重新登入</span><span class="sxs-lookup"><span data-stu-id="38160-125">Require the user to sign in again</span></span>
- <span data-ttu-id="38160-126">暫停使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="38160-126">Suspend the user account</span></span>
- <span data-ttu-id="38160-127">請參閱 Azure Active Directory (Azure AD) 使用者帳戶設定</span><span class="sxs-lookup"><span data-stu-id="38160-127">See the Azure Active Directory (Azure AD) user account settings</span></span>
- <span data-ttu-id="38160-128">查看使用者帳戶所擁有的檔案</span><span class="sxs-lookup"><span data-stu-id="38160-128">View the files owned by the user account</span></span>
- <span data-ttu-id="38160-129">查看與此使用者共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="38160-129">View files shared with this user.</span></span> 

<span data-ttu-id="38160-130">以下為範例。</span><span class="sxs-lookup"><span data-stu-id="38160-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 security center 中的事件之使用者帳戶的動作範例":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a><span data-ttu-id="38160-132">後續步驟</span><span class="sxs-lookup"><span data-stu-id="38160-132">Next steps</span></span>

<span data-ttu-id="38160-133">視需要進行處理內事件，繼續進行 [調查](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="38160-133">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="38160-134">請參閱</span><span class="sxs-lookup"><span data-stu-id="38160-134">See also</span></span>

- [<span data-ttu-id="38160-135">事件概觀</span><span class="sxs-lookup"><span data-stu-id="38160-135">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="38160-136">設定事件優先順序</span><span class="sxs-lookup"><span data-stu-id="38160-136">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="38160-137">管理事件</span><span class="sxs-lookup"><span data-stu-id="38160-137">Manage incidents</span></span>](manage-incidents.md)