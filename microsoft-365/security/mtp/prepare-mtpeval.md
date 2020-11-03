---
title: 準備您的 Microsoft 365 Defender 試用實驗室環境
description: 在設定 Microsoft 365 Defender 試用實驗室或試驗環境時，準備利益相關者簽署、時程表、環境考慮和採用順序
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
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: a255c74db030325ba22c2095fba732a93b8c269c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844845"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="ecaad-104">準備您的 Microsoft 365 Defender 試用實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="ecaad-104">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ecaad-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="ecaad-105">**Applies to:**</span></span>
- <span data-ttu-id="ecaad-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ecaad-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ecaad-107">建立 Microsoft 365 Defender 試驗實驗室或試驗環境並加以部署時，會有三個階段的處理常式：</span><span class="sxs-lookup"><span data-stu-id="ecaad-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab environment" title="準備您的 Microsoft 365 Defender 試用實驗室或試驗環境" />
      <br/><span data-ttu-id="ecaad-109">階段1：準備 </a></span><span class="sxs-lookup"><span data-stu-id="ecaad-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab environment" title="設定您的 Microsoft 365 Defender 試用實驗室或試驗環境" />
      <br/><span data-ttu-id="ecaad-111">階段2：設定 </a></span><span class="sxs-lookup"><span data-stu-id="ecaad-111">Phase 2: Setup </a></span></span><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft 365 Defender pillar" title="設定每個 Microsoft 365 Defender pillar 及您的端點板載" />
      <br/><span data-ttu-id="ecaad-113">階段3：設定板載 &</a></span><span class="sxs-lookup"><span data-stu-id="ecaad-113">Phase 3: Configure & Onboard</a></span></span><br>
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

<span data-ttu-id="ecaad-114">您目前是在準備階段。</span><span class="sxs-lookup"><span data-stu-id="ecaad-114">You're currently in the preparation phase.</span></span>


