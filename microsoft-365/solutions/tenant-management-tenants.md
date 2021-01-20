---
title: 步驟 1： 您的 Microsoft 365 for enterprise 承租人
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
ms.custom:
- Ent_Solutions
description: 部署及管理單一或多個 Microsoft 365 承租人，包含多地理位置和移動位置的選項。
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908510"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>步驟 1. 您的 Microsoft 365 for enterprise 承租人

您第一個承租人決策是多少。 每個 Microsoft 365 租使用者都是獨特且獨特的，並與所有其他 Microsoft 365 承租人分開。 其對應的 Azure AD 租使用者也是獨特且獨特的，且與所有其他 Microsoft 365 承租人分開。

## <a name="single-tenant"></a>單一租使用者
擁有單一租使用者可簡化貴組織的許多部分使用 Microsoft 365。 單一租使用者代表單一 Azure AD 租使用者搭配一群組帳戶、群組和原則。 您整個組織中的資源許可權及共用均可透過此中央身分識別提供者進行。

單一承租人為您的使用者提供功能最豐富且簡化的共同作業和生產力體驗。

以下是一個範例，顯示 Microsoft 365 租使用者的預設位置和 Azure AD 租使用者。

![單一 Microsoft 365 租使用者及其 Azure AD 租使用者](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>多個租用戶

您的組織可能有多個承租人的原因有多種：

- 系統管理隔離
- 分散 IT
- 歷史決策
- 合併、收購或 divestitures
- 清除集團組織的品牌分隔
- 預先生產、測試或沙箱承租人

以下是一個組織範例，其中有兩個承租人 (承租人 A 與租使用者 B) 相同的預設資料中心地理位置。 每個租使用者都是個別 Azure AD 租使用者。

![使用自身 Azure AD 承租人的多個 Microsoft 365 承租人](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

當您有多個承租人時，系統會有限制及其他考慮，以加以管理並為使用者提供服務。

### <a name="inter-tenant-collaboration"></a>租用戶間共同作業

如果您想要讓您的使用者在安全的情況下更有效率地跨不同的 Microsoft 365 承租人進行共同作業，則租使用者共同作業選項包括使用中心位置來進行檔案與交談、共用行事曆、使用 IM、音訊/視頻通話進行通訊，以及保護資源和應用程式的存取。

如需詳細資訊，請參閱 [Microsoft 365 內部租使用者共同](../enterprise/microsoft-365-inter-tenant-collaboration.md)作業。

### <a name="cross-tenant-mailbox-migration-preview"></a>跨承租人信箱遷移 (預覽) 

在 [) 預覽] 中的跨承租人信箱遷移 (之前，您必須在承租人之間移動 Exchange Online 信箱，以完全下架使用者信箱的目前租使用者， (來源租使用者) 至內部部署，然後再將其上架至新租使用者 (。 使用新的跨租使用者信箱遷移功能，來源和目標承租人中的租使用者管理員可以在租使用者內部部署系統中的基礎結構相依性之間移動信箱。 這樣就不再需要離線和上架信箱。

以下是跨租使用者信箱遷移之前的兩個範例承租人和其信箱。

![多個 Microsoft 365 承租人及其信箱](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

在此圖中，兩個不同的承租人具有自己的網域和 Exchange 信箱集。

以下是在跨租使用者信箱遷移之後， (租使用者) 的目標租使用者。

![跨承租人信箱遷移之後的目標租使用者](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

在此圖中，單一租使用者同時有兩個網域和兩組 Exchange 信箱。

如需詳細資訊，請參閱 [跨租使用者信箱遷移](../enterprise/cross-tenant-mailbox-migration.md)。

### <a name="tenant-to-tenant-migrations"></a>租用戶到租用戶的移轉

合併、收購、divestitures 及其他案例有數種架構方法可能會讓您將現有的 Microsoft 365 租使用者遷移至新的租使用者。 

如需詳細指示，請參閱 [Microsoft 365 租使用者對租使用者遷移](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)。

## <a name="multi-geo-for-a-tenant"></a>承租人的多地理位置

使用 Microsoft 365 多地理位置，您可以在其他資料中心地理位置中布建和儲存資料，而這些地理位置是您已選擇符合資料派駐要求的位置，同時也會解除對您的工作人員進行現代生產力體驗的全域部署。

在多地理位置環境中，您的 Microsoft 365 租使用者是由預設或中央位置所組成，您的 Microsoft 365 訂閱最初是建立所在的位置，以及一個或多個衛星位置。 在多地理位置承租人中，地理位置、群組和使用者資訊的相關資訊，都是在全域 Azure AD 租使用者中使用。 因為您的承租人資訊已集中集中並同步處理到每個地理位置，所以與您公司的任何人共同作業的共同作業體驗都會在各位置間共用。

以下是一個組織的範例，其預設位置在歐洲和北美的一個衛星位置。 這兩個位置都共用單一 Microsoft 365 租使用者的相同全域 Azure AD 租使用者。

![多地理位置 Microsoft 365 租使用者範例](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

如需詳細資訊，請參閱 [Microsoft 365 多地理位置](../enterprise/microsoft-365-multi-geo.md)。

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>將核心資料移至新的資料中心地理位置

Microsoft 繼續開啟新的資料中心 geos for Microsoft 365 服務。 這些新的資料中心 geos 可增加容量及計算資源，以支援我們持續的客戶需求和使用量成長。 此外，新的資料中心 geos 提供核心客戶資料的地理位置資料派駐服務。

雖然開啟新的資料中心地理位置並不會影響您和您的核心資料儲存在現有的資料中心地理位置，但 Microsoft 可讓您要求將組織的核心客戶資料及早遷移至新的資料中心地理位置。

以下是 Microsoft 365 租使用者從歐盟 (歐盟) 從歐盟地理位置移至英國 (UK) 的範例。

![在資料中心 geos 之間移動 Microsoft 365 承租人的範例](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

如需詳細資訊，請參閱 [將核心資料移至新的 Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md)。

## <a name="products-and-licenses-for-a-tenant"></a>租使用者的產品和授權

當您購買第一種產品時（例如 Microsoft 365 E3），您的 Microsoft 365 租使用者即會建立。 除了產品之外，還會收取每月或每年費用的授權。 然後，系統管理員可以直接或透過群組成員資格，將其中一項產品的可用授權指派給使用者帳戶。 根據組織的業務需求，您可能有一組產品，每個產品都有自己的授權集區。 

若要判斷一組產品以及每個產品的授權數目，必須進行下列規劃：

- 確定您有足夠的授權，可供需要高級功能的使用者帳戶使用。
- 根據組織中人員的變更，防止您的授權不足或未指派授權的數目。


## <a name="results-of-step-1"></a>步驟 1 的結果

針對您的 Microsoft 365 for enterprise 承租人，您已決定：

- 您有多少租使用者或需要多少承租人。
- 每個租使用者必須購買的產品和授權。
- 承租人是否必須是多地理位置，以符合資料派駐要求。
- 您是否需要設定承租人間共同作業。
- 是否需要將一個承租人遷移至另一個承租人。
- 您是否需要將核心資料從一個資料中心地理位置移至新。

以下是新租使用者的範例。

![新租使用者的範例](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

在此圖中，租使用者有：

- 與 Microsoft 365 資料中心地理位置相對應的預設位置。
- 一組產品和授權。
- 雲端生產力應用程式的集合，有些專用於產品。
- 包含全域管理員帳戶和初始 DNS 功能變數名稱的 Azure AD 租使用者。

當我們流覽此解決方案的其他步驟時，我們將會培養此圖。

## <a name="ongoing-maintenance-for-tenants"></a>承租人的持續維護

您可能需要進行下列作業：

- 新增租使用者。
- 使用初始授權數目新增產品至租使用者。
- 變更承租人中產品的授權集，以調整員工需求的變更。
- 將核心資料從租使用者移至新的資料中心地理位置。
- 針對資料派駐服務需求新增多地理位置。
- 設定承租人間共同作業。

## <a name="next-step"></a>後續步驟

[![步驟2。為您的網路存取優化您的租使用者](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

繼續 [聯網](tenant-management-networking.md) ，以提供與您的工作人員的最佳網路與 Microsoft 365 雲端服務的連線。
