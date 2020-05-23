---
title: '適用於企業工作負載的 Microsoft 365 '
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 讓貴組織的使用者快速上手企業用 Microsoft 365 的生產力工作負載。
ms.openlocfilehash: 0e1658655c4b97a7e571d1ac09c4b2edcc6c82ce
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268271"
---
# <a name="microsoft-365-for-enterprise-workloads"></a><span data-ttu-id="97a5b-103">適用於企業工作負載的 Microsoft 365 </span><span class="sxs-lookup"><span data-stu-id="97a5b-103">Microsoft 365 for enterprise workloads</span></span>

<span data-ttu-id="97a5b-104">若要獲得企業用 Microsoft 365 的創意暨團隊合作優點，請將這些工作負載部署到底層基礎結構上：</span><span class="sxs-lookup"><span data-stu-id="97a5b-104">To get the creativity and teamwork benefits of Microsoft 365 for enterprise, deploy these workloads over your foundation infrastructure:</span></span>

- [<span data-ttu-id="97a5b-105">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="97a5b-105">Microsoft Teams</span></span>](teams-workload.md)
- [<span data-ttu-id="97a5b-106">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="97a5b-106">Exchange Online</span></span>](exchangeonline-workload.md)
- [<span data-ttu-id="97a5b-107">SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="97a5b-107">SharePoint and OneDrive</span></span>](sharepoint-online-onedrive-workload.md)

<span data-ttu-id="97a5b-108">請參閱[移轉](migration-microsoft-365-enterprise-workload.md)文章，以了解用來將整個組織移轉到企業用 Microsoft 365 的一般藍圖，其內含 Microsoft Office 用戶端產品、內部部署 Office Server 產品和 Microsoft Windows 架構裝置。</span><span class="sxs-lookup"><span data-stu-id="97a5b-108">See the [migration](migration-microsoft-365-enterprise-workload.md) article for a general roadmap to migrate your entire organization to Microsoft 365 for enterprise, which includes Microsoft Office client products, on-premises Office Server products, and Microsoft Windows-based devices.</span></span>

<span data-ttu-id="97a5b-109">以下是整體企業用 Microsoft 365 部署指南中的工作負載：</span><span class="sxs-lookup"><span data-stu-id="97a5b-109">Here are the workloads in the overall Microsoft 365 for enterprise deployment guide:</span></span>

![整體企業用 Microsoft 365 部署指南中的工作負載](../media/deploy-workloads/m365-deploy-content-arch-workloads.png)

## <a name="foundation-infrastructure-prerequisites"></a><span data-ttu-id="97a5b-111">底層基礎結構先決條件</span><span class="sxs-lookup"><span data-stu-id="97a5b-111">Foundation infrastructure prerequisites</span></span>

<span data-ttu-id="97a5b-112">理論上\*\*，您應該在設定好[底層基礎結構](deploy-foundation-infrastructure.md)的所有階段後，再部署工作負載。</span><span class="sxs-lookup"><span data-stu-id="97a5b-112">*Ideally*, you should deploy workloads after you have configured all of the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span> <span data-ttu-id="97a5b-113">這可確保所有基礎層級都已就緒，而可為使用者及其裝置提供整合、安全性及最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="97a5b-113">This ensures that all of the underlying foundation layers are in place to provide integration, security, and the best experience for your users and their devices.</span></span>

