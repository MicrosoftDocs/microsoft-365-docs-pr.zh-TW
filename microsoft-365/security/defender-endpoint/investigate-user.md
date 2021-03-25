---
title: 調查 Microsoft Defender ATP 中的使用者帳戶
description: 調查使用者帳戶在調查期間，是否有可能遭到破壞的認證或在關聯的使用者帳戶上轉動。
keywords: 調查、帳戶、使用者、使用者實體、警示、microsoft defender atp
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: e79e558a7d256c46178e91b89bff27bfa6893ce9
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186710"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a>調查 Microsoft Defender for Endpoint 中的使用者帳戶

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a>調查使用者帳戶實體

識別具有最活躍之警示的使用者帳戶， (在儀表板上顯示為「面臨危險的使用者」 ) 並調查可能已遭破壞之憑證的案例，或在調查警示或裝置以找出裝置與該使用者帳戶間可能的側面移動時，在相關聯的使用者帳戶上進行資料透視。

您可以在下列視圖中尋找使用者帳戶資訊：

- 儀表板
- 警示佇列
- 裝置詳細資料頁面

在這些視圖中可以使用可按一下的使用者帳戶連結，這樣將會帶您前往 [使用者帳戶詳細資料] 頁面，以顯示更多關於使用者帳戶的詳細資訊。

當您調查使用者帳戶實體時，您會看到：

- 使用者帳戶詳細資料、Azure 高級威脅防護 (Azure ATP) 警示，以及登入的裝置、角色、登入類型和其他詳細資料
- 事件和使用者裝置的概述
- 與此使用者相關的警示
- 在組織中觀測的 (裝置登入) 

![使用者帳戶實體詳細資料頁面的圖像](images/atp-user-details-view.png)

### <a name="user-details"></a>使用者詳細資料

左側的 **使用者詳細資料** 窗格提供使用者的相關資訊，例如相關的開啟的事件、作用中的警示、SAM 名稱、SID、Azure ATP 警示、使用者登入的裝置數目、角色和登入類型。 視您已啟用的整合功能而定，您將會看到其他詳細資料。 例如，如果您啟用商務用 Skype 整合，您就可以從入口網站聯繫使用者。 **AZURE atp alerts** 區段包含連結，會帶您前往 azure atp 頁面（如果您已啟用 azure atp 功能，且有與使用者相關的警示）。 Azure ATP 頁面將提供有關提醒的詳細資訊。

>[!NOTE]
>您需要啟用 Azure ATP 和 Defender for Endpoint 上的整合，才能使用此功能。 在 [Defender for Endpoint] 中，您可以在 [高級功能] 中啟用這項功能。 如需如何啟用高級功能的詳細資訊，請參閱 [開啟高級功能](advanced-features.md)。

組織中的「綜述」、「警示」和「觀察」是不同的索引標籤，可顯示使用者帳戶的各種屬性。

### <a name="overview"></a>概觀

[ **一覽表** ] 索引標籤會顯示事件詳細資料，以及使用者已登入的裝置清單。 您可以展開這些功能，以查看每個裝置的登入事件詳細資料。

### <a name="alerts"></a>警示

[ **警示** ] 索引標籤提供與使用者帳戶相關聯的警示清單。 此清單是篩選 [佇列](alerts-queue.md)的篩選視圖，顯示使用者內容是選取的使用者帳戶、偵測到最後一個活動的日期、警報的簡短描述、警報的嚴重性、警報的狀態、警報的狀態，以及指派警示的寄件者的相關警示。

### <a name="observed-in-organization"></a>組織中的觀測

[ **組織中的觀測** 專案] 索引標籤可讓您指定日期範圍，以查看已登入此使用者的裝置清單。這兩個裝置中，每個裝置的最常見和最少登入記錄的使用者帳戶，以及每個裝置上觀測的使用者總數。

在 [在組織中所看到的專案] 表格中選取專案會展開專案，並顯示裝置的詳細資訊。 直接選取專案內的連結會將您傳送至對應的頁面。

## <a name="search-for-specific-user-accounts"></a>搜尋特定的使用者帳戶

1. 從 **搜尋** 列下拉式功能表中選取 [**使用者**]。
2. 在 [ **搜尋** ] 欄位中輸入使用者帳戶。
3. 按一下搜尋圖示或按 **enter** 鍵。

會顯示符合查詢文字的使用者清單。 您將會看到使用者帳戶的網域和名稱、上次看到使用者帳戶時，以及過去30天內所看到之已登入的裝置總數。

您可以依下列時間週期篩選結果：

- 1 天
- 3天
- 7 天
- 30 天
- 6 個月

## <a name="related-topics"></a>相關主題

- [查看和組織 Microsoft Defender for Endpoint 警示佇列](alerts-queue.md)
- [管理 Microsoft Defender for Endpoint 警示](manage-alerts.md)
- [調查 Microsoft Defender for Endpoint 警示](investigate-alerts.md)
- [調查與 Defender for Endpoint alert 相關聯的檔案](investigate-files.md)
- [調查 [Defender for Endpoint Devices] 清單中的裝置](investigate-machines.md)
- [調查與 Defender for Endpoint alert 相關聯的 IP 位址](investigate-ip.md)
- [調查與 Defender for Endpoint alert 相關聯的網域](investigate-domain.md)
