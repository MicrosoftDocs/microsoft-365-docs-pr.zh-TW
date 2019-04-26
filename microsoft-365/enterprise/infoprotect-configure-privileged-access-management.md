---
title: 步驟 6： 設定 Office 365 的特殊權限的存取管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: 了解及設定 Office 365 的特殊權限存取管理。
ms.openlocfilehash: 60b52825ead068cd0f068f78c1bbce263e8d7720
ms.sourcegitcommit: 9d4319a015e493fb88c7e1855bca0121654eb39d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304153"
---
# <a name="step-6-configure-privileged-access-management-for-office-365"></a><span data-ttu-id="ee27d-103">步驟 6： 設定 Office 365 的特殊權限的存取管理</span><span class="sxs-lookup"><span data-stu-id="ee27d-103">Step 6: Configure privileged access management for Office 365</span></span>

<span data-ttu-id="ee27d-104">*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 和進階合規性版本*</span><span class="sxs-lookup"><span data-stu-id="ee27d-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="ee27d-p101">特殊權限存取管理的啟用方法是透過設定原則，該原則會指定您的 Office 365 租用戶中工作型活動的 Just-In-Time 存取。它可以協助保護貴組織免於受到使用現有特殊權限系統管理員帳戶與機密資料的常設存取權或關鍵組態設定之存取權的缺口。例如，您可能會設定特殊權限存取管理原則，該原則需要明確核准的存取權，並且會變更您的 Office 365 租用戶中的組織信箱設定。</span><span class="sxs-lookup"><span data-stu-id="ee27d-p101">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="ee27d-p102">在這個步驟中，您會在 Office 365 租用戶中啟用特殊權限存取管理，並且設定特殊權限存取原則，該原則為 Office 365 資料的工作型存取以及貴組織的組態設定，提供額外的安全性。在您的 Office 365 組織中開始使用特殊權限存取有三個基本步驟：</span><span class="sxs-lookup"><span data-stu-id="ee27d-p102">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>
- <span data-ttu-id="ee27d-110">建立核准者的群組</span><span class="sxs-lookup"><span data-stu-id="ee27d-110">Creating an approver's group</span></span>
- <span data-ttu-id="ee27d-111">啟用特殊權限存取</span><span class="sxs-lookup"><span data-stu-id="ee27d-111">Enabling privileged access</span></span>
- <span data-ttu-id="ee27d-112">建立核准原則</span><span class="sxs-lookup"><span data-stu-id="ee27d-112">Creating approval policies</span></span>

<span data-ttu-id="ee27d-p103">一旦設定，特殊權限存取管理就會讓貴組織以零常設特殊權限來運作，並且針對由於此類常設系統管理存取而引發的漏洞提供一層防護。特殊權限存取需要對執行具有已定義相關聯核准原則的工作進行核准。需要執行包含在核准原則內工作的使用者必須要求存取核准並且獲得授與，才能夠具有執行原則中定義工作的必要權限。</span><span class="sxs-lookup"><span data-stu-id="ee27d-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="ee27d-116">若要啟用 Office 365 特殊權限存取管理，請參閱[在 Office 365 中設定特殊權限存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) (機器翻譯) 主題。</span><span class="sxs-lookup"><span data-stu-id="ee27d-116">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="ee27d-117">如需詳細資訊，請參閱 [Office 365 中的特殊權限存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) (機器翻譯) 主題。</span><span class="sxs-lookup"><span data-stu-id="ee27d-117">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>

## <a name="results"></a><span data-ttu-id="ee27d-118">結果</span><span class="sxs-lookup"><span data-stu-id="ee27d-118">Results</span></span>

<span data-ttu-id="ee27d-119">這個步驟的結果是您藉由針對貴組織的關鍵資料和組態設定啟用 Just-In-Time 存取控制，增強了 Office 365 的安全性。</span><span class="sxs-lookup"><span data-stu-id="ee27d-119">The result of this step is that you've increased the security of Office 365 by enabling just-in-time access control for key data and configuration settings for your organization.</span></span>

<span data-ttu-id="ee27d-120">作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step6)。</span><span class="sxs-lookup"><span data-stu-id="ee27d-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="ee27d-121">下一步</span><span class="sxs-lookup"><span data-stu-id="ee27d-121">Next Step</span></span>

[<span data-ttu-id="ee27d-122">資訊保護基礎結構的允出準則</span><span class="sxs-lookup"><span data-stu-id="ee27d-122">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)