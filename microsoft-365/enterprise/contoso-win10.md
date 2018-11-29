---
title: Contoso 的 Windows 10 企業版部署
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 深入了解 Contoso 如何使用 System Center Configuration Manager 來部署 Windows 10 企業版的就地升級。
ms.openlocfilehash: a4b24d55951c83875b9aa08db05fa4f8591472d6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866456"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="5b6a8-103">Contoso 的 Windows 10 企業版部署</span><span class="sxs-lookup"><span data-stu-id="5b6a8-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="5b6a8-104">**摘要：** 深入了解 Contoso 如何使用 System Center Configuration Manager 來部署 Windows 10 企業版的就地升級。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-104">**Summary:** Understand how Contoso used System Center Configuration Manager to deploy in-place upgrades for Windows 10 Enterprise.</span></span>

<span data-ttu-id="5b6a8-p101">在 Microsoft 365 企業版廣泛發佈之前，Contoso 擁有與 Windows 相容的電腦和裝置，分別執行 Windows 7 (10%)、Windows 8.1 (65%) 和 Windows 10 (25%)。Contoso 想要升級電腦至 Windows 10 企業版，好利用增強的安全性並透過自動化部署更新降低 IT 成本。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-p101">Prior to the wide rollout of Microsoft 365 Enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of improved security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="5b6a8-107">在評估基礎架構和業務需求後，Contoso 識別這些部署的關鍵需求：</span><span class="sxs-lookup"><span data-stu-id="5b6a8-107">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="5b6a8-108">執行 Windows 10 企業版的電腦和裝置越多越好</span><span class="sxs-lookup"><span data-stu-id="5b6a8-108">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="5b6a8-109">實施就地升級以利用現有的 System Center Configuration Manager 基礎架構</span><span class="sxs-lookup"><span data-stu-id="5b6a8-109">Rollout of the in-place upgrades leverages existing System Center Configuration Manager infrastructure</span></span>
- <span data-ttu-id="5b6a8-110">控制要部署的 Windows 10 企業版版本及週期性的更新</span><span class="sxs-lookup"><span data-stu-id="5b6a8-110">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="5b6a8-111">電腦和裝置應在最低 IT 管理成本與對使用者影響最低的情況下，保持最新狀態</span><span class="sxs-lookup"><span data-stu-id="5b6a8-111">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="5b6a8-112">最新的定義是指符合 Contoso 業務需求的受支援 Windows 10 企業版，並非指所有 Windows 相容的電腦皆執行 Windows 10 企業版最新版本。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-112">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="5b6a8-113">部署工具</span><span class="sxs-lookup"><span data-stu-id="5b6a8-113">Deployment tools</span></span>

<span data-ttu-id="5b6a8-114">在 Windows 10 企業版就地升級之前和期間，Contoso 使用以下 Windows Analytics 解決方案：</span><span class="sxs-lookup"><span data-stu-id="5b6a8-114">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="5b6a8-115">升級整備狀況</span><span class="sxs-lookup"><span data-stu-id="5b6a8-115">Upgrade Readiness</span></span>  

  <span data-ttu-id="5b6a8-116">收集系統、應用程式及驅動程式資料以供分析，然後識別可能會阻擋升級的相容性問題與 Microsoft 已知問題的建議修正。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-116">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="5b6a8-117">升級相容性</span><span class="sxs-lookup"><span data-stu-id="5b6a8-117">Update Compliance</span></span>  

  <span data-ttu-id="5b6a8-118">收集系統和診斷資料，包含升級安裝進度、商務用 Windows Update (WUfB) 配置資料、Windows Defender 防毒軟體資料，以及其他升級相關資訊，並將這些資料儲存在雲端分析與使用情況。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-118">Collects system and diagnostics data including update installation progress, Windows Update for Business (WUfB) configuration data, Windows Defender Antivirus data, and other update-specific information, and then stores this data in the cloud analysis and usage.</span></span>

- <span data-ttu-id="5b6a8-119">裝置健全狀況</span><span class="sxs-lookup"><span data-stu-id="5b6a8-119">Device Health</span></span>  

  <span data-ttu-id="5b6a8-120">收集 Windows 10 系統和診斷資料，包含升級安裝進度、商務用 Windows Update (WUfB) 配置資料、Windows Defender 防毒軟體資料，以及其他升級相關資訊，並將這些資料儲存在雲端分析與使用情況。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-120">Collects Windows 10 system and diagnostic data including update installation progress, Windows Update for Business (WUfB) configuration data, Windows Defender Antivirus data, and other update-specific information, and then stores this data in the cloud analysis and usage.</span></span>
 
<span data-ttu-id="5b6a8-p102">Contoso 已擁有 Configuration Manager (最新分支) 基礎架構。Configuration Manager 可針對大型環境進行調整並提供安裝、更新及設定的全面控制，其內建功能更讓您可輕鬆且有效率地部署及管理 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-p102">Contoso has an existing System Center Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="5b6a8-124">規劃程序</span><span class="sxs-lookup"><span data-stu-id="5b6a8-124">Planning process</span></span>

<span data-ttu-id="5b6a8-125">在部署之前，Contoso 定義了以下週期：</span><span class="sxs-lookup"><span data-stu-id="5b6a8-125">Prior to deployment, Contoso defined the following rings:</span></span>

