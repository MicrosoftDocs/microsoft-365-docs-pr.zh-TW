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
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>步驟 5： 部署 Windows 10 企業安全性功能

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 提供可協助保護威脅，協助您保護您的裝置，並協助存取控制功能。 

若要深入了解這些技術，請參閱：
* [存取保護](https://docs.microsoft.com/windows/access-protection/)-了解存取控制、 S/MIME 數位憑證，認證 Guard 使用者帳戶控制、 虛擬智慧卡、 Windows Hello for Business、 具有進階安全性的 Windows 防火牆等等
* [裝置安全性](https://docs.microsoft.com/windows/device-security/)-包含 AppLocker、 BitLocker、 裝置 Guard 及信任的平台模組
* [威脅保護](https://docs.microsoft.com/windows/threat-protection/)-包含 Windows 防禦者安全性中心、 Windows 防禦者進階威脅保護、 Windows 防禦者防毒、 Windows 防禦者應用程式 Guard、 Windows 防禦者智慧畫面及 Windows 資訊保護

此步驟會顯示您如何部署、 管理、 設定及使用這些安全性功能的疑難排解：

* [Windows Defender 防毒軟體](#windows-defender-antivirus)
* [Windows Defender 惡意探索防護](#windows-defender-exploit-guard)
* [Windows Defender 進階威脅防護](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender 防毒軟體
Windows 防禦者防毒 (AV) 是內建於 Windows 10 反惡意程式碼解決方案。安全性和反惡意程式碼管理提供桌上型電腦、 可攜式電腦與伺服器。如需 Windows 防禦者 AV、 最小需求，以及如何管理這項功能的詳細資訊，請參閱[Windows 防禦者防毒 Windows 10 和 Windows Server 2016 中](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)。

如果您不使用 Windows 防禦者 AV 作為主要防毒用戶端，或者是否也使用 Windows 防禦者 ATP，有一些考量您需要考慮事項。若要深入了解，請參閱[Windows 防禦者 AV 相容性](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility)。

### <a name="deployment-and-management"></a>部署及管理
部署及管理 Windows 防禦者 AV，請遵循此處的指導：

* [部署、 管理和 Windows 防禦者 AV 報告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [管理及設定工具的參考資料主題](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>組態
使用者可設定許多功能。如需詳細資訊，請參閱下列資源：

* [設定 Windows 防禦者 AV 功能](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [管理及設定工具的參考資料主題](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

若要協助了解設定選項，請參閱此清單中的所有設定 （如他們的群組原則設定所定義）：[使用群組原則設定來設定和管理 Windows 防禦者 AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

您可以使用[Windows 防禦者 AV 保護的評估指南 》](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus)可協助評估的保護層級及網路上的 Windows 防禦者 AV 影響。這也有助於在建立初始設定的或做為快速入門指南' 並定期更新用於設定及啟用以確保最大保護功能提供最有用的建議。

### <a name="reporting"></a>報告
您可以取得的使用設定工具，例如 System Center Configuration Manager 或 Microsoft Intune 報表。您也可以取得報表從更新規範 (OMS) 或取用您 SIEM 中的 Windows 事件記錄檔。如果您的 Windows 防禦者 ATP 的授權，您也可以取得 Windows 防禦者 AV 已偵測到報告，然後執行基本補救方法。如需詳細資訊，請參閱下列資源：
* [部署、 管理和 Windows 防禦者 AV 報告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [在 Windows 防禦者 AV 保護報告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Windows 防禦者 ATP 入口網站概觀 （英文)](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>疑難排解
上的錯誤和事件程式碼的基本疑難排解的資訊，請參閱[檢閱事件記錄檔和疑難排解問題 Windows 防禦者 AV 的錯誤碼](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)。

您也可以使用 Windows 防禦者安全性智慧提交系統提交 （例如誤判） 的問題。若要了解如何，請參閱[Microsoft 送出問題](https://www.microsoft.com/wdsi/filesubmission)。

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender 惡意探索防護
Windows 防禦者利用 Guard 是一組新的 Windows 10 主機入侵防護功能。如需 Windows 防禦者利用 Guard、 最小需求，以及如何管理這項功能的詳細資訊，請參閱[Windows 防禦者利用 Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)。

### <a name="deployment-management-and-configuration"></a>部署、 管理和設定
若要部署、 管理及設定 Windows 防禦者利用 Guard，請遵循此處的指導：
* [利用保護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [攻擊呈現保護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [網路防護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [控制資料夾存取](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

您可以使用一系列的評估各項主題可協助評估的保護層級及網路上的 Windows 防禦者利用 Guard 影響。這也是在建立初始設定的或做為快速入門指南' 很有用，並指引和主題定期更新用於設定及啟用以確保最大保護功能提供最有用的建議。如需詳細資訊]，[利用 Guard 評估 Windows 防禦者](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard)。

### <a name="reporting"></a>報告
您可以取得的使用設定工具，例如 System Center Configuration Manager 或 Intune 報表。您也可以取得的取用 Windows 事件記錄檔中您 SIEM 報表。如果您的 Windows 防禦者 ATP 的授權，您也可以取得 Windows 防禦者 AV 已偵測到報告，然後執行基本補救方法。如需詳細資訊，請參閱下列資源：
* [檢視 Windows 防禦者利用 Guard 事件](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Windows 防禦者 ATP 入口網站概觀 （英文)](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>疑難排解
您可以執行基本的疑難排解或 （選擇性） Microsoft 提供.cab 檔案並使用 Windows 防禦者安全性智慧提交系統提交 （例如誤判） 的問題。若要了解如何，請參閱[Microsoft 送出問題](https://www.microsoft.com/wdsi/filesubmission)。


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a>Windows Defender 進階威脅防護
Windows 防禦者 ATP，只能與 Microsoft 365 Enterprise E5 計劃是讓企業客戶偵測、 調查及回應在其網路上的進階威脅的安全性服務。如需 Windows 防禦者 ATP、 最小需求，以及如何管理這項功能的詳細資訊，請參閱：

* [Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [基本需求](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>部署、 管理和設定
若要部署 Windows 防禦者 ATP，您需要確定您有權利 Windows 授權。確認您已正確的授權之後, 必須決定要儲存資料的地理位置。之後，您可以啟動服務的 onboarding 端點。

如需這些步驟的詳細資訊，請參閱下列主要的主題： 

* [驗證授權佈建和設定完成設定](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [資料儲存區與隱私權](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [內建的端點和安裝程式存取](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>偵測、 調查、 回應
服務的成功 onboarding 端點] 後便可以開始調查從不同的儀表板的提醒。一旦您已經 1x-6x 提醒，您可以採取回應提醒。 

如需如何執行這些動作的詳細資訊，請參閱：
* [Windows 防禦者 ATP 入口網站概觀 （英文)](https://go.microsoft.com/fwlink/?linkid=861596)
* [使用 Windows 防禦者 ATP 入口網站](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [採取回應](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>整合其他產品與工具
Windows 防禦者 ATP 整合和支援各種其他產品及工具，以展開它的安全性功能。 

更多工具和其他產品的詳細資訊，請參閱：
* [SIEM 工具](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [建立自訂的提醒](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [使用 api （英文）](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [建置 Power BI 報告](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>疑難排解
您可能會發生問題時 onboarding 或使用產品時。如需如何以解決問題的詳細資訊，請參閱：
* [Onboarding 問題的疑難排解](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [疑難排解 Windows 防禦者 ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>下一步

[Windows 10 企業基礎結構允出準則](windows10-exit-criteria.md)
