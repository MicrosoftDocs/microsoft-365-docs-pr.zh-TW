---
title: 階段 3：Windows 10 企業版基礎結構允出準則
f1.keywords:
- NOCSH
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 請確定您的組態符合 Windows 10 企業版的 Microsoft 365 企業版準則。
ms.openlocfilehash: 42d8ec912a70aecef49672682c25f5e42c4bbe21
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085552"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a><span data-ttu-id="612ec-103">階段 3：Windows 10 企業版基礎結構允出準則</span><span class="sxs-lookup"><span data-stu-id="612ec-103">Phase 3: Windows 10 Enterprise infrastructure exit criteria</span></span>

![階段 3：Windows 10 企業版](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="612ec-105">請確定您的 Windows 10 企業版基礎結構符合下列必要準則，而且您已將這些視為選擇性準則。</span><span class="sxs-lookup"><span data-stu-id="612ec-105">Make sure your Windows 10 Enterprise infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a><span data-ttu-id="612ec-106">必要：您的 Microsoft 365 網域已新增並經過驗證</span><span class="sxs-lookup"><span data-stu-id="612ec-106">Required: Your Microsoft 365 domains are added and verified</span></span>

<span data-ttu-id="612ec-107">已使用您的網際網路網域名稱 (例如 contoso.com) 設定 Office 365 和 Intune 訂用帳戶的 Azure AD 租用戶 (而不是使用只包含 “onmicrosoft.com” 的網域名稱)。</span><span class="sxs-lookup"><span data-stu-id="612ec-107">The Azure AD tenant for your Office 365 and Intune subscriptions are configured with your Internet domain names (such as contoso.com), rather than just a domain name that includes “onmicrosoft.com”.</span></span> 

<span data-ttu-id="612ec-p101">如果不這麼做，您會受限於您可設定的驗證方法。例如，通過和同盟驗證無法使用 "onmicrosoft.com" 網域名稱。</span><span class="sxs-lookup"><span data-stu-id="612ec-p101">If you do not do so, you will be limited in the authentication methods that you can configure. For example, pass-through and federated authentication cannot use the “onmicrosoft.com”  domain name.</span></span>

<span data-ttu-id="612ec-110">如有需要，[步驟 1](windows10-prepare-your-org.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="612ec-110">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this requirement.</span></span>

## <a name="optional-your-users-are-added-and-licensed"></a><span data-ttu-id="612ec-111">選用：您的使用者已新增並或獲得授權</span><span class="sxs-lookup"><span data-stu-id="612ec-111">Optional: Your users are added and licensed</span></span>

<span data-ttu-id="612ec-112">已新增您的使用者的對應帳戶 (不是直接新增到 Office 365 和 Intune 訂用帳戶的 Azure AD 租用戶，就是從您的內部部署 Active Directory Domain Services (AD DS) 同步處理目錄)。</span><span class="sxs-lookup"><span data-stu-id="612ec-112">The accounts corresponding to your users are added, either directly to your Azure AD tenant for your Office 365 and Intune subscriptions, or from directory synchronization from your on-premises Active Directory Domain Services (AD DS).</span></span>

<span data-ttu-id="612ec-113">新增使用者後，您可以將 Microsoft 365 企業版授權指派給他們 (不是直接指派為全域管理員或使用者管理員，就是透過群組成員資格自動指派)。</span><span class="sxs-lookup"><span data-stu-id="612ec-113">Once the users are added, you can assign them Microsoft 365 Enterprise licenses, either directly as a global or user administrator, or automatically through group membership.</span></span>

<span data-ttu-id="612ec-114">如有需要，[步驟 1](windows10-prepare-your-org.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="612ec-114">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

## <a name="optional-diagnostics-are-enabled"></a><span data-ttu-id="612ec-115">選項：已啟用診斷</span><span class="sxs-lookup"><span data-stu-id="612ec-115">Optional: Diagnostics are enabled</span></span>

<span data-ttu-id="612ec-116">您已使用群組原則、Microsoft Intune、登錄編輯程式，或在命令提示字元啟用診斷資料設定。</span><span class="sxs-lookup"><span data-stu-id="612ec-116">You have enabled diagnostic data settings using Group Policy, Microsoft Intune, the Registry Editor, or at the command prompt.</span></span>

<span data-ttu-id="612ec-117">如有需要，[步驟 1](windows10-prepare-your-org.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="612ec-117">If needed, [Step 1](windows10-prepare-your-org.md) can help you with this option.</span></span>

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a><span data-ttu-id="612ec-118">就地升級所需：已建立作業系統部署的 Configuration Manager 工作順序</span><span class="sxs-lookup"><span data-stu-id="612ec-118">Required for in-place upgrade: Created a Configuration Manager task sequence for an operating system deployment</span></span>

<span data-ttu-id="612ec-119">若要啟動 Configuration Manager 工作順序，在執行 Windows 7 或 Windows 8.1 的裝置上進行就地升級，您必須：</span><span class="sxs-lookup"><span data-stu-id="612ec-119">To start a Configuration Manager task sequence to do an in-place upgrade on a device running Windows 7 or Windows 8.1, you must have:</span></span>

- <span data-ttu-id="612ec-120">設定適當的 Windows 診斷資料層級</span><span class="sxs-lookup"><span data-stu-id="612ec-120">Set the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="612ec-121">確認升級 Windows 的整備度</span><span class="sxs-lookup"><span data-stu-id="612ec-121">Verified the readiness to upgrade Windows</span></span>
- <span data-ttu-id="612ec-122">建立 Configuration Manager 工作順序，其中包含裝置集合和使用 Windows 10 OS 影像的作業系統部署</span><span class="sxs-lookup"><span data-stu-id="612ec-122">Created a Configuration Manager task sequence that includes a device collection and an operating system deployment with a Windows 10 OS image</span></span>

<span data-ttu-id="612ec-p102">一旦備妥，您就可以在準備好升級 Windows 的裝置上執行就地升級。若要從 Microsoft 365 企業版獲得最大好處，請儘可能多升級執行 Windows 7 和 Windows 8.1 的裝置。</span><span class="sxs-lookup"><span data-stu-id="612ec-p102">Once this is in place, you can perform in-place upgrades on devices that are ready to upgrade Windows. To get the maximum benefit out of Microsoft 365 Enterprise, upgrade as many devices running Windows 7 and Windows 8.1 as you can.</span></span> 

<span data-ttu-id="612ec-p103">每個執行 Windows 10 企業版的裝置都可以享有 Microsoft 365 企業版的整合式解決方案好處。其餘執行 Windows 7 或 Windows 8.1 的裝置無法使用 Windows 10 企業版的雲端相關技術和進階安全性功能。</span><span class="sxs-lookup"><span data-stu-id="612ec-p103">Each device running Windows 10 Enterprise can participate in the benefits of the integrated solution of Microsoft 365 Enterprise. The remaining devices running Windows 7 or Windows 8.1 cannot use the cloud-connected technologies and advanced security features of Windows 10 Enterprise.</span></span>

<span data-ttu-id="612ec-127">如有需要，[步驟 2](windows10-deploy-inplaceupgrade.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="612ec-127">If needed, [Step 2](windows10-deploy-inplaceupgrade.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a><span data-ttu-id="612ec-128">新裝置所需：已設定 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="612ec-128">Required for new devices: Configured Windows Autopilot</span></span>

<span data-ttu-id="612ec-129">若要使用 Windows Autopilot 在新的裝置上部署及自訂 Windows 10 企業版，您必須：</span><span class="sxs-lookup"><span data-stu-id="612ec-129">To use Windows Autopilot to deploy and customize Windows 10 Enterprise on a new device, you must have:</span></span>

- <span data-ttu-id="612ec-130">設定適當的 Windows 診斷資料層級</span><span class="sxs-lookup"><span data-stu-id="612ec-130">Configured the proper Windows diagnostics data level</span></span>
- <span data-ttu-id="612ec-131">設定 Windows Autopilot 的先決條件，其中包含：</span><span class="sxs-lookup"><span data-stu-id="612ec-131">Configured the prerequisites for Windows Autopilot, which include:</span></span>
   - <span data-ttu-id="612ec-132">裝置註冊和 OOBE 自訂</span><span class="sxs-lookup"><span data-stu-id="612ec-132">Device registration and OOBE customization</span></span>
   - <span data-ttu-id="612ec-133">OOBE 公司品牌推廣</span><span class="sxs-lookup"><span data-stu-id="612ec-133">Company branding for OOBE</span></span>
   - <span data-ttu-id="612ec-134">Microsoft Intune 中的 MDM 自動註冊</span><span class="sxs-lookup"><span data-stu-id="612ec-134">MDM auto-enrollment in Microsoft Intune</span></span>
   - <span data-ttu-id="612ec-135">Windows Autopilot 所用雲端服務的網路連線能力</span><span class="sxs-lookup"><span data-stu-id="612ec-135">Network connectivity to cloud services used by Windows Autopilot</span></span>
- <span data-ttu-id="612ec-136">已預先安裝 Windows 10 (版本 1703 或更新版本) 的裝置</span><span class="sxs-lookup"><span data-stu-id="612ec-136">Devices that are pre-installed with Windows 10, version 1703 or later</span></span>
- <span data-ttu-id="612ec-137">為您的組織選取 Windows Autopilot Deployment 方案</span><span class="sxs-lookup"><span data-stu-id="612ec-137">Selected the Windows Autopilot Deployment Program for your organization</span></span>

<span data-ttu-id="612ec-138">Windows Autopilot 設定好之後，您就可以使用它來設定和自訂 Windows 10 企業版，以獲得全新的體驗 (OOBE)：</span><span class="sxs-lookup"><span data-stu-id="612ec-138">Once the Windows Autopilot configuration is in place, you can use it to configure and customize Windows 10 Enterprise for the out-of-the-box experience (OOBE) for:</span></span>

- <span data-ttu-id="612ec-139">新裝置</span><span class="sxs-lookup"><span data-stu-id="612ec-139">New devices</span></span>
- <span data-ttu-id="612ec-140">已經在您的組織中完成全新安裝的裝置。</span><span class="sxs-lookup"><span data-stu-id="612ec-140">Devices that have already completed an out-of-box setup in your organization.</span></span> 

<span data-ttu-id="612ec-141">Windows Autopilot 會設定裝置並將它連線到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="612ec-141">Windows Autopilot configures the device and connects it to Azure AD.</span></span>

<span data-ttu-id="612ec-142">若沒有 Windows Autopilot，您必須手動設定新的裝置，包括 Azure AD 的連線。</span><span class="sxs-lookup"><span data-stu-id="612ec-142">Without Windows Autopilot, you must manually configure new devices, including the connection to Azure AD.</span></span>

<span data-ttu-id="612ec-143">如有需要，[步驟 3](windows10-deploy-autopilot.md) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="612ec-143">If needed, [Step 3](windows10-deploy-autopilot.md) can help you with this requirement.</span></span>

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a><span data-ttu-id="612ec-144">選用：您使用 Windows Analytics 裝置健全狀況來監視您的 Windows 10 企業版裝置</span><span class="sxs-lookup"><span data-stu-id="612ec-144">Optional: You are using Windows Analytics Device Health to monitor your Windows 10 Enterprise-based devices</span></span>

<span data-ttu-id="612ec-p104">您使用了「透過裝置健全狀況監視裝置的健全狀況」中的資訊，偵測及矯正會影響使用者的問題。快速解決使用者問題可減少支援成本，並向您的使用者證明對 Windows 10 企業版的 IT 承諾，這可協助推動整個組織採用。</span><span class="sxs-lookup"><span data-stu-id="612ec-p104">You used the information in Monitor the health of devices with Device Health to detect and remediate issues affecting end users. Quickly addressing end-user issues can reduce your support costs and demonstrate to your users the IT commitment to Windows 10 Enterprise, which can help drive adoption across your organization.</span></span> 

<span data-ttu-id="612ec-147">如有需要，[步驟 4](windows10-enable-windows-analytics.md) 可協助您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="612ec-147">If needed, [Step 4](windows10-enable-windows-analytics.md) can help you with this option.</span></span>

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a><span data-ttu-id="612ec-148">必要：您是使用 Windows Defender 防毒軟體或自有的反惡意程式碼解決方案</span><span class="sxs-lookup"><span data-stu-id="612ec-148">Required: You are using Windows Defender Antivirus or your own antimalware solution</span></span>

<span data-ttu-id="612ec-p105">您已部署 Windows Defender 防毒軟體或自有的防毒解決方案來保護執行 Windows 10 企業版的裝置，使其免於遭受惡意軟體攻擊。如果您已部署 Windows Defender 防毒軟體，您便已實作報告方法 (例如 Microsoft Endpoint Configuration Manager 或 Microsoft Intune) 來監視防毒事件和活動。</span><span class="sxs-lookup"><span data-stu-id="612ec-p105">You deployed Windows Defender Antivirus or your own antivirus solution to protect your devices running Windows 10 Enterprise from malicious software. If you deployed Windows Defender Antivirus, you have implemented a reporting method, such as Microsoft Endpoint Configuration Manager or Microsoft Intune, to monitor antivirus events and activity.</span></span>

<span data-ttu-id="612ec-151">如有需要，[步驟 5](windows10-enable-security-features.md#windows10-sec-av) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="612ec-151">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-av) can help you with this requirement.</span></span>

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a><span data-ttu-id="612ec-152">必要：您是使用 Windows Defender 惡意探索防護</span><span class="sxs-lookup"><span data-stu-id="612ec-152">Required: You are using Windows Defender Exploit Guard</span></span>

<span data-ttu-id="612ec-153">您已部署 Windows Defender 惡意探索防護來保護執行 Windows 10 企業版的裝置，使其免於遭到入侵，並已實作報告方法 (例如 Configuration Manager 或 Microsoft Intune) 來監視入侵事件和活動。</span><span class="sxs-lookup"><span data-stu-id="612ec-153">You deployed Windows Defender Exploit Guard to protect your devices running Windows 10 Enterprise from intrusion and have implemented a reporting method, such as Configuration Manager or Microsoft Intune, to monitor intrusion events and activity.</span></span>

<span data-ttu-id="612ec-154">如有需要，[步驟 5](windows10-enable-security-features.md#windows10-sec-eg) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="612ec-154">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-eg) can help you with this requirement.</span></span>

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a><span data-ttu-id="612ec-155">必要：使用 Microsoft Defender 進階威脅防護 (僅限 Microsoft 365 E5)</span><span class="sxs-lookup"><span data-stu-id="612ec-155">Required: You are using Microsoft Defender Advanced Threat Protection (Microsoft 365 E5 only)</span></span>

<span data-ttu-id="612ec-156">您已部署 Microsoft Defender 進階威脅防護 (ATP)，以針對您的網路及執行 Windows 10 企業版的裝置偵測、調查及回應進階威脅。</span><span class="sxs-lookup"><span data-stu-id="612ec-156">You deployed Microsoft Defender Advanced Threat Protection (ATP) to detect, investigate, and respond to advanced threats against your network and devices running Windows 10 Enterprise.</span></span> 

<span data-ttu-id="612ec-157">此外，您也已整合 Microsoft Defender ATP 與其他工具，以擴充其功能。</span><span class="sxs-lookup"><span data-stu-id="612ec-157">Optionally, you have integrated Microsoft Defender ATP with other tools to expand its capabilities.</span></span>

<span data-ttu-id="612ec-158">如有需要，[步驟 5](windows10-enable-security-features.md#windows10-sec-atp) 可協助您符合這項要求。</span><span class="sxs-lookup"><span data-stu-id="612ec-158">If needed, [Step 5](windows10-enable-security-features.md#windows10-sec-atp) can help you with this requirement.</span></span>

## <a name="results-and-next-steps"></a><span data-ttu-id="612ec-159">結果和後續步驟</span><span class="sxs-lookup"><span data-stu-id="612ec-159">Results and next steps</span></span>

<span data-ttu-id="612ec-160">您的 Windows 10 企業版基礎結構已準備好可以在新裝置上開始安裝，以及在執行舊版 Windows 的裝置上開始就地升級，且您會使用 Windows 10 企業版的重要安全性功能。</span><span class="sxs-lookup"><span data-stu-id="612ec-160">Your Windows 10 Enterprise infrastructure is ready to begin installation on new devices and upgrades-in-place on devices running previous versions of Windows, and you are using the key security features of Windows 10 Enterprise.</span></span>

|||
|:-------|:-----|
|![階段 4：Office 365 專業增強版](../media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| <span data-ttu-id="612ec-162">如果您會遵循 Microsoft 365 企業版的端對端部署階段，則下一個階段是 [Office 365 專業增強版](office365proplus-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="612ec-162">If you're following the phases for the end-to-end deployment of Microsoft 365 Enterprise, your next phase is [Office 365 ProPlus](office365proplus-infrastructure.md).</span></span> |
