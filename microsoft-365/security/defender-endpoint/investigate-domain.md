---
title: 調查 Microsoft Defender 的端點網域
description: 使用調查選項，查看裝置和伺服器是否已與惡意網域進行通訊。
keywords: 調查網域、網域、惡意網域、Microsoft Defender for Endpoint、alert、URL
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
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 7826229ba67384137c033745a5b85e557fc9c4a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933466"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a>調查與 Microsoft Defender for Endpoint alert 相關聯的網域

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

調查網域，以查看商業網路中的裝置和伺服器是否已與已知惡意的網域進行通訊。

您可以使用搜尋功能，或按一下 **裝置時程表** 中的網域連結，調查網域。

您可以在 URL 視圖中看到下列各節中的資訊：

- URL 詳細資料、連絡人、名稱伺服器
- 與此 URL 相關的警示 
- 組織中的 URL
- 最近透過 URL 觀察到的裝置

## <a name="url-worldwide"></a>全球 URL

「 **全球 url** 」一節列出 Url、Whois 的進一步詳細資料、相關開啟的事件數目，以及作用中警示的數目。

## <a name="incident"></a>事件

**事件** 卡片會顯示過去180天事件中所有活動警示的橫條圖。

## <a name="prevalence"></a>流行

「 **傳播** 卡片」提供組織內的 URL 的詳細資訊，在指定的一段時間內。

雖然預設時段是過去30天，您可以選取卡片一角的向下箭號，即可自訂範圍。 可使用的最短範圍是過去一天的流行，而最長的範圍則是過去6個月。

## <a name="alerts"></a>警示

[ **警示** ] 索引標籤提供與 URL 相關聯的警示清單。 這裡顯示的表格是警示佇列畫面上顯示之警示的篩選版本，只顯示與網域相關聯的警示、嚴重性、狀態、關聯的事件、分類、調查狀態等等。

您可以從欄標題上方的 [動作] 功能表中，選取 [ **自訂資料行** ]，以顯示更多或更少的資訊。 您也可以透過在相同功能表上選取 [ **每頁的專案** ] 來調整顯示的專案數。

## <a name="observed-in-organization"></a>組織中的觀測

在 [ **組織中看到** 的] 索引標籤會在 URL 上看到的事件及相關警示上，提供按時間排序的視圖。 此索引標籤包含時程表及可自訂的表格，其中列出事件詳細資料，例如時間、裝置及發生狀況的簡短描述。 

您可以在表格標題上方的文字欄位中輸入日期，以查看不同時間週期中的事件。 您也可以選擇不同的時程表區域，以自訂時間範圍。

**調查網域：**

1. 從 **搜尋** 列下拉式功能表中選取 [ **URL** ]。
2. 在 [ **搜尋** ] 欄位中輸入 URL。
3. 按一下搜尋圖示或按 **enter** 鍵。 顯示 URL 的詳細資料。 附注：只會針對來自組織中裝置的通訊所看到的 URLs 傳回搜尋結果。
4. 使用搜尋篩選以定義搜尋準則。 您也可以使用 [時程表] 搜尋方塊來篩選組織中所看到之所有裝置的顯示結果，與 URL 有關，與通訊和上次觀測的日期相關聯的檔。
5. 按一下任一裝置名稱將會帶您前往該裝置的視圖，您可以在其中繼續調查報告的警示、行為和事件。

## <a name="related-topics"></a>相關主題
- [查看和組織 Microsoft Defender for Endpoint 警示佇列](alerts-queue.md)
- [管理 Microsoft Defender for Endpoint 警示](manage-alerts.md)
- [調查 Microsoft Defender for Endpoint 警示](investigate-alerts.md)
- [調查與 Microsoft Defender for Endpoint alert 相關聯的檔案](investigate-files.md)
- [調查 Microsoft Defender for Endpoint Devices 清單中的裝置](investigate-machines.md)
- [調查與 Microsoft Defender for Endpoint 警示相關聯的 IP 位址](investigate-ip.md)
- [調查 Microsoft Defender for Endpoint 中的使用者帳戶](investigate-user.md)
