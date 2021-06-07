---
title: Microsoft Defender for Endpoint Flow connector
ms.reviewer: ''
description: 使用 Microsoft Defender for Endpoint Flow connector 來自動化安全性，並建立一個流程，每當租使用者發生新警示時，就會觸發此流程。
keywords: 流程、支援的 api、api、Microsoft flow、查詢、自動化
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: dd0cc3c2da134750f905b1f80746d6ec65cc70b2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769699"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a>Microsoft Power Automate (過去 Microsoft Flow) 和 Azure 函數

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


- 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

自動化的安全性程式是每一項新式安全性運作中心的標準需求。 缺乏專業的網路 defenders 強制 SOC 以最有效率的方式運作，而且自動化也是必須的。 Microsoft Power Automate 支援完全為該所建立的不同連接器。 您可以在數分鐘內建立端對端程式自動化。

Microsoft Defender API 具有許多功能的官方 Flow 連接器。

![編輯 credentials1 的影像](images/api-flow-0.png)

> [!NOTE]
> 如需有關高階 connector 授權必要條件的詳細資訊，請參閱 [優質連接器的授權](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)。


## <a name="usage-example"></a>使用範例

下列範例會示範如何建立在租使用者上發生新警示時所觸發的 Flow。

1. 登入[Microsoft Power Automate](https://flow.microsoft.com)。

2. 從空白移至 [**我的流程**]  >  （**新增**  >  **）**。

    ![編輯 credentials2 的影像](images/api-flow-1.png)

3. 選擇 Flow 的名稱，並搜尋「Microsoft Defender ATP 觸發器」做為觸發器，然後選取新的警示觸發。

    ![編輯 credentials3 的影像](images/api-flow-2.png)

現在，您已有 Flow 會在每次發生新警示時觸發。

![編輯 credentials4 的影像](images/api-flow-3.png)

您現在只需要選擇下一個步驟。
例如，您可以隔離裝置的嚴重性為高，並傳送與其相關的電子郵件時，您可以隔離裝置。
警示觸發器只會提供警示識別碼和電腦識別碼。 您可以使用連接器來展開這些實體。

### <a name="get-the-alert-entity-using-the-connector"></a>使用連接器取得警示實體

1. 為新步驟選擇 [ **Microsoft Defender ATP** ]。

2. 選擇 [ **警示-取得單一警示 API**]。

3. 設定最後一個步驟中的 **警示識別碼** 做為 **輸入**。

    ![編輯 credentials5 的影像](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>在警示嚴重性很高時隔離裝置

1. 將 **條件** 新增為新步驟。

2. 檢查警示嚴重性是否 **等於** High。

   如果是，請使用電腦識別碼及批註新增 **Microsoft Defender ATP 隔離的電腦** 動作。

    ![編輯 credentials6 的影像](images/api-flow-5.png)

3. 為有關預警和隔離的電子郵件新增步驟。 有多個可輕鬆使用的電子郵件連接器，例如 Outlook 或 Gmail。

4. 儲存您的流程。

您也可以建立執行高級搜尋查詢的 **排程** 流程，以及更多！

## <a name="related-topic"></a>相關主題
- [Microsoft Defender for Endpoint APIs](apis-intro.md)
