---
title: 適用于企業的 Microsoft 365 租使用者管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- m365solution-overview
- tenant-management
ms.custom:
- Ent_Solutions
description: 您的 Microsoft 365 承租人的規劃、部署及日常運作的概況。
ms.openlocfilehash: 42bde00fbd4ddc1cf92236f099a22b2260dbb980
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405675"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>適用于企業的 Microsoft 365 租使用者管理

若要建立您組織的數位轉換與雲端計算的路徑，需要一個可靠的基礎，讓您的工作人員可以以生產力、共同作業、效能、隱私權、合規性和安全性為基礎。

正確設定 Microsoft 365 租使用者可提供該基礎，讓您的工作人員致力於完成其工作，並讓您的 IT 部門專注于提供其他商業價值的端對端解決方案。 

此解決方案會透過下列步驟，透過該基礎進行設定：

1. 決定您的承租人
2. 優化網路
3. 同步處理您的身分識別並強制執行安全登入
4. 遷移您的 Windows 裝置、Office 用戶端，以及內部部署 Office 伺服器及資料
5. 部署裝置和應用程式管理

不過，首先讓我們花一些時間來瞭解租使用者是什麼，以及提供公司基礎的承租人的外觀。

## <a name="a-microsoft-365-tenant-defined"></a>定義的 Microsoft 365 租使用者

Microsoft 365 租使用者是 Microsoft 365 服務的專用實例，以及儲存在特定預設位置（例如歐洲或北美地區）的組織資料。 當您為組織建立租使用者時，就會指定此位置。 每個 Microsoft 365 租使用者都是獨特、獨特的，並與其他所有 Microsoft 365 承租人分開。 當您購買一或多個 Microsoft 的產品，例如 Microsoft 365 E3 或 E5，以及每個產品的授權集時，您會建立 Microsoft 365 租使用者。

您的 Microsoft 365 租使用者也包含 Azure Active Directory (azure ad) 租使用者，該租使用者帳戶、群組及其他物件的 azure ad 專用實例。 每個 Azure AD 租使用者皆為 distinct，unique，與其他所有 Azure AD 租使用者分開。 雖然您的組織可以有多個可使用 azure 訂閱設定的 azure ad 租使用者，Microsoft 365 租使用者才能使用單一 Azure ad 租使用者，這是您建立租使用者時所建立的承租人。 

範例如下：

![使用 Azure AD 租使用者 Microsoft 365 承租人的範例](../media/tenant-management-overview/tenant-management-example-tenant.png)

*租使用者管理* 是 Microsoft 365 承租人的規劃、部署及日常運作。 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>設計完善且運作租使用者的屬性

除了正確的承租人名稱和位置以外，還有其他一些元素可用於規劃、部署和管理，以確保您的使用者體驗 &mdash; Microsoft Teams 和 Exchange Online 等雲端生產力應用程式 &mdash; 是有效、安全和高性能。

以下是元素：

- 您有一組正確的產品 (訂閱) 和授權。
  - 產品集合符合您的業務、IT 及安全性需求。
  - 您的工作人員和人員的預期變更有適當數量的授權。
- 若為網路：
  - 您已設定正確的 DNS 功能變數名稱。
  - 針對商業網路，您已針對現場工作者的 Microsoft 網路優化網路流量。
  - 您已針對使用 VPN 用戶端的遠端工作者優化網路流量。
- 您已同步處理 Active Directory 網域服務 (AD DS) 帳戶、群組及其他物件。
  - 您的 Azure AD 租使用者帳戶會對應至具有正確 DNS 網域之電子郵件地址的 Exchange Online 信箱。
  - 您的使用者帳戶已被指派正確購買產品 (例如 Microsoft 365 E3 或 E5) 的授權。
- 您已設定強身分識別和存取管理。
  - 您需要使用 passwordless 或多重要素驗證 (MFA) 進行安全的使用者登入。
  - 您有條件式存取原則，可強制登入需求和限制更高的安全性層級。
- 內部部署 Office 伺服器及其資料已遷移至雲端應用程式，或是混合式設定中使用。
- 您正在使用 Microsoft 365 內建的 Intune 或基本行動及安全性進行裝置管理。
  - 組織擁有的裝置會註冊並管理。
  - 管理個人裝置的應用程式。

以下是具有所有這些元素的 Microsoft 365 承租人的範例。

![承租人 Microsoft 365 範例](../media/tenant-management-overview/tenant-management-tenant-config.png)

在此圖中，Microsoft 365 承租人包括：

- Microsoft 365 E3 和 E5 的產品及授權。
- Microsoft 365 生產力應用程式。
- 使用註冊裝置和裝置及應用程式原則的 Intune。
- 具有同步處理使用者帳戶 (群組和其他目錄物件的 Azure AD 租使用者不會顯示) 、網域和條件式存取原則。

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>適用于企業的 Microsoft 365 租使用者功能

下列各節和表格列出此方案中步驟的主要功能及授權。

### <a name="tenant"></a>租用戶

