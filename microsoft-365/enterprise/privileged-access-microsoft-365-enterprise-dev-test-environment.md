---
title: Microsoft 365 企業版測試環境的特殊權限存取管理
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: 使用此測試實驗室指南來啟用特殊權限的存取管理 Microsoft 365 企業版測試環境。
ms.openlocfilehash: 68d542b3f97022abc65b94162f333e7059f614a8
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673339"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="04a06-103">Microsoft 365 企業版測試環境的特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="04a06-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="04a06-104">*此測試實驗室指南可用於 Microsoft 365 企業版和 Office 365 企業版測試環境。*</span><span class="sxs-lookup"><span data-stu-id="04a06-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="04a06-105">透過本文中的指示，您可以設定若要提高安全性，Microsoft 365 企業版測試環境中的特殊權限的存取管理。</span><span class="sxs-lookup"><span data-stu-id="04a06-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="04a06-107">按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="04a06-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="04a06-108">階段 1：建置您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="04a06-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="04a06-109">如果您只想以具有最小需求的輕量型方式設定特殊權限的存取管理，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="04a06-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="04a06-110">如果您想要在模擬的企業中設定特殊權限的存取管理，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="04a06-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="04a06-111">測試特殊權限的存取管理，不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理的 AD DS 樹系。</span><span class="sxs-lookup"><span data-stu-id="04a06-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="04a06-112">它提供了以下選項，以便您可以測試權限存取管理及實驗它代表典型組織的環境中。</span><span class="sxs-lookup"><span data-stu-id="04a06-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="04a06-113">階段 2： 設定特殊權限的存取管理</span><span class="sxs-lookup"><span data-stu-id="04a06-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="04a06-114">在這個階段，您可以設定的核准者群組，並啟用適用於 Microsoft 365 企業版測試環境的特殊權限的存取管理。</span><span class="sxs-lookup"><span data-stu-id="04a06-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="04a06-115">其他詳細資料和概觀權限存取管理，請參閱[Office 365 中的特殊權限的存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)。</span><span class="sxs-lookup"><span data-stu-id="04a06-115">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="04a06-116">請遵循下列步驟來設定和使用 Office 365 組織中的特殊權限的存取：</span><span class="sxs-lookup"><span data-stu-id="04a06-116">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="04a06-117">步驟 1： 建立核准者群組</span><span class="sxs-lookup"><span data-stu-id="04a06-117">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    <span data-ttu-id="04a06-118">開始使用權限存取之前，請決定誰會具有存取提升權限和特殊權限的工作的傳入要求的核准授權。</span><span class="sxs-lookup"><span data-stu-id="04a06-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="04a06-119">屬於核准者群組的任何使用者將能夠核准存取要求。</span><span class="sxs-lookup"><span data-stu-id="04a06-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="04a06-120">這會啟用在 Office 365 中建立擁有郵件功能的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="04a06-120">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="04a06-121">建立測試環境中名為 「 特殊權限存取核准者 」 的新安全性群組並新增 「 使用者 3 」 先前在先前的測試實驗室指南步驟中建立。</span><span class="sxs-lookup"><span data-stu-id="04a06-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="04a06-122">步驟 2： 啟用特殊權限的存取</span><span class="sxs-lookup"><span data-stu-id="04a06-122">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    <span data-ttu-id="04a06-123">特殊權限的存取必須明確中開啟 Office 365 與預設的核准者群組包含一組您想要排除的特殊權限的存取管理存取控制的系統帳戶。</span><span class="sxs-lookup"><span data-stu-id="04a06-123">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="04a06-124">請務必啟用 Office 365 組織才能開始進行本指南的階段 3 中的特殊權限的存取。</span><span class="sxs-lookup"><span data-stu-id="04a06-124">Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="04a06-125">階段 3： 確認核准需要提高權限和特殊權限工作</span><span class="sxs-lookup"><span data-stu-id="04a06-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="04a06-126">在這個階段，您可以驗證的特殊權限的存取原則的運作，而且使用者要求核准] 若要執行已定義的提升權限和特殊權限工作。</span><span class="sxs-lookup"><span data-stu-id="04a06-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="04a06-127">測試能夠執行的特殊權限的存取原則中未定義的工作</span><span class="sxs-lookup"><span data-stu-id="04a06-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="04a06-128">首先，以設定測試環境中的全域系統管理員身分的使用者的認證連線到 Exchange Management PowerShell，並嘗試建立新的日誌規則。</span><span class="sxs-lookup"><span data-stu-id="04a06-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="04a06-129">該[New-journalrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps)任務是目前中未定義貴組織的特殊權限的存取原則。</span><span class="sxs-lookup"><span data-stu-id="04a06-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="04a06-130">在您的本機電腦上開啟並登入 Exchange Online 遠端 PowerShell 模組**Microsoft Corporation**在 > **Microsoft Exchange Online 遠端 PowerShell 模組**使用全域系統管理員帳戶的測試環境。</span><span class="sxs-lookup"><span data-stu-id="04a06-130">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="04a06-131">在 Exchange Management Powershell 中建立新的日誌規則，為您的組織：</span><span class="sxs-lookup"><span data-stu-id="04a06-131">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="04a06-132">檢視的新日誌規則已順利建立在 Exchange Management PowerShell。</span><span class="sxs-lookup"><span data-stu-id="04a06-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="04a06-133">建立新的特殊權限的存取原則，針對該 New-journalrule 任務</span><span class="sxs-lookup"><span data-stu-id="04a06-133">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="04a06-134">如果您已經完成步驟 1 和 2 從本指南的階段 2，是確定遵循的步驟來建立名為 」 權限存取核准者 」 的核准者群組，並讓測試環境中的特殊權限的存取。</span><span class="sxs-lookup"><span data-stu-id="04a06-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="04a06-135">適用於測試環境的全域系統管理員帳戶登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用認證。</span><span class="sxs-lookup"><span data-stu-id="04a06-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="04a06-136">在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="04a06-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="04a06-137">選取 [**管理存取原則和要求**。</span><span class="sxs-lookup"><span data-stu-id="04a06-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="04a06-138">選取 [**設定原則**，然後選取 [**新增原則**。</span><span class="sxs-lookup"><span data-stu-id="04a06-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="04a06-139">從下拉式清單的欄位，選取或輸入下列值：</span><span class="sxs-lookup"><span data-stu-id="04a06-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="04a06-140">**原則類型**： 工作</span><span class="sxs-lookup"><span data-stu-id="04a06-140">**Policy type**: Task</span></span>

    <span data-ttu-id="04a06-141">**原則範圍**： Exchange</span><span class="sxs-lookup"><span data-stu-id="04a06-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="04a06-142">**原則名稱**： 新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="04a06-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="04a06-143">**核准類型**： 手冊</span><span class="sxs-lookup"><span data-stu-id="04a06-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="04a06-144">**核准群組**： 特殊權限存取核准者</span><span class="sxs-lookup"><span data-stu-id="04a06-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="04a06-145">選取 [**建立**，然後**關閉**。</span><span class="sxs-lookup"><span data-stu-id="04a06-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="04a06-146">可能需要幾分鐘的完整設定並啟用原則。</span><span class="sxs-lookup"><span data-stu-id="04a06-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="04a06-147">請務必讓測試的核准要求在下一個步驟之前要完全啟用原則的時間。</span><span class="sxs-lookup"><span data-stu-id="04a06-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="04a06-148">測試特殊權限的存取原則中定義該 New-journalrule 任務核准的需求</span><span class="sxs-lookup"><span data-stu-id="04a06-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="04a06-149">在您的本機電腦上開啟並登入 Exchange Online 遠端 PowerShell 模組**Microsoft Corporation**在 > **Microsoft Exchange Online 遠端 PowerShell 模組**使用使用全域系統管理員帳戶的測試環境。</span><span class="sxs-lookup"><span data-stu-id="04a06-149">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="04a06-150">在 Exchange Management Powershell 中建立新的日誌規則，為您的組織：</span><span class="sxs-lookup"><span data-stu-id="04a06-150">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="04a06-151">在 Exchange Management PowerShell 中檢視 「 Insuffient 權限 」 錯誤：</span><span class="sxs-lookup"><span data-stu-id="04a06-151">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="04a06-152">若要建立新的日誌規則，使用該 New-journalrule 任務要求存取</span><span class="sxs-lookup"><span data-stu-id="04a06-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="04a06-153">登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)的測試環境中使用的全域系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="04a06-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="04a06-154">在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="04a06-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="04a06-155">選取 [**管理存取原則和要求**。</span><span class="sxs-lookup"><span data-stu-id="04a06-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="04a06-156">選取**新的要求**。</span><span class="sxs-lookup"><span data-stu-id="04a06-156">Select **New request**.</span></span> <span data-ttu-id="04a06-157">從下拉式清單的欄位，選取適當的值為您的組織：</span><span class="sxs-lookup"><span data-stu-id="04a06-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="04a06-158">**要求類型**： 工作</span><span class="sxs-lookup"><span data-stu-id="04a06-158">**Request type**: Task</span></span>

    <span data-ttu-id="04a06-159">**要求範圍**： Exchange</span><span class="sxs-lookup"><span data-stu-id="04a06-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="04a06-160">**要求**： 新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="04a06-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="04a06-161">**持續時間 （小時）**: 2</span><span class="sxs-lookup"><span data-stu-id="04a06-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="04a06-162">**註解**： 要求權限以建立新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="04a06-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="04a06-163">選取**儲存**，然後**關閉**。</span><span class="sxs-lookup"><span data-stu-id="04a06-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="04a06-164">您的要求會傳送至透過電子郵件的核准者群組。</span><span class="sxs-lookup"><span data-stu-id="04a06-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="04a06-165">核准建立新的日誌規則的特殊權限的存取要求</span><span class="sxs-lookup"><span data-stu-id="04a06-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="04a06-166">登入[Microsoft 365 系統管理中心](https://admin.microsoft.com)使用 User 3 在測試環境 （測試環境中的 「 特殊權限存取核准者 」 安全性] 群組的成員） 的認證。</span><span class="sxs-lookup"><span data-stu-id="04a06-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="04a06-167">在系統管理中心，移至 [**設定** > **安全性 & 隱私權** > **特殊權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="04a06-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="04a06-168">選取 [**管理存取原則和要求**。</span><span class="sxs-lookup"><span data-stu-id="04a06-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="04a06-169">選取 [擱置的要求，然後選取 [授與存取權的全域系統管理員帳戶，來建立新的日誌規則的**核准**。</span><span class="sxs-lookup"><span data-stu-id="04a06-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="04a06-170">全域系統管理員帳戶 （要求使用者） 時，會將傳送通知電子郵件，確認已授與核准。</span><span class="sxs-lookup"><span data-stu-id="04a06-170">An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="04a06-171">測試與核准該 New-journalrule 任務的特殊權限存取建立新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="04a06-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="04a06-172">在您的本機電腦上開啟並登入 Exchange Online 遠端 PowerShell 模組**Microsoft Corporation**在 > **Microsoft Exchange Online 遠端 PowerShell 模組**使用全域系統管理員帳戶的測試環境。</span><span class="sxs-lookup"><span data-stu-id="04a06-172">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="04a06-173">在 Exchange Management Powershell 中建立新的日誌規則，為您的組織：</span><span class="sxs-lookup"><span data-stu-id="04a06-173">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="04a06-174">檢視的新日誌規則已順利建立在 Exchange Management PowerShell。</span><span class="sxs-lookup"><span data-stu-id="04a06-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="04a06-175">下一步</span><span class="sxs-lookup"><span data-stu-id="04a06-175">Next step</span></span>

<span data-ttu-id="04a06-176">瀏覽額外的[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)功能和測試環境中的功能。</span><span class="sxs-lookup"><span data-stu-id="04a06-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="04a06-177">另請參閱</span><span class="sxs-lookup"><span data-stu-id="04a06-177">See also</span></span>

[<span data-ttu-id="04a06-178">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="04a06-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="04a06-179">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="04a06-179">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="04a06-180">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="04a06-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)