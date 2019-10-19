---
title: Microsoft 365 企業版的 Windows 10 企業版基礎結構
description: 針對 Microsoft 365 企業版的一部分部署在電腦上的 Windows 10 企業版所需的步驟提供高階指導。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 文件、 Windows 10 企業版部署
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/28/2019
ms.author: greglin
ms.openlocfilehash: 7253ea698613a38988bd7a6942a4908e9c797e2a
ms.sourcegitcommit: 0d423b50d2f1f4eccd64e35e00f67313244efba9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2019
ms.locfileid: "37372764"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="48c73-104">階段 3：Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="48c73-104">Phase 3: Windows 10 Enterprise</span></span>

![階段 3：Windows 10 企業版](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="48c73-106">Microsoft 365 企業版包含 Windows 10 企業版，可讓您進行更多作業及保持安全的工具。</span><span class="sxs-lookup"><span data-stu-id="48c73-106">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure.</span></span> <span data-ttu-id="48c73-107">Windows 10 企業版：</span><span class="sxs-lookup"><span data-stu-id="48c73-107">Windows 10 Enterprise:</span></span>

- <span data-ttu-id="48c73-108">**為了簡單起見整合**-控管的 cloud 電源，若要協助減少管理今天的複雜性的現代 IT 裝置環境中的，不論大小。</span><span class="sxs-lookup"><span data-stu-id="48c73-108">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="48c73-109">**提供智慧安全性**-曾經是最安全的 Windows 版本，請使用智慧安全性功能專為合作更妥善地保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="48c73-109">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="48c73-110">**可讓發揮創意並實現團隊合作**-解除鎖定發揮創意並實現團隊合作來傳遞最生產力體驗的使用者和 IT 會告訴。</span><span class="sxs-lookup"><span data-stu-id="48c73-110">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="48c73-111">您需要了解您可以部署 Windows 10 的作業系統，並選擇適合貴組織的不同方式。</span><span class="sxs-lookup"><span data-stu-id="48c73-111">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization.</span></span> <span data-ttu-id="48c73-112">根據您的 Microsoft 365 企業版訂閱，也有 Windows 10 服務與安全性功能，您必須設定成充分 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="48c73-112">Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

>[!Note]
><span data-ttu-id="48c73-113">若要同時部署 Windows 10 企業版和 Office 365 專業增強版，並且改為使用[現代化電腦](https://www.microsoft.com/microsoft-365/modern-desktop)，請參閱[現代化電腦的部署中心](http://aka.ms/howtoshift)。</span><span class="sxs-lookup"><span data-stu-id="48c73-113">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](http://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="48c73-114">Windows 10 部署</span><span class="sxs-lookup"><span data-stu-id="48c73-114">Windows 10 deployment</span></span>

<span data-ttu-id="48c73-115">有多種方法可以為貴組織中部署 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="48c73-115">There are multiple ways you can deploy Windows 10 Enterprise for your organization.</span></span> <span data-ttu-id="48c73-116">在這裡，我們將著重於如何設定及部署 Windows 10 企業版映像，透過這些現代化的部署案例。</span><span class="sxs-lookup"><span data-stu-id="48c73-116">Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="48c73-117">部署案例</span><span class="sxs-lookup"><span data-stu-id="48c73-117">Deployment scenario</span></span> | <span data-ttu-id="48c73-118">使用時機</span><span class="sxs-lookup"><span data-stu-id="48c73-118">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="48c73-119">使用 System Center Configuration Manager 以進行就地升級</span><span class="sxs-lookup"><span data-stu-id="48c73-119">Using System Center Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="48c73-120">如果您要升級 Windows 7 或<a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager （最新分支）</a>目前管理 Windows 10 企業版的<a href="https://aka.ms/windows-10-release-information" target="_blank">目前版本</a>的 Windows 8.1 電腦與您的電腦，請選取這個選項。</span><span class="sxs-lookup"><span data-stu-id="48c73-120">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="48c73-121">使用 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="48c73-121">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="48c73-122">如果您正在設定新有 Windows 10 企業版，版本 1703年或更新版本預先安裝的 Windows 電腦，請選取這個選項。</span><span class="sxs-lookup"><span data-stu-id="48c73-122">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed.</span></span> <span data-ttu-id="48c73-123">使用者將會啟動安裝程式使用您所需的設定，藉由輸入他們的公司或學校帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="48c73-123">End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="48c73-124">如果這些部署案例不符合您組織的需求，您可以了解其他案例，並了解的功能和每個在[Windows 10 部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)中的限制。</span><span class="sxs-lookup"><span data-stu-id="48c73-124">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="48c73-125">您也可以自行<a href="https://aka.ms/planforwin10deployment" target="_blank">規劃 Windows 10 部署</a>。</span><span class="sxs-lookup"><span data-stu-id="48c73-125">You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="48c73-126">您可以深入了解 Windows 10 使用以下文章：</span><span class="sxs-lookup"><span data-stu-id="48c73-126">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="48c73-127">Microsoft 365 Enterprise 產品頁面</span><span class="sxs-lookup"><span data-stu-id="48c73-127">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="48c73-128">Windows 10</span><span class="sxs-lookup"><span data-stu-id="48c73-128">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="48c73-129">部署及更新 Windows 10</span><span class="sxs-lookup"><span data-stu-id="48c73-129">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="48c73-130">其他服務與功能</span><span class="sxs-lookup"><span data-stu-id="48c73-130">Additional services and features</span></span>
<span data-ttu-id="48c73-131">Windows 10 企業版部署的一部分，您可以新增這些額外的服務和功能。</span><span class="sxs-lookup"><span data-stu-id="48c73-131">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="48c73-132">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="48c73-132">Windows Analytics</span></span>

<span data-ttu-id="48c73-133">Windows 用來提供豐富、 可採取動作的資訊可協助您深入了解深層作業效率和您環境中的 Windows 10 裝置的健康狀況情形診斷資料。</span><span class="sxs-lookup"><span data-stu-id="48c73-133">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="48c73-134">升級整備-升級整備可協助您移動到 Windows 10，並保持最新的 Windows 10 功能更新。</span><span class="sxs-lookup"><span data-stu-id="48c73-134">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="48c73-135">升級相容性-升級相容性為目標的 IT 系統管理員想要取得所有 Windows 10 裝置，沒有任何其他基礎結構需求的全方位檢視。</span><span class="sxs-lookup"><span data-stu-id="48c73-135">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="48c73-136">裝置健全狀況-您可以使用裝置健全狀況主動偵測及修復使用者影響問題。</span><span class="sxs-lookup"><span data-stu-id="48c73-136">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="48c73-137">如需詳細資訊，請參閱[Windows Analytics 概觀](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview)。</span><span class="sxs-lookup"><span data-stu-id="48c73-137">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="48c73-138">Windows 安全性</span><span class="sxs-lookup"><span data-stu-id="48c73-138">Windows security</span></span>

<span data-ttu-id="48c73-139">Windows 10 提供功能，協助防範威脅，協助保護您的裝置，並協助使用存取控制。</span><span class="sxs-lookup"><span data-stu-id="48c73-139">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> <span data-ttu-id="48c73-140">與 Windows 10 中，您可以取得重要的安全性功能，以保護您的裝置權限從開始。</span><span class="sxs-lookup"><span data-stu-id="48c73-140">With Windows 10, you get critical security features that protect your device right from the start.</span></span> <span data-ttu-id="48c73-141">Microsoft 365 E3，新增安全性功能，例如 Windows Hello 企業、 Windows Defender 應用程式控制和 Windows 資訊保護。</span><span class="sxs-lookup"><span data-stu-id="48c73-141">Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection.</span></span> <span data-ttu-id="48c73-142">使用 Microsoft 365 E5，您要從 Microsoft 365 E3 安全性加上雲端為基礎的安全性功能和 Microsoft Defender 進階威脅防護取得所有的保護。</span><span class="sxs-lookup"><span data-stu-id="48c73-142">With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Microsoft Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="48c73-143">若要深入了解您取得 Windows 10 企業版和取得指導方針如何部署、 管理、 設定及疑難排解三個主要的安全性功能的安全性功能，請參閱[步驟 5： 部署 Windows 10 企業版安全性功能](windows10-enable-security-features.md)。</span><span class="sxs-lookup"><span data-stu-id="48c73-143">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="48c73-144">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="48c73-144">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="48c73-145">一窺 Microsoft 並了解如何公司[部署 Windows 10 企業版，且正在使用 Intune，且 Microsoft Defender ATP 的強式驗證](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR6)。</span><span class="sxs-lookup"><span data-stu-id="48c73-145">Peek inside Microsoft and learn how the company [deployed Windows 10 Enterprise and is using strong authentication, Intune, and Microsoft Defender ATP](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR6).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="48c73-146">Contoso 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="48c73-146">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="48c73-147">請參閱如何 Contoso Corporation、 虛構但有代表性的跨國企業、[部署 Windows 10 企業版](contoso-win10.md)。</span><span class="sxs-lookup"><span data-stu-id="48c73-147">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![Contoso 公司](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="48c73-149">下一步</span><span class="sxs-lookup"><span data-stu-id="48c73-149">Next step</span></span>

|||
|:-------|:-----|
|![步驟 1](./media/stepnumbers/Step1.png)| [<span data-ttu-id="48c73-151">準備您的組織，Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="48c73-151">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
