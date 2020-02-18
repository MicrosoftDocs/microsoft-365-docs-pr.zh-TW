---
title: Contoso 的 Windows 10 企業版部署
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft Endpoint Configuration Manager 來部署 Windows 10 企業版的就地升級。
ms.openlocfilehash: 5dc58a9090dd6976d7c521f7552181a10f22f5b2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068002"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a><span data-ttu-id="82d61-103">Contoso 的 Windows 10 企業版部署</span><span class="sxs-lookup"><span data-stu-id="82d61-103">Windows 10 Enterprise deployment for Contoso</span></span>

<span data-ttu-id="82d61-p101">在 Microsoft 365 企業版廣泛發佈之前，Contoso 擁有與 Windows 相容的電腦和裝置，分別執行 Windows 7 (10%)、Windows 8.1 (65%) 和 Windows 10 (25%)。Contoso 想要升級電腦至 Windows 10 企業版，以利用進階安全性及透過自動化部署更新降低 IT 成本。</span><span class="sxs-lookup"><span data-stu-id="82d61-p101">Prior to the wide rollout of Microsoft 365 Enterprise, Contoso had Windows-compatible PCs and devices running a mixture of Windows 7 (10%), Windows 8.1 (65%), and Windows 10 (25%). Contoso wanted to upgrade their PCs for Windows 10 Enterprise take advantage of advanced security and lowered IT overhead from automated deployments of updates.</span></span> 

<span data-ttu-id="82d61-106">在評估基礎架構和業務需求後，Contoso 識別這些部署的關鍵需求：</span><span class="sxs-lookup"><span data-stu-id="82d61-106">After assessing their infrastructure and business needs, Contoso identified these key requirements for the deployment:</span></span>

- <span data-ttu-id="82d61-107">執行 Windows 10 企業版的電腦和裝置越多越好</span><span class="sxs-lookup"><span data-stu-id="82d61-107">As many PCs and devices as possible should run Windows 10 Enterprise</span></span>
- <span data-ttu-id="82d61-108">實施就地升級以利用現有的 Configuration Manager 基礎架構</span><span class="sxs-lookup"><span data-stu-id="82d61-108">Rollout of the in-place upgrades leverages existing Configuration Manager infrastructure</span></span>
- <span data-ttu-id="82d61-109">控制要部署的 Windows 10 企業版版本及週期性的更新</span><span class="sxs-lookup"><span data-stu-id="82d61-109">Control over which versions of Windows 10 Enterprise to deploy and updates are done through rings</span></span>
- <span data-ttu-id="82d61-110">電腦和裝置應在最低 IT 管理成本與對使用者影響最低的情況下，保持最新狀態</span><span class="sxs-lookup"><span data-stu-id="82d61-110">PCs and devices should stay up to date with minimal IT administrative costs and with minimal impact to end-users</span></span>

<span data-ttu-id="82d61-111">最新的定義是指符合 Contoso 業務需求的受支援 Windows 10 企業版，並非指所有 Windows 相容的電腦皆執行 Windows 10 企業版最新版本。</span><span class="sxs-lookup"><span data-stu-id="82d61-111">Up to date is defined as the supported version of Windows 10 Enterprise that meets Contoso’s business needs, which can be different from having all Windows-compatible PCs running the latest version of Windows 10 Enterprise.</span></span>

## <a name="deployment-tools"></a><span data-ttu-id="82d61-112">部署工具</span><span class="sxs-lookup"><span data-stu-id="82d61-112">Deployment tools</span></span>

<span data-ttu-id="82d61-113">在 Windows 10 企業版就地升級之前和期間，Contoso 使用以下 Windows Analytics 解決方案：</span><span class="sxs-lookup"><span data-stu-id="82d61-113">Prior to and during in-place upgrades of Windows 10 Enterprise, Contoso used the following solutions of Windows Analytics:</span></span>

- <span data-ttu-id="82d61-114">升級整備狀況</span><span class="sxs-lookup"><span data-stu-id="82d61-114">Upgrade Readiness</span></span>  

  <span data-ttu-id="82d61-115">收集系統、應用程式及驅動程式資料以供分析，然後識別可能會阻擋升級的相容性問題與 Microsoft 已知問題的建議修正。</span><span class="sxs-lookup"><span data-stu-id="82d61-115">Collects system, application, and driver data for analysis, and then identifies compatibility issues that can block an upgrade and suggested fixes the issues are known to Microsoft.</span></span>

- <span data-ttu-id="82d61-116">升級相容性</span><span class="sxs-lookup"><span data-stu-id="82d61-116">Update Compliance</span></span>  

  <span data-ttu-id="82d61-117">針對 Windows 更新顯示裝置的狀態，讓您能視需要確保這些裝置處於最新更新狀態。</span><span class="sxs-lookup"><span data-stu-id="82d61-117">Shows you the state of your devices with respect to the Windows updates so that you can ensure that they are on the most current updates as appropriate.</span></span>

