---
title: 設定舊版 Office 365 郵件加密的 Azure 版權管理
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
description: Office 365 邮件加密的早期版本依赖于 Microsoft Azure 权限管理（以前称为 Windows Azure 活动目录权限管理）。
ms.openlocfilehash: 84922a57c6245cf3214f17ba922417b5e025b796
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077393"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="ed038-103">設定舊版 Office 365 郵件加密的 Azure 版權管理</span><span class="sxs-lookup"><span data-stu-id="ed038-103">Set up Azure Rights Management for the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="ed038-104">本主题介绍激活并随后设置 Azure 权限管理 （RMS） 的步骤，这是 Azure 信息保护的一部分，以便与 Office 365 消息加密 （OME） 的早期版本一起使用。</span><span class="sxs-lookup"><span data-stu-id="ed038-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="ed038-105">本文仅适用于早期版本的 OME</span><span class="sxs-lookup"><span data-stu-id="ed038-105">This article only applies to the previous version of OME</span></span>
<span data-ttu-id="ed038-106">如果您尚未将 Office 365 组织迁移到新的 OME 功能，但已部署 OME，则本文中的信息将应用于您的组织。</span><span class="sxs-lookup"><span data-stu-id="ed038-106">If you haven't yet moved your Office 365 organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="ed038-107">Microsoft 建议您在您的组织合理时尽快制定计划，以迁移到新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="ed038-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="ed038-108">有关说明，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="ed038-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="ed038-109">如果要首先了解有关新功能工作方式的更多信息，请参阅[Office 365 邮件加密](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="ed038-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="ed038-110">本文的其余部分是指在新的 OME 功能发布之前的 OME 行为。</span><span class="sxs-lookup"><span data-stu-id="ed038-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="ed038-111">使用早期版本的 Office 365 邮件加密的先决条件</span><span class="sxs-lookup"><span data-stu-id="ed038-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="ed038-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="ed038-112"></span></span>

<span data-ttu-id="ed038-113">Office 365 消息加密 （OME） （包括 IRM） 依赖于 Azure 权限管理 （Azure RMS）。</span><span class="sxs-lookup"><span data-stu-id="ed038-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="ed038-114">Azure RMS 是 Azure 信息保护所使用的保护技术。</span><span class="sxs-lookup"><span data-stu-id="ed038-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="ed038-115">要使用 OME，Office 365 组织必须包括 Exchange 联机或 Exchange 联机保护订阅，而该订阅又包括 Azure 权限管理订阅。</span><span class="sxs-lookup"><span data-stu-id="ed038-115">To use OME, your Office 365 organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="ed038-116">如果您不确定订阅包含的内容，请参阅[有关消息策略、恢复和合规性](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)的 Exchange 在线服务说明。</span><span class="sxs-lookup"><span data-stu-id="ed038-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span></span>

- <span data-ttu-id="ed038-117">如果没有用于 Exchange 联机或 Exchange 联机保护的 Azure RMS 订阅，则必须先购买订阅并激活它。</span><span class="sxs-lookup"><span data-stu-id="ed038-117">If you don't have an Azure RMS subscription for Exchange Online or Exchange Online Protection, you must purchase a subscription and activate it first.</span></span>

    <span data-ttu-id="ed038-118">有关购买 Azure 权限管理的订阅的信息，请参阅[Azure 权限管理](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT)。</span><span class="sxs-lookup"><span data-stu-id="ed038-118">For information about purchasing a subscription to Azure Rights Management, see [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT).</span></span> <span data-ttu-id="ed038-119">下節提供啟動 Azure Rights Management 的資訊。</span><span class="sxs-lookup"><span data-stu-id="ed038-119">The next section gives you information about activating Azure Rights Management.</span></span>

