---
title: 步驟 7：設定 Office 365 的特殊權限存取管理
f1.keywords:
- NOCSH
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
ms.custom: ''
description: 了解及設定 Office 365 的特殊權限存取管理。
ms.openlocfilehash: f29b1e0934a4b9a6d4e3347584f39423d446ed58
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067230"
---
# <a name="step-7-configure-privileged-access-management-for-office-365"></a><span data-ttu-id="8ac9a-103">步驟 7：設定 Office 365 的特殊權限存取管理</span><span class="sxs-lookup"><span data-stu-id="8ac9a-103">Step 7: Configure privileged access management for Office 365</span></span>

<span data-ttu-id="8ac9a-104">*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 和進階合規性版本*</span><span class="sxs-lookup"><span data-stu-id="8ac9a-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![階段 6：資訊保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="8ac9a-p101">特殊權限存取管理的啟用方法是透過設定原則，該原則會指定您的 Office 365 租用戶中工作型活動的 Just-In-Time 存取。它可以協助保護貴組織免於受到使用現有特殊權限系統管理員帳戶與機密資料的常設存取權或關鍵組態設定之存取權的缺口。例如，您可能會設定特殊權限存取管理原則，該原則需要明確核准的存取權，並且會變更您的 Office 365 租用戶中的組織信箱設定。</span><span class="sxs-lookup"><span data-stu-id="8ac9a-p101">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="8ac9a-p102">在這個步驟中，您會在 Office 365 租用戶中啟用特殊權限存取管理，並且設定特殊權限存取原則，該原則為 Office 365 資料的工作型存取以及貴組織的組態設定，提供額外的安全性。在您的 Office 365 組織中開始使用特殊權限存取有三個基本步驟：</span><span class="sxs-lookup"><span data-stu-id="8ac9a-p102">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>
- <span data-ttu-id="8ac9a-111">建立核准者的群組</span><span class="sxs-lookup"><span data-stu-id="8ac9a-111">Creating an approver's group</span></span>
- <span data-ttu-id="8ac9a-112">啟用特殊權限存取</span><span class="sxs-lookup"><span data-stu-id="8ac9a-112">Enabling privileged access</span></span>
- <span data-ttu-id="8ac9a-113">建立核准原則</span><span class="sxs-lookup"><span data-stu-id="8ac9a-113">Creating approval policies</span></span>

<span data-ttu-id="8ac9a-p103">一旦設定，特殊權限存取管理就會讓貴組織以零常設特殊權限來運作，並且針對由於此類常設系統管理存取而引發的漏洞提供一層防護。特殊權限存取需要對執行具有已定義相關聯核准原則的工作進行核准。需要執行包含在核准原則內工作的使用者必須要求存取核准並且獲得授與，才能夠具有執行原則中定義工作的必要權限。</span><span class="sxs-lookup"><span data-stu-id="8ac9a-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="8ac9a-117">若要啟用 Office 365 特殊權限存取管理，請參閱[在 Office 365 中設定特殊權限存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) 主題。</span><span class="sxs-lookup"><span data-stu-id="8ac9a-117">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="8ac9a-118">如需詳細資訊，請參閱 [Office 365 中的特殊權限存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) 主題。</span><span class="sxs-lookup"><span data-stu-id="8ac9a-118">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="8ac9a-120">若要在測試實驗室環境中練習此組態，請參閱[特許存取管理測試實驗室指南](privileged-access-microsoft-365-enterprise-dev-test-environment.md) (部分內容機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="8ac9a-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="8ac9a-121">作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step7)。</span><span class="sxs-lookup"><span data-stu-id="8ac9a-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8ac9a-122">下一步</span><span class="sxs-lookup"><span data-stu-id="8ac9a-122">Next Step</span></span>

[<span data-ttu-id="8ac9a-123">資訊保護基礎結構的允出準則</span><span class="sxs-lookup"><span data-stu-id="8ac9a-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
