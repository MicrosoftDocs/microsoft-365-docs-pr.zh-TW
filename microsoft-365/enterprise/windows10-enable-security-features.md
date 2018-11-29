---
title: 部署 Windows 10 企業安全性功能
description: 提供高階指導您部署的 Pc 上的 Windows 10 Enterprise 做為 Microsoft 365 企業版的一部分所需的步驟。
keywords: Microsoft 365、 Microsoft 365 企業版、 Microsoft 365 文件、 Windows 10 Enterprise 安全性
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: d051f9e56d8e9986fbe0975c2bdc6c606b32a444
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866759"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a><span data-ttu-id="5f864-104">步驟 5： 部署 Windows 10 企業安全性功能</span><span class="sxs-lookup"><span data-stu-id="5f864-104">Step 5: Deploy Windows 10 Enterprise security features</span></span>

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

<span data-ttu-id="5f864-105">Windows 10 提供可協助保護威脅，協助您保護您的裝置，並協助存取控制功能。</span><span class="sxs-lookup"><span data-stu-id="5f864-105">Windows 10 provides features to help protect against threats, help you secure your devices, and help with access control.</span></span> 

<span data-ttu-id="5f864-106">若要深入了解這些技術，請參閱：</span><span class="sxs-lookup"><span data-stu-id="5f864-106">To learn more about these technologies, see:</span></span>
* <span data-ttu-id="5f864-107">[存取保護](https://docs.microsoft.com/windows/access-protection/)-了解存取控制、 S/MIME 數位憑證，認證 Guard 使用者帳戶控制、 虛擬智慧卡、 Windows Hello for Business、 具有進階安全性的 Windows 防火牆等等</span><span class="sxs-lookup"><span data-stu-id="5f864-107">[Access protection](https://docs.microsoft.com/windows/access-protection/) - Learn about access control, S/MIME, digital certificates, Credential Guard, User Account Control, virtual smart cards, Windows Hello for Business, Windows Firewall with Advanced Security, and more</span></span>
* <span data-ttu-id="5f864-108">[裝置安全性](https://docs.microsoft.com/windows/device-security/)-包含 AppLocker、 BitLocker、 裝置 Guard 及信任的平台模組</span><span class="sxs-lookup"><span data-stu-id="5f864-108">[Device security](https://docs.microsoft.com/windows/device-security/) - Includes AppLocker, BitLocker, Device Guard, and Trusted Platform Module</span></span>
* <span data-ttu-id="5f864-109">[威脅保護](https://docs.microsoft.com/windows/threat-protection/)-包含 Windows 防禦者安全性中心、 Windows 防禦者進階威脅保護、 Windows 防禦者防毒、 Windows 防禦者應用程式 Guard、 Windows 防禦者智慧畫面及 Windows 資訊保護</span><span class="sxs-lookup"><span data-stu-id="5f864-109">[Threat protection](https://docs.microsoft.com/windows/threat-protection/) - Includes Windows Defender Security Center, Windows Defender Advanced Threat Protection, Windows Defender Antivirus, Windows Defender Application Guard, Windows Defender Smart Screen, and Windows Information Protection</span></span>

<span data-ttu-id="5f864-110">此步驟會顯示您如何部署、 管理、 設定及使用這些安全性功能的疑難排解：</span><span class="sxs-lookup"><span data-stu-id="5f864-110">This step shows you how you can deploy, manage, configure, and troubleshoot using these security features:</span></span>

* [<span data-ttu-id="5f864-111">Windows Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="5f864-111">Windows Defender Antivirus</span></span>](#windows-defender-antivirus)
* [<span data-ttu-id="5f864-112">Windows Defender 惡意探索防護</span><span class="sxs-lookup"><span data-stu-id="5f864-112">Windows Defender Exploit Guard</span></span>](#windows-defender-exploit-guard)
* [<span data-ttu-id="5f864-113">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="5f864-113">Windows Defender Advanced Threat Protection</span></span>](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a><span data-ttu-id="5f864-114">Windows Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="5f864-114">Windows Defender Antivirus</span></span>
<span data-ttu-id="5f864-p101">Windows 防禦者防毒 (AV) 是內建於 Windows 10 反惡意程式碼解決方案。安全性和反惡意程式碼管理提供桌上型電腦、 可攜式電腦與伺服器。如需 Windows 防禦者 AV、 最小需求，以及如何管理這項功能的詳細資訊，請參閱[Windows 防禦者防毒 Windows 10 和 Windows Server 2016 中](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="5f864-p101">Windows Defender Antivirus (AV) is an antimalware solution that's built into Windows 10. It provides security and antimalware management for desktops, portable computers, and servers. For more info about Windows Defender AV, the minimum requirements, and how you can manage this feature, see [Windows Defender Antivirus in Windows 10 and Windows Server 2016](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10).</span></span>

<span data-ttu-id="5f864-p102">如果您不使用 Windows 防禦者 AV 作為主要防毒用戶端，或者是否也使用 Windows 防禦者 ATP，有一些考量您需要考慮事項。若要深入了解，請參閱[Windows 防禦者 AV 相容性](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="5f864-p102">If you are not using Windows Defender AV as your primary antivirus client, or if you are also using Windows Defender ATP, there are some considerations you need to take into account. To learn more, see [Windows Defender AV compatibility](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility).</span></span>

### <a name="deployment-and-management"></a><span data-ttu-id="5f864-120">部署及管理</span><span class="sxs-lookup"><span data-stu-id="5f864-120">Deployment and management</span></span>
<span data-ttu-id="5f864-121">部署及管理 Windows 防禦者 AV，請遵循此處的指導：</span><span class="sxs-lookup"><span data-stu-id="5f864-121">To deploy and manage Windows Defender AV, follow the guidance here:</span></span>

* [<span data-ttu-id="5f864-122">部署、 管理和 Windows 防禦者 AV 報告</span><span class="sxs-lookup"><span data-stu-id="5f864-122">Deploy, manage, and report on Windows Defender AV</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [<span data-ttu-id="5f864-123">管理及設定工具的參考資料主題</span><span class="sxs-lookup"><span data-stu-id="5f864-123">Reference topics for management and configuration tools</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a><span data-ttu-id="5f864-124">組態</span><span class="sxs-lookup"><span data-stu-id="5f864-124">Configuration</span></span>
<span data-ttu-id="5f864-p103">使用者可設定許多功能。如需詳細資訊，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="5f864-p103">Users can configure a number of features. For more info, see these resources:</span></span>

* [<span data-ttu-id="5f864-127">設定 Windows 防禦者 AV 功能</span><span class="sxs-lookup"><span data-stu-id="5f864-127">Configure Windows Defender AV features</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [<span data-ttu-id="5f864-128">管理及設定工具的參考資料主題</span><span class="sxs-lookup"><span data-stu-id="5f864-128">Reference topics for management and configuration tools</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

<span data-ttu-id="5f864-129">若要協助了解設定選項，請參閱此清單中的所有設定 （如他們的群組原則設定所定義）：[使用群組原則設定來設定和管理 Windows 防禦者 AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="5f864-129">To help understand configuration options, refer to this list of all settings (as defined by their Group Policy configuration): [Use Group Policy settings to configure and manage Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)</span></span>

<span data-ttu-id="5f864-p104">您可以使用[Windows 防禦者 AV 保護的評估指南 》](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus)可協助評估的保護層級及網路上的 Windows 防禦者 AV 影響。這也有助於在建立初始設定的或做為快速入門指南' 並定期更新用於設定及啟用以確保最大保護功能提供最有用的建議。</span><span class="sxs-lookup"><span data-stu-id="5f864-p104">You can use the [Windows Defender AV protection Evaluation Guide](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) to help evaluate the protection level and impact of Windows Defender AV on your network. This can also be useful in creating an initial configuration or as a ‘quick start guide’ and is regularly updated to provide the most useful recommendations for configuring and enabling features to ensure maximum protection.</span></span>

### <a name="reporting"></a><span data-ttu-id="5f864-132">報告</span><span class="sxs-lookup"><span data-stu-id="5f864-132">Reporting</span></span>
<span data-ttu-id="5f864-p105">您可以取得的使用設定工具，例如 System Center Configuration Manager 或 Microsoft Intune 報表。您也可以取得報表從更新規範 (OMS) 或取用您 SIEM 中的 Windows 事件記錄檔。如果您的 Windows 防禦者 ATP 的授權，您也可以取得 Windows 防禦者 AV 已偵測到報告，然後執行基本補救方法。如需詳細資訊，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="5f864-p105">You can obtain reporting by using a configuration tool, such as System Center Configuration Manager or Microsoft Intune. You can also obtain reporting from Update Compliance (OMS) or by consuming Windows event logs in your SIEM. If you have a license for Windows Defender ATP, you can also obtain reporting into Windows Defender AV detections and perform basic remediation. For more info, see these resources:</span></span>
* [<span data-ttu-id="5f864-137">部署、 管理和 Windows 防禦者 AV 報告</span><span class="sxs-lookup"><span data-stu-id="5f864-137">Deploy, manage, and report on Windows Defender AV</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [<span data-ttu-id="5f864-138">在 Windows 防禦者 AV 保護報告</span><span class="sxs-lookup"><span data-stu-id="5f864-138">Report on Windows Defender AV protection</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [<span data-ttu-id="5f864-139">Windows 防禦者 ATP 入口網站概觀 （英文)</span><span class="sxs-lookup"><span data-stu-id="5f864-139">Windows Defender ATP portal overview</span></span>](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a><span data-ttu-id="5f864-140">疑難排解</span><span class="sxs-lookup"><span data-stu-id="5f864-140">Troubleshooting</span></span>
<span data-ttu-id="5f864-141">上的錯誤和事件程式碼的基本疑難排解的資訊，請參閱[檢閱事件記錄檔和疑難排解問題 Windows 防禦者 AV 的錯誤碼](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="5f864-141">For info on basic troubleshooting of error and event codes, see [Review event logs and error codes to troubleshoot issues with Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).</span></span>

<span data-ttu-id="5f864-p106">您也可以使用 Windows 防禦者安全性智慧提交系統提交 （例如誤判） 的問題。若要了解如何，請參閱[Microsoft 送出問題](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="5f864-p106">You can also submit issues (such as false positives) by using the Windows Defender Security Intelligence submission system. To learn how, see [Submit issues to Microsoft](https://www.microsoft.com/wdsi/filesubmission).</span></span>

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a><span data-ttu-id="5f864-144">Windows Defender 惡意探索防護</span><span class="sxs-lookup"><span data-stu-id="5f864-144">Windows Defender Exploit Guard</span></span>
<span data-ttu-id="5f864-p107">Windows 防禦者利用 Guard 是一組新的 Windows 10 主機入侵防護功能。如需 Windows 防禦者利用 Guard、 最小需求，以及如何管理這項功能的詳細資訊，請參閱[Windows 防禦者利用 Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)。</span><span class="sxs-lookup"><span data-stu-id="5f864-p107">Windows Defender Exploit Guard is a new set of host intrusion prevention capabilities for Windows 10. For more info about Windows Defender Exploit Guard, the  minimum requirements, and how you can manage this feature, see [Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard).</span></span>

### <a name="deployment-management-and-configuration"></a><span data-ttu-id="5f864-147">部署、 管理和設定</span><span class="sxs-lookup"><span data-stu-id="5f864-147">Deployment, management, and configuration</span></span>
<span data-ttu-id="5f864-148">若要部署、 管理及設定 Windows 防禦者利用 Guard，請遵循此處的指導：</span><span class="sxs-lookup"><span data-stu-id="5f864-148">To deploy, manage, and configure Windows Defender Exploit Guard, follow the guidance here:</span></span>
* [<span data-ttu-id="5f864-149">利用保護</span><span class="sxs-lookup"><span data-stu-id="5f864-149">Exploit protection</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [<span data-ttu-id="5f864-150">攻擊呈現保護</span><span class="sxs-lookup"><span data-stu-id="5f864-150">Attack surface protection</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [<span data-ttu-id="5f864-151">網路防護</span><span class="sxs-lookup"><span data-stu-id="5f864-151">Network protection</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [<span data-ttu-id="5f864-152">控制資料夾存取</span><span class="sxs-lookup"><span data-stu-id="5f864-152">Controlled folder access</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

<span data-ttu-id="5f864-p108">您可以使用一系列的評估各項主題可協助評估的保護層級及網路上的 Windows 防禦者利用 Guard 影響。這也是在建立初始設定的或做為快速入門指南' 很有用，並指引和主題定期更新用於設定及啟用以確保最大保護功能提供最有用的建議。如需詳細資訊]，[利用 Guard 評估 Windows 防禦者](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard)。</span><span class="sxs-lookup"><span data-stu-id="5f864-p108">You can use a series of evaluation topics to help evaluate the protection level and impact of Windows Defender Exploit Guard on your network. This can also be useful in creating an initial configuration or as a ‘quick start guide’ and the topics and guidance are regularly updated to provide the most useful recommendations for configuring and enabling features to ensure maximum protection. For more info,  [Evaluate Windows Defender Exploit Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard).</span></span>

### <a name="reporting"></a><span data-ttu-id="5f864-156">報告</span><span class="sxs-lookup"><span data-stu-id="5f864-156">Reporting</span></span>
<span data-ttu-id="5f864-p109">您可以取得的使用設定工具，例如 System Center Configuration Manager 或 Intune 報表。您也可以取得的取用 Windows 事件記錄檔中您 SIEM 報表。如果您的 Windows 防禦者 ATP 的授權，您也可以取得 Windows 防禦者 AV 已偵測到報告，然後執行基本補救方法。如需詳細資訊，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="5f864-p109">You can obtain reporting by using a configuration tool, such as System Center Configuration Manager or Intune. You can also obtain reporting by consuming Windows event logs in your SIEM. If you have a license for Windows Defender ATP, you can also obtain reporting into Windows Defender AV detections and perform basic remediation. For more info, see these resources:</span></span>
* [<span data-ttu-id="5f864-161">檢視 Windows 防禦者利用 Guard 事件</span><span class="sxs-lookup"><span data-stu-id="5f864-161">View Windows Defender Exploit Guard events</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [<span data-ttu-id="5f864-162">Windows 防禦者 ATP 入口網站概觀 （英文)</span><span class="sxs-lookup"><span data-stu-id="5f864-162">Windows Defender ATP portal overview</span></span>](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a><span data-ttu-id="5f864-163">疑難排解</span><span class="sxs-lookup"><span data-stu-id="5f864-163">Troubleshooting</span></span>
<span data-ttu-id="5f864-p110">您可以執行基本的疑難排解或 （選擇性） Microsoft 提供.cab 檔案並使用 Windows 防禦者安全性智慧提交系統提交 （例如誤判） 的問題。若要了解如何，請參閱[Microsoft 送出問題](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="5f864-p110">You can perform basic troubleshooting or optionally provide Microsoft with .cab files and submit issues (such as false positives) by using the Windows Defender Security Intelligence submission system. To learn how, see [Submit issues to Microsoft](https://www.microsoft.com/wdsi/filesubmission).</span></span>


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a><span data-ttu-id="5f864-166">Windows Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="5f864-166">Windows Defender Advanced Threat Protection</span></span>
<span data-ttu-id="5f864-p111">Windows 防禦者 ATP，只能與 Microsoft 365 Enterprise E5 計劃是讓企業客戶偵測、 調查及回應在其網路上的進階威脅的安全性服務。如需 Windows 防禦者 ATP、 最小需求，以及如何管理這項功能的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="5f864-p111">Windows Defender ATP, only available with the Microsoft 365 Enterprise E5 plan, is a security service that enables enterprise customers to detect, investigate, and respond to advanced threats on their networks. For more info about Windows Defender ATP, the minimum requirements, and how you can manage this feature, see:</span></span>

* [<span data-ttu-id="5f864-169">Windows Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5f864-169">Windows Defender ATP</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [<span data-ttu-id="5f864-170">基本需求</span><span class="sxs-lookup"><span data-stu-id="5f864-170">Minimum requirements</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a><span data-ttu-id="5f864-171">部署、 管理和設定</span><span class="sxs-lookup"><span data-stu-id="5f864-171">Deployment, management, and configuration</span></span>
<span data-ttu-id="5f864-p112">若要部署 Windows 防禦者 ATP，您需要確定您有權利 Windows 授權。確認您已正確的授權之後, 必須決定要儲存資料的地理位置。之後，您可以啟動服務的 onboarding 端點。</span><span class="sxs-lookup"><span data-stu-id="5f864-p112">To deploy Windows Defender ATP, you’ll need to ensure you have the right Windows license. After verifying that you have the right license, you’ll need to decide the geolocation for where your data will be stored. After that, you can start onboarding endpoints to the service.</span></span>

<span data-ttu-id="5f864-175">如需這些步驟的詳細資訊，請參閱下列主要的主題：</span><span class="sxs-lookup"><span data-stu-id="5f864-175">For more details on these steps, see these main topics:</span></span> 

* [<span data-ttu-id="5f864-176">驗證授權佈建和設定完成設定</span><span class="sxs-lookup"><span data-stu-id="5f864-176">Validate licensing provisioning and complete set up</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="5f864-177">資料儲存區與隱私權</span><span class="sxs-lookup"><span data-stu-id="5f864-177">Data storage and privacy</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="5f864-178">內建的端點和安裝程式存取</span><span class="sxs-lookup"><span data-stu-id="5f864-178">Onboard endpoints and setup access</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a><span data-ttu-id="5f864-179">偵測、 調查、 回應</span><span class="sxs-lookup"><span data-stu-id="5f864-179">Detect, investigate, respond</span></span>
<span data-ttu-id="5f864-p113">服務的成功 onboarding 端點] 後便可以開始調查從不同的儀表板的提醒。一旦您已經 1x-6x 提醒，您可以採取回應提醒。</span><span class="sxs-lookup"><span data-stu-id="5f864-p113">After successfully onboarding endpoints to the service, you  can start investigating alerts from the various dashboards. Once you've investigated alerts, you can take response actions on alerts.</span></span> 

<span data-ttu-id="5f864-182">如需如何執行這些動作的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="5f864-182">For more info on how to do these, see:</span></span>
* [<span data-ttu-id="5f864-183">Windows 防禦者 ATP 入口網站概觀 （英文)</span><span class="sxs-lookup"><span data-stu-id="5f864-183">Windows Defender ATP portal overview</span></span>](https://go.microsoft.com/fwlink/?linkid=861596)
* [<span data-ttu-id="5f864-184">使用 Windows 防禦者 ATP 入口網站</span><span class="sxs-lookup"><span data-stu-id="5f864-184">Use the Windows Defender ATP portal</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="5f864-185">採取回應</span><span class="sxs-lookup"><span data-stu-id="5f864-185">Take response actions</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a><span data-ttu-id="5f864-186">整合其他產品與工具</span><span class="sxs-lookup"><span data-stu-id="5f864-186">Integrate with other products and tools</span></span>
<span data-ttu-id="5f864-187">Windows 防禦者 ATP 整合和支援各種其他產品及工具，以展開它的安全性功能。</span><span class="sxs-lookup"><span data-stu-id="5f864-187">Windows Defender ATP integrates and supports various other products and tools to expand its security capabilities.</span></span> 

<span data-ttu-id="5f864-188">更多工具和其他產品的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="5f864-188">For more info on the tools and other products, see:</span></span>
* [<span data-ttu-id="5f864-189">SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="5f864-189">SIEM tools</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="5f864-190">建立自訂的提醒</span><span class="sxs-lookup"><span data-stu-id="5f864-190">Create custom alerts</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="5f864-191">使用 api （英文）</span><span class="sxs-lookup"><span data-stu-id="5f864-191">Use APIs</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="5f864-192">建置 Power BI 報告</span><span class="sxs-lookup"><span data-stu-id="5f864-192">Build Power BI reports</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a><span data-ttu-id="5f864-193">疑難排解</span><span class="sxs-lookup"><span data-stu-id="5f864-193">Troubleshooting</span></span>
<span data-ttu-id="5f864-p114">您可能會發生問題時 onboarding 或使用產品時。如需如何以解決問題的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="5f864-p114">You might encounter issues while onboarding or while using the product. For more info on how to address issues, see:</span></span>
* [<span data-ttu-id="5f864-196">Onboarding 問題的疑難排解</span><span class="sxs-lookup"><span data-stu-id="5f864-196">Troubleshooting onboarding issues</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [<span data-ttu-id="5f864-197">疑難排解 Windows 防禦者 ATP</span><span class="sxs-lookup"><span data-stu-id="5f864-197">Troubleshooting Windows Defender ATP</span></span>](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a><span data-ttu-id="5f864-198">下一步</span><span class="sxs-lookup"><span data-stu-id="5f864-198">Next step</span></span>

[<span data-ttu-id="5f864-199">Windows 10 企業基礎結構允出準則</span><span class="sxs-lookup"><span data-stu-id="5f864-199">Windows 10 Enterprise infrastructure exit criteria</span></span>](windows10-exit-criteria.md)
