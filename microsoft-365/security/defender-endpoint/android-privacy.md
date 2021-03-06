---
title: Android 上適用於端點的 Microsoft Defender - 隱私權資訊
description: 隱私權控制，如何設定會影響隱私權的原則設定，以及在 Android 的 Microsoft Defender for Endpoint 中所收集的診斷資料資訊。
keywords: microsoft、defender、Microsoft Defender for Endpoint、android、隱私權、診斷
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c72e9491303d3f14ddb184e6a302a518643f709d
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694338"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Android 上適用於端點的 Microsoft Defender - 隱私權資訊

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Android 上的 Defender for Android 會從您設定的 Android 裝置收集資訊，並將其儲存在您擁有 Defender for Endpoint 的相同承租人中。 收集的資訊可協助您保持 Android 的 Defender 安全、更新、如期執行，以及支援服務。

如需資料儲存區的詳細資訊，請參閱 [Microsoft Defender Endpoint data storage and 隱私權](data-storage-privacy.md)。

收集的資訊可協助您保持 Android 的 Defender 安全、更新、如期執行，以及支援服務。

如需 Android 和 iOS 行動裝置上有關 Microsoft Defender for Endpoint 的常見隱私權問題的詳細資訊，請參閱 [Microsoft defender For endpoint 和您在 android 上的隱私權和 iOS 行動裝置](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)。

## <a name="required-data"></a>必要資料 

必要的資料是由將 Defender 用於 Android 的端點工作如預期的情況所需的資料所組成。 此資料對於服務的運作很重要，而且可以包含與使用者、組織、裝置及應用程式相關的資料。 以下是所收集的資料類型清單：

### <a name="app-information"></a>應用程式資訊

裝置上 (APKs) 的 **惡意** Android 應用程式套件相關資訊，包括

-  安裝來源
-  APK (檔案路徑) 的儲存體位置
-  安裝時間，APK 和許可權的大小

### <a name="web-page--network-information"></a>網頁/網路資訊

- 僅當偵測到惡意的連線或網頁時，才會完成網站的完整 URL。
- 連接資訊
- 通訊協定類型 (例如 HTTP、HTTPS 等 ) 


### <a name="device-and-account-information"></a>裝置和帳戶資訊

- 裝置資訊，例如日期 & time、Android 版本、OEM 模型、CPU 資訊和裝置識別碼
- 裝置識別碼為下列其中一項：
    - Wi-Fi 配接器 MAC 位址
    - 在第一次啟動裝置時， (Android 所產生的[ANDROID ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID)) 
    - 隨機產生的全域唯一識別碼 (GUID) 

- 租使用者、裝置和使用者資訊
    -   Azure Active Directory (AD) 裝置識別碼和 Azure 使用者 ID: 分別在 Azure Active Directory 上唯一識別裝置，使用者。

    -   Azure 租使用者識別碼-識別您的組織 Azure Active Directory 內的 GUID

    -   Microsoft Defender for Endpoint org ID-與裝置所屬之企業相關聯的唯一識別碼。 可讓 Microsoft 識別問題是否會影響一組選擇的企業，以及受影響的企業數目 

    -   使用者主要名稱–使用者的電子郵件識別碼

### <a name="product-and-service-usage-data"></a>產品和服務使用方式資料

僅針對裝置上安裝的 Microsoft Defender for Endpoint 應用程式收集下列資訊。 

-   應用程式套件資訊，包括名稱、版本及應用程式升級狀態

-   在應用程式中執行的動作

-   威脅偵測資訊，例如威脅名稱、類別等。

-   Android 產生的崩潰報告記錄

## <a name="optional-data"></a>選用的資料

選用的資料包括診斷資料和意見資料。 選用的診斷資料為額外資料，可協助我們進行產品改善，並提供增強的資訊來協助我們偵測、診斷以及修正問題。 選用的診斷資料包括：

-   應用程式、CPU 及網路使用量

-   從應用程式視點裝置的狀態，包括掃描狀態、掃描計時、授與的應用程式許可權，以及升級狀態

-   由系統管理員設定的功能

-   裝置上瀏覽器的基本資訊

透過使用者提供的應用程式意見反應收集 **回饋資料**

-   使用者的電子郵件地址（如果使用者選擇提供）

-   意見反應類型 (微笑、frown、構思) 和使用者提交的任何意見反應批註。
