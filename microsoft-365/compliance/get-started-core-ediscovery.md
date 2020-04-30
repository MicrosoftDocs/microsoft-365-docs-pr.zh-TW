---
title: Microsoft 365 中的核心 eDiscovery 案例快速入門
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 本文說明如何開始使用 Microsoft 365 中的核心 eDiscovery。 指派 eDiscovery 許可權並建立案例之後，您可以新增成員、建立 eDiscovery 保留，然後搜尋並匯出與調查相關的資料。
ms.openlocfilehash: c9c3d8c3832703e8dbbcf8b2c04a566af0f5eb6b
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943382"
---
# <a name="get-started-with-core-ediscovery"></a><span data-ttu-id="3a1bd-104">開始使用核心電子文件探索</span><span class="sxs-lookup"><span data-stu-id="3a1bd-104">Get started with Core eDiscovery</span></span>

<span data-ttu-id="3a1bd-105">Microsoft 365 中的核心 eDiscovery 提供一種基本 eDiscovery 工具，可讓組織用來搜尋並匯出 Microsoft 365 和 Office 365 中的內容。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-105">Core eDiscovery in Microsoft 365 provides a basic eDiscovery tool that organizations can use to search and export content in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="3a1bd-106">您也可以使用核心 eDiscovery，在內容位置（例如 Exchange 信箱、SharePoint 網站、OneDrive 帳戶和 Microsoft 小組）上進行 eDiscovery 暫止。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-106">You can also use Core eDiscovery to place an eDiscovery hold on content locations, such as Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft Teams.</span></span> <span data-ttu-id="3a1bd-107">不需要部署核心 eDiscovery，但在您的組織開始使用核心 eDiscovery 來搜尋、匯出及保留內容之前，必須先完成一些必要的工作，IT 系統管理員和 eDiscovery 管理員才能開始使用。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-107">Nothing is needed to deploy Core eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start using Core eDiscovery to search, export, and preserve content.</span></span>

<span data-ttu-id="3a1bd-108">本文討論設定核心 eDiscovery 所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-108">This article discusses the steps necessary to set up Core eDiscovery.</span></span> <span data-ttu-id="3a1bd-109">這包括確保存取核心 eDiscovery 所需的適當授權，並在內容位置上放置 eDiscovery 保留，以及將許可權指派給您的 IT、法律和調查小組，讓他們能夠存取及管理案例。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-109">This includes ensuring the proper licensing required to access Core eDiscovery and place an eDiscovery hold on content locations, as well as assigning permissions to your IT, legal, and investigation team so they can access and manage cases.</span></span> <span data-ttu-id="3a1bd-110">本文也提供使用案例來搜尋及匯出內容的高層次概述。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-110">This article also provides a high-level overview of using cases to search for and export content.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="3a1bd-111">步驟1：確認並指派適當的授權</span><span class="sxs-lookup"><span data-stu-id="3a1bd-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="3a1bd-112">核心 eDiscovery 的授權要求適當的組織訂閱和每一使用者授權。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-112">Licensing for Core eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span>

- <span data-ttu-id="3a1bd-113">**組織訂閱：** 若要存取 Microsoft 365 規範中心或 Office 365 安全性 & 規範中心的核心 eDiscovery，以及使用保留與匯出功能，您的組織必須具有 Microsoft 365 E3 或 Office 365 E3 訂閱或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-113">**Organization subscription:** To access Core eDiscovery in the Microsoft 365 compliance center or the Office 365 Security & Compliance Center and use the hold and export features, your organization must have a Microsoft 365 E3 or Office 365 E3 subscription or higher.</span></span>