- <span data-ttu-id="ed038-120">如果您有 Azure 权限管理，但未为 Exchange 联机或 Exchange 联机保护设置，则本文介绍了如何激活 Azure 权限管理，然后介绍了设置 OME 以使用 Azure 权限管理的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="ed038-120">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="ed038-121">如果已设置 OME 以使用 Azure 权限管理以进行联机交换或交换联机保护，具体取决于设置方式，则可以立即开始使用 OME 及其新功能。</span><span class="sxs-lookup"><span data-stu-id="ed038-121">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="ed038-122">本文介绍如何确定是否正确设置了 OME，如果需要更改设置该怎么办，以及选择不更改设置会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="ed038-122">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="ed038-123">例如，为了使用新功能，必须将 Azure RMS 与 OME 一起使用。</span><span class="sxs-lookup"><span data-stu-id="ed038-123">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="ed038-124">不能将新功能与本地活动目录 RMS 一起使用。</span><span class="sxs-lookup"><span data-stu-id="ed038-124">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="ed038-125">在 Office 365 中为早期版本的 OME 激活 Azure 权限管理</span><span class="sxs-lookup"><span data-stu-id="ed038-125">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="ed038-126">您需要激活 Azure 权限管理，以便组织中的用户可以对其发送的邮件应用信息保护，并打开受 Azure 权限管理服务保护的邮件和文件。</span><span class="sxs-lookup"><span data-stu-id="ed038-126">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="ed038-127">有关说明，请参阅[激活 Azure 权限管理](https://go.microsoft.com/fwlink/p/?LinkId=525775)。</span><span class="sxs-lookup"><span data-stu-id="ed038-127">For instructions, see [Activating Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775).</span></span> <span data-ttu-id="ed038-128">完成激活后，请返回此处并继续执行本文中的任务。</span><span class="sxs-lookup"><span data-stu-id="ed038-128">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="ed038-129">通过导入受信任的发布域 （TLD），将早期版本的 OME 设置为使用 Azure RMS</span><span class="sxs-lookup"><span data-stu-id="ed038-129">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="ed038-130">TPD 是一个 XML 文件，其中包含有关组织权限管理设置的信息。</span><span class="sxs-lookup"><span data-stu-id="ed038-130">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="ed038-131">例如，TPD 包含有关用于签名和加密证书和许可证的服务器许可方证书 （SLC） 的信息、用于许可和发布的 URL 等。</span><span class="sxs-lookup"><span data-stu-id="ed038-131">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="ed038-132">使用 Windows PowerShell 将 TPD 导入 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="ed038-132">You import the TPD into your Office 365 organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ed038-133">以前，您可以选择将 TD 从活动目录权限管理服务 （AD RMS） 导入 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="ed038-133">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your Office 365 organization.</span></span> <span data-ttu-id="ed038-134">但是，这样做将阻止您使用新的 OME 功能，并且不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="ed038-134">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="ed038-135">如果 Office 365 组织当前以这种方式配置，Microsoft 建议您创建计划，以便从本地活动目录 RMS 迁移到基于云的 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="ed038-135">If your Office 365 organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="ed038-136">有关详细信息，请参阅从[AD RMS 迁移到 Azure 信息保护](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。</span><span class="sxs-lookup"><span data-stu-id="ed038-136">For more information, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="ed038-137">在完成迁移到 Azure 信息保护之前，您将无法使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="ed038-137">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="ed038-138">**从 Azure RMS 导入 TD**</span><span class="sxs-lookup"><span data-stu-id="ed038-138">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="ed038-139">[使用远程电源外壳连接到在线交换。](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ed038-139">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="ed038-140">选择与 Office 365 组织的地理位置对应的密钥共享 URL：</span><span class="sxs-lookup"><span data-stu-id="ed038-140">Choose the key-sharing URL that corresponds to your Office 365 organization's geographic location:</span></span>

|<span data-ttu-id="ed038-141">**位置**</span><span class="sxs-lookup"><span data-stu-id="ed038-141">**Location**</span></span>|<span data-ttu-id="ed038-142">**密钥共享位置 URL**</span><span class="sxs-lookup"><span data-stu-id="ed038-142">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed038-143">北美</span><span class="sxs-lookup"><span data-stu-id="ed038-143">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="ed038-144">歐盟</span><span class="sxs-lookup"><span data-stu-id="ed038-144">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="ed038-145">亚洲</span><span class="sxs-lookup"><span data-stu-id="ed038-145">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="ed038-146">南美洲</span><span class="sxs-lookup"><span data-stu-id="ed038-146">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="ed038-147">Office 365 for Government (政府社群雲端)</span><span class="sxs-lookup"><span data-stu-id="ed038-147">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="ed038-148">此 RMS 密钥共享位置保留给已为政府 SKU 购买 Office 365 的客户。</span><span class="sxs-lookup"><span data-stu-id="ed038-148">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. <span data-ttu-id="ed038-149">通过运行[Set-IRM 配置](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx)cmdlet 来配置密钥共享位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ed038-149">Configure the key-sharing location by running the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet as follows:</span></span> 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    <span data-ttu-id="ed038-150">例如，如果您的组织位于北美，则配置密钥共享位置：</span><span class="sxs-lookup"><span data-stu-id="ed038-150">For example, to configure the key sharing location if your organization is located in North America:</span></span>
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. <span data-ttu-id="ed038-151">使用 -RMSOnline 开关运行[导入-RMS 信任发布域](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx)cmdlet 以从 Azure 权限管理导入 TPD：</span><span class="sxs-lookup"><span data-stu-id="ed038-151">Run the [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    <span data-ttu-id="ed038-152">其中*TPDName*是您要用于 TPD 的名称。</span><span class="sxs-lookup"><span data-stu-id="ed038-152">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="ed038-153">例如，"康托索北美 TPD"。</span><span class="sxs-lookup"><span data-stu-id="ed038-153">For example, "Contoso North American TPD".</span></span> 
    
5. <span data-ttu-id="ed038-154">要验证是否成功配置了 Office 365 组织以使用 Azure 权限管理服务，请使用 -RMSOnline 开关运行[测试 IRM 配置](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx)cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ed038-154">To verify that you successfully configured your Office 365 organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet with the -RMSOnline switch as follows:</span></span> 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    <span data-ttu-id="ed038-155">除其他事项外，此 cmdlet 会检查与 Azure 权限管理服务的连接，下载 TPD 并检查其有效性。</span><span class="sxs-lookup"><span data-stu-id="ed038-155">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>
    
6. <span data-ttu-id="ed038-156">运行[Set-IRM 配置](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)cmdlet，如下所示，以禁用 Azure 权限管理模板在 Web 和 Outlook 上的 Outlook 中可用：</span><span class="sxs-lookup"><span data-stu-id="ed038-156">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. <span data-ttu-id="ed038-157">按如下方式运行[Set-IRM 配置](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)cmdlet，为基于云的电子邮件组织启用 Azure 权限管理，并将其配置为对 Office 365 邮件加密使用 Azure 权限管理：</span><span class="sxs-lookup"><span data-stu-id="ed038-157">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span> 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. <span data-ttu-id="ed038-158">要验证是否成功导入了 TPD 并启用了 Azure 权限管理，请使用测试 IRM 配置 cmdlet 来测试 Azure 权限管理功能。</span><span class="sxs-lookup"><span data-stu-id="ed038-158">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="ed038-159">有关详细信息，请参阅[测试 IRM 配置](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)中的"示例 1"。</span><span class="sxs-lookup"><span data-stu-id="ed038-159">For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span></span>
    
## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="ed038-160">我使用活动目录权限管理而不是 Azure 信息保护设置了早期版本的 OME，我该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ed038-160">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="ed038-161"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="ed038-161"></span></span>

<span data-ttu-id="ed038-162">您可以继续使用现有的 Office 365 邮件加密邮件流规则与活动目录权限管理，但您无法配置或使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="ed038-162">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="ed038-163">相反，您需要迁移到 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="ed038-163">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="ed038-164">有关迁移及其对组织意味着什么的信息，请参阅从 AD [RMS 迁移到 Azure 信息保护](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)。</span><span class="sxs-lookup"><span data-stu-id="ed038-164">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="ed038-165">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ed038-165">Next steps</span></span>
<span data-ttu-id="ed038-166"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="ed038-166"></span></span>

<span data-ttu-id="ed038-167">完成 Azure 权限管理设置后，如果要启用新的 OME 功能，请参阅[设置在 Azure 信息保护之上构建的新 Office 365 邮件加密功能。](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span><span class="sxs-lookup"><span data-stu-id="ed038-167">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span></span>
  
<span data-ttu-id="ed038-168">将组织设置为使用新的 OME 功能后，即可[定义邮件流规则，以使用新的 OME 功能保护电子邮件。](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="ed038-168">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ed038-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="ed038-169">Related topics</span></span>
<span data-ttu-id="ed038-170"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="ed038-170"></span></span>

[<span data-ttu-id="ed038-171">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="ed038-171">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="ed038-172">關於 Office 365 中加密的技術參考細節</span><span class="sxs-lookup"><span data-stu-id="ed038-172">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="ed038-173">什么是 Azure 权限管理？</span><span class="sxs-lookup"><span data-stu-id="ed038-173">What is Azure Rights Management?</span></span>](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