| <span data-ttu-id="97a5b-114">階段</span><span class="sxs-lookup"><span data-stu-id="97a5b-114">Phase</span></span> | <span data-ttu-id="97a5b-115">結果</span><span class="sxs-lookup"><span data-stu-id="97a5b-115">Result</span></span> |
|:-------|:-----|
| <span data-ttu-id="97a5b-116">網路</span><span class="sxs-lookup"><span data-stu-id="97a5b-116">Network</span></span> | <span data-ttu-id="97a5b-117">網路會進行更新，以獲得最佳的 Microsoft 365 雲端服務效能。</span><span class="sxs-lookup"><span data-stu-id="97a5b-117">Your network is updated for optimum performance to Microsoft 365 cloud services.</span></span> |
| <span data-ttu-id="97a5b-118">身分識別</span><span class="sxs-lookup"><span data-stu-id="97a5b-118">Identity</span></span> | <span data-ttu-id="97a5b-119">身分識別會進行同步處理，並讓使用者帳戶使用增強式驗證以及讓系統管理員帳戶使用保護機制來確保身分識別的安全。</span><span class="sxs-lookup"><span data-stu-id="97a5b-119">Identity is synchronized and secured with strong authentication for user accounts and protection for admin accounts.</span></span> |
| <span data-ttu-id="97a5b-120">Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="97a5b-120">Windows 10 Enterprise</span></span> | <span data-ttu-id="97a5b-121">執行 Windows 7 或 Windows 8.1 的電腦可升級為 Windows 10 企業版，且新裝置會使用 Windows 10 企業版來進行安裝。</span><span class="sxs-lookup"><span data-stu-id="97a5b-121">Your computers running Windows 7 or Windows 8.1 can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
| <span data-ttu-id="97a5b-122">Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="97a5b-122">Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="97a5b-123">現有的 Microsoft Office 使用者可升級為 Microsoft 365 Apps 企業版。</span><span class="sxs-lookup"><span data-stu-id="97a5b-123">Your existing users of Microsoft Office can upgrade to Microsoft 365 Apps for enterprise.</span></span> |
| <span data-ttu-id="97a5b-124">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="97a5b-124">Mobile device management</span></span> | <span data-ttu-id="97a5b-125">裝置可以進行註冊並受到管理。</span><span class="sxs-lookup"><span data-stu-id="97a5b-125">Your devices can be enrolled and managed.</span></span> |
| <span data-ttu-id="97a5b-126">資訊保護</span><span class="sxs-lookup"><span data-stu-id="97a5b-126">Information protection</span></span> | <span data-ttu-id="97a5b-127">會啟用 Microsoft 365 資訊保護功能，且敏感度標籤或 Azure 資訊保護標籤已準備好而可保護文件和電子郵件。</span><span class="sxs-lookup"><span data-stu-id="97a5b-127">Microsoft 365 information protection features are configured and your sensitivity or Azure Information Protection labels are ready to protect documents and email.</span></span> |

<span data-ttu-id="97a5b-128">請記住，這是理想狀況，您可能需要花點時間來規劃、設定、測試和試驗，尤其是有既存基礎結構和多個位置的大型組織更是如此。</span><span class="sxs-lookup"><span data-stu-id="97a5b-128">Remember that this is ideal and can take some time to plan for, configure, test, and pilot, especially in large organizations with existing infrastructure and multiple locations.</span></span> <span data-ttu-id="97a5b-129">您不一定要為了更快速地從企業用 Microsoft 365 獲得商業價值，而在所有位置完成所有階段。</span><span class="sxs-lookup"><span data-stu-id="97a5b-129">Completing all of these phases in all locations is not necessary for you to more quickly get business value from Microsoft 365 for enterprise.</span></span> 

<span data-ttu-id="97a5b-130">以下是一些要立即部署的常見工作負載：</span><span class="sxs-lookup"><span data-stu-id="97a5b-130">Here are some common workloads to deploy right away:</span></span> 

