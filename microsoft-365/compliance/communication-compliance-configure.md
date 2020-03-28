---
title: 設定通訊相容性
description: 設定通訊相容性原則，以設定員工交流以供審查。
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
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 87be266fe9c117afdaf68b66db5d4cf4c7a3d94e
ms.sourcegitcommit: ce6121a8e3ca7438071d73b0c76e2b6f33ac1cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/27/2020
ms.locfileid: "43029889"
---
# <a name="configure-communication-compliance-in-microsoft-365"></a><span data-ttu-id="cfa56-103">設定 Microsoft 365 中的通訊合規性</span><span class="sxs-lookup"><span data-stu-id="cfa56-103">Configure communication compliance in Microsoft 365</span></span>

>[!IMPORTANT]
><span data-ttu-id="cfa56-104">本主題適用于設定 Microsoft 365 訂閱中的通訊相容性。</span><span class="sxs-lookup"><span data-stu-id="cfa56-104">This topic applies to configuring communication compliance in a Microsoft 365 subscription.</span></span> <span data-ttu-id="cfa56-105">如果您想要為 Office 365 訂閱設定監察原則，請參閱[設定 office 365 的監管](supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="cfa56-105">If you want to configure Supervision policies for an Office 365 subscription, see [Configure supervision for Office 365](supervision-policies.md).</span></span>

<span data-ttu-id="cfa56-106">使用通訊相容性原則來捕獲員工透過內部或外部檢閱者進行檢查的通訊。</span><span class="sxs-lookup"><span data-stu-id="cfa56-106">Use communication compliance policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="cfa56-107">如需通訊相容性原則如何協助您監視組織中的通訊的詳細資訊，請參閱[Microsoft 365 中的通訊相容性原則](communication-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="cfa56-107">For more information about how communication compliance policies can help you monitor communications in your organization, see [communication compliance policies in Microsoft 365](communication-compliance.md).</span></span> <span data-ttu-id="cfa56-108">如果您想要查看 Contoso 如何快速設定通訊相容性原則，以監視 Microsoft 小組和 Exchange Online 通訊中的冒犯性語言，請參閱此[案例研究](communication-compliance-case-study.md)。</span><span class="sxs-lookup"><span data-stu-id="cfa56-108">If you'd like to review how Contoso quickly configured a communication compliance policy to monitor for offensive language in Microsoft Teams and Exchange Online communications, check out this [case study](communication-compliance-case-study.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cfa56-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="cfa56-109">Before you begin</span></span>

<span data-ttu-id="cfa56-110">在您開始進行通訊相容性之前，您應該先確認您的 Microsoft 365 訂閱。</span><span class="sxs-lookup"><span data-stu-id="cfa56-110">Before you get started with communication compliance, you should confirm your Microsoft 365 subscription.</span></span> <span data-ttu-id="cfa56-111">通訊相容性原則中所含的使用者必須具備 Microsoft 365 E5 相容性授權、具有高級合規性附加元件的 Office 365 企業版 E3 授權，或是包含在 Office 365 企業版 E5 訂閱中，或包含在 Microsoft365 E5 訂閱。</span><span class="sxs-lookup"><span data-stu-id="cfa56-111">Users included in communication compliance policies must have a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription, or be included in a Microsoft 365 E5 subscription.</span></span>

<span data-ttu-id="cfa56-112">如果您沒有 Microsoft 365 企業版 E5 方案，且想要試用測試人員風險管理，您可以[將 Microsoft 365 新增](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)至現有的 Office 365 訂閱，或[註冊 Microsoft 365 企業版 E5 的試用版](https://www.microsoft.com/microsoft-365/enterprise)。</span><span class="sxs-lookup"><span data-stu-id="cfa56-112">If you don't have an existing Microsoft 365 Enterprise E5 plan and want to try insider risk management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>
  
<span data-ttu-id="cfa56-113">完成下列步驟，以在您的 Microsoft 365 組織中設定與使用通訊合規性：</span><span class="sxs-lookup"><span data-stu-id="cfa56-113">Complete these steps to set up and use communication compliance in your Microsoft 365 organization:</span></span>

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a><span data-ttu-id="cfa56-114">步驟1（必要）：啟用通訊相容性的許可權</span><span class="sxs-lookup"><span data-stu-id="cfa56-114">Step 1 (required): Enable permissions for communication compliance</span></span>

>[!Important]
><span data-ttu-id="cfa56-115">根據預設，全域管理員無法存取通訊規範功能。</span><span class="sxs-lookup"><span data-stu-id="cfa56-115">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="cfa56-116">在此步驟中所指派的角色是必要的通訊相容性功能才能存取。</span><span class="sxs-lookup"><span data-stu-id="cfa56-116">The roles assigned in this step are required before any communication compliance features will be accessible.</span></span>

<span data-ttu-id="cfa56-117">若要在 Microsoft 365 規範中心中以功能表選項的方式使用**通訊相容性**，您必須獲指派**主管審查系統管理員**角色。</span><span class="sxs-lookup"><span data-stu-id="cfa56-117">To make **Communication compliance** available as a menu option in Microsoft 365 compliance center, you must be assigned the **Supervisory Review Administrator** role.</span></span> <span data-ttu-id="cfa56-118">您必須建立新的角色群組供**主管審查系統管理員**、**案例管理**、**合規性管理員**，以及**審查**角色，以透過原則相符的方式調查和修正郵件。</span><span class="sxs-lookup"><span data-stu-id="cfa56-118">You must create a new role group for reviewers with the **Supervisory Review Administrator**, **Case Management**, **Compliance Administrator**, and **Review** roles to investigate and remediate messages with policy matches.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="cfa56-119">建立新的角色群組</span><span class="sxs-lookup"><span data-stu-id="cfa56-119">Create a new role group</span></span>

1. <span data-ttu-id="cfa56-120">使用 Microsoft 365 組織中的系統管理員帳戶認證登入[https://protection.office.com/permissions](https://protection.office.com/permissions)。</span><span class="sxs-lookup"><span data-stu-id="cfa56-120">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="cfa56-121">在 Microsoft Office 365 安全性與合規合規性中心，移至 **[權限]**。</span><span class="sxs-lookup"><span data-stu-id="cfa56-121">In the Microsoft Office 365 security and compliance center, go to **Permissions**.</span></span> <span data-ttu-id="cfa56-122">選取連結，以在 Office 365 中檢視及管理角色。</span><span class="sxs-lookup"><span data-stu-id="cfa56-122">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="cfa56-123">選取 **[建立]**。</span><span class="sxs-lookup"><span data-stu-id="cfa56-123">Select **Create**.</span></span>

4. <span data-ttu-id="cfa56-124">在 **[名稱]** 欄位中，為新的角色群組取個好記的名稱。</span><span class="sxs-lookup"><span data-stu-id="cfa56-124">In the **Name** field, give the new role group a friendly name.</span></span> <span data-ttu-id="cfa56-125">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfa56-125">Select **Next**.</span></span>

5. <span data-ttu-id="cfa56-126">選取 **[選擇角色]**，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="cfa56-126">Select **Choose roles** and then select **Add**.</span></span> <span data-ttu-id="cfa56-127">選取「**主管審查管理員**」、「**案例管理**」、「**合規性管理員**」及「**複查**」的核取方塊，然後選取 [**新增**並**完成**]。</span><span class="sxs-lookup"><span data-stu-id="cfa56-127">Select the checkbox for **Supervisory Review Administrator**, **Case Management**, **Compliance Administrator**, and **Review**, then select **Add** and **Done**.</span></span> <span data-ttu-id="cfa56-128">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cfa56-128">Select **Next**.</span></span>

    ![通訊規範必要的角色群組](../media/communication-compliance-role-groups-1.png)

6. <span data-ttu-id="cfa56-130">選取 **[選擇成員]**，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="cfa56-130">Select **Choose members** and then select **Add**.</span></span> <span data-ttu-id="cfa56-131">針對要建立原則的所有使用者和群組勾選核取方塊，並使用原則符合項目管理訊息，然後選取 **[新增]** 和 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="cfa56-131">Select the checkbox for all the users and groups you want create policies and manage messages with policy matches, then select **Add** and **Done**.</span></span> <span data-ttu-id="cfa56-132">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="cfa56-132">Select **Next**.</span></span>

7. <span data-ttu-id="cfa56-133">選取 **[建立角色群組]** 來完成。</span><span class="sxs-lookup"><span data-stu-id="cfa56-133">Select **Create role group** to finish.</span></span>

<span data-ttu-id="cfa56-134">如需角色群組和權限的詳細資訊，請參閱[規範中心的權限](../security/office-365-security/protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="cfa56-134">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

## <a name="step-2-required-enable-the-office-365-audit-log"></a><span data-ttu-id="cfa56-135">步驟2（必要）：啟用 Office 365 審核記錄</span><span class="sxs-lookup"><span data-stu-id="cfa56-135">Step 2 (required): Enable the Office 365 audit log</span></span>

<span data-ttu-id="cfa56-136">通訊合規性需要「審核記錄檔」顯示提醒，並追蹤檢閱者採取的修復動作。</span><span class="sxs-lookup"><span data-stu-id="cfa56-136">Communication compliance requires audit logs to show alerts and track remediation actions taken by reviewers.</span></span> <span data-ttu-id="cfa56-137">「審核記錄檔」會摘要所有與已定義的組織原則相關聯的活動，或在任何時刻的通訊合規性原則變更時。</span><span class="sxs-lookup"><span data-stu-id="cfa56-137">The audit logs are a summary of all activities associated with a defined organizational policy or anytime a communication compliance policy changes.</span></span>

<span data-ttu-id="cfa56-138">如需開啟審核的逐步指示，請參閱[開啟或關閉 Office 365 審核記錄搜尋](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="cfa56-138">For step-by-step instructions to turn on auditing, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="cfa56-139">在您開啟審核後，會顯示一則訊息，指出已準備好審核記錄，而且您可以在準備完成後數小時執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="cfa56-139">After you turn on auditing, a message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="cfa56-140">您只需執行這項動作一次。</span><span class="sxs-lookup"><span data-stu-id="cfa56-140">You only have to do this action once.</span></span> <span data-ttu-id="cfa56-141">如需使用審核記錄的詳細資訊，請參閱[搜尋審核記錄](search-the-audit-log-in-security-and-compliance.md)檔。</span><span class="sxs-lookup"><span data-stu-id="cfa56-141">For more information about the using the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a><span data-ttu-id="cfa56-142">步驟3（選用）：設定通訊相容性群組</span><span class="sxs-lookup"><span data-stu-id="cfa56-142">Step 3 (optional): Set up groups for communication compliance</span></span>

 <span data-ttu-id="cfa56-143">當您建立通訊相容性原則時，您會定義誰會檢查其通訊，以及誰會執行評論。</span><span class="sxs-lookup"><span data-stu-id="cfa56-143">When you create a communication compliance policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="cfa56-144">在原則中，您將使用電子郵件地址來識別個人或人員群組。</span><span class="sxs-lookup"><span data-stu-id="cfa56-144">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="cfa56-145">若要簡化您的設定，您可以為進行通訊檢查的使用者建立群組，並為審查這些通訊的使用者群組建立群組。</span><span class="sxs-lookup"><span data-stu-id="cfa56-145">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="cfa56-146">如果您正在使用群組，可能需要數個。</span><span class="sxs-lookup"><span data-stu-id="cfa56-146">If you're using groups, you may need several.</span></span> <span data-ttu-id="cfa56-147">例如，如果您想要監視兩個不同的使用者群組之間的通訊，或是想要指定不會受到監督的群組。</span><span class="sxs-lookup"><span data-stu-id="cfa56-147">For example, if you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="cfa56-148">使用下列圖表可協助您設定組織中的通訊遵循原則的群組：</span><span class="sxs-lookup"><span data-stu-id="cfa56-148">Use the following chart to help you configure groups in your organization for communication compliance policies:</span></span>

| <span data-ttu-id="cfa56-149">**原則成員**</span><span class="sxs-lookup"><span data-stu-id="cfa56-149">**Policy Member**</span></span> | <span data-ttu-id="cfa56-150">**支援的群組**</span><span class="sxs-lookup"><span data-stu-id="cfa56-150">**Supported Groups**</span></span> | <span data-ttu-id="cfa56-151">**不支援的群組**</span><span class="sxs-lookup"><span data-stu-id="cfa56-151">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="cfa56-152">監督的使用者</span><span class="sxs-lookup"><span data-stu-id="cfa56-152">Supervised users</span></span> <br> <span data-ttu-id="cfa56-153">非監督的使用者</span><span class="sxs-lookup"><span data-stu-id="cfa56-153">Non-supervised users</span></span> | <span data-ttu-id="cfa56-154">通訊群組</span><span class="sxs-lookup"><span data-stu-id="cfa56-154">Distribution groups</span></span> <br> <span data-ttu-id="cfa56-155">Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="cfa56-155">Office 365 groups</span></span> | <span data-ttu-id="cfa56-156">動態通訊群組</span><span class="sxs-lookup"><span data-stu-id="cfa56-156">Dynamic distribution groups</span></span> |
| <span data-ttu-id="cfa56-157">檢閱者</span><span class="sxs-lookup"><span data-stu-id="cfa56-157">Reviewers</span></span> | <span data-ttu-id="cfa56-158">無</span><span class="sxs-lookup"><span data-stu-id="cfa56-158">None</span></span> | <span data-ttu-id="cfa56-159">通訊群組</span><span class="sxs-lookup"><span data-stu-id="cfa56-159">Distribution groups</span></span> <br> <span data-ttu-id="cfa56-160">動態通訊群組</span><span class="sxs-lookup"><span data-stu-id="cfa56-160">Dynamic distribution groups</span></span> <br> <span data-ttu-id="cfa56-161">擁有郵件功能的安全性群組</span><span class="sxs-lookup"><span data-stu-id="cfa56-161">Mail-enabled security groups</span></span> |
  
<span data-ttu-id="cfa56-162">當您為監督的使用者選取 Office 365 群組時，該原則會監控共用 Office 365 信箱的內容，以及與群組相關聯的 Microsoft 小組頻道。</span><span class="sxs-lookup"><span data-stu-id="cfa56-162">When you select an Office 365 group for supervised users, the policy monitors the content of the shared Office 365 mailbox and the Microsoft Teams channels associated with the group.</span></span> <span data-ttu-id="cfa56-163">當您選取通訊群組清單時，該原則會監控個別的使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="cfa56-163">When you select a distribution list, the policy monitors individual user mailboxes.</span></span>

<span data-ttu-id="cfa56-164">如需設定群組的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="cfa56-164">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="cfa56-165">建立並管理通訊群組</span><span class="sxs-lookup"><span data-stu-id="cfa56-165">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="cfa56-166">Office 365 群組的概述</span><span class="sxs-lookup"><span data-stu-id="cfa56-166">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-4-required-create-a-communication-compliance-policy"></a><span data-ttu-id="cfa56-167">步驟4（必要）：建立通訊相容性原則</span><span class="sxs-lookup"><span data-stu-id="cfa56-167">Step 4 (required): Create a communication compliance policy</span></span>
  
>[!Important]
><span data-ttu-id="cfa56-168">不支援使用 PowerShell 建立及管理通訊相容性原則。</span><span class="sxs-lookup"><span data-stu-id="cfa56-168">Using PowerShell to create and manage communication compliance policies is not supported.</span></span> <span data-ttu-id="cfa56-169">若要建立及管理這些原則，您必須使用[Microsoft 365 通訊規範解決方案](https://compliance.microsoft.com/supervisoryreview)中的原則管理控制項。</span><span class="sxs-lookup"><span data-stu-id="cfa56-169">To create and manage these policies, you must use the policy management controls in the [Microsoft 365 communication compliance solution](https://compliance.microsoft.com/supervisoryreview).</span></span>

1. <span data-ttu-id="cfa56-170">使用 Microsoft 365 組織中的系統管理員帳戶認證登入[https://compliance.microsoft.com](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="cfa56-170">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="cfa56-171">在 [Microsoft 365 規範中心] 中，選取 [**通訊符合性**]。</span><span class="sxs-lookup"><span data-stu-id="cfa56-171">In the Microsoft 365 compliance center, select **Communication compliance**.</span></span>
  
3. <span data-ttu-id="cfa56-172">選取 [原則] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="cfa56-172">Select the **Policies** tab.</span></span>

4. <span data-ttu-id="cfa56-173">選取 [**建立原則**]，以從範本建立及設定新原則，或建立及設定自訂原則。</span><span class="sxs-lookup"><span data-stu-id="cfa56-173">Select **Create policy** to create and configure a new policy from a template or to create and configure a custom policy.</span></span>

    <span data-ttu-id="cfa56-174">如果您選擇原則範本以建立原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="cfa56-174">If you choose a policy template to create a policy, you will:</span></span>

    - <span data-ttu-id="cfa56-175">確認或更新原則名稱。</span><span class="sxs-lookup"><span data-stu-id="cfa56-175">Confirm or update the policy name.</span></span> <span data-ttu-id="cfa56-176">建立原則之後，便無法變更原則名稱。</span><span class="sxs-lookup"><span data-stu-id="cfa56-176">Policy names cannot be changed once the policy is created.</span></span>
    - <span data-ttu-id="cfa56-177">選擇要監督的使用者或群組，包括選擇您想要排除的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="cfa56-177">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="cfa56-178">選擇原則的檢閱者。</span><span class="sxs-lookup"><span data-stu-id="cfa56-178">Choose the reviewers for the policy.</span></span> <span data-ttu-id="cfa56-179">「檢閱者」是個別的使用者，而且所有檢閱者都必須在 Exchange Online 上主控信箱。</span><span class="sxs-lookup"><span data-stu-id="cfa56-179">Reviewers are individual users and all reviewers must have mailboxes hosted on Exchange Online.</span></span> <span data-ttu-id="cfa56-180">在此新增的檢閱者是在調查和修正工作流程中升級提醒時，可選擇的檢閱者。</span><span class="sxs-lookup"><span data-stu-id="cfa56-180">Reviewers added here are the reviewers that you can choose from when escalating an alert in the investigation and remediation workflow.</span></span>
    - <span data-ttu-id="cfa56-181">選擇 [有限條件] 欄位，通常是要套用至原則的敏感資訊類型或關鍵字字典。</span><span class="sxs-lookup"><span data-stu-id="cfa56-181">Choose a limited condition field, usually a sensitive info type or keyword dictionary to apply to the policy.</span></span>

    <span data-ttu-id="cfa56-182">如果您選擇使用原則嚮導建立自訂原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="cfa56-182">If you choose to use the policy wizard to create a custom policy, you will:</span></span>

    - <span data-ttu-id="cfa56-183">將原則命名為 [名稱] 和 [描述]。</span><span class="sxs-lookup"><span data-stu-id="cfa56-183">Give the policy a name and description.</span></span> <span data-ttu-id="cfa56-184">建立原則之後，便無法變更原則名稱。</span><span class="sxs-lookup"><span data-stu-id="cfa56-184">Policy names can't be changed once the policy is created.</span></span>
    - <span data-ttu-id="cfa56-185">選擇要監督的使用者或群組，包括您組織中的所有使用者、特定使用者和群組，或是您想要排除的其他使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="cfa56-185">Choose the users or groups to supervise, including all users in your organization, specific users and groups, or other users and groups you'd like to exclude.</span></span>
    - <span data-ttu-id="cfa56-186">選擇原則的檢閱者。</span><span class="sxs-lookup"><span data-stu-id="cfa56-186">Choose the reviewers for the policy.</span></span> <span data-ttu-id="cfa56-187">「檢閱者」是個別的使用者，而且所有檢閱者都必須在 Exchange Online 上主控信箱。</span><span class="sxs-lookup"><span data-stu-id="cfa56-187">Reviewers are individual users and all reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="cfa56-188">選擇要掃描的通訊通道，包括 Exchange、Microsoft 團隊或商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="cfa56-188">Choose the communication channels to scan, including Exchange, Microsoft Teams, or Skype for Business.</span></span> <span data-ttu-id="cfa56-189">如果您已在 Microsoft 365 中設定連接器，您也會選擇掃描協力廠商來源。</span><span class="sxs-lookup"><span data-stu-id="cfa56-189">You'll also choose to scan third-party sources if you've configured a connector in Microsoft 365.</span></span>
    - <span data-ttu-id="cfa56-190">選擇要監視的通訊方向，包括輸入、輸出或內部通訊。</span><span class="sxs-lookup"><span data-stu-id="cfa56-190">Choose the communication direction to monitor, including inbound, outbound, or internal communications.</span></span>
    - <span data-ttu-id="cfa56-191">定義通訊相容性原則[條件](communication-compliance-feature-reference.md#ConditionalSettings)。</span><span class="sxs-lookup"><span data-stu-id="cfa56-191">Define the communication compliance policy [conditions](communication-compliance-feature-reference.md#ConditionalSettings).</span></span> <span data-ttu-id="cfa56-192">您可以選擇 [郵寄地址]、[關鍵字]、[檔案類型] 和 [大小相符] 條件。</span><span class="sxs-lookup"><span data-stu-id="cfa56-192">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    - <span data-ttu-id="cfa56-193">選擇是否要包含機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cfa56-193">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="cfa56-194">在這個步驟中，您可以選取預設和自訂的機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cfa56-194">This step is where you can select default and custom sensitive info types.</span></span> <span data-ttu-id="cfa56-195">在 [通訊合規性原則] 中，從現有的自訂敏感資訊類型或自訂關鍵字字典中挑選。</span><span class="sxs-lookup"><span data-stu-id="cfa56-195">Pick from existing custom sensitive information types or custom keyword dictionaries in the communication compliance policy wizard.</span></span> <span data-ttu-id="cfa56-196">如有需要，您可以在執行該嚮導之前建立這些專案。</span><span class="sxs-lookup"><span data-stu-id="cfa56-196">You can create these items before running the wizard if needed.</span></span> <span data-ttu-id="cfa56-197">您也可以從通訊合規性原則嚮導中建立新的敏感資訊類型。</span><span class="sxs-lookup"><span data-stu-id="cfa56-197">You can also create new sensitive information types from within the communication compliance policy wizard.</span></span>
    - <span data-ttu-id="cfa56-198">選擇是否要啟用冒犯性語言分類器。</span><span class="sxs-lookup"><span data-stu-id="cfa56-198">Choose if you'd like to enable the offensive language classifier.</span></span> <span data-ttu-id="cfa56-199">此分類器會偵測到電子郵件內送出或接收到不適當的語言。</span><span class="sxs-lookup"><span data-stu-id="cfa56-199">This  classifier detects inappropriate language sent or received in the body of email messages.</span></span>
    - <span data-ttu-id="cfa56-200">定義要複查的通訊百分比。</span><span class="sxs-lookup"><span data-stu-id="cfa56-200">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="cfa56-201">檢查您的原則選擇並建立原則。</span><span class="sxs-lookup"><span data-stu-id="cfa56-201">Review your policy selections and create the policy.</span></span>

5. <span data-ttu-id="cfa56-202">使用 [自訂原則] 嚮導時，選取 [使用範本或**提交**時**建立原則**]。</span><span class="sxs-lookup"><span data-stu-id="cfa56-202">Select **Create policy** when using the templates or **Submit** when using the custom policy wizard.</span></span>

6. <span data-ttu-id="cfa56-203">**已建立您**的原則頁面會隨著原則的啟動時間及將捕獲哪些通訊的指導方針來顯示。</span><span class="sxs-lookup"><span data-stu-id="cfa56-203">The **Your policy was created** page is displayed with guidelines on when policy will be activated and which communications will be captured.</span></span>

## <a name="step-5-optional-create-employee-notice-templates"></a><span data-ttu-id="cfa56-204">步驟5（選用）：建立員工通知範本</span><span class="sxs-lookup"><span data-stu-id="cfa56-204">Step 5 (optional): Create employee notice templates</span></span>

<span data-ttu-id="cfa56-205">如果您想要選擇以傳送提醒通知給關聯的員工來回應原則警示，您必須在組織中至少建立一個公告範本。</span><span class="sxs-lookup"><span data-stu-id="cfa56-205">If you want to have the option of responding to a policy alert by sending a reminder notice to the associated employee, you'll need to create at least one notice template in your organization.</span></span> <span data-ttu-id="cfa56-206">[！注意事項] [通知範本] 欄位是可編輯的，在傳送為警示修復程式的一部分之前，建議您為每個通訊相容性原則建立自訂的通知範本。</span><span class="sxs-lookup"><span data-stu-id="cfa56-206">The notice template fields are editable before they're sent as part of the alert remediation process, and creating a customized notice template for each communication compliance policy is recommended.</span></span>

1. <span data-ttu-id="cfa56-207">使用 Microsoft 365 組織中的系統管理員帳戶認證登入[https://compliance.microsoft.com](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="cfa56-207">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="cfa56-208">在 Microsoft 365 規範中心內，移至 [**通訊符合性**]。</span><span class="sxs-lookup"><span data-stu-id="cfa56-208">In the Microsoft 365 compliance center, go to **Communication compliance**.</span></span>

3. <span data-ttu-id="cfa56-209">選取 [**公告範本**] 索引標籤，然後選取 [**建立公告範本**]。</span><span class="sxs-lookup"><span data-stu-id="cfa56-209">Select the **Notice templates** tab and then select **Create notice template**.</span></span>

4. <span data-ttu-id="cfa56-210">在 [**修改公告範本**] 頁面上，完成下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="cfa56-210">On the **Modify a notice template** page, complete the following fields:</span></span>

    - <span data-ttu-id="cfa56-211">通知範本名稱（必要）</span><span class="sxs-lookup"><span data-stu-id="cfa56-211">Notice template name (required)</span></span>
    - <span data-ttu-id="cfa56-212">寄件者（必要）</span><span class="sxs-lookup"><span data-stu-id="cfa56-212">Send from (required)</span></span>
    - <span data-ttu-id="cfa56-213">Cc 和 Bcc （選用）</span><span class="sxs-lookup"><span data-stu-id="cfa56-213">Cc and Bcc (optional)</span></span>
    - <span data-ttu-id="cfa56-214">Subject （必要）</span><span class="sxs-lookup"><span data-stu-id="cfa56-214">Subject (required)</span></span>
    - <span data-ttu-id="cfa56-215">郵件主體（必要）</span><span class="sxs-lookup"><span data-stu-id="cfa56-215">Message body (required)</span></span>

5. <span data-ttu-id="cfa56-216">選取 [**儲存**] 以建立及儲存 [公告] 範本。</span><span class="sxs-lookup"><span data-stu-id="cfa56-216">Select **Save** to create and save the notice template.</span></span>

## <a name="step-6-optional-test-your-communication-compliance-policy"></a><span data-ttu-id="cfa56-217">步驟6（選用）：測試通訊合規性原則</span><span class="sxs-lookup"><span data-stu-id="cfa56-217">Step 6 (optional): Test your communication compliance policy</span></span>

<span data-ttu-id="cfa56-218">在您建立通訊相容性原則之後，建議您加以測試，以確定原則已正確地強制執行您所定義的條件。</span><span class="sxs-lookup"><span data-stu-id="cfa56-218">After you create a communication compliance policy, it's a good idea to test it to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="cfa56-219">您也可能想要[測試您的資料遺失防護（DLP）原則（](create-test-tune-dlp-policy.md)如果通訊相容性原則包括敏感資訊類型）。</span><span class="sxs-lookup"><span data-stu-id="cfa56-219">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your communication compliance policies include sensitive information types.</span></span> <span data-ttu-id="cfa56-220">請務必提供您的原則啟動時間，以便您想要測試的通訊得以捕獲。</span><span class="sxs-lookup"><span data-stu-id="cfa56-220">Make sure you give your policies time to activate so that the communications you want to test are captured.</span></span>

<span data-ttu-id="cfa56-221">請遵循下列步驟來測試您的通訊合規性原則：</span><span class="sxs-lookup"><span data-stu-id="cfa56-221">Follow these steps to test your communication compliance policy:</span></span>

1. <span data-ttu-id="cfa56-222">在您要測試之原則中所定義的監督使用者登入時，開啟電子郵件客戶程式或 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="cfa56-222">Open an email client or Microsoft Teams while signed in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="cfa56-223">傳送電子郵件或 Microsoft 小組聊天，其符合您在通訊合規性原則中所定義的準則。</span><span class="sxs-lookup"><span data-stu-id="cfa56-223">Send an email or Microsoft Teams chat that meets the criteria you've defined in the communication compliance policy.</span></span> <span data-ttu-id="cfa56-224">此測試可以是關鍵字、附件大小、網域等等。確定您判斷原則中設定的設定條件設定過於嚴格或太 lenient。</span><span class="sxs-lookup"><span data-stu-id="cfa56-224">This test can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cfa56-225">在原則中，所有來源通道中的通訊最多可能需要24小時才能完整處理。</span><span class="sxs-lookup"><span data-stu-id="cfa56-225">Communications in all source channels can take up to 24 hours to fully process in a policy.</span></span>

3. <span data-ttu-id="cfa56-226">以通訊合規性原則中指定的檢閱者身分登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="cfa56-226">Sign in to Microsoft 365 as a reviewer designated in the communication compliance policy.</span></span> <span data-ttu-id="cfa56-227">流覽至 [**通訊相容性** > **警示**]，以查看原則的警示。</span><span class="sxs-lookup"><span data-stu-id="cfa56-227">Navigate to **Communication compliance** > **Alerts** to view the alerts for your policies.</span></span>

4. <span data-ttu-id="cfa56-228">使用修正控制措施修正警示，並確認已正確解決警示。</span><span class="sxs-lookup"><span data-stu-id="cfa56-228">Remediate the alert using the remediation controls and verify that the alert is properly resolved.</span></span>
