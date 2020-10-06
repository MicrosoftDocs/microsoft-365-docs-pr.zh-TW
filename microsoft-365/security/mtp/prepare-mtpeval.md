---
title: 準備您的 Microsoft 威脅防護試用實驗室環境
description: 在設定 Microsoft 威脅防護試用實驗室或試驗環境時，準備利益相關者簽署、時程表、環境考慮和採用順序
keywords: MTP 試用準備，MTP 試驗準備，準備執行 MTP 試驗專案、執行試驗 MTP 專案、部署、準備工作、專案關係人、時程表、環境、端點、伺服器、管理、採用
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: ac60415f38644c4630a181b1c8d696acced57ded
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367998"
---
# <a name="prepare-your-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="f9cc4-104">準備您的 Microsoft 威脅防護試用實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="f9cc4-104">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f9cc4-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f9cc4-105">**Applies to:**</span></span>
- <span data-ttu-id="f9cc4-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="f9cc4-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f9cc4-107">建立 Microsoft 威脅防護試用實驗室或試驗環境並加以部署時，會有三個階段的處理常式：</span><span class="sxs-lookup"><span data-stu-id="f9cc4-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="準備您的 Microsoft 威脅防護試用實驗室或試驗環境" />
      <br/><span data-ttu-id="f9cc4-109">階段1：準備 </a></span><span class="sxs-lookup"><span data-stu-id="f9cc4-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="設定您的 Microsoft 威脅防護試用實驗室或試驗環境" />
      <br/><span data-ttu-id="f9cc4-111">階段2：設定 </a></span><span class="sxs-lookup"><span data-stu-id="f9cc4-111">Phase 2: Setup </a></span></span><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft Threat Protection pillar" title="設定每個 Microsoft 威脅防護 pillar 及端點的板載" />
      <br/><span data-ttu-id="f9cc4-113">階段3：設定板載 &</a></span><span class="sxs-lookup"><span data-stu-id="f9cc4-113">Phase 3: Configure & Onboard</a></span></span><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

<span data-ttu-id="f9cc4-114">您目前是在準備階段。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-114">You're currently in the preparation phase.</span></span>


