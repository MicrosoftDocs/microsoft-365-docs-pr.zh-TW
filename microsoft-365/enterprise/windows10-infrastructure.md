---
title: Microsoft 365 企業版的 Windows 10 企業基礎結構
description: 提供高階指導您部署的 Pc 上的 Windows 10 Enterprise 做為 Microsoft 365 企業版的一部分所需的步驟。
keywords: Microsoft 365、 Microsoft 365 企業版、 Microsoft 365 文件、 Windows 10 企業部署
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 80d7c1b56434647387b9c428ca07effdff929abf
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866123"
---
# <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="db1e3-104">階段 3：Windows 10 企業版</span><span class="sxs-lookup"><span data-stu-id="db1e3-104">Phase 3: Windows 10 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

<span data-ttu-id="db1e3-p101">Microsoft 365 企業版包含 Windows 10 企業可讓您執行多並保持在最安全的工具。Windows 10 Enterprise：</span><span class="sxs-lookup"><span data-stu-id="db1e3-p101">Microsoft 365 Enterprise includes Windows 10 Enterprise, which gives you the tools to do more and stay secure. Windows 10 Enterprise:</span></span>

- <span data-ttu-id="db1e3-107">**簡化了程序已整合**-控管的雲端強大功能來協助減少管理今天的複雜性的現代 IT 裝置環境中的，不論大小。</span><span class="sxs-lookup"><span data-stu-id="db1e3-107">**Is integrated for simplicity** - Harness the power of the cloud to help reduce the complexity of managing today's modern IT device environment, no matter the size.</span></span>
- <span data-ttu-id="db1e3-108">**具有智慧型安全性**-曾經是最安全版本的 Windows、 具有智慧型安全性設計用來共同運作來改善的功能會保護您的組織。</span><span class="sxs-lookup"><span data-stu-id="db1e3-108">**Has intelligent security** - It's the most secure release of Windows ever, with intelligent security capabilities that are designed to work together to better protect your organization.</span></span>
- <span data-ttu-id="db1e3-109">**讓創造力與團隊合作**-解除鎖定創造力並傳遞以最有效率的團隊合作體驗的使用者和 IT 會愛。</span><span class="sxs-lookup"><span data-stu-id="db1e3-109">**Enables creativity and teamwork** - Unlocks creativity and teamwork to deliver the most productive experience that both users and IT will love.</span></span>

<span data-ttu-id="db1e3-p102">您需要了解您可以部署 Windows 10 作業系統及選擇您的組織右邊一種不同方式。根據您的 Microsoft 365 企業版訂閱，也有 Windows 10 服務與您需要設定成 Windows 10 發揮最大的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="db1e3-p102">You'll need to understand the different ways you can deploy the Windows 10 operating system and choose the right one for your organization. Depending on your Microsoft 365 Enterprise subscription, there are also Windows 10 services and security features that you'll need to configure to get the most out of Windows 10.</span></span>

<span data-ttu-id="db1e3-112">Windows 10 Microsoft 365 enterprise 讓這些策略性商務案例：</span><span class="sxs-lookup"><span data-stu-id="db1e3-112">Windows 10 enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="db1e3-113">運用集體知識和專業技能，讓組織中的使用者可探索、共用及改善檔案、資訊和想法</span><span class="sxs-lookup"><span data-stu-id="db1e3-113">Harness collective knowledge and expertise by empowering people to discover, share, and progress files, information, and ideas across your organization</span></span>
- <span data-ttu-id="db1e3-114">隨時隨地在裝置上安全地工作，以達成更多目標，同時維持彈性的工作方式</span><span class="sxs-lookup"><span data-stu-id="db1e3-114">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="db1e3-115">通過產業驗證符合合規性的全球標準，提供控制和可見度讓您安心</span><span class="sxs-lookup"><span data-stu-id="db1e3-115">Provide peace-of-mind with controls and visibility for industry-verified conformity with global standards in compliance</span></span>
- <span data-ttu-id="db1e3-116">保護您的資訊，並降低資料遺失風險</span><span class="sxs-lookup"><span data-stu-id="db1e3-116">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="db1e3-117">偵測及防範外部威脅-監視、 報告及分析活動回應立即提供組織的安全性</span><span class="sxs-lookup"><span data-stu-id="db1e3-117">Detect and protect against external threats --Monitor, report and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="db1e3-118">保護您的使用者和其帳戶</span><span class="sxs-lookup"><span data-stu-id="db1e3-118">Protect your users and their accounts</span></span>
- <span data-ttu-id="db1e3-119">使用增強的隱私權和法規遵循來支援貴組織，以符合一般資料保護規定 (GDPR)</span><span class="sxs-lookup"><span data-stu-id="db1e3-119">Support your organization with enhanced privacy and compliance to meet the General Data Protection Regulation (GDPR)</span></span>
- <span data-ttu-id="db1e3-120">為桌面軟體與裝置取得並保持在目前最新狀態，同時降低安全性風險並將 IT 部門的效率最大化</span><span class="sxs-lookup"><span data-stu-id="db1e3-120">Get current and stay current on your desktop software and devices while reducing security risks and maximizing IT efficiency</span></span>

