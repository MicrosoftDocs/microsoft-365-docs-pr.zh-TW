---
title: 設定 Microsoft 365 中的 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 本文說明如何設定 Advanced eDiscovery，讓您可以開始建立及管理案例。 此外，它也會說明必要的 Microsoft 訂閱和授權。 完成一些快速步驟之後，Advanced eDiscovery 工具便可供使用。
ms.openlocfilehash: 6c6aed482da8f203154d94313ec04519d6a330ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919741"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="06d3d-105">設定 Microsoft 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="06d3d-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="06d3d-106">Microsoft 365 中 Advanced eDiscovery 提供的端對端工作流程，可保留、收集、審閱、分析及匯出回應組織內部和外部調查的資料。</span><span class="sxs-lookup"><span data-stu-id="06d3d-106">Advanced eDiscovery in Microsoft 365 provides an end-to-end workflow to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="06d3d-107">不需要部署 Advanced eDiscovery，但是必須先執行一些必要的工作，IT 系統管理員和 eDiscovery 管理員才能開始建立並使用 Advanced eDiscovery 案例來管理調查。</span><span class="sxs-lookup"><span data-stu-id="06d3d-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="06d3d-108">本文討論設定 Advanced eDiscovery 所需的下列步驟。</span><span class="sxs-lookup"><span data-stu-id="06d3d-108">This article discusses the following steps necessary to set up Advanced eDiscovery.</span></span>

![設定 Advanced eDiscovery 的步驟](../media/set-up-advanced-ediscovery.png)