- <span data-ttu-id="82d61-118">裝置健全狀況</span><span class="sxs-lookup"><span data-stu-id="82d61-118">Device Health</span></span>  

  <span data-ttu-id="82d61-119">識別經常當機，因此可能需要重建或更換的裝置，以及導致裝置當機的裝置驅動程式，並建議能減少當機次數的驅動程式替代版本。</span><span class="sxs-lookup"><span data-stu-id="82d61-119">Identifies devices that crash frequently, and therefore might need to be rebuilt or replaced and device drivers that are causing device crashes, with suggestions of alternative versions of those drivers that might reduce the number of crashes.</span></span> <span data-ttu-id="82d61-120">提供 Windows 資訊保護設定錯誤的通知，並傳送提示給使用者。</span><span class="sxs-lookup"><span data-stu-id="82d61-120">Provides notification of Windows Information Protection misconfigurations that send prompts to end users.</span></span>
 
<span data-ttu-id="82d61-p103">Contoso 已擁有 Configuration Manager (最新分支) 基礎架構。Configuration Manager 可針對大型環境進行調整並提供安裝、更新及設定的全面控制，其內建功能更讓您可輕鬆且有效率地部署及管理 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="82d61-p103">Contoso has an existing Configuration Manager (Current Branch) infrastructure. Configuration Manager scales for large environments and provides extensive control over installation, updates, and settings. It also has built-in features to make it easier and more efficient to deploy and manage Windows 10 Enterprise.</span></span>

## <a name="planning-process"></a><span data-ttu-id="82d61-124">規劃程序</span><span class="sxs-lookup"><span data-stu-id="82d61-124">Planning process</span></span>

<span data-ttu-id="82d61-125">在部署之前，Contoso 定義了以下週期：</span><span class="sxs-lookup"><span data-stu-id="82d61-125">Prior to deployment, Contoso defined the following rings:</span></span>

- <span data-ttu-id="82d61-126">三個驗證及部署階段週期</span><span class="sxs-lookup"><span data-stu-id="82d61-126">Three rings for validation and deployment staging</span></span> 
  - <span data-ttu-id="82d61-127">一個預覽組建週期</span><span class="sxs-lookup"><span data-stu-id="82d61-127">One for preview builds</span></span> 
  - <span data-ttu-id="82d61-128">一個全新發行週期</span><span class="sxs-lookup"><span data-stu-id="82d61-128">One for new release builds</span></span>
  - <span data-ttu-id="82d61-129">一個先前組建週期</span><span class="sxs-lookup"><span data-stu-id="82d61-129">One for a previous build</span></span> 
- <span data-ttu-id="82d61-130">一個根據驗證週期資料的廣泛部署 Windows 10 企業版週期</span><span class="sxs-lookup"><span data-stu-id="82d61-130">One ring for broad deployment of Windows 10 Enterprise based on data from the validation rings</span></span>

<span data-ttu-id="82d61-131">Contoso 同時也使用 Windows Analytics 的「升級整備狀況」解決方案，判斷已安裝應用程式與 Windows 10 企業版的相容性。</span><span class="sxs-lookup"><span data-stu-id="82d61-131">Contoso also used the Upgrade Readiness solution of Windows Analytics to determine the set of installed apps and their compatibility with Windows 10 Enterprise.</span></span>

## <a name="deployment-process"></a><span data-ttu-id="82d61-132">部署程序</span><span class="sxs-lookup"><span data-stu-id="82d61-132">Deployment process</span></span>

<span data-ttu-id="82d61-133">為了完成 Windows 10 企業版的就地升級部署，Contoso 實施了以下程序，包含 Microsoft 的最佳實務建議：</span><span class="sxs-lookup"><span data-stu-id="82d61-133">To complete the in-place upgrade deployment of Windows 10 Enterprise, Contoso implemented the following process, which includes best practice recommendations from Microsoft:</span></span>

