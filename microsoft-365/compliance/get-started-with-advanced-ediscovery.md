---
title: Microsoft 365 中的高級 eDiscovery 入門
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文說明如何開始使用 Microsoft 365 中的「高級 eDiscovery」。 完成一些快速步驟之後，就可以使用「高級 eDiscovery」工具。 第一步是建立案例，然後開始使用 Advanced eDiscovery 的功能和功能。
ms.openlocfilehash: 64c8681a47c21a7a6bfa9d67677405f74d75a96f
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398492"
---
# <a name="get-started-with-advanced-ediscovery"></a><span data-ttu-id="395c8-105">開始使用進階電子文件探索</span><span class="sxs-lookup"><span data-stu-id="395c8-105">Get started with Advanced eDiscovery</span></span>

<span data-ttu-id="395c8-106">Microsoft 365 中的「高級 eDiscovery」提供端對端工作流程，可保留、收集、審查、分析和匯出回應組織內部和外部調查的資料。</span><span class="sxs-lookup"><span data-stu-id="395c8-106">Advanced eDiscovery in Microsoft 365 provides an end-to-end workflow to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="395c8-107">不需要部署高級 eDiscovery，但是必須先執行一些必要的工作，IT 系統管理員和 eDiscovery 管理員必須完成，您的組織才可以開始建立及使用高級 eDiscovery 案例來管理調查。</span><span class="sxs-lookup"><span data-stu-id="395c8-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="395c8-108">本文討論設定高級 eDiscovery 所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="395c8-108">This article discusses the steps necessary to set up Advanced eDiscovery.</span></span> <span data-ttu-id="395c8-109">這包括確定存取高級 eDiscovery 及將保管人新增至案例的適當授權，以及將許可權指派給法律和調查小組，讓他們可以存取和管理案例。</span><span class="sxs-lookup"><span data-stu-id="395c8-109">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, as well as assigning permissions to your legal and investigation team so they can access and manage cases.</span></span> <span data-ttu-id="395c8-110">本文也提供使用案例來管理法律調查之高級 eDiscovery 工作流程的高層次概述。</span><span class="sxs-lookup"><span data-stu-id="395c8-110">This article also provides a high-level overview of using cases to manage the Advanced eDiscovery workflow for a legal investigation.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="395c8-111">步驟1：確認並指派適當的授權</span><span class="sxs-lookup"><span data-stu-id="395c8-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="395c8-112">「高級 eDiscovery」的授權需要適當的組織訂閱和每一使用者授權。</span><span class="sxs-lookup"><span data-stu-id="395c8-112">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="395c8-113">**組織訂閱：** 若要存取 Microsoft 365 規範中心或安全性 & 規範中心的高級 eDiscovery，您的組織必須具備下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="395c8-113">**Organization subscription:** To access Advanced eDiscovery in the Microsoft 365 compliance center or the Security & Compliance Center, your organization must have one of the following:</span></span>

  - <span data-ttu-id="395c8-114">Microsoft 365 E5 或 Office 365 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="395c8-114">Microsoft 365 E5 or Office 365 E5 subscription</span></span>
  
  - <span data-ttu-id="395c8-115">含 E5 合規性附加元件的 Microsoft 365 E3 訂閱</span><span class="sxs-lookup"><span data-stu-id="395c8-115">Microsoft 365 E3 subscription with E5 Compliance add-on</span></span>

  - <span data-ttu-id="395c8-116">具有 E5 電子檔探索和審核附加元件的 Microsoft 365 E3 訂閱</span><span class="sxs-lookup"><span data-stu-id="395c8-116">Microsoft 365 E3 subscription with E5 eDiscovery and Audit add-on</span></span>

  <span data-ttu-id="395c8-117">如果您沒有現有的 Microsoft 365 E5 計畫，且想要嘗試使用 Advanced eDiscovery，您可以 [將 microsoft 365 新增](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 至現有的訂閱，或註冊 Microsoft 365 E5 的 [試用版](https://www.microsoft.com/microsoft-365/enterprise) 。</span><span class="sxs-lookup"><span data-stu-id="395c8-117">If you don't have an existing Microsoft 365 E5 plan and want to try Advanced eDiscovery, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 E5.</span></span>

- <span data-ttu-id="395c8-118">**每位使用者授權：** 若要在預先 eDiscovery 案例中將使用者新增為系統管理員，該使用者必須根據您的組織訂閱，被指派下列其中一個授權：</span><span class="sxs-lookup"><span data-stu-id="395c8-118">**Per-user licensing:** To add a user as a custodian in an Advance eDiscovery case, that user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="395c8-119">Microsoft 365：使用者必須被指派 Microsoft 365 E5 授權、E5 相容性附加元件授權或 E5 eDiscovery 和審核附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="395c8-119">Microsoft 365: Users must be assigned a Microsoft 365 E5 license, an E5 Compliance add-on license, or an E5 eDiscovery and Audit add-on license.</span></span>

  - <span data-ttu-id="395c8-120">Office 365：使用者必須獲指派 Office 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="395c8-120">Office 365: Users must be assigned an Office 365 E5 license.</span></span>

   <span data-ttu-id="395c8-121">如需如何指派授權的詳細資訊，請參閱 [將授權指派給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="395c8-121">For information about how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

> [!NOTE]
> <span data-ttu-id="395c8-122">使用者只需要 E5 授權 (或適當的附加元件授權) ，以在高級 eDiscovery 案例中新增為保管人。</span><span class="sxs-lookup"><span data-stu-id="395c8-122">Users only need an E5 license (or the appropriate add-on license) to be added as custodians to an Advanced eDiscovery case.</span></span> <span data-ttu-id="395c8-123">IT 系統管理員、eDiscovery 管理員、律師、paralegals 或調查人員，使用高級 eDiscovery 來管理案例及審閱案例資料，不需要 E5 或附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="395c8-123">IT admins, eDiscovery managers, lawyers, paralegals, or investigators who use Advanced eDiscovery to manage cases and review case data don't need an E5 or add-on license.</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="395c8-124">步驟2：指派 eDiscovery 許可權</span><span class="sxs-lookup"><span data-stu-id="395c8-124">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="395c8-125">若要存取高級 eDiscovery 或新增為高級 eDiscovery 案例的成員，必須對使用者指派適當的許可權。</span><span class="sxs-lookup"><span data-stu-id="395c8-125">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="395c8-126">具體說來，使用者必須新增為安全性 & 規範中心的 eDiscovery 管理員角色群組成員。</span><span class="sxs-lookup"><span data-stu-id="395c8-126">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="395c8-127">這個角色群組的成員可以建立及管理高級 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="395c8-127">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="395c8-128">他們可以新增及移除成員、將保管人和內容位置置於保留狀態、管理合法保留通知、建立及編輯案例中相關聯的搜尋、將搜尋結果新增至審閱集、分析複查集中的資料，以及從高級 eDiscovery 案例匯出及下載。</span><span class="sxs-lookup"><span data-stu-id="395c8-128">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="395c8-129">完成下列步驟，將使用者新增至 eDiscovery 管理員角色群組：</span><span class="sxs-lookup"><span data-stu-id="395c8-129">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="395c8-130">移至 [https://protection.office.com/permissions](https://protection.office.com/permissions) 並使用您的 Microsoft 365 組織中的系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="395c8-130">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="395c8-131">在 [ **許可權** ] 頁面上，選取 [ **eDiscovery 管理員** ] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="395c8-131">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="395c8-132">在 [eDiscovery 管理員飛出] 頁面上，按一下 [ **Ediscovery 管理員**] 區段旁邊的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="395c8-132">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="395c8-133">在 [編輯角色群組] 嚮導的 [ **選擇 EDiscovery 管理員** ] 頁面上，按一下 **[選擇探索管理員**]。</span><span class="sxs-lookup"><span data-stu-id="395c8-133">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose Discovery Manager**.</span></span>

5. <span data-ttu-id="395c8-134">按一下 [ **新增** ]，然後選取您要新增至角色群組之所有使用者的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="395c8-134">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="395c8-135">按一下 [ **新增** ] 以新增選取的使用者，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="395c8-135">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="395c8-136">按一下 [ **儲存** ]，將使用者新增至角色群組，然後按一下 [ **關閉** ] 完成步驟。</span><span class="sxs-lookup"><span data-stu-id="395c8-136">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="395c8-137">EDiscovery 管理員角色群組的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="395c8-137">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="395c8-138">EDiscovery 管理員角色群組中有兩個子群組。</span><span class="sxs-lookup"><span data-stu-id="395c8-138">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="395c8-139">這些子群組之間的差異是以範圍為基礎。</span><span class="sxs-lookup"><span data-stu-id="395c8-139">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="395c8-140">**EDiscovery 管理員：** 可以查看和管理其所建立或其成員的高級 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="395c8-140">**eDiscovery Manager:** Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="395c8-141">如果另一個 eDiscovery 管理員建立了案例，但沒有將第二個 eDiscovery 管理員新增為該案例的成員，則第二個 eDiscovery 管理員將無法在「規範中心」的 [高級 eDiscovery] 頁面上，查看或開啟此案例。</span><span class="sxs-lookup"><span data-stu-id="395c8-141">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="395c8-142">一般說來，您組織中的大部分人員都可以新增至 eDiscovery Manager 子組。</span><span class="sxs-lookup"><span data-stu-id="395c8-142">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="395c8-143">**EDiscovery 管理員：** 可以執行 eDiscovery 管理員可以執行的所有案例管理工作。</span><span class="sxs-lookup"><span data-stu-id="395c8-143">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="395c8-144">此外，電子檔探索管理員也可以：</span><span class="sxs-lookup"><span data-stu-id="395c8-144">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="395c8-145">查看 [高級 eDiscovery] 頁面上列出的所有案例。</span><span class="sxs-lookup"><span data-stu-id="395c8-145">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="395c8-146">管理組織中的任何案例後，將自己新增為案例成員。</span><span class="sxs-lookup"><span data-stu-id="395c8-146">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="395c8-147">針對組織中的任何案例，存取及匯出案例資料。</span><span class="sxs-lookup"><span data-stu-id="395c8-147">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="395c8-148">因為存取範圍廣泛，所以組織應該只有少數管理員是 eDiscovery Administrators 子群組的成員。</span><span class="sxs-lookup"><span data-stu-id="395c8-148">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="395c8-149">如需有關 eDiscovery 許可權的詳細資訊，以及指派給 eDiscovery 管理員角色群組之每個角色的說明，請參閱 [指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="395c8-149">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="395c8-150">步驟3：設定高級電子檔探索的全域設定</span><span class="sxs-lookup"><span data-stu-id="395c8-150">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="395c8-151">在貴組織中的人員開始建立及使用案例之前完成的最後一個步驟，就是設定適用于組織中所有案例的全域設定。</span><span class="sxs-lookup"><span data-stu-id="395c8-151">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="395c8-152">目前只有一個全域設定是 *律師-用戶端許可權偵測* (未來) 會提供更多全域設定。</span><span class="sxs-lookup"><span data-stu-id="395c8-152">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="395c8-153">當您分析考核集中的資料時，此設定可讓律師-用戶端許可權模型執行。</span><span class="sxs-lookup"><span data-stu-id="395c8-153">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="395c8-154">模型使用電腦學習，判斷檔中包含法律性質的內容的可能性。</span><span class="sxs-lookup"><span data-stu-id="395c8-154">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="395c8-155">此外，它也會比較檔的參與者清單 (在您設定模型) 時所提交的律師清單，以判斷檔是否至少有一個擁有者的參與者。</span><span class="sxs-lookup"><span data-stu-id="395c8-155">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="395c8-156">如需設定和使用律師-用戶端許可權偵測模型的詳細資訊，請參閱 [Advanced eDiscovery 中的設定律師-用戶端許可權偵測](attorney-privilege-detection.md)。</span><span class="sxs-lookup"><span data-stu-id="395c8-156">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="395c8-157">這是選擇性的步驟，您可以隨時執行。</span><span class="sxs-lookup"><span data-stu-id="395c8-157">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="395c8-158">未實施律師-用戶端許可權偵測模型不會妨礙您建立及使用高級 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="395c8-158">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="step-4-create-an-advanced-ediscovery-case"></a><span data-ttu-id="395c8-159">步驟4：建立高級 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="395c8-159">Step 4: Create an Advanced eDiscovery case</span></span>

<span data-ttu-id="395c8-160">下一步是建立案例，並開始使用高級 eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="395c8-160">The next step is to create a case and start using Advanced eDiscovery.</span></span> <span data-ttu-id="395c8-161">完成下列步驟以建立案例並新增成員。</span><span class="sxs-lookup"><span data-stu-id="395c8-161">Complete the following steps to create a case and add members.</span></span> <span data-ttu-id="395c8-162">建立案例的使用者會自動新增為成員。</span><span class="sxs-lookup"><span data-stu-id="395c8-162">The user who creates the case is automatically added as a member.</span></span>

1. <span data-ttu-id="395c8-163">移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並登入使用已獲指派適當 eDiscovery 許可權之使用者帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="395c8-163">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span> <span data-ttu-id="395c8-164">組織管理角色群組的成員也可以建立高級 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="395c8-164">Members of the Organization Management role group can also create Advanced eDiscovery cases.</span></span>

2. <span data-ttu-id="395c8-165">在 Microsoft 365 規範中心的左功能窗格中，按一下 [ **全部顯示**]，然後按一下 [ **eDiscovery > Advanced**]。</span><span class="sxs-lookup"><span data-stu-id="395c8-165">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

3. <span data-ttu-id="395c8-166">在 [ **高級 eDiscovery** ] 頁面上，按一下 [ **案例** ] 索引標籤，然後按一下 [ **建立案例**]。</span><span class="sxs-lookup"><span data-stu-id="395c8-166">On the **Advanced eDiscovery** page, click the **Cases** tab, and then click **Create a case**.</span></span>

4. <span data-ttu-id="395c8-167">在 [ **新 eDiscovery 案例** 飛出] 頁面上，為案例輸入 (必要) 的名稱，然後輸入選用的案例編號及描述。</span><span class="sxs-lookup"><span data-stu-id="395c8-167">On the **New eDiscovery case** flyout page, give the case a name (required), and then type an optional case number and description.</span></span> <span data-ttu-id="395c8-168">案例名稱在您的組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="395c8-168">The case name must be unique in your organization.</span></span>

5. <span data-ttu-id="395c8-169">按一下 [ **儲存** ] 以建立案例。</span><span class="sxs-lookup"><span data-stu-id="395c8-169">Click **Save** to create the case.</span></span>

   <span data-ttu-id="395c8-170">會建立新案例，並顯示新案例中的 [ **設定** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="395c8-170">The new case is created and the **Settings** tab in the new case is displayed.</span></span> 

6. <span data-ttu-id="395c8-171">在 [**設定**] 索引標籤上的 [ **Access & 許可權**] 方塊中，按一下 [**選取**]，然後按一下 [**更新**]。</span><span class="sxs-lookup"><span data-stu-id="395c8-171">In the **Access & permissions** tile on the **Settings** tab, click **Select**, and then click **Update**.</span></span>

7. <span data-ttu-id="395c8-172">按一下 [更新]。</span><span class="sxs-lookup"><span data-stu-id="395c8-172">Click **Update**.</span></span>

8. <span data-ttu-id="395c8-173">在 [ **管理此案例** 飛入] 頁面上的 [ **管理成員**] 底下，按一下 [ **新增** ] 以將成員新增至案例。</span><span class="sxs-lookup"><span data-stu-id="395c8-173">On the **Manage this case** flyout page, under **Manage members**, click **Add** to add members to the case.</span></span>

9. <span data-ttu-id="395c8-174">在 [人員] 清單中，選取您要新增至案例之人員名稱旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="395c8-174">In the list of people, select the check box next to the names of the people that you want to add to the case.</span></span> <span data-ttu-id="395c8-175">如先前所述，請確定您加入案例的人員已獲指派適當的 eDiscovery 許可權。</span><span class="sxs-lookup"><span data-stu-id="395c8-175">As previously explained, be sure that the people you add to the case have been assigned the appropriate eDiscovery permissions.</span></span>

10. <span data-ttu-id="395c8-176">在您選取要新增為案例成員的人員之後，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="395c8-176">After you've selected the people to add as members of the case, click **Add**.</span></span>

11. <span data-ttu-id="395c8-177">在 [ **管理此案例** 飛入] 頁面中，按一下 [ **儲存** ] 儲存新的案例成員清單。</span><span class="sxs-lookup"><span data-stu-id="395c8-177">In the **Manage this case** flyout page, click **Save** to save the new list of case members.</span></span>

12. <span data-ttu-id="395c8-178">按一下 [ **首頁** ] 索引標籤，移至案例首頁。</span><span class="sxs-lookup"><span data-stu-id="395c8-178">Click the **Home** tab to go to the case home page.</span></span>

## <a name="explore-the-advanced-ediscovery-workflow"></a><span data-ttu-id="395c8-179">探索高級 eDiscovery 工作流程</span><span class="sxs-lookup"><span data-stu-id="395c8-179">Explore the Advanced eDiscovery workflow</span></span>

<span data-ttu-id="395c8-180">為了讓您開始使用高級 eDiscovery，以下是一個簡單的工作流程，可與 [一般 ediscovery 做法](overview-ediscovery-20.md#alignment-with-edrm)搭配使用。</span><span class="sxs-lookup"><span data-stu-id="395c8-180">To get you started using Advanced eDiscovery, here's a simple workflow that aligns with [common eDiscovery practices](overview-ediscovery-20.md#alignment-with-edrm).</span></span> <span data-ttu-id="395c8-181">在上述每個步驟中，我們也會強調您可以探索的一些擴充的高級 eDiscovery 功能。</span><span class="sxs-lookup"><span data-stu-id="395c8-181">In each of these steps, we'll also highlight some extended Advanced eDiscovery functionality that you can explore.</span></span>

![高級 eDiscovery 工作流程](../media/AeDWorkflow.png)

1. <span data-ttu-id="395c8-183">**[將保管人新增至案例](add-custodians-to-case.md)**。</span><span class="sxs-lookup"><span data-stu-id="395c8-183">**[Add custodians to a case](add-custodians-to-case.md)**.</span></span> <span data-ttu-id="395c8-184">建立案例之後的第一個步驟是新增保管人。</span><span class="sxs-lookup"><span data-stu-id="395c8-184">The first step after creating a case is to add custodians.</span></span> <span data-ttu-id="395c8-185">*管理員*是指具有可能與案例相關之檔或電子檔的系統管理控制權的人員。</span><span class="sxs-lookup"><span data-stu-id="395c8-185">A *custodian* is a person having administrative control of a document or electronic file that may be relevant to the case.</span></span> <span data-ttu-id="395c8-186">以下是一些 (，也就是在您將保管人新增至案例時) 的情況：</span><span class="sxs-lookup"><span data-stu-id="395c8-186">Here are some things that happen (or that you can do) when you add custodians to a case:</span></span>

   - <span data-ttu-id="395c8-187">保管人的 Exchange 信箱、OneDrive 帳戶，以及保管人隸屬的任何 Microsoft 團隊或 Yammer 群組中的資料，都可以 "標示" 為案例中的 custodial 資料。</span><span class="sxs-lookup"><span data-stu-id="395c8-187">Data in the custodian's Exchange mailbox, OneDrive account, and any Microsoft Teams or Yammer groups that the custodian is a member of can be "marked" as custodial data in the case.</span></span>
  
   - <span data-ttu-id="395c8-188">保管人資料是由稱為「 *高級索引*) 」的程式 (重新編制索引。</span><span class="sxs-lookup"><span data-stu-id="395c8-188">Custodian data is reindexed (by a process called *Advanced indexing*).</span></span> <span data-ttu-id="395c8-189">這可協助您在下一個步驟中優化搜尋。</span><span class="sxs-lookup"><span data-stu-id="395c8-189">This helps optimize searching for it in the next step.</span></span>
  
   - <span data-ttu-id="395c8-190">您可以對保管人資料進行保留。</span><span class="sxs-lookup"><span data-stu-id="395c8-190">You can place a hold on custodian data.</span></span> <span data-ttu-id="395c8-191">這會在調查期間保留與案例相關的資料。</span><span class="sxs-lookup"><span data-stu-id="395c8-191">This preserves data that may be relevant to the case during the investigation.</span></span>
  
   - <span data-ttu-id="395c8-192">您可以將其他資料來源與保管人 (產生關聯。例如，您可以將 SharePoint 網站或 Microsoft 365 群組與保管人) 產生關聯，這樣就可以重新編制索引、保留及搜尋此資料，就像是保管人的信箱或 OneDrive 帳戶中的資料一樣。</span><span class="sxs-lookup"><span data-stu-id="395c8-192">You can associate other data sources with a custodian (for example, you can associate a SharePoint site or Microsoft 365 Group with a custodian) so this data can be reindexed, placed on hold, and searched, just like the data in the custodian's mailbox or OneDrive account.</span></span>

   - <span data-ttu-id="395c8-193">您可以使用高級 eDiscovery 中的 [通訊工作流程](managing-custodian-communications.md) ，將合法保留通知傳送給保管人。</span><span class="sxs-lookup"><span data-stu-id="395c8-193">You can use the [communications workflow](managing-custodian-communications.md) in Advanced eDiscovery to send a legal hold notification to custodians.</span></span>

2. <span data-ttu-id="395c8-194">**[搜尋與案例相關之資料的 custodial 資料來源](collecting-data-for-ediscovery.md)**。</span><span class="sxs-lookup"><span data-stu-id="395c8-194">**[Search custodial data sources for data relevant to the case](collecting-data-for-ediscovery.md)**.</span></span> <span data-ttu-id="395c8-195">在您將保管人新增至案例後，請使用內建的搜尋工具，針對可能與案例相關的資料，搜尋保管人資料位置。</span><span class="sxs-lookup"><span data-stu-id="395c8-195">After you add custodians to a case, use the built-in search tool to search the custodian data locations for data that may be relevant to the case.</span></span> <span data-ttu-id="395c8-196">您可以使用關鍵字、屬性和條件來 [建立搜尋查詢](building-search-queries.md) ，以利用最可能與案例相關的資料傳回搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="395c8-196">You use keywords, properties, and conditions to [build search queries](building-search-queries.md) that return search results with the data that's most likely relevant to the case.</span></span> <span data-ttu-id="395c8-197">您也可以：</span><span class="sxs-lookup"><span data-stu-id="395c8-197">You can also:</span></span>

   - <span data-ttu-id="395c8-198">查看可協助您縮小搜尋查詢以縮小結果的 [搜尋統計資料](search-statistics.md) 。</span><span class="sxs-lookup"><span data-stu-id="395c8-198">View [search statistics](search-statistics.md) that may help you refine a search query to narrow the results.</span></span>

   - <span data-ttu-id="395c8-199">預覽搜尋結果，以快速確認是否找到相關資料。</span><span class="sxs-lookup"><span data-stu-id="395c8-199">Preview the search results to quickly verify whether the relevant data is being found.</span></span>

   - <span data-ttu-id="395c8-200">修改查詢，然後重新執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="395c8-200">Revise a query and rerun the search.</span></span>

3. <span data-ttu-id="395c8-201">**[將資料新增至審閱集](add-data-to-review-set.md)**。</span><span class="sxs-lookup"><span data-stu-id="395c8-201">**[Add data to a review set](add-data-to-review-set.md)**.</span></span> <span data-ttu-id="395c8-202">當您設定並確認搜尋傳回所需的資料之後，下一步是將搜尋結果新增至審閱集。</span><span class="sxs-lookup"><span data-stu-id="395c8-202">Once you've configured and verified that a search returns the desired data, the next step is to add the search results to a review set.</span></span> <span data-ttu-id="395c8-203">當您將資料新增至審閱集時，專案會從其原始位置複製到安全的 Azure 存放位置。</span><span class="sxs-lookup"><span data-stu-id="395c8-203">When you add data to a review set, items are copied from their original location to a secure Azure Storage location.</span></span> <span data-ttu-id="395c8-204">當審閱及分析審閱集中的專案時，會再次重新編制索引資料，以優化完整和快速的搜尋。</span><span class="sxs-lookup"><span data-stu-id="395c8-204">The data is reindexed again to optimize it for thorough and fast searches when reviewing and analyzing items in the review set.</span></span> <span data-ttu-id="395c8-205">此外，您也可以 [將非 Office 365 資料新增至審閱集](load-non-office-365-data-into-a-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="395c8-205">Additionally, you can also [add non-Office 365 data into a review set](load-non-office-365-data-into-a-review-set.md).</span></span>

   <span data-ttu-id="395c8-206">此外還有一種特殊的審閱集，您可以將資料新增至（稱為「 *交談複查集*」）。</span><span class="sxs-lookup"><span data-stu-id="395c8-206">There's also a special kind of review set that you can add data to, called a *conversation review set*.</span></span> <span data-ttu-id="395c8-207">這兩種審閱集可提供交談重新構建功能，以重新構建、審閱及匯出像是 Microsoft 小組中的對話交談。</span><span class="sxs-lookup"><span data-stu-id="395c8-207">These types of reviews sets provide conversation reconstruction capabilities to reconstruct, review, and export threaded conversations like those in Microsoft Teams.</span></span> <span data-ttu-id="395c8-208">如需詳細資訊，請參閱 [在高級 eDiscovery 中查看交談](conversation-review-sets.md)。</span><span class="sxs-lookup"><span data-stu-id="395c8-208">For more information, see [Review conversations in Advanced eDiscovery](conversation-review-sets.md).</span></span>

4. <span data-ttu-id="395c8-209">**檢查及分析審閱集中的資料**。</span><span class="sxs-lookup"><span data-stu-id="395c8-209">**Review and analyze data in a review set**.</span></span> <span data-ttu-id="395c8-210">現在，資料是在審校集中，您可以使用各種各樣的工具和功能來查看及分析案例資料，將資料集減至最適合您所調查案例的目標。</span><span class="sxs-lookup"><span data-stu-id="395c8-210">Now that data is in a review set, you can use a wide-variety of tools and capabilities to view and analyze the case data with the goal of reducing the data set to what is most relevant to the case you're investigation.</span></span> <span data-ttu-id="395c8-211">以下是您可以在此程式中使用之部分工具和功能的清單。</span><span class="sxs-lookup"><span data-stu-id="395c8-211">Here's a list of some tools and capabilities that you can use during this process.</span></span>

   - <span data-ttu-id="395c8-212">[View documents](view-documents-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="395c8-212">[View documents](view-documents-in-review-set.md).</span></span> <span data-ttu-id="395c8-213">這包括針對審閱集中的每一份檔，查看其中繼資料，並以原生版本或文字版本查看該檔。</span><span class="sxs-lookup"><span data-stu-id="395c8-213">This includes viewing the metadata for each document in a review set, and viewing the document in its native version or text version.</span></span>

   - <span data-ttu-id="395c8-214">[建立查詢和篩選](review-set-search.md)。</span><span class="sxs-lookup"><span data-stu-id="395c8-214">[Create queries and filters](review-set-search.md).</span></span> <span data-ttu-id="395c8-215">您可以使用各種搜尋準則來建立搜尋查詢 (包括搜尋所有檔案 [中繼資料屬性](document-metadata-fields-in-advanced-ediscovery.md) 的功能) 以進一步精煉及挑選案例資料至與案例最為相關的專案。</span><span class="sxs-lookup"><span data-stu-id="395c8-215">You create search queries using a variety of search criteria (including the ability to search all [file metadata properties](document-metadata-fields-in-advanced-ediscovery.md)) to further refine and cull the case data to what is most relevant to the case.</span></span> <span data-ttu-id="395c8-216">您也可以使用 [審閱集合篩選]，將其他條件快速套用至搜尋查詢的結果，以進一步精煉這些結果。</span><span class="sxs-lookup"><span data-stu-id="395c8-216">You can also use review set filters to quickly apply additional conditions to the results of a search query to further refine those results.</span></span> 

   - <span data-ttu-id="395c8-217">[建立及使用標記](tagging-documents.md)。</span><span class="sxs-lookup"><span data-stu-id="395c8-217">[Create and use tags](tagging-documents.md).</span></span> <span data-ttu-id="395c8-218">您可以將標記套用至審閱集合中的檔，以識別哪些回應 (或沒有回應案例) ，然後在建立搜尋查詢以包含或排除已標記的檔時，使用這些標記。</span><span class="sxs-lookup"><span data-stu-id="395c8-218">You can apply tags to documents in a review set to identify which are responsive (or non-responsive to the case) and then use those tags when creating search queries to include or exclude the tagged documents.</span></span> <span data-ttu-id="395c8-219">您也可以進行標記，以決定要匯出的檔。</span><span class="sxs-lookup"><span data-stu-id="395c8-219">You can also tagging to determine which documents to export.</span></span>

   - <span data-ttu-id="395c8-220">[批註和密文檔](view-documents-in-review-set.md#annotate-view)。</span><span class="sxs-lookup"><span data-stu-id="395c8-220">[Annotate and redact documents](view-documents-in-review-set.md#annotate-view).</span></span> <span data-ttu-id="395c8-221">您可以使用審閱中的批註工具，註釋檔，並在檔中以工作產品標記密文內容。</span><span class="sxs-lookup"><span data-stu-id="395c8-221">You can use the annotation tool in a review to annotate documents and redact content in documents as work product.</span></span> <span data-ttu-id="395c8-222">我們會在評審時產生 PDF 版本的批註或 redacted 檔，以降低匯出檔的 unredacted 原生版本的風險。</span><span class="sxs-lookup"><span data-stu-id="395c8-222">We generate a PDF version of an annotated or redacted document during review to reduce the risk of exporting the unredacted native version of the document.</span></span>

   - <span data-ttu-id="395c8-223">[分析案例資料](analyzing-data-in-review-set.md)。</span><span class="sxs-lookup"><span data-stu-id="395c8-223">[Analyze case data](analyzing-data-in-review-set.md).</span></span> <span data-ttu-id="395c8-224">高級 eDiscovery 的分析功能非常強大。</span><span class="sxs-lookup"><span data-stu-id="395c8-224">The analytics functionality in Advanced eDiscovery is powerful.</span></span> <span data-ttu-id="395c8-225">在複查集中的資料執行分析之後，我們會執行分析，例如接近重複偵測、電子郵件執行緒和主題，可協助減少您必須查看的檔數量。</span><span class="sxs-lookup"><span data-stu-id="395c8-225">After you run analytics on the data in review set, we perform analysis such as near duplicate detection, email threading, and themes that can help reduce the volume of documents that you have to review.</span></span> <span data-ttu-id="395c8-226">我們也會產生分析報告，以匯總執行分析的結果。</span><span class="sxs-lookup"><span data-stu-id="395c8-226">We also generate an Analytics reports that summarize the result of running analytics.</span></span> <span data-ttu-id="395c8-227">如先前所述，執行分析也會執行 [律師-用戶端許可權偵測模型](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)。</span><span class="sxs-lookup"><span data-stu-id="395c8-227">As previously explained, running analytics also runs [the attorney-client privilege detection model](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model).</span></span>

5. <span data-ttu-id="395c8-228">**匯出及下載案例資料**。</span><span class="sxs-lookup"><span data-stu-id="395c8-228">**Export and download case data**.</span></span> <span data-ttu-id="395c8-229">收集、複查及分析案例資料的最後一個步驟是，將其匯出至「高級 eDiscovery」以供外部檢查，或由調查小組以外的人員進行審閱。</span><span class="sxs-lookup"><span data-stu-id="395c8-229">A final step after collecting, reviewing, and analyzing case data is to export it out of Advanced eDiscovery for external review or for review by people outside of the investigation team.</span></span> <span data-ttu-id="395c8-230">匯出資料的過程分為兩個步驟。</span><span class="sxs-lookup"><span data-stu-id="395c8-230">Exporting data is a two-step process.</span></span> <span data-ttu-id="395c8-231">第一步是將資料 [匯出](export-documents-from-review-set.md) 至審閱集，並將它複製到不同的 Azure 存放位置， (由 Microsoft 提供，或是由組織) 所管理。</span><span class="sxs-lookup"><span data-stu-id="395c8-231">The first step is to [export](export-documents-from-review-set.md) data out of the review set and copy it to a different Azure Storage location (one provided by Microsoft or one managed by your organization).</span></span> <span data-ttu-id="395c8-232">然後，您使用 Azure Storage Explorer 將資料 [下載](download-export-jobs.md) 到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="395c8-232">Then you use Azure Storage Explorer to [download](download-export-jobs.md) the data to a local computer.</span></span> <span data-ttu-id="395c8-233">除了匯出的資料檔案之外，匯出套件也包含匯出報告、摘要報告及錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="395c8-233">In addition to the exported data files, the contains of the export package also contains an export report, a summary report, and an error report.</span></span>
