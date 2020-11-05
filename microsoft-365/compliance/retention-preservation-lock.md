---
title: 使用「保留鎖定」來限制變更保留原則和保留標籤原則
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 將「保留鎖定」搭配保留原則和保留標籤原則使用，以協助您符合法規需求，並防範惡意系統管理員。
ms.openlocfilehash: 6f6cfc5bef9b93af08fcc9b703b29facb9a7c576
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920689"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a><span data-ttu-id="05bab-103">使用「保留鎖定」來限制變更保留原則和保留標籤原則</span><span class="sxs-lookup"><span data-stu-id="05bab-103">Use Preservation Lock to restrict changes to retention policies and retention label policies</span></span>

><span data-ttu-id="05bab-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="05bab-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="05bab-105">「保留鎖定」可確保您的組織能夠符合這類法規需求，因為它會鎖定保留原則或保留標籤原則，使得沒有任何人 (包括系統管理員) 可以關閉原則、刪除原則或降低限制。</span><span class="sxs-lookup"><span data-stu-id="05bab-105">Preservation Lock locks a retention policy or retention label policy so that no one—including a global admin—can turn off the policy, delete the policy, or make it less restrictive.</span></span> <span data-ttu-id="05bab-106">可能有法規需求需要此設定，並有助於防範惡意系統管理員。</span><span class="sxs-lookup"><span data-stu-id="05bab-106">This configuration might be needed for regulatory requirements and can help safeguard against rogue administrators.</span></span>

<span data-ttu-id="05bab-107">當保留原則鎖定時：</span><span class="sxs-lookup"><span data-stu-id="05bab-107">When a policy for retention is locked:</span></span>

- <span data-ttu-id="05bab-108">沒有人可以將它關閉</span><span class="sxs-lookup"><span data-stu-id="05bab-108">No one can turn it off</span></span>
- <span data-ttu-id="05bab-109">可以新增位置但不能移除位置</span><span class="sxs-lookup"><span data-stu-id="05bab-109">Locations can be added but not removed</span></span>
- <span data-ttu-id="05bab-110">您可以延長保留期間，但不能減少保留期間</span><span class="sxs-lookup"><span data-stu-id="05bab-110">You can extend a retention period but not decrease it</span></span>

<span data-ttu-id="05bab-111">總的來説，鎖定的保留原則可以增加或延長，但是不能減少或關閉。</span><span class="sxs-lookup"><span data-stu-id="05bab-111">In summary, a locked policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="05bab-112">在您鎖定保留原則或保留標籤原則之前，請務必了解其影響，並確認您的組織是否需要它。</span><span class="sxs-lookup"><span data-stu-id="05bab-112">Before you lock a retention policy or retention label policy, it's critical that you understand the impact and confirm whether it's required for your organization.</span></span> <span data-ttu-id="05bab-113">例如，可能需要它來滿足法規需求。</span><span class="sxs-lookup"><span data-stu-id="05bab-113">For example, it might be needed to meet regulatory requirements.</span></span> <span data-ttu-id="05bab-114">套用保留鎖定之後，系統管理員將無法停用或刪除保留原則。</span><span class="sxs-lookup"><span data-stu-id="05bab-114">Administrators won't be able to disable or delete these policies after the preservation lock is applied.</span></span>

<span data-ttu-id="05bab-115">請在您建立[保留原則](create-retention-policies.md)，或[發佈](create-apply-retention-labels.md)或[自動套用](apply-retention-labels-automatically.md)保留標籤原則之後，再設定保留鎖定。</span><span class="sxs-lookup"><span data-stu-id="05bab-115">Configure Preservation Lock after you've created a [retention policy](create-retention-policies.md), or a retention label policy that you [publish](create-apply-retention-labels.md) or [auto-apply](apply-retention-labels-automatically.md).</span></span> 

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a><span data-ttu-id="05bab-116">如何鎖定保留原則或保留標籤原則</span><span class="sxs-lookup"><span data-stu-id="05bab-116">How to lock a retention policy or retention label policy</span></span>

<span data-ttu-id="05bab-117">如果您需要使用保留鎖定，您必須使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="05bab-117">You must use PowerShell if you need to use Preservation Lock.</span></span> <span data-ttu-id="05bab-118">因為系統管理員無法在套用保留鎖定之後停用或刪除保留原則，因此在 UI 中無法使用此功能來防範意外的設定。</span><span class="sxs-lookup"><span data-stu-id="05bab-118">Because administrators can't disable or delete a policy for retention after this lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="05bab-119">具有任何設定的所有保留原則都支持保留鎖定。</span><span class="sxs-lookup"><span data-stu-id="05bab-119">All policies for retention and with any configuration support Preservation Lock.</span></span>

1. <span data-ttu-id="05bab-120">[連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="05bab-120">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="05bab-121">執行 [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy) ，並尋找您想要鎖定的原則名稱。</span><span class="sxs-lookup"><span data-stu-id="05bab-121">Find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="05bab-122">例如：</span><span class="sxs-lookup"><span data-stu-id="05bab-122">For example:</span></span>
    
   ![PowerShell 中保留原則的清單](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. <span data-ttu-id="05bab-124">若要將保留鎖定置於保留原則上，請以保留原則名稱執行 [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet，並將 *RestrictiveRetention* 參數設為 true：</span><span class="sxs-lookup"><span data-stu-id="05bab-124">To place a Preservation Lock on your policy, run the [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet with the name of the policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="05bab-125">例如：</span><span class="sxs-lookup"><span data-stu-id="05bab-125">For example:</span></span>
    
    ![PowerShell 中的 RestrictiveRetention 參數](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="05bab-127">當系統提示時，請閱讀並輸入 **Y** 來認可此設定隨附的限制：</span><span class="sxs-lookup"><span data-stu-id="05bab-127">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y** :</span></span>
    
   ![確認您在 PowerShell 想要鎖定保留原則的提示。](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="05bab-129">保留鎖定現在放置於保留原則上。</span><span class="sxs-lookup"><span data-stu-id="05bab-129">A Preservation Lock is now placed on the policy.</span></span> <span data-ttu-id="05bab-130">若要確認，請再次執行 `Get-RetentionCompliancePolicy`，但指定保留原則名稱並顯示原則參數：</span><span class="sxs-lookup"><span data-stu-id="05bab-130">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="05bab-131">您應該會看到 **RestrictiveRetention** 設定為 **True** 。</span><span class="sxs-lookup"><span data-stu-id="05bab-131">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="05bab-132">例如：</span><span class="sxs-lookup"><span data-stu-id="05bab-132">For example:</span></span>

![PowerShell 中顯示所有參數的鎖定原則](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a><span data-ttu-id="05bab-134">另請參閱</span><span class="sxs-lookup"><span data-stu-id="05bab-134">See also</span></span>

[<span data-ttu-id="05bab-135">協助您符合資訊管理與記錄管理法規需求的資源</span><span class="sxs-lookup"><span data-stu-id="05bab-135">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)
