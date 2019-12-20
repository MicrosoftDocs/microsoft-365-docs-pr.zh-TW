---
title: 在 Microsoft Edge 中使用 Office 365 電子文件探索匯出工具
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 您必須啟用 ClickOnce 支援，以使用 Microsoft Edge 從內容搜尋和 eDiscovery 的安全性與合規性中心匯出搜尋結果。
ms.openlocfilehash: f3e0442fe349aa3364594e07873b229f3205fb5e
ms.sourcegitcommit: d656fd58e5491cfb7fee16b55dc7a58904ed128d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/06/2019
ms.locfileid: "39891124"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a>在 Microsoft Edge 中使用 Office 365 電子文件探索匯出工具

由於 Microsoft edge 的最新變更，依預設不會再啟用 ClickOnce 支援方法。 若要繼續使用 Microsoft Office 365 電子文件探索匯出工具來下載內容搜尋] 或 [eDiscovery 搜尋結果，您需要使用[Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads)或啟用 ClickOnce 支援 Microsoft Edge 中。

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a>如何啟用 ClickOnce 支援 Microsoft Edge 中

1. 在 Microsoft Edge、 瀏覽至**edge://flags/#edge-click-once**。

2. 如果現有的值設為**預設值**] 或 [**已停用**在下拉式清單中，則會變更為 [**已啟用**。
    
   ![](media/ClickOnceimage1.png)

3. 捲動至底部的瀏覽器視窗，然後按一下 [重新啟動 Edge 的 [**重新啟動**。

   ![](media/ClickOnceimage2.png)

**附註：** 組織可以使用群組原則停用 ClickOnce 支援。 若要檢查是否有 ClickOnce 支援的組織原則，請瀏覽至 [ **edge://policy**。 下列螢幕擷取畫面顯示 ClickOnce 已啟用整個組織。 如果此原則值設為**false**，您必須連絡貴組織中的系統管理員。

![](media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a>安裝和執行 Office 365 電子文件探索匯出工具

1. 在匯出內容搜尋] 或 [eDiscovery 案例中的彈出式頁面上，按一下 [**下載結果**。

   ![按一下 [下載結果在彈出式視窗] 頁面上，若要下載搜尋結果](media/ClickOnceExport1.png)

2. 您將會出現確認提示來啟動工具，請按一下 [**開啟**。

   ![按一下 [開啟] 以啟動 eDiscovery 匯出工具](media/ClickOnceimage4.png)

   如果未安裝 Microsoft Office 365 電子文件探索匯出工具，將會提示您安全性警告， 

   ![按一下 [安裝] 來安裝 eDiscovery 匯出工具](media/ClickOnceimage5.png)

3. 按一下 [安裝]****。 安裝之後，匯出工具會自動啟動。

如需詳細資訊，請參閱下列主題：

- [匯出內容搜尋結果](export-search-results.md)

- [如何啟用 Microsoft Edge 中的實驗旗標](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
