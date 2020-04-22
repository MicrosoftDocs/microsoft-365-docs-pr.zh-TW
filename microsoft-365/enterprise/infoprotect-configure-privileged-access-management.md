---
title: 步驟7：設定特殊許可權存取管理
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
description: 瞭解和設定特殊許可權存取管理。
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636985"
---
# <a name="step-7-configure-privileged-access-management"></a><span data-ttu-id="22d76-103">步驟7：設定特殊許可權存取管理</span><span class="sxs-lookup"><span data-stu-id="22d76-103">Step 7: Configure privileged access management</span></span>

<span data-ttu-id="22d76-104">*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 和進階合規性版本*</span><span class="sxs-lookup"><span data-stu-id="22d76-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![第 6 階段：資訊保護](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="22d76-106">設定特殊許可權存取管理是透過設定在您租使用者中的任務型活動的即時存取原則來啟用。</span><span class="sxs-lookup"><span data-stu-id="22d76-106">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant.</span></span> <span data-ttu-id="22d76-107">它可以協助保護您的組織不會因可能使用現有的許可權系統管理員帳戶存取機密資料或存取重要的設定設定而遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="22d76-107">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="22d76-108">例如，您可以設定特殊許可權存取管理原則，此原則需要明確核准，才能存取和變更您租使用者中的組織信箱設定。</span><span class="sxs-lookup"><span data-stu-id="22d76-108">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="22d76-109">在這個步驟中，您將在您的租使用者中啟用特殊許可權存取管理，並設定特殊許可權存取原則，以提供對組織之資料和設定設定的任務型存取的額外安全性。</span><span class="sxs-lookup"><span data-stu-id="22d76-109">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization.</span></span> <span data-ttu-id="22d76-110">您的組織中有三個基本步驟可讓您開始使用具有特殊許可權的存取權：</span><span class="sxs-lookup"><span data-stu-id="22d76-110">There are three basic steps to get started with privileged access in your organization:</span></span>
- <span data-ttu-id="22d76-111">建立核准者的群組</span><span class="sxs-lookup"><span data-stu-id="22d76-111">Creating an approver's group</span></span>
- <span data-ttu-id="22d76-112">啟用特殊權限存取</span><span class="sxs-lookup"><span data-stu-id="22d76-112">Enabling privileged access</span></span>
- <span data-ttu-id="22d76-113">建立核准原則</span><span class="sxs-lookup"><span data-stu-id="22d76-113">Creating approval policies</span></span>

<span data-ttu-id="22d76-p103">一旦設定，特殊權限存取管理就會讓貴組織以零常設特殊權限來運作，並且針對由於此類常設系統管理存取而引發的漏洞提供一層防護。特殊權限存取需要對執行具有已定義相關聯核准原則的工作進行核准。需要執行包含在核准原則內工作的使用者必須要求存取核准並且獲得授與，才能夠具有執行原則中定義工作的必要權限。</span><span class="sxs-lookup"><span data-stu-id="22d76-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="22d76-117">若要啟用特殊許可權存取管理，請參閱設定特殊許可權[存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)主題。</span><span class="sxs-lookup"><span data-stu-id="22d76-117">To enable privileged access management, see the [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="22d76-118">如需詳細資訊，請參閱「[特權存取管理](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)」主題。</span><span class="sxs-lookup"><span data-stu-id="22d76-118">For more information, see the [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="22d76-120">若要在測試實驗室環境中練習此組態，請參閱[特許存取管理測試實驗室指南](privileged-access-microsoft-365-enterprise-dev-test-environment.md) (部分內容機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="22d76-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="22d76-121">作為過渡期的檢查點，您可以看到與此步驟相對應的[允出準則](infoprotect-exit-criteria.md#crit-infoprotect-step7)。</span><span class="sxs-lookup"><span data-stu-id="22d76-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="22d76-122">下一步</span><span class="sxs-lookup"><span data-stu-id="22d76-122">Next Step</span></span>

[<span data-ttu-id="22d76-123">資訊保護基礎結構的允出準則</span><span class="sxs-lookup"><span data-stu-id="22d76-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
