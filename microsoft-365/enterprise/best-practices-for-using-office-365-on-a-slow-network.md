---
title: 在網路緩慢的情況下使用 Office 365 的最佳做法
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: End User
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- MET150
- MET150
- MOP150
- MEW150
- BCS160
ms.assetid: fd16c8d2-4799-4c39-8fd7-045f06640166
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: 本文會引導您完成在慢速網路上使用 Office 365 的最佳作法。
ms.openlocfilehash: a0a15191fa0240f24cecc5e595de9a259cacc9f9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688666"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>在網路緩慢的情況下使用 Office 365 的最佳做法

如果您的網際網路連線一直都很快且未曾中斷，不是很好嗎？ 或許那一天會到來。 但在此同時，有一些實務做法可暫時解決不聽使喚的網路，讓您仍可完成日常工作。 雖然 Office 365 是一項雲端式服務，但也提供多種方法來離線處理內容，且順暢地讓變更保持同步。 此外，有時候離線處理內容會更有效率，因為應用程式的執行速度更快且使用者介面更有回應。 重點是：Office 365 讓您在這兩方面都達到最佳效能。 以下是利用該服務的方式。 
  
> [!TIP]
> 想要查看您的網路連線速度有多緩慢 (或快速) 嗎？ 請嘗試 [OOKLA 速度測試](https://www.speedtest.net/)或[網路速度測試應用程式](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70)。 

## <a name="why-is-my-network-so-slow"></a>為何我的網路如此緩慢？

雖然您無法控制網路效能本身，但這有助於了解幕後真相。 網際網路極度複雜，但有一些概念可協助您更加了解情況。 遵循本文中的最佳做法，有助於暫時解決效能問題並減輕挫折感。
  
**影響網路效能的主要因素**

![網路效能因素](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)
  
 **頻寬和延遲** 頻寬和延遲是網路效能的兩項最重要的量值： 
  
- 頻寬是以每秒位元數測量的輸送量速率。 越大越好。 頻寬就像是水管。 管道越大，您就可以「接通」更多水。

- 延遲是從伺服器或服務取得內容並送到您的裝置所需的時間 (以毫秒為測量單位)。 越快越好。 導致延遲的因素有很多，包括低頻寬、稀疏連線或傳輸時間。

 **常見問題** 除了頻寬和延遲，其他問題也會影響網路效能，且通常無法預期。 網路效能可能會隨著一天的時間或您的實體位置而波動。 發生會阻止網際網路使用的特定事件 (例如自然災害或重大公共事件) 時，網路可能會堵塞。 所載入頁面的大小和複雜度以及所傳送檔案的數目和大小對效能有直接關聯。 WiFi 連線可能會暫時降級：例如，您會要求每個人同時推文，以輪詢數千人參與的大型會議。 
  
 **衛星網路的考量** 在地面網路不可行的情況下，衛星網路會相當實用，例如原始山林、郵輪或偏遠科學區域。 這些網路依靠在赤道上方 22,000 英哩處的地球同步軌道中所部署之衛星。 不過，傳輸實際行進約 90,000 英哩，所以相較於地面網路 (20 到 50ms)，衛星網路會有較慢的延遲 (500 ms 或以上)。 在最佳的情況下，您可能不會察覺此延遲，但若是下載大型檔案、串流視訊及玩遊戲，您可能就會察覺。 另一個問題是「雨致衰減」，當天氣惡劣時 (例如雷暴雨和暴風雪)，會使衛星傳輸暫時中斷。
  
## <a name="are-you-sure-its-the-network"></a>您確定是網路問題嗎？

每當發生效能問題時，首先請確保您的裝置並非問題的根本來源。 您可以執行以下兩項操作，效能即可有大幅的提升：
  
- 請確認裝置運作正常且電腦沒有惡意程式碼。

- 可能的話，請購買更多記憶體。 新增記憶體是最簡單且通常最有效的裝置效能改善方式。 在處理大型檔案和影片時特別有幫助。

如需詳細資訊，請參閱 [Windows 效能與維護](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help)及[改善 Windows 10 電腦效能的秘訣](https://support.microsoft.com/en-za/help/4002019/windows-10-improve-pc-performance)。

## <a name="best-practices-for-using-your-browser"></a>使用您的瀏覽器的最佳做法

您的瀏覽器是您通往 Office 365 的閘道，所以它會影響效能，尤其是載入頁面所需的時間，以及您反覆存取 Office 365 服務的頻率。
  
 **瀏覽器概觀**
  
以下是適用於一般瀏覽器的一些建議：
  
- 停用可能會影響效能或其實不需要的瀏覽器附加元件。

- 提高暫存網際網路檔案的快取大小。

- 當您登入您的公司或學校帳戶後，請讓瀏覽器視窗整天保持開啟狀態。 您不必再次登入，即可開啟其他分頁和視窗。 如果您需要登入另一個帳戶，請使用「隱私瀏覽」。 

- 下載並開啟每一頁後，請利用分頁使其開啟保持開啟狀態。 您可輕鬆瀏覽分頁並在當天稍後使用該頁面。 只有在您需要頁面上的最新資料時，才要重新整理該頁面。

- 如果頁面花費過多的時間開啟，請停止下載頁面 (按 ESC)，然後重新整理頁面 (按 F5)。 

-  可能的話，請減少 Office 365 的來回行程。 例如，使用搜尋在大型文件庫中尋找檔案並在清單中篩選，直接前往您想要的結果，而不是逐頁瀏覽清單或文件庫。 或者，建立可將頁面載入時間最小化的檢視。 如需更多資訊，請參閱[管理 Office 365 中的大型清單和文件庫](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES)。

- 如果影片效能不佳，您可以下載影片並在您的裝置上觀看。 您可以使用下載連結，也能夠以滑鼠右鍵按一下影片連結，然後選取 [另存目標]****。

 **特定瀏覽器**
  
以下是適用於特定瀏覽器的一些建議：
  
- **Internet Explorer** 升級為 Internet Explorer 版本 11 或更新版本，獲得超乎以往版本的效能提升。 如需詳細資訊，請參閱 [Internet Explorer 的疑難排解指南](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365)。

- **FireFox** 如需詳細資訊，請參閱 [Firefox 緩慢或停止運作](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging)。

- **Safari** 如需詳細資訊，請參閱 [Apple - Safari](https://www.apple.com/safari/)。

- **Chrome** 如需詳細資訊，請參閱 [Chrome 說明](https://support.google.com/chrome/?hl=en)。
  
## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>使用 Outlook 與 Outlook Web App 的最佳做法

閱讀、撰寫及組織電子郵件是每個人的重要日常工作。 Outlook 和 Outlook Web 應用程式 (OWA) 均提供離線支援。 在智慧型手機上使用電子郵件應用程式是另一種實用替代方式。 使用最符合您需求的下列選項：
  
- 升級為最新版的 Outlook，獲得超乎以往版本的效能提升。 

-  Outlook Web 應用程式可讓您建立離線郵件、連絡人及行事曆事件，以便在 OWA 下一次能夠連線到 Office 365 時上傳。 如需在離線模式中設定及使用 OWA 的詳細資訊，請參閱[離線使用 Outlook Web 應用程式](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36)。

- Outlook 可讓您在快取模式中工作，只要有可能就會自動連線。 您可以讓 Outlook 下載整個信箱或只是其中一部分。 如需詳細資訊，請參閱[開啟 Exchange 快取模式](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c)及[在 Outlook 中離線工作](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633)。

- Outlook 也會提供離線模式。 若要使用此模式，您必須先設定快取模式，讓您帳戶中的資訊複製到您的電腦。 在離線模式中，Outlook 會嘗試使用傳送和接收設定進行連線，或在您手動將它設為線上工作時連線。 如需詳細資訊，請參閱[離線工作以免產生資料連線費用](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282)、[在離線工作時變更傳送和接收設定](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)，以及[從離線工作切換為線上工作](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9)。

- 如果您有智慧型手機，您可以透過電信業者的網路在手機上分類電子郵件與行事曆。

> [!NOTE]
> 以下是一些有關何時使用 Outlook 或 OWA 的指引。 如果您裝置上的磁碟空間不成問題，則 Outlook 有一組可能最適合您的完整功能。 如果您裝置上的磁碟空間是個問題，請考慮使用 OWA，其具有一小組功能，但也最適合用於線上情況。 當然，您可以使用任一項，因為兩者一起運作良好。
  
## <a name="best-practices-for-using-onedrive-for-business"></a>使用商務用 OneDrive 的最佳做法

商務用 OneDrive 已從頭開始設計為在線上或離線處理您的檔案。 設定完成後，當您隨時隨地進行變更時，就會自動且可靠地同步處理變更。 如果網路速度緩慢，您可以使用離線版本的檔案。
  
商務用 OneDrive 同步處理應用程式隨附於 SharePoint 和 Office 365 商務版訂閱，或者您也可以免費[下載](https://support.microsoft.com/kb/2903984)商務用 OneDrive 同步處理應用程式。 比起使用 [在檔案總管中開啟]**** 或 [上傳]**** 命令，此應用程式也比較快。 如需詳細資訊，請參閱[設定您的電腦在 Office 365 同步處理商務用 OneDrive 檔案](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16)。
  
以下是使用商務用 OneDrive 同步處理應用程式的一些額外指導方針：
  
- 如果您是第一次同步處理大型文件庫，請在離峰時段開始同步處理，例如半夜。

- 您可以使用[暫停同步處理文件庫與商務用 OneDrive 應用程式](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330)功能，暫時停止同步處理更新。 然而，此功能的使用時間不宜過長 (例如每次限制為幾個小時)，如此可避免大量的更新排入佇列，並盡可能減輕多人使用相同文件時所會發生的合併衝突風險。
  
## <a name="best-practices-for-using-onenote"></a>使用 OneNote 的最佳做法

每個 SharePoint 小組網站都有內建 OneNote 筆記本，您可以輕鬆地建立自己的筆記本。 OneNote 是及時收集每天完成工作所需資訊的絕佳方式。 比方說，許多小組都使用 OneNote 作為每週會議、專案注意事項、構想、計畫和狀態報告的收集點。 您可以使用頁面、區段和分頁，整齊地組織這些迥然不同的資訊。
  
OneNote 的優點是，您可以從任何裝置 (不論是桌上型電腦、膝上型電腦、平板電腦或智慧型手機) 存取內容。 而不需擔心儲存或同步處理事宜，因為 OneNote 會為您執行這類操作。
  
如需詳細資訊，請參閱 [Microsoft OneNote](https://office.microsoft.com/onenote)。

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>使用商務用 Skype 和 Lync Online 的最佳做法

以下是在網路速度緩慢時使用 商務用 Skype 或 Lync Online 的一般指導方針：

- 可以的話，盡量使用立即訊息功能，因為這對網路緩慢的情況相當有效。

- 避免透過虛擬私人網路 (VPN) 或遠端存取服務 (RAS) 連線來撥打電話。

- 確定已核准您的音訊裝置。 如需詳細資訊，請參閱[合格的 Microsoft Lync 電話與裝置](https://docs.microsoft.com/skypeforbusiness/lync-cert/ip-phones)。

- 在線上簡報中使用 PowerPoint 時，請降低投影片的大小和複雜度。 如需詳細資訊，請參閱[提升簡報效能的祕訣](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949)。

- 視訊效能非常依賴網路效能。 如果您的網路很慢，請避免使用視訊。

如需詳細資訊，請參閱 [Lync Online 中不佳的音訊或視訊品質](https://support.microsoft.com/kb/2386655)，或是如何[針對商務用 Skype 中的連線問題進行疑難排解](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771)。
  
## <a name="best-practices-for-using-sharepoint-lists"></a>使用 SharePoint 清單的最佳做法

離線使用清單資料來「清除」、分析或報告資料，是將慢速網路的影響降到最低的絕佳方式。 您可藉由連結方式，從 Microsoft Access 2019 和 Microsoft Access 2016 讀取及寫入大部分清單。 您可以將清單匯出到 Excel 表格，這麼做會在 Excel 表格與清單之間建立單向資料連線。 了解如何[離線使用連結到 SharePoint 清單的資料表](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e)。
  
如需詳細資訊，請參閱[管理 Office 365 中的大型清單與文件庫](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784)中的＜深入了解管理大型清單＞一節。
  
## <a name="best-practices-for-customizing-web-pages"></a>自訂網頁的最佳做法

當您自訂網頁時，您可能會不小心導致該頁面的效能不佳。 許多因素都有可能造成影響，例如頁面的複雜度與大小、新增的網頁組件數、剛開始顯示的清單或文件庫項目數，以及您對頁面編碼的方式。
  
如需詳細資訊，請參閱[調整 SharePoint Online 效能](tune-sharepoint-online-performance.md)。
  
## <a name="best-practices-for-using-project-online"></a>使用 Project Online 的最佳做法

下列指導方針可協助改善網路效能。
  
- Project Online 和 SharePoint Online 需要同步處理，而這可能會很耗費時間。 如果您專案小組的流動率較低，請停用 [專案網站同步處理] 以改善 [專案發佈] 和 [專案詳細資料頁面] 效能。 將 Active Directory 同步處理限制為實際需要使用系統的資源群組，並在大型群組同步處理後監控任何可能的權限問題。

- 如果貴組織使用專案網站，請根據需求加以建立，而非自動建立。 這可加快首次發佈經驗，且避免建立不必要的網站和內容。

- [專案詳細資料頁面] (PDP) 會觸發整個專案和開始工作流程行動的重新計算，這兩者都會是強調效能的作業。 若要避免在相同 PDP 上同時觸發兩項更新處理程序，請避免更新行事曆欄位 (開始日期、完成日期、狀態日期和目前日期)，以及非排程的欄位 (專案名稱、描述和擁有者)。

- 減少每個 PDP 上顯示的 Web 組件和自訂欄位之數量。 只用需要更新的欄位建立專用 PDP，以改善負載並節省時間。

- 當您使用 OData 進行報告時，請透過使用伺服器端篩選，限制您在執行階段查詢的資料量。

如需詳細資訊，請參閱[調整 Project Online 效能](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)。
  
## <a name="whats-the-best-way-to-report-problems"></a>什麼是提報問題的最好方法？

Microsoft 透過監控網路、測量頻寬和延遲、改善頁面載入時間、降低磁碟 I/O、將頁面重新設計為使用 [基本下載策略]、新增硬體到資料中心以及新增更多資料中心，致力持續改善 Office 365 的整體效能。 如需有關檢查目前狀態及提報問題的詳細資訊，請參閱[如何檢查 Office 365 服務健康狀況](view-service-health.md)。
  
## <a name="see-also"></a>另請參閱

[Office 365 的網路規劃和效能調整](network-planning-and-performance.md)
  
[Office 365 網路連線原則](microsoft-365-network-connectivity-principles.md)
  
[管理 Office 365 端點](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Office 365 端點常見問題集](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d) (機器翻譯)
 
