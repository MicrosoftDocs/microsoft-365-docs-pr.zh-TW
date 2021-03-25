---
title: 管理 Microsoft Defender for Endpoint 警示
description: 變更警示的狀態、建立抑制規則，以隱藏提醒、提交批註，以及使用「管理警示」功能表查看個別警示的變更歷程記錄。
keywords: 管理提醒、管理、警示、狀態、新、進行中、已解決、解決警告、抑制、supression、規則、內容、記錄、批註、變更
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
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186998"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a>管理 Microsoft Defender for Endpoint 警示

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

Defender for Endpoint 會透過提醒通知您可能的惡意事件、屬性和內容資訊。 [ **安全性作業] 儀表板** 會顯示新警示的摘要，您可以在 [ **警示] 佇列** 中存取所有警示。

您可以在 [ **警示] 佇列** 中選取警示，或個別裝置之 [裝置] 頁面的 [ **警示** ] 索引標籤，以管理提醒。

在其中一個位置選取警示會顯示 **警示管理窗格**。

![警示管理窗格和警示佇列的影像](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a>連結至另一個事件
您可以從警示中建立新的事件，或從現有的事件連結。 

## <a name="assign-alerts"></a>指派提醒
若尚未指派警示，您可以選取 [ **指派給我** ] 指派提醒給您自己。


## <a name="suppress-alerts"></a>抑制提醒
在某些情況下，您可能需要抑制 Microsoft Defender Security Center 中顯示的提醒。 Defender for Endpoint 可讓您針對已知的特殊警示（如組織中的已知工具或處理常式），建立抑制規則。

抑制規則可以從現有的警示建立。 您可以視需要停用或重新啟用。

在建立抑制規則時，它會從建立規則的點生效。 在建立規則之前，規則不會影響佇列中已存在的警示。 規則只會在建立規則之後，于符合條件設定的警示上套用。

抑制規則有兩個內容可供您選擇：

- **抑制此裝置上的警示**
- **抑制組織中的警示**

規則的內容可讓您定制入口網站中所呈現的內容，並確保只會將實際的安全性警示放入入口網站中。

您可以使用下表中的範例，協助您選擇抑制規則的內容：

| **Context**                           | **定義**                                                                                                                                              | **範例案例**                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **抑制此裝置上的警示**    | 只有在該特定裝置上具有相同警示標題及的警示，才會遭到抑制。 <br /><br />將不會抑制該裝置上的所有其他警示。 | <ul><li>安全性研究人員正在調查已用來攻擊組織中其他裝置的惡意腳本。</li><li>開發人員定期為小組建立 PowerShell 腳本。</li></ul> |
| **抑制組織中的警示** | 任何裝置上具有相同警示標題的警示都會遭到抑制。                                                                                         | <ul><li>您組織中的每個人都會使用良性系統管理工具。</li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a>抑制警示並建立新的抑制規則：
建立自訂規則，以控制何時抑制或解決警告。 您可以指定警示標題、安全指示器及條件，以控制抑制警示的上下文。 在指定內容之後，您可以設定警示的動作和範圍。 

1. 選取您想要隱藏的警示。 這會顯示 **警示管理** 窗格。

2.  選取 [ **建立抑制規則**]。

    您可以使用這些屬性建立抑制條件。 每個條件間都會套用一個 AND 運算子，所以只有在符合所有條件時，才會發生抑制。
    
    * 檔 SHA1
    * 檔案名-支援萬用字元
    * 資料夾路徑-支援萬用字元
    * IP 位址
    * URL-支援萬用字元
    * 命令列-支援萬用字元

3. 選取 **觸發 IOC**。
    
4. 指定警示的動作和範圍。 <br>
   您可以自動解決或隱藏來自入口網站的警示。 自動解決的警示將會出現在 [警示佇列]、[警示] 頁面及裝置時程表的 [已解析] 區段中，且會在每個 Defender for Endpoint APIs 中顯示為 [已解決]。 <br><br> 標記為隱藏的警示會從整個系統中抑制，這兩者位於裝置相關聯的警示上，以及來自于儀表板，而且不會在每個 Defender 進行端點 APIs 之間流動。


5. 輸入規則名稱和批註。

6. 按一下 **[儲存]**。

#### <a name="view-the-list-of-suppression-rules"></a>查看隱藏規則清單

1. 在功能窗格中，選取 [**設定**  >  **警示抑制**]。

2. 抑制規則清單會顯示組織中使用者所建立的所有規則。

如需管理抑制規則的相關資訊，請參閱 [Manage 抑制規則](manage-suppression-rules.md)

## <a name="change-the-status-of-an-alert"></a>變更警示的狀態

您可以在調查的進展中變更其狀態，將警示分類 (為 **新** 的、 **進行中** 或 **解決** 的) 。 這可協助您組織和管理您的小組可以回應提醒的方式。

例如，小組主持人可以查看所有 **新** 的警示，並決定將其指派給 **進行中** 的佇列以進行進一步分析。

或者，小組主持人可能會將警示指派給 **已解析** 的佇列，如果他們知道警示是良性的，來自不 (相關的裝置，例如屬於安全性管理員的裝置) ，或是透過先前的警示來處理。



## <a name="alert-classification"></a>警示分類
您可以選擇不設定分類，或指定警示為 true 警示或 false 警示。 務必提供 true 正/假正值的分類。 這種分類是用來監視警示品質，並使提醒更準確。 「判斷」欄位會定義 "true 正值" 分類的額外逼真度。 

## <a name="add-comments-and-view-the-history-of-an-alert"></a>新增批註並查看警示的記錄
您可以新增批註及查看有關警示的歷史事件，以查看先前對警示所做的變更。

每當對警示進行變更或批註時，就會將它記錄在 [ **批註和記錄** ] 區段中。

新增的註解會立即顯示在窗格中。


## <a name="related-topics"></a>相關主題
- [管理抑制規則](manage-suppression-rules.md)
- [查看和組織 Microsoft Defender for Endpoint 警示佇列](alerts-queue.md)
- [調查 Microsoft Defender for Endpoint 警示](investigate-alerts.md)
- [調查與 Microsoft Defender for Endpoint alert 相關聯的檔案](investigate-files.md)
- [調查 Microsoft Defender for Endpoint Devices 清單中的裝置](investigate-machines.md)
- [調查與 Microsoft Defender for Endpoint 警示相關聯的 IP 位址](investigate-ip.md)
- [調查與 Microsoft Defender for Endpoint alert 相關聯的網域](investigate-domain.md)
- [調查 Microsoft Defender for Endpoint 中的使用者帳戶](investigate-user.md)
