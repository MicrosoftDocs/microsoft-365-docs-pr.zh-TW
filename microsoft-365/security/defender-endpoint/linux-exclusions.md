---
title: 在 Linux 上設定及驗證 Microsoft Defender for Endpoint 的排除專案
description: 在 Linux 上提供及驗證 Microsoft Defender for Endpoint 的排除專案。 您可以為檔案、資料夾及處理常式設定排除。
keywords: microsoft，defender，Microsoft Defender for Endpoint，linux，排除，掃描，防毒程式
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b55572509e9837f2858f96b01a13fbf259b2b770
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393784"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a>在 Linux 上設定及驗證 Microsoft Defender for Endpoint 的排除專案

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

本文提供有關如何定義適用于隨選掃描和即時保護和監控之排除的資訊。

> [!IMPORTANT]
> 本文中所述的排除項不適用於 Linux 功能上的其他 Defender for the endpoint，包括 (EDR) 的端點偵測和回應。 使用本文所述方法排除的檔案，仍然可以觸發 EDR 警示及其他偵測。

您可以從 Linux 掃描上的「Defender for Endpoint」排除某些檔案、資料夾、處理常式及處理常式開啟的檔案。

排除在您的組織中，避免對檔或軟體的錯誤偵測非常有用。 它們也可用於減輕由 Linux 上的 Defender for Endpoint 所導致的效能問題。

> [!WARNING]
> 定義排除項會降低在 Linux 上的 Defender for Endpoint 所提供的保護。 您應時刻評估與執行排除相關的風險，您應該只排除您確信不會惡意的檔案。

## <a name="supported-exclusion-types"></a>支援的排除類型

下表顯示在 Linux 上的 Defender for Endpoint 所支援的排除類型。

排除 | 定義 | 範例
---|---|---
副檔名 | 在裝置上的任何位置具有分機的所有檔案 | `.test`
檔案 | 完整路徑所識別的特定檔案 | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
資料夾 | 指定資料夾底下的所有檔案 (以遞迴方式)  | `/var/log/`<br/>`/var/*/`
流程 | 指定的程式 (會以完整路徑或檔案名指定，也可以是由它所開啟的所有檔案)  | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> 以上的路徑必須是硬連結，而不是符號連結，才可成功排除。 您可以執行，檢查路徑是否為符號連結 `file <path-name>` 。

檔案、資料夾及處理常式排除支援下列萬用字元：

萬用字元 | 描述 | 範例 | 比賽 | 不符合
---|---|---|---|---
\* |    符合任何數目的任何字元，包含無 (請注意，當路徑內使用此萬用字元時，它只會取代一個資料夾)  | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
? | 符合任何單一字元 | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a>如何設定排除清單

### <a name="from-the-management-console"></a>從管理主控台

如需如何設定 Puppet、Ansible 或其他管理主控台之排除專案的詳細資訊，請參閱 [設定 Linux 上的 Defender For Endpoint 的喜好設定](linux-preferences.md)。

### <a name="from-the-command-line"></a>從命令列

執行下列命令，以查看管理排除專案時可用的參數：

```bash
mdatp exclusion
```

> [!TIP]
> 設定包含萬用字元的排除時，請以雙引號括住參數，以防止內括弧。

範例：

- 新增副檔名的排除專案：

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- 為檔案新增排除專案：

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- 為資料夾新增排除專案：

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```


- 新增第二個資料夾的排除專案：

    ```bash
    mdatp exclusion folder add --path /var/log/
    mdatp exclusion folder add --path /other/folder
    ```
    ```Output
    Folder exclusion configured successfully
    ```


- 為包含萬用字元的資料夾新增排除專案：

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > 這只會排除 */var/* 下一個層級的路徑，但不會排除更深層嵌套的資料夾;例如， */var/this-subfolder/but-not-this-subfolder*。
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > 這將排除父級為 */var/* 的所有路徑;例如， */var/this-subfolder/and-this-subfolder-as-well*。

    ```Output
    Folder exclusion configured successfully
    ```

- 新增處理常式的排除專案：

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```


- 新增第二個處理常式的排除專案：

    ```bash
    mdatp exclusion process add --name cat
    mdatp exclusion process add --name dog
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>使用 EICAR.TXT 測試檔案驗證排除清單

您可以使用下載測試檔案，驗證您的排除清單是否運作正常 `curl` 。

在下列 Bash 程式碼片段中， `test.txt` 以符合您的排除規則的檔案加以取代。 例如，如果您已排除該 `.testing` 副檔名，請將其取代 `test.txt` `test.testing` 。 若要測試路徑，請確定您在該路徑中執行命令。

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

如果在 Linux 上的 Defender for Endpoint 報告為惡意程式碼，則規則不會正常運作。 如果沒有惡意程式碼的報表，而且下載的檔案存在，則排除作業正常運作。 您可以開啟檔案，確認內容與 [eicar.txt test file 網站](http://2016.eicar.org/86-0-Intended-use.html)上所述的內容相同。

如果您沒有網際網路存取權，可以建立您自己的 EICAR.TXT 測試檔案。 使用下列 Bash 命令，將 EICAR.TXT 字串寫入新的文字檔：

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

您也可以將字串複製到空白的文字檔中，並嘗試使用檔案名或您嘗試排除的資料夾來儲存。

## <a name="allow-threats"></a>允許威脅

除了排除特定內容的掃描之外，您也可以設定產品不要偵測威脅名稱)  (所識別的某些威脅類別。 使用此功能時，您應該小心謹慎，因為這會讓您的裝置保持不受保護。

若要將威脅名稱新增至允許的清單，請執行下列命令：

```bash
mdatp threat allowed add --name [threat-name]
```

您可以使用下列命令取得與裝置偵測相關聯的威脅名稱：

```bash
mdatp threat list
```

例如，若要將 `EICAR-Test-File (not a virus)` eicar.txt 偵測) 相關聯 (威脅名稱新增至允許清單，請執行下列命令：

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
