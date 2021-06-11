---
title: 收集診斷資料以取得更新規範和 Windows Defender Microsoft Defender 防毒軟體
description: 使用工具收集資料，以在使用 Microsoft Defender 防毒軟體評估新增時，對更新規範問題進行疑難排解
keywords: 疑難排解，錯誤，修正，更新規範，oms，監視器，報表，Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 9fbe2b624bec6bbe17bcf6bc8d3f842ba1e43ad7
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903729"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-antivirus-assessment"></a>收集 Microsoft Defender 防毒軟體評估的更新規範診斷資料


**適用於：**

- [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

本文說明如何收集可供 Microsoft 支援人員和工程小組使用的診斷資料，以協助疑難排解在更新規範增益集中使用 Microsoft Defender 防毒軟體評估區段時可能遇到的問題。

嘗試此程式之前，請先確定您已閱讀「[疑難排解 Microsoft Defender 防毒軟體報告](troubleshoot-reporting.md)」、[符合所有需求的必要條件]，並採取任何其他建議的疑難排解步驟。

在至少兩部未報告或顯示更新規範的裝置上，採取下列步驟取得 .cab 診斷檔案：

1. 以下列方式開啟命令提示字元的系統管理員層級版本：
        
    a. 開啟 [ **開始** ] 功能表。

    b. 輸入 **cmd**。 在 **命令提示** 字元上按一下滑鼠右鍵，然後選取 [ **以系統管理員身分執行**]。

    c. 指定系統管理員認證或核准提示。
        
2. 流覽至 Windows Defender 目錄。 此為預設值 `C:\Program Files\Windows Defender` 。

3. 輸入下列命令，然後按 **enter**
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. 會產生包含各種診斷記錄的 .cab 檔案。 會在命令提示字元的輸出中指定檔案的位置。 根據預設，位置是 `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 。

5. 將這些 .cab 檔複製到可供 Microsoft 支援人員存取的位置。 例如，您可以將密碼保護的 OneDrive 資料夾與我們共用。

6. 使用 <a href="mailto:ucsupport@microsoft.com?subject=MDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">更新規範支援電子郵件範本</a>傳送電子郵件，並使用下列資訊填寫範本：
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>另請參閱

- [Windows Defender Microsoft Defender 防毒軟體報告疑難排解](troubleshoot-reporting.md)