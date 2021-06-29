---
title: 報告及疑難排解 Microsoft Defender for Endpoint ASR 規則
description: 本主題說明如何報告及疑難排解 Microsoft Defender for Endpoint ASR 規則
keywords: 攻擊面減少規則，asr，hips，主機入侵防護系統，保護規則，反侵入，antiexploit，exploit，感染防護，microsoft defender for endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 65e3e8d1baef7ca4440824c9a262f0b5f696b657
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194742"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a>報告及疑難排解 Microsoft Defender 以取得 ATP ASR 規則

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft 365 的安全性中心是一個新的介面，可監控和管理跨您的 Microsoft identity、資料、裝置、應用程式和基礎結構的安全性。 其可讓您輕鬆檢視組織的安全性狀況、採取行動來設定裝置、使用者和應用程式，並取得可疑活動的警示。 Microsoft 365 安全性中心主要供安全性管理員和安全性作業小組更妥善地管理及保護其組織。 流覽 Microsoft 365 的安全性中心，網址為 https://security.microsoft.com 。
在 Microsoft 365 的安全性中心，我們為您提供了目前的 ASR 規則設定和房地產中的事件的完整外觀。 請注意，您的裝置必須架至 Microsoft Defender for Endpoint service 中，才可填入這些報告。
以下是「Microsoft 365 安全性中心」 (「**報告**  >  **裝置**  >  **攻擊面降低**) 」下的螢幕擷取畫面。 在裝置層級 **，從 [** **攻擊面減少規則** ] 窗格中選取 [設定]。 此時會顯示下列畫面，您可以在其中選取特定裝置，並檢查其個別的 ASR 規則設定。

:::image type="content" source="images/asrrulesnew.png" alt-text="ASR 規則畫面":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a>Microsoft Defender for Endpoint –高級搜尋

Microsoft Defender 端點最強大的功能之一是「高級搜尋」。 如果您不熟悉高級搜尋，請參閱 [使用高級搜尋主動搜尋威脅](advanced-hunting-overview.md)。

「高級搜尋」是以查詢為基礎的 (Kusto 查詢語言) 威脅搜尋工具，可讓您探索最多30天的已捕獲 (raw) 資料，該 Defender 的端點會從您的裝置收集。 透過「高級搜尋」，您可以主動檢查事件，以找出感興趣的指示器和實體。 對資料的靈活存取可協助對已知和潛在威脅進行無限制的搜尋。

透過「高級搜尋」，可以解壓縮 ASR 規則資訊、建立報告，以及取得指定之 ASR 規則 audit 或封鎖事件內容的詳細資訊。

在 Microsoft Defender 資訊安全中心的「高級搜尋」區段中，您可以從 [DeviceEvents] 表格中查詢 ASR 規則事件。 例如，下列的簡單查詢可以在過去30天內，以資料來源形式報告所有具有 ASR 規則的事件，並以 ActionType 計數來匯總這些事件，在此情況下，它會是 ASR 規則的實際 codename。

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="高級搜尋查詢":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="高級搜尋畫面":::

透過高級搜尋，您可以將查詢整形成您的喜好，這樣您就可以查看所發生的情形，不論您是想要尋找個別機器上的某個專案，還是想要從您的整個環境析取見解。

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>Microsoft Defender for Endpoint machine 時序表

「高級搜尋」（但範圍較窄）是「Microsoft Defender for Endpoint machine」時程表的替代方法。 您可以在過去六個月內，查看裝置的所有收集的事件，在 Microsoft Defender 資訊安全中心中，移至 [機器] 清單，選取指定的機器，然後按一下 [時程表] 索引標籤。

下圖是在指定的端點上，這些事件的時程表視圖的螢幕擷取畫面。  在此視圖中，您可以根據右側窗格中的任何事件群組來篩選事件清單。 您也可以啟用或停用已標記和詳細的事件，同時在歷史時程表中查看提醒及滾動。

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="microsoft defender 安全中心時程表":::

## <a name="how-to-troubleshoot-asr-rules"></a>如何疑難排解 ASR 規則？

第一個也是最直接的方式，就是在 Windows 裝置上進行檢查，啟用了哪些 ASR 規則 (及其設定) 使用 PowerShell Cmdlet。

以下是一些 Windows 提供的資訊來源，可疑難排解 ASR 規則的影響與運作。

### <a name="querying-which-rules-are-active"></a>查詢作用中的規則
判斷是否已啟用 ASR 規則的最簡單方法之一，也就是透過 PowerShell Cmdlet MpPreference。
以下為範例：

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="取得 mppreference 腳本":::

有多個啟用中的 ASR 規則，具有不同的已設定動作。

若要展開有關 ASR 規則的上述資訊，您可以使用 **AttackSurfaceReductionRules_Ids** 和/或 **AttackSurfaceReductionRules_Actions** 屬性。

範例：

*MPPreference |Select-Object-ExpandProperty * * AttackSurfaceReductionRules_Ids*

:::image type="content" source="images/getmpref-examplenew.png" alt-text="取得 mpreference 範例":::

以上會顯示所有 IDs，使其設定值不同于 0 (未設定) 的 ASR 規則。

接下來的步驟是列出每個規則所設定的實際動作 (區塊或審計) 。 

*MPPreference |Select-Object-ExpandProperty * * AttackSurfaceReductionRules_Actions*

:::image type="content" source="images/getmpref-example2new.png" alt-text="取得 mppreference example2":::

### <a name="querying-blocking-and-auditing-events"></a>查詢封鎖和審核事件
可在 Windows Defender 記錄中查看 ASR 規則事件。

若要存取它，請開啟 Windows 事件檢視器，並流覽至 **應用程式及服務記錄**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **運作**。

:::image type="content" source="images/eventviewerscrnew.png" alt-text="事件檢視器 scr":::

## <a name="microsoft-defender-malware-protection-logs"></a>Microsoft Defender 惡意程式碼保護記錄
您也可以透過可用於管理及設定的 Microsoft Defender 防毒軟體專用命令列工具（稱為）來查看規則事件， `*mpcmdrun.exe*` 並視需要自動化工作。

您可以在 *%ProgramFiles% \ Windows Defender\MpCmdRun.exe* 中找到此公用程式。 您必須從提升許可權的命令提示字元執行 (，也就是以系統管理員身分) 執行。

若要產生支援資訊，請輸入 *MpCmdRun.exe-getfiles*。 經過一段時間後，會將幾個記錄封裝到封存 (MpSupportFiles.cab) 並在 *C:\ProgramData\Microsoft\ Windows Defender \Support* 中提供。

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="惡意程式碼保護記錄":::

解壓縮該封存，您將有許多檔案可供疑難排解之用。

最相關的檔如下：

- **MPOperationalEvents.txt** -此檔案包含在事件檢視器中找到 Windows Defender 操作記錄檔的相同層級資訊。
- **MPRegistry.txt** –在此檔案中，您可以從捕獲支援記錄檔的時刻分析所有目前的 Windows Defender 設定。
- **MPLog.txt** –此記錄檔包含 Windows Defender 所有動作/作業的詳細資訊。