1. <span data-ttu-id="82d61-134">為 Configuration Manager 啟用對等快取。</span><span class="sxs-lookup"><span data-stu-id="82d61-134">Enabled peer cache for Configuration Manager.</span></span>
2. <span data-ttu-id="82d61-135">根據大量授權服務中心建立自訂 Windows 套件。</span><span class="sxs-lookup"><span data-stu-id="82d61-135">Created customized Windows packages based on images from the Volume Licensing Service Center.</span></span>
3. <span data-ttu-id="82d61-136">使用 Configuration Manager 部署 Windows 套件以在內部網路發佈點，並將組建部署至三個驗證和部署執行週期。</span><span class="sxs-lookup"><span data-stu-id="82d61-136">Used Configuration Manager to deploy the Windows packages to distribution points across their network and deployed builds to the three validation and deployment staging rings.</span></span>
4. <span data-ttu-id="82d61-137">使用 Windows Analytics 的「裝置健全狀況」和「升級相容性」解決方案，對在三個驗證和部署執行週期中的電腦和裝置執行成功評估。</span><span class="sxs-lookup"><span data-stu-id="82d61-137">Performed assessment of success for PCs and devices in the three validation and deployment staging rings using the Device Health and Update Compliance solutions of Windows Analytics.</span></span>
5. <span data-ttu-id="82d61-138">Contoso 根據 Windows Analytics 資訊，判斷要部署至廣泛部署週期的 Windows 10 企業版版本。</span><span class="sxs-lookup"><span data-stu-id="82d61-138">Based on the Windows Analytics information, Contoso determined the version of Windows 10 Enterprise to deploy to the broad deployment ring.</span></span>
6. <span data-ttu-id="82d61-139">執行 Configuration Manager 的部署工作順序，將指定的 Windows 套件部署至廣泛部署週期。</span><span class="sxs-lookup"><span data-stu-id="82d61-139">Ran the Configuration Manager deployment task sequences to deploy the selected Windows package to the broad deployment ring.</span></span>
7. <span data-ttu-id="82d61-140">使用「裝置健康情況」和「更新合規性」解決方案，監控在廣泛部署週期中的電腦和裝置，以解決問題。</span><span class="sxs-lookup"><span data-stu-id="82d61-140">Monitored PCs and devices in the broad deployment ring using the Device Health and Update Compliance solutions to address issues.</span></span>

<span data-ttu-id="82d61-141">這是 Contoso 就地升級和持續更新部署的基礎架構。</span><span class="sxs-lookup"><span data-stu-id="82d61-141">Here is Contoso’s in-place upgrade and ongoing updates deployment architecture.</span></span>

![Contoso 的 Windows 10 企業版部署基礎架構](../media/contoso-win10/contoso-win10-fig1.png)

<span data-ttu-id="82d61-143">此基礎架構的組成為：</span><span class="sxs-lookup"><span data-stu-id="82d61-143">This infrastructure consists of:</span></span>

- <span data-ttu-id="82d61-144">Configuration Manager，其：</span><span class="sxs-lookup"><span data-stu-id="82d61-144">Configuration Manager, which:</span></span>
  - <span data-ttu-id="82d61-145">從 Microsoft 網路中的 Microsoft 大量授權取得取得 Windows 10 企業版套件的映像。</span><span class="sxs-lookup"><span data-stu-id="82d61-145">Obtains images for Windows 10 Enterprise packages from the Microsoft Volume Licensing Center in the Microsoft Network.</span></span>
  - <span data-ttu-id="82d61-146">部署套件的管理中心點。</span><span class="sxs-lookup"><span data-stu-id="82d61-146">Is the central administration point for deployment packages.</span></span>
- <span data-ttu-id="82d61-147">通常位於 Contoso 地區中心辦公室的地區發布點。</span><span class="sxs-lookup"><span data-stu-id="82d61-147">Regional distribution points that are typically located in Contoso’s regional hub offices.</span></span>
- <span data-ttu-id="82d61-148">在不同地點的 Windows 電腦和裝置會根據週期成員資格，收到並安裝就地升級部署或持續更新套件。</span><span class="sxs-lookup"><span data-stu-id="82d61-148">Windows PCs and devices in various locations that receive and install the deployment packages for the in-place upgrade or ongoing updates based on ring membership.</span></span>

## <a name="next-step"></a><span data-ttu-id="82d61-149">下一步</span><span class="sxs-lookup"><span data-stu-id="82d61-149">Next step</span></span>

<span data-ttu-id="82d61-150">[了解](contoso-o365pp.md) Contoso 如何使用 Configuration Manager 基礎結構，在整個組織部署及保留目前的 Office 365 專業增強版。</span><span class="sxs-lookup"><span data-stu-id="82d61-150">[Learn](contoso-o365pp.md) how Contoso is leveraging its Configuration Manager infrastructure to deploy and keep current Office 365 ProPlus across its organization.</span></span> 

## <a name="see-also"></a><span data-ttu-id="82d61-151">另請參閱</span><span class="sxs-lookup"><span data-stu-id="82d61-151">See also</span></span>

[<span data-ttu-id="82d61-152">Microsoft 365 企業版的 Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="82d61-152">Windows 10 Enterprise for Microsoft 365 Enterprise</span></span>](windows10-infrastructure.md)

[<span data-ttu-id="82d61-153">部署指南</span><span class="sxs-lookup"><span data-stu-id="82d61-153">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="82d61-154">測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="82d61-154">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
