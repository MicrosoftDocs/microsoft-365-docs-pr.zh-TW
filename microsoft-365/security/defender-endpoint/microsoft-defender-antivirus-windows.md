---
title: Microsoft Defender 防毒軟體
description: 了解如何管理、設定和使用 Microsoft Defender 防毒軟體、內建防毒軟體和防毒保護。
keywords: Microsoft Defender 防毒軟體、Windows Defender、防毒軟體、SCEP、System Center Endpoint Protection、System Center Configuration Manager、病毒、惡意軟體、威脅、偵測、保護、安全性
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ceaf694d8b81e6b06ffe74efc4ad3d4d73471752
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322587"
---
# <a name="microsoft-defender-antivirus-in-windows"></a>Windows 中的 Microsoft Defender 防毒軟體

**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 防毒軟體是新一代適用於端點的 Microsoft Defender 的主要保護元件。 此保護結合機器學習、巨量資料分析、深度威脅抵禦研究和 Microsoft 雲端基礎結構來保護貴組織中的裝置 (或端點)。 Microsoft Defender 防毒軟體內建於 Windows，且可與適用於端點的 Microsoft Defender 一起運作，以在裝置和雲端提供保護。 

## <a name="compatibility-with-other-antivirus-products"></a>與其他防毒軟體產品的相容性

如果您在裝置上使用非 Microsoft 防毒軟體/反惡意程式碼軟體產品，您或許可以在被動模式中執行 Microsoft Defender 防毒軟體，以及非 Microsoft 防毒軟體解決方案。 這取決於您所使用的作業系統，以及您的裝置是否已加入適用於端點的 Microsoft Defender。 如需深入了解，請參閱 [Microsoft Defender 防毒軟體相容性](microsoft-defender-antivirus-compatibility.md)。

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a>比較主動模式、被動模式和停用模式

下表說明 Microsoft Defender 防毒軟體處於主動模式、被動模式或停用模式時預期的情況。

| 模式  | 發生的情況  |
|---------|---------|
| 主動模式 | 在主動模式中，Microsoft Defender 防毒軟體會做為裝置上的主要防毒軟體應用程式。 系統會掃描檔案、補救威脅，並將偵測到的威脅列在貴組織的安全性報告和 Windows 安全性應用程式中。 |
| 被動模式 | 在被動模式中，Microsoft Defender 防毒軟體不會做為裝置上的主要防毒軟體應用程式。 系統會掃描檔案並報告偵測到的威脅，但 Microsoft Defender 防毒軟體不會補救威脅。   |
| 已停用或已解除安裝  | 已停用或已解除安裝時，系統不會使用 Microsoft Defender 防毒軟體。 系統不會掃描檔案，而且不會補救威脅。 一般而言，我們不建議停用或解除安裝 Microsoft Defender 防毒軟體。  |

如需深入了解，請參閱 [Microsoft Defender 防毒軟體相容性](microsoft-defender-antivirus-compatibility.md)。

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a>檢查您裝置上的 Microsoft Defender 防毒軟體狀態

如果您想要檢查裝置上的 Microsoft Defender 防毒軟體狀態，您有數種方法可以使用，例如 Windows 安全性應用程式或 Windows PowerShell。

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a>使用 Windows 安全性應用程式檢查 Microsoft Defender 防毒軟體的狀態

1. 在 Windows 裝置上，選取開始功能表，然後開始輸入 `Security`。 然後在結果中開啟 Windows 安全性應用程式。

2. 選取 **[病毒與威脅防護]**。

3. 在 **[病毒與威脅防護]** 設定下方，選擇 **[管理提供者]**。

您可以在設定頁面上看到防毒軟體/反惡意程式碼軟體解決方案的名稱。

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a>使用 PowerShell 檢查 Microsoft Defender 防毒軟體的狀態

1. 選取開始功能表，然後開始輸入 `PowerShell`。 然後在結果中開啟 Windows PowerShell。

2. 輸入 `Get-MpComputerStatus`。

3. 在結果清單中，查看 **AMRunningMode** 資料列。

   - **標準** 表示 Microsoft Defender 防毒軟體正在以主動模式執行。
   - **被動模式** 表示 Microsoft Defender 防毒軟體執行中，但不是裝置上的主要防毒軟體/反惡意程式碼軟體產品。
   - **EDR 封鎖模式** 表示 Microsoft Defender 防毒軟體執行中，且適用於端點的 Microsoft Defender 中稱為「封鎖模式 EDR」的功能已啟用。 (請參閱[封鎖模式中的端點偵測和回應 (EDR)](edr-in-block-mode.md)。)
   - **SxS 被動模式** 表示 Microsoft Defender 防毒軟體正以被動模式與另一個防毒軟體/反惡意程式碼軟體產品一起執行，且您的裝置未加入適用於端點的 Microsoft Defender。 在此情況下，Microsoft Defender 防毒軟體使用有限的定期掃描。 若要深入了解，請參閱[在 Microsoft Defender 防毒軟體中使用有限的定期掃描](limited-periodic-scanning-microsoft-defender-antivirus.md)。

若要深入了解 Get-MpComputerStatus PowerShell Cmdlet，請參閱參考文章 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus)。

## <a name="get-your-antivirusantimalware-platform-updates"></a>取得您的防毒軟體和反惡意程式碼軟體平台更新

將 Microsoft Defender 防毒軟體或任何防毒軟體/反惡意程式碼軟體解決方案保持在最新狀態非常重要。 Microsoft 會發行定期更新，確保您的裝置擁有最新的技術，以防範新的惡意程式碼軟體和攻擊技術。 若要深入了解，請參閱[管理Microsoft Defender 防毒軟體更新及套用基準](manage-updates-baselines-microsoft-defender-antivirus.md)。 

## <a name="see-also"></a>另請參閱

- [Windows Server 上的 Microsoft Defender 防毒軟體](microsoft-defender-antivirus-on-windows-server.md)
- [Microsoft Defender 防毒軟體管理和設定](configuration-management-reference-microsoft-defender-antivirus.md)
- [評估 Microsoft Defender 防毒軟體保護](evaluate-microsoft-defender-antivirus.md)