- <span data-ttu-id="3a1bd-114">**每位使用者授權：** 若要在信箱和網站上放置 eDiscovery 暫止，必須根據您的組織訂閱，為使用者指派下列其中一個授權：</span><span class="sxs-lookup"><span data-stu-id="3a1bd-114">**Per-user licensing:** To place an eDiscovery hold on mailboxes and sites, a user must be assigned one of the following licenses, depending on your organization subscription:</span></span>

  - <span data-ttu-id="3a1bd-115">Microsoft 365 E3 或 Office 365 E3 授權或更高版本</span><span class="sxs-lookup"><span data-stu-id="3a1bd-115">A Microsoft 365 E3 or Office 365 E3 license or higher</span></span>

   <span data-ttu-id="3a1bd-116">OR</span><span class="sxs-lookup"><span data-stu-id="3a1bd-116">OR</span></span>

  - <span data-ttu-id="3a1bd-117">Microsoft 365 E1 或 Office 365 E1 授權與 Exchange Online 方案2或 Exchange Online 封存附加元件授權</span><span class="sxs-lookup"><span data-stu-id="3a1bd-117">A Microsoft 365 E1 or Office 365 E1 license with an Exchange Online Plan 2 or Exchange Online Archiving add-on license</span></span>

  <span data-ttu-id="3a1bd-118">AND</span><span class="sxs-lookup"><span data-stu-id="3a1bd-118">AND</span></span>

  - <span data-ttu-id="3a1bd-119">Microsoft 365 E1 或 Office 365 E1 授權，具有 SharePoint Online Plan 2 或 OneDrive for Business Plan 2 附加元件授權</span><span class="sxs-lookup"><span data-stu-id="3a1bd-119">A Microsoft 365 E1 or Office 365 E1 license with an SharePoint Online Plan 2 or OneDrive for Business Plan 2 add-on license</span></span>
  
  <span data-ttu-id="3a1bd-120">如需如何指派授權的詳細資訊，請參閱[將授權指派給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-120">For information about how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="3a1bd-121">如需授權的相關資訊：</span><span class="sxs-lookup"><span data-stu-id="3a1bd-121">For information about licensing:</span></span>

- <span data-ttu-id="3a1bd-122">下載並查看[Microsoft 365 合規性授權比較](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)中的「探索 & 回應」方案。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-122">Download and see the "Discover & Respond" solution in the [Microsoft 365 Compliance Licensing Comparison](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx).</span></span>

- <span data-ttu-id="3a1bd-123">請參閱[安全性 & 規範中心服務說明](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-123">See the [Security & Compliance Center service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="3a1bd-124">步驟2：指派 eDiscovery 許可權</span><span class="sxs-lookup"><span data-stu-id="3a1bd-124">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="3a1bd-125">若要存取核心 ediscovery 或新增為核心 eDiscovery 案例的成員，必須對使用者指派適當的許可權。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-125">To access Core eDiscovery or be added as a member of a Core eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="3a1bd-126">具體而言，使用者必須新增為 Office 365 安全性 & 合規性中心內的 eDiscovery 管理員角色群組成員。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-126">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="3a1bd-127">這個角色群組的成員可以建立及管理核心 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-127">Members of this role group can create and manage Core eDiscovery cases.</span></span> <span data-ttu-id="3a1bd-128">他們可以新增及移除成員、為使用者放置 eDiscovery 暫止功能、建立及編輯搜尋，以及從核心 eDiscovery 案例中匯出內容。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-128">They can add and remove members, place an eDiscovery hold on users, create and edit searches, and export content from a Core eDiscovery case.</span></span>

<span data-ttu-id="3a1bd-129">完成下列步驟，將使用者新增至 eDiscovery 管理員角色群組：</span><span class="sxs-lookup"><span data-stu-id="3a1bd-129">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="3a1bd-130">移至[https://protection.office.com/permissions](https://protection.office.com/permissions)並使用您的 Microsoft 365 或 Office 365 組織中的系統管理員帳戶的認證登入。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-130">Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 or Office 365 organization.</span></span>

2. <span data-ttu-id="3a1bd-131">在 [**許可權**] 頁面上，選取 [ **eDiscovery 管理員**] 角色群組。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-131">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="3a1bd-132">在 [eDiscovery 管理員飛出] 頁面上，按一下 [ **Ediscovery 管理員**] 區段旁邊的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-132">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="3a1bd-133">在 [編輯角色群組] 嚮導的 [**選擇 EDiscovery 管理員**] 頁面上，按一下 **[選擇探索管理員**]。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-133">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose Discovery Manager**.</span></span>

5. <span data-ttu-id="3a1bd-134">按一下 [**新增**]，然後選取您要新增至角色群組之所有使用者的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-134">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="3a1bd-135">按一下 [**新增**] 以新增選取的使用者，然後按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-135">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="3a1bd-136">按一下 [**儲存**]，將使用者新增至角色群組，然後按一下 [**關閉**] 完成步驟。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-136">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="3a1bd-137">EDiscovery 管理員角色群組的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="3a1bd-137">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="3a1bd-138">EDiscovery 管理員角色群組中有兩個子群組。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-138">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="3a1bd-139">這些子群組之間的差異是以範圍為基礎。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-139">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="3a1bd-140">**EDiscovery 管理員：** 可以查看和管理其所建立或屬於的核心 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-140">**eDiscovery Manager:** Can view and manage the Core eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="3a1bd-141">如果另一個 eDiscovery 管理員建立了案例，但沒有將第二個 eDiscovery 管理員新增為該案例的成員，則第二個 eDiscovery 管理員將無法在規範中心的核心 eDiscovery 頁面上查看或開啟此案例。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-141">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Core eDiscovery page in the compliance center.</span></span> <span data-ttu-id="3a1bd-142">一般說來，您組織中的大部分人員都可以新增至 eDiscovery Manager 子組。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-142">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="3a1bd-143">**EDiscovery 管理員：** 可以執行 eDiscovery 管理員可以執行的所有案例管理工作。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-143">**eDiscovery Administrator:** Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="3a1bd-144">此外，電子檔探索管理員也可以：</span><span class="sxs-lookup"><span data-stu-id="3a1bd-144">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="3a1bd-145">查看核心 eDiscovery 頁面上列出的所有案例。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-145">View all cases that are listed on the Core eDiscovery page.</span></span>
  
  - <span data-ttu-id="3a1bd-146">管理組織中的任何案例後，將自己新增為案例成員。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-146">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="3a1bd-147">針對組織中的任何案例，存取及匯出案例資料。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-147">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="3a1bd-148">因為存取範圍廣泛，所以組織應該只有少數管理員是 eDiscovery Administrators 子群組的成員。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-148">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="3a1bd-149">如需有關 eDiscovery 許可權的詳細資訊，以及指派給 eDiscovery 管理員角色群組之每個角色的說明，請參閱[指派 eDiscovery 許可權](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-149">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-create-a-core-ediscovery-case"></a><span data-ttu-id="3a1bd-150">步驟3：建立核心 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="3a1bd-150">Step 3: Create a Core eDiscovery case</span></span>

<span data-ttu-id="3a1bd-151">下一步是建立案例，並開始使用核心 eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-151">The next step is to create a case and start using Core eDiscovery.</span></span> <span data-ttu-id="3a1bd-152">完成下列步驟以建立案例並新增成員。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-152">Complete the following steps to create a case and add members.</span></span> <span data-ttu-id="3a1bd-153">建立案例的使用者會自動新增為成員。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-153">The user who creates the case is automatically added as a member.</span></span>

1. <span data-ttu-id="3a1bd-154">移至[https://compliance.microsoft.com](https://compliance.microsoft.com)並登入使用已獲指派適當 eDiscovery 許可權之使用者帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for a user account that has been assigned the appropriate eDiscovery permissions.</span></span> <span data-ttu-id="3a1bd-155">組織管理角色群組的成員也可以建立核心 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-155">Members of the Organization Management role group can also create Core eDiscovery cases.</span></span>

2. <span data-ttu-id="3a1bd-156">在 Microsoft 365 規範中心的左功能窗格中，按一下 [**全部顯示**]，然後按一下 [ **eDiscovery > Core**]。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-156">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="3a1bd-157">在 [**核心電子**檔探索] 頁面上，按一下 [**建立案例**]。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-157">On the **Core eDiscovery** page, click **Create a case**.</span></span>

4. <span data-ttu-id="3a1bd-158">在 [**新案例**飛入] 頁面上，為案例提供名稱（必要），然後輸入選用的案例編號及描述。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-158">On the **New case** flyout page, give the case a name (required), and then type an optional case number and description.</span></span> <span data-ttu-id="3a1bd-159">案例名稱在您的組織中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-159">The case name must be unique in your organization.</span></span>

5. <span data-ttu-id="3a1bd-160">按一下 [**儲存**] 以建立案例。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-160">Click **Save** to create the case.</span></span>

   <span data-ttu-id="3a1bd-161">在核心 eDiscovery 頁面上建立及顯示新案例。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-161">The new case is created and displayed on the Core eDiscovery page.</span></span> <span data-ttu-id="3a1bd-162">您可能**需要按一下 [** 重新整理] 以顯示新的案例。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-162">You may have to click **Refresh** to display the new case.</span></span> 

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a><span data-ttu-id="3a1bd-163">步驟4（選用）：將成員新增至核心 eDiscovery 案例</span><span class="sxs-lookup"><span data-stu-id="3a1bd-163">Step 4 (optional): Add members to a Core eDiscovery case</span></span>

<span data-ttu-id="3a1bd-164">如果您在步驟3中建立案例，而且您是唯一會使用此案例的人員，則您不需要執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-164">If you create a case in Step 3 and you're the only person who will use the case, then you don't have to perform this step.</span></span> <span data-ttu-id="3a1bd-165">您可以開始使用案例來建立 eDiscovery 保留、搜尋內容或匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-165">You can start using the case to create eDiscovery holds, search for content, or export search results.</span></span> <span data-ttu-id="3a1bd-166">如果您想要授與其他使用者（或角色群組）存取案例，請執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-166">Perform this step if you want to give other users (or roles group) access to the case.</span></span>

1. <span data-ttu-id="3a1bd-167">在 Microsoft 365 規範中心的**核心 eDiscovery**頁面上，按一下您要新增成員的案例名稱。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-167">On the **Core eDiscovery** page in the Microsoft 365 compliance center, click the name of the case that you want to add members to.</span></span>

2. <span data-ttu-id="3a1bd-168">在 [**管理此案例**飛入] 頁面上的 [**管理成員**] 底下，按一下 [**新增**] 以將成員新增至案例。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-168">On the **Manage this case** flyout page, under **Manage members**, click **Add** to add members to the case.</span></span> 

    <span data-ttu-id="3a1bd-169">您也可以選擇新增角色群組做為案例的成員。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-169">You can also choose to add role group as members of a case.</span></span> <span data-ttu-id="3a1bd-170">在 [**管理角色群組**] 底下，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-170">Under **Manage role groups**, click **Add**.</span></span> <span data-ttu-id="3a1bd-171">您只能將您所屬的角色群組指派給案例。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-171">You can only assign the role groups that you are a member of to a case.</span></span> <span data-ttu-id="3a1bd-172">這是因為角色群組控制誰可以指派成員至 eDiscovery 案例。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-172">That's because role groups control who can assign members to an eDiscovery case.</span></span>

3. <span data-ttu-id="3a1bd-173">在可以新增為案例成員的人員或角色群組清單中，按一下您要新增之人員（或角色群組）名稱旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-173">In the list of people or role groups that can be added as members of the case, click the check box next to the names of the people (or role groups) that you want to add.</span></span> <span data-ttu-id="3a1bd-174">如果您有很多可以新增為成員的人員清單，請使用**搜尋**方塊來搜尋清單中的特定人員。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-174">If you have a large list of people who can added as members, use the **Search** box to search for a specific person in the list.</span></span>
  
4. <span data-ttu-id="3a1bd-175">選取要新增為案例成員的人員或角色群組之後，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-175">After you select the people or role groups to add as members of the case, click **Add**.</span></span>

5. <span data-ttu-id="3a1bd-176">按一下 [**儲存**] 儲存新的案例成員清單。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-176">Click **Save** to save the new list of case members.</span></span>

## <a name="explore-the-core-ediscovery-workflow"></a><span data-ttu-id="3a1bd-177">探索核心 eDiscovery 工作流程</span><span class="sxs-lookup"><span data-stu-id="3a1bd-177">Explore the Core eDiscovery workflow</span></span>

<span data-ttu-id="3a1bd-178">為了讓您開始使用核心 eDiscovery，以下是簡單的工作流程，可為感興趣的人員建立 eDiscovery 保留，搜尋與調查相關的內容，然後匯出該資料以進一步複查。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-178">To get you started using core eDiscovery, here's a simple workflow of creating eDiscovery holds for people of interest, searching for content that relevant to your investigation, and then exporting that data for further review.</span></span> <span data-ttu-id="3a1bd-179">在上述每個步驟中，我們也會強調您可以探索的一些擴充核心 eDiscovery 功能。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-179">In each of these steps, we'll also highlight some extended Core eDiscovery functionality that you can explore.</span></span>

![核心 eDiscovery 工作流程](../media/CoreEdiscoveryWorkflow.png)

1. <span data-ttu-id="3a1bd-181">**[建立 eDiscovery 保留](create-ediscovery-holds.md)**。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-181">**[Create an eDiscovery hold](create-ediscovery-holds.md)**.</span></span> <span data-ttu-id="3a1bd-182">在建立案例之後的第一個步驟是在調查中所關注之人員的內容位置保留（也稱為*eDiscovery 保留*）。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-182">The first step after creating a case is placing a hold (also called an *eDiscovery hold*) on the content locations of the people of interest in your investigation.</span></span> <span data-ttu-id="3a1bd-183">內容位置包含 Exchange 信箱、SharePoint 網站、OneDrive 帳戶，以及與 Microsoft 團隊和 Office 365 群組相關聯的信箱和網站。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-183">Content locations include Exchange mailboxes, SharePoint sites, OneDrive accounts, as well as the mailboxes and sites associated with Microsoft Teams and Office 365 Groups.</span></span> <span data-ttu-id="3a1bd-184">這是選用的步驟，建立 eDiscovery 保留可在調查期間保留與案例相關的內容。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-184">While this step is optional, creating an eDiscovery hold preserves content that may be relevant to the case during the investigation.</span></span> <span data-ttu-id="3a1bd-185">當您建立 eDiscovery 暫止功能時，您可以保留特定內容位置中的所有內容，也可以建立查詢型保留，只保留符合保留查詢的內容。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-185">When you create an eDiscovery hold you can preserve all content in specific content locations or you can create a query-based hold to preserve only the content that matches a hold query.</span></span> <span data-ttu-id="3a1bd-186">除了保留內容之外，另一個建立 eDiscovery 保留的最佳原因是，在下一個步驟中建立和執行搜尋時，請快速搜尋內容位置（而不是必須選取要搜尋的各個位置）。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-186">In addition to preserving content, another good reason to create eDiscovery holds is to quickly search the content locations on hold (instead of having to select each location to search) when you create and run searches in the next step.</span></span> <span data-ttu-id="3a1bd-187">完成調查之後，您可以放開您建立的任何保留。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-187">After you complete your investigation, you can release any hold that you created.</span></span>

2. <span data-ttu-id="3a1bd-188">**[搜尋內容](search-for-content-in-core-ediscovery.md)**。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-188">**[Search for content](search-for-content-in-core-ediscovery.md)**.</span></span> <span data-ttu-id="3a1bd-189">在您建立 eDiscovery 保留後，請使用內建的搜尋工具來搜尋保留中的內容位置。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-189">After you create eDiscovery holds, use the built-in search tool to search the content locations on hold.</span></span> <span data-ttu-id="3a1bd-190">您也可以在其他內容位置搜尋可能與案例相關的資料。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-190">You can also search other content locations for data that may be relevant to the case.</span></span> <span data-ttu-id="3a1bd-191">您可以建立及執行與案例相關聯的不同搜尋。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-191">You can create and run different searches that are associated with the case.</span></span> <span data-ttu-id="3a1bd-192">您可以使用關鍵字、屬性和條件來[建立搜尋查詢](keyword-queries-and-search-conditions.md)，以利用最可能與案例相關的資料傳回搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-192">You use keywords, properties, and conditions to [build search queries](keyword-queries-and-search-conditions.md) that return search results with the data that's most likely relevant to the case.</span></span> <span data-ttu-id="3a1bd-193">您也可以：</span><span class="sxs-lookup"><span data-stu-id="3a1bd-193">You can also:</span></span>

   - <span data-ttu-id="3a1bd-194">查看可協助您縮小搜尋查詢以縮小結果的搜尋統計資料。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-194">View search statistics that may help you refine a search query to narrow the results.</span></span>

   - <span data-ttu-id="3a1bd-195">預覽搜尋結果，以快速確認是否找到相關資料。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-195">Preview the search results to quickly verify whether the relevant data is being found.</span></span>

   - <span data-ttu-id="3a1bd-196">修改查詢，然後重新執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-196">Revise a query and rerun the search.</span></span>

3. <span data-ttu-id="3a1bd-197">**[匯出及下載搜尋結果](export-content-in-core-ediscovery.md)**。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-197">**[Export and download search results](export-content-in-core-ediscovery.md)**.</span></span> <span data-ttu-id="3a1bd-198">搜尋並找出與調查相關的資料之後，您可以將其匯出至 Office 365，以供調查小組以外的人員複查。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-198">After you search for and find data that's relevant to your investigation, you can export it out of Office 365 for review by people outside of the investigation team.</span></span> <span data-ttu-id="3a1bd-199">匯出資料的過程分為兩個步驟。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-199">Exporting data is a two-step process.</span></span> <span data-ttu-id="3a1bd-200">第一步是在不在 Office 365 的情況下，匯出搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-200">The first step is to export the results of a search in the case out of Office 365.</span></span> <span data-ttu-id="3a1bd-201">若要完成此工作，您可以將搜尋結果複製到 Microsoft 提供的 Azure 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-201">This is accomplished by copying the results of a search to a Microsoft-provided Azure Storage location.</span></span> <span data-ttu-id="3a1bd-202">下一步是使用 eDiscovery 匯出工具，將內容下載到本機電腦。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-202">The next step is to use the eDiscovery Export tool to download the content to a local computer.</span></span> <span data-ttu-id="3a1bd-203">除了匯出的資料檔案之外，匯出套件也包含匯出報告、摘要報告及錯誤報表。</span><span class="sxs-lookup"><span data-stu-id="3a1bd-203">In addition to the exported data files, the contains of the export package also contains an export report, a summary report, and an error report.</span></span>
