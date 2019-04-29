---
title: Microsoft 365 企業版工作負載和案例
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 讓貴組織的使用者快速上手 Microsoft 365 企業版的生產力工作負載。
ms.openlocfilehash: 30dbf913016687025c6159f1f1fc311462a13d29
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400137"
---
# <a name="microsoft-365-enterprise-workloads-and-scenarios"></a><span data-ttu-id="ea827-103">Microsoft 365 企業版工作負載和案例</span><span class="sxs-lookup"><span data-stu-id="ea827-103">Microsoft 365 Enterprise workloads and scenarios</span></span>

<span data-ttu-id="ea827-104">若要獲得 Microsoft 365 企業版的創意暨團隊合作優點，請將這些工作負載部署到底層基礎結構上：</span><span class="sxs-lookup"><span data-stu-id="ea827-104">To get the creativity and teamwork benefits of Microsoft 365 Enterprise, deploy these workloads over your foundation infrastructure:</span></span>

- [<span data-ttu-id="ea827-105">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ea827-105">Microsoft Teams</span></span>](teams-workload.md)
- [<span data-ttu-id="ea827-106">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea827-106">Exchange Online</span></span>](exchangeonline-workload.md)
- [<span data-ttu-id="ea827-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ea827-107">SharePoint Online</span></span>](sharepoint-online-onedrive-workload.md)

<span data-ttu-id="ea827-108">請參閱[移轉](migration-microsoft-365-enterprise-workload.md)工作負載，以了解用來將整個組織遷移到 Microsoft 365 企業版的一般藍圖，其內含 Microsoft Office 用戶端產品、內部部署 Office Server 產品和 Microsoft Windows 架構裝置。</span><span class="sxs-lookup"><span data-stu-id="ea827-108">See the [migration](migration-microsoft-365-enterprise-workload.md) workload for a general roadmap to migrate your entire organization to Microsoft 365 Enterprise, which includes Microsoft Office client products, on-premises Office Server products, and Microsoft Windows-based devices.</span></span>

<span data-ttu-id="ea827-109">這些案例會以整合方式使用來自 Microsoft 365 企業版的功能和服務，以因應商務需求。</span><span class="sxs-lookup"><span data-stu-id="ea827-109">Scenarios use features and services from across Microsoft 365 Enterprise in an integrated way to address a business need.</span></span> <span data-ttu-id="ea827-110">其中一個這類需求是保護 Microsoft 365 中所儲存的高管制資料。</span><span class="sxs-lookup"><span data-stu-id="ea827-110">One such need is to protect highly regulated data stored in Microsoft 365.</span></span> <span data-ttu-id="ea827-111">高管制資料包含下列數位資產：</span><span class="sxs-lookup"><span data-stu-id="ea827-111">Highly regulated data includes digital assets that are:</span></span>

- <span data-ttu-id="ea827-112">受限於區域法規。</span><span class="sxs-lookup"><span data-stu-id="ea827-112">Subject to regional regulations.</span></span>
- <span data-ttu-id="ea827-113">貴組織最有價值的資料，例如營業秘密、財務或人力資源資訊，以及組織策略。</span><span class="sxs-lookup"><span data-stu-id="ea827-113">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="ea827-114">若要讓此資料免於遭受內部和外部威脅，請參閱[適用於高管制資料的 Microsoft Teams 和 SharePoint Online 網站](teams-sharepoint-online-sites-highly-regulated-data.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="ea827-114">To protect this data from internal and external threats, see the instructions in [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span> <span data-ttu-id="ea827-115">此案例會逐步引導您完成 SharePoint Online 網站或 Microsoft Teams 小組的設定，以便安全地儲存您最有價值的資料。</span><span class="sxs-lookup"><span data-stu-id="ea827-115">This scenario steps you through configuring a SharePoint Online site or a Microsoft Teams team to securely store your most valuable data.</span></span>

<span data-ttu-id="ea827-116">以下是整體 Microsoft 365 企業版部署指南中的工作負載和案例：</span><span class="sxs-lookup"><span data-stu-id="ea827-116">Here are the workloads and scenarios in the overall Microsoft 365 Enterprise deployment guide:</span></span>

![](./media/deploy-workloads/m365-deploy-content-arch-workloads.png)

## <a name="foundation-infrastructure-prerequisites"></a><span data-ttu-id="ea827-117">底層基礎結構先決條件</span><span class="sxs-lookup"><span data-stu-id="ea827-117">Foundation infrastructure prerequisites</span></span>

<span data-ttu-id="ea827-118">理論上\*\*，您應該在設定好[底層基礎結構](deploy-foundation-infrastructure.md)的所有階段後部署工作負載和案例。</span><span class="sxs-lookup"><span data-stu-id="ea827-118">*Ideally*, you should deploy workloads and scenarios after you have configured all of the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span> <span data-ttu-id="ea827-119">這可確保所有基礎層級都已就緒，而可為使用者及其裝置提供整合、安全性及最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="ea827-119">This ensures that all of the underlying layers are in place to provide integration, security, and the best experience for your users and their devices.</span></span>

| <span data-ttu-id="ea827-120">階段</span><span class="sxs-lookup"><span data-stu-id="ea827-120">Phase</span></span> | <span data-ttu-id="ea827-121">結果</span><span class="sxs-lookup"><span data-stu-id="ea827-121">Result</span></span> |
|:-------|:-----|
| <span data-ttu-id="ea827-122">網路</span><span class="sxs-lookup"><span data-stu-id="ea827-122">Network</span></span> | <span data-ttu-id="ea827-123">網路會進行更新，以獲得最佳的 Microsoft 365 雲端服務效能。</span><span class="sxs-lookup"><span data-stu-id="ea827-123">Your network is updated for optimum performance to Microsoft 365 cloud services.</span></span> |
| <span data-ttu-id="ea827-124">身分識別</span><span class="sxs-lookup"><span data-stu-id="ea827-124">Identity</span></span> | <span data-ttu-id="ea827-125">身分識別會進行同步處理，並讓使用者帳戶使用增強式驗證以及讓系統管理員帳戶使用保護機制來確保身分識別的安全。</span><span class="sxs-lookup"><span data-stu-id="ea827-125">Identity is synchronized and secured with strong authentication for user accounts and protection for admin accounts.</span></span> |
| <span data-ttu-id="ea827-126">Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="ea827-126">Windows 10 Enterprise</span></span> | <span data-ttu-id="ea827-127">執行 Windows 7 或 Windows 8.1 的電腦可升級為 Windows 10 企業版，且新裝置會使用 Windows 10 企業版來進行安裝。</span><span class="sxs-lookup"><span data-stu-id="ea827-127">Your computers running Windows 7 or Windows 8.1 can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
| <span data-ttu-id="ea827-128">Office 365 專業增強版</span><span class="sxs-lookup"><span data-stu-id="ea827-128">Office 365 ProPlus</span></span> | <span data-ttu-id="ea827-129">現有的 Microsoft Office 使用者可升級為 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="ea827-129">Your existing users of Microsoft Office can upgrade to Office 365 ProPlus.</span></span> |
| <span data-ttu-id="ea827-130">行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="ea827-130">Mobile device management</span></span> | <span data-ttu-id="ea827-131">裝置可以進行註冊並受到管理。</span><span class="sxs-lookup"><span data-stu-id="ea827-131">Your devices can be enrolled and managed.</span></span> |
| <span data-ttu-id="ea827-132">資訊保護</span><span class="sxs-lookup"><span data-stu-id="ea827-132">Information protection</span></span> | <span data-ttu-id="ea827-133">會啟用 Office 365 安全性功能，且敏感度標籤或 Azure 資訊保護標籤已準備好而可保護文件。</span><span class="sxs-lookup"><span data-stu-id="ea827-133">Office 365 security features are enabled and your sensitivity or Azure Information Protection labels are ready to protect documents.</span></span> |

<span data-ttu-id="ea827-134">請記住，這是理想狀況，您可能需要花點時間來規劃、設定、測試和試驗，尤其是有既存基礎結構和多個位置的大型組織更是如此。</span><span class="sxs-lookup"><span data-stu-id="ea827-134">Remember that this is ideal and can take some time to plan for, configure, test, and pilot, especially in large organizations with existing infrastructure and multiple locations.</span></span> <span data-ttu-id="ea827-135">您不一定要為了更快速地從 Microsoft 365 企業版獲得商業價值，而在所有位置都備有上述所有層級。</span><span class="sxs-lookup"><span data-stu-id="ea827-135">Putting all of these layers in place in all locations is not necessary for you to more quickly get business value from Microsoft 365 Enterprise.</span></span> 

<span data-ttu-id="ea827-136">以下是一些要立即部署的常見工作負載：</span><span class="sxs-lookup"><span data-stu-id="ea827-136">Here are some common workloads to deploy right away:</span></span> 

- <span data-ttu-id="ea827-137">在對使用者推出底層基礎結構的**身分識別**層級後，許多組織會部署：</span><span class="sxs-lookup"><span data-stu-id="ea827-137">After the **Identity** layer of the foundation infrastructure is rolled out to users, many organizations deploy:</span></span>
  - <span data-ttu-id="ea827-138">[Office 365 專業增強版](office365proplus-infrastructure.md)加上[商務用 OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)。</span><span class="sxs-lookup"><span data-stu-id="ea827-138">[Office 365 ProPlus](office365proplus-infrastructure.md) combined with [OneDrive for Business](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).</span></span> <span data-ttu-id="ea827-139">Office 365 專業增強版可提供新式驗證的安全性和最新 Microsoft Office 用戶端的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="ea827-139">Office 365 ProPlus provides the security of modern authentication and the user experience of the latest Microsoft Office client.</span></span> <span data-ttu-id="ea827-140">將使用者的個人檔案遷移到商務用 OneDrive 會減少基礎結構和對於主資料夾及主目錄磁碟的支援需求。</span><span class="sxs-lookup"><span data-stu-id="ea827-140">The migration of user's personal files to OneDrive for Business reduces infrastructure and the need to support home folders and drives.</span></span>
  - <span data-ttu-id="ea827-141">[Exchange Online](exchangeonline-workload.md)，讓使用者可以開始使用雲端式電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ea827-141">[Exchange Online](exchangeonline-workload.md) so that users can begin using cloud-based email.</span></span>
- <span data-ttu-id="ea827-142">如果您並非立即需要在雲端中儲存高管制的數位資產，請先為使用者部署 [Microsoft Teams](teams-workload.md) 和 [SharePoint Online](sharepoint-online-onedrive-workload.md)，再部署**資訊保護**層級。</span><span class="sxs-lookup"><span data-stu-id="ea827-142">If you don't have an immediate need for storing highly regulated digital assets in the cloud, deploy [Microsoft Teams](teams-workload.md) and [SharePoint Online](sharepoint-online-onedrive-workload.md) for your users prior to the **Information protection** layer.</span></span>

<span data-ttu-id="ea827-143">您必須決定要如何針對底層基礎結構的先決條件階段，做出最佳的設定順序並進行部署，才會最能符合您的業務需求。</span><span class="sxs-lookup"><span data-stu-id="ea827-143">You must decide on how to best order and deploy the configuration of prerequisite phases of foundation infrastructure to best meet your business needs.</span></span>

### <a name="best-practice"></a><span data-ttu-id="ea827-144">最佳作法</span><span class="sxs-lookup"><span data-stu-id="ea827-144">Best practice</span></span>

<span data-ttu-id="ea827-145">強烈建議您先部署和推出底層基礎結構的**身分識別**階段，再讓使用者快速上手工作負載或案例。</span><span class="sxs-lookup"><span data-stu-id="ea827-145">We highly recommend that you deploy and roll out the **Identity** phase of the foundation infrastructure prior to onboarding your users to any workloads or scenarios.</span></span>

<span data-ttu-id="ea827-146">**身分識別**階段可確保雲端式身分識別 (無論是只有雲端，還是會與內部部署 Active Directory Domain Services (AD DS) 同步處理) 會包含可用來管理驗證及存取的使用者和電腦帳戶與群組。</span><span class="sxs-lookup"><span data-stu-id="ea827-146">The **Identity** phase ensures that your cloud-based identity, whether cloud-only or synchronized with your on-premises Active Directory Domain Services (AD DS), contains the user and computer accounts and groups to manage authentication and access.</span></span> <span data-ttu-id="ea827-147">所有使用者都必須使用增強式驗證且系統管理員帳戶必須使用增強式保護，才能將組織的數位資產放入 Microsoft 365 雲端。</span><span class="sxs-lookup"><span data-stu-id="ea827-147">Strong authentication for all your users along with strong protection of admin accounts is required before placing your organization's digital assets in the Microsoft 365 cloud.</span></span>

<span data-ttu-id="ea827-148">雖然整體效能屬於基礎要求且非常重要，但您還是可以在讓使用者快速上手工作負載時同時在網路上推出**網路**階段，因為您知道 Microsoft 365應用程式和服務的效能會慢慢改善。</span><span class="sxs-lookup"><span data-stu-id="ea827-148">Although foundational and very important to overall performance, the rollout of the **Networking** phase on your network can be in progress while onboarding your users to workloads, with the understanding that Microsoft 365 application and service performance will improve over time.</span></span>

<span data-ttu-id="ea827-149">對於有多個位置並混合使用邊緣裝置與網際網路連線的企業組織來說，更是如此。</span><span class="sxs-lookup"><span data-stu-id="ea827-149">This is especially true for enterprise organizations with multiple locations and a mixture of edge devices and Internet connections.</span></span>
