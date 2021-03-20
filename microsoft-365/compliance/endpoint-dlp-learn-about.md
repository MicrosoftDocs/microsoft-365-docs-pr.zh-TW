---
title: 深入了解 Microsoft 365 端點資料外洩防護
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
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
description: 'Microsoft 365 端點資料外洩防護可擴充檔案活動的監視以及這些檔案到端點的保護動作。 在 Microsoft 365 合規性中心解決方案中可看到檔案 '
ms.openlocfilehash: d4a3fef03322912bf169cd195984a17d8dfe3b17
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907047"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a>深入了解 Microsoft 365 端點資料外洩防護

您可以使用 Microsoft 365 資料外洩防護（DLP）來監視正在進行的動作，這些動作會受到您認為敏感性的專案影響，並協助防止意外共用這些專案。 如需 DLP 的詳細資訊，請參閱[資料外洩防護概觀](data-loss-prevention-policies.md)。

**端點資料外洩防護** （端點 DLP）將 DLP 的活動監視和保護功能擴充到 Windows 10 裝置上的敏感性專案。 將裝置上架至 Microsoft 365 合規性解決方案之後，使用者對敏感度項目所進行動作的相關資訊會顯示在[活動總管](data-classification-activity-explorer.md)中，而且您可以透過 [DLP 原則](create-test-tune-dlp-policy.md)對這些項目強制執行保護動作。

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>您可以監視和採取動作的端點活動

Microsoft 端點 DLP 可讓您稽核及管理下列類型的活動，而使用者會在執行 Windows 10 的裝置上透過這些活動使用敏感度專案。 

|活動 |描述  | 可稽核的/可限制的|
|---------|---------|---------|
|上傳到雲端服務，或透過不允許的瀏覽器存取    | 使用者嘗試將項目上載到受限服務域或透過瀏覽器存取項目時偵測。  如果他們使用的瀏覽器在 DLP 中列為不允許使用的瀏覽器，則上載活動將被封鎖，使用者將被重新導向到使用Edge Chromium。 然後，Edge Chromium 將基於 DLP 原則設定允許或封鎖上載或存取         |可稽核與可限制|
|複製到其他應用程式    |使用者嘗試從受保護項目複製資訊，然後將其貼上到另一個應用程式、流程或項目中時偵測。 此活動不會偵測到在同一應用程式、流程或項目中複製和貼上資訊。         | 可稽核與可限制|
|複製到 USB 卸除式媒體 |使用者嘗試將項目或資訊複製到卸除式媒體或 USB 裝置時偵測。         | 可稽核與可限制|
|複製到網路共用    |使用者嘗試將項目複製到網路共用或對應的網路磁碟機時偵測         |可稽核與可限制|
|列印文件    |當使用者試圖將受保護的項目列印到本機或網路列印機時偵測。| 可稽核與可限制         |
|複製到遠端工作階段|偵測使用者何時嘗試將項目複製到遠端桌面工作階段 |  可稽核與可限制|
|複製到藍牙裝置|偵測使用者何時嘗試將項目複製到不允許的藍牙應用程式 (如端點 DLP 設定中不允許的藍牙應用程式清單中所定義)。| 可稽核與可限制|
|建立項目|當使用者建立項時偵測| 可稽核的|
|重新命名項目|當使用者重新命名項時偵測| 可稽核的|

 ## <a name="monitored-files"></a>受監視的檔案

端點 DLP 支援監視下列檔案類型：

- Word 檔案
- PowerPoint 檔案
- Excel 檔案
- PDF 檔案
- .csv 檔案
- .tsv 檔案
- .txt 檔案
- .rtf 檔案
- .c 檔案
- .class 檔案
- .cpp 檔案
- .cs 檔案
- .h 檔案
- .java 檔案
 
根據預設，端點 DLP 會稽核這些檔案類型的活動（即使沒有相符原則）。 如果您只想要從相符原則監控資料，您可以關閉端點 DLP 全域設定中的 **[一律稽核裝置的檔案活動]**。 無論如何，Word、PowerPoint、Excel、PDF 和 .csv 檔案中的相符活動都將一律受到稽核。