- <span data-ttu-id="97a5b-131">在對使用者推出底層基礎結構的**身分識別**階段後，許多組織會部署：</span><span class="sxs-lookup"><span data-stu-id="97a5b-131">After the **Identity** phase of the foundation infrastructure is rolled out to users, many organizations deploy:</span></span>
  - <span data-ttu-id="97a5b-132">與 [OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) 結合的 [Microsoft 365 Apps 企業版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="97a5b-132">[Microsoft 365 Apps for enterprise](office365proplus-infrastructure.md) combined with [OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span> <span data-ttu-id="97a5b-133">Microsoft 365 Apps 企業版可提供新式驗證的安全性和最新 Microsoft Office 用戶端的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="97a5b-133">Microsoft 365 Apps for enterprise provides the security of modern authentication and the user experience of the latest Microsoft Office client.</span></span> <span data-ttu-id="97a5b-134">將使用者的個人檔案移轉到 OneDrive 會減少基礎結構和對於主資料夾及主目錄磁碟的支援需求。</span><span class="sxs-lookup"><span data-stu-id="97a5b-134">The migration of user's personal files to OneDrive reduces infrastructure and the need to support home folders and drives.</span></span>
  - <span data-ttu-id="97a5b-135">[Exchange Online](exchangeonline-workload.md)，讓使用者可以開始使用雲端式電子郵件。</span><span class="sxs-lookup"><span data-stu-id="97a5b-135">[Exchange Online](exchangeonline-workload.md) so that users can begin using cloud-based email.</span></span>
- <span data-ttu-id="97a5b-136">如果您並非立即需要在雲端中儲存高度管制的數位資產，請先為使用者部署 [Microsoft Teams](teams-workload.md) 和 [SharePoint](sharepoint-online-onedrive-workload.md)，再部署**資訊保護**階段。</span><span class="sxs-lookup"><span data-stu-id="97a5b-136">If you don't have an immediate need for storing highly regulated digital assets in the cloud, deploy [Microsoft Teams](teams-workload.md) and [SharePoint](sharepoint-online-onedrive-workload.md) for your users prior to the **Information protection** phase.</span></span>

<span data-ttu-id="97a5b-137">您必須決定要如何針對底層基礎結構的先決條件階段，做出最佳的設定順序並進行部署，才能符合您的業務需求。</span><span class="sxs-lookup"><span data-stu-id="97a5b-137">You must decide on how to best order and deploy the configuration of prerequisite phases of foundation infrastructure to meet your business needs.</span></span>

### <a name="best-practice"></a><span data-ttu-id="97a5b-138">最佳作法</span><span class="sxs-lookup"><span data-stu-id="97a5b-138">Best practice</span></span>

<span data-ttu-id="97a5b-139">強烈建議您先部署和推出底層基礎結構的**身分識別**階段，再讓使用者快速上手工作負載或案例。</span><span class="sxs-lookup"><span data-stu-id="97a5b-139">We highly recommend that you deploy and roll out the **Identity** phase of the foundation infrastructure prior to onboarding your users to any workloads or scenarios.</span></span>

<span data-ttu-id="97a5b-140">**身分識別**階段可確保雲端式身分識別 (無論是只有雲端，還是會與內部部署 Active Directory Domain Services (AD DS) 同步處理) 會包含可用來管理驗證及存取的使用者和電腦帳戶與群組。</span><span class="sxs-lookup"><span data-stu-id="97a5b-140">The **Identity** phase ensures that your cloud-based identity, whether cloud-only or synchronized with your on-premises Active Directory Domain Services (AD DS), contains the user and computer accounts and groups to manage authentication and access.</span></span> <span data-ttu-id="97a5b-141">所有使用者都必須使用增強式驗證且系統管理員帳戶必須使用增強式保護，才能將組織的數位資產放入 Microsoft 365 雲端。</span><span class="sxs-lookup"><span data-stu-id="97a5b-141">Strong authentication for all your users along with strong protection of admin accounts is required before placing your organization's digital assets in the Microsoft 365 cloud.</span></span>

<span data-ttu-id="97a5b-142">雖然整體效能是基本且非常重要的要求，然而在將使用者導入工作負載的同時，**網路**階段的部署可能仍在進行中，因為您知道 Microsoft 365 工作負載和服務係能會隨著時間的而改善。</span><span class="sxs-lookup"><span data-stu-id="97a5b-142">Although foundational and very important to overall performance, the rollout of the **Networking** phase can be in progress while onboarding your users to workloads, with the understanding that Microsoft 365 workload and service performance will improve over time.</span></span> <span data-ttu-id="97a5b-143">對於有多個位置並混合使用邊緣裝置與網際網路連線的企業組織來說，更是如此。</span><span class="sxs-lookup"><span data-stu-id="97a5b-143">This is especially true for enterprise organizations with multiple locations and a mixture of edge devices and Internet connections.</span></span>
