---
title: 自動化 Office 365 中的事件回應 （空調）
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 11/15/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 在 Office 365 進階威脅防護計劃 2 中，取得自動化調查及回應能力的概觀。
ms.openlocfilehash: 18da20491f9641b8313304e350f9c224b63cc5d9
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673399"
---
# <a name="automated-incident-response-air-in-office-365"></a>自動化 Office 365 中的事件回應 （空調）

自動化事件回應 （空調） 功能可讓您回應熟知威脅存在於今天執行自動化的調查程序。 空調可協助您操作更有效率的安全性作業小組。
- 若要取得航空的運作方式的概觀，請使用本文。
- 若要開始使用空調，請參閱[自動調查及回應 Office 365 中的威脅](office-365-air.md)。

> [!NOTE]
> 您必須是全域系統管理員、 安全性系統管理員、 安全性運算子或安全性助讀程式來存取空調功能。 若要深入了解這些權限，請參閱[Microsoft 365 安全性中心： 角色和權限](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。

## <a name="the-overall-flow-of-air"></a>航空的整體流程

在高的層級，空調流程的運作方式如下：

|階段  |涉及的內容  |
|---------|---------|
|1     |就會觸發[警示](#alerts)和[安全性 playbook](#security-playbooks)起始。         |
|2     |根據特定提醒及安全性 playbook，[自動化的調查會立即開始](#example-a-user-reported-phish-message-launches-an-investigation-playbook)。 （或者，安全性分析師可以[手動啟動自動化的調查](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)，請從報表，例如[檔案總管](threat-explorer.md)中的值。）         |
|3     |執行自動化調查時，其範圍會隨著新的相關警示觸發而增加。         |
|4     |期間和之後自動調查，[詳細資料和結果](#investigation-graph)可供檢視。 結果包含[建議的動作](#recommended-actions)可以採取回應及修復任何發現的威脅。 此外，也可以使用[playbook 記錄](#playbook-log)中追蹤調查的所有活動。<br/>如果您的組織會使用自訂的報表解決方案或協力廠商解決方案，您可以[使用 Office 365 管理活動 API](office-365-air.md#use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions) ，可檢視自動化的調查和威脅的相關資訊。         |
|5     |您的安全性作業小組會檢閱結果和建議，並核准補救動作。 在 Office 365 中，只能在貴組織的安全性小組核准時採取補救動作。         |

下列各節提供更多詳細資訊空調，包括提醒、 安全性 playbooks 和調查詳細資料相關的詳細資料。 此外，本文中包含航空的運作方式的兩個範例。 若要開始使用空調，請參閱[自動調查及回應 Office 365 中的威脅](office-365-air.md)。

## <a name="alerts"></a>警示

[提醒](../../compliance/alert-policies.md#viewing-alerts)代表觸發程序適用於安全性事件回應作業小組工作流程。 排列優先順序的調查，同時確保沒有威脅 unaddressed 提醒右組是一項挑戰。 時以手動方式執行提醒到調查，安全性作業小組必須搜尋，並與實體 （例如： 內容、 裝置及使用者） 相互關聯威脅的風險。 這類任務及工作流程相當耗時且牽涉到多個工具和系統。 與空調、 調查及回應會自動完成到主要安全性和威脅管理警報自動觸發您安全性回應 playbooks。 

在初始版本空調 （開始年 4 月 2019年），產生的警示，下列的單一事件警示原則會自動調查。 

- 偵測到有潛在的惡意 URL 點擊

- 報告的釣魚程式 * 作為使用者的電子郵件

- 電子郵件包含惡意程式碼傳遞 * 後移除

- 電子郵件訊息包含傳遞 * 後移除的釣魚程式 Url

- 傳送模式偵測到可疑的電子郵件#

- 使用者限制而無法傳送電子郵件#

> [!NOTE]
> 以星號 （*） 標記的警示關閉的電子郵件通知與指派安全性 & 合規性中心，各自的警示原則*提示資訊*嚴重性。 電子郵件通知可以開啟透過[警示原則設定](../../compliance/alert-policies.md#alert-policy-settings)。 以雜湊 （#） 標記的提醒是通常可公開預覽 playbooks 相關聯的提醒。

若要檢視提醒，安全性 & 合規性中心中，選擇 [**提醒** > **檢視警示**。 選取警示若要檢視其詳細資料，並從該處，使用的**檢視調查**連結移至對應的[調查](#investigation-graph)。 請注意預設將資訊警示隱藏 [警示] 檢視中。 若要查看它們，您需要變更篩選功能，包括資訊警示的警示。

如果您的組織管理您的安全性提醒透過警示管理系統、 服務管理系統或安全性資訊和事件管理 (SIEM) 的系統，您可以透過 [電子郵件通知，或是透過[Office 365 管理活動 API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)該系統傳送 Office 365 警示。 透過電子郵件或 API 調查警示通知包含連結來存取安全性 & 合規性中心，啟用快速瀏覽到調查指派的安全性系統管理員中的警示。

![連結至調查的提醒](../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>安全性 playbooks

安全性 playbooks 所面臨的自動化 Microsoft 威脅防護中的核心的後端原則。 常見的真實世界的安全性案例根據空調中提供安全性 playbooks。 當組織內就會觸發警示時，就會自動啟動安全性 playbook。 之後會觸發警示，自動執行相關聯的 playbook。 Playbook 執行和調查]，查看所有關聯的中繼資料 （包括電子郵件、 使用者、 主旨、 寄件者等）。 根據 playbook 所發現的錯誤，空調建議一組的動作，貴組織的安全性小組可以採取控制項，並降低威脅。 

您會看到與空調安全性 playbooks 專為今天處理最常見的威脅該組織圖像。 他們根據安全性作業和事件回應小組，包括協助防禦 Microsoft 和我們的客戶資產的輸入。

### <a name="security-playbooks-are-rolling-out-in-phases"></a>安全性 playbooks 已推出階段

航空的一部分，安全性 playbooks 已推出階段。 階段 1 是現在可使用，並包含數個 playbooks 提供建議的安全性系統管理員可以檢閱和核准的動作：
- 使用者報告的釣魚程式訊息
- URL 按一下 verdict 變更
- 偵測到的惡意程式碼後傳遞 （惡意程式碼時能量光束）
- 釣魚程式偵測到後續傳遞 ZAP （Phish 時能量光束）

階段 1 也包含手動的電子郵件調查 （使用[威脅總管](threat-explorer.md)） 的支援。

階段 2 現在是與**公開預覽**中提供建議的動作，並在調查問題達到安全性管理員下列 playbooks 的進度：
- 使用者回報為遭入侵 （公用預覽）

將發行進一步 playbooks，因為它們已完成。 請造訪[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)請參閱什麼是計劃的及接下來推出。

### <a name="playbooks-include-investigation-and-recommendations"></a>Playbooks 包括調查與建議

在空調，每個安全性 playbook 包括： 
- 根和調查]， 
- 識別並對應其他潛在威脅，所採取的步驟和 
- 建議的威脅修復動作。

每個高階步驟包括提供深層、 詳細又詳盡回應威脅時所執行的許多子步驟。

## <a name="automated-investigations"></a>自動化的調查

[自動化的調查] 頁面上顯示貴組織的調查和其目前狀態。

![空調主要調查頁面](../media/air-maininvestigationpage.png) 
  
您可以：
- 直接前往調查 （選取**調查識別碼**）。
- 套用篩選。 選擇 [從**調查類型**、**時間範圍**、**狀態**或這些項目的組合。
- 將資料匯出至.csv 檔案。

調查狀態表示分析和動作的進度。 當調查執行時，狀態會變更為表示是否已找到威脅，以及是否已核准的動作。 


|狀態  |其意思  |
|---------|---------|
|啟動中 | 調查已排入佇列推出開始 |
|正在執行 | 調查已啟動，並且所進行的分析 |
|沒有找到的威脅 | 調查已完成其分析，而且找不到任何威脅 |
|由系統終止 | 調查已不關閉，並將在 7 天後過期 |
|擱置中的巨集指令 | 調查找到威脅與建議的動作 |
|找到的威脅 | 調查找到威脅，但威脅沒有空調內可用的動作 |
|修復 | 調查完成，並完全修復 （已核准所有動作） |
|部分修復 | 調查完成，並建議的動作的一些已核准 |
|終止的使用者 | 系統管理員終止調查 |
|失敗 | 禁止達到上威脅結論調查期間發生錯誤 |
|排入佇列的節流設定 | 調查正在等候由於系統處理限制 （以保護服務效能） 的分析 |
|終止的節流設定 | 在有足夠的時間，因為調查磁碟區及處理限制的系統無法完成調查。 您可以重新觸發調查，選取 [檔案總管中的 [電子郵件，然後選取調查巨集指令。 |

### <a name="investigation-graph"></a>調查圖

當您開啟特定調查時，您會看到 [調查 graph] 頁面。 此頁面會顯示所有不同的實體： 電子郵件、 使用者 （和其活動），以及已自動調查一部分警示所觸發的裝置。

![空調調查 graph 頁面](../media/air-investigationgraphpage.png)

您可以：
- 取得目前調查的視覺化概觀。
- 檢視調查工期的摘要。
- 若要檢視該節點的詳細資料視覺效果中選取節點。
- 若要檢視該索引標籤的詳細資訊，在頂端選取] 索引標籤。

### <a name="alert-investigation"></a>警示調查

調查的 [**提醒**] 索引標籤中，您可以看到與調查有關的提醒。 詳細資料包含觸發調查警示和其他警示，例如風險登入，大量下載等的相互關聯的調查。 此頁面上，從安全性分析師也可以檢視其他詳細資料上獲取個別警示。

![產生提醒] 頁面上](../media/air-investigationalertspage.png)

您可以：
- 取得目前的觸發警示和任何相關聯的警示的視覺化概觀。
- 若要開啟 [顯示完整警示的詳細資訊的飛出視窗頁面清單中，選取 [警示。

### <a name="email-investigation"></a>電子郵件調查

在調查的**電子郵件**] 索引標籤中，您可以看到電子郵件被識別為調查的一部分的所有叢集。 

指定大量的電子郵件組織中的使用者傳送和接收的程序 
- 根據類似的屬性，從郵件標頭、 內文、 URL 和附件; 叢集的電子郵件 
- 從良好的電子郵件; 分隔惡意電子郵件和 
- 對惡意電子郵件採取的動作 

可能需要多個小時。 空調現在會自動執行此程序，儲存您的組織安全性小組時間和精力。 

可能會在電子郵件分析步驟期間識別的電子郵件叢集的兩種不同類型： 相似性叢集與標記叢集。 
- 相似性叢集會包含類似的寄件者和內容屬性的電子郵件訊息。 這些叢集會評估為惡意內容根據原始偵測結果。 包含足夠惡意偵測電子郵件叢集會被視為惡意。
- 標記叢集是包含相同指示器實體 （檔案雜湊或 URL） 從原始的電子郵件的電子郵件訊息。 時的原始的檔案/URL 實體便會被視為惡意，空調套用於標記 verdict 整個叢集的電子郵件訊息包含的實體。 為檔案識別為惡意程式碼指的是叢集中的電子郵件訊息包含該檔案會視為惡意程式碼的電子郵件。

叢集的目標是要尋找由攻擊或活動的一部分的相同寄件者所傳送的其他相關的電子郵件。

[**電子郵件**] 索引標籤也會顯示電子郵件項目相關的調查，例如使用者回報的電子郵件的詳細資訊，原始的電子郵件報告，電子郵件訊息 zapped 因為惡意程式碼/釣魚程式等等。

在 [電子郵件] 索引標籤上目前所識別的電子郵件計數代表顯示在 [**電子郵件**] 索引標籤上的所有電子郵件訊息的總和。因為電子郵件訊息中都有多個叢集，實際電子郵件訊息總數識別 （和受影響的補救動作） 跨所有叢集與原始收件者的電子郵件是唯一的電子郵件訊息存在的計數。 

檔案總管和空調計數上每個收件者為基礎的電子郵件，因為安全性結果、 動作和傳遞位置而異每個收件者為基礎。 因此原始的電子郵件傳送給三個使用者計數為總計的三個電子郵件，而不是一個電子郵件。 請注意那里可能會取得一封電子郵件的其中的情況下被計算兩個或更多時間，因為電子郵件可能會在其上有多個動作，而且可能會有多個電子郵件複本一次的所有動作會都發生。 例如時，傳遞偵測到惡意程式碼電子郵件可能會導致封鎖 （隔離） 電子郵件以及已被取代的電子郵件 （威脅檔案取代警告： 檔案，再傳遞到使用者的信箱）。 因為實際上，有兩個副本的電子郵件系統中-這些可能同時會計算叢集計數中。 

電子郵件計數計算調查的同時，和某些計數的重新計算當您開啟調查延伸顯示 （根據基準查詢）。 電子郵件計算所顯示的電子郵件] 索引標籤上的電子郵件叢集，並在叢集彈出式視窗上所顯示的電子郵件數量值的計算調查次。 在叢集彈出式視窗中，[電子郵件] 索引標籤的底端顯示的電子郵件計數和總管] 中顯示的訊息會反映在調查的初始分析後收到電子郵件訊息的電子郵件的計數。 因此顯示 10 的電子郵件的原始數量電子郵件叢集會顯示電子郵件清單總數的 15 5 的多個電子郵件訊息送達之間調查分析階段和系統管理員檢閱調查時。 顯示完成這兩個不同的檢視中的計數來指出電子郵件影響調查和到時間現行的目前影響次該修復為止。

做為範例，請考慮下列案例。 三個電子郵件的第一個叢集已被視為是釣魚程式。 類似郵件具有相同的 IP 和主旨的另一個叢集已找到，而且視為惡意，有些已識別為釣魚程式初始偵測期間。 

![空調電子郵件調查] 頁面](../media/air-investigationemailpage.png)

您可以：
- 取得目前的叢集結果和威脅找到的視覺化概觀。
- 按一下 [叢集實體或威脅清單] 以開啟飛出視窗] 頁面上顯示的完整警示的詳細資料。
- 進一步調查的電子郵件叢集按一下頂端的 '電子郵件叢集詳細資料] 索引標籤上的 '在檔案總管中開啟' 連結

![空調調查的電子郵件與彈出式詳細資料](../media/air-investigationemailpageflyoutdetails.png)

> [!NOTE]
> 在電子郵件的內容，您可能會看到大量異常威脅表面調查的一部分。 磁碟區異常指出相較於舊版項調查事件時間前後的類似電子郵件訊息中的特殊圖文集。 此特殊圖文集的特性類似的電子郵件流量 (例如主旨] 和 [寄件者的網域，本文相似性和寄件者 IP) 是一般的電子郵件行銷活動或攻擊的開始。 不過，大量、 垃圾郵件和合法電子郵件行銷活動常共用這些特性。 磁碟區異常代表潛在威脅，並據此可能少數嚴重相較惡意程式碼或釣魚程式的威脅，用來識別的防毒引擎、 爆炸或惡意的信譽。

### <a name="user-investigation"></a>使用者調查

在 [**使用者**] 索引標籤中，您可以看到識別為調查的一部分的所有使用者。 使用者帳戶出現在調查時沒有事件或可能影響這些使用者帳戶，或遭到盜用的指示。

例如，在下列映像，空調已識別危害和異常根據新的收件匣規則所建立的指標。 調查的其他詳細資料 （辨識項） 可透過此危害的指標] 索引標籤內的詳細檢視，而且異常也可包含從[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)的異常偵測。

![空調調查的使用者] 頁面](../media/air-investigationuserspage.png)

您可以：
- 取得已識別的使用者結果與風險找到的視覺化概觀。
- 選取使用者，若要開啟 [飛出視窗] 頁面上顯示的完整警示的詳細資料。

### <a name="machine-investigation"></a>機器調查

**機器**索引標籤上，您可以看到識別為調查的一部分的所有機器。 

![空調調查機器頁面](../media/air-investigationmachinepage.png)

調查的一部分，空調相互關聯至裝置的電子郵件威脅。 例如，調查遞給惡意檔案雜湊跨[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
)調查。 這可讓您的使用者，以協助確保已解決威脅，在雲端和跨端點相關機器的自動化調查。 

您可以：
- 取得目前機器和威脅找到的視覺化概觀。
- 選取 [若要開啟 [檢視電腦，到 Microsoft defender 資訊安全中心中相關的[Microsoft Defender ATP 調查](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)。

### <a name="entity-investigation"></a>實體調查

在 [**實體**] 索引標籤上，您可以看到識別為調查的一部分的所有實體。 

在這裡，您可以看到的調查實體與類型的實體，例如電子郵件、 叢集、 IP 位址、 使用者和更多詳細資料。 您也可以查看多少實體進行分析，且威脅，與每個相關聯。 

![空調調查實體] 頁面上](../media/air-investigationentitiespage.png)

您可以：
- 取得調查實體和威脅找到的視覺化概觀。
- 選取要開啟飛出視窗] 頁面顯示相關的實體詳細資料的實體。

![空調調查實體詳細資料](../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>Playbook 記錄檔

在 [**記錄**] 索引標籤中，您可以看到調查期間所發生的所有 playbook 步驟。 記錄檔擷取由 Office 365 自動調查功能完成空調一部分的所有動作的完整詳細目錄。 它本身、 描述及的實際工期提供清楚的所有所採取的步驟，包括巨集指令檢視從開始到完成。 

![空調調查記錄頁面](../media/air-investigationlogpage.png)

您可以：
- 取得看到所採取的 playbook 步驟的視覺化概觀。
- 將結果匯出至 CSV 檔案。
- 篩選的檢視。

### <a name="recommended-actions"></a>建議的動作

在 [**動作**] 索引標籤中，您可以看到建議的修復後調查已完成的所有 playbook 動作。 

動作擷取 Microsoft 建議您採取調查結尾處的步驟。 您可以藉由選取一或多個動作採取以下修復動作。 按一下 [**核准**允許修復以開始。 （所需的適當的權限-'搜尋及清除' 角色，才能執行從檔案總管和空調）。 例如，安全性讀取者可以檢視動作，而不是核准它們。 請注意-不需要核准的每個動作。 如果您不一致的建議的動作，或您的組織未選擇特定類型的動作-然後您可以選擇 [以**拒絕**動作或只需加以略過，並不採取任何動作。 核准及/或拒絕的所有動作可讓調查完全關閉時前面調查狀態變更為部分修復狀態中的某些動作不完整的結果。

![空調調查動作] 頁面上](../media/air-investigationactionspage.png)

您可以：
- 取得 playbook 建議動作的視覺化概觀。
- 選取單一動作或多個動作。
- 核准或拒絕建議的動作與註解。
- 將結果匯出至 CSV 檔案。
- 篩選的檢視。

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>範例： 使用者回報的釣魚程式訊息啟動調查 playbook

當您組織中的使用者送出的電子郵件訊息和報告至 Microsoft，請使用[報告訊息增益集以進行 Outlook 或 Outlook Web Access](enable-the-report-message-add-in.md)，報告也會傳送到您的系統，且使用者報告檢視中顯示在檔案總管。 此使用者回報郵件現在會觸發系統架構資訊警示，這會自動啟動 [調查 playbook。

在根調查階段中，會評估的電子郵件的各個層面。 包括：
- 可能需有哪些類型的威脅它決定;
- 寄件者; 它
- 其中電子郵件寄件地 （傳送基礎結構）;
- 電子郵件的其他執行個體是否已傳遞或封鎖;
- 從我們分析師; 評估
- 是否任何已知的行銷活動; 相關聯的電子郵件
- 等等。

根調查完成後，playbook 會提供建議的動作，才會在原始的電子郵件和與它相關聯的實體清單。
  
接下來，數個威脅調查並狩獵步驟執行：

- 要搜尋其他電子郵件叢集中的類似電子郵件訊息。
- 其他平台，例如[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)可共用接收的訊號。
- 決定在任何使用者是否按下可疑的電子郵件訊息中任何前往惡意連結。
- 檢查完成跨 Office 365 Exchange Online Protection ([EOP](exchange-online-protection-eop.md)) 和 Office 365 進階威脅防護 ([ATP](office-365-atp.md))，以查看是否有任何其他類似的訊息報告的使用者。
- 若要查看是否使用者已遭洩露完成查核。 這項檢查跨[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)和[Azure Active Directory](https://docs.microsoft.com/azure/active-directory)，相互關聯任何相關的使用者活動異常運用訊號。 

狩獵階段風險和威脅指派給各種狩獵步驟。 

修復為 playbook 的最後一個階段。 在這個階段，採取補救步驟為止，根據調查和狩獵階段。 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>範例： 安全性系統管理員會觸發從威脅總管調查

除了警示所觸發的自動調查，貴組織的安全性作業小組可以觸發自動進行調查，從[威脅總管](threat-explorer.md)] 中檢視。

例如，假設您正在檢視的資料在檔案總管中關於使用者報告的郵件。 您可以在結果清單中選取項目，然後按一下 [**調查]**。

![使用者報告中的郵件檔案總管與調查] 按鈕](../media/Explorer-UserReported-Investigate.png)

另一個範例，假設您正在檢視包含惡意程式碼，偵測到的電子郵件的相關資料，並有幾個偵測為包含惡意程式碼的電子郵件訊息。 您可以選取 [**電子郵件**] 索引標籤，選取一或多個電子郵件訊息，然後在 [**動作**] 功能表上選取 [**調查]**。 

![在檔案總管中開始進行調查，惡意程式碼](../media/Explorer-Malware-Email-ActionsInvestigate.png)

類似於 playbooks 觸發警示的通知，會觸發從瀏覽器中檢視的自動調查包含根目錄和調查]，以找出並相互關聯的威脅，步驟及建議的動作來減輕這些威脅。

## <a name="how-to-get-air"></a>如何取得航空

Office 365 AIR 現在包含在以下訂閱中：

- Microsoft 365 E5
- Office 365 E5
- Microsoft 威脅防護
- Office 365 進階威脅防護方案 2

如果您不需要任何這些訂閱，[開始免費試用版](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US)。

若要深入了解可用的功能，請造訪[進階威脅防護 (ATP) 計劃的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

## <a name="next-steps"></a>後續步驟

[開始使用 Office 365 中的空調](office-365-air.md)

[了解 Microsoft Defender ATP 中的空調](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) 

[請造訪 Microsoft 365 藍圖 」 來查看的項目是即將推出以及推行](https://www.microsoft.com/microsoft-365/roadmap?filters=)

