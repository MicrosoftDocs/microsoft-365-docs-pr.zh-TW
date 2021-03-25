---
title: 疑難排解攻擊面減少規則的問題
description: 用於疑難排解 Microsoft Defender for Endpoint 中的攻擊面降低規則問題的資源和範例程式碼。
keywords: 疑難排解，錯誤，修正，windows defender 例如，asr，rules，hips，疑難排解，審核，排除，錯誤正值，已中斷，封鎖，microsoft defender for endpoint，microsoft defender 高級威脅防護
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: d483c098f221e2d4d2e61a10393154b8f5d1498d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198738"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>疑難排解攻擊面降低規則

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


當您使用 [攻擊面降減規則](attack-surface-reduction.md) 時，您可能會遇到問題，例如：

- 規則會封鎖檔案、處理常式或執行某些其他的動作，但不應 (false 正值) 

- 規則不會如所述那樣運作，也不會封鎖檔案或處理應該 (false 的處理常式) 

疑難排解這些問題有四個步驟：

1. [確認必要條件](#confirm-prerequisites)

2. [使用稽核模式來測試規則](#use-audit-mode-to-test-the-rule)

3. 針對誤報) [新增指定之規則](#add-exclusions-for-a-false-positive) (的排除

4. [提交支援記錄檔](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>確認必要條件

攻擊面減少規則只會在裝置上運作，但有下列情況：

- 端點正在執行 Windows 10 企業版，版本 1709 (也稱為「秋季建立者更新) 。

- 端點使用 Microsoft Defender 防病毒作為獨立的防防毒保護應用程式。 [使用任何其他防病毒應用程式會使 Microsoft DEFENDER AV 自行自行停用](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。

- 已啟用[即時保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)。

- 未啟用稽核模式。 使用群組原則將規則設定為 **停用** (值： **0**) 如 [啟用攻擊面降低規則](enable-attack-surface-reduction.md)中所述。

如果已符合這些必要條件，請繼續進行下一個步驟，以審計模式測試規則。

## <a name="use-audit-mode-to-test-the-rule"></a>使用稽核模式來測試規則

您可以在 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 流覽 Windows Defender Test 基礎網站，以確認攻擊面降低規則一般會在裝置上預先設定的案例和程式中運作，也可以使用審計模式，啟用僅限報告的規則。

請遵循下列指示， [使用示範工具來查看攻擊面降低規則的運作方式](evaluate-attack-surface-reduction.md) ，以測試您所遇到之問題的特定規則。

1. 針對您想要測試的特定規則，啟用稽核模式。 使用群組原則將規則設定為「 **稽核模式** 」 (值： **2**) 如 [啟用攻擊面降低規則](enable-attack-surface-reduction.md)中所述。 稽核模式允許規則報告檔或程式，但仍允許它執行。

2. 執行導致問題的活動 (例如，開啟或執行應該封鎖但允許的檔案或處理常式) 。

3. [檢查攻擊面減少規則事件記錄](attack-surface-reduction.md) 檔，以查看規則是否會封鎖檔或處理常式（如果規則已設定為 **啟用**）。

如果規則未封鎖您預期會封鎖的檔案或進程，請先檢查是否已啟用稽核模式。

已啟用稽核模式，以測試另一個功能，或透過自動化的 PowerShell 腳本，在測試完成後可能尚未停用。

如果您已使用示範工具和審計模式來測試規則，而攻擊面降低規則正在處理預先設定的案例，但是規則未如預期運作，請根據您的情況繼續執行下列其中一節：

1. 如果攻擊面降減規則封鎖不應該封鎖的專案 (又稱為誤報) ，您可以 [先新增攻擊面降減規則排除](#add-exclusions-for-a-false-positive)。

2. 如果攻擊面降低規則不會封鎖應該封鎖 (又稱為誤報) 的專案，則可以立即繼續進行最後一個步驟， [收集診斷資料並將問題提交給我們](#collect-diagnostic-data-for-file-submissions)。

## <a name="add-exclusions-for-a-false-positive"></a>新增誤報的排除

如果攻擊面降減規則封鎖不應該封鎖的專案 (也稱為誤報) ，您可以新增排除專案，以防止攻擊面不足規則評估排除的檔案或資料夾。

若要新增排除，請參閱 [自訂攻擊面降減](customize-attack-surface-reduction.md)。

>[!IMPORTANT]
>您可以指定要排除的個別檔案和資料夾，但不能指定個別規則。
>這表示排除的任何檔案或資料夾都會從所有 ASR 規則中排除。

## <a name="report-a-false-positive-or-false-negative"></a>報告誤報或 false 負數

使用 [Windows Defender 安全性情報 web 型提交表單](https://www.microsoft.com/wdsi/filesubmission) ，針對網路保護報告虛假的負數或假正值。 使用 Windows E5 訂閱，您也可以 [提供任何相關聯警示的連結](alerts-queue.md)。

## <a name="collect-diagnostic-data-for-file-submissions"></a>收集診斷資料以取得檔提交

當您報告攻擊面減少規則的問題時，系統會要求您收集並提交可供 Microsoft 支援人員和工程團隊使用的診斷資料，以協助疑難排解問題。

1. 開啟提升許可權的命令提示字元，並變更為 Windows Defender 目錄：

   ```console
   cd "c:\program files\windows defender"
   ```

2. 執行下列命令以產生診斷記錄：

   ```console
   mpcmdrun -getfiles
   ```

3. 根據預設，會將其儲存至 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 。 將檔案附加到提交表單。

## <a name="related-articles"></a>相關文章

- [受攻擊面縮小規則](attack-surface-reduction.md)

- [啟用攻擊面減少規則](enable-attack-surface-reduction.md)

- [評估攻擊面減少規則](evaluate-attack-surface-reduction.md)
