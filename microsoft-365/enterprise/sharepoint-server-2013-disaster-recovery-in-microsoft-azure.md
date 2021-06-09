---
title: Microsoft Azure 中的 SharePoint Server 2013 災害復原
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 04/17/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Deployment
- seo-marvel-apr2020
ms.assetid: e9d14cb2-ff28-4a18-a444-cebf891880ea
description: 本文說明如何使用 Azure 為您的內部部署 SharePoint 伺服器陣列建立災害復原環境。
ms.openlocfilehash: 01a49cfa19711caa36190a795792635431dd7d04
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907429"
---
# <a name="sharepoint-server-2013-disaster-recovery-in-microsoft-azure"></a>Microsoft Azure 中的 SharePoint Server 2013 災害復原

 使用 Azure，您可以為內部部署 SharePoint 伺服器陣列建立災害復原環境。 本文說明如何設計和實作本解決方案。

 **觀賞 SharePoint Server 2013 嚴重損壞恢復概述影片**
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1b73ec8f-29bd-44eb-aa3a-f7932784bfd9?autoplay=false]
  
 當發生災難時，您的 SharePoint 內部部署環境，您的最高優先順序是讓系統立即重新執行。 當您已在 Microsoft Azure 中執行備份環境時，具有 SharePoint 的嚴重損壞修復會變得更快速且更容易。 這段影片說明 SharePoint 溫容錯移轉環境的主要概念，並補充本文中提供的完整詳細資料。
  
請使用本文搭配下列解決方案模型： **Microsoft Azure 中的 SharePoint** 嚴重損壞修復。
  
