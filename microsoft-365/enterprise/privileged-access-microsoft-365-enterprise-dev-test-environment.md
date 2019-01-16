---
title: Microsoft 365 企業版測試環境的特殊權限存取管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: 若要啟用權限的存取管理 Microsoft 365 企業版測試環境使用此測試實驗室指南。
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866127"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="bdf5c-103">Microsoft 365 企業版測試環境的特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="bdf5c-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="bdf5c-104">使用本文中的指示，您可以設定以增加安全性 Microsoft 365 企業版測試環境中的權限的存取管理。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="bdf5c-106">按一下[這裡](https://aka.ms/m365etlgstack)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="bdf5c-107">階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境</span><span class="sxs-lookup"><span data-stu-id="bdf5c-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="bdf5c-108">如果只想要設定權限的存取管理的基本需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="bdf5c-109">如果您要設定模擬企業中的存取權限的管理，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bdf5c-p101">測試權限的存取管理不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。這裡提供選項，讓您可以測試權限存取管理並代表的典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-p101">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="bdf5c-112">階段 2： 設定權限的存取管理</span><span class="sxs-lookup"><span data-stu-id="bdf5c-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="bdf5c-p102">在此階段中，您可以設定核准者群組及權限的存取管理啟用 Microsoft 365 企業版測試環境。如需其他詳細資料及權限的概觀存取管理，請參閱[Office 365 中的權限的存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-p102">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment. For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="bdf5c-115">請遵循下列步驟來設定和 Office 365 組織中使用特殊權限的存取：</span><span class="sxs-lookup"><span data-stu-id="bdf5c-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="bdf5c-116">步驟 1： 建立核准者群組</span><span class="sxs-lookup"><span data-stu-id="bdf5c-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    <span data-ttu-id="bdf5c-p103">在您開始使用最低權限存取之前，請決定誰將擁有的傳入要求提高權限與權限工作的存取權核准授權單位。任何已核准者的群組之一部分的使用者將能夠核准存取要求。這會啟用在 Office 365 中建立擁有郵件功能的安全性群組。建立測試環境中名為 」 權限存取核准者"的新安全性群組並新增"使用者 3"先前在先前的測試實驗室指南步驟中建立。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-p103">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365. Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="bdf5c-121">步驟 2： 啟用權限的存取</span><span class="sxs-lookup"><span data-stu-id="bdf5c-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    <span data-ttu-id="bdf5c-p104">權限的存取必須明確開啟 Office 365 中使用的預設核准者群組與包括一組您想要排除的權限的存取管理存取控制的系統帳戶。請務必啟用之前先啟動本指南的階段 3： 在 Office 365 組織中的權限的存取。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-p104">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control. Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="bdf5c-124">階段 3： 確認核准需要提高權限和權限工作</span><span class="sxs-lookup"><span data-stu-id="bdf5c-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>
<span data-ttu-id="bdf5c-125">在此階段中，您可以確認運作的權限的存取原則及使用者需要核准執行已定義的提高權限和權限工作。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="bdf5c-126">測試能夠執行的特殊權限的存取原則中未定義的工作</span><span class="sxs-lookup"><span data-stu-id="bdf5c-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="bdf5c-p105">首先，設定為在測試環境中的全域管理員使用者的認證以連線至 Exchange Management PowerShell 並嘗試建立新的日誌規則。[New-journalrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps)任務目前未定義在您的組織權限的存取原則。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-p105">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule. The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="bdf5c-129">在您的本機電腦上開啟並登入 Exchange Online 遠端 PowerShell 模組**Microsoft**corporation > **Microsoft Exchange Online 遠端 PowerShell 模組**使用全域管理員帳戶的測試環境。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="bdf5c-130">在 Exchange Management Powershell 中建立新的日誌規則的組織：</span><span class="sxs-lookup"><span data-stu-id="bdf5c-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. <span data-ttu-id="bdf5c-131">新的日誌規則已成功建立的 Exchange Management PowerShell] 檢視。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="bdf5c-132">建立新的權限的存取原則 New-journalrule 工作</span><span class="sxs-lookup"><span data-stu-id="bdf5c-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="bdf5c-133">如果您已經尚未完成步驟 1 和 2 從本指南的階段 2，是確定遵循的步驟來建立名為"最低權限存取核准者 」 的核准者群組以及能在測試環境中的權限的存取。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="bdf5c-134">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用認證測試環境的全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-134">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="bdf5c-135">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="bdf5c-136">選取 [**管理存取原則及要求**。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="bdf5c-137">選取 [**設定的原則**，並選取 [**新增原則**。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="bdf5c-138">從下拉式欄位中，選取或輸入下列值：</span><span class="sxs-lookup"><span data-stu-id="bdf5c-138">From the drop-down fields, select or enter the following values:</span></span>
    
    <span data-ttu-id="bdf5c-139">**原則類型**： 任務</span><span class="sxs-lookup"><span data-stu-id="bdf5c-139">**Policy type**: Task</span></span>

    <span data-ttu-id="bdf5c-140">**原則範圍**： Exchange</span><span class="sxs-lookup"><span data-stu-id="bdf5c-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="bdf5c-141">**原則名稱**： 新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="bdf5c-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="bdf5c-142">**核准類型**： 能沒有的手冊</span><span class="sxs-lookup"><span data-stu-id="bdf5c-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="bdf5c-143">**核准群組**： 權限存取核准者</span><span class="sxs-lookup"><span data-stu-id="bdf5c-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="bdf5c-p106">選取 [**建立**並再**關閉**。可能需要幾分鐘時間可完全設定並啟用原則。請務必允許完全之前測試核准需求下一個步驟中啟用之原則的時間。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-p106">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled. Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="bdf5c-147">測試核准權限的存取原則所定義的 New-journalrule 工作需求</span><span class="sxs-lookup"><span data-stu-id="bdf5c-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="bdf5c-148">在您的本機電腦上開啟並登入 Exchange Online 遠端 PowerShell 模組**Microsoft**corporation > **Microsoft Exchange Online 遠端 PowerShell 模組**使用使用全域管理員帳戶的測試環境。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="bdf5c-149">在 Exchange Management Powershell 中建立新的日誌規則的組織：</span><span class="sxs-lookup"><span data-stu-id="bdf5c-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="bdf5c-150">在 Exchange Management PowerShell 檢視 「 Insuffient 權限 」 錯誤：</span><span class="sxs-lookup"><span data-stu-id="bdf5c-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="bdf5c-151">若要建立新的日誌規則使用 New-journalrule 工作要求存取</span><span class="sxs-lookup"><span data-stu-id="bdf5c-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="bdf5c-152">登入[Microsoft 365 系統管理中心](https://portal.office.com)的測試環境中使用的全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="bdf5c-153">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="bdf5c-154">選取 [**管理存取原則及要求**。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="bdf5c-p107">選取**新的要求**。從下拉式欄位中，選取您的組織適當的值：</span><span class="sxs-lookup"><span data-stu-id="bdf5c-p107">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="bdf5c-157">**要求類型**： 任務</span><span class="sxs-lookup"><span data-stu-id="bdf5c-157">**Request type**: Task</span></span>

    <span data-ttu-id="bdf5c-158">**要求範圍**： Exchange</span><span class="sxs-lookup"><span data-stu-id="bdf5c-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="bdf5c-159">**要求**： 新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="bdf5c-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="bdf5c-160">**持續時間 （小時）**: 2</span><span class="sxs-lookup"><span data-stu-id="bdf5c-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="bdf5c-161">**註解**： 要求權限可建立新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="bdf5c-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="bdf5c-p108">選取 [**儲存**並再**關閉**。您的要求會傳送到透過電子郵件的核准者群組。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-p108">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="bdf5c-164">核准權限的存取要求建立新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="bdf5c-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="bdf5c-165">登入[Microsoft 365 系統管理中心](https://portal.office.com)使用使用者 3 在測試環境中 （在測試環境中 」 權限存取核准者 」 安全性群組的成員） 的認證。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-165">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="bdf5c-166">在管理中心中，移至 [**設定** > **安全性與隱私權** > **權限的存取**。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="bdf5c-167">選取 [**管理存取原則及要求**。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="bdf5c-p109">選取 [擱置的要求，並選取 [建立新的日誌規則的全域管理員帳戶的存取權授與**核准**。通知電子郵件確認您已授與核准就會傳送給全域管理員帳戶 （要求的使用者）。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-p109">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule. An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="bdf5c-170">測試與核准 New-journalrule 工作的存取權限建立新的日誌規則</span><span class="sxs-lookup"><span data-stu-id="bdf5c-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="bdf5c-171">在您的本機電腦上開啟並登入 Exchange Online 遠端 PowerShell 模組**Microsoft**corporation > **Microsoft Exchange Online 遠端 PowerShell 模組**使用全域管理員帳戶的測試環境。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="bdf5c-172">在 Exchange Management Powershell 中建立新的日誌規則的組織：</span><span class="sxs-lookup"><span data-stu-id="bdf5c-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="bdf5c-173">新的日誌規則已成功建立的 Exchange Management PowerShell] 檢視。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="bdf5c-174">下一步</span><span class="sxs-lookup"><span data-stu-id="bdf5c-174">Next step</span></span>

<span data-ttu-id="bdf5c-175">探索測試環境的其他[資訊保護](m365-enterprise-test-lab-guides.md#information-protection)特色和功能。</span><span class="sxs-lookup"><span data-stu-id="bdf5c-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdf5c-176">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bdf5c-176">See also</span></span>

[<span data-ttu-id="bdf5c-177">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="bdf5c-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="bdf5c-178">部署 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="bdf5c-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="bdf5c-179">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="bdf5c-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)