<span data-ttu-id="06d3d-110">這包括確保存取 Advanced eDiscovery 和將保管人新增至案例，以及將許可權指派給法律和調查小組所需的適當授權，以便他們可以存取和管理案例。</span><span class="sxs-lookup"><span data-stu-id="06d3d-110">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="06d3d-111">步驟1：確認並指派適當的授權</span><span class="sxs-lookup"><span data-stu-id="06d3d-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="06d3d-112">Advanced eDiscovery 授權要求適當的組織訂閱和每一使用者授權。</span><span class="sxs-lookup"><span data-stu-id="06d3d-112">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span> <span data-ttu-id="06d3d-113">如需 Advanced eDiscovery 的授權需求清單，請參閱[訂閱和授權](overview-ediscovery-20.md#subscriptions-and-licensing)。</span><span class="sxs-lookup"><span data-stu-id="06d3d-113">For a list of licensing requirements for Advanced eDiscovery, see [Subscriptions and licensing](overview-ediscovery-20.md#subscriptions-and-licensing).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="06d3d-114">步驟2：指派 eDiscovery 許可權</span><span class="sxs-lookup"><span data-stu-id="06d3d-114">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="06d3d-115">若要存取 Advanced eDiscovery 或新增為 Advanced eDiscovery 案例的成員，必須為使用者指派適當的許可權。</span><span class="sxs-lookup"><span data-stu-id="06d3d-115">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="06d3d-116">具體說來，使用者必須新增為安全性 & 規範中心的 eDiscovery 管理員角色群組成員。</span><span class="sxs-lookup"><span data-stu-id="06d3d-116">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="06d3d-117">這個角色群組的成員可以建立及管理 Advanced eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="06d3d-117">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="06d3d-118">他們可以新增及移除成員、將保管人和內容位置置於保留狀態、管理合法保留通知、建立及編輯案例中相關聯的搜尋、將搜尋結果新增至審閱集、分析審閱集中的資料，以及從 Advanced eDiscovery 案例中匯出及下載。</span><span class="sxs-lookup"><span data-stu-id="06d3d-118">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="06d3d-119">完成下列步驟，將使用者新增至 eDiscovery 管理員角色群組：</span><span class="sxs-lookup"><span data-stu-id="06d3d-119">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="06d3d-120">移至 <https://protection.office.com/permissions> 並使用 Microsoft 365 組織中的系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="06d3d-120">Go to <https://protection.office.com/permissions> and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="06d3d-121">在 [ **許可權** ] 頁面上，選取 [ **eDiscovery 管理員** ] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="06d3d-121">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="06d3d-122">在 [eDiscovery 管理員飛出] 頁面上，按一下 [ **Ediscovery 管理員**] 區段旁邊的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="06d3d-122">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="06d3d-123">在 [編輯角色群組] 嚮導的 [ **選擇 Ediscovery 管理員** ] 頁面上，按一下 **[選擇 ediscovery 管理員**]。</span><span class="sxs-lookup"><span data-stu-id="06d3d-123">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="06d3d-124">按一下 [ **新增** ]，然後選取您要新增至角色群組之所有使用者的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="06d3d-124">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="06d3d-125">按一下 [ **新增** ] 以新增選取的使用者，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="06d3d-125">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="06d3d-126">按一下 [ **儲存** ]，將使用者新增至角色群組，然後按一下 [ **關閉** ] 完成步驟。</span><span class="sxs-lookup"><span data-stu-id="06d3d-126">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="06d3d-127">EDiscovery 管理員角色群組的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="06d3d-127">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="06d3d-128">EDiscovery 管理員角色群組中有兩個子群組。</span><span class="sxs-lookup"><span data-stu-id="06d3d-128">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="06d3d-129">這些子群組之間的差異是以範圍為基礎。</span><span class="sxs-lookup"><span data-stu-id="06d3d-129">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="06d3d-130">**eDiscovery Manager**：可以查看和管理他們建立或屬於的 Advanced eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="06d3d-130">**eDiscovery Manager**: Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="06d3d-131">如果另一個 ediscovery 管理員建立了案例，但沒有將第二個 ediscovery 管理員新增為該案例的成員，則第二個 ediscovery 管理員將無法在規範中心的 [Advanced eDiscovery] 頁面上，查看或開啟此案例。</span><span class="sxs-lookup"><span data-stu-id="06d3d-131">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="06d3d-132">一般說來，您組織中的大部分人員都可以新增至 eDiscovery Manager 子組。</span><span class="sxs-lookup"><span data-stu-id="06d3d-132">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="06d3d-133">**Ediscovery 管理員**：可以執行 eDiscovery 管理員可以執行的所有案例管理工作。</span><span class="sxs-lookup"><span data-stu-id="06d3d-133">**eDiscovery Administrator**: Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="06d3d-134">此外，電子文件探索系統管理員還可以︰</span><span class="sxs-lookup"><span data-stu-id="06d3d-134">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="06d3d-135">檢視 [進階電子文件探索] 頁面上列出的所有案例。</span><span class="sxs-lookup"><span data-stu-id="06d3d-135">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="06d3d-136">在其自行新增為案例成員後，管理組織中的任何案例。</span><span class="sxs-lookup"><span data-stu-id="06d3d-136">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="06d3d-137">存取和匯出組織中任何案例的案例資料。</span><span class="sxs-lookup"><span data-stu-id="06d3d-137">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="06d3d-138">由於存取權範圍廣泛，組織只應讓少數系統管理員成為電子文件探索系統管理員子群組的成員。</span><span class="sxs-lookup"><span data-stu-id="06d3d-138">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="06d3d-139">如需有關 eDiscovery 許可權的詳細資訊，以及指派給 eDiscovery 管理員角色群組之每個角色的說明，請參閱 [指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="06d3d-139">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="06d3d-140">步驟3：設定 Advanced eDiscovery 的通用設定</span><span class="sxs-lookup"><span data-stu-id="06d3d-140">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="06d3d-141">在貴組織中的人員開始建立及使用案例之前完成的最後一個步驟，就是設定適用于組織中所有案例的全域設定。</span><span class="sxs-lookup"><span data-stu-id="06d3d-141">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="06d3d-142">目前只有一個全域設定是 *律師-用戶端許可權偵測* (未來) 會提供更多全域設定。</span><span class="sxs-lookup"><span data-stu-id="06d3d-142">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="06d3d-143">當您分析考核集中的資料時，此設定可讓律師-用戶端許可權模型執行。</span><span class="sxs-lookup"><span data-stu-id="06d3d-143">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="06d3d-144">模型使用電腦學習，判斷檔中包含法律性質的內容的可能性。</span><span class="sxs-lookup"><span data-stu-id="06d3d-144">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="06d3d-145">此外，它也會比較檔的參與者清單 (在您設定模型) 時所提交的律師清單，以判斷檔是否至少有一個擁有者的參與者。</span><span class="sxs-lookup"><span data-stu-id="06d3d-145">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="06d3d-146">如需設定和使用律師-用戶端許可權偵測模型的詳細資訊，請參閱[Advanced eDiscovery 中的設定律師-用戶端許可權偵測](attorney-privilege-detection.md)。</span><span class="sxs-lookup"><span data-stu-id="06d3d-146">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="06d3d-147">這是選擇性的步驟，您可以隨時執行。</span><span class="sxs-lookup"><span data-stu-id="06d3d-147">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="06d3d-148">未實施律師-用戶端許可權偵測模型不會使您無法建立及使用 Advanced eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="06d3d-148">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="06d3d-149">後續步驟</span><span class="sxs-lookup"><span data-stu-id="06d3d-149">Next steps</span></span>

<span data-ttu-id="06d3d-150">在您設定 Advanced eDiscovery 後，您就可以[建立案例](create-and-manage-advanced-ediscoveryv2-case.md)。</span><span class="sxs-lookup"><span data-stu-id="06d3d-150">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>