---
title: 資訊保護基礎結構的允出準則
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
ms.openlocfilehash: 02e972a80d4b42ae66193bbbc55d0f1e63be5ba6
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047236"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="d17ed-103">資訊保護基礎結構的允出準則</span><span class="sxs-lookup"><span data-stu-id="d17ed-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="d17ed-104">請確定您的資訊保護基礎結構符合下列必要準則，而且您已將這些視為選擇性準則。</span><span class="sxs-lookup"><span data-stu-id="d17ed-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="d17ed-105">必要：定義組織的安全性和資訊保護層級</span><span class="sxs-lookup"><span data-stu-id="d17ed-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="d17ed-p101">您已規劃並決定組織需要的安全性層級。這些層級定義了最低層級的安全性和資訊機密性增加的其他層級及其所需的資料安全性。</span><span class="sxs-lookup"><span data-stu-id="d17ed-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="d17ed-108">您至少要使用三種安全性層級：</span><span class="sxs-lookup"><span data-stu-id="d17ed-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="d17ed-109">基準</span><span class="sxs-lookup"><span data-stu-id="d17ed-109">Baseline</span></span>
- <span data-ttu-id="d17ed-110">敏感性</span><span class="sxs-lookup"><span data-stu-id="d17ed-110">Sensitive</span></span>
- <span data-ttu-id="d17ed-111">高管制</span><span class="sxs-lookup"><span data-stu-id="d17ed-111">Highly regulated</span></span>

