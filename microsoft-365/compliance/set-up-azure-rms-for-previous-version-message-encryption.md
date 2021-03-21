---
title: 設定舊版郵件加密的 Azure Rights Management
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 先前版本的 Office 365 郵件加密，取決於 Microsoft Azure Rights Management (先前稱為 Windows Azure Active Directory Rights Management) 。
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919489"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a><span data-ttu-id="98c2b-103">設定舊版郵件加密的 Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="98c2b-103">Set up Azure Rights Management for the previous version of Message Encryption</span></span>

<span data-ttu-id="98c2b-104">本主題說明您必須遵循的步驟，才能啟動並設定 Azure Rights Management (RMS) （Azure 資訊保護的一部分），以用於舊版 Office 365 郵件加密 (OME) 。</span><span class="sxs-lookup"><span data-stu-id="98c2b-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="98c2b-105">本文僅適用于舊版的 OME</span><span class="sxs-lookup"><span data-stu-id="98c2b-105">This article only applies to the previous version of OME</span></span>

<span data-ttu-id="98c2b-106">如果您尚未將組織移至新的 OME 功能，但您已部署 OME，則本文中的資訊適用于您的組織。</span><span class="sxs-lookup"><span data-stu-id="98c2b-106">If you haven't yet moved your organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="98c2b-107">Microsoft 建議您在組織合理的情況時，安排移至新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="98c2b-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="98c2b-108">如需相關指示，請參閱 [Set up New Office 365 Message Encryption 功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="98c2b-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="98c2b-109">如果您想要進一步瞭解新功能的運作方式，請參閱 [Office 365 Message Encryption](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="98c2b-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="98c2b-110">本文的其餘部分是在發行新的 OME 功能之前，OME 行為。</span><span class="sxs-lookup"><span data-stu-id="98c2b-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="98c2b-111">使用舊版 Office 365 郵件加密的必要條件</span><span class="sxs-lookup"><span data-stu-id="98c2b-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="98c2b-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="98c2b-112"><a name="warmprereqs"> </a></span></span>

<span data-ttu-id="98c2b-113">Office 365 郵件加密 (OME) （包括 IRM）取決於 Azure Rights Management (Azure RMS) 。</span><span class="sxs-lookup"><span data-stu-id="98c2b-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="98c2b-114">Azure RMS 是 Azure 資訊保護所使用的保護技術。</span><span class="sxs-lookup"><span data-stu-id="98c2b-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="98c2b-115">若要使用 OME，您的組織必須包含 Exchange Online 或 Exchange Online Protection 訂閱，進而包含 Azure Rights Management 訂閱。</span><span class="sxs-lookup"><span data-stu-id="98c2b-115">To use OME, your organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="98c2b-116">若不確定您的訂閱所包含的內容，請參閱 [訊息原則、復原和合規性](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)的 Exchange Online 服務說明。</span><span class="sxs-lookup"><span data-stu-id="98c2b-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

