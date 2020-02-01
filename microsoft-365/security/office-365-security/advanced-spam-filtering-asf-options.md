---
title: 進階垃圾郵件篩選選項
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
description: 進階垃圾郵件篩選選項可讓系統管理員檢查郵件的各種內容屬性。 郵件中有此類屬性存在時，將會提高該郵件的垃圾郵件計分 (進而提高該郵件被識別為垃圾郵件的可能性)，或將該郵件標記為垃圾郵件。 ASF 選項以特定郵件內容為目標，例如 HTML 標記與 URL 重新導向這類常出現在垃圾郵件中的項目。
ms.openlocfilehash: 07f2b32dac6ba4a04fbccac5f015be399f62e254
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599960"
---
# <a name="advanced-spam-filtering-options"></a>進階垃圾郵件篩選選項

> [!NOTE]
> 進階垃圾郵件篩選設定的反垃圾郵件原則目前已被取代。 我們建議的設定，這些是以將其**關閉**。 進階垃圾郵件篩選器中可用的功能是要併入篩選堆疊的其他部分。

進階垃圾郵件篩選選項可讓系統管理員檢查郵件的各種內容屬性。 郵件中有此類屬性存在時，將會提高該郵件的垃圾郵件計分 (進而提高該郵件被識別為垃圾郵件的可能性)，或將該郵件標記為垃圾郵件。 ASF 選項以特定郵件內容為目標，例如 HTML 標記與 URL 重新導向這類常出現在垃圾郵件中的項目。
  
啟用 ASF 選項是一種很激進的垃圾郵件篩選方式，這些選項所篩選出來的任何郵件都無法回報為誤判。您可透過定期的使用者垃圾郵件通知來識別這些郵件，並從垃圾郵件隔離區將其救回。也可以透過 X-header 文字來識別這些郵件，此文字為各個 ASF 選項所特有，出現在已找到相符 ASF 選項的郵件的 Internet 標頭中。如需詳細資訊，請參閱＜[反垃圾郵件訊息標頭](anti-spam-message-headers.md)＞。
  
可以設定 ASF 選項，開啟、 關閉，或若要測試模式時編輯內容篩選原則。 如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。 測試模式不適用於**NDR 退信攻擊**，**的 SPF 記錄： 完全未通過**、**條件式寄件者識別碼篩選： 完全未通過**，和**大量電子郵件**選項。 
  
下表說明各個進階垃圾郵件篩選選項。
  