<span data-ttu-id="f9cc4-115">準備工作是任何成功部署的關鍵。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="f9cc4-116">本節會引導您在準備建立 Microsoft 威脅防護部署的試用實驗室或試驗環境時，您需要考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-116">This section will guide you through what you need to consider as you prepare to create a trial lab or pilot environment for your Microsoft Threat Protection deployment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f9cc4-117">必要條件</span><span class="sxs-lookup"><span data-stu-id="f9cc4-117">Prerequisites</span></span>
<span data-ttu-id="f9cc4-118">瞭解授權、硬體和軟體需求，以及其他設定，以提供和使用 Microsoft 威脅防護。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-118">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span> <span data-ttu-id="f9cc4-119">請參閱 [Microsoft 威脅防護](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)的最低需求， [microsoft Defender atp](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)， [OFFICE 365 atp](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)， [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)， [microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-119">See the minimum requirements for [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [Microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).</span></span>

## <a name="stakeholders-and-sign-off"></a><span data-ttu-id="f9cc4-120">利益關係人和簽署</span><span class="sxs-lookup"><span data-stu-id="f9cc4-120">Stakeholders and sign-off</span></span>
<span data-ttu-id="f9cc4-121">您可以在下列區段中找出專案中相關的所有利益關係人，以及可能需要登入、審查或通知的所有利益關係人，是否要評估或執行試驗。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-121">The following section serves to identify all the stakeholders that are involved in the project and who may need to sign-off, review, or stay informed, whether for evaluation or running a pilot.</span></span>

>[!NOTE]
><span data-ttu-id="f9cc4-122">並非所有組織都可能具有這類角色的安全性組織成熟度。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-122">Not all organizations might have the security organization maturity to have such roles.</span></span> <span data-ttu-id="f9cc4-123">在這種情況下，請與您的領導團隊聯繫，以複查和核准職責。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-123">In such case, consult with your leadership team on review and approval accountabilities.</span></span>

<span data-ttu-id="f9cc4-124">視您的組織而定，將相關者新增至下表。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-124">Add stakeholders to the table below as appropriate for your organization.</span></span>

-   <span data-ttu-id="f9cc4-125">SO = 在此專案上登出</span><span class="sxs-lookup"><span data-stu-id="f9cc4-125">SO = Sign-off on this project</span></span>

-   <span data-ttu-id="f9cc4-126">R = 審閱此專案並提供輸入</span><span class="sxs-lookup"><span data-stu-id="f9cc4-126">R = Review this project and provide input</span></span>

-   <span data-ttu-id="f9cc4-127">I = 此專案的通知</span><span class="sxs-lookup"><span data-stu-id="f9cc4-127">I = Informed of this project</span></span>

| <span data-ttu-id="f9cc4-128">姓名</span><span class="sxs-lookup"><span data-stu-id="f9cc4-128">Name</span></span>                 | <span data-ttu-id="f9cc4-129">角色</span><span class="sxs-lookup"><span data-stu-id="f9cc4-129">Role</span></span>                                                                                                                                                                                                          | <span data-ttu-id="f9cc4-130">動作</span><span class="sxs-lookup"><span data-stu-id="f9cc4-130">Action</span></span> |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| <span data-ttu-id="f9cc4-131">輸入名稱和電子郵件</span><span class="sxs-lookup"><span data-stu-id="f9cc4-131">Enter name and email</span></span> | <span data-ttu-id="f9cc4-132">\*\*首席資訊安全性監察官 (CISO) \*\* *成為新技術部署之組織內充當主管的執行代表。*</span><span class="sxs-lookup"><span data-stu-id="f9cc4-132">**Chief Information Security Officer (CISO)** *An executive representative who serves as sponsor inside the organization for the new technology deployment.*</span></span>                                                  | <span data-ttu-id="f9cc4-133">所以</span><span class="sxs-lookup"><span data-stu-id="f9cc4-133">SO</span></span>     |
| <span data-ttu-id="f9cc4-134">輸入名稱和電子郵件</span><span class="sxs-lookup"><span data-stu-id="f9cc4-134">Enter name and email</span></span> | <span data-ttu-id="f9cc4-135">\*\*網路防護運作中心的 Head (CDOC) \*\* *CDOC 小組的代表，以定義如何將此變更與客戶的安全性作業小組中的處理常式對齊。*</span><span class="sxs-lookup"><span data-stu-id="f9cc4-135">**Head of Cyber Defense Operations Center (CDOC)** *A representative from the CDOC team in charge of defining how this change is aligned with the processes in the customers security operations team.*</span></span>       | <span data-ttu-id="f9cc4-136">所以</span><span class="sxs-lookup"><span data-stu-id="f9cc4-136">SO</span></span>     |
| <span data-ttu-id="f9cc4-137">輸入名稱和電子郵件</span><span class="sxs-lookup"><span data-stu-id="f9cc4-137">Enter name and email</span></span> | <span data-ttu-id="f9cc4-138">\**安全性\*\*\*小組中的代表負責定義如何將此變更與組織中的核心安全性架構對應。*</span><span class="sxs-lookup"><span data-stu-id="f9cc4-138">**Security Architect** *A representative from the Security team in charge of defining how this change is aligned with the core Security architecture in the organization.*</span></span>                         | <span data-ttu-id="f9cc4-139">R</span><span class="sxs-lookup"><span data-stu-id="f9cc4-139">R</span></span>      |
| <span data-ttu-id="f9cc4-140">輸入名稱和電子郵件</span><span class="sxs-lookup"><span data-stu-id="f9cc4-140">Enter name and email</span></span> | <span data-ttu-id="f9cc4-141">\**工作場所\*\*\*會為 IT 小組設計代表，以定義如何將此變更與組織中的核心工作區架構對齊。*</span><span class="sxs-lookup"><span data-stu-id="f9cc4-141">**Workplace Architect** *A representative from the IT team in charge of defining how this change is aligned with the core workplace architecture in the organization.*</span></span>                             | <span data-ttu-id="f9cc4-142">R</span><span class="sxs-lookup"><span data-stu-id="f9cc4-142">R</span></span>      |
| <span data-ttu-id="f9cc4-143">輸入名稱和電子郵件</span><span class="sxs-lookup"><span data-stu-id="f9cc4-143">Enter name and email</span></span> | <span data-ttu-id="f9cc4-144">\**安全性分析員\*\*\*來自 CDOC 小組的代表，可提供偵測功能、使用者經驗和安全性作業的整體有用性。*</span><span class="sxs-lookup"><span data-stu-id="f9cc4-144">**Security Analyst** *A representative from the CDOC team who can provide input on the detection capabilities, user experience, and overall usefulness of this change from a security operations perspective.*</span></span> | <span data-ttu-id="f9cc4-145">I</span><span class="sxs-lookup"><span data-stu-id="f9cc4-145">I</span></span>      |

## <a name="prepare-your-azure-active-directory"></a><span data-ttu-id="f9cc4-146">準備您的 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f9cc4-146">Prepare your Azure Active Directory</span></span>
<span data-ttu-id="f9cc4-147">如果您已啟用 Active Directory 和 Azure Active Directory 內部部署之間的同步處理，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-147">Skip this step if you have already enabled synchronization between Active Directory and Azure Active Directory on premises.</span></span> <span data-ttu-id="f9cc4-148">從 Azure Active Directory 複查現有的最佳作法檔。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-148">Review existing best practices documentation from Azure Active Directory.</span></span> <span data-ttu-id="f9cc4-149">下列步驟經過優化，可以評估或執行試驗 Microsoft 威脅防護專案。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-149">The following steps are optimized to evaluate or run a pilot Microsoft Threat Protection project.</span></span>

1. <span data-ttu-id="f9cc4-150">移至 [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) 入口網站 > **azure AD Connect**。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-150">Go to the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) portal > **Azure AD Connect**.</span></span> 
<span data-ttu-id="f9cc4-151">![Azure Active Directory 入口網站頁面的影像](../../media/mtp-eval-1.png)</span><span class="sxs-lookup"><span data-stu-id="f9cc4-151">![Image of Azure Active Directory portal page](../../media/mtp-eval-1.png)</span></span> <br> 

2. <span data-ttu-id="f9cc4-152">按一下**Download** [從**Microsoft Azure Active Directory 連線]** ，然後將它轉接至您的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-152">Click **Download** from **Microsoft Azure Active Directory Connect** and transfer it to your Domain Controller.</span></span>
<span data-ttu-id="f9cc4-153">![Azure Active Directoru Connect 下載頁面的圖像](../../media/mtp-eval-2.png)</span><span class="sxs-lookup"><span data-stu-id="f9cc4-153">![Image of Azure Active Directoru Connect download page](../../media/mtp-eval-2.png)</span></span> <br>

3. <span data-ttu-id="f9cc4-154">在網域控制站上，遵循 Azure Active Directory Connect 嚮導。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-154">On the domain controller, follow the Azure Active Directory Connect wizard.</span></span> <span data-ttu-id="f9cc4-155">閱讀授權條款和隱私權通知，如果您同意，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-155">Read the license terms and privacy notice and select the checkbox if you agree.</span></span> <span data-ttu-id="f9cc4-156">按一下 [繼續]。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-156">Click **Continue**.</span></span>
<span data-ttu-id="f9cc4-157">![Azure AD Connect 歡迎頁面的圖像](../../media/mtp-eval-3.png)</span><span class="sxs-lookup"><span data-stu-id="f9cc4-157">![Image of Azure AD Connect welcome page](../../media/mtp-eval-3.png)</span></span> <br>

4. <span data-ttu-id="f9cc4-158">流覽至 **Express 設定**。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-158">Navigate to **Express Settings**.</span></span>
<span data-ttu-id="f9cc4-159">![快速設定頁面的圖像](../../media/mtp-eval-4.png)</span><span class="sxs-lookup"><span data-stu-id="f9cc4-159">![Image of Express Settings page](../../media/mtp-eval-4.png)</span></span> <br>

5. <span data-ttu-id="f9cc4-160">輸入您的全域系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-160">Enter your global administrator credentials.</span></span> <span data-ttu-id="f9cc4-161">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-161">Click **Next**.</span></span>
<span data-ttu-id="f9cc4-162">![您應輸入全域系統管理員認證的 [連線到 Azure AD] 頁面影像](../../media/mtp-eval-5.png)</span><span class="sxs-lookup"><span data-stu-id="f9cc4-162">![Image of Connect to Azure AD page where you should enter your global administrator credentials](../../media/mtp-eval-5.png)</span></span> <br>

6. <span data-ttu-id="f9cc4-163">輸入您的 Active Directory 網域服務企業系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-163">Enter your Active Directory Domain Services enterprise administrator credentials.</span></span> <span data-ttu-id="f9cc4-164">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-164">Click **Next**.</span></span>
<span data-ttu-id="f9cc4-165">![您應輸入認證的 [連線到 AD DS] 頁面影像](../../media/mtp-eval-6.png)</span><span class="sxs-lookup"><span data-stu-id="f9cc4-165">![Image of Connect to AD DS page where you should enter your credentials](../../media/mtp-eval-6.png)</span></span> <br>

7. <span data-ttu-id="f9cc4-166">按一下 [ **安裝** ] 以確認設定。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-166">Click **Install** to confirm the configuration.</span></span>
<span data-ttu-id="f9cc4-167">![設定確認頁面的影像](../../media/mtp-eval-7.png)</span><span class="sxs-lookup"><span data-stu-id="f9cc4-167">![Image of configuration confirmation page](../../media/mtp-eval-7.png)</span></span> <br>

8. <span data-ttu-id="f9cc4-168">恭喜，您已成功設定 Azure Active Directory Connect。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-168">Congratulations, you have successfully configured Azure Active Directory Connect.</span></span>
<span data-ttu-id="f9cc4-169">![已成功設定 Azure Active Directory Connect 頁面的圖像](../../media/mtp-eval-8.png)</span><span class="sxs-lookup"><span data-stu-id="f9cc4-169">![Image of a successfully configured Azure Active Directory Connect page](../../media/mtp-eval-8.png)</span></span> <br>

<span data-ttu-id="f9cc4-170">您現在可以 [將使用者和群組新增至 Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) ，並 [設定 SAM-R 原則](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-170">You can now [add users and groups to Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) and [configure a SAM-R policy](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).</span></span>  


## <a name="configuration-order"></a><span data-ttu-id="f9cc4-171">設定順序</span><span class="sxs-lookup"><span data-stu-id="f9cc4-171">Configuration order</span></span>
<span data-ttu-id="f9cc4-172">下表指出 Microsoft 建議為您的試用實驗室或試驗環境部署設定 Microsoft 威脅防護元件的順序。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-172">The table below indicates the order Microsoft recommends for configuring the Microsoft Threat Protection components for your trial lab or pilot environment deployment.</span></span>

| <span data-ttu-id="f9cc4-173">元件</span><span class="sxs-lookup"><span data-stu-id="f9cc4-173">Component</span></span>                               | <span data-ttu-id="f9cc4-174">描述</span><span class="sxs-lookup"><span data-stu-id="f9cc4-174">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="f9cc4-175">設定順序排名</span><span class="sxs-lookup"><span data-stu-id="f9cc4-175">Configuration order rank</span></span> |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| <span data-ttu-id="f9cc4-176">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="f9cc4-176">Office 365 Advanced Threat Protection</span></span>| <span data-ttu-id="f9cc4-177">Office 365 ATP 會保護您的組織免受電子郵件訊息、連結 (URLs) 和共同作業工具所帶來的惡意威脅。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-177">Office 365 ATP safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <br> [<span data-ttu-id="f9cc4-178">瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-178">Learn more.</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | <span data-ttu-id="f9cc4-179">1 </span><span class="sxs-lookup"><span data-stu-id="f9cc4-179">1</span></span>                   |
|<span data-ttu-id="f9cc4-180">Azure 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="f9cc4-180">Azure Advanced Threat Protection</span></span>|<span data-ttu-id="f9cc4-181">Azure ATP 使用 Active Directory 信號來識別、偵測和調查您組織中的高級威脅、已遭破壞的身分識別，以及惡意的有問必答行為。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-181">Azure ATP uses Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <br> <span data-ttu-id="f9cc4-182">[深入了解](https://docs.microsoft.com/azure-advanced-threat-protection/)。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-182">[Learn more](https://docs.microsoft.com/azure-advanced-threat-protection/).</span></span>| <span data-ttu-id="f9cc4-183">2 </span><span class="sxs-lookup"><span data-stu-id="f9cc4-183">2</span></span> |
|<span data-ttu-id="f9cc4-184">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f9cc4-184">Microsoft Cloud App Security</span></span>| <span data-ttu-id="f9cc4-185">Microsoft Cloud App Security 是雲端存取安全性經紀人 (CASB) ，可在多個雲端上運作。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-185">Microsoft Cloud App Security is a Cloud Access Security Broker (CASB) that operates on multiple clouds.</span></span> <span data-ttu-id="f9cc4-186">它可提供豐富的知名度、控制資料旅行和複雜的分析，以在所有雲端服務之間識別及打擊 cyberthreats。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-186">It provides rich visibility, control over data travel, and sophisticated analytics to identify and combat cyberthreats across all your cloud services.</span></span> <br> <span data-ttu-id="f9cc4-187">[深入了解](https://docs.microsoft.com/cloud-app-security/)。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-187">[Learn more](https://docs.microsoft.com/cloud-app-security/).</span></span>                                                                                                                                                                                                                                                                                                                                                                       |<span data-ttu-id="f9cc4-188">3 </span><span class="sxs-lookup"><span data-stu-id="f9cc4-188">3</span></span>                   |
|<span data-ttu-id="f9cc4-189">Microsoft Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="f9cc4-189">Microsoft Defender Advanced Threat Protection</span></span> | <span data-ttu-id="f9cc4-190">Microsoft Defender ATP 端點偵測和回應功能可提供近乎即時並可採取行動的進階攻擊偵測。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-190">Microsoft Defender ATP endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="f9cc4-191">安全性分析人員可以有效地排定警示的優先順序、深入了解入侵的全貌，並採取回應動作來補救威脅。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-191">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span> <br> [<span data-ttu-id="f9cc4-192">瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="f9cc4-192">Learn more.</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |<span data-ttu-id="f9cc4-193">4 </span><span class="sxs-lookup"><span data-stu-id="f9cc4-193">4</span></span>                   |                                                                                                                                                                                                                                    

## <a name="next-step"></a><span data-ttu-id="f9cc4-194">下一步</span><span class="sxs-lookup"><span data-stu-id="f9cc4-194">Next step</span></span>
|<span data-ttu-id="f9cc4-195">![階段2：設定](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="f9cc4-195">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="f9cc4-196">階段2：設定</span><span class="sxs-lookup"><span data-stu-id="f9cc4-196">Phase 2: Setup</span></span>](setup-mtpeval.md) | <span data-ttu-id="f9cc4-197">設定您的 Microsoft 威脅防護試用實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="f9cc4-197">Set up your Microsoft Threat Protection trial lab or pilot environment</span></span>
|:-------|:-----|