<span data-ttu-id="ecaad-115">準備工作是任何成功部署的關鍵。</span><span class="sxs-lookup"><span data-stu-id="ecaad-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="ecaad-116">本節會引導您在準備建立 Microsoft 365 Defender 部署的試用實驗室或試驗環境時，您需要考慮的事項。</span><span class="sxs-lookup"><span data-stu-id="ecaad-116">This section will guide you through what you need to consider as you prepare to create a trial lab or pilot environment for your Microsoft 365 Defender deployment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ecaad-117">先決條件</span><span class="sxs-lookup"><span data-stu-id="ecaad-117">Prerequisites</span></span>
<span data-ttu-id="ecaad-118">瞭解授權、硬體和軟體需求，以及其他設定，以提供和使用 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="ecaad-118">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft 365 Defender.</span></span> <span data-ttu-id="ecaad-119">請參閱 [microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)、microsoft Defender for [Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)、 [microsoft defender For Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)、 [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)、 [microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)的最低需求。</span><span class="sxs-lookup"><span data-stu-id="ecaad-119">See the minimum requirements for [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [Microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).</span></span>

## <a name="stakeholders-and-sign-off"></a><span data-ttu-id="ecaad-120">利益關係人和簽署</span><span class="sxs-lookup"><span data-stu-id="ecaad-120">Stakeholders and sign-off</span></span>
<span data-ttu-id="ecaad-121">找出專案中相關的所有利益關係人，以及可能需要登入、審查或通知的所有利益關係人，不論評估或執行試驗專案。</span><span class="sxs-lookup"><span data-stu-id="ecaad-121">Identify all the stakeholders that are involved in the project and who may need to sign-off, review, or stay informed, whether for evaluation or running a pilot project.</span></span>

>[!NOTE]
><span data-ttu-id="ecaad-122">並非所有組織都可能具有這類角色的安全性組織成熟度。</span><span class="sxs-lookup"><span data-stu-id="ecaad-122">Not all organizations might have the security organization maturity to have such roles.</span></span> <span data-ttu-id="ecaad-123">在這種情況下，請與您的領導團隊聯繫，以複查和核准職責。</span><span class="sxs-lookup"><span data-stu-id="ecaad-123">In such case, consult with your leadership team on review and approval accountabilities.</span></span>

<span data-ttu-id="ecaad-124">視您的組織而定，將相關者新增至下表。</span><span class="sxs-lookup"><span data-stu-id="ecaad-124">Add stakeholders to the table below as appropriate for your organization.</span></span>

-   <span data-ttu-id="ecaad-125">SO = 在此專案上登出</span><span class="sxs-lookup"><span data-stu-id="ecaad-125">SO = Sign-off on this project</span></span>

-   <span data-ttu-id="ecaad-126">R = 審閱此專案並提供輸入</span><span class="sxs-lookup"><span data-stu-id="ecaad-126">R = Review this project and provide input</span></span>

-   <span data-ttu-id="ecaad-127">I = 此專案的通知</span><span class="sxs-lookup"><span data-stu-id="ecaad-127">I = Informed of this project</span></span>

| <span data-ttu-id="ecaad-128">姓名</span><span class="sxs-lookup"><span data-stu-id="ecaad-128">Name</span></span>                 | <span data-ttu-id="ecaad-129">角色</span><span class="sxs-lookup"><span data-stu-id="ecaad-129">Role</span></span>                                                                                                                                                                                                          | <span data-ttu-id="ecaad-130">動作</span><span class="sxs-lookup"><span data-stu-id="ecaad-130">Action</span></span> |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| <span data-ttu-id="ecaad-131">輸入名稱和電子郵件</span><span class="sxs-lookup"><span data-stu-id="ecaad-131">Enter name and email</span></span> | <span data-ttu-id="ecaad-132">**首席資訊安全性監察官 (CISO)** *成為新技術部署之組織內充當主管的執行代表。*</span><span class="sxs-lookup"><span data-stu-id="ecaad-132">**Chief Information Security Officer (CISO)** *An executive representative who serves as sponsor inside the organization for the new technology deployment.*</span></span>                                                  | <span data-ttu-id="ecaad-133">所以</span><span class="sxs-lookup"><span data-stu-id="ecaad-133">SO</span></span>     |
| <span data-ttu-id="ecaad-134">輸入名稱和電子郵件</span><span class="sxs-lookup"><span data-stu-id="ecaad-134">Enter name and email</span></span> | <span data-ttu-id="ecaad-135">**網路防護運作中心的 Head (CDOC)** *CDOC 小組的代表，以定義如何將此變更與客戶的安全性作業小組中的處理常式對齊。*</span><span class="sxs-lookup"><span data-stu-id="ecaad-135">**Head of Cyber Defense Operations Center (CDOC)** *A representative from the CDOC team in charge of defining how this change is aligned with the processes in the customers security operations team.*</span></span>       | <span data-ttu-id="ecaad-136">所以</span><span class="sxs-lookup"><span data-stu-id="ecaad-136">SO</span></span>     |
| <span data-ttu-id="ecaad-137">輸入名稱和電子郵件</span><span class="sxs-lookup"><span data-stu-id="ecaad-137">Enter name and email</span></span> | <span data-ttu-id="ecaad-138">\**安全性\*\*\*小組中的代表負責定義如何將此變更與組織中的核心安全性架構對應。*</span><span class="sxs-lookup"><span data-stu-id="ecaad-138">**Security Architect** *A representative from the Security team in charge of defining how this change is aligned with the core Security architecture in the organization.*</span></span>                         | <span data-ttu-id="ecaad-139">R</span><span class="sxs-lookup"><span data-stu-id="ecaad-139">R</span></span>      |
| <span data-ttu-id="ecaad-140">輸入名稱和電子郵件</span><span class="sxs-lookup"><span data-stu-id="ecaad-140">Enter name and email</span></span> | <span data-ttu-id="ecaad-141">\**工作場所\*\*\*會為 IT 小組設計代表，以定義如何將此變更與組織中的核心工作區架構對齊。*</span><span class="sxs-lookup"><span data-stu-id="ecaad-141">**Workplace Architect** *A representative from the IT team in charge of defining how this change is aligned with the core workplace architecture in the organization.*</span></span>                             | <span data-ttu-id="ecaad-142">R</span><span class="sxs-lookup"><span data-stu-id="ecaad-142">R</span></span>      |
| <span data-ttu-id="ecaad-143">輸入名稱和電子郵件</span><span class="sxs-lookup"><span data-stu-id="ecaad-143">Enter name and email</span></span> | <span data-ttu-id="ecaad-144">\**安全性分析員\*\*\*來自 CDOC 小組的代表，可提供偵測功能、使用者經驗，以及安全性作業觀點之變更的整體有用性的意見反應。*</span><span class="sxs-lookup"><span data-stu-id="ecaad-144">**Security Analyst** *A representative from the CDOC team who can provide feedback on the detection capabilities, user experience, and overall usefulness of this change from a security operations perspective.*</span></span> | <span data-ttu-id="ecaad-145">I</span><span class="sxs-lookup"><span data-stu-id="ecaad-145">I</span></span>      |

## <a name="prepare-your-azure-active-directory"></a><span data-ttu-id="ecaad-146">準備您的 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ecaad-146">Prepare your Azure Active Directory</span></span>
<span data-ttu-id="ecaad-147">如果您已啟用 Active Directory 和 Azure Active Directory 內部部署之間的同步處理，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="ecaad-147">Skip this step if you have already enabled synchronization between Active Directory and Azure Active Directory on premises.</span></span> <span data-ttu-id="ecaad-148">從 Azure Active Directory 複查現有的最佳作法檔。</span><span class="sxs-lookup"><span data-stu-id="ecaad-148">Review existing best practices documentation from Azure Active Directory.</span></span> <span data-ttu-id="ecaad-149">下列步驟經過優化，可以評估或執行 Microsoft 365 Defender 專案的試用版。</span><span class="sxs-lookup"><span data-stu-id="ecaad-149">The following steps are optimized to evaluate or run a pilot Microsoft 365 Defender project.</span></span>

1. <span data-ttu-id="ecaad-150">移至 [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) 入口網站 > **azure AD Connect** 。</span><span class="sxs-lookup"><span data-stu-id="ecaad-150">Go to the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) portal > **Azure AD Connect**.</span></span> 
<span data-ttu-id="ecaad-151">![Azure Active Directory 入口網站頁面的影像](../../media/mtp-eval-1.png)</span><span class="sxs-lookup"><span data-stu-id="ecaad-151">![Image of Azure Active Directory portal page](../../media/mtp-eval-1.png)</span></span> <br> 

