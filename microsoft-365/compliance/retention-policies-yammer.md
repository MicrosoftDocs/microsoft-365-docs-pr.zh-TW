---
title: 了解 Yammer 的保留
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 了解適用於 Yammer 的保留原則。
ms.openlocfilehash: 1398bf385631967d92de760924ef94e2b3c16441
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362291"
---
# <a name="learn-about-retention-for-yammer"></a>了解 Yammer 的保留

>*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

> [!NOTE]
> 此功能處於預覽階段，可能會有所變更。

本文中的資訊可補充[了解保留原則](retention.md)，因為其包含 Yammer 專用的資訊。

若為其他工作負載，請參閱：

- [了解 SharePoint 和 OneDrive 的保留功能](retention-policies-sharepoint.md)
- [了解 Microsoft Teams 保留](retention-policies-teams.md)
- [了解 Exchange 的保留](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>保留與刪除包含的內容

您可以使用保留原則來保留及刪除下列 Yammer 項目：社群訊息和使用者訊息。

不會在這些訊息中包含來自其他人表情符號形式的反應。

## <a name="how-retention-works-with-yammer"></a>Yammer 保留功能的運作方式

使用本章節了解後端儲存空間和流程如何滿足您的合規性要求，並且應透過電子文件探索工具而不是 Yammer 應用程式中目前可見的訊息進行驗證。

您可以使用保留原則來保留 Yammer 中社群訊息和使用者訊息的資料，並刪除這些訊息。 在幕後，會使用 Exchange 信箱來儲存從這些訊息複製的資料。 來自 Yammer 使用者訊息的資料會儲存在使用者訊息中包含的每個使用者的信箱中的隱藏資料夾中，且會將社群訊息儲存在群組信箱中一個類似的隱藏資料夾中。

當訊息 @ 提及使用者或通知使用者回覆時，社群訊息的複本也可以儲存在使用者信箱的隱藏資料夾中。 雖然這些訊息源自社群訊息，但 Yammer 使用者訊息的保留原則通常會包含社群訊息的複本。

這些隱藏資料夾不是為使用者或管理員直接存取而設計的，而是儲存合規性系統管理員可以使用電子文件探索工具搜尋的資料。

> [!IMPORTANT]
> 因為社群訊息的複本也可以儲存在使用者信箱中，具有 Yammer 使用者訊息刪除動作的保留原則可能會導致 Yammer 應用程式中的使用者無法再看到原始的社群訊息。
> 
> 不過，在社群群組信箱的隱藏資料夾中仍可使用原始訊息的複本，且可為合規性目的，透過電子文件探索搜尋存取。

Yammer 訊息不受針對 Exchange 信箱設定的保留原則影響。 儘管 Yammer 訊息會儲存在 Exchange 中，此 Yammer 資料只會由針對 **Yammer 社群訊息** 和 **Yammer 使用者訊息** 位置設定的保留原則包含。

> [!NOTE]
> 如果使用者包含在保留 Yammer 資料的作用中保留原則中，且您刪除了包含在此原則中使用者的信箱，若要保留此 Yammer 資料，該信箱會轉換成[非作用中信箱](inactive-mailboxes-in-office-365.md)。 如果您不需要為使用者保留此 Yammer 資料，請在刪除其信箱之前先將該使用者帳戶從保留原則排除。

針對 Yammer 訊息設定保留原則之後，Exchange 服務中的計時器工作就會針對儲存這些 Yammer 訊息所在的隱藏資料夾，定期評估其中項目。 計時器工作最多需要七天的時間來執行。 當這些項目超過其保留期間時，就會移至 SubstrateHolds 資料夾 (進行永久刪除前，每個使用者或群組信箱中用來儲存「虛刪除」項目的隱藏資料夾)。

> [!NOTE]
> 有鑑於[保留的首要原則](retention.md#the-principles-of-retention-or-what-takes-precedence)，若因為另一個保留原則而必須保留同一個項目，或因為法律或調查理由，而該項目在 eDiscovery 保留之下，則一律會暫停永久刪除。

針對 Yammer 訊息設定保留原則後，內容的路徑會取決於保留原則為保留然後刪除、僅保留或僅刪除。

當保留原則為保留然後刪除時：

![Yammer 訊息的保留流程圖](../media/yammerretentionlifecycle.png)

針對圖表中的兩個路徑：

1. 如果在保留期間使用者 **編輯或刪除某個 Yammer 訊息**，系統就立即複製原始訊息 (如果是編輯) 或將其移動 (如果是刪除) 到 SubstrateHolds 資料夾。 訊息會儲存在那裡直到保留期間到期為止，然後永久刪除訊息。

2. **如果未刪除 Yammer 訊息**，以及目前訊息經過編輯後，則會在保留期間到期後，將訊息移至 SubstrateHolds 資料夾。 此動作從到期日起最多需要七天才會完成。 當訊息位於 SubstrateHolds 資料夾，即會立即永久刪除。 

> [!NOTE]
> SubstrateHolds 資料夾中的訊息可供電子文件探索工具搜尋。 在訊息遭到永久刪除 (在 [SubstrateHolds] 資料夾中) 前，電子文件探索工具都可以搜尋到這些訊息。

當保留原則為僅保留或僅刪除時，內容路徑為保留和刪除的變化。

### <a name="content-paths-for-retain-only-retention-policy"></a>「僅保留」保留原則的內容路徑

1. **如果已編輯或刪除 Yammer 訊息**：系統會立即在 SubstrateHolds 資料夾中建立原始訊息的複本，並保留在該處，直到保留期間到期。 然後訊息會從立即從 SubstrateHolds 資料夾中永久刪除。

2. **如果未修改或刪除 Yammer 訊息**，以及針對在保留期間經過編輯的目前訊息：保留期間前後不會有任何變化；訊息仍會保留在其原始位置。

### <a name="content-paths-for-delete-only-retention-policy"></a>僅刪除保留原則的內容路徑

1. **如果未在保留期間刪除 Yammer 訊息**：在保留期間結束時，系統會將訊息移至 SubstrateHolds 資料夾。 此動作從到期日起最多需要七天才會完成。 然後訊息會從立即從 SubstrateHolds 資料夾中永久刪除。

2. **如果使用者在保留期間刪除 Yammer 訊息**，系統會立即將該項目移至 SubstrateHolds 資料夾，在其中會立即永久刪除該項目。


## <a name="messages-and-external-users"></a>訊息和外部使用者

根據預設，Yammer 使用者訊息的保留原則會套用至貴組織中的所有使用者，但不會套用至外部使用者。 如果您針對包含的使用者使用 **[編輯]** 選項，則可以將保留原則套用至外部使用者，並指定其帳戶。

目前不支援 Azure B2B 來賓使用者。

## <a name="when-a-user-leaves-the-organization"></a>當使用者離開組織時 

如果某位使用者離開您的組織，且其 Microsoft 365 帳戶被刪除，則其要保留的 Yammer 使用者訊息會儲存在非作用中的信箱中。 這些訊息仍受限於在他們的信箱被設成非作用中之前，對使用者設定的任何保留原則，且內容可供電子文件探索搜尋。 如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](inactive-mailboxes-in-office-365.md)。 

如果使用者將所有檔案儲存在 Yammer 中，請參閱適用於 SharePoint 和 OneDrive 的[同等小節](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。

## <a name="limitations"></a>限制

Yammer 保留原則目前處於預覽，且我們會持續努力將保留功能最佳化。 同時，當您對 Yammer 社群訊息和使用者訊息使用保留時，請注意下列限制：

- 當您針對 **[Yammer 使用者訊息]** 位置選取 **[編輯]** 時，您可能會看到來賓和非信箱使用者。 保留原則並非為這些使用者設計，因此請不要選取他們。

## <a name="configuration-guidance"></a>配置指導方針

如果您才剛開始在 Microsoft 365 中進行設定保留，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。

如果您已準備好為 Yammer 設定保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。