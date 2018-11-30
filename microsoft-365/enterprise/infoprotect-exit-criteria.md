---
title: 資訊保護基礎結構的允出準則
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 檢查資訊保護型服務和基礎結構的準則，確定您的設定符合 Microsoft 365 企業版的需求。
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866647"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="b0228-103">資訊保護基礎結構的允出準則</span><span class="sxs-lookup"><span data-stu-id="b0228-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="b0228-104">完成基本的基礎結構之前，請確定您的資訊保護基礎結構符合這些條件。</span><span class="sxs-lookup"><span data-stu-id="b0228-104">Before you are complete with your foundation infrastructure, make sure that your information protection infrastructure meets these conditions.</span></span> 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="b0228-105">必要：定義組織的安全性和資訊保護層級</span><span class="sxs-lookup"><span data-stu-id="b0228-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="b0228-p101">您已規劃並決定組織需要的安全性層級。這些層級定義了最低層級的安全性和資訊機密性增加的其他層級及其所需的資料安全性。</span><span class="sxs-lookup"><span data-stu-id="b0228-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="b0228-108">您至少要使用三種安全性層級：</span><span class="sxs-lookup"><span data-stu-id="b0228-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="b0228-109">基準</span><span class="sxs-lookup"><span data-stu-id="b0228-109">Baseline</span></span>
- <span data-ttu-id="b0228-110">敏感性</span><span class="sxs-lookup"><span data-stu-id="b0228-110">Sensitive</span></span>
- <span data-ttu-id="b0228-111">高管制</span><span class="sxs-lookup"><span data-stu-id="b0228-111">Highly regulated</span></span>

<span data-ttu-id="b0228-112">如有需要，[步驟 1](infoprotect-define-sec-infoprotect-levels.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="b0228-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a><span data-ttu-id="b0228-113">必要：設定增強的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="b0228-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="b0228-114">您已根據[設定 Office 365 租用戶的增強安全性](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355)中的資訊，設定下列項目以增強安全性：</span><span class="sxs-lookup"><span data-stu-id="b0228-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span></span>

- <span data-ttu-id="b0228-115">Office 365 安全與規範中心中的威脅管理原則</span><span class="sxs-lookup"><span data-stu-id="b0228-115">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="b0228-116">Exchange Online 的其他全租用戶設定</span><span class="sxs-lookup"><span data-stu-id="b0228-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="b0228-117">SharePoint 系統管理中心中的全租用戶共用原則</span><span class="sxs-lookup"><span data-stu-id="b0228-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="b0228-118">Azure Active Directory 中的設定</span><span class="sxs-lookup"><span data-stu-id="b0228-118">Settings in Azure Active Directory</span></span>

<span data-ttu-id="b0228-119">您也已經[啟用 Office 365 進階威脅防護 (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton)。</span><span class="sxs-lookup"><span data-stu-id="b0228-119">You've also [enabled Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="b0228-120">如有需要，[步驟 3](infoprotect-configure-increased-security-office-365.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="b0228-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="b0228-121">選用：設定環境的分類</span><span class="sxs-lookup"><span data-stu-id="b0228-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="b0228-122">您已與法律和法規遵循小組合作，為組織的資料開發出適當的分類和標籤配置，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="b0228-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span>

- <span data-ttu-id="b0228-123">敏感資料類型</span><span class="sxs-lookup"><span data-stu-id="b0228-123">Sensitive data types</span></span>
- <span data-ttu-id="b0228-124">Office 365 標籤</span><span class="sxs-lookup"><span data-stu-id="b0228-124">Office 365 labels</span></span>
- <span data-ttu-id="b0228-125">Azure 資訊保護標籤</span><span class="sxs-lookup"><span data-stu-id="b0228-125">Azure Information Protection labels</span></span>

<span data-ttu-id="b0228-126">如有需要，[步驟 2](infoprotect-configure-classification.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="b0228-126">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="b0228-127">選用：在 Office 365 中設定特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="b0228-127">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="b0228-p102">您已使用[在 Office 365 中設定特殊權限存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) (機器翻譯) 主題中的資訊，在您的 Office 365 組織中啟用特殊權限存取並建立一或多個特殊權限存取原則。您已設定這些原則並且啟用 Just-In-Time 存取，以存取機密資料或存取重要組態設定。</span><span class="sxs-lookup"><span data-stu-id="b0228-p102">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="b0228-130">如有需要，[步驟 4](infoprotect-configure-privileged-access-management.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="b0228-130">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="next-step"></a><span data-ttu-id="b0228-131">下一步</span><span class="sxs-lookup"><span data-stu-id="b0228-131">Next Step</span></span>

<span data-ttu-id="b0228-132">您現在可以開始部署[工作負載和案例](deploy-workloads.md)，例如在 Microsoft 365 企業版基本基礎結構上執行的 Microsoft Teams 和 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b0228-132">You're now ready to deploy [workloads and scenarios](deploy-workloads.md), such as Microsoft Teams and Exchange Online, that run on top of your Microsoft 365 Enterprise foundation infrastructure.</span></span>