2. <span data-ttu-id="ecaad-152">按一下 **Download** [從 **Microsoft Azure Active Directory 連線]** ，然後將它轉接至您的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="ecaad-152">Click **Download** from **Microsoft Azure Active Directory Connect** and transfer it to your Domain Controller.</span></span>
<span data-ttu-id="ecaad-153">![Azure Active Directoru Connect 下載頁面的圖像](../../media/mtp-eval-2.png)</span><span class="sxs-lookup"><span data-stu-id="ecaad-153">![Image of Azure Active Directoru Connect download page](../../media/mtp-eval-2.png)</span></span> <br>

3. <span data-ttu-id="ecaad-154">在網域控制站上，遵循 Azure Active Directory Connect 嚮導。</span><span class="sxs-lookup"><span data-stu-id="ecaad-154">On the domain controller, follow the Azure Active Directory Connect wizard.</span></span> <span data-ttu-id="ecaad-155">閱讀授權條款和隱私權通知，如果您同意，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ecaad-155">Read the license terms and privacy notice and select the checkbox if you agree.</span></span> <span data-ttu-id="ecaad-156">按一下 [繼續]。</span><span class="sxs-lookup"><span data-stu-id="ecaad-156">Click **Continue**.</span></span>
<span data-ttu-id="ecaad-157">![Azure AD Connect 歡迎頁面的圖像](../../media/mtp-eval-3.png)</span><span class="sxs-lookup"><span data-stu-id="ecaad-157">![Image of Azure AD Connect welcome page](../../media/mtp-eval-3.png)</span></span> <br>

4. <span data-ttu-id="ecaad-158">流覽至 **Express 設定** 。</span><span class="sxs-lookup"><span data-stu-id="ecaad-158">Navigate to **Express Settings**.</span></span>
<span data-ttu-id="ecaad-159">![快速設定頁面的圖像](../../media/mtp-eval-4.png)</span><span class="sxs-lookup"><span data-stu-id="ecaad-159">![Image of Express Settings page](../../media/mtp-eval-4.png)</span></span> <br>