<span data-ttu-id="d17ed-112">如有需要，[步驟 1](infoprotect-define-sec-infoprotect-levels.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="d17ed-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="d17ed-113">必要：設定增強的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="d17ed-113">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="d17ed-114">您已為 [Office 365 增強的安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="d17ed-114">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="d17ed-115">Microsoft 365 安全性中心的威脅管理原則</span><span class="sxs-lookup"><span data-stu-id="d17ed-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="d17ed-116">Exchange Online 的其他全租用戶設定</span><span class="sxs-lookup"><span data-stu-id="d17ed-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="d17ed-117">SharePoint Online 系統管理中心中的全租用戶共用原則</span><span class="sxs-lookup"><span data-stu-id="d17ed-117">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="d17ed-118">Azure Active Directory (Azure AD) 中的設定</span><span class="sxs-lookup"><span data-stu-id="d17ed-118">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="d17ed-119">您已經[為 SharePoint、OneDrive 和 Microsoft Teams 啟用了 Office 365 進階威脅防護 (ATP)](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)。</span><span class="sxs-lookup"><span data-stu-id="d17ed-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="d17ed-120">如有需要，[步驟 3](infoprotect-configure-increased-security-office-365.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="d17ed-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="d17ed-121">選用：設定環境的分類</span><span class="sxs-lookup"><span data-stu-id="d17ed-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="d17ed-122">您已與您的法務和法規遵循小組合作，為組織的資料監管和安全性原則開發出適當的分類和標籤配置。</span><span class="sxs-lookup"><span data-stu-id="d17ed-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="d17ed-123">這些原則對應以下設定及部署：</span><span class="sxs-lookup"><span data-stu-id="d17ed-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="d17ed-124">敏感資料類型</span><span class="sxs-lookup"><span data-stu-id="d17ed-124">Sensitive data types</span></span>
- <span data-ttu-id="d17ed-125">保留標籤</span><span class="sxs-lookup"><span data-stu-id="d17ed-125">Retention labels</span></span>
- <span data-ttu-id="d17ed-126">敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="d17ed-126">Sensitivity labels</span></span>
- <span data-ttu-id="d17ed-127">Azure 資訊保護標籤</span><span class="sxs-lookup"><span data-stu-id="d17ed-127">Azure Information Protection labels</span></span>

<span data-ttu-id="d17ed-128">如有需要，[步驟 2](infoprotect-configure-classification.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="d17ed-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="d17ed-129">選用：在您的環境之間部署 Windows 資訊保護</span><span class="sxs-lookup"><span data-stu-id="d17ed-129">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="d17ed-130">您已註冊 Windows 10 企業版裝置，該裝置已部署並套用 Intune 原則，定義了：</span><span class="sxs-lookup"><span data-stu-id="d17ed-130">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="d17ed-131">要保護的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d17ed-131">Which apps to protect.</span></span>
- <span data-ttu-id="d17ed-132">保護的層級。</span><span class="sxs-lookup"><span data-stu-id="d17ed-132">The level of protection.</span></span>
- <span data-ttu-id="d17ed-133">保護延伸的位置。</span><span class="sxs-lookup"><span data-stu-id="d17ed-133">Where the protection extends.</span></span>

<span data-ttu-id="d17ed-134">如有需要，[步驟 4](infoprotect-deploy-windows-information-protection.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="d17ed-134">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="d17ed-135">選用：部署 Office 365 資料外洩防護 (DLP)</span><span class="sxs-lookup"><span data-stu-id="d17ed-135">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="d17ed-136">您已分析、測試然後推出一組 DLP 原則 (具有位置和規則與條件和動作)，貴組織需要保護客戶和其他類型的私密資料，並且遵循產業和地區法規及需求。</span><span class="sxs-lookup"><span data-stu-id="d17ed-136">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="d17ed-137">您的資料合規性和安全性人員使用 Office 365 安全性與合規性中心儀表板來監視 DLP 事件。</span><span class="sxs-lookup"><span data-stu-id="d17ed-137">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="d17ed-138">如有需要，[步驟 5](infoprotect-data-loss-prevention.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="d17ed-138">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a><span data-ttu-id="d17ed-139">選用：已設定電子郵件加密</span><span class="sxs-lookup"><span data-stu-id="d17ed-139">Optional: Email encryption is configured</span></span>

<span data-ttu-id="d17ed-140">您已視需要設定組織的以下電子郵件加密：</span><span class="sxs-lookup"><span data-stu-id="d17ed-140">You've configured the following email encryption as needed for your organization:</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="d17ed-141">**加密方法**</span><span class="sxs-lookup"><span data-stu-id="d17ed-141">**Encryption method**</span></span> | <span data-ttu-id="d17ed-142">**針對傳送的電子郵件**</span><span class="sxs-lookup"><span data-stu-id="d17ed-142">**For email sent**</span></span> |
| [<span data-ttu-id="d17ed-143">Office 365 郵件加密 (OME)</span><span class="sxs-lookup"><span data-stu-id="d17ed-143">Office 365 Message Encryption (OME)</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | <span data-ttu-id="d17ed-144">在組織外部使用加密</span><span class="sxs-lookup"><span data-stu-id="d17ed-144">Outside your organization with encryption</span></span> |
| [<span data-ttu-id="d17ed-145">資訊版權管理 (IRM)</span><span class="sxs-lookup"><span data-stu-id="d17ed-145">Information Rights Management (IRM)</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | <span data-ttu-id="d17ed-146">具有加密和權限</span><span class="sxs-lookup"><span data-stu-id="d17ed-146">With both encryption and permissions</span></span> |
| <span data-ttu-id="d17ed-147">[安全多用途網際網路郵件延伸 (S/MIME)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime)</span><span class="sxs-lookup"><span data-stu-id="d17ed-147">[](https://docs.microsoft.com/Exchange/policy-and-compliance/smime)Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span> | <span data-ttu-id="d17ed-148">使用公開金鑰加密同時使用加密和數位簽章</span><span class="sxs-lookup"><span data-stu-id="d17ed-148">With both encryption and digital signatures using public key cryptography</span></span> |
|||

<span data-ttu-id="d17ed-149">如有需要，[步驟 6](infoprotect-email-encryption.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="d17ed-149">If needed, [Step 6](infoprotect-email-encryption.md) can help you meet this requirement.</span></span>

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="d17ed-150">選用：在 Office 365 中設定特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="d17ed-150">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="d17ed-151">您已使用[在 Office 365 中設定特殊存取權限管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主題中的資訊來啟用特殊存取權限，並在組織中建立一個或多個特殊存取權限原則。</span><span class="sxs-lookup"><span data-stu-id="d17ed-151">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="d17ed-152">您已設定這些原則，並且啟用了即時存取，以存取敏感資料或存取關鍵配置設定。</span><span class="sxs-lookup"><span data-stu-id="d17ed-152">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="d17ed-153">如有需要，[步驟 7](infoprotect-configure-privileged-access-management.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="d17ed-153">If needed, [Step 7](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="d17ed-154">結果和後續步驟</span><span class="sxs-lookup"><span data-stu-id="d17ed-154">Results and next steps</span></span>

<span data-ttu-id="d17ed-155">Microsoft 365 企業版的資訊保護基礎架構使用已定義的安全性層級、Office 365 的增強安全性、使用敏感資料類型和標籤的分類、Windows 資訊保護、資料外洩防護、電子郵件加密以及特殊存取權限管理。</span><span class="sxs-lookup"><span data-stu-id="d17ed-155">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, and privileged access management.</span></span>

<span data-ttu-id="d17ed-156">如果您遵照 Microsoft 365 企業版的端到端部署，那麼現在您已準備好讓[工作負載和案例](deploy-workloads.md)利用基礎架構的所有功能和設定。</span><span class="sxs-lookup"><span data-stu-id="d17ed-156">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
