---
title: 使用 Microsoft Defender for Endpoint 中的即時回應調查裝置上的實體
description: 使用安全的遠端命令介面連線存取裝置，以執行調查工作並即時立即對裝置採取回應動作。
keywords: remote，shell，connection，live，response，real，command，script，修正，搜尋，匯出，記錄，刪除，下載，檔案，
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d5e48f1e4f6bc2cfaa836d90e24f2ce8ba3f2114
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845327"
---
# <a name="investigate-entities-on-devices-using-live-response"></a>使用即時回應調查裝置上的實體

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Live response 讓安全性運作小組能夠暫態存取裝置 (也稱為) 使用遠端命令介面連線的電腦。 這可讓您在深入調查工作中做為您的力量，並立即採取回應動作，及時包含已識別的威脅（即時）。 

Live response 的設計目的是讓您的安全性作業小組收集法律資料、執行腳本、傳送可疑實體以進行分析、修正威脅，以及主動搜尋新興威脅，以加強調查。<br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

使用 live response 時，分析員可以執行下列所有工作：
- 執行基本和高級命令，在裝置上執行調查工作。
- 下載檔案，例如惡意程式碼範例和 PowerShell 腳本的結果。
- 在背景 (new！ ) 中下載檔案。
- Upload PowerShell 腳本或可執行檔至文件庫，並在租使用者層級上的裝置上執行該腳本。
- 採取或撤銷修正動作。

## <a name="before-you-begin"></a>開始之前

在裝置上啟動會話之前，請先確定您符合下列需求：