5. <span data-ttu-id="ecaad-160">輸入您的全域系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="ecaad-160">Enter your global administrator credentials.</span></span> <span data-ttu-id="ecaad-161">按 [下一步 **]** 。</span><span class="sxs-lookup"><span data-stu-id="ecaad-161">Click **Next**.</span></span>
<span data-ttu-id="ecaad-162">![您應輸入全域系統管理員認證的 [連線到 Azure AD] 頁面影像](../../media/mtp-eval-5.png)</span><span class="sxs-lookup"><span data-stu-id="ecaad-162">![Image of Connect to Azure AD page where you should enter your global administrator credentials](../../media/mtp-eval-5.png)</span></span> <br>

6. <span data-ttu-id="ecaad-163">輸入您的 Active Directory 網域服務企業系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="ecaad-163">Enter your Active Directory Domain Services enterprise administrator credentials.</span></span> <span data-ttu-id="ecaad-164">按 [下一步 **]** 。</span><span class="sxs-lookup"><span data-stu-id="ecaad-164">Click **Next**.</span></span>
<span data-ttu-id="ecaad-165">![您應輸入認證的 [連線到 AD DS] 頁面影像](../../media/mtp-eval-6.png)</span><span class="sxs-lookup"><span data-stu-id="ecaad-165">![Image of Connect to AD DS page where you should enter your credentials](../../media/mtp-eval-6.png)</span></span> <br>

7. <span data-ttu-id="ecaad-166">按一下 [ **安裝** ] 以確認設定。</span><span class="sxs-lookup"><span data-stu-id="ecaad-166">Click **Install** to confirm the configuration.</span></span>
<span data-ttu-id="ecaad-167">![設定確認頁面的影像](../../media/mtp-eval-7.png)</span><span class="sxs-lookup"><span data-stu-id="ecaad-167">![Image of configuration confirmation page](../../media/mtp-eval-7.png)</span></span> <br>

8. <span data-ttu-id="ecaad-168">恭喜，您已成功設定 Azure Active Directory Connect。</span><span class="sxs-lookup"><span data-stu-id="ecaad-168">Congratulations, you have successfully configured Azure Active Directory Connect.</span></span>
<span data-ttu-id="ecaad-169">![已成功設定 Azure Active Directory Connect 頁面的圖像](../../media/mtp-eval-8.png)</span><span class="sxs-lookup"><span data-stu-id="ecaad-169">![Image of a successfully configured Azure Active Directory Connect page](../../media/mtp-eval-8.png)</span></span> <br>

<span data-ttu-id="ecaad-170">您現在可以 [將使用者和群組新增至 Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) ，並 [設定 SAM-R 原則](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)。</span><span class="sxs-lookup"><span data-stu-id="ecaad-170">You can now [add users and groups to Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) and [configure a SAM-R policy](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).</span></span>  


## <a name="configuration-order"></a><span data-ttu-id="ecaad-171">設定順序</span><span class="sxs-lookup"><span data-stu-id="ecaad-171">Configuration order</span></span>
<span data-ttu-id="ecaad-172">下表指出 Microsoft 建議為您的試用實驗室或試驗環境部署設定 Microsoft 365 Defender 元件的順序。</span><span class="sxs-lookup"><span data-stu-id="ecaad-172">The following table indicates the order Microsoft recommends for configuring the Microsoft 365 Defender components for your trial lab or pilot environment deployment.</span></span>