||||
|:-----|:-----|:-----|
|**進階垃圾郵件篩選選項** <br/> |**描述** <br/> |**X-header 文字** <br/> |
|**增加垃圾郵件計分] 區段** <br/> |啟用時，這些選項會設定為 5 或 6，符合郵件會被視為可疑的垃圾郵件的垃圾郵件信賴等級 (SCL)。 對郵件執行的巨集指令會比對內容篩選器原則中的**垃圾郵件**設定。  <br/> ||
|遠端站台的影像連結  <br/> |啟用此設定時，具有連結遠端 （例如，使用 http） 的 IMG 標籤的 HTML 內容任何訊息會收到增加垃圾郵件計分。  <br/> |X-customspam： 遠端站台的影像連結  <br/> |
|在 URL 中的數值 IP 位址  <br/> |啟用此設定時，任何具有數值式 Url （通常中的 IP 位址的形式） 的郵件會得到增加垃圾郵件計分。  <br/> |X-customspam: URL 中的數值 IP  <br/> |
|URL 重新導向到其他連接埠  <br/> |啟用此設定時，任何訊息包含的超連結，而不將使用者重新導向至連接埠連接埠 80 （一般 HTTP 通訊協定連接埠）、 8080 （HTTP 替代連接埠） 或 443 （HTTPS 連接埠） 會得到增加垃圾郵件計分。  <br/> |X-customspam: URL 重新導向到其他連接埠  <br/> |
|.Biz 或.info 網站的 URL  <br/> |啟用此設定時，任何包含.biz 或.info 副檔名為郵件本文中的郵件會得到增加垃圾郵件計分。  <br/> |X-customspam:.biz 或.info 網站的 URL  <br/> |
|**標記為垃圾郵件] 區段** <br/> |啟用時，這些選項設定垃圾郵件信賴等級 (SCL) 符合為郵件 9，這會被視為特定垃圾郵件。 對郵件執行的巨集指令會比對內容篩選器原則中的**高信賴度垃圾郵件**設定。  <br/> ||
|空白訊息  <br/> |啟用此設定時，郵件只要任何內文與主旨行皆空白，以及其也有不含附件，將會標示為垃圾郵件。  <br/> |X-customspam： 空白郵件  <br/> |
|JavaScript 或 VBScript html  <br/> |啟用此設定時，任何使用 JavaScript 或 Visual Basic 指令碼版本以 html 格式的郵件會被標示為垃圾郵件。 這兩個這些指令碼語言可用來自動會導致特定動作發生 HTML 郵件中。 在瀏覽器會剖析和處理程序的其餘部分文件以及指令碼。  <br/> |X-customspam: HTML 中有 Javascript 或 VBscript 標籤  <br/> |
|HTML 中有 frame 或 IFrame 標籤  <br/> |啟用此設定時，會包含任何訊息\<圖文框\>或\<IFrame\> HTML 標記會被標示為垃圾郵件。 這些標記用於在網站上或 HTML 郵件中，將格式化顯示的文字或圖形的頁面。  <br/> |X-customspam: IFRAME 或 FRAME 中 HTML  <br/> |
|HTML 中有 object 標籤  <br/> |啟用此設定時，會包含任何訊息\<物件\>HTML 標記會被標示為垃圾郵件。 外掛程式或 HTML 視窗中執行的應用程式，可讓此 HTML 標記。  <br/> |X-customspam: Html 中有 Object 標記  <br/> |
|HTML 中有 embed 標籤  <br/> |啟用此設定時，會包含任何訊息\<Embed\> HTML 標記會被標示為垃圾郵件。 此 HTML 標記可讓不同種類的 varying 內嵌到 HTML 文件的資料類型的文件。 範例包括音效、 電影或圖片。  <br/> |X-customspam: Html 中有 Embed 標記  <br/> |
|HTML 中有 form 標籤  <br/> |啟用此設定時，會包含任何訊息\<表單\>HTML 標記會被標示為垃圾郵件。 此 HTML 標記用於建立網站的表單。 電子郵件廣告通常包含此標記，以取得收件者的資訊。  <br/> |X-customspam: Html 中有 Form 標記  <br/> |
|HTML 中有錯誤網頁  <br/> |啟用此設定時，任何包含 Web bug 的郵件會被標示為垃圾郵件。 Web bug 是設計用來判斷是否已讀取的網頁或電子郵件訊息的圖形。 Web bug 通常是看不到收件者的因為它們通常是新增至訊息做為同一個像素的一個像素的圖形。 雖然許多這部分一併考慮侵犯隱私權合法電子報可能也會使用此技術。  <br/> |X-customspam: Web bug  <br/> |
|套用敏感字詞清單  <br/> |啟用此設定時，任何包含文字，請從敏感字詞清單中的郵件會被標示為垃圾郵件。 使用敏感字詞清單，可讓簡單封鎖可能令人不悅的郵件相關聯的字。 這些字詞的某些不區分大小寫。 身為管理員，您無法編輯此清單。 根據敏感字詞清單篩選會套用至郵件的主旨和郵件內文。  <br/> |X-customspam： 主旨/本文中的敏感字詞  <br/> |
|SPF 記錄： 完全未通過|啟用此設定時，無法通過 SPF 檢查 （表示寄件 SPF 記錄中未指定 IP 位址） 的郵件會被標示為垃圾郵件。 身為擔心接收網路釣魚郵件的組織，建議您開啟此設定。  <br/> <br/> 測試模式不適用於此選項。  <br/> |X-customspam: SPF 記錄失敗  <br/> |
|條件式寄件者識別碼篩選： 完全未通過  <br/> |啟用此設定時，完全失敗時的條件式寄件者識別碼檢查任何郵件已標示為垃圾郵件。 此選項結合了 SPF 檢查與寄件者識別碼檢查，以協助防範包含偽造寄件者的郵件標頭。  <br/> <br/> 測試模式不適用於此選項。  <br/> |X-customspam: SPF 寄件者記錄失敗  <br/> |
|NDR 非法回應  <br/> |如果您正在使用 EOP 來保護內部部署信箱，啟用此設定時，所有合法的未傳遞回報 (NDR) 郵件會傳遞給原始寄件者和 backscatter (非法 NDR) 的所有郵件會被都標示為垃圾郵件。 如果您未啟用此設定，然後所有 Ndr 仍都經過垃圾郵件篩選。 在此情況下，最合法郵件會取得傳遞給原始寄件者時，但並非所有，將會收到退信攻擊郵件標示為垃圾郵件。 不過，未標示為垃圾郵件的非法回應郵件將不會移至原始寄件者，因為它將會移至詐騙的寄件者。 <br/> <br/> 如果您使用服務來保護 Exchange Online 雲端託管信箱，您不需要進行此設定。  <br/><br/> 這兩個案例中 （內部部署和雲端託管信箱），它也不是必要時啟用此設定為透過服務，以是合法退回的郵件將會自動偵測並傳遞給原始寄件者的 Ndr 傳送的外寄郵件. 無法使用此選項 > 測試模式。           <br/><br/>秘訣： 如需退信攻擊郵件與 EOP 的詳細資訊，請參閱[退信攻擊郵件與 EOP](backscatter-messages-and-eop.md)。           |X-customspam： 非法回應 NDR  <br/> |
|大宗郵件|進階垃圾郵件篩選大量電子郵件的已停用並取代為大量及電子郵件設定的臨界值。 請參閱[垃圾郵件和大量電子郵件之間的差異為何？](what-s-the-difference-between-junk-email-and-bulk-email.md)及[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)的詳細資訊，以及如何進行設定。|X-customspam： 大宗郵件 | 大宗郵件  <br/> |
|
