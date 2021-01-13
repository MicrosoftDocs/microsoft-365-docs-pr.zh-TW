---
title: 在 Microsoft 365 中設定高級 eDiscovery
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
search.appverid:
- MOE150
- MET150
description: 本文說明如何設定高級 eDiscovery，讓您可以開始建立及管理案例。 此外，它也會說明必要的 Microsoft 訂閱和授權。 完成一些快速步驟之後，就可以使用「高級 eDiscovery」工具。
ms.openlocfilehash: aef5cd2e465306b4401cda66d4ba30c97b9fc8cd
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841174"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="8d0b5-105">設定 Microsoft 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="8d0b5-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="8d0b5-106">Microsoft 365 中的「高級 eDiscovery」提供 [端對端工作流程](overview-ediscovery-20.md#advanced-ediscovery-workflow) ，可保留、收集、審查、分析和匯出回應組織內部和外部調查的資料。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-106">Advanced eDiscovery in Microsoft 365 provides an [end-to-end workflow](overview-ediscovery-20.md#advanced-ediscovery-workflow) to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="8d0b5-107">不需要部署高級 eDiscovery，但是必須先執行一些必要的工作，IT 系統管理員和 eDiscovery 管理員必須完成，您的組織才可以開始建立及使用高級 eDiscovery 案例來管理調查。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="8d0b5-108">本文討論設定高級 eDiscovery 所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-108">This article discusses the steps necessary to set up Advanced eDiscovery.</span></span> <span data-ttu-id="8d0b5-109">這包括確保存取高級 eDiscovery 及將保管人新增至案例，以及將許可權指派給法律和調查小組以供存取及管理案例所需的適當授權。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-109">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="8d0b5-110">步驟1：確認並指派適當的授權</span><span class="sxs-lookup"><span data-stu-id="8d0b5-110">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="8d0b5-111">「高級 eDiscovery」的授權需要適當的組織訂閱和每一使用者授權。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-111">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="8d0b5-112">**組織訂閱：** 若要存取 Microsoft 365 規範中心或安全性 & 規範中心的高級 eDiscovery，您的組織必須具備下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="8d0b5-112">**Organization subscription:** To access Advanced eDiscovery in the Microsoft 365 compliance center or the Security & Compliance Center, your organization must have one of the following:</span></span>

  - <span data-ttu-id="8d0b5-113">Microsoft 365 E5 或 Office 365 E5 訂閱</span><span class="sxs-lookup"><span data-stu-id="8d0b5-113">Microsoft 365 E5 or Office 365 E5 subscription</span></span>
  
  - <span data-ttu-id="8d0b5-114">含 E5 合規性附加元件的 Microsoft 365 E3 訂閱</span><span class="sxs-lookup"><span data-stu-id="8d0b5-114">Microsoft 365 E3 subscription with E5 Compliance add-on</span></span>

  - <span data-ttu-id="8d0b5-115">具有 E5 電子檔探索和審核附加元件的 Microsoft 365 E3 訂閱</span><span class="sxs-lookup"><span data-stu-id="8d0b5-115">Microsoft 365 E3 subscription with E5 eDiscovery and Audit add-on</span></span>

  <span data-ttu-id="8d0b5-116">如果您沒有現有的 Microsoft 365 E5 計畫，且想要嘗試使用 Advanced eDiscovery，您可以 [將 microsoft 365 新增](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 至現有的訂閱，或註冊 Microsoft 365 E5 的 [試用版](https://www.microsoft.com/microsoft-365/enterprise) 。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-116">If you don't have an existing Microsoft 365 E5 plan and want to try Advanced eDiscovery, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 E5.</span></span>

- <span data-ttu-id="8d0b5-117">**每位使用者授權：** 若要在預先 eDiscovery 案例中將使用者新增為系統管理員，該使用者必須根據您的組織訂閱，被指派下列其中一個授權：</span><span class="sxs-lookup"><span data-stu-id="8d0b5-117">**Per-user licensing:** To add a user as a custodian in an Advance eDiscovery case, that user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="8d0b5-118">Microsoft 365：使用者必須被指派 Microsoft 365 E5 授權、E5 相容性附加元件授權或 E5 eDiscovery 和審核附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-118">Microsoft 365: Users must be assigned a Microsoft 365 E5 license, an E5 Compliance add-on license, or an E5 eDiscovery and Audit add-on license.</span></span>

  - <span data-ttu-id="8d0b5-119">Office 365：使用者必須獲指派 Office 365 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-119">Office 365: Users must be assigned an Office 365 E5 license.</span></span>

   <span data-ttu-id="8d0b5-120">如需如何指派授權的詳細資訊，請參閱 [將授權指派給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-120">For information about how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

> [!NOTE]
> <span data-ttu-id="8d0b5-121">使用者只需要 E5 授權 (或適當的附加元件授權) ，以在高級 eDiscovery 案例中新增為保管人。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-121">Users only need an E5 license (or the appropriate add-on license) to be added as custodians to an Advanced eDiscovery case.</span></span> <span data-ttu-id="8d0b5-122">IT 系統管理員、eDiscovery 管理員、律師、paralegals 或調查人員，使用高級 eDiscovery 來管理案例及審閱案例資料，不需要 E5 或附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-122">IT admins, eDiscovery managers, lawyers, paralegals, or investigators who use Advanced eDiscovery to manage cases and review case data don't need an E5 or add-on license.</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="8d0b5-123">步驟2：指派 eDiscovery 許可權</span><span class="sxs-lookup"><span data-stu-id="8d0b5-123">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="8d0b5-124">若要存取高級 eDiscovery 或新增為高級 eDiscovery 案例的成員，必須對使用者指派適當的許可權。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-124">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="8d0b5-125">具體說來，使用者必須新增為安全性 & 規範中心的 eDiscovery 管理員角色群組成員。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-125">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="8d0b5-126">這個角色群組的成員可以建立及管理高級 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-126">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="8d0b5-127">他們可以新增及移除成員、將保管人和內容位置置於保留狀態、管理合法保留通知、建立及編輯案例中相關聯的搜尋、將搜尋結果新增至審閱集、分析複查集中的資料，以及從高級 eDiscovery 案例匯出及下載。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-127">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="8d0b5-128">完成下列步驟，將使用者新增至 eDiscovery 管理員角色群組：</span><span class="sxs-lookup"><span data-stu-id="8d0b5-128">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="8d0b5-129">移至 [https://protection.office.com/permissions](https://protection.office.com/permissions) 並使用您的 Microsoft 365 組織中的系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-129">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="8d0b5-130">在 [ **許可權** ] 頁面上，選取 [ **eDiscovery 管理員** ] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-130">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="8d0b5-131">在 [eDiscovery 管理員飛出] 頁面上，按一下 [ **Ediscovery 管理員**] 區段旁邊的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-131">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="8d0b5-132">在 [編輯角色群組] 嚮導的 [ **選擇 Ediscovery 管理員** ] 頁面上，按一下 **[選擇 ediscovery 管理員**]。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-132">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="8d0b5-133">按一下 [ **新增** ]，然後選取您要新增至角色群組之所有使用者的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-133">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="8d0b5-134">按一下 [ **新增** ] 以新增選取的使用者，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-134">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="8d0b5-135">按一下 [ **儲存** ]，將使用者新增至角色群組，然後按一下 [ **關閉** ] 完成步驟。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-135">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="8d0b5-136">EDiscovery 管理員角色群組的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="8d0b5-136">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="8d0b5-137">EDiscovery 管理員角色群組中有兩個子群組。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-137">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="8d0b5-138">這些子群組之間的差異是以範圍為基礎。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-138">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="8d0b5-139">**EDiscovery 管理員：** 可以查看和管理其所建立或其成員的高級 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-139">**eDiscovery Manager:** Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="8d0b5-140">如果另一個 eDiscovery 管理員建立了案例，但沒有將第二個 eDiscovery 管理員新增為該案例的成員，則第二個 eDiscovery 管理員將無法在「規範中心」的 [高級 eDiscovery] 頁面上，查看或開啟此案例。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-140">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="8d0b5-141">一般說來，您組織中的大部分人員都可以新增至 eDiscovery Manager 子組。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-141">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="8d0b5-142">**EDiscovery 管理員：** 可以執行 eDiscovery 管理員可以執行的所有案例管理工作。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-142">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="8d0b5-143">此外，電子檔探索管理員也可以：</span><span class="sxs-lookup"><span data-stu-id="8d0b5-143">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="8d0b5-144">查看 [高級 eDiscovery] 頁面上列出的所有案例。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-144">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="8d0b5-145">管理組織中的任何案例後，將自己新增為案例成員。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-145">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="8d0b5-146">針對組織中的任何案例，存取及匯出案例資料。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-146">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="8d0b5-147">因為存取範圍廣泛，所以組織應該只有少數管理員是 eDiscovery Administrators 子群組的成員。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-147">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="8d0b5-148">如需有關 eDiscovery 許可權的詳細資訊，以及指派給 eDiscovery 管理員角色群組之每個角色的說明，請參閱 [指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-148">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="8d0b5-149">步驟3：設定高級電子檔探索的全域設定</span><span class="sxs-lookup"><span data-stu-id="8d0b5-149">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="8d0b5-150">在貴組織中的人員開始建立及使用案例之前完成的最後一個步驟，就是設定適用于組織中所有案例的全域設定。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-150">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="8d0b5-151">目前只有一個全域設定是 *律師-用戶端許可權偵測* (未來) 會提供更多全域設定。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-151">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="8d0b5-152">當您分析考核集中的資料時，此設定可讓律師-用戶端許可權模型執行。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-152">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="8d0b5-153">模型使用電腦學習，判斷檔中包含法律性質的內容的可能性。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-153">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="8d0b5-154">此外，它也會比較檔的參與者清單 (在您設定模型) 時所提交的律師清單，以判斷檔是否至少有一個擁有者的參與者。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-154">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="8d0b5-155">如需設定和使用律師-用戶端許可權偵測模型的詳細資訊，請參閱 [Advanced eDiscovery 中的設定律師-用戶端許可權偵測](attorney-privilege-detection.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-155">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8d0b5-156">這是選擇性的步驟，您可以隨時執行。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-156">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="8d0b5-157">未實施律師-用戶端許可權偵測模型不會妨礙您建立及使用高級 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-157">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8d0b5-158">後續步驟</span><span class="sxs-lookup"><span data-stu-id="8d0b5-158">Next steps</span></span>

<span data-ttu-id="8d0b5-159">在您設定高級 eDiscovery 後，您就可以 [建立案例](create-and-manage-advanced-ediscoveryv2-case.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0b5-159">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>