[![SharePoint 到 Azure 的災害復原程序](../media/SP-DR-Azure.png)](https://go.microsoft.com/fwlink/p/?LinkId=392555)
  
 [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555) |  [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)
  
## <a name="use-azure-infrastructure-services-for-disaster-recovery"></a>使用 Azure 基礎結構服務進行嚴重損壞修復

許多組織沒有 SharePoint 的嚴重損壞復原環境，因此建立及維護內部部署成本可能很高。 Azure 基礎結構服務為嚴重損壞復原環境提供了極具說服力的選項，其可比內部部署方案更靈活且成本低。
  
使用 Azure 基礎結構服務的優點包括：
  
- **成本較低的資源** 維護和支付的資源少於內部部署的嚴重損壞修復環境。 資源數目取決於您所選擇的嚴重損壞復原環境：冷待命、暖色待命或熱待機。
    
- **更好的資源彈性** 萬一發生嚴重損壞，請輕鬆擴充您的復原 SharePoint 伺服器陣列，以滿足負載需求。 當您不再需要資源時放大。
    
- **資料中心承諾較低** 使用 Azure 基礎結構服務，而不是在不同的區域中投資至次要資料中心。
    
組織的選項非常不復雜，只是針對具有高恢復性需求的組織開始使用災難修復和高級選項。 當環境主控于雲端平臺上時，cold、溫及熱備用環境的定義會有些不同。 下表說明這些在 Azure 中建立 SharePoint 復原伺服器陣列的環境。
  
**表：復原環境**

|**復原環境的類型**|**描述**|
|:-----|:-----|
|熱  <br/> |在待命中布建、更新及執行完全大小的伺服器陣列。  <br/> |
|溫暖  <br/> |伺服器陣列已建立，且虛擬機器正在執行並更新。  <br/> 復原包括附加內容資料庫、布建服務應用程式，以及編目內容。  <br/> 伺服器陣列可以是較小版本的實際執行伺服器陣列，然後擴充以服務于完整的使用者群。  <br/> |
|冷  <br/> |伺服器陣列已完全建立，但虛擬機器已停止。  <br/> 維護環境包括從時間開始虛擬機器、修補、更新及驗證環境。  <br/> 發生嚴重損壞時，請啟動完整環境。  <br/> |
   
請務必評估貴組織的修復時間目標 (Rto) 和復原點目標 (Rpo) 。 這些需求決定哪個環境為您的組織最適合的投資。
  
本文中的指導方針會說明如何執行預熱的待機環境。 您也可以將它調整為 cold 待命環境，但是您必須遵循其他程式以支援這類環境。 本文不會說明如何執行熱待機環境。
  
如需有關嚴重損壞修復解決方案的詳細資訊，請參閱[SharePoint 2013 的高可用性和嚴重損壞修復概念](/SharePoint/administration/high-availability-and-disaster-recovery-concepts)，然後[選擇 SharePoint 2013](/SharePoint/administration/plan-for-disaster-recovery)的嚴重損壞修復策略。
  
## <a name="solution-description"></a>解決方案說明

暖色待命災害復原解決方案需要下列環境：
  
- 內部部署 SharePoint 的實際執行伺服器陣列
    
- Azure 中的復原 SharePoint 伺服器陣列
    
- 兩個環境間的網站對網站 VPN 連線
    
下圖說明這三個元素。
  
**圖： Azure 中的暖色待命方案元素**

![Azure 中 SharePoint 暖待命解決方案的元素](../media/AZarch-AZWarmStndby.png)
  
使用分散式檔案系統複寫 SQL Server 記錄傳送 (DFSR) 用來將資料庫備份和交易記錄檔複製到 Azure 中的復原伺服器陣列： 
  
- DFSR 會將記錄從實際執行環境轉移至復原環境。 在 WAN 案例中，DFSR 比直接將記錄傳送至 Azure 中的次要伺服器更為有效率。
    
- 將記錄檔重播至 Azure 的復原環境中的 SQL Server。
    
- 除非執行復原練習，否則您不會在復原環境中附加記錄傳送的 SharePoint 內容資料庫。
    
若要復原伺服器陣列，請執行下列步驟：
  
1. 停止記錄傳送。
    
2. 停止接受主要伺服器陣列的流量。
    
3. 重新顯示最後的交易記錄檔。
    
4. 將內容資料庫附加至伺服器陣列。
    
5. 從複製的服務資料庫還原服務應用程式。
    
6. Update Domain Name System (DNS) 記錄，以指向復原伺服器陣列。
    
7. 開始完整編目。
    
建議您定期預演這些步驟，並加以記錄以協助確保即時修復順利執行。 附加內容資料庫及還原服務應用程式可能需要一些時間，通常需要一些手動設定。
  
執行復原後，此解決方案會提供下表所列的專案。
  
**表：解決方案復原目標**

|**項目**|**描述**|
|:-----|:-----|
|網站和內容  <br/> |網站和內容可在復原環境中使用。  <br/> |
|新的搜尋實例  <br/> |在此暖色待命方案中，不會從搜尋資料庫還原搜尋。 復原伺服器陣列中的搜尋元件與實際執行伺服器陣列盡可能地設定。 還原網站和內容之後，就會開始完整編目以重建搜尋索引。 您不需要等候編目即可完成，讓網站和內容能夠可用。  <br/> |
|服務  <br/> | 在資料庫中儲存資料的服務會從記錄傳送資料庫還原。 不會將資料儲存在資料庫中的服務只是啟動。 <br/>  並非所有包含資料庫的服務都必須還原。 下列服務不需要從資料庫還原，而且可以在容錯移轉後直接啟動： <br/>  Usage and Health Data Collection <br/>  狀態服務 <br/>  Word automation <br/>  任何未使用資料庫的其他服務 <br/> |
   
您可以使用 Microsoft 諮詢服務 (MCS) 或合作夥伴，以處理更複雜的復原目標。 下表摘要說明這些摘要。
  
**表：其他可由 MCS 或合作夥伴處理的專案**

|**項目**|**描述**|
|:-----|:-----|
|同步處理自訂伺服器陣列解決方案  <br/> |理想狀況下，復原伺服器陣列設定與實際執行伺服器陣列相同。 您可以與顧問或合作夥伴合作，評估是否要複製自訂的伺服器陣列解決方案，以及是否已將兩個環境同步處理。  <br/> |
|連接至內部部署的資料來源  <br/> |複製後端資料系統的連線（例如備份網域控制站 (BDC) 連線和搜尋內容來源）可能不實用。  <br/> |
|搜尋還原案例  <br/> |因為企業搜尋部署一般都是非常獨特且複雜，所以從資料庫還原搜尋需要更多的投資。 您可以與顧問或合作夥伴合作，識別及執行您的組織可能需要的搜尋還原案例。  <br/> |
   
本文所提供的指導方針假設已經設計及部署了內部部署伺服器陣列。
  
## <a name="detailed-architecture"></a>詳細架構

理想狀況下，Azure 中的復原伺服器陣列設定與實際部署的實際執行伺服器陣列相同，包括下列各項：
  
- 伺服器角色的相同標記法
    
- 自訂的相同設定
    
- 相同的搜尋元件設定
    
Azure 中的環境可以是較小版本的實際執行伺服器陣列。 如果您打算在容錯移轉後擴充復原伺服器陣列，則必須最初代表每一種類型的伺服器角色。
  
在容錯移轉環境中進行複寫時，有些設定可能不實用。 請務必測試容錯移轉程式和環境，以協助確保容錯移轉伺服器陣列提供預期的服務等級。
  
此方案不規定 SharePoint 伺服器陣列的特定拓撲。 此解決方案的重點是使用 Azure 進行容錯移轉伺服器陣列，並在兩個環境間執行記錄傳送和 DFSR。
  
### <a name="warm-standby-environments"></a>暖色待命環境

在暖待命環境中，Azure 環境中的所有虛擬機器都在執行中。 環境已準備好進行容錯移轉練習或事件。
  
下圖說明從內部部署 SharePoint 伺服器陣列到設定為暖色待命環境之 Azure 架構 SharePoint 伺服器陣列的嚴重損壞修復解決方案。
  
**圖：實際執行伺服器陣列和暖待命復原伺服器陣列的拓撲和重要專案**

![SharePoint 伺服器陣列和暖待命復原伺服器陣列的拓撲](../media/AZarch-AZWarmStndby.png)
  
在此圖表中：
  
- 並排說明兩個環境：內部部署 SharePoint 伺服器陣列和 Azure 中的暖色待命伺服器陣列。
    
- 每個環境都包括檔案共用。
    
- 每個伺服器陣列包含四個層。 為了實現高可用性，每一層都包含兩個伺服器或虛擬機器，其設定與特定角色相同，例如前端服務、分散式快取、後端服務和資料庫。 請不要在此圖例中撥打特定的元件。 兩個伺服器陣列的設定都相同。
    
- 第四層是資料庫層。 記錄傳送可用於將記錄從內部部署環境中的輔助資料庫伺服器複製到相同環境中的檔案共用。
    
- DFSR 會將檔案從內部部署環境中的檔案共用複製至 Azure 環境中的檔案共用。
    
- 記錄傳送會將記錄從 Azure 環境中的檔案共用重新執行至復原環境的 SQL Server AlwaysOn 可用性群組中的主要複本。
    
### <a name="cold-standby-environments"></a>Cold 待命環境

在冷待命環境中，大部分的 SharePoint 伺服器陣列虛擬機器都可以關閉。  (我們建議您偶爾開始虛擬機器，例如每兩周或每月一次，讓每個虛擬機器都可以與網域同步。 ) Azure 復原環境中的下列虛擬機器必須保持執行，以協助確保連續運作記錄傳送和 DFSR：
  
- 檔案共用
    
- 主資料庫伺服器
    
- 至少一部執行 Windows Server Active Directory 網域服務和 DNS 的虛擬機器
    
下圖顯示執行檔案共用虛擬機器及主要 SharePoint 資料庫虛擬機器的 Azure 容錯移轉環境。 所有其他的 SharePoint 虛擬機器都已停止。 不會顯示執行 Windows Server Active Directory 和 DNS 的虛擬機器。
  
**圖：具有執行虛擬機器的 Cold 待命復原伺服器陣列**

![Azure 中 SharePoint 冷待命解決方案的元素](../media/AZarch-AZColdStndby.png)
  
容錯移轉至冷待命環境之後，所有虛擬機器都會啟動，而且必須設定實現資料庫伺服器高可用性的方法，例如 SQL Server AlwaysOn 可用性群組。
  
如果已執行多個儲存群組 (資料庫會分散在多個 SQL Server 高可用性集) 上，必須執行每個儲存群組的主資料庫，以接受與其儲存群組相關聯的記錄檔。
  
### <a name="skills-and-experience"></a>技能和經驗

在此嚴重損壞修復解決方案中使用多項技術。 為了協助確保這些技術如預期的方式互動，必須正確安裝和設定內部部署和 Azure 環境中的每個元件。 建議設定此解決方案的人員或小組具備下列文章中所述技術，具有和實際執行技能的強有力的工作知識。
  
- [分散式檔案系統 (DFS) 複寫服務](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))
    
- [Windows伺服器容錯移轉叢集 (WSFC) 與 SQL Server](/sql/sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server)
    
