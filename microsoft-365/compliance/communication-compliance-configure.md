---
title: 開始使用通訊合規性
description: 設定通訊相容性原則，以設定使用者的通訊以進行審閱。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: a3c9aabd370117c085574144ff9450e74ae277c7
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527522"
---
# <a name="get-started-with-communication-compliance"></a><span data-ttu-id="ff35e-103">開始使用通訊合規性</span><span class="sxs-lookup"><span data-stu-id="ff35e-103">Get started with communication compliance</span></span>

<span data-ttu-id="ff35e-104">使用通訊相容性原則，識別內部或外部檢閱者進行檢查的使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="ff35e-104">Use communication compliance policies to identify user communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="ff35e-105">如需通訊相容性原則如何協助您監視組織中的通訊的詳細資訊，請參閱 [Microsoft 365 中的通訊相容性原則](communication-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="ff35e-105">For more information about how communication compliance policies can help you monitor communications in your organization, see [communication compliance policies in Microsoft 365](communication-compliance.md).</span></span> <span data-ttu-id="ff35e-106">如果您想要查看 Contoso 如何快速設定通訊相容性原則，以監視 Microsoft 小組、Exchange Online 和 Yammer 通訊中的冒犯性語言，請參閱此 [案例研究](communication-compliance-case-study.md)。</span><span class="sxs-lookup"><span data-stu-id="ff35e-106">If you'd like to review how Contoso quickly configured a communication compliance policy to monitor for offensive language in Microsoft Teams, Exchange Online, and Yammer communications, check out this [case study](communication-compliance-case-study.md).</span></span>

## <a name="subscriptions-and-licensing"></a><span data-ttu-id="ff35e-107">訂閱與授權</span><span class="sxs-lookup"><span data-stu-id="ff35e-107">Subscriptions and licensing</span></span>

<span data-ttu-id="ff35e-108">在您開始進行通訊相容性之前，您應該先確認您的 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 和任何附加元件。</span><span class="sxs-lookup"><span data-stu-id="ff35e-108">Before you get started with communication compliance, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="ff35e-109">若要存取及使用通訊相容性，您的組織必須具備下列其中一項訂閱或附加元件：</span><span class="sxs-lookup"><span data-stu-id="ff35e-109">To access and use communication compliance, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="ff35e-110">Microsoft 365 E5 訂閱 (付費或試用版本) </span><span class="sxs-lookup"><span data-stu-id="ff35e-110">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="ff35e-111">Microsoft 365 E3 訂閱 + Microsoft 365 E5 合規性附加元件</span><span class="sxs-lookup"><span data-stu-id="ff35e-111">Microsoft 365 E3 subscription + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="ff35e-112">Microsoft 365 E3 訂閱 + Microsoft 365 E5 「內幕人員風險管理附加元件」</span><span class="sxs-lookup"><span data-stu-id="ff35e-112">Microsoft 365 E3 subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="ff35e-113">Microsoft 365 A5 訂閱 (付費或試用版本) </span><span class="sxs-lookup"><span data-stu-id="ff35e-113">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="ff35e-114">Microsoft 365 A3 訂閱 + Microsoft 365 A5 合規性附加元件</span><span class="sxs-lookup"><span data-stu-id="ff35e-114">Microsoft 365 A3 subscription + the Microsoft 365 A5 Compliance add-on</span></span>
- <span data-ttu-id="ff35e-115">Microsoft 365 A3 訂閱 + Microsoft 365 A5 內幕人士風險管理附加元件</span><span class="sxs-lookup"><span data-stu-id="ff35e-115">Microsoft 365 A3 subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="ff35e-116">Microsoft 365 G5 訂閱 (付費或試用版本) </span><span class="sxs-lookup"><span data-stu-id="ff35e-116">Microsoft 365 G5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="ff35e-117">Microsoft 365 G5 訂閱 + Microsoft 365 G5 合規性附加元件</span><span class="sxs-lookup"><span data-stu-id="ff35e-117">Microsoft 365 G5 subscription + the Microsoft 365 G5 Compliance add-on</span></span>
- <span data-ttu-id="ff35e-118">Microsoft 365 G5 訂閱 + Microsoft 365 G5 有問必答風險管理附加元件</span><span class="sxs-lookup"><span data-stu-id="ff35e-118">Microsoft 365 G5 subscription + the Microsoft 365 G5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="ff35e-119">Office 365 企業版 E5 訂閱 (付費或試用版本) </span><span class="sxs-lookup"><span data-stu-id="ff35e-119">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="ff35e-120">Office 365 A5 訂閱 (付費或試用版本) </span><span class="sxs-lookup"><span data-stu-id="ff35e-120">Office 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="ff35e-121">Office 365 企業版 E3 訂閱 + Office 365 Advanced 合規性附加元件 (已無法再供新訂閱使用，請參閱記事) </span><span class="sxs-lookup"><span data-stu-id="ff35e-121">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="ff35e-122">必須將上述其中一個授權指派給通訊符合性原則中所含的使用者。</span><span class="sxs-lookup"><span data-stu-id="ff35e-122">Users included in communication compliance policies must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="ff35e-123">Office 365 Advanced 合規性不再銷售為獨立訂閱。</span><span class="sxs-lookup"><span data-stu-id="ff35e-123">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="ff35e-124">當目前的訂閱到期時，客戶應轉換至上述其中一個訂閱，其中包含相同或其他的符合性功能。</span><span class="sxs-lookup"><span data-stu-id="ff35e-124">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="ff35e-125">如果您沒有現有的 Office 365 企業版 E5 計畫，而且想要嘗試通訊相容性，您可以 [將 Microsoft 365 新增](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 至現有的訂閱，或註冊 Office 365 Enterprise E5 的 [試用版](https://www.microsoft.com/microsoft-365/enterprise) 。</span><span class="sxs-lookup"><span data-stu-id="ff35e-125">If you don't have an existing Office 365 Enterprise E5 plan and want to try communication compliance, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Office 365 Enterprise E5.</span></span>

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a><span data-ttu-id="ff35e-126">步驟 1 (必要) ：啟用通訊相容性的許可權</span><span class="sxs-lookup"><span data-stu-id="ff35e-126">Step 1 (required): Enable permissions for communication compliance</span></span>

>[!Important]
><span data-ttu-id="ff35e-127">根據預設，全域管理員無法存取通訊規範功能。</span><span class="sxs-lookup"><span data-stu-id="ff35e-127">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="ff35e-128">在此步驟中所指派的角色是必要的通訊相容性功能才能存取。</span><span class="sxs-lookup"><span data-stu-id="ff35e-128">The roles assigned in this step are required before any communication compliance features will be accessible.</span></span> <span data-ttu-id="ff35e-129">設定角色群組之後，最多可能需要30分鐘的時間，才能將角色群組許可權套用至組織中指派給指派的使用者。</span><span class="sxs-lookup"><span data-stu-id="ff35e-129">After configuring your role groups, it may take up to 30 minutes for the role group permissions to apply to assigned users across your organization.</span></span>

<span data-ttu-id="ff35e-130">有五個角色群組可用來設定管理通訊符合性功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="ff35e-130">There are five role groups used to configure permissions to manage communication compliance features.</span></span> <span data-ttu-id="ff35e-131">若要在 Microsoft 365 規範中心中以功能表選項的方式提供 **通訊相容性** ，並繼續這些設定步驟，您必須指派給 *通訊合規性* 或 *通訊合規性系統管理員* 角色群組。</span><span class="sxs-lookup"><span data-stu-id="ff35e-131">To make **Communication compliance** available as a menu option in Microsoft 365 compliance center and to continue with these configuration steps, you must be assigned to the *Communication Compliance* or *Communication Compliance Admin* role groups.</span></span> <span data-ttu-id="ff35e-132">若要在初始設定之後存取及管理通訊相容性功能，使用者必須是至少一個通訊合規性角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ff35e-132">To access and manage communication compliance features after initial configuration, users must be a member of at least one communication compliance role group.</span></span>

<span data-ttu-id="ff35e-133">視您想要管理通訊原則及警示的方式而定，您必須將使用者指派給特定角色群組。</span><span class="sxs-lookup"><span data-stu-id="ff35e-133">Depending on how you wish to manage communication policies and alerts, you'll need to assign users to specific role groups.</span></span> <span data-ttu-id="ff35e-134">您可以選擇將具有不同規範責任的使用者指派給特定角色群組，以管理不同的通訊相容性功能範圍。</span><span class="sxs-lookup"><span data-stu-id="ff35e-134">You have the option to assign users with different compliance responsibilities to specific role groups to manage different areas of communication compliance features.</span></span> <span data-ttu-id="ff35e-135">或者，您也可以決定將指定系統管理員、分析員、調查人員和檢視器的所有使用者帳戶指派給 *通訊合規性* 角色群組。</span><span class="sxs-lookup"><span data-stu-id="ff35e-135">Or you may decide to assign all user accounts for designated administrators, analysts, investigators, and viewers to the *Communication Compliance* role group.</span></span> <span data-ttu-id="ff35e-136">請使用單一角色群組或多個角色群組，盡可能符合您的規範管理需求。</span><span class="sxs-lookup"><span data-stu-id="ff35e-136">Use a single role group or multiple role groups to best fit your compliance management requirements.</span></span>

<span data-ttu-id="ff35e-137">設定通訊相容性時，請從下列角色群組選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="ff35e-137">Choose from these role group options when configuring communication compliance:</span></span>

| <span data-ttu-id="ff35e-138">角色</span><span class="sxs-lookup"><span data-stu-id="ff35e-138">Role</span></span> | <span data-ttu-id="ff35e-139">角色權限</span><span class="sxs-lookup"><span data-stu-id="ff35e-139">Role permissions</span></span> |
|:-----|:-----|
| <span data-ttu-id="ff35e-140">**通訊相容性**</span><span class="sxs-lookup"><span data-stu-id="ff35e-140">**Communication Compliance**</span></span> | <span data-ttu-id="ff35e-141">使用此角色群組來管理單一群組中組織的通訊相容性。</span><span class="sxs-lookup"><span data-stu-id="ff35e-141">Use this role group to manage communication compliance for your organization in a single group.</span></span> <span data-ttu-id="ff35e-142">新增指派管理員、分析員、調查人員和檢視器的所有使用者帳戶，您可以在單一群組中設定通訊合規性許可權。</span><span class="sxs-lookup"><span data-stu-id="ff35e-142">By adding all user accounts for designated administrators, analysts, investigators, and viewers, you can configure communication compliance permissions in a single group.</span></span> <span data-ttu-id="ff35e-143">此角色群組包含所有通訊符合性許可權角色。</span><span class="sxs-lookup"><span data-stu-id="ff35e-143">This role group contains all the communication compliance permission roles.</span></span> <span data-ttu-id="ff35e-144">這項設定是快速開始使用通訊相容性的最簡單方法，而且很適合不需要個別使用者群組定義個別許可權的組織。</span><span class="sxs-lookup"><span data-stu-id="ff35e-144">This configuration is the easiest way to quickly get started with communication compliance and is a good fit for organizations that do not need separate permissions defined for separate groups of users.</span></span> |
| <span data-ttu-id="ff35e-145">**通訊合規性管理**</span><span class="sxs-lookup"><span data-stu-id="ff35e-145">**Communication Compliance Admin**</span></span> | <span data-ttu-id="ff35e-146">使用此角色群組開始設定通訊相容性和更新後，以將通訊合規性管理員隔離成定義的群組。</span><span class="sxs-lookup"><span data-stu-id="ff35e-146">Use this role group to initially configure communication compliance and later to segregate communication compliance administrators into a defined group.</span></span> <span data-ttu-id="ff35e-147">指派給此角色群組的使用者，可以建立、讀取、更新和刪除通訊符合性原則、全域設定和角色群組指派。</span><span class="sxs-lookup"><span data-stu-id="ff35e-147">Users assigned to this role group can create, read, update, and delete communication compliance policies, global settings, and role group assignments.</span></span> <span data-ttu-id="ff35e-148">指派給此角色群組的使用者無法查看郵件警示。</span><span class="sxs-lookup"><span data-stu-id="ff35e-148">Users assigned to this role group cannot view message alerts.</span></span> |
| <span data-ttu-id="ff35e-149">**通訊法規遵從性分析師**</span><span class="sxs-lookup"><span data-stu-id="ff35e-149">**Communication Compliance Analyst**</span></span> | <span data-ttu-id="ff35e-150">使用此群組可將許可權指派給將充當通訊相容性分析員的使用者。</span><span class="sxs-lookup"><span data-stu-id="ff35e-150">Use this group to assign permissions to users that will act as communication compliance analysts.</span></span> <span data-ttu-id="ff35e-151">指派給此角色群組的使用者可以查看其被指派為檢閱者的原則、查看郵件中繼資料 (非郵件內容) 、升級至其他檢閱者，或傳送通知給使用者。</span><span class="sxs-lookup"><span data-stu-id="ff35e-151">Users assigned to this role group can view policies where they are assigned as Reviewers, view message metadata (not message content), escalate to additional reviewers, or send notifications to users.</span></span> <span data-ttu-id="ff35e-152">分析員無法解析待處理的警示。</span><span class="sxs-lookup"><span data-stu-id="ff35e-152">Analysts cannot resolve pending alerts.</span></span> |
| <span data-ttu-id="ff35e-153">**通訊合規性調查員**</span><span class="sxs-lookup"><span data-stu-id="ff35e-153">**Communication Compliance Investigator**</span></span> | <span data-ttu-id="ff35e-154">使用此群組可將許可權指派給將充當通訊合規性調查人員的使用者。</span><span class="sxs-lookup"><span data-stu-id="ff35e-154">Use this group to assign permissions to users that will act as communication compliance investigators.</span></span> <span data-ttu-id="ff35e-155">指派給此角色群組的使用者可以查看郵件中繼資料和內容、升級至其他檢閱者、升級至高級 eDiscovery 案例、將通知傳送給使用者，以及解決警示。</span><span class="sxs-lookup"><span data-stu-id="ff35e-155">Users assigned to this role group can view message metadata and content, escalate to additional reviewers, escalate to an Advanced eDiscovery case, send notifications to users, and resolve the alert.</span></span> |
| <span data-ttu-id="ff35e-156">**通訊規範檢視器**</span><span class="sxs-lookup"><span data-stu-id="ff35e-156">**Communication Compliance Viewer**</span></span> | <span data-ttu-id="ff35e-157">使用此群組可將管理通訊報告的許可權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="ff35e-157">Use this group to assign permissions to users that will manage communication reports.</span></span> <span data-ttu-id="ff35e-158">指派給此角色群組的使用者，可以存取通訊合規性首頁上的所有報告元件，並可以查看所有的通訊符合性報告。</span><span class="sxs-lookup"><span data-stu-id="ff35e-158">Users assigned to this role group can access all reporting widgets on the communication compliance home page and can view all communication compliance reports.</span></span> |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a><span data-ttu-id="ff35e-159">選項1：將所有規範使用者指派給通訊合規性角色群組</span><span class="sxs-lookup"><span data-stu-id="ff35e-159">Option 1: Assign all compliance users to the Communication Compliance role group</span></span>

1. <span data-ttu-id="ff35e-160">使用 Microsoft 365 組織中的系統管理員帳戶認證登入[https://protection.office.com/permissions](https://protection.office.com/permissions)。</span><span class="sxs-lookup"><span data-stu-id="ff35e-160">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="ff35e-161">在安全性與 &amp; 合規性中心，移至 [ **許可權**]。</span><span class="sxs-lookup"><span data-stu-id="ff35e-161">In the Security &amp; Compliance Center, go to **Permissions**.</span></span> <span data-ttu-id="ff35e-162">選取連結，以在 Office 365 中檢視及管理角色。</span><span class="sxs-lookup"><span data-stu-id="ff35e-162">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="ff35e-163">選取 [ *通訊合規性* ] 角色群組，然後選取 [ **編輯角色群組**]。</span><span class="sxs-lookup"><span data-stu-id="ff35e-163">Select the *Communication Compliance* role group, then select **Edit role group**.</span></span>

4. <span data-ttu-id="ff35e-164">在左側瀏覽窗格中選取 **[選擇成員]**，然後選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="ff35e-164">Select **Choose members** from the left navigation pane, then select **Edit**.</span></span>

5. <span data-ttu-id="ff35e-165">選取 [ **新增** ]，然後選取您要新增至 *通訊符合性* 角色群組之所有使用者的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ff35e-165">Select **Add** and then select the checkbox for all users you want to add to the *Communication Compliance* role group.</span></span>

6. <span data-ttu-id="ff35e-166">選取 **[新增]**，然後選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ff35e-166">Select **Add**, then select **Done**.</span></span>

7. <span data-ttu-id="ff35e-167">選取 **[儲存]** 以將使用者新增至角色群組。</span><span class="sxs-lookup"><span data-stu-id="ff35e-167">Select **Save** to add the users to the role group.</span></span> <span data-ttu-id="ff35e-168">選取 [ **關閉** ] 以完成步驟</span><span class="sxs-lookup"><span data-stu-id="ff35e-168">Select **Close** to complete the steps</span></span>

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a><span data-ttu-id="ff35e-169">選項2：將使用者指派給特定的通訊符合性角色群組</span><span class="sxs-lookup"><span data-stu-id="ff35e-169">Option 2: Assign users to specific communication compliance role groups</span></span>

<span data-ttu-id="ff35e-170">使用此選項可將使用者指派給特定角色群組，以分割組織中不同使用者之間的通訊一致性存取和責任。</span><span class="sxs-lookup"><span data-stu-id="ff35e-170">Use this option to assign users to specific role groups to segment communication compliance access and responsibilities among different users in your organization.</span></span>

1. <span data-ttu-id="ff35e-171">使用 Microsoft 365 組織中的系統管理員帳戶認證登入[https://protection.office.com/permissions](https://protection.office.com/permissions)。</span><span class="sxs-lookup"><span data-stu-id="ff35e-171">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="ff35e-172">在安全性與 &amp; 合規性中心，移至 [ **許可權**]。</span><span class="sxs-lookup"><span data-stu-id="ff35e-172">In the Security &amp; Compliance Center, go to **Permissions**.</span></span> <span data-ttu-id="ff35e-173">選取連結，以在 Office 365 中檢視及管理角色。</span><span class="sxs-lookup"><span data-stu-id="ff35e-173">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="ff35e-174">選取其中一個通訊符合性角色群組，然後選取 [ **編輯角色群組**]。</span><span class="sxs-lookup"><span data-stu-id="ff35e-174">Select one of the communication compliance role groups, then select **Edit role group**.</span></span>

4. <span data-ttu-id="ff35e-175">在左側瀏覽窗格中選取 **[選擇成員]**，然後選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="ff35e-175">Select **Choose members** from the left navigation pane, then select **Edit**.</span></span>

5. <span data-ttu-id="ff35e-176">選取 **[新增]**，然後針對所有要新增至角色群組的使用者勾選核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ff35e-176">Select **Add** and then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="ff35e-177">選取 **[新增]**，然後選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ff35e-177">Select **Add**, then select **Done**.</span></span>

7. <span data-ttu-id="ff35e-178">選取 **[儲存]** 以將使用者新增至角色群組。</span><span class="sxs-lookup"><span data-stu-id="ff35e-178">Select **Save** to add the users to the role group.</span></span>

8. <span data-ttu-id="ff35e-179">選取下一個通訊符合性角色群組，然後針對每個必要的角色群組重複步驟4-7。</span><span class="sxs-lookup"><span data-stu-id="ff35e-179">Select the next communication compliance role group, then repeat steps 4-7 for each required role group.</span></span>

9. <span data-ttu-id="ff35e-180">選取 **[關閉]** 以完成步驟。</span><span class="sxs-lookup"><span data-stu-id="ff35e-180">Select **Close** to complete the steps.</span></span>

<span data-ttu-id="ff35e-181">如需角色群組和權限的詳細資訊，請參閱[規範中心的權限](../security/office-365-security/protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="ff35e-181">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

## <a name="step-2-required-enable-the-audit-log"></a><span data-ttu-id="ff35e-182">步驟 2 (必要) ：啟用審核記錄檔</span><span class="sxs-lookup"><span data-stu-id="ff35e-182">Step 2 (required): Enable the audit log</span></span>

<span data-ttu-id="ff35e-183">通訊合規性需要「審核記錄檔」顯示提醒，並追蹤檢閱者採取的修復動作。</span><span class="sxs-lookup"><span data-stu-id="ff35e-183">Communication compliance requires audit logs to show alerts and track remediation actions taken by reviewers.</span></span> <span data-ttu-id="ff35e-184">「審核記錄檔」會摘要所有與已定義的組織原則相關聯的活動，或在任何時刻的通訊合規性原則變更時。</span><span class="sxs-lookup"><span data-stu-id="ff35e-184">The audit logs are a summary of all activities associated with a defined organizational policy or anytime a communication compliance policy changes.</span></span>

<span data-ttu-id="ff35e-185">如需開啟審計的逐步指示，請參閱 [開啟或關閉審計記錄搜尋](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="ff35e-185">For step-by-step instructions to turn on auditing, see [Turn audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="ff35e-186">在您開啟審核後，會顯示一則訊息，指出已準備好審核記錄，而且您可以在準備完成後數小時執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="ff35e-186">After you turn on auditing, a message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="ff35e-187">您只需執行這項動作一次。</span><span class="sxs-lookup"><span data-stu-id="ff35e-187">You only have to do this action once.</span></span> <span data-ttu-id="ff35e-188">如需使用審核記錄的詳細資訊，請參閱 [搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。</span><span class="sxs-lookup"><span data-stu-id="ff35e-188">For more information about the using the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a><span data-ttu-id="ff35e-189">步驟 3 (選用) ：設定通訊相容性群組</span><span class="sxs-lookup"><span data-stu-id="ff35e-189">Step 3 (optional): Set up groups for communication compliance</span></span>

 <span data-ttu-id="ff35e-190">當您建立通訊相容性原則時，您會定義誰會檢查其通訊，以及誰會執行評論。</span><span class="sxs-lookup"><span data-stu-id="ff35e-190">When you create a communication compliance policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="ff35e-191">在原則中，您將使用電子郵件地址來識別個人或人員群組。</span><span class="sxs-lookup"><span data-stu-id="ff35e-191">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="ff35e-192">若要簡化您的設定，您可以為進行通訊檢查的使用者建立群組，並為審查這些通訊的使用者群組建立群組。</span><span class="sxs-lookup"><span data-stu-id="ff35e-192">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="ff35e-193">如果您正在使用群組，可能需要數個。</span><span class="sxs-lookup"><span data-stu-id="ff35e-193">If you're using groups, you may need several.</span></span> <span data-ttu-id="ff35e-194">例如，如果您想要監視兩個不同的使用者群組之間的通訊，或是想要指定不會受到監督的群組。</span><span class="sxs-lookup"><span data-stu-id="ff35e-194">For example, if you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="ff35e-195">使用下列圖表可協助您設定組織中的通訊遵循原則的群組：</span><span class="sxs-lookup"><span data-stu-id="ff35e-195">Use the following chart to help you configure groups in your organization for communication compliance policies:</span></span>

| <span data-ttu-id="ff35e-196">**原則成員**</span><span class="sxs-lookup"><span data-stu-id="ff35e-196">**Policy Member**</span></span> | <span data-ttu-id="ff35e-197">**支援的群組**</span><span class="sxs-lookup"><span data-stu-id="ff35e-197">**Supported Groups**</span></span> | <span data-ttu-id="ff35e-198">**不支援的群組**</span><span class="sxs-lookup"><span data-stu-id="ff35e-198">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="ff35e-199">監督的使用者</span><span class="sxs-lookup"><span data-stu-id="ff35e-199">Supervised users</span></span> <br> <span data-ttu-id="ff35e-200">非監督的使用者</span><span class="sxs-lookup"><span data-stu-id="ff35e-200">Non-supervised users</span></span> | <span data-ttu-id="ff35e-201">通訊群組</span><span class="sxs-lookup"><span data-stu-id="ff35e-201">Distribution groups</span></span> <br> <span data-ttu-id="ff35e-202">Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="ff35e-202">Microsoft 365 Groups</span></span> | <span data-ttu-id="ff35e-203">動態通訊群組</span><span class="sxs-lookup"><span data-stu-id="ff35e-203">Dynamic distribution groups</span></span> <br> <span data-ttu-id="ff35e-204">嵌套通訊群組</span><span class="sxs-lookup"><span data-stu-id="ff35e-204">Nested distribution groups</span></span> <br> <span data-ttu-id="ff35e-205">擁有郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="ff35e-205">Mail-enabled security groups</span></span> |
| <span data-ttu-id="ff35e-206">檢閱者</span><span class="sxs-lookup"><span data-stu-id="ff35e-206">Reviewers</span></span> | <span data-ttu-id="ff35e-207">無</span><span class="sxs-lookup"><span data-stu-id="ff35e-207">None</span></span> | <span data-ttu-id="ff35e-208">通訊群組</span><span class="sxs-lookup"><span data-stu-id="ff35e-208">Distribution groups</span></span> <br> <span data-ttu-id="ff35e-209">動態通訊群組</span><span class="sxs-lookup"><span data-stu-id="ff35e-209">Dynamic distribution groups</span></span> <br> <span data-ttu-id="ff35e-210">嵌套通訊群組</span><span class="sxs-lookup"><span data-stu-id="ff35e-210">Nested distribution groups</span></span> <br> <span data-ttu-id="ff35e-211">擁有郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="ff35e-211">Mail-enabled security groups</span></span> |
  
<span data-ttu-id="ff35e-212">當您指派原則中的通訊群組時，該原則會監控通訊群組中每個使用者的所有電子郵件和團隊聊天。</span><span class="sxs-lookup"><span data-stu-id="ff35e-212">When you assign a distribution group in the policy, the policy monitors all emails and Teams chats from each user in distribution group.</span></span> <span data-ttu-id="ff35e-213">當您在原則中指派 Microsoft 365 群組時，原則會監控傳送至該群組的所有電子郵件和團隊聊天，而不是每個群組成員所收到的個別電子郵件和聊天。</span><span class="sxs-lookup"><span data-stu-id="ff35e-213">When you assign a Microsoft 365 group in the policy, the policy monitors all emails and Teams chats sent to that group, not the individual emails and chats received by each group member.</span></span>

<span data-ttu-id="ff35e-214">如果您是具有 Exchange 內部部署或外部電子郵件提供者的組織，且您想要為使用者監視 Microsoft 團隊聊天，您必須為使用內部部署或外部信箱進行監視的使用者建立通訊群組。</span><span class="sxs-lookup"><span data-stu-id="ff35e-214">If you're an organization with an Exchange on-premises deployment or an external email provider and you want to monitor Microsoft Teams chats for your users, you must create a distribution group for the users with on-premises or external mailboxes to monitor.</span></span> <span data-ttu-id="ff35e-215">在上述步驟中，您會將此通訊群組指派為 [原則嚮導] 中的 [授與 **群組** ] 選擇。</span><span class="sxs-lookup"><span data-stu-id="ff35e-215">Later in these steps, you'll assign this distribution group as the **Supervised users and groups** selection in the policy wizard.</span></span>

>[!IMPORTANT]
><span data-ttu-id="ff35e-216">您必須向 Microsoft 支援服務提交要求，才能讓組織使用安全性與合規性中心的圖形化使用者介面來搜尋內部部署使用者的 Teams 聊天資料。</span><span class="sxs-lookup"><span data-stu-id="ff35e-216">You must file a request with Microsoft Support to enable your organization to use the graphical user interface in the Security & Compliance Center to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="ff35e-217">如需詳細資訊，請參閱針對 [內部部署使用者搜尋雲端架構信箱](search-cloud-based-mailboxes-for-on-premises-users.md)。</span><span class="sxs-lookup"><span data-stu-id="ff35e-217">For more information, see [Searching cloud-based mailboxes for on-premises users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>

<span data-ttu-id="ff35e-218">如需設定群組的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="ff35e-218">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="ff35e-219">建立並管理通訊群組</span><span class="sxs-lookup"><span data-stu-id="ff35e-219">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="ff35e-220">Microsoft 365 群組的概述</span><span class="sxs-lookup"><span data-stu-id="ff35e-220">Overview of Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a><span data-ttu-id="ff35e-221">步驟 4 (選用) ：確認 Yammer 租使用者處於原生模式</span><span class="sxs-lookup"><span data-stu-id="ff35e-221">Step 4 (optional): Verify your Yammer tenant is in Native Mode</span></span>

<span data-ttu-id="ff35e-222">在純模式中，所有 Yammer 使用者都在 Azure Active Directory 中 (Azure AD) ，所有群組都是 Office 365 群組，而且所有檔案都儲存在 SharePoint 線上中。</span><span class="sxs-lookup"><span data-stu-id="ff35e-222">In Native Mode, all Yammer users are in Azure Active Directory (Azure AD), all groups are Office 365 Groups, and all files are stored in SharePoint Online.</span></span> <span data-ttu-id="ff35e-223">您的 Yammer 租使用者必須採用原生模式，以進行通訊相容性原則，以掃描及識別 Yammer 中的私人郵件和社區交談中有風險的交談。</span><span class="sxs-lookup"><span data-stu-id="ff35e-223">Your Yammer tenant must be in Native Mode for communication compliance policies to scan and identify risky conversations in private messages and community conversations in Yammer.</span></span>

<span data-ttu-id="ff35e-224">如需在原生模式中設定 Yammer 的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="ff35e-224">For more information about configuring Yammer in Native Mode, see:</span></span>

- [<span data-ttu-id="ff35e-225">Microsoft 365 中的 Yammer 原生模式概述</span><span class="sxs-lookup"><span data-stu-id="ff35e-225">Overview of Yammer Native Mode in Microsoft 365</span></span>](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)
- [<span data-ttu-id="ff35e-226">針對 Microsoft 365 設定您的 Yammer 網路使用原生模式</span><span class="sxs-lookup"><span data-stu-id="ff35e-226">Configure your Yammer network for Native Mode for Microsoft 365</span></span>](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a><span data-ttu-id="ff35e-227">步驟 5 (必要) ：建立通訊相容性原則</span><span class="sxs-lookup"><span data-stu-id="ff35e-227">Step 5 (required): Create a communication compliance policy</span></span>
  
>[!Important]
><span data-ttu-id="ff35e-228">不支援使用 PowerShell 建立及管理通訊相容性原則。</span><span class="sxs-lookup"><span data-stu-id="ff35e-228">Using PowerShell to create and manage communication compliance policies is not supported.</span></span> <span data-ttu-id="ff35e-229">若要建立及管理這些原則，您必須使用 [Microsoft 365 通訊規範解決方案](https://compliance.microsoft.com/supervisoryreview)中的原則管理控制項。</span><span class="sxs-lookup"><span data-stu-id="ff35e-229">To create and manage these policies, you must use the policy management controls in the [Microsoft 365 communication compliance solution](https://compliance.microsoft.com/supervisoryreview).</span></span>

1. <span data-ttu-id="ff35e-230">使用 Microsoft 365 組織中的系統管理員帳戶認證登入[https://compliance.microsoft.com](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="ff35e-230">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="ff35e-231">在 [Microsoft 365 規範中心] 中，選取 [ **通訊符合性**]。</span><span class="sxs-lookup"><span data-stu-id="ff35e-231">In the Microsoft 365 compliance center, select **Communication compliance**.</span></span>
  
3. <span data-ttu-id="ff35e-232">選取 [原則] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ff35e-232">Select the **Policies** tab.</span></span>

4. <span data-ttu-id="ff35e-233">選取 [ **建立原則** ]，以從範本建立及設定新原則，或建立及設定自訂原則。</span><span class="sxs-lookup"><span data-stu-id="ff35e-233">Select **Create policy** to create and configure a new policy from a template or to create and configure a custom policy.</span></span>

    <span data-ttu-id="ff35e-234">如果您選擇原則範本以建立原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="ff35e-234">If you choose a policy template to create a policy, you will:</span></span>

    - <span data-ttu-id="ff35e-235">確認或更新原則名稱。</span><span class="sxs-lookup"><span data-stu-id="ff35e-235">Confirm or update the policy name.</span></span> <span data-ttu-id="ff35e-236">建立原則之後，便無法變更原則名稱。</span><span class="sxs-lookup"><span data-stu-id="ff35e-236">Policy names cannot be changed once the policy is created.</span></span>
    
    - <span data-ttu-id="ff35e-237">選擇要監督的使用者或群組，包括選擇您想要排除的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="ff35e-237">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    
    - <span data-ttu-id="ff35e-238">選擇原則的檢閱者。</span><span class="sxs-lookup"><span data-stu-id="ff35e-238">Choose the reviewers for the policy.</span></span> <span data-ttu-id="ff35e-239">「檢閱者」是個別的使用者，而且所有檢閱者都必須在 Exchange Online 上主控信箱。</span><span class="sxs-lookup"><span data-stu-id="ff35e-239">Reviewers are individual users and all reviewers must have mailboxes hosted on Exchange Online.</span></span> <span data-ttu-id="ff35e-240">在此新增的檢閱者是在調查和修正工作流程中升級提醒時，可選擇的檢閱者。</span><span class="sxs-lookup"><span data-stu-id="ff35e-240">Reviewers added here are the reviewers that you can choose from when escalating an alert in the investigation and remediation workflow.</span></span> <span data-ttu-id="ff35e-241">當檢閱者新增至原則時，會自動收到一封電子郵件，通知他們對原則的指派，並提供審閱程式相關資訊的連結。</span><span class="sxs-lookup"><span data-stu-id="ff35e-241">When reviewers are added to a policy, they automatically receive an email message that notifies them of the assignment to the policy and provides links to information about the review process.</span></span>
    
    - <span data-ttu-id="ff35e-242">選擇 [有限條件] 欄位，通常是要套用至原則的敏感資訊類型或關鍵字字典。</span><span class="sxs-lookup"><span data-stu-id="ff35e-242">Choose a limited condition field, usually a sensitive info type or keyword dictionary to apply to the policy.</span></span>

    <span data-ttu-id="ff35e-243">如果您選擇使用原則嚮導建立自訂原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="ff35e-243">If you choose to use the policy wizard to create a custom policy, you will:</span></span>

    - <span data-ttu-id="ff35e-244">將原則命名為 [名稱] 和 [描述]。</span><span class="sxs-lookup"><span data-stu-id="ff35e-244">Give the policy a name and description.</span></span> <span data-ttu-id="ff35e-245">建立原則之後，便無法變更原則名稱。</span><span class="sxs-lookup"><span data-stu-id="ff35e-245">Policy names can't be changed once the policy is created.</span></span>
    
    - <span data-ttu-id="ff35e-246">選擇要監督的使用者或群組，包括您組織中的所有使用者、特定使用者和群組，或是您想要排除的其他使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="ff35e-246">Choose the users or groups to supervise, including all users in your organization, specific users and groups, or other users and groups you'd like to exclude.</span></span>
    
    - <span data-ttu-id="ff35e-247">選擇原則的檢閱者。</span><span class="sxs-lookup"><span data-stu-id="ff35e-247">Choose the reviewers for the policy.</span></span> <span data-ttu-id="ff35e-248">「檢閱者」是個別的使用者，而且所有檢閱者都必須在 Exchange Online 上主控信箱。</span><span class="sxs-lookup"><span data-stu-id="ff35e-248">Reviewers are individual users and all reviewers must have mailboxes hosted on Exchange Online.</span></span> <span data-ttu-id="ff35e-249">在此新增的檢閱者是在調查和修正工作流程中升級提醒時，可選擇的檢閱者。</span><span class="sxs-lookup"><span data-stu-id="ff35e-249">Reviewers added here are the reviewers that you can choose from when escalating an alert in the investigation and remediation workflow.</span></span> <span data-ttu-id="ff35e-250">當檢閱者新增至原則時，會自動收到一封電子郵件，通知他們對原則的指派，並提供審閱程式相關資訊的連結。</span><span class="sxs-lookup"><span data-stu-id="ff35e-250">When reviewers are added to a policy, they automatically receive an email message that notifies them of the assignment to the policy and provides links to information about the review process.</span></span>
    
    - <span data-ttu-id="ff35e-251">選擇要掃描的通訊通道，包括 Exchange、Microsoft 團隊、Yammer 或商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="ff35e-251">Choose the communication channels to scan, including Exchange, Microsoft Teams, Yammer, or Skype for Business.</span></span> <span data-ttu-id="ff35e-252">如果您已在 Microsoft 365 中設定連接器，您也會選擇掃描協力廠商來源。</span><span class="sxs-lookup"><span data-stu-id="ff35e-252">You'll also choose to scan third-party sources if you've configured a connector in Microsoft 365.</span></span>
    
    - <span data-ttu-id="ff35e-253">選擇要監視的通訊方向，包括輸入、輸出或內部通訊。</span><span class="sxs-lookup"><span data-stu-id="ff35e-253">Choose the communication direction to monitor, including inbound, outbound, or internal communications.</span></span>
    
    - <span data-ttu-id="ff35e-254">定義通訊相容性原則 [條件](communication-compliance-feature-reference.md#ConditionalSettings)。</span><span class="sxs-lookup"><span data-stu-id="ff35e-254">Define the communication compliance policy [conditions](communication-compliance-feature-reference.md#ConditionalSettings).</span></span> <span data-ttu-id="ff35e-255">您可以選擇 [郵寄地址]、[關鍵字]、[檔案類型] 和 [大小相符] 條件。</span><span class="sxs-lookup"><span data-stu-id="ff35e-255">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    
    - <span data-ttu-id="ff35e-256">選擇是否要包含機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ff35e-256">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="ff35e-257">在這個步驟中，您可以選取預設和自訂的機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ff35e-257">This step is where you can select default and custom sensitive info types.</span></span> <span data-ttu-id="ff35e-258">在 [通訊合規性原則] 中，從現有的自訂敏感資訊類型或自訂關鍵字字典中挑選。</span><span class="sxs-lookup"><span data-stu-id="ff35e-258">Pick from existing custom sensitive information types or custom keyword dictionaries in the communication compliance policy wizard.</span></span> <span data-ttu-id="ff35e-259">如有需要，您可以在執行該嚮導之前建立這些專案。</span><span class="sxs-lookup"><span data-stu-id="ff35e-259">You can create these items before running the wizard if needed.</span></span> <span data-ttu-id="ff35e-260">您也可以從通訊合規性原則嚮導中建立新的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ff35e-260">You can also create new sensitive information types from within the communication compliance policy wizard.</span></span>
    
    - <span data-ttu-id="ff35e-261">選擇是否要啟用分類器。</span><span class="sxs-lookup"><span data-stu-id="ff35e-261">Choose if you'd like to enable classifiers.</span></span> <span data-ttu-id="ff35e-262">分類器可以偵測電子郵件訊息或其他類型的文字內傳送或接收的不適當語言和圖像。</span><span class="sxs-lookup"><span data-stu-id="ff35e-262">Classifiers can detect inappropriate language and images sent or received in the body of email messages or other types of text.</span></span> <span data-ttu-id="ff35e-263">您可以選擇下列內建的分類符： *威脅*、 *猥褻*、 *目標騷擾*、 *成人影像*、 *Racy 影像* 和 *Gory 影像*。</span><span class="sxs-lookup"><span data-stu-id="ff35e-263">You can choose the following built-in classifiers: *Threat*, *Profanity*, *Targeted harassment*, *Adult images*, *Racy images*, and *Gory images*.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="ff35e-264">我們正在淘汰 [粗穢言語] 內建分類器，因為這個分類器產生了大量的誤報。</span><span class="sxs-lookup"><span data-stu-id="ff35e-264">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="ff35e-265">請勿使用它，如果您目前使用它，您應該將商務程式移出它。</span><span class="sxs-lookup"><span data-stu-id="ff35e-265">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="ff35e-266">我們建議您改用 **威脅**、 **猥褻** 和 **目標騷擾** 內建的分類符。</span><span class="sxs-lookup"><span data-stu-id="ff35e-266">We recommend using the **Threat**, **Profanity**, and **Targeted harassment** built-in classifiers instead.</span></span>

    - <span data-ttu-id="ff35e-267">定義要複查的通訊百分比。</span><span class="sxs-lookup"><span data-stu-id="ff35e-267">Define the percentage of communications to review.</span></span>
    
    - <span data-ttu-id="ff35e-268">檢查您的原則選擇並建立原則。</span><span class="sxs-lookup"><span data-stu-id="ff35e-268">Review your policy selections and create the policy.</span></span>

5. <span data-ttu-id="ff35e-269">使用 [自訂原則] 嚮導時，選取 [使用範本或 **提交** 時 **建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="ff35e-269">Select **Create policy** when using the templates or **Submit** when using the custom policy wizard.</span></span>

6. <span data-ttu-id="ff35e-270">**已建立您** 的原則頁面會隨著原則的啟動時間及將捕獲哪些通訊的指導方針來顯示。</span><span class="sxs-lookup"><span data-stu-id="ff35e-270">The **Your policy was created** page is displayed with guidelines on when policy will be activated and which communications will be captured.</span></span>

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a><span data-ttu-id="ff35e-271">步驟 6 (選用) ：建立公告範本及設定使用者匿名</span><span class="sxs-lookup"><span data-stu-id="ff35e-271">Step 6 (optional): Create notice templates and configure user anonymization</span></span>

<span data-ttu-id="ff35e-272">如果您想要選擇以傳送提醒通知給關聯的使用者來回應原則警示，您必須在組織中至少建立一個公告範本。</span><span class="sxs-lookup"><span data-stu-id="ff35e-272">If you want to have the option of responding to a policy alert by sending a reminder notice to the associated user, you'll need to create at least one notice template in your organization.</span></span> <span data-ttu-id="ff35e-273">[！注意事項] [通知範本] 欄位是可編輯的，在傳送為警示修復程式的一部分之前，建議您為每個通訊相容性原則建立自訂的通知範本。</span><span class="sxs-lookup"><span data-stu-id="ff35e-273">The notice template fields are editable before they're sent as part of the alert remediation process, and creating a customized notice template for each communication compliance policy is recommended.</span></span>

<span data-ttu-id="ff35e-274">您也可以選擇在調查原則符合和對郵件採取動作時，啟用顯示之使用者的匿名。</span><span class="sxs-lookup"><span data-stu-id="ff35e-274">You can also choose to enable anonymization for displayed usernames when investigating policy matches and taking action on messages.</span></span>

1. <span data-ttu-id="ff35e-275">使用 Microsoft 365 組織中的系統管理員帳戶認證登入[https://compliance.microsoft.com](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="ff35e-275">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="ff35e-276">在 Microsoft 365 規範中心內，移至 [ **通訊符合性**]。</span><span class="sxs-lookup"><span data-stu-id="ff35e-276">In the Microsoft 365 compliance center, go to **Communication compliance**.</span></span>

3. <span data-ttu-id="ff35e-277">若要設定匿名的使用者名，請選取 [ **隱私權** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ff35e-277">To configure anonymization for usernames, select the **Privacy** tab.</span></span>

4. <span data-ttu-id="ff35e-278">若要啟用匿名，請選取 [ **顯示匿名版本的使用者名**]。</span><span class="sxs-lookup"><span data-stu-id="ff35e-278">To enable anonymization, select **Show anonymized versions of usernames**.</span></span>

5. <span data-ttu-id="ff35e-279">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="ff35e-279">Select **Save**.</span></span>

6. <span data-ttu-id="ff35e-280">流覽至 [ **公告範本** ] 索引標籤，然後選取 [ **建立公告範本**]。</span><span class="sxs-lookup"><span data-stu-id="ff35e-280">Navigate to the **Notice templates** tab and then select **Create notice template**.</span></span>

7. <span data-ttu-id="ff35e-281">在 [ **修改公告範本** ] 頁面上，完成下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="ff35e-281">On the **Modify a notice template** page, complete the following fields:</span></span>

    - <span data-ttu-id="ff35e-282">範本名稱 (必要) </span><span class="sxs-lookup"><span data-stu-id="ff35e-282">Template name (required)</span></span>
    - <span data-ttu-id="ff35e-283"> (必要的傳送) </span><span class="sxs-lookup"><span data-stu-id="ff35e-283">Send from (required)</span></span>
    - <span data-ttu-id="ff35e-284">抄送和 Bcc (選用) </span><span class="sxs-lookup"><span data-stu-id="ff35e-284">Cc and Bcc (optional)</span></span>
    - <span data-ttu-id="ff35e-285">主體 (必要) </span><span class="sxs-lookup"><span data-stu-id="ff35e-285">Subject (required)</span></span>
    - <span data-ttu-id="ff35e-286">需要郵件內文 () </span><span class="sxs-lookup"><span data-stu-id="ff35e-286">Message body (required)</span></span>

8. <span data-ttu-id="ff35e-287">選取 [ **儲存** ] 以建立及儲存 [公告] 範本。</span><span class="sxs-lookup"><span data-stu-id="ff35e-287">Select **Save** to create and save the notice template.</span></span>

## <a name="step-7-optional-test-your-communication-compliance-policy"></a><span data-ttu-id="ff35e-288">步驟 7 (選用) ：測試通訊合規性原則</span><span class="sxs-lookup"><span data-stu-id="ff35e-288">Step 7 (optional): Test your communication compliance policy</span></span>

<span data-ttu-id="ff35e-289">在您建立通訊相容性原則之後，建議您加以測試，以確定原則已正確地強制執行您所定義的條件。</span><span class="sxs-lookup"><span data-stu-id="ff35e-289">After you create a communication compliance policy, it's a good idea to test it to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="ff35e-290">您也可以在通訊相容性原則包括敏感資訊類型時， [測試您的資料遺失防護 (DLP) 原則](create-test-tune-dlp-policy.md) 。</span><span class="sxs-lookup"><span data-stu-id="ff35e-290">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your communication compliance policies include sensitive information types.</span></span> <span data-ttu-id="ff35e-291">請務必提供您的原則啟動時間，以便您想要測試的通訊得以捕獲。</span><span class="sxs-lookup"><span data-stu-id="ff35e-291">Make sure you give your policies time to activate so that the communications you want to test are captured.</span></span>

<span data-ttu-id="ff35e-292">請遵循下列步驟來測試您的通訊合規性原則：</span><span class="sxs-lookup"><span data-stu-id="ff35e-292">Follow these steps to test your communication compliance policy:</span></span>

1. <span data-ttu-id="ff35e-293">在您要測試之原則中所定義的監督使用者登入時，開啟電子郵件客戶程式、Microsoft 小組或 Yammer。</span><span class="sxs-lookup"><span data-stu-id="ff35e-293">Open an email client, Microsoft Teams, or Yammer while signed in as a supervised user defined in the policy you want to test.</span></span>

2. <span data-ttu-id="ff35e-294">傳送電子郵件、Microsoft 小組聊天或 Yammer 訊息，其符合您在通訊相容性原則中所定義的準則。</span><span class="sxs-lookup"><span data-stu-id="ff35e-294">Send an email, Microsoft Teams chat, or Yammer message that meets the criteria you've defined in the communication compliance policy.</span></span> <span data-ttu-id="ff35e-295">此測試可以是關鍵字、附件大小、網域等等。確定您判斷原則中設定的設定條件設定過於嚴格或太 lenient。</span><span class="sxs-lookup"><span data-stu-id="ff35e-295">This test can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ff35e-296">在原則中，電子郵件訊息最多可能需要24小時才能完全處理。</span><span class="sxs-lookup"><span data-stu-id="ff35e-296">Email messages can take up to 24 hours to fully process in a policy.</span></span> <span data-ttu-id="ff35e-297">在 Microsoft 小組、Yammer 和協力廠商平臺中的通訊可能需要長達48小時才能完整處理原則。</span><span class="sxs-lookup"><span data-stu-id="ff35e-297">Communications in Microsoft Teams, Yammer, and third-party platforms can take up to 48 hours to fully process in a policy.</span></span>

3. <span data-ttu-id="ff35e-298">以通訊合規性原則中指定的檢閱者身分登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="ff35e-298">Sign in to Microsoft 365 as a reviewer designated in the communication compliance policy.</span></span> <span data-ttu-id="ff35e-299">流覽至 [**通訊相容性**  >  **警示**]，以查看原則的警示。</span><span class="sxs-lookup"><span data-stu-id="ff35e-299">Navigate to **Communication compliance** > **Alerts** to view the alerts for your policies.</span></span>

4. <span data-ttu-id="ff35e-300">使用修正控制措施修正警示，並確認已正確解決警示。</span><span class="sxs-lookup"><span data-stu-id="ff35e-300">Remediate the alert using the remediation controls and verify that the alert is properly resolved.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ff35e-301">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ff35e-301">Next steps</span></span>

<span data-ttu-id="ff35e-302">當您完成這些步驟來建立您的第一個通訊符合性原則之後，您將在24-48 小時後開始從活動指示器接收提醒。</span><span class="sxs-lookup"><span data-stu-id="ff35e-302">After you've completed these steps to create your first communication compliance policy, you'll start to receive alerts from activity indicators after 24-48 hours.</span></span> <span data-ttu-id="ff35e-303">根據需要使用本文步驟5的指導方針設定其他原則。</span><span class="sxs-lookup"><span data-stu-id="ff35e-303">Configure additional policies as needed using the guidance in Step 5 of this article.</span></span>

<span data-ttu-id="ff35e-304">若要深入瞭解如何調查通訊相容性警示，請參閱 [調查和修正通訊相容性警示](communication-compliance-investigate-remediate.md)。</span><span class="sxs-lookup"><span data-stu-id="ff35e-304">To learn more about investigating communication compliance alerts, see [Investigate and remediate communication compliance alerts](communication-compliance-investigate-remediate.md).</span></span>
