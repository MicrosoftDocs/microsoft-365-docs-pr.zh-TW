---
title: 設定裝置探索
description: 瞭解如何使用基本或標準探索在 Microsoft 365 Defender 中設定裝置探索
keywords: basic，standard，configure endpoint discovery，裝置探索
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 7125a6953b9be46af9073b50c9268ce65dc0cd30
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339523"
---
# <a name="configure-device-discovery"></a>設定裝置探索

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

探索可以設定為 on standard 或 basic 模式。 使用標準選項可在您的網路中主動尋找裝置，這樣就能更好地保證端點的探索，並提供更豐富的裝置分類。 

您可以自訂用來執行標準探索的裝置清單。 您可以在所有也支援此功能的架裝置上啟用 standard discovery， (目前 Windows 10 裝置只) 或透過指定裝置的裝置標記來選取裝置的子集或子集。

> [!IMPORTANT]
> 預覽時，您必須先在 Microsoft 365 Defender 中開啟預覽功能。
> 然後，您可以在 Microsoft 365 的安全性中心存取裝置探索設定。 在 Microsoft 365 Defender 和 Microsoft 365 的安全性中心都有未管理裝置及安全性建議的清單，而儀表板磚只會 Microsoft 365 安全性中心提供。

在 Microsoft 365 的安全性中心採取下列設定步驟：

1. 流覽至 **設定 > 裝置探索**。
2. 選取要用於架裝置的探索模式。
3. 如果您已選擇使用標準探索，請選取要用於作用中探測的裝置： [所有裝置] 或 [子集]，方法是指定其裝置標記。
4. 按一下 **儲存**。

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>排除在標準探索中積極探測裝置

如果您的網路上有不應該主動掃描的裝置 (例如，使用另一種安全性工具的裝置做為 honeypots) 中，您也可以定義排除清單以避免掃描這些裝置。 請注意，使用基本探索模式仍可探索裝置。 將會被動探索這些裝置，但不會主動加以探測。 

## <a name="select-networks-to-monitor"></a>選取要監視的網路

 Microsoft Defender for Endpoint 會分析網路，並判斷其是否為需要監控的公司網路，或是可以忽略的非公司網路。 公司網路通常會選擇加以監視。 不過，您可以選擇監視未找到架裝置的非公司網路，以覆寫此決策。 

您可以指定要監視的網路，以設定可執行裝置探索的位置。 監視網路時，可對其執行設備探索。 

「 **受監視的網路** 」頁面中顯示可執行裝置探索的網路清單。 

> [!NOTE]
> 根據 [網路] 清單中提供的相關裝置的數目) ，只會 (前50網路。 

受監視網路的清單是根據在過去7天內網路上看到之裝置的總數排序。

您可以套用篩選器以查看下列任何網路探索狀態：

- **受監視的網路** -執行設備探索的網路。
- 已 **忽略的網路**-將會忽略此網路，而且不會在其上執行設備探索。
- 隨即會顯示 **所有** 受監視和忽略的網路。

### <a name="configure-the-network-monitor-state"></a>設定網路監視器狀態

您可以控制裝置探索發生的位置。 受監視的網路是指執行設備探索的地方，通常是公司網路。 您也可以選擇略過網路或在修改狀態後選取初始探索分類。

選擇初始探索分類意味著套用預設的系統建立網路監視器狀態。 選取預設的系統網路監視器狀態，表示系統會自動忽略已識別成公司的網路，並將其識別為非公司的網路。

1. 選取 [**設定 > 裝置探索**]。
2. 選取 [ **受監視的網路**]。
3. 查看網路清單。
4. 選取網路名稱旁邊的三個點。
5. 選擇您是否要監視、忽略或使用初始探索分類。

    > [!WARNING]
    >
    > - 選擇監視未由 Microsoft Defender for Endpoint 做為公司網路的網路，可導致公司網路以外的設備探索，因此可能會偵測到家用或其他非公司的裝置。
    > - 選擇 [略過網路] 會停止監控和搜尋該網路中的裝置。 已探索的裝置將不會從清查中移除，但將不再更新，而且將會保留詳細資料，直到 Endpoint for Endpoint 的資料保留期間到期為止。
    > - 在選擇監視非公司網路之前，您必須確定您有許可權執行該動作。

6. 確認您要進行變更。 

## <a name="explore-devices-in-the-network"></a>在網路中探索裝置

您可以使用下列高級搜尋查詢，取得 [網路] 清單中所述之每個網路名稱的詳細內容。 此查詢會列出過去7天內連線至特定網路的所有架裝置。

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| summarize arg_max(Timestamp, *) by DeviceId
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
```

## <a name="see-also"></a>另請參閱

- [裝置探索概觀](device-discovery.md)
- [裝置探索 FAQs](device-discovery-faq.md)