- <span data-ttu-id="5b6a8-126">三個驗證及部署階段週期</span><span class="sxs-lookup"><span data-stu-id="5b6a8-126">Three rings for validation and deployment staging</span></span> 
  - <span data-ttu-id="5b6a8-127">一個預覽組建週期</span><span class="sxs-lookup"><span data-stu-id="5b6a8-127">One for preview builds</span></span> 
  - <span data-ttu-id="5b6a8-128">一個全新發行週期</span><span class="sxs-lookup"><span data-stu-id="5b6a8-128">One for new release builds</span></span>
  - <span data-ttu-id="5b6a8-129">一個先前組建週期</span><span class="sxs-lookup"><span data-stu-id="5b6a8-129">One for a previous build</span></span> 
- <span data-ttu-id="5b6a8-130">一個根據驗證週期資料的廣泛部署 Windows 10 企業版週期</span><span class="sxs-lookup"><span data-stu-id="5b6a8-130">One ring for broad deployment of Windows 10 Enterprise based on data from the validation rings</span></span>

<span data-ttu-id="5b6a8-131">Contoso 同時也使用 Windows Analytics 的「升級整備狀況」解決方案，判斷已安裝應用程式與 Windows 10 企業版的相容性。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-131">Contoso also used the Upgrade Readiness solution of Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="5b6a8-132">部署程序</span><span class="sxs-lookup"><span data-stu-id="5b6a8-132">Deployment process</span></span>

<span data-ttu-id="5b6a8-133">為了完成 Windows 10 企業版的就地升級部署，Contoso 實施了以下程序，包含 Microsoft 的最佳實務建議：</span><span class="sxs-lookup"><span data-stu-id="5b6a8-133">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="5b6a8-134">為 Configuration Manager 啟用對等快取。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-134">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="5b6a8-135">根據大量授權服務中心建立自訂 Windows 套件。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-135">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="5b6a8-136">使用 Configuration Manager 部署 Windows 套件以在內部網路發佈點，並將組建部署至三個驗證和部署執行週期。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-136">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging rings.</span></span>
4. <span data-ttu-id="5b6a8-137">使用 Windows Analytics 的「裝置健全狀況」和「升級相容性」解決方案，對在三個驗證和部署執行週期中的電腦和裝置執行成功評估。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-137">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="5b6a8-138">Contoso 根據 Windows Analytics 資訊，判斷要部署至廣泛部署週期的 Windows 10 企業版版本。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-138">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment ring.</span></span>
6. <span data-ttu-id="5b6a8-139">執行 Configuration Manager 的部署工作順序，將指定的 Windows 套件部署至廣泛部署週期。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-139">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment ring.</span></span>
7. <span data-ttu-id="5b6a8-140">使用 Windows Analytics 的「裝置健全狀況」和「升級相容性」解決方案，監控在廣泛部署週期中的電腦和裝置及解決問題。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-140">Monitored PCs and devices in the broad deployment ring using the Device Health and Update Compliance solutions provided by Windows Analytics to address issues.</span></span>

<span data-ttu-id="5b6a8-141">圖 1 顯示就地升級和持續更新部署的基礎架構。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-141">Figure 1 shows the in-place upgrade and ongoing updates deployment architecture.</span></span>

![](./media/contoso-win10/contoso-win10-fig1.png)
 
<span data-ttu-id="5b6a8-142">**圖 1：Contoso 的 Windows 10 企業版部署基礎架構**</span><span class="sxs-lookup"><span data-stu-id="5b6a8-142">**Figure 1: Contoso’s Windows 10 Enterprise deployment infrastructure**</span></span>

<span data-ttu-id="5b6a8-143">此基礎架構的組成為：</span><span class="sxs-lookup"><span data-stu-id="5b6a8-143">This infrastructure consists of:</span></span>

- <span data-ttu-id="5b6a8-144">System Center Configuration Manager，功用是：</span><span class="sxs-lookup"><span data-stu-id="5b6a8-144">System Center Configuration Manager, which:</span></span>
  - <span data-ttu-id="5b6a8-145">從 Microsoft 網路中的 Microsoft 大量授權取得取得 Windows 10 企業版套件的映像。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-145">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="5b6a8-146">部署套件的管理中心點。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-146">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="5b6a8-147">通常位於 Contoso 衛星辦公室的地區發布點。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-147">Regional distribution points that are typically located in Contoso’s satellite offices.</span></span>
- <span data-ttu-id="5b6a8-148">在不同地點的 Windows 電腦和裝置會根據週期成員資格，收到並安裝就地升級部署或持續更新套件。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-148">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on ring membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="5b6a8-149">下一步</span><span class="sxs-lookup"><span data-stu-id="5b6a8-149">Next step</span></span>

<span data-ttu-id="5b6a8-150">[深入了解](contoso-o365pp.md) Contoso 如何使用 System Center Configuration Manager 基礎結構，在整個組織部署及保持目前的 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="5b6a8-150">[Learn](contoso-o365pp.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Office 365 ProPlus across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="5b6a8-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5b6a8-151">See also</span></span>

[<span data-ttu-id="5b6a8-152">Microsoft 365 企業版的 Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="5b6a8-152">Windows 10 Enterprise for Microsoft 365 Enterprise</span></span>](windows10-infrastructure.md)

[<span data-ttu-id="5b6a8-153">部署指南</span><span class="sxs-lookup"><span data-stu-id="5b6a8-153">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="5b6a8-154">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="5b6a8-154">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
