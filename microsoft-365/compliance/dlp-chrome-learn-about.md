---
title: 瞭解 Microsoft 合規性延伸模組 (預覽)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 合規性延伸模組會將監視並控制檔案活動和保護動作擴充至 Google Chrome 瀏覽器
ms.openlocfilehash: 38609b6920478085a28c7ec510bc5c9c4229543d
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826237"
---
# <a name="learn-about-the-microsoft-compliance-extension-preview"></a>瞭解 Microsoft 合規性延伸模組 (預覽)

[端點資料外洩防護 (端點 DLP)](endpoint-dlp-learn-about.md)將 [Microsoft 365 資料外洩防護 (DLP)](data-loss-prevention-policies.md) 的活動監視和保護功能擴充到 Windows 10 裝置上的敏感性項目。 將裝置上架至 Microsoft 365 合規性解決方案之後，使用者對敏感度項目所進行動作的相關資訊會顯示在[活動總管](data-classification-activity-explorer.md)中，而且您可以透過 [DLP 原則](create-test-tune-dlp-policy.md)對這些項目強制執行保護動作。

在 Windows 10 裝置上安裝 Microsoft 合規性延伸模組之後，組織就可以在使用者嘗試使用 Google Chrome 存取或上傳敏感性項目至雲端服務時加以監視，並透過 DLP 強制執行保護動作。  

## <a name="activities-you-can-monitor-and-take-action-on"></a>您可以監視和採取動作的活動

Microsoft 合規性延伸模組可讓您稽核及管理下列類型的活動，而使用者會在執行 Windows 10 的裝置上透過這些活動使用敏感度項目。

活動 |描述  | 支援的原則動作|
|---------|---------|---------|
|檔案已複製到雲端  | 當使用者嘗試透過 Chrome 瀏覽器將敏感性項目上傳到受限服務網域時偵測。 |稽核，封鎖|
|已列印檔案  |當使用者嘗試將 Chrome 瀏覽器中開啟的敏感性項目列印到本地或網路印表機時偵測 |稽核、透過複寫封鎖、封鎖|
|檔案已複製到剪貼簿 |當使用者嘗試從正於 Chrome 瀏覽器中查看的敏感性項目中複製資訊，然後將其貼上到另一個應用程式、流程或項目中時偵測。 |稽核、透過複寫封鎖、封鎖|
|檔案已複製到卸除式儲存空間    | 當使用者嘗試從 Chrome 瀏覽器中開啟的敏感性項目中的敏感性項目或資訊複製到卸除式媒體或 USB 裝置時偵測 |稽核、透過複寫封鎖、封鎖|
|檔案已複製到網路共用  |當使用者嘗試從 Chrome 瀏覽器中開啟的敏感性項目中的敏感性項目或資訊複製到網路共用或對應望露磁碟機時偵測。|稽核、透過複寫封鎖、封鎖 |

## <a name="deployment-process"></a>部署程序
1. [開始使用端點資料外洩防護](endpoint-dlp-getting-started.md)
2. [Windows 10 裝置的上線工具及方法](dlp-configure-endpoints.md)
3. [在 Windows 10 裝置上安裝擴充功能](dlp-chrome-get-started.md)
4. [建立或編輯 DLP 原則](create-test-tune-dlp-policy.md) 限制上傳到雲端服務，或以不允許的瀏覽器動作存取，並將其套用至您的 Windows 10 裝置

## <a name="next-steps"></a>後續步驟

請參閱 [Microsoft 合規性延伸模組](dlp-chrome-get-started.md) 以取得完整的部署程序和案例。

## <a name="see-also"></a>請參閱

- [開始使用 Microsoft 合規性延伸模組](dlp-chrome-get-started.md)
- [深入瞭解 Microsoft 365 端點資料外洩防護](endpoint-dlp-learn-about.md)
- [Microsoft 端點資料外洩防護快速入門](endpoint-dlp-getting-started.md)
- [使用 Microsoft 端點資料外洩防護](endpoint-dlp-using.md)
- [資料外洩防護概觀](data-loss-prevention-policies.md)
- [建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)
- [開始使用活動總管](data-classification-activity-explorer.md)
- [適用於端點的 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)
- [測試人員風險管理](insider-risk-management.md)