| <span data-ttu-id="ecaad-173">元件</span><span class="sxs-lookup"><span data-stu-id="ecaad-173">Component</span></span>                               | <span data-ttu-id="ecaad-174">描述</span><span class="sxs-lookup"><span data-stu-id="ecaad-174">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="ecaad-175">設定順序排名</span><span class="sxs-lookup"><span data-stu-id="ecaad-175">Configuration order rank</span></span> |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|<span data-ttu-id="ecaad-176">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ecaad-176">Microsoft Defender for Office 365</span></span>|<span data-ttu-id="ecaad-177">Microsoft Defender for Office 365 保護您的組織免受電子郵件訊息、連結 (URLs) 和共同作業工具所造成的惡意威脅。</span><span class="sxs-lookup"><span data-stu-id="ecaad-177">Microsoft Defender for Office 365 safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <br> [<span data-ttu-id="ecaad-178">瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="ecaad-178">Learn more.</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | <span data-ttu-id="ecaad-179">1 </span><span class="sxs-lookup"><span data-stu-id="ecaad-179">1</span></span>                   |
|<span data-ttu-id="ecaad-180">適用於身分識別的 Microsoft Defender </span><span class="sxs-lookup"><span data-stu-id="ecaad-180">Microsoft Defender for Identity</span></span>|<span data-ttu-id="ecaad-181">Microsoft Defender for Identity 使用 Active Directory 信號來識別、偵測和調查您組織中的高級威脅、已遭破壞的身分識別，以及惡意的有問必答行為。</span><span class="sxs-lookup"><span data-stu-id="ecaad-181">Microsoft Defender for Identity uses Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <br> <span data-ttu-id="ecaad-182">[深入了解](https://docs.microsoft.com/azure-advanced-threat-protection/)。</span><span class="sxs-lookup"><span data-stu-id="ecaad-182">[Learn more](https://docs.microsoft.com/azure-advanced-threat-protection/).</span></span>| <span data-ttu-id="ecaad-183">第</span><span class="sxs-lookup"><span data-stu-id="ecaad-183">2</span></span> |
|<span data-ttu-id="ecaad-184">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ecaad-184">Microsoft Cloud App Security</span></span>| <span data-ttu-id="ecaad-185">Microsoft Cloud App Security 是雲端存取安全性經紀人 (CASB) ，可在多個雲端上運作。</span><span class="sxs-lookup"><span data-stu-id="ecaad-185">Microsoft Cloud App Security is a Cloud Access Security Broker (CASB) that operates on multiple clouds.</span></span> <span data-ttu-id="ecaad-186">它可提供豐富的知名度、控制資料旅行和複雜的分析，以在所有雲端服務之間識別及打擊 cyberthreats。</span><span class="sxs-lookup"><span data-stu-id="ecaad-186">It provides rich visibility, control over data travel, and sophisticated analytics to identify and combat cyberthreats across all your cloud services.</span></span> <br> <span data-ttu-id="ecaad-187">[深入了解](https://docs.microsoft.com/cloud-app-security/)。</span><span class="sxs-lookup"><span data-stu-id="ecaad-187">[Learn more](https://docs.microsoft.com/cloud-app-security/).</span></span>                                                                                                                                                                                                                                                                                                                                                                       |<span data-ttu-id="ecaad-188">個</span><span class="sxs-lookup"><span data-stu-id="ecaad-188">3</span></span>                   |
|<span data-ttu-id="ecaad-189">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ecaad-189">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="ecaad-190">Microsoft Defender for Endpoint endpoint endpoint 偵測和回應功能提供接近即時及可行動的高級攻擊偵測。</span><span class="sxs-lookup"><span data-stu-id="ecaad-190">Microsoft Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="ecaad-191">安全性分析人員可以有效地排定警示的優先順序、深入了解入侵的全貌，並採取回應動作來補救威脅。</span><span class="sxs-lookup"><span data-stu-id="ecaad-191">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span> <br> [<span data-ttu-id="ecaad-192">瞭解更多資訊。</span><span class="sxs-lookup"><span data-stu-id="ecaad-192">Learn more.</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |<span data-ttu-id="ecaad-193">4 </span><span class="sxs-lookup"><span data-stu-id="ecaad-193">4</span></span>                   |                                                                                                                                                                                                                                    

## <a name="next-step"></a><span data-ttu-id="ecaad-194">下一步</span><span class="sxs-lookup"><span data-stu-id="ecaad-194">Next step</span></span>
|<span data-ttu-id="ecaad-195">![階段2：設定](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="ecaad-195">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="ecaad-196">階段2：設定</span><span class="sxs-lookup"><span data-stu-id="ecaad-196">Phase 2: Setup</span></span>](setup-mtpeval.md) | <span data-ttu-id="ecaad-197">設定您的 Microsoft 365 Defender 試用實驗室或試驗環境</span><span class="sxs-lookup"><span data-stu-id="ecaad-197">Set up your Microsoft 365 Defender trial lab or pilot environment</span></span>
|:-------|:-----|

