---
title: 部署 Windows 10 企業版安全性功能
description: 提供在 Microsoft 365 企業版的電腦上部署 Windows 10 企業版安全性功能時，所需步驟的高階指導方針。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 檔，Windows 10 企業版，安全性
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 5407370933c2a99781adf4ca58d3fa905328ed04
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633001"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>步驟5：部署 Windows 10 企業版安全性功能

![階段 3：Windows 10 企業版](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 提供保護企業使用者、停止 cyberthreats 及防止資料遺失的安全性功能。 

若要深入瞭解這些技術，請參閱：

* [Identity protection](https://docs.microsoft.com/windows/security/identity-protection/) -瞭解 Windows Hello 企業版、憑證防護和存取控制。
* [威脅防護](https://docs.microsoft.com/windows/threat-protection/)-深入瞭解 Microsoft Defender 高級威脅防護，這是一種適用于預防防護、入侵後偵測、自動調查和回應的整合平臺。
* [資訊保護](https://docs.microsoft.com/windows/security/information-protection/)-深入瞭解 BitLocker、Windows 資訊保護，以及 windows 10 協助保護企業資料的其他方式。 

這個步驟將告訴您，如何使用下列安全性功能來部署、管理、設定及疑難排解：

* [Windows Defender 防毒軟體](#windows-defender-antivirus)
* [Windows Defender 惡意探索防護](#windows-defender-exploit-guard)
* [Windows Defender 進階威脅防護](#windows10-sec-atp)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender 防毒軟體
Windows Defender 防毒軟體（AV）是 Windows 10 內建的反惡意程式碼解決方案。 它會為桌上型電腦、可擕式電腦及伺服器提供安全性和反惡意程式碼管理。 如需 Windows Defender AV、基本需求以及您如何管理此功能的詳細資訊，請參閱 windows [10 和 Windows Server 2016 中的 Windows Defender 防毒軟體](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)。

如果您不是使用 Windows Defender AV 作為主要防病毒用戶端，或您也在使用 Microsoft Defender ATP，必須考慮考慮一些事項。 若要深入瞭解，請參閱[Windows DEFENDER AV 相容性](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility)。

### <a name="deployment-and-management"></a>部署和管理
若要部署及管理 Windows Defender AV，請遵循下列指導：

* [在 Windows Defender AV 上部署、管理和報告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [管理及設定工具的參考主題](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>組態
使用者可以設定許多功能。 如需詳細資訊，請參閱下列資源：

* [設定 Windows Defender AV 功能](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [管理及設定工具的參考主題](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

若要協助瞭解設定選項，請參閱此清單的所有設定（如其群組原則設定所定義）：[使用群組原則設定來設定及管理 Windows DEFENDER AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

您可以使用[Windows DEFENDER AV 保護評估指南](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus)來協助評估網路上 WINDOWS defender av 的保護層級和影響。 這也可用於建立初始設定或「快速入門手冊」，並定期更新，以提供最實用的建議來設定及啟用功能，以確保最大的保護。

### <a name="reporting"></a>Reporting
您可以使用設定工具（例如 Microsoft 端點 Configuration Manager 或 Microsoft Intune）取得報告。 您也可以從更新規範（OMS）或在 SIEM 中使用 Windows 事件記錄檔取得報告。 如果您有 Microsoft Defender ATP 的授權，您也可以在 Windows Defender AV 偵測中取得報告，並執行基本修復。 如需詳細資訊，請參閱下列資源：
* [在 Windows Defender AV 上部署、管理和報告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [報告 Windows Defender AV 保護](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Microsoft Defender ATP 入口網站概述](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>疑難排解
如需有關錯誤和事件代碼的基本疑難排解資訊，請參閱[複查事件記錄檔和錯誤碼，以排查 Windows DEFENDER AV 的問題](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)。

您也可以使用 Windows Defender 安全性情報提交系統提交問題（例如誤報）。 若要深入瞭解，請參閱[將問題提交至 Microsoft](https://www.microsoft.com/wdsi/filesubmission)。

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender 惡意探索防護
Windows Defender Exploit Guard 是一組新的 Windows 10 主機入侵防護功能。 如需有關 Windows Defender 利用防護、基本需求以及如何管理此功能的詳細資訊，請參閱[Windows Defender 利用防護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)。

### <a name="deployment-management-and-configuration"></a>部署、管理及設定
若要部署、管理及設定 Windows Defender Exploit Guard 防護，請遵循以下的指導方針：
* [Exploit protection](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [攻擊面保護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [網路保護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [受控資料夾存取權](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

您可以使用一系列的評估主題，協助評估網路上 Windows Defender 利用防護的保護層級和影響。 這在建立初始設定或「快速入門手冊」時也很有用，主題和指引會定期更新，以提供最實用的建議來設定及啟用功能，以確保最大的保護。 如需詳細資訊，請[評估 Windows Defender 利用防護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard)。

### <a name="reporting"></a>Reporting
您可以使用設定工具（例如 Configuration Manager 或 Intune）取得報告。 您也可以在 SIEM 中使用 Windows 事件記錄檔，以取得報告。 如果您有 Microsoft Defender ATP 的授權，您也可以在 Windows Defender AV 偵測中取得報告，並執行基本修復。 如需詳細資訊，請參閱下列資源：
* [查看 Windows Defender 利用防護事件](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Microsoft Defender ATP 入口網站概述](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>疑難排解
您可以使用 Windows Defender 安全性情報提交系統執行基本疑難排解，或選擇性地提供 Microsoft with .cab 檔案，並提交問題（例如誤報）。 若要深入瞭解，請參閱[將問題提交至 Microsoft](https://www.microsoft.com/wdsi/filesubmission)。


<a name="windows10-sec-atp"></a>
## <a name="microsoft-defender-advanced-threat-protection"></a>Windows Defender 進階威脅防護
Microsoft Defender ATP 只適用于 Microsoft 365 E5 方案，它是一種安全性服務，可讓企業客戶偵測、調查和回應其網路上的高級威脅。 如需 Microsoft Defender ATP （最低需求）和您如何管理此功能的詳細資訊，請參閱：

* [Microsoft Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [基本需求](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>部署、管理及設定
若要部署 Microsoft Defender ATP，您必須確定您有適當的 Windows 授權。 確認您具有正確的授權後，您必須決定存放資料的位置地理位置。 之後，您就可以啟動將端點加入服務。

如需這些步驟的詳細資訊，請參閱下列主要主題： 

* [驗證授權布建和完整設定](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [資料儲存區與隱私權](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [板載端點和設定存取](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>偵測、調查、回應
成功將端點加入服務後，即可開始調查來自各種儀表板的警示。 當您已調查提醒之後，您可以對提醒採取回應動作。 

如需如何執行這些作業的詳細資訊，請參閱：
* [Microsoft Defender ATP 入口網站概述](https://go.microsoft.com/fwlink/?linkid=861596)
* [使用 Microsoft Defender ATP 入口網站](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [採取回應動作](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>與其他產品及工具整合
Microsoft Defender ATP 會整合及支援各種其他產品及工具，以擴充其安全性功能。 

如需工具及其他產品的詳細資訊，請參閱：
* [SIEM 工具](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [建立自訂警示](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [使用 APIs](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [組建 Power BI 報表](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>疑難排解
當您上架或使用產品時，可能會發生問題。 如需如何解決問題的詳細資訊，請參閱：
* [疑難排解上架問題](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [疑難排解 Microsoft Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>下一步

[Windows 10 企業版基礎結構出口準則](windows10-exit-criteria.md)
