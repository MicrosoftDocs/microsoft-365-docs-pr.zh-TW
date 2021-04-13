---
title: 收集 Microsoft Defender 防病毒的診斷資料
description: 使用工具收集資料，以疑難排解 Microsoft Defender 防毒程式
keywords: 疑難排解，錯誤，修正，更新規範，oms，監視器，報表，Microsoft Defender av，群組原則物件，設定，診斷資料
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/29/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b7c07bace86a2a4651e5c951c6e0b7d954f0982
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690129"
---
# <a name="collect-microsoft-defender-av-diagnostic-data"></a>收集 Microsoft Defender AV 診斷資料

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

本文說明如何收集可供 Microsoft 支援人員和工程團隊使用的診斷資料，以協助疑難排解使用 Microsoft Defender AV 時可能遇到的問題。

> [!NOTE]
> 作為調查或回應程式的一部分，您可以從裝置收集調查套件。 方法如下： [從裝置收集調查套件](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)。

在至少有兩個裝置出現相同問題時，請採取下列步驟取得 .cab 診斷檔案：

1. 以下列方式開啟命令提示字元的系統管理員層級版本：

    a. 開啟 [ **開始** ] 功能表。

    b. 輸入 **cmd**。 在 **命令提示** 字元上按一下滑鼠右鍵，然後按一下 [以 **系統管理員身分執行**]。

    c. 輸入系統管理員認證或核准提示。

2. 流覽至 Microsoft Defender 目錄。 此為預設值 `C:\Program Files\Windows Defender` 。

> [!NOTE]
> 如果您正在執行 [更新的 Microsoft Defender 平臺版本](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)，請 `MpCmdRun` 從下列位置執行： `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` 。

3. 輸入下列命令，然後按 **enter**  

    ```Dos
    mpcmdrun.exe -GetFiles
    ```
  
4. 會產生包含各種診斷記錄的 .cab 檔案。 會在命令提示字元的輸出中指定檔案的位置。 根據預設，位置是 `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` 。

> [!NOTE]
> 若要將 cab 檔重新導向至不同的路徑或 UNC 共用，請使用下列命令： `mpcmdrun.exe -GetFiles -SupportLogLocation <path>`  <br/>如需詳細資訊，請參閱 [將診斷資料重新導向至 UNC 共用](#redirect-diagnostic-data-to-a-unc-share)。

5. 將這些 .cab 檔案複製到可供 Microsoft 支援人員存取的位置。 例如，您可以將密碼保護的 OneDrive 資料夾與我們共用。

> [!NOTE]
>如果您有更新規範的問題，請使用 <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">更新規範支援電子郵件範本</a>傳送電子郵件，並使用下列資訊填寫範本：
>```
> I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
> I have provided at least 2 support .cab files at the following location:  
> <accessible share, including access details such as password>
>
>    My OMS workspace ID is:
>
>    Please contact me at:

## <a name="redirect-diagnostic-data-to-a-unc-share"></a>將診斷資料重新導向至 UNC 共用
若要在中央存放庫上收集診斷資料，您可以指定 SupportLogLocation 參數。

```Dos
mpcmdrun.exe -GetFiles -SupportLogLocation <path>
```

將診斷資料複製到指定的路徑。 如果未指定路徑，則診斷資料會複製到支援記錄檔位置設定所指定的位置。

使用 SupportLogLocation 參數時，會在目的地路徑中建立類似下列的資料夾結構：

```Dos
<path>\<MMDD>\MpSupport-<hostname>-<HHMM>.cab
```

| 欄位  | 描述   |
|:----|:----|
| 路徑 | 命令列上指定的路徑，或從設定中檢索
| MMDD | 收集診斷資料的月和日 (例如，0530) 
| 主機 名 | 收集診斷資料之裝置的主機名稱
| HHMM | 收集診斷資料的時數和分鐘 (例如，1422) 

> [!NOTE]
> 使用檔案共用時，請確定用來收集診斷套件的帳戶具有共用的寫入存取權。  

## <a name="specify-location-where-diagnostic-data-is-created"></a>指定診斷資料的建立位置

您也可以使用群組原則物件 (GPO) ，指定要建立的診斷 .cab 檔案的位置。 

1. 開啟本機組策略編輯器，並在下列位置找到 SupportLogLocation GPO： `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\SupportLogLocation`
   
1. 選取 **[定義目錄路徑]，以複製支援記錄** 檔。

    ![本機組策略編輯器的螢幕擷取畫面](images/GPO1-SupportLogLocationDefender.png)  
        
     ![[定義記錄檔的路徑] 設定的螢幕擷取畫面](images/GPO2-SupportLogLocationGPPage.png)  
3. 在原則編輯器內，選取 [ **已啟用**]。
       
4. 在 [ **選項** ] 欄位中，指定您要將支援記錄檔複製到其中的目錄路徑。
     ![已啟用目錄路徑自訂設定的螢幕擷取畫面](images/GPO3-SupportLogLocationGPPageEnabledExample.png) 
5. 選取 **[確定]** **或**[套用]。

## <a name="see-also"></a>另請參閱

- [疑難排解 Microsoft Defender 防病毒報告](troubleshoot-reporting.md)