- <span data-ttu-id="98c2b-117">如果您有 Azure Rights Management，但未設定 Exchange Online 或 Exchange Online Protection，本文將說明如何啟用 Azure 版權管理，然後描述設定 OME 以搭配 Azure Rights Management 的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="98c2b-117">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="98c2b-118">如果您已設定 OME 以使用 Azure Rights Management for Exchange Online 或 Exchange Online Protection （取決於其設定方式），您可能會立即開始使用 OME 及其新功能。</span><span class="sxs-lookup"><span data-stu-id="98c2b-118">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="98c2b-119">本文說明如何判斷您是否已正確設定 OME、需要變更設定的方式，以及如果您選擇不要變更設定，會發生什麼事。</span><span class="sxs-lookup"><span data-stu-id="98c2b-119">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="98c2b-120">例如，若要使用新功能，您必須搭配使用 Azure RMS 與 OME。</span><span class="sxs-lookup"><span data-stu-id="98c2b-120">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="98c2b-121">您無法搭配內部部署 Active Directory RMS 使用新功能。</span><span class="sxs-lookup"><span data-stu-id="98c2b-121">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="98c2b-122">在 Office 365 中啟動舊版 OME 的 Azure 版權管理</span><span class="sxs-lookup"><span data-stu-id="98c2b-122">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="98c2b-123">您必須啟用 Azure Rights Management，讓組織中的使用者能夠對傳送的郵件套用資訊保護，並開啟已由 Azure Rights Management 服務保護的郵件和檔案。</span><span class="sxs-lookup"><span data-stu-id="98c2b-123">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="98c2b-124">如需相關指示，請參閱 [啟用 Azure Rights Management](/azure/information-protection/activate-service)。</span><span class="sxs-lookup"><span data-stu-id="98c2b-124">For instructions, see [Activating Azure Rights Management](/azure/information-protection/activate-service).</span></span> <span data-ttu-id="98c2b-125">當您完成啟用之後，請回到這裡，繼續執行本文中的工作。</span><span class="sxs-lookup"><span data-stu-id="98c2b-125">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="98c2b-126">透過匯入信任的發行網域 (Tpd，將舊版的 OME 設定為使用 Azure RMS) </span><span class="sxs-lookup"><span data-stu-id="98c2b-126">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="98c2b-127">TPD 是一種 XML 檔案，其中包含組織的版權管理設定資訊。</span><span class="sxs-lookup"><span data-stu-id="98c2b-127">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="98c2b-128">例如，TPD 包含伺服器許可方憑證的相關資訊， (SLC) 用於簽署和加密憑證和授權、用於授權和發行的 URLs 等。</span><span class="sxs-lookup"><span data-stu-id="98c2b-128">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="98c2b-129">您可以使用 Windows PowerShell 將 TPD 匯入您的組織。</span><span class="sxs-lookup"><span data-stu-id="98c2b-129">You import the TPD into your organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="98c2b-130">先前，您可以選擇從 Active Directory Rights Management service 將 Tpd 匯入到您的組織中 (AD RMS) 。</span><span class="sxs-lookup"><span data-stu-id="98c2b-130">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your organization.</span></span> <span data-ttu-id="98c2b-131">不過，這樣做會使您無法使用新的 OME 功能，因此建議您不要這樣做。</span><span class="sxs-lookup"><span data-stu-id="98c2b-131">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="98c2b-132">如果您的組織目前是以這種方式設定，Microsoft 建議您建立從您的內部部署 Active Directory RMS 遷移至雲端式 Azure 資訊保護的計畫。</span><span class="sxs-lookup"><span data-stu-id="98c2b-132">If your organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="98c2b-133">如需詳細資訊，請參閱 [從 AD RMS 遷移至 Azure 資訊保護](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。</span><span class="sxs-lookup"><span data-stu-id="98c2b-133">For more information, see [Migrating from AD RMS to Azure Information Protection](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="98c2b-134">您必須完成遷移至 Azure 資訊保護後，才能使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="98c2b-134">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="98c2b-135">**從 Azure RMS 匯入 Tpd**</span><span class="sxs-lookup"><span data-stu-id="98c2b-135">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="98c2b-136">[使用遠端 PowerShell 連接至 Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="98c2b-136">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="98c2b-137">選擇對應于您組織之地理位置的金鑰共用 URL：</span><span class="sxs-lookup"><span data-stu-id="98c2b-137">Choose the key-sharing URL that corresponds to your organization's geographic location:</span></span>

|<span data-ttu-id="98c2b-138">**位置**</span><span class="sxs-lookup"><span data-stu-id="98c2b-138">**Location**</span></span>|<span data-ttu-id="98c2b-139">**主要共用位置 URL**</span><span class="sxs-lookup"><span data-stu-id="98c2b-139">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98c2b-140">北美</span><span class="sxs-lookup"><span data-stu-id="98c2b-140">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="98c2b-141">歐盟</span><span class="sxs-lookup"><span data-stu-id="98c2b-141">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="98c2b-142">亞洲</span><span class="sxs-lookup"><span data-stu-id="98c2b-142">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="98c2b-143">南美洲</span><span class="sxs-lookup"><span data-stu-id="98c2b-143">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="98c2b-144">Office 365 for Government (政府社群雲端)</span><span class="sxs-lookup"><span data-stu-id="98c2b-144">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="98c2b-145">此 RMS 金鑰共用位置是針對政府 SKUs 購買 Office 365 的客戶所保留。</span><span class="sxs-lookup"><span data-stu-id="98c2b-145">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. <span data-ttu-id="98c2b-146">執行 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) Cmdlet 以設定金鑰共用位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="98c2b-146">Configure the key-sharing location by running the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows:</span></span> 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   <span data-ttu-id="98c2b-147">例如，若您的組織位於北美，若要設定金鑰共用位置：</span><span class="sxs-lookup"><span data-stu-id="98c2b-147">For example, to configure the key sharing location if your organization is located in North America:</span></span>

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. <span data-ttu-id="98c2b-148">使用-RMSOnline 參數執行 [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) Cmdlet，以從 Azure Rights Management 匯入 TPD：</span><span class="sxs-lookup"><span data-stu-id="98c2b-148">Run the [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   <span data-ttu-id="98c2b-149">其中  *TPDName*  是您要用於 TPD 的名稱。</span><span class="sxs-lookup"><span data-stu-id="98c2b-149">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="98c2b-150">例如，"Contoso 北美 TPD"。</span><span class="sxs-lookup"><span data-stu-id="98c2b-150">For example, "Contoso North American TPD".</span></span> 

5. <span data-ttu-id="98c2b-151">若要確認您是否已成功將組織設定為使用 Azure Rights Management 服務，請使用-RMSOnline 參數執行 [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="98c2b-151">To verify that you successfully configured your organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) cmdlet with the -RMSOnline switch as follows:</span></span>

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   <span data-ttu-id="98c2b-152">此外，此 Cmdlet 還會檢查 Azure 版權管理服務的連線能力、下載 TPD，以及檢查其有效性。</span><span class="sxs-lookup"><span data-stu-id="98c2b-152">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>

6. <span data-ttu-id="98c2b-153">依下列方式執行 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) Cmdlet，以停用 outlook 網頁版和 Outlook 版中的 Azure 版權管理範本：</span><span class="sxs-lookup"><span data-stu-id="98c2b-153">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. <span data-ttu-id="98c2b-154">依下列方式執行 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) Cmdlet，以為您的雲端式電子郵件組織啟用 Azure rights management，並將其設定為使用 Azure rights Management for Office 365 郵件加密：</span><span class="sxs-lookup"><span data-stu-id="98c2b-154">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span>

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. <span data-ttu-id="98c2b-155">若要確認您是否已成功匯入 TPD 及 enabled Azure Rights Management，請使用 Test-IRMConfiguration Cmdlet 來測試 Azure 版權管理功能。</span><span class="sxs-lookup"><span data-stu-id="98c2b-155">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="98c2b-156">如需詳細資訊，請參閱 [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration)中的「範例1」。</span><span class="sxs-lookup"><span data-stu-id="98c2b-156">For details, see "Example 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span></span>

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="98c2b-157">我已將舊版的 OME 設定為使用 Active Directory Rights Management，但不是 Azure 資訊保護，我該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="98c2b-157">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="98c2b-158"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="98c2b-158"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="98c2b-159">您可以繼續使用現有的 Office 365 郵件加密郵件流程規則與 Active Directory Rights Management，但您無法設定或使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="98c2b-159">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="98c2b-160">相反地，您必須遷移到 Azure 資訊保護。</span><span class="sxs-lookup"><span data-stu-id="98c2b-160">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="98c2b-161">如需有關遷移的詳細資訊及其對您組織的意義，請參閱 [從 AD RMS 遷移到 Azure 資訊保護](/information-protection/deploy-use/prepare-environment-adrms)。</span><span class="sxs-lookup"><span data-stu-id="98c2b-161">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="98c2b-162">後續步驟</span><span class="sxs-lookup"><span data-stu-id="98c2b-162">Next steps</span></span>
<span data-ttu-id="98c2b-163"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="98c2b-163"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="98c2b-164">當您完成 Azure Rights Management 安裝程式之後，如果您想要啟用新的 OME 功能，請參閱[設定新的 Office 365 郵件加密功能（以 Azure 資訊保護為](./set-up-new-message-encryption-capabilities.md)基礎）。</span><span class="sxs-lookup"><span data-stu-id="98c2b-164">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)</span></span>
  
<span data-ttu-id="98c2b-165">在您設定組織使用新的 OME 功能之後，您就可以 [定義郵件流程規則，以使用新的 OME 功能來保護電子郵件](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="98c2b-165">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="98c2b-166">相關主題</span><span class="sxs-lookup"><span data-stu-id="98c2b-166">Related topics</span></span>
<span data-ttu-id="98c2b-167"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="98c2b-167"><a name="importTPDs"> </a></span></span>

[<span data-ttu-id="98c2b-168">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="98c2b-168">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="98c2b-169">關於 Office 365 中加密的技術參考細節</span><span class="sxs-lookup"><span data-stu-id="98c2b-169">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="98c2b-170">什麼是 Azure 版權管理？</span><span class="sxs-lookup"><span data-stu-id="98c2b-170">What is Azure Rights Management?</span></span>](/information-protection/understand-explore/what-is-azure-rms)