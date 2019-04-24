---
title: 部署 Windows 10 企業版安全性功能
description: 針對 Microsoft 365 企業版的一部分部署在電腦上的 Windows 10 企業版所需的步驟提供高階指導。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 文件、 Windows 10 企業版安全性
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: 60145444a7fb2b4ddf2ea6a3606e04aa04a578af
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291620"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>步驟 5： 部署 Windows 10 企業版安全性功能

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 提供保護企業使用者，停止 cyberthreats，並防止資料遺失的安全性功能。 

若要深入了解關於這些技術的詳細資訊，請參閱：
* [Identity protection](https://docs.microsoft.com/windows/security/identity-protection/) -了解 Windows Hello 企業版，Credential Guard 和存取控制。
* [威脅防護](https://docs.microsoft.com/windows/threat-protection/)-了解 Windows Defender 進階威脅防護，統一的平台預防性的保護、 後的資料外洩偵測、 自動化的調查及回應。
* [資訊保護](https://docs.microsoft.com/windows/security/information-protection/)– 了解 BitLocker、 Windows 資訊保護，以及其他 Windows 10 可協助保護企業資料的方式。 

此步驟顯示如何部署、 管理、 設定及疑難排解使用這些安全性功能：

* [Windows Defender 防毒軟體](#windows-defender-antivirus)
* [Windows Defender 惡意探索防護](#windows-defender-exploit-guard)
* [Windows Defender 進階威脅防護](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender 防毒軟體
Windows Defender 防毒軟體 (AV) 是內建於 Windows 10 的反惡意程式碼解決方案。 它提供安全性和反惡意程式碼管理的桌上型電腦、 可攜式電腦及伺服器。 如需更多有關 Windows Defender AV、 最小需求，以及如何管理這項功能的詳細資訊，請參閱 <<c0>在 Windows 10 和 Windows Server 2016 的 Windows Defender 防毒軟體。

如果您不使用 Windows Defender AV 做為您主要的防毒用戶端，或如果您同時使用 Windows Defender ATP，有一些考量必須列入考量。 若要深入了解，請參閱 < <b0>Windows Defender AV 相容性</b0>。

### <a name="deployment-and-management"></a>部署及管理
若要部署和管理 Windows Defender AV，請遵循此處的指導方針：

* [部署、 管理和 Windows Defender AV 報告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [管理及設定工具的參考主題](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>組態
使用者可以設定許多功能。 如需詳細資訊，請參閱下列資源：

* [設定 Windows Defender AV 功能](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [管理及設定工具的參考主題](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

若要協助您了解設定選項，請參閱此清單中的所有設定 （如其群組原則設定所定義）：[使用群組原則設定來設定和管理 Windows Defender AV](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

您可以使用[Windows Defender AV 保護評估指南](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus)可協助評估的保護層級與您網路上的 Windows Defender AV 影響。 這也相當有用或做為 '快速入門指南' 中建立的初始設定和定期更新，以提供最實用的建議設定並啟用功能，以確保最大保護。

### <a name="reporting"></a>報告
您可以取得報告使用的組態工具，例如 System Center Configuration Manager 或 Microsoft Intune。 您也可以取得報告中更新規範 (OMS) 或耗用您 SIEM 中的 Windows 事件記錄檔。 如果您有 Windows Defender ATP 授權，您也可以取得到 Windows Defender AV 偵測報告，並執行基本的補救措施。 如需詳細資訊，請參閱下列資源：
* [部署、 管理和 Windows Defender AV 報告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [在 Windows Defender AV 保護報告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Windows Defender ATP 入口網站 」 概觀](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>疑難排解
如需基本疑難排解錯誤和事件程式碼的資訊，請參閱[檢閱事件記錄檔和 Windows Defender AV 與問題進行疑難排解的錯誤碼](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)。

您也可以藉由使用 Windows Defender 安全性智慧提交系統提交問題 （例如，則為 false positive)。 若要深入了解，請參閱[提交給 Microsoft 的問題](https://www.microsoft.com/wdsi/filesubmission)。

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender 惡意探索防護
Windows Defender 惡意探索防護是一組新的適用於 Windows 10 的主機入侵防護功能。 如需有關 Windows Defender 惡意探索防護、 最小需求，以及如何管理這項功能的詳細資訊，請參閱 < <b0>Windows Defender 惡意探索防護</b0>。

### <a name="deployment-management-and-configuration"></a>部署、 管理和設定
若要部署、 管理和設定 Windows Defender 惡意探索防護，請遵循此處的指導方針：
* [利用保護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [攻擊面保護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [網路保護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [控制資料夾存取權](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

您可以使用一系列的評估主題可協助評估的保護層級與您網路上的 Windows Defender 惡意探索防護的影響。 這也是很有用或做為 '快速入門指南' 中建立的初始設定和指導方針與主題定期更新以便提供最實用的建議設定並啟用功能，以確保最大保護。 如需詳細資訊，[評估 Windows Defender 惡意探索防護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard)。

### <a name="reporting"></a>報告
您可以取得藉由設定工具，例如 System Center Configuration Manager 或 Intune 報告。 您也可以取得所耗用 Windows 事件記錄檔中您 SIEM 報告。 如果您有 Windows Defender ATP 授權，您也可以取得到 Windows Defender AV 偵測報告，並執行基本的補救措施。 如需詳細資訊，請參閱下列資源：
* [檢視 Windows Defender 惡意探索防護事件](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Windows Defender ATP 入口網站 」 概觀](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>疑難排解
您可以執行基本的疑難排解或選擇性地提供 Microsoft 的.cab 檔案和藉由使用 Windows Defender 安全性智慧提交系統提交問題 （例如，則為 false positive)。 若要深入了解，請參閱[提交給 Microsoft 的問題](https://www.microsoft.com/wdsi/filesubmission)。


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a>Windows Defender 進階威脅防護
Windows Defender ATP，只能使用 Microsoft 365 企業版 E5 方案中，是一種安全性服務，可讓企業客戶偵測、 調查及回應進階威脅其網路上。 如需有關 Windows Defender ATP、 最小需求，以及如何管理這項功能的詳細資訊，請參閱：

* [Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [基本需求](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>部署、 管理和設定
若要將 Windows Defender ATP 的部署，您需要確定您有權 Windows 授權。 確認您具有正確的授權之後, 您需要決定 geolocation 用於儲存您的資料。 之後，您可以開始上架至服務的端點。

如需這些步驟的詳細資訊，請參閱下列主要的主題： 

* [驗證授權佈建和設定完成設定](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [資料儲存區與隱私](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [上架端點和安裝程式存取](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>偵測、 調查、 回應
在服務的成功上架端點之後, 便可以開始調查從各種儀表板的提醒。 一旦您已調查提醒，您可以執行提醒回應動作。 

如需如何執行這些動作的詳細資訊，請參閱：
* [Windows Defender ATP 入口網站 」 概觀](https://go.microsoft.com/fwlink/?linkid=861596)
* [使用 Windows Defender ATP 入口網站](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [採取回應動作](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>整合其他產品及工具
Windows Defender ATP 整合，並支援各種其他產品及工具，以擴充其安全性功能。 

如需工具和其他產品的詳細資訊，請參閱：
* [SIEM 工具](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [建立自訂的提醒](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [使用 Api](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [建置 Power BI 報表](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>疑難排解
您可能會遇到問題時上架或使用產品時。 如需如何解決問題的詳細資訊，請參閱：
* [上架問題的疑難排解](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [疑難排解 Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>下一步

[Windows 10 企業版基礎結構允出準則](windows10-exit-criteria.md)