- [AlwaysOn 可用性群組 (SQL Server)](/sql/database-engine/availability-groups/windows/always-on-availability-groups-sql-server)
    
- [備份及還原 SQL Server 資料庫](/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases)
    
- [SharePoint伺服器2013安裝和伺服器陣列部署](/SharePoint/install/installation-and-configuration-overview)
    
- [Microsoft Azure](/azure/)
    
最後，我們建議您可以用來自動化與這些技術相關之工作的腳本技能。 您可以使用可用的使用者介面，以完成此方案中所述的所有工作。 不過，手動方法可能非常耗時且容易出錯，並提供不一致的結果。
  
除了 Windows PowerShell 之外，SQL Server、SharePoint Server 和 Azure 也會 Windows PowerShell 文件庫。 別忘了 T-SQL，也有助於縮短設定及維護災難復原環境的時間。
  
## <a name="disaster-recovery-roadmap"></a>嚴重損壞修復藍圖

![SharePoint 嚴重損壞修復藍圖的視覺表示法。](../media/Azure-DRroadmap.png)
  
此藍圖假設您已在生產環境中部署 SharePoint Server 2013 伺服器陣列。
  
**表：嚴重損壞修復的藍圖**

|**階段**|**描述**|
|:-----|:-----|
|階段1  <br/> |設計嚴重損壞修復環境。  <br/> |
|階段2  <br/> |建立 Azure 虛擬網路和 VPN 連線。  <br/> |
|階段3  <br/> |將 Windows Active Directory 和網功能變數名稱稱服務部署到 Azure 虛擬網路。  <br/> |
|階段4  <br/> |在 Azure 中部署 SharePoint 復原伺服器陣列。  <br/> |
|階段5  <br/> |在伺服器陣列之間設定 DFSR。  <br/> |
|階段6  <br/> |設定恢復伺服器陣列的記錄傳送。  <br/> |
|階段7  <br/> | 驗證容錯移轉和復原解決方案。 這包括下列程式及技術： <br/>  停止記錄傳送。 <br/>  還原備份。 <br/>  編目內容。 <br/>  復原服務。 <br/>  管理 DNS 記錄。 <br/> |
   
## <a name="phase-1-design-the-disaster-recovery-environment"></a>階段1：設計嚴重損壞修復環境

