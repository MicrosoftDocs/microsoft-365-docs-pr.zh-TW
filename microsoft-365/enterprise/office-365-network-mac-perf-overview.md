---
title: Microsoft 365 系統管理中心的網路連線能力
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
description: Microsoft 365 系統管理中心的網路連線能力
ms.openlocfilehash: 05247c73bec3a11905890d26db84f8fe1a288a99
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53419796"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center"></a>Microsoft 365 系統管理中心的網路連線能力

Microsoft 365 系統管理中心現在包括從 Microsoft 365 租使用者收集到的匯總網路連線量，而且只能在租使用者中查看其管理使用者。

> [!div class="mx-imgBorder"]
> ![Network connectivity test 工具](../media/m365-mac-perf/m365-mac-perf-admin-center.png)

**網路評估** 和 **網路洞察力** 會顯示在 [狀況] 底下的 [Microsoft 365 系統管理] 中央 **|網路連線能力**。

> [!div class="mx-imgBorder"]
> ![網路效能頁面](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

>[!NOTE]
>Admin Center 中的網路連線支援 WW 商業銀行或德國的承租人，但不會 GCC 適中、GCC 高、DoD 或中國。

當您第一次流覽至 [網路性能] 頁面時，您必須設定位置，以查看全域網路效能對應、整個租使用者的網路評等範圍、遠端工作的使用者百分比與現場工作，以及要採取行動以進行進一步調查的目前問題清單。 您可以從 [一覽表] 窗格中，向下流覽以查看依位置的特定網路效能度量及問題。 如需詳細資訊，請參閱[Microsoft 365 系統管理 Center 中的網路效能一覽](#network-connectivity-overview-in-the-microsoft-365-admin-center)。

您可能需要代表您的組織加入此功能的公開預覽。 驗收通常會立即發生，之後您會看到 [網路連接] 頁面。

若要存取 [網路連線] 頁面，您必須是 Microsoft 365 內組織的管理員。 報告讀取器系統管理角色對此資訊具有「讀取」許可權。 若要設定網路連線的位置和其他元素，系統管理員必須是伺服器管理員角色的一部分，例如服務支援系統管理員角色。

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a>顯示網路連線評估的先決條件

若要開始使用，請開啟您的位置加入宣告使用 Windows 位置服務自動收集裝置中的資料，移至您的位置清單，以新增或上傳位置資料，或從您的辦公室位置執行 Microsoft 365 網路連線測試。 網路連線能力可以在整個組織中評估，因此必須針對特定的 office 位置進行任何網路設計改進。 可以決定這些位置之後，會為每個辦公室位置提供網路連線資訊。 有三個選項可從您的 office 位置取得網路評估：

### <a name="1-enable-windows-location-services"></a>1. 啟用 Windows 位置服務

針對此選項，您必須至少要有兩部電腦在支援先決條件的辦公室位置執行。 Windows 版本的 OneDrive 必須是最新的，且安裝在每一部電腦上。 如需 OneDrive 版本的詳細資訊，請參閱[OneDrive 版本](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0)資訊。 在近期，網路度量計畫可以新增至其他 Office 365 用戶端應用程式。

Windows位置服務必須同意電腦。 您可以執行 **地圖** 應用程式，並尋找自己，以進行測試。 您可以在具有設定 | 的單一機器上啟用此功能。 **隱私權 |** 必須啟用設定 _允許應用程式存取您的位置_ 的位置。 Windows位置服務同意可透過設定 _LetAppsAccessLocation_，將其部署至使用 MDM 或群組原則的電腦。

您不需要使用此方法在系統管理中心中新增位置，因為它們會在城市解析度中自動識別。 使用 Windows 位置服務時，不會顯示同一個城市中的多個辦公室位置。 位置資訊會四捨五入為最接近的300米乘以300米，這樣就不會存取更精確的位置資訊。

電腦應該有 Wi-Fi 網路，而不是乙太網線。 使用乙太網線的電腦沒有正確的位置資訊。

在符合這些先決條件後，應會在24小時內開始顯示度量範例和辦公室位置。

### <a name="2-add-locations-and-provide-lan-subnet-information"></a>2. 新增位置及提供 LAN 子網資訊

若為此選項，則不需要 Windows 位置服務，也不需要 Wi-Fi。 Windows 版本的 OneDrive 必須是最新的，且至少安裝在同一位置的一部電腦上。

您也需要在 [ **位置] 頁面** 中新增位置，或從 CSV 檔案匯入這些位置。 新增的位置必須包含您的 office LAN 子網資訊。

此選項可讓您在城市內定義多個辦公室。

來自用戶端電腦的所有測試度量，都包括 LAN 子網資訊，與您輸入的 office 位置詳細資料相關聯。 在符合這些先決條件後，應會在24小時內開始顯示度量範例和辦公室位置。

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a>3. 使用 Microsoft 365 network connectivity test 工具手動收集測試報表

針對此選項，您必須在每個位置識別人員。 要求使用者在其具有系統管理許可權的 Windows 電腦上流覽[Microsoft 365 網路連線測試](https://connectivity.office.com)。 在網站上，他們必須登入他們的 Office 365 帳戶，以取得您想要查看結果的相同組織。 然後，他們應該按一下 [ **執行測試**]。 在測試期間，有一個已下載的 Connectivity test EXE。 他們必須開啟並執行該程式。 測試完成後，測試結果便會上傳至系統管理中心。

測試報告如果是以 LAN 子網資訊新增，則會連結至該位置，否則只會顯示在城市位置。

測試報告完成後，測量範例和辦公室位置應會在2-3 分鐘內開始顯示。 如需詳細資訊，請參閱[Microsoft 365 network connectivity test](office-365-network-mac-perf-onboarding-tool.md)。

> [!NOTE]
> 目前，wWhen 新增您的 office 位置以 Microsoft 365 Microsoft 365 系統管理中心中的網路連線，您只能為您的局域網子網提供 IPv4 位址。 EgressIP 位址必須使用 IPv4。

## <a name="how-do-i-use-this-information"></a>如何使用此資訊？

**網路洞察力**，其相關的效能建議和網路評估是為了協助您為辦公室位置設計網路周邊。 每個洞察力都會針對使用者存取租使用者時，針對每個地理位置的特定常見網路問題，提供其效能特性的詳細資料。 每個網路洞察力的 **效能建議** 提供特定的網路架構設計變更，以改善與 Microsoft 365 網路連接相關的使用者體驗。 網路評估顯示網路連線影響使用者經驗的方式，允許比較不同的使用者位置網路連接。

**網路評估** 會將許多網路效能度量的集合提煉成商業網路健康情況的快照，以點數從 0-100。 網路評估同時適用于整個承租人和每個地理位置，供使用者從該位置連線到您的租使用者時，可提供 Microsoft 365 管理員來立即抓住商業網路健康情況的 gestalt，並快速深入查看任何全球辦公室位置的詳細報告。

具有多個辦公室位置和非一般網路周邊架構的複雜企業，可在初始上架到 Microsoft 365 時受益，或修復使用狀況成長所發現的網路效能問題。 使用 Microsoft 365 或任何已具備簡易及直接網路連線能力的企業，這通常不需要使用。 使用超過500個使用者和多個辦公室位置的企業，可獲得最大效益。

>[!IMPORTANT]
>[！注意] Microsoft 365 系統管理 Center 中的網路洞察力、效能建議和評估目前處於預覽狀態，只適用于已登記功能預覽方案 Microsoft 365 承租人。

## <a name="enterprise-network-connectivity-challenges"></a>Enterprise 網路連線挑戰

> [!div class="mx-imgBorder"]
> ![客戶網路到雲端](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

許多企業的網路周邊設定已經成長，主要是用來容納員工網際網路網站存取，而大多數網站卻不會事先知道，而且不受信任。 必要和必要的重點是避免來自這些未知網站的惡意程式碼和網路釣魚攻擊。 這個網路設定策略在安全性方面很有説明，可導致 Microsoft 365 使用者效能和使用者經驗降低。

## <a name="how-we-can-solve-these-challenges"></a>我們可如何解決這些難題

企業可以遵循[Office 365 連線原則](./microsoft-365-network-connectivity-principles.md)，以及使用 Microsoft 365 系統管理中心網路連線功能，來改善一般使用者經驗並保護其環境。 在大多數情況下，遵循這些一般原則會對使用者延隔時間產生重大的積極影響、服務可靠性和 Microsoft 365 的整體效能。

Microsoft 有時候會要求您調查大型企業客戶 Microsoft 365 的網路效能問題，這些問題通常會與客戶的網路周邊基礎結構相關的根本原因。 當找到客戶網路周邊問題的常見根本原因時，我們會搜尋識別它所識別的簡單測試度量。 使用識別特定問題的測量臨界值進行測試是非常有價值的，因為我們可以在任何位置測試相同的度量，判斷是否存在此根本原因，並加以共用，以與系統管理員的網路洞察力共用。

有些網路洞察力只會指出需要進一步調查的問題。 網路洞察力：我們有足夠的測試顯示特定的修正動作，以修正根本原因，會列為建議的 **動作**。 這些建議會根據即時度量，顯示在預先確定的臨界值以外的值，比一般的最佳作法建議更為重要，因為它們是特定于您的環境，而且會在進行建議的變更之後顯示實際的改進。

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a>Microsoft 365 系統管理中心的網路連線能力一覽

Microsoft 已有數個 Office 桌面和網頁用戶端的現有網路度量，可支援 Microsoft 365 的運作。 這些測量現在是用來提供網路架構設計真知灼見和網路評估，顯示在 Microsoft 365 系統管理 Center 的 [**網路連接**] 頁面中。

根據預設，與網路度量相關聯的大致位置資訊，識別用戶端裝置所在的城市。 每個位置的網路評估會顯示色彩，每個位置的使用者相對數量是以圓形大小來表示。

> [!div class="mx-imgBorder"]
> ![網路洞察力綜述對應](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

[一覽表] 頁面也會顯示客戶的網路評估，在所有辦公室位置都是加權平均。

> [!div class="mx-imgBorder"]
> ![網路評估](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

您可以在 [ **位置** ] 索引標籤中，查看可篩選、排序及編輯之位置的表格視圖。具有特定建議的位置也會包含估計的潛在延遲改進。 這是透過在該位置取得組織使用者的中間延遲，並減去同一個城市中所有組織的中間延遲。

> [!div class="mx-imgBorder"]
> ![網路洞察力位置](../media/m365-mac-perf/m365-mac-perf-locations.png)

## <a name="remote-worker-assessment-and-user-connection-metrics"></a>遠端工作者評估和使用者連線度量

我們會將網路流量記錄分類為遠端或現場使用者，並在 [一覽表] 窗格的 [使用者連線度量] 區段中顯示其百分比。 對於您有遠端使用者的城市，當您開啟該位置的頁面時，您會發現位置特定的遠端網路評估分數。 [位置] 清單會同時包含辦公室位置和遠端工作者城市，可以進行篩選和排序。 我們會提供遠端工作者評估分數，針對 Exchange、SharePoint 和 Teams 進行分數分解。

家用使用者網路洞察力會在城市階層進行匯總和報告，並限制在至少有5個遠端員工的城市。 我們不會識別在家運作的個別員工。

位置是自動分類為 [現場] 或 [遠端]，不過，您可以選擇手動輸入所有的上門出口 IP 位址，以確保100% 分類。 如果您決定移至此路由，您必須在新增您的所有出局 IP 位址後，在 [位置] 設定浮出的位置選取 [**手動輸入所有現場輸出 ip 位址**] 核取方塊。 完成此動作後，來自您已標示為「在現場」之出局 IP 位址的所有網路流量記錄都會永遠歸為「辦公室」，而每個其他出口 IP 位址都會分類為「遠端」。

## <a name="specific-office-location-network-performance-summary-and-insights"></a>特定的辦公室位置網路效能摘要和洞察力

選取「辦公室位置」會開啟位置特定摘要頁面，顯示已從該辦公室位置度量單位識別的網路出局詳細資料。

> [!div class="mx-imgBorder"]
> ![依位置的網路洞察力詳細資料](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

組織中組織使用者的周邊網路對應，包含下列部分或所有要素：

- **Office 位置**-您正在查看之頁面的辦公室位置
- **網路周邊** -從辦公室位置連接之來源 IP 位址的位置。 這取決於地理位置 IP 位置資料庫的準確性
- **Exchange 最優服務的前端門**-此辦公室位置的使用者應該連接到的建議 Exchange 服務前端門之一。
- **Exchange 欠最優** 的前門-使用者所連接的 Exchange 服務前端門，但不建議使用。
- **SharePoint 最優服務的前端門**-此辦公室位置的使用者應該連接到的建議 SharePoint 服務前端門之一。
- **SharePoint 欠最優的服務前端門**-一種已連接至使用者的 SharePoint 服務前門門，但不建議使用。
- **DNS 遞迴解析伺服器**-從偵測到之 DNS 遞迴解析程式（如果有的話）所用的地域 IP 資料庫的位置 Exchange Online () 
- **Proxy 伺服器** -從偵測到之 proxy 伺服器之地理 IP 資料庫的位置 (（如果有的話）) 

「Office 位置摘要」頁面也會顯示位置的網路評估、網路評估記錄、此位置的評估與相同城市中其他客戶的比較，以及您可以採取以改善網路效能與可靠性的特定真知灼見和建議清單。

在相同城市中的客戶之間的比較，取決於所有客戶都對網路服務提供者、電信基礎結構和目前的 Microsoft 網路點狀態具有相同存取權的預期。

位置名稱可以自訂時加入新位置或編輯位置快顯視窗中的現有位置。 這為您提供了隨時自訂您的位置名稱的彈性。 此外，當您直接在位置快顯視窗中新增 LAN 子網時，會顯示可供您選取之軟匹配 LAN 子網的下拉式清單。 您也可以新增及編輯特定 office 出局 IP 位址的電路名稱。

[Office 位置] 頁面上的 [詳細資料] 索引標籤會顯示用來提出任何真知灼見、建議及網路評估的特定測量結果。 這樣做是為了讓網路工程師能夠驗證其環境中任何限制或細節的建議和因素。 您也會發現在該辦公室位置上收集的範例以及該城市中的遠端工作人員預估的使用者人數。

> [!div class="mx-imgBorder"]
> ![位置特定詳細資料](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)

## <a name="sharing-network-assessment-data-with-microsoft"></a>與 Microsoft 共用網路評估資料

根據預設，貴組織和網路洞察力的網路評估是與 Microsoft 員工共用。 這不包括來自您員工的任何個人資料，但僅限於您的 office 位置之系統管理中心中所顯示的特定網路評估計量和網路洞察力。 此外，它也不會包含您的 office 位置名稱或街道位址，因此您需要告訴他們您想要討論之 office 的城市和支援識別碼。 如果關閉此功能，表示您與其討論網路連線的 Microsoft 工程師無法查看任何這項資訊。 啟用此設定只會在您啟用之後，共用未來所開始的資料。

## <a name="csv-import-for-lan-subnet-office-locations"></a>LAN 子網辦公位置的 CSV 匯入

針對 LAN 子網的 office 身分識別，您必須預先新增每個位置。 您可以從 CSV 檔案匯入這些位置，而不是在 [ **位置** ] 索引標籤中新增個別的 office 位置。 您可以從其他儲存的地方取得此資料，例如通話品質儀表板或 Active Directory 網站和服務

在 CSV 檔案中，發現的城市位置會顯示在 [userEntered] 欄中為空白，而手動新增的 office 位置會顯示為1。

1. 在 [主 _Microsoft 365_ 的連線] 視窗中，按一下 [**位置**] 索引標籤。

1. 按一下 [位置] 清單上方的 [匯 **入** ] 按鈕。 隨即會顯示 [匯 **入 office 位置** ] 快顯視窗。

   > [!div class="mx-imgBorder"]
   > ![CSV 匯入訊息](../media/m365-mac-perf/m365-mac-perf-import.png)

1. 按一下 [ **下載目前的 office 位置] (.csv)** 連結，將目前的位置清單匯出至 CSV 檔案，並將它儲存到本機硬碟。 這將為您提供正確的格式 CSV 和您可以新增位置的欄標題。 您可以保留現有的匯出位置。當您匯入更新的 CSV 時，將不會重複。 如果您想要變更現有位置的位址，當您匯入 CSV 時，它就會更新。 您無法變更所探索之城市的位址。

1. 開啟 CSV 並新增您的位置，方法是針對您想要新增的每個位置，在新行上填上下欄欄位。 保留所有其他欄位為空白;您在其他欄位中輸入的值將會被忽略。

   1. **userEntered** (必要) ：必須為1，以加入新的局域網子網辦公地點。
   1. **Name** (必要) ：辦公室位置的名稱
   1. **Address** (必要) ： office 的實體位址
   1. **Latitude** (選用) ：已從 Bing 對應位址的查找中填入空白
   1. **經度** (選用) ：從 Bing 對應位址的查找中填入空白
   1. **Egress IP 位址範圍 1-5** (選用) ：針對每個範圍，輸入電路名稱，後面接著以空格分隔的有效 IPv4 CIDR 地址清單。 這些值是用來區分您使用相同 LAN 子網 IP 位址的多個辦公室位置。 EgressIP 位址範圍全部必須為/24 網路大小，輸入中不包含/24。
   1. **LanIps** (必要) ：列出此辦公室位置所使用的局域網子網範圍。 LAN 子網 IDs 需要包含 CIDR 網路大小，網路大小可以介於/8 和/29 之間。 多個 LAN 子網範圍可以以逗號或分號分隔。

1. 當您已新增辦公室位置並儲存檔案時，請按一下 [完成] 欄位 **Upload** 旁邊的 [**流覽]** 按鈕，然後選取儲存的 CSV 檔案。

1. 檔案將會自動驗證。 如果有驗證錯誤，您會看到錯誤訊息：匯 _入檔案中有一些錯誤。請複查錯誤，修正匯入檔，然後再試一次。_ 按一下 [連結] 中的 [ **開啟錯誤詳細資料** ]，以取得特定欄位驗證錯誤的清單。

   > [!div class="mx-imgBorder"]
   > ![CSV 匯入錯誤訊息](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. 如果檔案中沒有錯誤，您會看到訊息： _報告已就緒。找到要新增的 x 位置和要更新的 x 位置。_ 按一下 [匯 **入** ] 按鈕上傳 CSV。

   > [!div class="mx-imgBorder"]
   > ![CSV 匯入準備郵件](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>常見問題集

### <a name="what-is-a-microsoft-365-service-front-door"></a>何謂 Microsoft 365 服務前門？

Microsoft 365 服務前門是 Microsoft 全域網路上的進入點，其中 Office 用戶端和服務會中斷其網路連接。 若要 Microsoft 365 的最佳網路連線，建議您的網路連線終止于最接近的 Microsoft 365 前門。

>[!NOTE]
>Microsoft 365 服務前端與 azure marketplace 中提供的 azure 前門服務產品沒有直接關聯。

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>最佳的 Microsoft 365 服務前門是什麼？

最佳的 Microsoft 365 服務前端是最接近您的網路出局，通常是在您的城市或大都市區域中。 使用[Microsoft 365 connectivity test 工具 (preview) ](office-365-network-mac-perf-onboarding-tool.md) ，判斷您的使用中 Microsoft 365 服務前蓋和最優服務前門的位置。 如果工具判斷您的使用中的前門是最優的，您會以最佳方式連線至 Microsoft 的全域網路。

### <a name="what-is-an-internet-egress-location"></a>何謂網際網路出口的位置？

網際網路出局位置是網路流量結束商業網路並連接到網際網路的位置。 此位置也會識別為您具有網路位址轉譯 (NAT) 裝置的位置，通常是您與網際網路服務提供者 (ISP) 的位置。 如果您看到位置和網際網路出局位置之間的距離很長，這可能表示有重要的 WAN backhaul。

### <a name="what-license-is-needed-for-this-capability"></a>這項功能所需的授權為何？

您需要可提供 Microsoft 365 系統管理中心存取權的授權。

## <a name="related-topics"></a>相關主題

[Microsoft 365 網路洞察力 (預覽) ](office-365-network-mac-perf-insights.md)

[ (預覽 Microsoft 365 網路評估) ](office-365-network-mac-perf-score.md)

[Microsoft 365 connectivity test 工具 (預覽) ](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365Network Connectivity Location 服務 (預覽) ](office-365-network-mac-location-services.md)
