---
title: 疑難排解 Linux 上 Microsoft Defender for Endpoint 的效能問題
description: 疑難排解 Linux 上的 Microsoft Defender for Endpoint 中的效能問題。
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，效能
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 998d8c500613ffa9fc6d790535e555ff9503f590
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281014"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a>疑難排解 Linux 上 Microsoft Defender for Endpoint 的效能問題

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

本文提供一些一般步驟，可用來縮小與在 Linux 上的 Defender for Endpoint 相關的效能問題。

[！注意] 即時保護 (RTP) 是一種適用于 Linux 上的端點的功能，可以持續監視和保護您的裝置免受威脅。 它包含檔案和程式監視及其他試探法。

根據您執行的應用程式和您的裝置特性，在 Linux 上執行 Defender for Endpoint 時，可能會體驗到最優效能。 特別是，在短時間記憶體取許多資源的應用程式或系統進程，可能會在 Linux 上的 Endpoint for Endpoint 中導致效能問題。

開始之前， **請確定目前沒有在裝置上執行其他安全性產品**。 多個安全性產品可能會衝突，並影響主機效能。

下列步驟可用於疑難排解及緩解下列問題：

1. 使用下列其中一種方法來停用即時保護，並觀察效能是否提高。 這種方法有助於縮小效能的 Defender 是否對效能問題產生影響。

    如果您的裝置不是由您的組織管理，可以從命令列停用即時保護：

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    如果您的裝置是由您的組織管理，您的系統管理員可以使用在 [Linux 上的 Defender For Endpoint 的 Set 偏好設定](linux-preferences.md)中的指示來停用即時保護。

    如果在即時保護關閉時出現效能問題，則問題的來源可能是端點偵測和回應元件。 在此情況下，請與客戶支援部門聯繫，以取得進一步的指示和緩解。

2. 若要尋找觸發大多數掃描的應用程式，您可以使用在 Linux 上的 Defender for Endpoint 所收集的即時統計資料。

    > [!NOTE]
    > 100.90.70 或更新版本中提供此功能。

    預設會在和頻道上啟用此 `Dogfood` 功能 `InsiderFast` 。 如果您是使用不同的更新通道，可以從命令列啟用此功能：
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    這項功能需要啟用即時保護。 若要檢查即時保護的狀態，請執行下列命令：

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    確認 `real_time_protection_enabled` 專案是 `true` 。 否則，請執行下列命令來啟用它：

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    若要收集目前的統計資料，請執行：

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > 使用 ```--output json``` (請注意雙破折號) 確保輸出格式準備好進行分析。

    這個命令的輸出會顯示所有程式及其相關聯的掃描活動。

3. 在您的 Linux 系統上，使用命令下載範例 Python 分析程式 **high_cpu_parser py** ：

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    此命令的輸出應類似下列所示：

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. 接下來，輸入下列命令：

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      以上的輸出是效能問題的最熱門貢獻因素清單。 第一欄是進程識別碼 (PID) ，第二欄是 te 進程名稱，最後一欄是依影響排序的掃描檔數目。
    例如，命令的輸出會如下所示： 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool     1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd    407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    若要提升 Linux 上的 Defender for Endpoint 的效能，請找出列在列下方的最大值 `Total files scanned` ，並為其新增排除。 如需詳細資訊，請參閱 [設定及驗證 Linux 上的 Defender For Endpoint 的排除](linux-exclusions.md)專案。

    >[!NOTE]
    > 應用程式會將統計資料儲存在記憶體中，且只會在啟動之後繼續追蹤檔活動，並啟用即時保護。 在即時保護關閉之前或期間所啟動的處理常式不會計算在內。 此外，只會計算觸發掃描的事件。

5. 針對影響效能問題及重新啟用即時保護的處理常式或磁片位置，設定 Linux 上的 Microsoft Defender for Endpoint with 排除專案。

    如需詳細資訊，請參閱[設定及驗證 Linux 上適用於端點的 Microsoft Defender 排除項目](linux-exclusions.md)。

## <a name="see-also"></a>另請參閱
- [調查代理程式健康狀況問題](health-status.md)