---
title: 步驟 8：監控同步處理健全狀況
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
description: 了解及設定 Azure AD Connect Health。
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866541"
---
# <a name="step-8-monitor-synchronization-health"></a><span data-ttu-id="c3135-103">步驟 8：監控同步處理健全狀況</span><span class="sxs-lookup"><span data-stu-id="c3135-103">Step 8: Monitor synchronization health</span></span>

<span data-ttu-id="c3135-104">*此為選用步驟，且同時適用於 Microsoft 365 企業版 E3 和 E5 版本*</span><span class="sxs-lookup"><span data-stu-id="c3135-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="c3135-p101">在此步驟中，您會在每個內部部署身分識別伺服器上安裝 Azure AD Connect Health 代理程式，以監控您的身分識別基礎結構，以及由 Azure AD Connect 提供的同步處理服務。監控資訊會在 Azure AD Connect Health 入口網站提供，您可以在其中檢視警訊、效能監控、使用量分析及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="c3135-p101">In Step 4, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect. The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Azure AD Connect Health 的元件](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="c3135-108">如何使用 Azure AD Connect Health 的關鍵設計決策取決於您如何使用 Azure AD Connect：</span><span class="sxs-lookup"><span data-stu-id="c3135-108">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="c3135-109">如果您使用的是**受管理的驗證**選項，請先從[使用 Azure AD Connect Health 搭配同步處理](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)開始，以了解並設定 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="c3135-109">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="c3135-110">如果您使用**同盟驗證**搭配 Active Directory 同盟服務 (AD FS) 來同步處理帳戶及群組名稱，請先從[使用 Azure AD Connect Health 搭配 AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) 開始，以了解並設定 Azure AD Connect Health。</span><span class="sxs-lookup"><span data-stu-id="c3135-110">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="c3135-111">完成此步驟後的結果：</span><span class="sxs-lookup"><span data-stu-id="c3135-111">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="c3135-112">已在內部部署身分識別提供者伺服器上安裝 Azure AD Connect Health 代理程式。</span><span class="sxs-lookup"><span data-stu-id="c3135-112">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="c3135-113">Azure AD Connect Health 入口網站會顯示您內部部署基礎結構和同步處理活動的目前狀態以及 Office 365 和 EMS 訂閱的 Azure AD 租用戶。</span><span class="sxs-lookup"><span data-stu-id="c3135-113">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="c3135-114">作為過渡期的檢查點，您可以看到此步驟的[允出準則](identity-exit-criteria.md#crit-identity-sync-health)。</span><span class="sxs-lookup"><span data-stu-id="c3135-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="c3135-115">下一步</span><span class="sxs-lookup"><span data-stu-id="c3135-115">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="c3135-116">簡化密碼更新</span><span class="sxs-lookup"><span data-stu-id="c3135-116">Simplify password updates</span></span>](identity-password-writeback.md) |