- **請確認您執行的是支援的 Windows 版本**。 <br/>
裝置必須執行下列其中一個 Windows 版本

  - **Windows 10**
    - [版本 1909](/windows/whats-new/whats-new-windows-10-version-1909) 或更新版本  
    - [版本 1903](/windows/whats-new/whats-new-windows-10-version-1903) 與 [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)
    - [版本 1809 (RS 5) ](/windows/whats-new/whats-new-windows-10-version-1809) 與 [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)
    - [版本 1803 (RS 4) ](/windows/whats-new/whats-new-windows-10-version-1803) 與 [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)
    - [版本 1709 (RS 3) ](/windows/whats-new/whats-new-windows-10-version-1709) 與 [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)
  
  - **Windows伺服器 2019-僅適用于公開預覽**
    - 版本1903或 (隨 [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) 更新版本 
    - 版本 1809 (，含 [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818)) 

- **從 [高級設定] 頁面啟用即時回應**。<br>
您必須啟用 [ [高級功能設定](advanced-features.md) ] 頁面中的 [即時回應] 功能。

    >[!NOTE]
    >只有具有「管理安全性」或「全域系統管理員」角色的使用者可以編輯這些設定。

- **從 [高級設定] 頁面啟用伺服器的即時回應** (建議) 。<br>

    >[!NOTE]
    >只有具有「管理安全性」或「全域系統管理員」角色的使用者可以編輯這些設定。
    
- **確定裝置具有指派的「自動化修正」層級**。<br>
您必須至少啟用特定裝置群組的最低修正層級。 否則，您將無法為該群組的成員建立即時回應會話。

    您會收到下列錯誤：

    ![錯誤訊息影像](images/live-response-error.png)

- **啟用 live response 未簽署的腳本執行** (選用) 。 <br>

    >[!WARNING]
    >允許使用未簽署的腳本可能會增加威脅的暴露程度。
 
  不建議執行未簽署的腳本，因為這樣可增加您對威脅的暴露程度。 如果您必須使用它們，但是您必須啟用 [ [高級功能設定](advanced-features.md) ] 頁面中的設定。
    
- **確定您具有適當的許可權**。<br>
    只有已使用適當許可權布建的使用者才能啟動會話。 如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。 

    > [!IMPORTANT]
    > 將檔案上傳至文件庫的選項只適用于具有適當 RBAC 許可權的選項。 只有委派許可權的使用者，此按鈕才會顯示為灰色。

    您可以執行基本或高級 live 回應命令，視授與您的角色而定。 使用者許可權是由 RBAC 自訂角色所控制。 

## <a name="live-response-dashboard-overview"></a>Live response 儀表板一覽
當您在裝置上啟動即時回應會話時，儀表板會開啟。 儀表板提供會話的相關資訊，如下所示： 

- 神秘建立會話
- 啟動會話時
- 會話的持續時間

儀表板也可讓您存取：
- 中斷連線會話
- Upload 檔案至文件庫 
- 命令主控台
- 命令記錄檔


## <a name="initiate-a-live-response-session-on-a-device"></a>在裝置上啟動即時回應會話 

1. 登入 Microsoft Defender 資訊安全中心。

2. 流覽至 [裝置] 清單頁面，然後選取要調查的裝置。 隨即會開啟 [裝置] 頁面。

3. 選取 [ **啟動即時回應會話**]，以啟動即時回應會話。 隨即會顯示命令主控台。 在會話連接至裝置時等候。

4. 使用內建的命令執行調查工作。 如需詳細資訊，請參閱 [Live response 命令](#live-response-commands)。

5. 完成調查後，請選取 **[中斷連線會話]**，然後選取 [ **確認**]。

## <a name="live-response-commands"></a>即時回應命令

您可以執行基本或高級 live 回應命令，視授與您的角色而定。 使用者權限是由 RBAC 自訂角色所控制。 如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。 


>[!NOTE]
>Live response 是雲端型互動命令介面，如此一來，特定的命令體驗可能會因回應時間而異，取決於使用者與目標裝置之間的網路品質和系統負載。

### <a name="basic-commands"></a>基本命令

下列命令適用于授與執行 **基本** live 回應命令之功能的使用者角色。 如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。 

| 命令 | 描述 |
|---|---|--- |
|`cd` | 變更目前的目錄。 | 
|`cls` | 清除主控台畫面。  |
|`connect` | 啟動裝置的即時回應會話。 |
|`connections` | 顯示所有使用中的連線。 |
|`dir` | 顯示目錄中的檔案及子目錄清單。 |
|`drivers` |  顯示裝置上安裝的所有驅動程式。 |
|`fg <command ID>` | 將指定的工作置於前臺，使其成為目前工作。 <br> 附注： fg 採用工作中提供的「命令識別碼」，而不是 PID |
|`fileinfo` | 取得檔案的相關資訊。 |
|`findfile` | 以指定的名稱在裝置上尋找檔案。 |
|`getfile <file_path>` | 下載檔案。 |
|`help` | 提供即時回應命令的説明資訊。 |
|`jobs` | 顯示目前執行中的工作、其識別碼和狀態。 |
|`persistence` | 顯示裝置上所有已知的持久性方法。 |
|`processes` | 顯示裝置上執行的所有進程。 |
|`registry` | 顯示登錄值。 |
|`scheduledtasks` | 顯示裝置上的所有排程任務。 |
|`services` | 顯示裝置上的所有服務。 |
|`trace` | 設定終端的記錄模式進行調試。 |

### <a name="advanced-commands"></a>Advanced 命令
下列命令適用于授與執行「 **高級** 即時回應」命令功能的使用者角色。 如需角色指派的詳細資訊，請參閱 [建立與管理角色](user-roles.md)。 

| 命令 | 描述 |
|---|---|
| `analyze` | 分析具有各種 incrimination 引擎的實體，以達到判定。 |
| `run` | 從裝置上的文件庫執行 PowerShell 腳本。 |
| `library` | 列出已上傳至 live response library 的檔案。 |
| `putfile` | 將檔案從文件庫放入裝置。 檔案儲存在工作資料夾中，而且會在預設重新開機裝置時刪除。 |
| `remediate` | 在裝置上 Remediates 實體。 修正動作會因實體類型而異：<br>-File： delete<br>-進程：停止、刪除影像檔<br>-服務：停止、刪除映射檔<br>-登錄專案：刪除<br>-排程任務：移除<br>-Startup 資料夾專案：刪除檔案 <br> 注意：此命令具有必要條件命令。 您可以搭配使用此 `-auto` 命令 `remediate` ，以自動執行必要條件命令。 
|`undo` | 還原已修正的實體。 |


## <a name="use-live-response-commands"></a>使用即時回應命令

您可以在主控台中使用的命令遵循與[Windows 命令](/windows-server/administration/windows-commands/windows-commands#BKMK_c)類似的原則。

Advanced 命令提供一組更為強大的動作，可讓您採取更強大的動作，例如下載和上傳檔案、在裝置上執行腳本，以及對實體採取修正動作。

### <a name="get-a-file-from-the-device"></a>從裝置取得檔案

例如，如果您想要從您正在調查的裝置取得檔案，您可以使用此 `getfile` 命令。 這可讓您儲存裝置中的檔案進行進一步調查。

>[!NOTE]
>適用下列檔案大小限制：
>- `getfile` 限制： 3 GB
>- `fileinfo` 限制： 10 GB
>- `library` 限制： 250 MB

### <a name="download-a-file-in-the-background"></a>下載背景中的檔案

若要讓您的安全性運作小組繼續調查受影響的裝置，現在可以在後臺下載檔案。

- 若要在後臺下載檔案，請在 live response 命令主控台中輸入 `download <file_path> &` 。
- 如果您正在等候下載檔案，您可以使用 Ctrl+Z 將檔案移至背景。
- 若要將檔案下載移至前臺，請在 live response 命令主控台中輸入 `fg <command_id>` 。

範例如下：


|命令  |功能  |
|---------|---------|
|`getfile "C:\windows\some_file.exe" &`     |開始在背景中下載名為 *some_file.exe* 的檔案。         |
|`fg 1234`     |會傳回具有命令識別碼 *1234* 至前景的下載。         |


### <a name="put-a-file-in-the-library"></a>將檔案放入文件庫中

Live response 具有可讓您存放盤案的文件庫。 文件庫儲存 (例如腳本) ，可在租使用者層級的即時回應會話中執行。

Live response 允許執行 PowerShell 腳本，但是您必須先將檔案放入文件庫中，才可執行這些檔案。 

您可以在用來啟動 live 回應會話的裝置上，使用可在其上執行的 PowerShell 腳本集合。 

#### <a name="to-upload-a-file-in-the-library"></a>上傳文件庫中的檔案

1. 按一下 [ **Upload 檔案至文件庫**]。 

2. 按一下 **[流覽]** 並選取檔案。

3. 提供簡短的描述。

4. 指定您是否要覆寫具有相同名稱的檔案。

5. 如果您想要的話，請知道腳本所需的參數，然後選取 [腳本參數] 核取方塊。 在 [文字] 欄位中，輸入範例和描述。

6. 按一下 [ **確認**]。 

7.  (選用) 若要確認已將檔案上傳至文件庫，請執行 `library` 命令。


### <a name="cancel-a-command"></a>取消命令
在會話期間，您可以隨時按 CTRL+C 取消命令。  

>[!WARNING]
>使用此快捷方式不會停止代理端中的命令。 它只會取消入口網站中的命令。 這樣一來，在取消變更時，"修正" 作業可能會繼續進行。 

## <a name="run-a-powershell-script"></a>執行 PowerShell 腳本 

在您可以執行 PowerShell 腳本之前，您必須先將其上傳至文件庫。 

將腳本上傳至文件庫之後，請使用 `run` 命令來執行腳本。

如果您想要在會話中使用未簽署的腳本，您必須啟用 [ [高級功能設定](advanced-features.md) ] 頁面中的設定。

>[!WARNING]
>允許使用未簽署的腳本可能會增加威脅的暴露程度。

## <a name="apply-command-parameters"></a>套用命令參數

- 若要瞭解命令參數的資訊，請參閱主控台説明。 若要瞭解個別命令，請執行：
 
    `help <command name>`

- 對命令套用參數時，請注意，參數的處理方式取決於固定順序：
 
    `<command name> param1 param2` 

- 指定固定順序以外的參數時，在提供值之前，請使用連字號指定參數的名稱：
 
    `<command name> -param2_name param2`

- 使用具有必要條件命令的命令時，您可以使用旗標：

    `<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto` 。

## <a name="supported-output-types"></a>支援的輸出類型

Live response 支援表格和 JSON 格式的輸出類型。 針對每個命令，都有預設的輸出行為。 您可以使用下列命令，修改您偏好輸出格式的輸出：

- `-output json`
- `-output table`

>[!NOTE]
>因為空間有限，所以表格格式會顯示較少的欄位。 若要查看輸出中的更多詳細資料，您可以使用 JSON 輸出命令，以顯示更多詳細資料。

## <a name="supported-output-pipes"></a>支援的輸出管道

Live response 支援將輸出管道傳送至 CLI 和檔案。 CLI 是預設的輸出行為。 您可以使用下列命令，將輸出輸送至檔案： [命令] > [filename] .txt。  

範例：

```console
processes > output.txt
```

## <a name="view-the-command-log"></a>查看命令記錄檔

選取 [ **命令記錄** ] 索引標籤，以查看在會話期間用於裝置的命令。 每個命令都會以完整的詳細資料來追蹤：
- ID
- 命令列
- 持續時間
- 狀態和輸入或輸出側條

## <a name="limitations"></a>限制

- Live 回應會話一次僅限25個即時回應會話。
- Live response session 非使用中超時值為30分鐘。 
- 使用者最多可以啟動10個同時會話。
- 一個裝置一次只能在一個會話中。
- 適用下列檔案大小限制：
   - `getfile` 限制： 3 GB
   - `fileinfo` 限制： 10 GB
   - `library` 限制： 250 MB

## <a name="related-article"></a>相關文章
- [即時回應命令範例](live-response-command-examples.md)
