---
title: 步驟 6：防護認證洩露
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解並設定 Azure AD Identity Protection。
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866763"
---
# <a name="step-6-protect-against-credential-compromise"></a><span data-ttu-id="5593b-103">步驟 6：防護認證洩露</span><span class="sxs-lookup"><span data-stu-id="5593b-103">Step 6: Protect against credential compromise</span></span>

<span data-ttu-id="5593b-104">*此為選用步驟，且僅適用於 Microsoft 365 企業版 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="5593b-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="5593b-p101">在本步驟中，您將學習如何設定原則以防護認證洩露，避免攻擊者判斷出使用者的帳戶名稱和密碼並存取組織的雲端服務和資料。Azure AD Identity Protection 提供許多方法，協助防止攻擊者透過您的帳戶和群組而入侵，以及協助保護您最寶貴的資料。</span><span class="sxs-lookup"><span data-stu-id="5593b-p101">In Step 15, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="5593b-107">使用 Azure AD Identity Protection，您可以：</span><span class="sxs-lookup"><span data-stu-id="5593b-107">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="5593b-108">判斷並處理組織身分識別中潛在的弱點</span><span class="sxs-lookup"><span data-stu-id="5593b-108">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="5593b-p102">Azure AD 使用機器學習來偵測異常和可疑活動，例如登入和登入後的活動。Identity Protection 可使用此資料產生報告和警訊，協助您評估問題及採取行動。</span><span class="sxs-lookup"><span data-stu-id="5593b-p102">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="5593b-111">偵測與組織身分識別相關的可疑活動，並自動進行回應處理</span><span class="sxs-lookup"><span data-stu-id="5593b-111">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="5593b-p103">您可以設定風險原則，在達到指定的風險層級時，會自動回應偵測到的問題。由 Azure Active Directory 和 Enterprise Mobility + Security (EMS) 提供的這些原則，以及其他條件式存取控制，可自動封鎖存取或採取修正動作，包括密碼重設和要求後續登入的多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="5593b-p103">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="5593b-114">調查可疑事件，並使用系統管理動作加以解決</span><span class="sxs-lookup"><span data-stu-id="5593b-114">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="5593b-p104">您可以使用安全性事件的相關資訊來調查風險事件。基本工作流程可用於追蹤調查及啟動修復動作，例如密碼重設。</span><span class="sxs-lookup"><span data-stu-id="5593b-p104">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="5593b-117">請參閱 [Azure AD Identity Protection 的相關詳細資訊](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)。</span><span class="sxs-lookup"><span data-stu-id="5593b-117">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="5593b-118">請參閱[啟用 Azure AD Identity Protection 的步驟](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)。</span><span class="sxs-lookup"><span data-stu-id="5593b-118">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="5593b-119">此步驟的結果會是您已啟用 Azure AD Identity Protection，並將其用於：</span><span class="sxs-lookup"><span data-stu-id="5593b-119">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="5593b-120">解決潛在的身分識別弱點。</span><span class="sxs-lookup"><span data-stu-id="5593b-120">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="5593b-121">偵測可能的認證洩露嘗試。</span><span class="sxs-lookup"><span data-stu-id="5593b-121">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="5593b-122">調查並解決持續的可疑身分識別事件。</span><span class="sxs-lookup"><span data-stu-id="5593b-122">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="5593b-124">測試實驗室指南：Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="5593b-124">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="5593b-125">作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-ident-prot)。</span><span class="sxs-lookup"><span data-stu-id="5593b-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="5593b-126">下一步</span><span class="sxs-lookup"><span data-stu-id="5593b-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="5593b-127">同步處理目錄</span><span class="sxs-lookup"><span data-stu-id="5593b-127">Synchronize directories</span></span>](identity-azure-ad-connect.md) |


