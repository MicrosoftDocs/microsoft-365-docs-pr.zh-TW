---
title: 適用于 Office 365 之 Microsoft Defender 的高級搜尋範例
description: 使用高級搜尋開始搜尋電子郵件威脅
keywords: 高級搜尋，威脅搜尋，網路威脅搜尋，Microsoft 365 Defender，Microsoft 365，m365，search，query，遙測，自訂偵測，schema，kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965139"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>適用于 Office 365 之 Microsoft Defender 的高級搜尋範例

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender

想要開始使用進階搜捕來搜尋電子郵件威脅嗎？ 嘗試這樣做：

[適用於 Office 365 的 Microsoft Defender 文章](/microsoft-365/security/office-365-security/defender-for-office-365)的[快速入門](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started)小節包含的邏輯早期設定區塊，看起來像這樣：

1. 使用名稱中的「反」設定所有專案。
   - 反惡意程式碼
   - 反網路釣魚
   - 反垃圾郵件
2. 使用名稱中的 ' Safe ' 設定所有專案。
   - 安全連結
   - 安全附件
3. 保護工作負載 (例如: SharePoint線上、OneDrive 和 Teams) 。
4. 使用零小時自動清除加以保護。

還有可直接進入並在第 1 天便完成設定的[連結](../office-365-security/protect-against-threats.md)。

**快速入門** 的最後一個步驟會使用 **零時差自動清除** (也稱為 ZAP) 來保護使用者。 了解您對可疑或惡意郵件執行的 ZAP 在傳遞後是否成功非常重要。

快速瀏覽至 Kusto 查詢語言以搜捕問題，是這兩個安全性中心交集的優點。 安全小組 [可以在 [](https://security.microsoft.com/advanced-hunting)**搜尋** \> **高級搜尋**] 底下執行下一個步驟，以監視 ZAP 未命中。

1. 在 [高級搜尋] 頁面上，按一下 [ **查詢**]。
1. 將下列查詢複製到查詢視窗。
1. 選取 [ **執行查詢**]。

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="[高級搜尋] 頁面 ([搜尋) 上的 [搜尋] 面板上方已選取 [查詢]，並執行 Kusto 查詢，以在過去7天內捕獲 ZAP 動作。":::

來自此查詢的資料會顯示在查詢本身下方的結果面板中。 結果包含可自訂的結果集中的資訊，例如 'DeviceName'、'AccountDisplayName' 和 'ZapTime'。 也可以匯出結果做為記錄。 如果查詢是您所需要的，請再次選取 [儲存 **]**  >  [另存新檔 **]**，並將查詢新增至您的查詢、共用或社群查詢的清單中。

## <a name="related-information"></a>相關資訊
- [高級搜尋最佳作法](advanced-hunting-best-practices.md)
- [概覽-高級搜尋](advanced-hunting-overview.md)