| 功能 | 描述 | 授權 |
|:-------|:-----|:-------|
| 多個租用戶 | 每個 Microsoft 365 租使用者都是獨特、獨特的，並與其他所有 Microsoft 365 承租人分開。 使用多個承租人時，在管理及為使用者提供服務時會有一些限制與其他考慮。 | Microsoft 365 E3 或 E5 | 
| 跨租用戶信箱移轉 | 租使用者管理員可以在承租人之間移動信箱，但其內部部署系統中的基礎結構相依性最低。 這樣就不再需要離線和上架信箱。 | Microsoft 365 E3 或 E5 | 
| 多地理位置 | 您的租使用者可以將靜態資料儲存在其他資料中心地理位置，您已選擇這些地理位置，以符合資料派駐要求。 | Microsoft 365 E3 或 E5 | 
| 將核心資料移至新的資料中心地理位置 | 當 Microsoft 新增新的資料中心 geos 以取得額外的容量及計算資源時，您可以針對您的核心客戶資料要求針對地理位置的資料派駐服務，要求資料中心地理位置移動。 | Microsoft 365 E3 或 E5 | 
||||

### <a name="networking"></a>網路功能

| 功能 | 描述 | 授權 |
|:-------|:-----|:-------|
| 網路洞察力 | 從 Microsoft 365 租使用者收集的網路效能度量，協助您為辦公室位置設計網路周邊。 | Microsoft 365 E3 或 E5 | 
| 自動化端點更新 | 為用戶端 PAC 檔案和網路裝置及服務中的 Microsoft 365 端點自動化設定和持續更新。 | Microsoft 365 E3 或 E5 | 
||||

### <a name="identity"></a>身分識別

| 功能 | 描述 | 授權 |
|:-------|:-----|:-------|
| 使用您的 Azure AD 租使用者同步處理內部部署 Active Directory 網域服務 (AD DS)     | 針對使用者帳戶、群組及其他物件，利用您的內部部署身分識別提供者。 | Microsoft 365 E3 或 E5 |
| 採用安全性預設值強制執行 MFA   | 要求第二種形式的登入驗證，以防止身分識別和裝置遭到入侵。安全性預設值要求所有使用者帳戶使用 MFA。   | Microsoft 365 E3 或 E5 |
| 使用條件式存取強制執行 MFA| 根據具有條件式存取原則之登入的屬性，需要 MFA。    | Microsoft 365 E3 或 E5 | 
| 使用風險型條件式存取強制執行 MFA   | 根據使用適用於身分識別的 Microsoft Defender 的使用者登入的風險，要求使用 MFA。 | Microsoft 365 E5 或 E3 (含 Azure AD Premium P2 授權) | 
| 自助式密碼重設 (SSPR)    | 允許您的使用者重設或解除鎖定他們的密碼或帳戶。  | Microsoft 365 E3 或 E5 |
||||

### <a name="migration"></a>移轉

| 功能 | 描述 | 授權 |
|:-------|:-----|:-------|
| 移轉至 Windows 10 | 將執行 Windows 7 或 Windows 8.1 的裝置遷移至 Windows 10 企業版。 | Windows 10 企業版包含 Microsoft 365 E3 或 E5 的授權 | 
| 遷移至 Microsoft 365 Apps 企業版 | 將 Office 用戶端應用程式（如 Word）和 PowerPoint，遷移至以新功能更新的雲端版本。 | Microsoft 365 E3 或 E5 | 
| 將內部部署伺服器和資料移轉至 Microsoft 365 | 將您的 Exchange 信箱、SharePoint 網站和商務用 Skype 線上遷移，以 Microsoft 365 雲端服務。 | Microsoft 365 E3 或 E5 | 
||||

### <a name="device-and-app-management"></a>裝置和應用程式管理

| 功能 | 描述 | 授權 |
|:-------|:-----|:-------|
| Microsoft Intune | 提供行動裝置管理 (MDM) 和行動應用程式管理 (MAM) 的雲端式服務，可控制組織的應用程式和裝置的使用方式，包括行動電話、平板電腦和可擕式電腦。 | Microsoft 365 E3 或 E5 | 
| 設定基本行動與安全性 | 使用此內建服務，保護和管理使用者的行動裝置，例如 iphone、ipad、Androids 和 Windows 電話。  | Microsoft 365 E3 或 E5 | 
||||

## <a name="next-steps"></a>後續步驟

使用這些步驟來設定和管理您的 Microsoft 365 承租人。

1. [決定您的承租人](tenant-management-tenants.md)
2. [優化網路](tenant-management-networking.md)
3. [同步處理您的身分識別並強制執行安全登入](tenant-management-identity.md)
4. [遷移內部部署 Office 伺服器與資料](tenant-management-migration.md)
5. [部署裝置和應用程式管理](tenant-management-device-management.md)

[![部署及管理 Microsoft 365 租使用者的步驟](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

每個步驟都說明部署選項、摘要結果及日常維護工作。

若要瞭解虛構但具有代表性的跨國組織如何部署其 Microsoft 365 租使用者的元素，請參閱[Contoso 案例研究](../enterprise/contoso-case-study.md)。
