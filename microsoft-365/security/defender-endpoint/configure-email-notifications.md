---
title: 在 Microsoft Defender for Endpoint 中設定警示通知
description: 您可以使用 Microsoft Defender for Endpoint，根據嚴重性和其他準則，設定安全性警示的電子郵件通知設定。
keywords: 電子郵件通知，設定警示通知，Microsoft Defender for Endpoint，Microsoft defender for endpoint 通知，Microsoft Defender for Endpoint alert，windows 10 企業版，windows 10 教育版
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
ms.openlocfilehash: c60bed1fb2cc17c9f5dfbd1289ae5f5b5e13faec
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933946"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中設定警示通知

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

您可以將 Defender for Endpoint 設定為將電子郵件通知傳送給指定的收件者，以取得新的提醒。 這項功能可讓您找出會立即獲得通知的個人群組，並根據其嚴重性採取行動。

> [!NOTE]
> 只有具有「管理安全性設定」許可權的使用者才能設定電子郵件通知。 如果您已選擇使用基本版權管理，具有安全性管理員或全域系統管理員角色的使用者便可以設定電子郵件通知。

您可以設定觸發通知的警示嚴重性層級。 您也可以新增或移除電子郵件通知的收件者。 新增的收件者會在新增通知之後通知您。 如需提醒的詳細資訊，請參閱 [查看和組織警示佇列](alerts-queue.md)。

如果您是使用角色型存取控制 (RBAC) ，收件者只會根據通知規則中設定的裝置群組來接收通知。
具有適當許可權的使用者只能建立、編輯或刪除局限于其裝置群組管理範圍的通知。
只有指派給全域系統管理員角色的使用者才可以管理為所有裝置群組設定的通知規則。

電子郵件通知包含有關警示的基本資訊，以及可以進行進一步調查之入口網站的連結。


## <a name="create-rules-for-alert-notifications"></a>建立警示通知的規則
您可以建立規則來決定裝置及警示嚴重性，以傳送電子郵件通知及通知收件者。


1. 在功能窗格中，選取 [**設定**  >  **電子郵件通知**]。

2. 按一下 [ **新增專案**]。

3. 指定一般資訊：
    - **規則名稱** -指定通知規則的名稱。
    - **包含組織名稱** -指定電子郵件通知上顯示的客戶名稱。
    - **包含租使用者專用的入口網站連結** -新增具有租使用者識別碼的連結，以允許存取特定租使用者。
    - **包含裝置資訊** -包括電子郵件警示內文中的裝置名稱。
    
        >[!NOTE]
        > 此資訊可能會由收件者郵件伺服器處理，而不是在您為您的 Defender for Endpoint data 選取的地理位置中進行 ar。

    - **裝置** -選擇是否要將收件者的警示通知給收件者 (全域系統管理員角色只) 或選取的裝置群組。 如需詳細資訊，請參閱 [Create and manage device groups](machine-groups.md)。
    - **警示嚴重性** -選擇警示嚴重性層級。

4. 按 [下一步]。
    
5. 輸入收件者的電子郵件地址，然後按一下 [ **新增收件** 者]。 您可以新增多個電子郵件地址。

6. 選取 [ **傳送測試電子郵件**]，檢查電子郵件收件者是否可接收電子郵件通知。

7. 按一下 [ **儲存通知規則**]。

## <a name="edit-a-notification-rule"></a>編輯通知規則
1. 選取您想要編輯的通知規則。

2. 更新 [一般] 和 [收件者] 索引標籤資訊。

3. 按一下 [ **儲存通知規則**]。


## <a name="delete-notification-rule"></a>刪除通知規則

1. 選取您想要刪除的通知規則。

2. 按一下 [刪除]。


## <a name="troubleshoot-email-notifications-for-alerts"></a>疑難排解提醒電子郵件通知
本節列出使用提醒電子郵件通知時可能會遇到的各種問題。

**問題：** 「預定收件者」報告他們不會收到通知。

**解決方案：** 請確定電子郵件篩選器沒有封鎖通知：

1. 檢查 [Defender for Endpoint email] 通知是否未傳送至 [垃圾郵件] 資料夾。 將它們標示為非垃圾郵件。
2. 請檢查您的電子郵件安全性產品未阻止來自 Defender for Endpoint 的電子郵件通知。
3. 請檢查您的電子郵件應用程式規則，可能會為您的 Defender 寄出或移動您的 Defender 電子郵件通知。

## <a name="related-topics"></a>相關主題
- [更新資料保留設定](data-retention-settings.md)
- [設定進階功能](advanced-features.md)