[端點 DLP] 可監視基於 MIME 類型的活動，因此即使副檔名變更，也能截取活動。 

## <a name="whats-different-in-endpoint-dlp"></a>端點 DLP 有何不同

在您深入了解端點 DLP 之前，您必須先注意一些額外的概念。

### <a name="enabling-device-management"></a>啟用裝置管理

[裝置管理] 是一種能夠從裝置收集遙測資訊，並將之引入 Microsoft 365 合規性中心解決方案，例如端點 DLP 和 [測試人員風險管理](insider-risk-management.md) 中的功能。 在 DLP 原則中，您需登入您想要用作位置的所有裝置。

> [!div class="mx-imgBorder"]
> ![啟用裝置管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

您可以從 [裝置管理中心] 下載的腳本處理「登入和登出」。 該中心含有下列每種部署方法的自訂腳本：

- 本機腳本（最多10台電腦）
- 群組原則
- 系統中心設定管理 (版本 1610 或更新版本)
- 行動裝置管理 / Microsoft Intune
- 非持久電腦的 VDI 登入腳本

> [!div class="mx-imgBorder"]
> ![裝置上線頁面](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 使用 [開始使用 Microsoft 365 端點 DLP](endpoint-dlp-getting-started.md) 的程式以登入程式。

如果您透過[適用於端點的 Microsoft Defender](/windows/security/threat-protection/) 上線裝置，這些裝置會自動顯示在裝置清單中。

> [!div class="mx-imgBorder"]
> ![受管理的裝置清單](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>查看端點 DLP 資料



您可以移至 [DLP 警示管理儀表板](dlp-configure-view-alerts-policies.md)，檢視與在端點裝置上強制執行的 DLP 原則相關的警示。

![警示資訊](../media/Alert-info-1.png)

您還可以在同一個儀表板中檢視具有豐富中繼資料的關聯事件的詳細資訊

![活動資訊](../media/Event-info-1.png)

當裝置登入時，在您設定並部署任何被裝置視為位置的 DLP 原則之前，稽核活動的相關資訊便會導入 [活動總管]。

> [!div class="mx-imgBorder"]
> ![活動總管中的端點 DLP 事件](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

在稽核活動中，端點 DLP 會收集大量資訊。

例如，如果將檔案複製到可移動 USB 媒體，您會在活動詳細資料中看到下列屬性：

- 活動類型
- 用戶端 IP
- 目標檔案路徑
- 時間戳記
- 檔案名稱
- 使用者
- 檔案副檔名
- 檔案大小
- 敏感資訊類型 (若適用)
- sha1 值
- sha256 值
- 上一個檔案名稱
- 位置
- 母
- 檔案路徑
- 來源位置類型
- 平台
- 裝置名稱
- 目的地位置類型
- 執行複製的應用程式
- 適用於端點的 Microsoft Defender 裝置識別碼 (如果適用)
- 可移除式媒體裝置製造商
- 可移除式裝置模型
- 可移除式裝置序號

> [!div class="mx-imgBorder"]
> ![複製到 usb 活動屬性](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a>後續步驟

現在您已經瞭解了端點 DLP，接下來的步驟如下：

1) [Microsoft 端點資料外洩防護快速入門](endpoint-dlp-getting-started.md)
2) [使用 Microsoft 端點資料外洩防護](endpoint-dlp-using.md)

## <a name="see-also"></a>另請參閱

- [Microsoft 端點資料外洩防護快速入門](endpoint-dlp-getting-started.md)
- [使用 Microsoft 端點資料外洩防護](endpoint-dlp-using.md)
- [資料外洩防護概觀](data-loss-prevention-policies.md)
- [建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)
- [開始使用活動總管](data-classification-activity-explorer.md)
- [適用於端點的 Microsoft Defender](/windows/security/threat-protection/)
- [測試人員風險管理](insider-risk-management.md)