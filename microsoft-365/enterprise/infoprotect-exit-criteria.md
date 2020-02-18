---
title: 資訊保護基礎結構的允出準則
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 檢查資訊保護型服務和基礎結構的準則，確定您的設定符合 Microsoft 365 企業版的需求。
ms.openlocfilehash: 28eff02ea870dcfca7e2e32580ed6a3a9e8a9484
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067110"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="3c0ce-103">資訊保護基礎結構的允出準則</span><span class="sxs-lookup"><span data-stu-id="3c0ce-103">Information protection infrastructure exit criteria</span></span>

![階段 6：資訊保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="3c0ce-105">請確定您的資訊保護基礎結構符合下列必要準則，而且您已將這些視為選擇性準則。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-105">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="3c0ce-106">必要：定義組織的安全性和資訊保護層級</span><span class="sxs-lookup"><span data-stu-id="3c0ce-106">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="3c0ce-p101">您已規劃並決定組織需要的安全性層級。這些層級定義了最低層級的安全性和資訊機密性增加的其他層級及其所需的資料安全性。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="3c0ce-109">您至少要使用三種安全性層級：</span><span class="sxs-lookup"><span data-stu-id="3c0ce-109">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="3c0ce-110">基準</span><span class="sxs-lookup"><span data-stu-id="3c0ce-110">Baseline</span></span>
- <span data-ttu-id="3c0ce-111">敏感性</span><span class="sxs-lookup"><span data-stu-id="3c0ce-111">Sensitive</span></span>
- <span data-ttu-id="3c0ce-112">高管制</span><span class="sxs-lookup"><span data-stu-id="3c0ce-112">Highly regulated</span></span>

<span data-ttu-id="3c0ce-113">如有需要，[步驟 1](infoprotect-define-sec-infoprotect-levels.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-113">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="3c0ce-114">必要：設定增強的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="3c0ce-114">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="3c0ce-115">您已為 [Office 365 增強的安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="3c0ce-115">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="3c0ce-116">Microsoft 365 安全性中心的威脅管理原則</span><span class="sxs-lookup"><span data-stu-id="3c0ce-116">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="3c0ce-117">Exchange Online 的其他全租用戶設定</span><span class="sxs-lookup"><span data-stu-id="3c0ce-117">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="3c0ce-118">SharePoint Online 系統管理中心中的全租用戶共用原則</span><span class="sxs-lookup"><span data-stu-id="3c0ce-118">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="3c0ce-119">Azure Active Directory (Azure AD) 中的設定</span><span class="sxs-lookup"><span data-stu-id="3c0ce-119">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="3c0ce-120">您已經[為 SharePoint、OneDrive 和 Microsoft Teams 啟用了 Office 365 進階威脅防護 (ATP)](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-120">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="3c0ce-121">如有需要，[步驟 3](infoprotect-configure-increased-security-office-365.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-121">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="3c0ce-122">選用：設定環境的分類</span><span class="sxs-lookup"><span data-stu-id="3c0ce-122">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="3c0ce-123">您已與您的法務和法規遵循小組合作，為組織的資料監管和安全性原則開發出適當的分類和標籤配置。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-123">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="3c0ce-124">這些原則對應以下設定及部署：</span><span class="sxs-lookup"><span data-stu-id="3c0ce-124">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="3c0ce-125">敏感資料類型</span><span class="sxs-lookup"><span data-stu-id="3c0ce-125">Sensitive data types</span></span>
- <span data-ttu-id="3c0ce-126">保留標籤</span><span class="sxs-lookup"><span data-stu-id="3c0ce-126">Retention labels</span></span>
- <span data-ttu-id="3c0ce-127">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="3c0ce-127">Sensitivity labels</span></span>
- <span data-ttu-id="3c0ce-128">Azure 資訊保護標籤</span><span class="sxs-lookup"><span data-stu-id="3c0ce-128">Azure Information Protection labels</span></span>

<span data-ttu-id="3c0ce-129">如有需要，[步驟 2](infoprotect-configure-classification.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-129">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="3c0ce-130">選用：在您的環境之間部署 Windows 資訊保護</span><span class="sxs-lookup"><span data-stu-id="3c0ce-130">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="3c0ce-131">您已註冊 Windows 10 企業版裝置，該裝置已部署並套用 Intune 原則，定義了：</span><span class="sxs-lookup"><span data-stu-id="3c0ce-131">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="3c0ce-132">要保護的應用程式。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-132">Which apps to protect.</span></span>
- <span data-ttu-id="3c0ce-133">保護的層級。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-133">The level of protection.</span></span>
- <span data-ttu-id="3c0ce-134">保護延伸的位置。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-134">Where the protection extends.</span></span>

<span data-ttu-id="3c0ce-135">如有需要，[步驟 4](infoprotect-deploy-windows-information-protection.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-135">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="3c0ce-136">選用：部署 Office 365 資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="3c0ce-136">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="3c0ce-137">您已分析、測試然後推出一組 DLP 原則 (具有位置和規則與條件和動作)，貴組織需要保護客戶和其他類型的私密資料，並且遵循產業和地區法規及需求。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-137">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="3c0ce-138">您的資料合規性和安全性人員使用 Office 365 安全性與合規性中心儀表板來監視 DLP 事件。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-138">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="3c0ce-139">如有需要，[步驟 5](infoprotect-data-loss-prevention.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-139">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a><span data-ttu-id="3c0ce-140">選用：已設定電子郵件加密</span><span class="sxs-lookup"><span data-stu-id="3c0ce-140">Optional: Email encryption is configured</span></span>

<span data-ttu-id="3c0ce-141">您已視需要設定組織的以下電子郵件加密：</span><span class="sxs-lookup"><span data-stu-id="3c0ce-141">You've configured the following email encryption as needed for your organization:</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="3c0ce-142">**加密方法**</span><span class="sxs-lookup"><span data-stu-id="3c0ce-142">**Encryption method**</span></span> | <span data-ttu-id="3c0ce-143">**針對傳送的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="3c0ce-143">**For email sent**</span></span> |
| [<span data-ttu-id="3c0ce-144">Office 365 郵件加密 (OME)</span><span class="sxs-lookup"><span data-stu-id="3c0ce-144">Office 365 Message Encryption (OME)</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | <span data-ttu-id="3c0ce-145">在組織外部使用加密</span><span class="sxs-lookup"><span data-stu-id="3c0ce-145">Outside your organization with encryption</span></span> |
| [<span data-ttu-id="3c0ce-146">資訊版權管理 (IRM)</span><span class="sxs-lookup"><span data-stu-id="3c0ce-146">Information Rights Management (IRM)</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | <span data-ttu-id="3c0ce-147">具有加密和權限</span><span class="sxs-lookup"><span data-stu-id="3c0ce-147">With both encryption and permissions</span></span> |
| [<span data-ttu-id="3c0ce-148">安全多用途網際網路郵件延伸 (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="3c0ce-148">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | <span data-ttu-id="3c0ce-149">使用公開金鑰加密同時使用加密和數位簽章</span><span class="sxs-lookup"><span data-stu-id="3c0ce-149">With both encryption and digital signatures using public key cryptography</span></span> |
|||

<span data-ttu-id="3c0ce-150">如有需要，[步驟 6](infoprotect-email-encryption.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-150">If needed, [Step 6](infoprotect-email-encryption.md) can help you meet this requirement.</span></span>

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="3c0ce-151">選用：在 Office 365 中設定特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="3c0ce-151">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="3c0ce-152">您已使用[在 Office 365 中設定特殊存取權限管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主題中的資訊來啟用特殊存取權限，並在組織中建立一個或多個特殊存取權限原則。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-152">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="3c0ce-153">您已設定這些原則，並且啟用了即時存取，以存取敏感資料或存取關鍵配置設定。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-153">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="3c0ce-154">如有需要，[步驟 7](infoprotect-configure-privileged-access-management.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-154">If needed, [Step 7](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="3c0ce-155">結果和後續步驟</span><span class="sxs-lookup"><span data-stu-id="3c0ce-155">Results and next steps</span></span>

<span data-ttu-id="3c0ce-156">Microsoft 365 企業版的資訊保護基礎架構使用已定義的安全性層級、Office 365 的增強安全性、使用敏感資料類型和標籤的分類、Windows 資訊保護、資料外洩防護、電子郵件加密以及特殊存取權限管理。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-156">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, email encryption, and privileged access management.</span></span>

<span data-ttu-id="3c0ce-157">如果您遵照 Microsoft 365 企業版的端到端部署，那麼現在您已準備好讓[工作負載和案例](deploy-workloads.md)利用基礎架構的所有功能和設定。</span><span class="sxs-lookup"><span data-stu-id="3c0ce-157">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
