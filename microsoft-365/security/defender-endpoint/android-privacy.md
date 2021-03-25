---
title: 適用于 Android 的 Microsoft Defender ATP-隱私權資訊
description: 隱私權控制，如何設定會影響隱私權的原則設定，以及 Microsoft Defender ATP for Android 中所收集診斷資料的相關資訊。
keywords: microsoft、defender、atp、android、隱私權、診斷
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
ms.openlocfilehash: abb22b2e733d1e40bd4f2733ef2d25767c69ccf7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163324"
---
#  <a name="microsoft-defender-for-endpoint-for-android---privacy-information"></a>適用于 Android 的 Microsoft Defender Endpoint-隱私權資訊

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


適用于 Android 的 defender for Android 會從您設定的 Android 裝置收集資訊，並將其儲存在您擁有 Defender for Endpoint 的相同承租人中。

收集的資訊可協助您保持 Android 的 Defender 安全、更新、如期執行，以及支援服務。

## <a name="required-data"></a>必要資料 

必要的資料是由將 Defender 用於 Android 的端點工作如預期的情況所需的資料所組成。 此資料對於服務的運作很重要，而且可以包含與使用者、組織、裝置及應用程式相關的資料。 以下是所收集的資料類型清單：

### <a name="app-information"></a>應用程式資訊

裝置上 (APKs) 的 Android 應用程式套件相關資訊，包括

-  安裝來源
-  APK 的儲存位置 (檔案路徑) 
-  安裝時間，APK 和許可權的大小

### <a name="web-page--network-information"></a>網頁/網路資訊

- 支援的瀏覽器) 上的完整 URL (，當按一下時）
- 連接資訊
- 通訊協定類型 (例如 HTTP、HTTPS 等 ) 


### <a name="device-and-account-information"></a>裝置和帳戶資訊

- 裝置資訊，例如日期 & time、Android 版本、OEM 模型、CPU 資訊和裝置識別碼
- 裝置識別碼為下列其中一項：
    - Wi-Fi 配接器 MAC 位址
    - 在第一次啟動裝置時， (Android 所產生的[ANDROID ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID)) 
    - 隨機產生的全域唯一識別碼 (GUID) 

- 租使用者、裝置和使用者資訊
    -   Azure Active Directory (AD) 裝置識別碼和 Azure 使用者 ID: 在 Azure Active Directory 上分別識別裝置，使用者。

    -   Azure 租使用者識別碼-識別您的組織在 Azure Active Directory 中的 GUID

    -   Microsoft Defender ATP org ID-與裝置所屬之企業相關聯的唯一識別碼。 可讓 Microsoft 識別問題是否會影響一組選擇的企業，以及受影響的企業數目 

    -   使用者主要名稱–使用者的電子郵件識別碼

### <a name="product-and-service-usage-data"></a>產品和服務使用方式資料
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
