---
title: 使用網路保護來協助防止連線不良網站
description: 防止使用者存取已知的惡意和可疑網路位址，以保護您的網路
keywords: 網路保護、手段、惡意網站、ip、網域、網域
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b6b664d471e238e2feb1e1aedd100c1299fc5bbe
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844259"
---
# <a name="protect-your-network"></a>保護您的網路

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

網路保護可協助從網際網路型事件降低裝置的受攻擊面。 它可防止員工使用任何應用程式來存取可能在網際網路上主控網路釣魚詐騙、利用方式及其他惡意內容的危險網域。 網路保護會擴充[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)的範圍，以封鎖嘗試連線至低信譽來源的所有輸出 HTTP (s) 流量， (根據網域或主機名稱) 。

從 Windows 10 版本1709開始，Windows 支援網路保護。 在其他作業系統上尚不支援網路保護，但使用新 Microsoft Edge 以 Chromium 來支援 web 保護。 若要深入瞭解，請參閱 [Web 保護](web-protection-overview.md)。

網路保護將 [Web 保護](web-protection-overview.md) 的保護擴充至作業系統層級。 它提供與其他支援的瀏覽器和非瀏覽器應用程式 Edge 的 web 保護功能。 此外，網路保護也會在與 [端點偵測和回應](overview-endpoint-detection-response.md)搭配使用時，提供與封鎖 (IOCs) 遭到損害的可見度和封鎖。 例如，網路保護可與您的 [自訂指示器](manage-indicators.md)搭配運作。

如需如何啟用網路保護的詳細資訊，請參閱 [enable network protection](enable-network-protection.md)。 使用群組原則、PowerShell 或 MDM Csp 來啟用和管理網路中的網路保護。

> [!TIP]
> 請參閱 Microsoft Defender for Endpoint testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) ，以查看網路保護的運作方式。

網路保護適用于 [Microsoft Defender For Endpoint](microsoft-defender-endpoint.md)，可讓您在 [警示調查案例](investigate-alerts.md)中深入報告以利用保護事件和區塊。

當網路保護封鎖連線時，會從動作中心顯示通知。 您的安全性運作小組可以自訂您組織的詳細資料和連絡人資訊 [的通知](customize-attack-surface-reduction.md#customize-the-notification) 。 此外，您可以啟用和自訂個別攻擊面減少規則，以符合特定的監控技巧。

您也可以使用 [審計模式](audit-windows-defender.md) ，評估當組織啟用時，網路保護會如何影響您的組織。

## <a name="requirements"></a>需求

網路保護需要 Windows 10 專業版或 Enterprise，且 Microsoft Defender 防毒軟體即時保護。

| Windows 版本 | Microsoft Defender 防毒軟體 |
|:---|:---|
| Windows 10 版本1709或更新版本 <p>Windows伺服器1803或更新版本 | 必須啟用[即時保護](configure-real-time-protection-microsoft-defender-antivirus.md)和[雲端傳送保護](enable-cloud-protection-microsoft-defender-antivirus.md)Microsoft Defender 防毒軟體 |

在您啟用服務之後，您可能需要設定網路或防火牆，以允許服務和裝置之間的連線 (也稱為端點) 。  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>在 Microsoft Defender for Endpoint Security Center 中查看網路保護事件

Microsoft Defender for Endpoint 提供事件和區塊的詳細報告，成為其 [警示調查案例](investigate-alerts.md)的一部分。

您可以使用 [ [高級搜尋](advanced-hunting-overview.md)] 查詢 Microsoft Defender 的端點資料。 如果您使用的是「 [稽核模式](audit-windows-defender.md)」，您可以使用高級搜尋查看網路保護設定如何影響環境（如果已啟用）。

以下是範例查詢

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>在 Windows 事件檢視器中查看網路保護事件

您可以查看 Windows 事件記錄檔，以查看網路保護封鎖 (或審核) 對惡意 IP 或網域的存取權時所建立的事件：

1. [直接複製 XML](event-views.md)。

2. 選取 **[確定]**。

此程式會建立自訂視圖，篩選為只顯示下列與網路保護相關的事件：

| 事件識別碼 | 描述 |
|:---|:---|
| 5007 | 設定變更時的事件 |
| 1125 | 在稽核模式中觸發網路保護時的事件 |
| 1126 | 在封鎖模式中觸發網路保護時的事件 |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a>在多重會話 Windows 10 企業版執行 Windows 虛擬桌面的考慮

由於 Windows 10 企業版的多使用者性質，請牢記下列幾點：

1. 網路保護是全裝置的功能，無法以特定的使用者會話為目標。

2. Web 內容篩選原則也是裝置範圍。

3. 如果您需要區分使用者群組，請考慮建立個別的 Windows 虛擬桌面主機集區和指派。

4. 在執行之前，先在審計模式中測試網路保護，以評估其行為。 

5. 如果您有大量的使用者或大量的多使用者會話，請考慮調整部署的大小。

### <a name="alternative-option-for-network-protection"></a>網路保護的替代選項

若為 Windows 10 企業版多重會話1909和 up，使用於 Azure 上 Windows 虛擬桌面，可使用下列方法來啟用網路保護 Microsoft Edge：

1. 使用 [ [開啟網路保護](enable-network-protection.md) ]，然後依照指示套用原則。

2. 執行下列 PowerShell 命令： `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`

## <a name="network-protection-troubleshooting"></a>網路保護疑難排解

由於網路保護的執行環境，Microsoft 可能無法偵測到作業系統 proxy 設定。 在某些情況下，網路保護用戶端無法到達雲端服務。 若要解決連線問題，具有 E5 授權的客戶應設定下列其中一個 Defender 登錄機碼：

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a>相關文章

- [評估網路保護](evaluate-network-protection.md) |採取一種快速案例，示範該功能的運作方式，以及通常會建立什麼事件。

- [啟用網路保護](enable-network-protection.md) |使用群組原則、PowerShell 或 MDM Csp 來啟用和管理網路中的網路保護。
