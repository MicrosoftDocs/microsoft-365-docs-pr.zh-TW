---
title: 'Microsoft 365 系統管理中心的網路連線 (預覽) '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
description: 'Microsoft 365 系統管理中心的網路連線能力 (預覽) '
ms.openlocfilehash: 2b80dd001bd2ee5d5725ea67c73aa34b4eb8816c
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408402"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center-preview"></a>Microsoft 365 系統管理中心的網路連線 (預覽) 

Microsoft 365 系統管理中心現在包含從您的 Microsoft 365 租使用者收集到的匯總網路連線衡量標準，而且只能在租使用者中查看其管理使用者。

> [!div class="mx-imgBorder"]
> ![Network connectivity test 工具](../media/m365-mac-perf/m365-mac-perf-admin-center.png)

**網路評估** 和 **網路洞察力** 會顯示在 Microsoft 365 系統管理中心的 [ **狀況] |連線能力**。

> [!div class="mx-imgBorder"]
> ![網路效能頁面](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

>[!NOTE]
>Network connectivity test 工具支援位於 WW 和德國的承租人，但不支援 GCC 適中、GCC 高、DoD 或中國。

當您第一次流覽至 [網路性能] 頁面時，您會看到 [一覽表] 窗格，其中包含全域網路效能對應、整個承租人範圍的網路評估，以及目前問題的清單。 您可以從 [概述] 中深入查看特定的網路效能度量和依位置的問題。 如需詳細資訊，請參閱 [Microsoft 365 系統管理中心的網路效能概述](#network-connectivity-overview-in-the-microsoft-365-admin-center)。

您可能需要代表您的組織加入此功能的公開預覽。 接受通常會立即發生，然後您就會看到 [網路連接] 頁面。 

流覽至 [網路連線] 頁面時，您會看到 [一覽表] 窗格，其中包含全域網路效能對應、整個承租人範圍的網路評估，以及目前問題的清單。 若要存取此頁面，您必須是 Microsoft 365 內組織的管理員。 報告讀取器系統管理角色對此資訊具有「讀取」許可權。 若要設定網路連線的位置和其他元素，系統管理員必須是伺服器管理員角色的一部分，例如服務支援系統管理員角色。 您可以從 [概述] 中深入查看特定的網路效能度量和依位置的問題。 如需詳細資訊，請參閱 [Microsoft 365 系統管理中心的網路連線概述](#network-connectivity-overview-in-the-microsoft-365-admin-center)。

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a>顯示網路連線評估的先決條件

若要開始使用，請開啟您的位置加入宣告使用 Windows 位置服務的裝置自動收集資料，移至您的位置清單，以新增或上傳位置資料，或從您的辦公室位置執行 Microsoft 365 網路連線測試。 網路連線能力可以在整個組織中評估，因此必須針對特定的 office 位置進行任何網路設計改進。 可以決定這些位置之後，會為每個辦公室位置提供網路連線資訊。 有三個選項可從您的 office 位置取得網路評估：

### <a name="1-enable-windows-location-services"></a>1. 啟用 Windows 位置服務

針對此選項，您必須至少要有兩部電腦在支援先決條件的辦公室位置執行。 Windows 版本的 OneDrive 必須是最新的，且已安裝在每一部電腦上。 如需 OneDrive 版本的詳細資訊，請參閱 [OneDrive 版本](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0)資訊。 在近期的 Office 365 用戶端應用程式中，計畫加入網路度量。

Windows 位置服務必須同意電腦。 您可以執行「 **地圖** 」應用程式並自行尋找，以測試這種情況。 可在具有設定的單一機器上啟用 **|隱私權 |** 必須啟用設定 _允許應用程式存取您的位置_ 的位置。 您可以使用 MDM 或群組原則，將 Windows Location 服務同意部署至使用設定 _LetAppsAccessLocation_ 的電腦。

您不需要使用此方法在系統管理中心中新增位置，因為它們會在城市解析度中自動識別。 您無法使用 Windows 位置服務，在城市內顯示多個辦公室位置。 位置資訊也會四捨五入至最接近的300米（300米），以便在上傳之前，無法存取更精確的位置資訊。

電腦應該有 Wi-Fi 網路，而不是乙太網線。 使用乙太網線的電腦沒有正確的位置資訊。

在符合這些先決條件後，應會在24小時內開始顯示度量範例和辦公室位置。

### <a name="2-add-locations-and-provide-lan-subnet-information"></a>2. 新增位置及提供 LAN 子網資訊

若為此選項，則不需要 Windows Location 服務和 Wi-Fi。 您的 Windows 版本 OneDrive 必須是最新的，且安裝在每個電腦上的位置。

您也需要在系統管理中心的 [網路連線] 頁面中新增位置，或從 CSV 檔案匯入這些位置。 新增的位置必須包含您的 office LAN 子網資訊。

自您新增位置後，您可以在城市內定義多個辦事處。

來自用戶端電腦的所有測試度量，都包括 LAN 子網資訊，與您輸入的 office 位置詳細資料相關聯。 在符合這些先決條件後，應會在24小時內開始顯示度量範例和辦公室位置。

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a>3. 使用 Microsoft 365 network connectivity test 工具手動收集測試報告

針對此選項，您必須在每個位置識別人員。 要求使用者在其具有系統管理許可權的 Windows 電腦上流覽至 [Microsoft 365 網路連線測試](https://connectivity.office.com) 。 在網站上，他們必須登入其 Office 365 帳戶，以取得您想要查看結果的相同組織。 然後，他們應該按一下 [ **執行測試**]。 在測試期間，有一個已下載的 Connectivity test EXE。 他們也需要開啟並執行這種情況。 測試完成後，測試結果會上傳至 Office 365。

測試報告如果是以 LAN 子網資訊新增，則會連結至該位置，否則只會顯示在城市位置。

測試報告完成後，測量範例和辦公室位置應會在2-3 分鐘內開始顯示。 如需詳細資訊，請參閱 [Microsoft 365 network connectivity test (preview) ](office-365-network-mac-perf-onboarding-tool.md)。

## <a name="how-do-i-use-this-information"></a>如何使用此資訊？

**網路洞察力**，其相關的效能建議和網路評估是為了協助您為辦公室位置設計網路周邊。 每個洞察力都會針對使用者存取租使用者時，針對每個地理位置的特定一般問題，提供有關效能特性的詳細資料。 每個網路洞察力的 **效能建議** 提供特定的網路架構設計變更，以改進與 Microsoft 365 網路連接相關的使用者體驗。 網路評估顯示網路連線影響使用者經驗的方式，允許比較不同的使用者位置網路連接。

**網路評估** 會將許多網路效能度量的集合提煉成商業網路健康情況的快照，以點數從 0-100。 網路評估同時適用于整個承租人和每個地理位置，讓使用者可以從該位置連線到您的租使用者，為 Microsoft 365 系統管理員提供一種簡單的方法來立即抓住商業網路健康情況的 gestalt，並快速深入查看任何全球辦公室位置的詳細報告。

具有多個辦公室位置和非普通網路周邊架構的複雜企業，可在初始上架至 Microsoft 365 時受益，或修復使用狀況成長所發現的網路效能問題。 使用 Microsoft 365 的小型企業或任何已具備簡易和直接網路連線能力的企業，通常不需要這麼做。 使用超過500個使用者和多個辦公室位置的企業，可獲得最大效益。

>[!IMPORTANT]
>Microsoft 365 系統管理中心的網路洞察力、效能建議和評估目前處於預覽狀態，只適用于已在功能預覽計畫中註冊的 Microsoft 365 承租人。

## <a name="enterprise-network-connectivity-challenges"></a>商業網路連線挑戰

> [!div class="mx-imgBorder"]
> ![客戶網路到雲端](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

許多企業的網路周邊設定已經成長，主要是用來容納員工網際網路網站存取，而大多數網站卻不會事先知道，而且不受信任。 「主要」和「必要」的重點是避免來自這些未知網站的惡意程式碼和釣魚攻擊。 這個網路設定策略在安全性方面很有説明，可能會導致 Microsoft 365 使用者效能和使用者體驗的降級。

## <a name="how-we-can-solve-these-challenges"></a>我們可如何解決這些難題

企業可以遵循 [Office 365 連線原則](./microsoft-365-network-connectivity-principles.md) ，以及使用 Microsoft 365 系統管理中心的網路連線功能，來改善一般使用者經驗並保護其環境。 在大多數情況下，遵循這些一般原則會對使用者的延遲（服務可靠性和 Microsoft 365 的整體效能）產生重大的積極影響。

Microsoft 有時候會要求您調查大型企業客戶的 Microsoft 365 的網路效能問題，這些問題通常會與客戶網路周邊基礎結構相關的根本原因。 當找到客戶網路周邊問題的常見根本原因時，我們會搜尋識別它所識別的簡單測試度量。 使用識別特定問題的測量臨界值進行測試是非常有價值的，因為我們可以在任何位置測試相同的度量，判斷是否存在此根本原因，並加以共用，以與系統管理員的網路洞察力共用。

有些網路洞察力只會指出需要進一步調查的問題。 網路洞察力：我們有足夠的測試顯示特定的修正動作，以修正根本原因，會列為建議的 **動作**。 這些建議會根據即時度量，顯示在預先確定的臨界值以外的值，比一般的最佳作法建議更為重要，因為它們是特定于您的環境，而且會在進行建議的變更之後顯示實際的改進。

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a>Microsoft 365 系統管理中心的網路連線性一覽表

Microsoft 已從數個 Office 桌面和網頁用戶端，提供支援 Microsoft 365 作業的現有網路度量。 這些測量現在是用來提供網路架構設計真知灼見和網路評估，其顯示在 Microsoft 365 系統管理中心的 [ **網路** 連線] 頁面中。

根據預設，與網路度量相關聯的大致位置資訊，識別用戶端裝置所在的城市。 每個位置的網路評估會顯示色彩，每個位置的使用者相對數量是以圓形大小來表示。

> [!div class="mx-imgBorder"]
> ![網路洞察力綜述對應](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

[一覽表] 頁面也會顯示客戶的網路評估，在所有辦公室位置都是加權平均。

> [!div class="mx-imgBorder"]
> ![網路評估](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

您可以在 [位置] 索引標籤中，查看可篩選、排序及編輯之位置的表格視圖。具有特定建議的位置也會包含估計的潛在延遲改進。 這是透過在該位置取得組織使用者的中間延遲，並減去同一個城市中所有組織的中間延遲。

> [!div class="mx-imgBorder"]
> ![網路洞察力位置](../media/m365-mac-perf/m365-mac-perf-locations.png)

## <a name="specific-office-location-network-performance-summary-and-insights"></a>特定的辦公室位置網路效能摘要和洞察力

選取「辦公室位置」會開啟位置特定摘要頁面，顯示已從該辦公室位置度量單位識別的網路出局詳細資料。

> [!div class="mx-imgBorder"]
> ![依位置的網路洞察力詳細資料](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

組織中組織使用者的周邊網路對應，包含下列部分或所有要素：

- **Office 位置** -您正在查看之頁面的辦公室位置
- **網路周邊** -從辦公室位置連接之來源 IP 位址的位置。 這取決於地理位置 IP 位置資料庫的準確性
- **Exchange 最優服務的前端門** -此辦公室位置的使用者應該連接至其中一個建議的 Exchange 服務前端門
- **Exchange 欠最優** 的前門-使用者連線到的 exchange 服務前門，但是不建議使用
- **SharePoint 最優服務的前端門** -此辦公室位置的使用者應該連接到的建議 SharePoint 服務前端門之一。
- **SharePoint 欠最優的服務前端門** -一種已連接至使用者的 SharePoint 服務前門門，但不建議使用。
- **DNS 遞迴解析伺服器** -從偵測到之 DNS 遞迴解析程式（如果有的話）所用的地域 IP 資料庫的位置（如果有的話） () 
- **Proxy 伺服器** -從偵測到之 proxy 伺服器之地理 IP 資料庫的位置 (（如果有的話）)  

「Office 位置摘要」頁面也會顯示位置的網路評估、網路評估記錄、此位置的評估與相同城市中其他客戶的比較，以及您可以採取以改善網路效能與可靠性的特定真知灼見和建議清單。

在相同城市中的客戶之間的比較，取決於所有客戶都對網路服務提供者、電信基礎結構和目前的 Microsoft 網路點狀態具有相同存取權的預期。

[Office 位置] 頁面上的 [詳細資料] 索引標籤會顯示用來提出任何真知灼見、建議及網路評估的特定測量結果。 這樣做是為了讓網路工程師能夠驗證其環境中任何限制或細節的建議和因素。

> [!div class="mx-imgBorder"]
> ![位置特定詳細資料](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)

## <a name="sharing-network-assessment-data-with-microsoft"></a>與 Microsoft 共用網路評估資料

根據預設，貴組織和網路洞察力的網路評估是與 Microsoft 員工共用。 這不包括來自您員工的任何個人資料，但僅限於您的 office 位置之系統管理中心中所顯示的特定網路評估計量和網路洞察力。 此外，它也不會包含您的 office 位置名稱或街道位址，因此您需要告訴他們您想要討論之 office 的城市和支援識別碼。 如果關閉此功能，表示您與其討論網路連線的 Microsoft 工程師無法查看任何這項資訊。 啟用此設定只會在您啟用之後，共用未來所開始的資料。

## <a name="csv-import-for-lan-subnet-office-locations"></a>LAN 子網辦公位置的 CSV 匯入

針對 LAN 子網的 office 身分識別，您必須預先新增每個位置。 您可以從 CSV 檔案匯入這些位置，而不是在 [ **位置** ] 索引標籤中新增個別的 office 位置。 您可以從其他儲存的地方取得此資料，例如通話品質儀表板或 Active Directory 網站和服務

在 CSV 檔案中，已發現的城市位置會顯示在 [userEntered] 欄中為空白，手動新增的 office 位置會顯示為1。

1. 在 [主要 _連接至 Microsoft 365_ ] 視窗中，按一下 [ **位置** ] 索引標籤。

1. 按一下 [位置] 清單上方的 [匯 **入** ] 按鈕。 隨即會顯示 [匯 **入 office 位置** ] 快顯視窗。

   > [!div class="mx-imgBorder"]
   > ![CSV 匯入訊息](../media/m365-mac-perf/m365-mac-perf-import.png)

1. 按一下 [將 **目前的 office 位置 ( .csv)** ] 連結，將目前的位置清單匯出至 csv 檔案，並將其儲存到本機硬碟。 這將為您提供正確的格式 CSV 和您可以新增位置的欄標題。 您可以保留現有的匯出位置。當您匯入更新的 CSV 時，將不會重複。 如果您想要變更現有位置的位址，當您匯入 CSV 時，它就會更新。 您無法變更所探索之城市的位址。

1. 開啟 CSV 並新增您的位置，方法是針對您想要新增的每個位置，在新行上填上下欄欄位。 保留所有其他欄位為空白;您在其他欄位中輸入的值將會被忽略。

   1. **userEntered** (必要) ：必須為1，以供新的 LAN 子網辦公位置使用
   1. **Address** (必要) ： office 的實體位址
   1. **Latitude** (選用) ：以 Bing 地圖（如果空白）的查閱來填入。
   1. **經度** (選用) ：填入的 Bing 地圖中的位址若為空白
   1. **出局 IP 位址範圍 1-5** (選用) ：針對每個範圍，請輸入電路名稱，後面接著是以空格分隔的有效 IPv4 或 IPv6 CIDR 地址清單。 這些值是用來區分您使用相同 LAN 子網 IP 位址的多個辦公室位置。 出局 IP 位址範圍全部必須為/24 網路大小，且輸入中不包含/24。
   1. **LanIps** (必要) ：列出此辦公室位置所使用的局域網子網範圍。 LAN 子網 IDs 需要包含 CIDR 網路大小，網路大小可以介於/8 和/29 之間。 多個 LAN 子網範圍可以以逗號或分號分隔。
   
1. 當您已新增辦公室位置並儲存檔案後，請按一下 [**上傳完成**] 欄位旁邊的 [**流覽]** 按鈕，然後選取儲存的 CSV 檔案。

1. 檔案將會自動驗證。 如果有驗證錯誤，您會看到錯誤訊息在匯 _入檔案中有一些錯誤。請複查錯誤，修正匯入檔，然後再試一次。_ 按一下 [連結] 中的 [ **開啟錯誤詳細資料** ]，以取得特定欄位驗證錯誤的清單。

   > [!div class="mx-imgBorder"]
   > ![CSV 匯入錯誤訊息](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. 如果檔案中沒有錯誤，您將會看到 _[報告已就緒] 的訊息。找到要新增的 x 位置和要更新的 x 位置。_ 按一下 [匯 **入** ] 按鈕上傳 CSV。

   > [!div class="mx-imgBorder"]
   > ![CSV 匯入準備郵件](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>常見問題集

### <a name="what-is-a-microsoft-365-service-front-door"></a>何謂 Microsoft 365 服務的前門？

Microsoft 365 服務前端是 Microsoft 全球網路的進入點，Office 用戶端和服務會在此位置中斷其網路連線。 為了獲得最佳網路連接至 Microsoft 365，建議您的網路連線中斷最近的 Microsoft 365 前端。

>[!NOTE]
>Microsoft 365 服務前端沒有 azure marketplace 中可用的 Azure 前門服務產品的直接關聯。

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>何謂最優的 Microsoft 365 服務前門？

最佳的 Microsoft 365 服務前端是最接近您的網路出局，通常是在您的城市或大都市區域中。 使用 [Microsoft 365 connectivity test 工具 (預覽) ](office-365-network-mac-perf-onboarding-tool.md) ，以判斷您的使用中的 microsoft 365 服務前門和最優服務前端門的位置。 如果工具判斷您的使用中的前門是最優的，您就會以最優化方式連線至 Microsoft 的全球網路。

### <a name="what-is-an-internet-egress-location"></a>何謂網際網路出口的位置？

網際網路出局位置是網路流量結束商業網路並連接到網際網路的位置。 此位置也會識別為您具有網路位址轉譯 (NAT) 裝置的位置，通常是您與網際網路服務提供者 (ISP) 的位置。 如果您看到位置和網際網路出局位置之間有長距離的距離，則這可能表示有重要的 WAN backhaul。

## <a name="related-topics"></a>相關主題

[Microsoft 365 網路洞察力 (預覽) ](office-365-network-mac-perf-insights.md)

[Microsoft 365 網路評估 (預覽) ](office-365-network-mac-perf-score.md)

[Microsoft 365 connectivity test tool (預覽) ](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Network Connectivity Location 服務 (預覽) ](office-365-network-mac-location-services.md)