<span data-ttu-id="db1e3-121">如需詳細資訊，請參閱[使用 Microsoft 365 進行數位轉換](http://transform.microsoft.com) (英文)。</span><span class="sxs-lookup"><span data-stu-id="db1e3-121">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

>[!Note]
><span data-ttu-id="db1e3-122">若要同時部署 Windows 10 企業版和 Office 365 專業增強版，並且改為使用[現代化電腦](https://www.microsoft.com/microsoft-365/modern-desktop)，請參閱[現代化電腦的部署中心](http://aka.ms/howtoshift)。</span><span class="sxs-lookup"><span data-stu-id="db1e3-122">To deploy both Windows 10 Enterprise and Office 365 ProPlus together and shift to a [modern desktop](https://www.microsoft.com/microsoft-365/modern-desktop), see the [Modern Desktop Deployment Center](http://aka.ms/howtoshift).</span></span>
>

## <a name="windows-10-deployment"></a><span data-ttu-id="db1e3-123">Windows 10 部署</span><span class="sxs-lookup"><span data-stu-id="db1e3-123">Windows 10 deployment</span></span>

<span data-ttu-id="db1e3-p103">有多個方法可以為組織中部署 Windows 10 Enterprise。以下，我們會將焦點如何設定及部署這些摩登的部署案例透過 Windows 10 Enterprise 映像上。</span><span class="sxs-lookup"><span data-stu-id="db1e3-p103">There are multiple ways you can deploy Windows 10 Enterprise for your organization. Here, we'll focus on how you can configure and deploy a Windows 10 Enterprise image through these modern deployment scenarios.</span></span>

| <span data-ttu-id="db1e3-126">部署案例</span><span class="sxs-lookup"><span data-stu-id="db1e3-126">Deployment scenario</span></span> | <span data-ttu-id="db1e3-127">使用時機</span><span class="sxs-lookup"><span data-stu-id="db1e3-127">When to use it</span></span> |
|:--- |:--- |
| [<span data-ttu-id="db1e3-128">使用 System Center Configuration Manager 作為在就地升級</span><span class="sxs-lookup"><span data-stu-id="db1e3-128">Using System Center Configuration Manager as an in-place upgrade</span></span>](windows10-deploy-inplaceupgrade.md) | <span data-ttu-id="db1e3-129">如果您需要升級 Windows 7 或 Windows 8.1 電腦<a href="https://aka.ms/windows-10-release-information" target="_blank">目前版本</a>的 Windows 10 Enterprise 與您的電腦目前 managed 搭配<a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager （目前分支）</a>，選取此選項。</span><span class="sxs-lookup"><span data-stu-id="db1e3-129">Select this option if you need to upgrade Windows 7 or Windows 8.1 computers to the <a href="https://aka.ms/windows-10-release-information" target="_blank">current version</a> of Windows 10 Enterprise and your computers are currently managed with <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current branch)</a>.</span></span> |
| [<span data-ttu-id="db1e3-130">使用 Windows 自動駕駛儀上</span><span class="sxs-lookup"><span data-stu-id="db1e3-130">Using Windows Autopilot</span></span>](windows10-deploy-autopilot.md) | <span data-ttu-id="db1e3-p104">如果您要設定具有 Windows 10 企業版 1703年或更新版本預先安裝的新 Windows 電腦，選取此選項。使用者將會啟動安裝程式使用輸入其工作所需的設定或學校帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="db1e3-p104">Select this option if you are setting up new Windows computers that have Windows 10 Enterprise, version 1703 or later pre-installed. End users will initiate setup using your desired configuration by entering their work or school account credentials.</span></span> |

<span data-ttu-id="db1e3-p105">如果這些部署案例不會符合組織的需求，您可以了解其他案例及了解功能及限制的每個[Windows 10 的部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)中。您也可以在您自己的<a href="https://aka.ms/planforwin10deployment" target="_blank">規劃 Windows 10 部署</a>。</span><span class="sxs-lookup"><span data-stu-id="db1e3-p105">If these deployment scenarios do not fit the needs of your organization, you can learn about other scenarios and understand the capabilities and limitations of each in [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). You can also <a href="https://aka.ms/planforwin10deployment" target="_blank">plan for Windows 10 deployment</a> on your own.</span></span>

<span data-ttu-id="db1e3-135">您可以深入了解 Windows 10 請配合下列文章：</span><span class="sxs-lookup"><span data-stu-id="db1e3-135">You can learn more about Windows 10 with these articles:</span></span>

- [<span data-ttu-id="db1e3-136">Microsoft 365 Enterprise 產品頁面</span><span class="sxs-lookup"><span data-stu-id="db1e3-136">Microsoft 365 Enterprise product page</span></span>](https://www.microsoft.com/microsoft-365/enterprise)
- [<span data-ttu-id="db1e3-137">Windows 10</span><span class="sxs-lookup"><span data-stu-id="db1e3-137">Windows 10</span></span>](https://docs.microsoft.com/windows/windows-10)
- [<span data-ttu-id="db1e3-138">部署及更新 Windows 10</span><span class="sxs-lookup"><span data-stu-id="db1e3-138">Deploy and update Windows 10</span></span>](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a><span data-ttu-id="db1e3-139">其他服務與功能</span><span class="sxs-lookup"><span data-stu-id="db1e3-139">Additional services and features</span></span>
<span data-ttu-id="db1e3-140">Windows 10 企業部署的一部分，您可以新增下列其他服務和功能。</span><span class="sxs-lookup"><span data-stu-id="db1e3-140">As part of your deployment of Windows 10 Enterprise, you can add these additional services and features.</span></span>

### <a name="windows-analytics"></a><span data-ttu-id="db1e3-141">Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="db1e3-141">Windows Analytics</span></span>

<span data-ttu-id="db1e3-142">Windows 使用診斷資料提供豐富、 可採取的資訊可協助您獲取深層洞察力到的操作效率和您環境中的 Windows 10 裝置的狀況。</span><span class="sxs-lookup"><span data-stu-id="db1e3-142">Windows uses diagnostics data to provide rich, actionable information to help you gain deep insights into operational efficiency and the health of Windows 10 devices in your environment.</span></span>

* <span data-ttu-id="db1e3-143">升級整備-升級整備可協助您移動到 Windows 10 並保持在最新的 Windows 10 功能更新目前。</span><span class="sxs-lookup"><span data-stu-id="db1e3-143">Upgrade Readiness - Upgrade Readiness will help you move to Windows 10 and stay current with new Windows 10 Feature Updates.</span></span> 
* <span data-ttu-id="db1e3-144">更新規範-更新規範被針對 IT 管理員想要取得所有其 Windows 10 裝置不需要其他基礎結構的整體檢視。</span><span class="sxs-lookup"><span data-stu-id="db1e3-144">Update Compliance - Update Compliance is targeted to the IT admin who wants to gain a holistic view of all their Windows 10 devices, without any additional infrastructure requirements.</span></span>
* <span data-ttu-id="db1e3-145">裝置狀況-您可以使用裝置狀況主動偵測及修復使用者影響的問題。</span><span class="sxs-lookup"><span data-stu-id="db1e3-145">Device Health - You can use Device Health to proactively detect and remediate end-user impacting issues.</span></span>

<span data-ttu-id="db1e3-146">如需詳細資訊，請參閱[Windows 分析概觀 （英文）](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) 。</span><span class="sxs-lookup"><span data-stu-id="db1e3-146">See [Windows Analytics Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) for more information.</span></span>

### <a name="windows-security"></a><span data-ttu-id="db1e3-147">Windows 安全性</span><span class="sxs-lookup"><span data-stu-id="db1e3-147">Windows security</span></span>

<span data-ttu-id="db1e3-p106">Windows 10 提供可協助保護威脅，協助您保護您的裝置，並協助存取控制功能。使用 Windows 10 您取得從開始保護裝置右邊的關鍵安全性功能。Microsoft 365 E3 新增安全性功能，例如 Windows Hello Business、 Windows 防禦者應用程式控制項和 Windows 資訊保護。使用 Microsoft 365 E5，您可以取得所有保護從 Microsoft 365 E3 安全性加上雲端式安全性功能和 Windows 防禦者進階威脅保護。</span><span class="sxs-lookup"><span data-stu-id="db1e3-p106">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control. With Windows 10, you get critical security features that protect your device right from the start. Microsoft 365 E3 adds security features such as Windows Hello for Business, Windows Defender Application Control, and Windows Information Protection. With Microsoft 365 E5, you get all the protection from Microsoft 365 E3 security plus cloud-based security features and Windows Defender Advanced Threat Protection.</span></span> 

<span data-ttu-id="db1e3-152">若要深入了解您取得 Windows 10 Enterprise 和取得指導如何部署、 管理、 設定及疑難排解三個主要的安全性功能的安全性功能，請參閱[步驟 5： 部署 Windows 10 企業安全性功能](windows10-enable-security-features.md)。</span><span class="sxs-lookup"><span data-stu-id="db1e3-152">To learn more about the security features that you get with Windows 10 Enterprise and get guidance on how you can deploy, manage, configure, and troubleshoot three key ecurity features, see [Step 5: Deploy Windows 10 Enterprise security features](windows10-enable-security-features.md).</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="db1e3-153">Microsoft 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="db1e3-153">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="db1e3-154">Microsoft 內鑽入並了解公司如何為規劃、 部署、 及管理更新的 Windows 10，請參閱：</span><span class="sxs-lookup"><span data-stu-id="db1e3-154">To peek inside Microsoft and learn how the company planned for, deployed, and is managing updates for Windows 10, see:</span></span>

- [<span data-ttu-id="db1e3-155">準備您的組織以便進行完美的 Windows 10 部署</span><span class="sxs-lookup"><span data-stu-id="db1e3-155">Preparing your organization for a seamless Windows 10 deployment</span></span>](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [<span data-ttu-id="db1e3-156">採用 Microsoft 的 Windows 即服務</span><span class="sxs-lookup"><span data-stu-id="db1e3-156">Adopting Windows as a service at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [<span data-ttu-id="db1e3-157">在 Microsoft 以就地升級方式部署 Windows 10</span><span class="sxs-lookup"><span data-stu-id="db1e3-157">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [<span data-ttu-id="db1e3-158">使用 Windows Hello 企業版實作強大的使用者驗證</span><span class="sxs-lookup"><span data-stu-id="db1e3-158">Implementing strong user authentication with Windows Hello for Business</span></span>](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- <span data-ttu-id="db1e3-159">[Windows 10 部署：Microsoft IT 的秘訣與技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (影片)</span><span class="sxs-lookup"><span data-stu-id="db1e3-159">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
- [<span data-ttu-id="db1e3-160">Windows Defender ATP 可協助偵測複雜的威脅</span><span class="sxs-lookup"><span data-stu-id="db1e3-160">Windows Defender ATP helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- <span data-ttu-id="db1e3-161">[使用 Windows Defender 和 Windows Defender ATP 保護現代的企業](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (影片)</span><span class="sxs-lookup"><span data-stu-id="db1e3-161">[Securing the modern enterprise with Windows Defender and Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="db1e3-162">Contoso 如何執行 Microsoft 365 企業版</span><span class="sxs-lookup"><span data-stu-id="db1e3-162">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="db1e3-163">請參閱如何 Contoso Corporation、 虛構但代表性多重國民 business、[部署 Windows 10 Enterprise](contoso-win10.md)。</span><span class="sxs-lookup"><span data-stu-id="db1e3-163">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Windows 10 Enterprise](contoso-win10.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="db1e3-164">下一步</span><span class="sxs-lookup"><span data-stu-id="db1e3-164">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="db1e3-165">準備您的組織 Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="db1e3-165">Prepare your organization for Windows 10 Enterprise</span></span>](windows10-prepare-your-org.md) |
