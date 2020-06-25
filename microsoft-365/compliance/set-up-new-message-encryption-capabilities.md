---
title: 設定全新的郵件加密功能
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 瞭解可與組織內外的人員進行受保護的電子郵件通訊的全新 Office 365 訊息加密功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6d6e37da7456cfbb0b7cbf8d986b54615aca60f0
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819183"
---
# <a name="set-up-new-message-encryption-capabilities"></a><span data-ttu-id="e644d-103">設定全新的郵件加密功能</span><span class="sxs-lookup"><span data-stu-id="e644d-103">Set up new Message Encryption capabilities</span></span>

<span data-ttu-id="e644d-104">新的 Office 365 郵件加密 (OME) 功能可讓組織與任何裝置上的任何人共用受保護的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="e644d-104">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="e644d-105">使用者可以與其他 Microsoft 365 組織以及使用 Outlook.com、Gmail 和其他電子郵件服務的非客戶交換受保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="e644d-105">Users can exchange protected messages with other Microsoft 365 organizations, as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="e644d-106">遵循下列步驟以確保新的 OME 功能可在您的組織中使用。</span><span class="sxs-lookup"><span data-stu-id="e644d-106">Follow the steps below to ensure that the new OME capabilities are available in your organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="e644d-107">驗證 Azure 版權管理作用中</span><span class="sxs-lookup"><span data-stu-id="e644d-107">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="e644d-108">全新的 OME 功能利用 [Azure 版權管理服務 (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) 中的保護功能，它是 [Azure 資訊保護](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)用來透過加密和存取控制保護電子郵件和文件的技術。</span><span class="sxs-lookup"><span data-stu-id="e644d-108">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="e644d-109">使用全新 OME 功能的唯一先決條件是必須在組織的租用戶中啟用 [Azure 版權管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)。</span><span class="sxs-lookup"><span data-stu-id="e644d-109">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="e644d-110">如果是，Microsoft 365 會自動啟用新的 OME 功能，您不需要採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="e644d-110">If it is, Microsoft 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="e644d-111">Azure RMS 也會對多數合格方案自動啟用，因此您也不需要對此採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="e644d-111">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="e644d-112">如需詳細資訊，請參閱[啟用 Azure 版權管理](https://docs.microsoft.com/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="e644d-112">See [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e644d-113">如果您使用 Active Directory 版權管理服務 (AD RMS) 搭配 Exchange Online，您需要先[移轉至 Azure 資訊保護](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)，之後才能使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="e644d-113">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="e644d-114">OME 與 AD RMS 不相容。</span><span class="sxs-lookup"><span data-stu-id="e644d-114">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="e644d-115">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="e644d-115">For more information, see:</span></span>

- <span data-ttu-id="e644d-116">[要使用全新的 OME 功能，我需要什麼訂閱？](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities)可檢查您的訂閱方案是否包含 Azure 資訊保護 (其中包含 Azure RMS 功能)。</span><span class="sxs-lookup"><span data-stu-id="e644d-116">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="e644d-117">[Azure 資訊保護](https://azure.microsoft.com/services/information-protection/)可取得購買合格訂閱的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e644d-117">[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="e644d-118">手動啟用 Azure 版權管理</span><span class="sxs-lookup"><span data-stu-id="e644d-118">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="e644d-119">如果您已停用 Azure RMS，或如果它因任何原因無法自動啟用，您可以在以下位置手動啟用：</span><span class="sxs-lookup"><span data-stu-id="e644d-119">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="e644d-120">**Microsoft 365 系統管理中心**：如需相關指示，請參閱[如何從系統管理中心啟用 Azure 版權管理](https://docs.microsoft.com/azure/information-protection/activate-office365)。</span><span class="sxs-lookup"><span data-stu-id="e644d-120">**Microsoft 365 admin center**: See [How to activate Azure Rights Management from the admin center](https://docs.microsoft.com/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="e644d-121">**Azure 入口網站**：如需相關指示，請參閱[如何從 Azure 入口網站中啟用 Azure 版權管理](https://docs.microsoft.com/azure/information-protection/activate-azure)。</span><span class="sxs-lookup"><span data-stu-id="e644d-121">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="e644d-122">設定 Azure 資訊保護租用戶金鑰的管理</span><span class="sxs-lookup"><span data-stu-id="e644d-122">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="e644d-123">這是選擇性的步驟。</span><span class="sxs-lookup"><span data-stu-id="e644d-123">This is an optional step.</span></span> <span data-ttu-id="e644d-124">允許 Microsoft 管理 Azure 資訊保護的根金鑰是大部分組織的預設設定和建議的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="e644d-124">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most organizations.</span></span> <span data-ttu-id="e644d-125">如果是這種情況，您不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="e644d-125">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="e644d-126">有許多原因，例如合規性需求，可能要求您產生及管理您的根金鑰 (也稱為使用自己的金鑰 (BYOK))。</span><span class="sxs-lookup"><span data-stu-id="e644d-126">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="e644d-127">如果是這種情況，建議您完成所需的步驟，之後再設定全新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="e644d-127">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="e644d-128">如需詳細資訊，請參閱[規劃及實作您的 Azure 資訊保護租用戶金鑰](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="e644d-128">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="e644d-129">在 Exchange Online PowerShell 中驗證 新的 OME 設定</span><span class="sxs-lookup"><span data-stu-id="e644d-129">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="e644d-130">您可以驗證您的 Microsoft 365 租用戶已正確設定以使用 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) 中的新 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="e644d-130">You can verify that your Microsoft 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="e644d-131">使用具有 Microsoft 365 租用戶中全域系統管理員權限的帳戶[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e644d-131">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Microsoft 365 tenant.</span></span>

2. <span data-ttu-id="e644d-132">執行 Get-IRMConfiguration Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e644d-132">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="e644d-133">您應該會看到 $True AzureRMSLicensingEnabled 參數，這表示 OME 已設定租用戶中的值。</span><span class="sxs-lookup"><span data-stu-id="e644d-133">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="e644d-134">如果不是，請使用 Set-IRMConfiguration 將 AzureRMSLicensingEnabled 的值設為 $True 以啟用 OME。</span><span class="sxs-lookup"><span data-stu-id="e644d-134">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="e644d-135">使用以下語法來執行 Test-IRMConfiguration Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e644d-135">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="e644d-136">**範例**：</span><span class="sxs-lookup"><span data-stu-id="e644d-136">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="e644d-137">提供寄件者電子郵件是選擇性的，但會強制系統執行額外的檢查。</span><span class="sxs-lookup"><span data-stu-id="e644d-137">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="e644d-138">使用 Microsoft 365 租用戶中任何使用者的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e644d-138">Use the email address of any user in your Microsoft 365 tenant.</span></span>

     <span data-ttu-id="e644d-139">您的結果應該類似於：</span><span class="sxs-lookup"><span data-stu-id="e644d-139">Your results should be similar to:</span></span>

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - <span data-ttu-id="e644d-140">您的組織名稱將取代 *Contoso*。</span><span class="sxs-lookup"><span data-stu-id="e644d-140">Your organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="e644d-141">預設範本名稱可能與上方顯示的不同。</span><span class="sxs-lookup"><span data-stu-id="e644d-141">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="e644d-142">如需詳細資訊，請參閱[設定及管理 Azure 資訊保護的範本](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="e644d-142">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="e644d-143">移除 Remove-PSSession Cmdlet 來與版權管理服務中斷連線。</span><span class="sxs-lookup"><span data-stu-id="e644d-143">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="e644d-144">後續步驟：定義郵件流程規則，以使用新 OME 功能</span><span class="sxs-lookup"><span data-stu-id="e644d-144">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="e644d-145">如果有先前設定的郵件流程規則可加密您的組織中的電子郵件，則必須更新現有規則，才能使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="e644d-145">If there are previously configured mail flow rules to encrypt email in your organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="e644d-146">針對新的部署，您必須建立新的電子郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="e644d-146">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e644d-147">如果您不更新現有的郵件流程規則，您的使用者會繼續收到使用先前的 HTML 附件格式的加密電子郵件，而非新的無縫 OME 體驗。</span><span class="sxs-lookup"><span data-stu-id="e644d-147">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="e644d-148">郵件流程規則決定在何情況下應該加密電子郵件訊息，以及移除該加密的情況。</span><span class="sxs-lookup"><span data-stu-id="e644d-148">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="e644d-149">當您設定規則的動作時，符合規則條件的任何郵件在傳送時都會經過加密。</span><span class="sxs-lookup"><span data-stu-id="e644d-149">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="e644d-150">如需為 OME 建立郵件流程規則的步驟，請參閱[定義郵件流規則以加密 Office 365 中的電子郵件](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="e644d-150">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="e644d-151">若要更新現有規則，以使用新 OME 功能：</span><span class="sxs-lookup"><span data-stu-id="e644d-151">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="e644d-152">在 Microsoft 365 系統管理中心，移至 [系統管理中心] > [Exchange]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e644d-152">In the Microsoft 365 admin center, go to **Admin centers > Exchange**.</span></span>
2. <span data-ttu-id="e644d-153">在 Exchange 系統管理中心，移至 [郵件流程] > [規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e644d-153">In the Exchange admin center, go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="e644d-154">對於每個規則，在 [執行下列動作]\*\*\*\* 中：</span><span class="sxs-lookup"><span data-stu-id="e644d-154">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="e644d-155">選取 [修改郵件安全性]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e644d-155">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="e644d-156">選取 [套用 Office 365 郵件加密與權限保護]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e644d-156">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="e644d-157">從清單中選取 RMS 範本。</span><span class="sxs-lookup"><span data-stu-id="e644d-157">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="e644d-158">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e644d-158">Select **Save**.</span></span>
    - <span data-ttu-id="e644d-159">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e644d-159">Select **OK**.</span></span>