使用[SharePoint 2013 Microsoft Azure 架構](microsoft-azure-architectures-for-sharepoint-2013.md)的指導方針來設計災難復原環境，包括 SharePoint 復原伺服器陣列。 您可以使用 Azure 中 SharePoint 嚴重損壞復原[解決方案中](https://go.microsoft.com/fwlink/p/?LinkId=392554)的圖形 Visio 檔案，以啟動設計程式。 建議您先設計整個環境，然後再開始執行 Azure 環境中的任何工作。
  
除了[Microsoft Azure 架構 2013 SharePoint 用於](microsoft-azure-architectures-for-sharepoint-2013.md)設計虛擬網路、VPN 連線、Active Directory 及 SharePoint 伺服器陣列的指導方針之外，請務必將檔案共用角色新增至 Azure 環境。
  
若要在嚴重損壞修復解決方案中支援記錄傳送，則會將檔案共用虛擬機器新增至資料庫角色所在的子網。 檔案共用也會充當 SQL Server AlwaysOn 可用性群組的節點的第三個節點。 在使用 SQL Server AlwaysOn 可用性群組的標準 SharePoint 伺服器陣列中，這是建議的設定。 
  
> [!NOTE]
> 務必要檢查資料庫的必要條件，以加入 SQL Server AlwaysOn 可用性群組。 如需詳細資訊，請參閱[AlwaysOn 可用性群組的必要條件、限制和建議](/sql/database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability)。 
  
**圖：用於嚴重損壞修復解決方案的檔案伺服器位置**

![顯示新增至含有 SharePoint 資料庫伺服器角色之相同雲端服務的檔案共用 VM。](../media/AZenv-FSforDFSRandWSFC.png)
  
在此圖中，檔案共用虛擬機器會新增至包含資料庫伺服器角色之 Azure 中的相同子網。 請勿將檔案共用虛擬機器新增至具有其他伺服器角色的可用性設定，例如 SQL Server 角色。
  
如果您擔心記錄的高可用性，請考慮使用使用[Azure Blob 儲存體服務的 SQL Server 備份與還原](/sql/relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service)來採取不同的方式。 這是 Azure 中的新功能，可直接將記錄儲存至 blob 儲存 URL。 此方案不包含使用此功能的指導方針。
  
當您設計復原伺服器陣列時，請記住成功的嚴重損壞修復環境會正確反映您要復原的實際執行伺服器陣列。 復原伺服器陣列的大小並不是復原伺服器陣列設計、部署及測試中最重要的一點。 伺服器陣列規模會根據業務需求，依組織而異。 您可以使用縮小的伺服器陣列進行短暫的中斷，或直到效能與容量需求需要您縮放伺服器陣列。
  
盡可能將復原伺服器陣列設定為與實際執行伺服器陣列相同的服務等級協定，使其符合您的服務等級協定 (SLA) 需求，並提供您支援您的企業所需的功能。 當您設計嚴重損壞復原環境時，也請查看您實際執行環境的變更管理程式。 建議您以與實際執行環境相同的間隔更新復原環境，將變更管理程式擴充至復原環境。 在變更管理程式中，我們建議您維護伺服器陣列設定、應用程式和使用者的詳細清查。 
  
## <a name="phase-2-create-the-azure-virtual-network-and-vpn-connection"></a>階段2：建立 Azure 虛擬網路和 VPN 連線

[連線內部部署網路至 Microsoft Azure 虛擬網路](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)顯示如何在 Azure 中規劃及部署虛擬網路，以及如何建立 VPN 連線。 遵循主題中的指導方針完成下列程式：
  
- 規劃虛擬網路的私人 IP 位址空間。
    
- 規劃虛擬網路的路由基礎結構變更。
    
- 規劃進出內部部署 VPN 裝置之流量的防火牆規則。
    
- 在 Azure 中建立跨單位虛擬網路。
    
- 設定您的內部部署網路和虛擬網路之間的路由。
    
## <a name="phase-3-deploy-active-directory-and-domain-name-services-to-the-azure-virtual-network"></a>階段3：將 Active Directory 和功能變數名稱服務部署到 Azure 虛擬網路

此階段包含[SharePoint 2013 Microsoft Azure 架構](microsoft-azure-architectures-for-sharepoint-2013.md)中所述的混合式案例中，部署 Windows Server Active Directory 和 DNS 至虛擬網路，如下圖所示。
  
**圖：混合式 Active Directory 網域設定**

![兩部部署至 Azure 虛擬網路的虛擬機器，以及 SharePoint 的伺服器陣列子網為複本網域控制站和 DNS 伺服器](../media/AZarch-HyADdomainConfig.png)
  
在圖例中，兩部虛擬機器會部署至相同的子網。 這些虛擬機器分別主控兩個角色： Active Directory 和 DNS。
  
在 azure 中部署 Active directory 之前，請閱讀在[azure 虛擬機器上部署 Windows Server Active Directory 的指導方針](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100)。 這些指導方針可協助您判斷方案是否需要不同的架構或不同的設定設定。
  
如需在 Azure 中設定網域控制站的詳細指導，請參閱 [在 Azure 虛擬網路中安裝複本 Active Directory 網域控制站](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100)。
  
在此階段之前，您未將虛擬機器部署到虛擬網路。 主控 Active Directory 和 DNS 的虛擬機器可能不是解決方案所需的最大虛擬機器。 在您部署這些虛擬機器之前，請先建立您計畫用於虛擬網路的最大虛擬機器。 這可協助確保您的解決方案集中于 Azure 中的標記，以允許您需要的最大大小。 此時您不需要設定此虛擬機器。 只需建立它，並將它放在一邊。 如果您不這麼做，當您嘗試建立較大的虛擬機器時，可能會發生限制，這是撰寫本文時的問題。 
  
## <a name="phase-4-deploy-the-sharepoint-recovery-farm-in-azure"></a>階段4：在 Azure 中部署 SharePoint 復原伺服器陣列

根據設計方案，在您的虛擬網路中部署 SharePoint 伺服器陣列。 檢查 azure[基礎結構服務上的 SharePoint 2013](/previous-versions/azure/dn275958(v=azure.100)) ，以在 azure 中部署 SharePoint 角色之前，可能會有所説明。
  
請考慮我們透過建立概念證明環境所學到的下列做法：
  
- 使用 Azure 入口網站或 PowerShell 建立虛擬機器。
    
- Azure 和 Hyper-V 不支援動態記憶體。 請確定這會考慮您的效能與容量計劃。
    
- 透過 Azure 介面重新開機虛擬機器，而非來自虛擬機器登入本身。 使用 Azure 介面會更好地運作，而且更具可預測性。
    
- 如果您想要關閉虛擬機器以節約成本，請使用 Azure 介面。 如果您從虛擬機器登入關閉，費用仍會繼續累算。
    
- 使用虛擬機器的命名慣例。
    
- 請留意虛擬機器部署所在的資料中心位置。
    
- SharePoint 角色不支援 Azure 中的自動縮放功能。
    
- 請勿在伺服器陣列中設定將要還原的專案，例如網站集合。 
    
## <a name="phase-5-set-up-dfsr-between-the-farms"></a>階段5：設定伺服器陣列之間的 DFSR

若要使用 DFSR 設定檔複寫，請使用 DNS 管理嵌入式管理單元。 不過，在 DFSR 設定之前，請登入您的內部部署檔案伺服器和 Azure 檔案伺服器，並在 Windows 中啟用服務。
  
在 [伺服器管理員] 儀表板中，完成下列步驟：
  
- 設定本機伺服器。
    
- 啟動 **[新增角色及功能精靈]**。
    
- 開啟 [檔案 **和儲存體服務**] 節點。
    
- 選取 [ **Dfs 命名空間** 及 **dfs** 複寫]。
    
- 按 **[下一步** ] 完成嚮導的步驟。
    
下表提供 DFSR 參考文章和博客文章的連結。
  
**表： DFSR 的參考文章**

|**標題**|**描述**|
|:-----|:-----|
|[複製](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770278(v=ws.11)) <br/> |具有複寫連結的 DFS 管理 TechNet 主題  <br/> |
|[DFS 複寫：倖存指南](https://go.microsoft.com/fwlink/p/?LinkId=392737) <br/> |包含 DFS 資訊連結的 Wiki  <br/> |
|[DFS 複寫：常見問題](/previous-versions/windows/it-pro/windows-server-2003/cc773238(v=ws.10)) <br/> |DFS 複寫 TechNet 主題  <br/> |
|[聖約瑟 Barreto 的博客](/archive/blogs/josebda/) <br/> |Microsoft 的檔案伺服器小組主要程式管理員撰寫的博客  <br/> |
|[Microsoft 檔案檔案櫃博客的儲存體小組](https://go.microsoft.com/fwlink/p/?LinkId=392740) <br/> |關於 Windows Server 中的檔案服務和儲存功能的博客  <br/> |
   
## <a name="phase-6-set-up-log-shipping-to-the-recovery-farm"></a>階段6：設定對復原伺服器陣列的記錄傳送

「記錄傳送」是在此環境中設定嚴重損壞修復的重要元件。 您可以使用記錄傳送，將資料庫的交易記錄檔從主要資料庫伺服器實例自動傳送至輔助資料庫伺服器實例。 若要設定記錄傳送，請參閱[在 2013 SharePoint 中設定記錄傳送](/sharepoint/administration/configure-log-shipping)。 
  
> [!IMPORTANT]
> SharePoint Server 中的記錄傳送支援僅限特定資料庫。 如需詳細資訊，請參閱[SharePoint 資料庫支援的高可用性和嚴重損壞修復選項 (SharePoint 2013) ](/SharePoint/administration/supported-high-availability-and-disaster-recovery-options-for-sharepoint-databas)。 
  
## <a name="phase-7-validate-failover-and-recovery"></a>階段7：驗證容錯移轉和復原

此項最後階段的目的是驗證嚴重損壞修復解決方案的運作方式是否為已計畫。 若要這麼做，請建立容錯移轉事件，以關閉實際執行伺服器陣列，並以取代的方式啟動復原伺服器陣列。 您可以手動或透過使用腳本來啟動容錯移轉案例。
  
第一步是停止傳入的使用者伺服器陣列服務或內容的要求。 若要執行此動作，您可以停用 DNS 專案或關閉前端網頁伺服器。 伺服器陣列 "停機" 後，您就可以容錯移轉至復原伺服器陣列。
  
### <a name="stop-log-shipping"></a>停止記錄傳送

在伺服器陣列復原之前，您必須停止記錄傳送。 請先停止 Azure 中次要伺服器上的記錄傳送，然後再將它停止在內部部署的主伺服器上。 在第一部伺服器上，使用下列腳本停止記錄傳送，然後再停止主伺服器上的記錄傳送。 腳本中的資料庫名稱可能會不同，這要視您的環境而定。
  
```
-- This script removes log shipping from the server.
-- Commands must be executed on the secondary server first and then on the primary server.

SET NOCOUNT ON
DECLARE  @PriDB nvarchar(max)
,@SecDB nvarchar(250)
,@PriSrv nvarchar(250)
,@SecSrv nvarchar(250)

Set @PriDB= ''
SET @PriDB = UPPER(@PriDB)
SET @PriDB = REPLACE(@PriDB, ' ', '')
SET @PriDB = '''' + REPLACE(@PriDB, ',', ''', ''') + ''''

Set @SecDB = @PriDB

Exec ( 'Select  ''exec master..sp_delete_log_shipping_secondary_database '' + '''''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_primary_secondary '' + '''''''' + prm.Primary_Database + '''''', '''''' + sec.Secondary_Server + '''''', '''''' + sec.Secondary_database + ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_primary_database '' + '''''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_secondary_primary '' + '''''''' + prm.primary_server + '''''', '''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

```

### <a name="restore-the-backups"></a>還原備份

備份必須以建立的順序還原。 在還原特定的交易記錄檔備份之前，必須先還原下列先前的備份，而不回退未提交的交易 (也就是說，也就是使用  `WITH NORECOVERY`) ：
  
- 完整資料庫備份及最後一個差異備份-還原這些備份（若有的話），在特定交易記錄備份之前進行。 在建立最近的完整資料庫備份或差異資料庫備份之前，資料庫使用的是完整復原模式或大容量記錄復原模式。
    
- 所有交易記錄檔備份-還原完整資料庫備份或差異備份之後所進行的任何交易記錄檔備份。如果您還原一) ，且在特定交易記錄備份之前，請執行 (。 記錄備份必須依其建立的順序套用，不含記錄鏈中的任何間隙。
    
若要復原次要伺服器上的內容資料庫，讓網站能夠轉譯，請在復原之前移除所有資料庫連線。 若要還原資料庫，請執行下列 SQL 語句。
  
```
restore database WSS_Content with recovery

```

> [!IMPORTANT]
> 當您明確使用 T-SQL 時，請在每個 RESTORE 語句中指定 **with NORECOVERY** or **with RECOVERY** ，以消除多義性，這在撰寫腳本時非常重要。 還原完整和差異備份後，可在 SQL Server Management Studio 中還原交易記錄。 此外，因為已停止記錄傳送，所以內容資料庫處於待機狀態，所以您必須將狀態變更為 [完整存取]。
  
在 SQL Server Management Studio 中，以滑鼠右鍵按一下 **WSS_Content** 資料庫，指向 [**任務**  >  **還原**]，然後按一下 [**交易記錄** 檔 (]。如果您未還原完整備份，) 將無法使用此功能。 如需詳細資訊，請參閱[還原交易記錄備份 (SQL Server) ](/sql/relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server)。
  
### <a name="crawl-the-content-source"></a>編目內容來源

您必須啟動每個內容來源的完整編目，才可還原搜尋服務。 請注意，您會失去來自內部部署伺服器陣列的某些分析資訊，例如搜尋建議。 在您開始完整編目之前，請使用 Windows PowerShell Cmdlet **Restore-SPEnterpriseSearchServiceApplication** ，並指定記錄傳送及複寫的搜尋管理資料庫， **Search_Service__DB_ <GUID>**。 此 Cmdlet 會提供搜尋設定、架構、managed 屬性、規則和來源，並建立其他元件的預設集合。
  
若要開始完整編目，請完成下列步驟：
  
1. 在 SharePoint 2013 管理中心中，移至 **應用程式管理**  >  **服務應用程式**  >  **管理服務應用** 程式，然後按一下您要編目的 Search Service 應用程式。
    
2. 在 [ **搜尋管理** ] 頁面上，按一下 [ **內容來源**]，指向您想要的內容來源，按一下箭號，然後按一下 [ **啟動完整** 編目]。
    
### <a name="recover-farm-services"></a>復原伺服器陣列服務

下表顯示如何復原具有記錄傳送資料庫的服務、具有資料庫但不建議使用記錄傳送還原的服務，以及沒有資料庫的服務。
  
> [!IMPORTANT]
> 將內部部署 SharePoint 資料庫還原到 azure 環境中，不會復原您在 azure 中已手動安裝的任何 SharePoint 服務。 
  
**表：服務應用程式資料庫參考**

|**從記錄傳送的資料庫還原這些服務**|**這些服務具有資料庫，但建議您在不還原其資料庫的情況下啟動這些服務**|**這些服務不會將資料儲存在資料庫中;容錯移轉後啟動這些服務**|
|:-----|:-----|:-----|
| 機器翻譯服務 <br/>  Managed Metadata Service <br/>  Secure Store Service <br/>  使用者設定檔。  (只支援設定檔和社交標記資料庫。 不支援同步處理資料庫。 )  <br/>  Microsoft SharePoint Foundation 訂閱設定服務 <br/> | Usage and Health Data Collection <br/>  狀態服務 <br/>  Word automation <br/> | Excel Services <br/>  PerformancePoint Services <br/>  PowerPoint 轉換 <br/>  Visio Graphics Service <br/>  Work Management <br/> |
   
下列範例顯示如何從資料庫還原 Managed Metadata service。
  
這會使用現有的 Managed_Metadata_DB 資料庫。 此資料庫為記錄傳送，但是在次要伺服器陣列上沒有任何使用中的服務應用程式，因此在服務應用程式就緒後，必須進行連線。
  
首先，使用  `New-SPMetadataServiceApplication` ，並指定  `DatabaseName` 具有還原資料庫名稱的參數。
  
接下來，在次要伺服器上設定新的 Managed Metadata Service 應用程式，如下所示：
  
- 名稱： Managed Metadata Service
    
- 資料庫伺服器：已運送交易記錄檔中的資料庫名稱
    
- 資料庫名稱： Managed_Metadata_DB
    
- 應用程式集區： SharePoint 服務應用程式 
    
### <a name="manage-dns-records"></a>管理 DNS 記錄

您必須手動建立 DNS 記錄，以指向您的 SharePoint 伺服器陣列。
  
在大多數前端網頁伺服器的情況下，使用 Windows Server 2012 或硬體負載平衡器中的網路負載平衡功能，可在伺服器陣列中的 web 前端伺服器間散佈要求。 網路負載平衡也可以將要求散佈至其他伺服器，以協助降低風險，如果其中一部 web 前端伺服器失敗。 
  
一般來說，當您設定網路負載平衡時，您的叢集會被指派單一 IP 位址。 接著，您可以在網路的 DNS 提供者中建立指向該叢集的 DNS 主機記錄。  (針對此專案，我們會在 Azure 中放置一個 DNS 伺服器以進行復原，以防內部部署資料中心失敗。 ) 例如，您可以在 Active Directory 的 DNS 管理員中建立 DNS 記錄，例如，稱為  `https://sharepoint.contoso.com` ，指向您負載平衡叢集的 IP 位址。
  
針對您的 SharePoint 伺服器陣列，您可以在外部 DNS 伺服器上使用用戶端使用的相同 URL 來建立主機記錄 (例如， `https://sharepoint.contoso.com`) 指向防火牆中的外部 IP 位址。  (使用此範例的最佳作法是設定分割 DNS，讓內部 DNS 伺服器直接對 SharePoint 伺服器陣列叢集進行授權 `contoso.com` 和路由要求，而不是將 DNS 要求路由傳送至外部 DNS 伺服器。 ) 您可以將外部 IP 位址對應至內部部署叢集的內部 IP 位址，讓用戶端找到他們所要尋找的資源。
  
從這裡，您可能會遇到幾個不同的災害復原案例：
  
 **範例案例：內部部署 SharePoint 伺服器陣列因內部部署 SharePoint 伺服器陣列中的硬體故障而無法使用。** 在此情況下，在您完成容錯移轉至 Azure SharePoint 伺服器陣列的步驟之後，您可以在復原 SharePoint 伺服器陣列的 web 前端伺服器上設定網路負載平衡，其方式與使用內部部署伺服器陣列的方式相同。 然後，您可以重新導向內部 DNS 提供者中的主機記錄，以指向復原伺服器陣列的叢集 IP 位址。 請注意，在重新整理用戶端的快取 DNS 記錄之前，可能需要一些時間，並指向復原伺服器陣列。
  
 **範例案例：內部部署資料中心完全遺失。** 這種情況可能是由於自然災害，例如火災或洪水引起。 在此情況下，針對企業，您可能會在另一個區域中裝載次要資料中心，以及您的 Azure 子網具有自己的目錄服務和 DNS。 如先前的嚴重情況，您可以重新導向您的內部和外部 DNS 記錄，以指向 Azure SharePoint 伺服器陣列。 另外請注意，DNS 記錄傳播可能需要一些時間。
  
如果您使用主機命名型網站集合（如[主機命名型網站集合架構和部署 (](/SharePoint/administration/host-named-site-collection-architecture-and-deployment)中所建議的） SharePoint 2013) ，則 SharePoint 伺服器陣列中的相同 web 應用程式可能會有多個網站集合，且有唯一的 DNS 名稱 (例如， `https://sales.contoso.com` 及 `https://marketing.contoso.com`) 。 在此情況下，您可以針對每個指向您的叢集 IP 位址的網站集合建立 DNS 記錄。 要求到達您 SharePoint 的 web 前端伺服器後，它們會處理每個要求的路由傳送至適當的網站集合。
  
## <a name="microsoft-proof-of-concept-environment"></a>Microsoft 概念證明環境

我們為此方案設計及測試了概念證明環境。 測試環境的設計目標是部署及復原我們在客戶環境中所找到的 SharePoint 伺服器陣列。 我們進行了數個假設，但我們知道，伺服器陣列必須提供所有現成的功能，而不需要任何自訂。 拓撲的設計方式是使用來自欄位及產品群組的最佳做法指導方針，以取得高可用性。
  
下表說明為內部部署測試環境建立及設定的 Hyper-V 虛擬機器。
  
**表：內部部署測試的虛擬機器**

|**伺服器名稱**|**Role**|**設定**|
|:-----|:-----|:-----|
|DC1  <br/> |使用 Active Directory 的網域控制站。  <br/> |兩個處理器  <br/> 從 512 MB 到 4 GB 的 RAM  <br/> 1 x 127 GB 的硬碟  <br/> |
|RRAS  <br/> |以路由和遠端存取服務設定 (RRAS) role 的伺服器。  <br/> |兩個處理器  <br/> 2-8 GB 的 RAM  <br/> 1 x 127 GB 的硬碟  <br/> |
|FS1  <br/> |包含備份共用的檔案伺服器，以及 DFSR 的端點。  <br/> |四個處理器  <br/> 2-12 GB 的 RAM  <br/> 1 x 127 GB 的硬碟  <br/> 1 x 1 TB 的硬碟 (SAN)   <br/> 1 x 750 GB 的硬碟  <br/> |
|SP-WFE1，SP-WFE2  <br/> |前端網頁伺服器。  <br/> |四個處理器  <br/> 16 GB 的 RAM  <br/> |
|SP-APP1，SP-1 APP2，SP-1 APP3  <br/> |應用程式伺服器。  <br/> |四個處理器  <br/> 2-16 GB 的 RAM  <br/> |
|SP-SQL-HA1，SP-SQL-HA2  <br/> |使用 SQL Server 2012 設定的資料庫伺服器 AlwaysOn 可用性群組，以提供高可用性。 這種設定會使用 SP-SQL-HA1 和 SP-SQL-HA2 做為主要和次要複本。  <br/> |四個處理器  <br/> 2-16 GB 的 RAM  <br/> |
   
下表說明為內部部署測試環境的前端網頁伺服器和應用程式伺服器建立及設定的 Hyper-V 虛擬機器的磁片磁碟機設定。
  
**表：內部部署測試的前端 Web 和應用程式伺服器的虛擬機器磁碟機需求**

|**磁碟機號**|**大小**|**目錄名稱**|**Path**|
|:-----|:-----|:-----|:-----|
|C  <br/> |80  <br/> |系統磁片磁碟機  <br/> |<DriveLetter>： \\ 程式檔案 \\ Microsoft SQL Server\\  <br/> |
|E  <br/> |80  <br/> |記錄磁片磁碟機 (40 GB)   <br/> |<DriveLetter>： \\ Program Files \\ Microsoft SQL Server \\ MSSQL10_50 MSSQLSERVER \\ MSSQL \\ 資料  <br/> |
|F  <br/> |80  <br/> |頁面 (36 GB)   <br/> |<DriveLetter>： \\ Program Files \\ Microsoft SQL Server \\ MSSQL \\ 資料  <br/> |
   
下表說明建立並設定為內部部署資料庫伺服器的 Hyper-V 虛擬機器的磁片磁碟機設定。 在 [**資料庫引擎** 設定] 頁面上，存取 [**資料目錄**] 索引標籤以設定及確認下表所示的設定。
  
**表：內部部署測試的資料庫伺服器的虛擬機器磁碟機需求**

|**磁碟機號**|**大小**|**目錄名稱**|**Path**|
|:-----|:-----|:-----|:-----|
|C  <br/> |80  <br/> |資料根目錄  <br/> |<DriveLetter>： \\ 程式檔案 \\ Microsoft SQL Server\\  <br/> |
|E  <br/> |500  <br/> |使用者資料庫目錄  <br/> |<DriveLetter>： \\ Program Files \\ Microsoft SQL Server \\ MSSQL10_50 MSSQLSERVER \\ MSSQL \\ 資料  <br/> |
|F  <br/> |500  <br/> |使用者資料庫記錄目錄  <br/> |<DriveLetter>： \\ Program Files \\ Microsoft SQL Server \\ MSSQL10_50 MSSQLSERVER \\ MSSQL \\ 資料  <br/> |
|G  <br/> |500  <br/> |Temp DB 目錄  <br/> |<DriveLetter>： \\ Program Files \\ Microsoft SQL Server \\ MSSQL10_50 MSSQLSERVER \\ MSSQL \\ 資料  <br/> |
|H  <br/> |500  <br/> |Temp DB 記錄目錄  <br/> |<DriveLetter>： \\ Program Files \\ Microsoft SQL Server \\ MSSQL10_50 MSSQLSERVER \\ MSSQL \\ 資料  <br/> |
   
### <a name="setting-up-the-test-environment"></a>設定測試環境

在不同的部署階段中，測試小組通常會在內部部署架構上先進行，然後再于對應的 Azure 環境上進行處理。 這會反映內部生產伺服器陣列已經執行的一般實際案例。 更為重要的是，您應該知道目前的實際執行工作量、容量及一般效能。 除了建立可滿足業務需求的嚴重損壞復原模式之外，您還應該調整復原伺服器陣列伺服器的大小，以提供最低的服務等級。 在 cold 或暖色待命環境中，復原伺服器陣列通常會比實際執行伺服器陣列小。 在復原伺服器陣列穩定且投入實際執行後，可將伺服器陣列向上及向內擴充，以符合工作負載需求。
  
我們已在下列三個階段部署測試環境：
  
- 設定混合式基礎結構
    
- 布建伺服器
    
- 部署 SharePoint 伺服器陣列
    
#### <a name="set-up-the-hybrid-infrastructure"></a>設定混合式基礎結構

此階段涉及為內部部署伺服器陣列和 Azure 中的復原伺服器陣列設定網域環境。 除了與設定 Active Directory 相關的一般工作之外，測試小組還會在兩個環境間執行路由解決方案和 VPN 連線。
  
#### <a name="provision-the-servers"></a>布建伺服器

除了伺服器陣列的伺服器之外，還需要布建網域控制站的伺服器，並設定伺服器來處理 RRAS，以及網站對網站的 VPN。 已布建了 DFSR 服務的兩個檔案伺服器，並且為測試人員布建了許多用戶端電腦。
  
#### <a name="deploy-the-sharepoint-farms"></a>部署 SharePoint 伺服器陣列

SharePoint 伺服器陣列是以兩個階段進行部署，以簡化環境穩定化及疑難排解（如有必要）。 在第一個階段中，每個伺服器陣列都是針對拓撲的各層級的伺服器上的最低數目部署，以支援必要的功能。
  
在建立 SharePoint 2013 伺服器之前，我們會建立 SQL Server 已安裝的資料庫伺服器。 由於這是新的部署，因此我們先建立可用性群組，再部署 SharePoint。 我們會根據 MCS 最佳做法指導方針建立三個群組。 
  
> [!NOTE]
> 建立預留位置資料庫，這樣您就可以在安裝 SharePoint 之前建立可用性群組。 如需詳細資訊，請參閱[Configure SQL Server 2012 AlwaysOn Availability Groups for SharePoint 2013](/SharePoint/administration/configure-an-alwayson-availability-group)
  
我們依下列順序建立伺服器陣列及加入其他伺服器：
  
- 布建 SP-SQL-HA1 和 SP-SQL-HA2。
    
- 設定 AlwaysOn，並為伺服器陣列建立三個可用性群組。 
    
- 布建主控管理中心的 SP-APP1。
    
- 布建 SP-WFE1 和 SP-WFE2 以主控分散式快取。 
    
我們在命令列上執行 **psconfig.exe** 時使用 _skipRegisterAsDistributedCachehost_ 參數。 如需詳細資訊，請參閱[Plan for feed and 分散式快取服務 in SharePoint Server 2013](/sharepoint/administration/plan-for-feeds-and-the-distributed-cache-service)。 
  
我們在復原環境中重複下列步驟：
  
- 布建 AZ-SQL-HA1 和 AZ SQL-HA2。
    
- 設定 AlwaysOn，並為伺服器陣列建立三個可用性群組。
    
- 提供 AZ-APP1 以主控管理中心。
    
- 布建 AZ-WFE1 和 WFE2 以主控分散式快取。
    
設定好分散式快取並新增測試使用者和測試內容之後，我們已開始第二階段的部署。 這需要將層級和設定為支援伺服器陣列架構中所述的高可用性拓撲。
  
下表說明我們為復原伺服器陣列設定的虛擬機器、子網及可用性設定。
  
**表：復原伺服器陣列基礎結構**

|**伺服器名稱**|**Role**|**設定**|**子網路**|**可用性設定組**|
|:-----|:-----|:-----|:-----|:-----|
|spDRAD  <br/> |使用 Active Directory 的網域控制站  <br/> |兩個處理器  <br/> 從 512 MB 到 4 GB 的 RAM  <br/> 1 x 127 GB 的硬碟  <br/> |sp-ADservers  <br/> ||
|AZ-SP-FS  <br/> |含備份共用及 DFSR 端點的檔案伺服器  <br/> | A5 設定： <br/>  兩個處理器 <br/>  14 GB 的 RAM <br/>  1 x 127 GB 的硬碟 <br/>  1 x 135 GB 的硬碟 <br/>  1 x 127 GB 的硬碟 <br/>  1 x 150 GB 的硬碟 <br/> |sp-databaseservers  <br/> |DATA_SET  <br/> |
|AZ-WFE1，AZ-WFE2  <br/> |前端網頁伺服器  <br/> | A5 設定： <br/>  兩個處理器 <br/>  14 GB 的 RAM <br/>  1 x 127 GB 的硬碟 <br/> |sp-webservers  <br/> |WFE_SET  <br/> |
|AZ-APP1，AZ-APP2，AZ-APP3  <br/> |應用程式伺服器  <br/> | A5 設定： <br/>  兩個處理器 <br/>  14 GB 的 RAM <br/>  1 x 127 GB 的硬碟 <br/> |sp-applicationservers  <br/> |APP_SET  <br/> |
|AZ-SQL-HA1，AZ SQL-HA2  <br/> |資料庫伺服器及主要和次要複本 AlwaysOn 可用性群組  <br/> | A5 設定： <br/>  兩個處理器 <br/>  14 GB 的 RAM <br/> |sp-databaseservers  <br/> |DATA_SET  <br/> |
   
### <a name="operations"></a>作業

測試小組穩定了伺服器陣列環境及已完成的功能測試之後，他們會啟動設定內部部署復原環境所需的下列作業工作：
  
- 設定完整和差異備份。
    
- 在內部部署環境和 Azure 環境之間的檔案伺服器上設定 DFSR，以傳輸交易記錄。
    
- 在主資料庫伺服器上設定記錄傳送。
    
- 視需要進行穩定、驗證及疑難排解記錄傳送。 這包括識別及記錄可能造成問題的任何行為，例如網路延遲，這會導致記錄傳送或 DFSR 檔同步處理失敗。
    
### <a name="databases"></a>資料庫

我們的容錯移轉測試包含下列資料庫： 
  
- WSS_Content
    
- ManagedMetadata
    
- Profile DB
    
- Sync DB
    
- 社交 DB
    
- 內容類型中樞 (專用內容類型整合中樞的資料庫) 
    
## <a name="troubleshooting-tips"></a>疑難排解提示

本節說明我們在測試期間所遇到的問題，以及其解決方案。 
  
### <a name="using-the-term-store-management-tool-caused-the-error-the-managed-metadata-store-or-connection-is-currently-not-available"></a>使用術語存放區管理工具導致錯誤 "Managed Metadata Store 或 Connection 目前無法使用。

確定 web 應用程式使用的應用程式集區帳戶具有字詞存放區許可權的「讀取」許可權。
  
### <a name="custom-term-sets-are-not-available-in-the-site-collection"></a>無法在網站集合中使用自訂字詞集

檢查您的內容網站集合與內容類型中樞之間是否有遺失的服務應用程式關聯。 此外，在 [ **受管理的元 <site collection name> 資料-** 線上內容] 畫面底下，確定已啟用此選項： **此服務應用程式是欄特定字詞集的預設儲存位置。**
  
### <a name="the-get-adforest-windows-powershell-command-generates-the-error-the-term-get-adforest-is-not-recognized-as-the-name-of-a-cmdlet-function-script-file-or-operable-program"></a>Get-ADForest Windows PowerShell 命令會產生錯誤，「字詞 ' ADForest ' 不會被辨識為 Cmdlet、function、script file 或可運行程式的名稱。

設定使用者設定檔時，您需要使用 Active Directory 樹系名稱。 在 [新增角色及功能] 嚮導中，確定已在 [**遠端伺服器管理工具>ad DS 和 ad LDS 工具**]) 區段中，啟用 Windows PowerShell (的 Active Directory 模組>。 此外，在使用 **ADForest** 之前，請先執行下列命令，以協助確保載入您的軟體相依性。
  
```
Import-module servermanager
Import-module activedirectory

```

### <a name="availability-group-creation-fails-at-starting-the-alwayson_health-xevent-session-on-server-name"></a>在 ' ' 上開始 ' AlwaysOn_health ' XEvent 會話」時，可用性群組建立失敗 <server name>

確定容錯移轉叢集的兩個節點都處於「Up」狀態，而不是「已暫停」或「已停止」。 
  
### <a name="sql-server-log-shipping-job-fails-with-access-denied-error-trying-to-connect-to-the-file-share"></a>在嘗試連線至檔案共用時，存取權遭到拒絕時，SQL Server 記錄傳送作業失敗

確定您的 SQL Server 代理程式是在 [網路認證] （而非預設認證）下執行。
  
### <a name="sql-server-log-shipping-job-indicates-success-but-no-files-are-copied"></a>SQL Server 記錄傳送工作會指出成功，但不會複製檔案

發生這種情況是因為可用性群組的預設備份喜好設定 **優先于第二** 個。 確定您從可用性群組的次要伺服器（而非主要）執行記錄傳送工作。否則，工作將會以無訊息的方式失敗。 
  
### <a name="managed-metadata-service-or-other-sharepoint-service-fails-to-start-automatically-after-installation"></a>在安裝之後，Managed Metadata service (或其他 SharePoint 服務) 無法自動啟動

服務可能需要數分鐘的時間，視效能和目前負載的 SharePoint 伺服器而定。 手動按一下服務的 [ **啟動** ]，並提供足夠的啟動時間，以偶爾重新整理伺服器畫面上的服務來監視其狀態。 若服務保持停止狀態，請啟用 SharePoint 診斷記錄，然後再次嘗試啟動服務，然後檢查記錄是否有錯誤。 如需詳細資訊，請參閱[Configure SharePoint 2013 中的診斷記錄](/sharepoint/administration/configure-diagnostic-logging)
  
### <a name="after-changing-dns-to-the-azure-failover-environment-client-browsers-continue-to-use-the-old-ip-address-for-the-sharepoint-site"></a>將 DNS 變更為 Azure 容錯移轉環境之後，用戶端瀏覽器會繼續使用舊的 SharePoint 網站的 IP 位址。

您的 DNS 變更可能不會立即對所有用戶端顯示。 在測試用戶端上，從提升許可權的命令提示字元中執行下列命令，然後再次嘗試存取網站。
  
```
Ipconfig /flushdns
```

## <a name="additional-resources"></a>其他資源

[SharePoint 資料庫支援的高可用性和災害復原選項](/sharepoint/administration/supported-high-availability-and-disaster-recovery-options-for-sharepoint-databas)
  
[為 SharePoint 2013 設定 SQL Server 2012 AlwaysOn 可用性群組](/SharePoint/administration/configure-an-alwayson-availability-group)
  
## <a name="see-also"></a>另請參閱

[Microsoft 365 解決方案與架構中心](../solutions/index.yml)