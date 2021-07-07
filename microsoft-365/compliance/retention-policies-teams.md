---
title: 了解 Teams 的保留
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
description: 了解適用於 Microsoft Teams 的保留原則。
ms.openlocfilehash: 5d888232d94ccd6634fc6102c26958e20d88fb4d
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322398"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>了解 Microsoft Teams 的保留

>*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

> [!NOTE]
> 如果您在 Teams 訊息中得知保留原則已刪除聊天或訊息，請參閱 [關於保留原則的 Teams 訊息](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b)。
> 
> 本頁面上的資訊適用於管理這些保留原則的 IT 系統管理員。

本文中的資訊可補充 [了解保留原則](retention.md)，因為其包含 Microsoft Teams 訊息專用的資訊。

若為其他工作負載，請參閱：

- [了解 SharePoint 和 OneDrive 的保留功能](retention-policies-sharepoint.md)
- [了解 Yammer 的保留](retention-policies-yammer.md)
- [了解 Exchange 的保留](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>保留與刪除包含的內容

您可以使用 Teams 的保留原則來刪除 Teams 聊天訊息和頻道訊息，而除了郵件中的文字，還可以基於合規性理由保留下列項目：內嵌影像、表格、超文字連結、其他 Teams 訊息和檔案的連結，以及[卡片內容](/microsoftteams/platform/task-modules-and-cards/what-are-cards)。 聊天訊息包括聊天中所有人的姓名，頻道訊息包括小組名稱和訊息標題 (如有)。 
> [!NOTE]
> 在私人頻道中支援訊息的功能目前正在預覽版中推出。

當您對 Teams 使用保留原則，系統不會保留程式碼片段、來自 Teams 行動用戶端的錄製語音備忘錄、縮圖、宣告影像，以及來自其他人表情符號形式的反應。

Teams 保留原則中不包括與 Teams 一起使用的電子郵件和檔案。這些項目有各自的保留原則。

## <a name="how-retention-works-with-microsoft-teams"></a>保留如何與 Microsoft Teams 搭配使用

使用本節了解後端儲存空間和流程如何滿足您的合規性要求，並且應透過電子文件探索工具而不是 Teams 應用程式中目前可見的郵件進行驗證。

您可以使用保留原則來保留 Teams 中聊天和頻道訊息的資料，並刪除這些聊天和訊息。 在幕後，會使用 Exchange 信箱來儲存複製自這些郵件的資料。 來自 Teams 聊天的資料會儲存在聊天內包含的每個使用者信箱的隱藏資料夾中，且會將群組信箱中的一個類似的隱藏資料夾用於 Teams 頻道訊息。 這些隱藏資料夾不是為使用者或管理員直接存取而設計的，而是儲存合規性系統管理員可以使用電子文件探索工具搜尋的資料。

這些信箱是依其 RecipientTypeDetails 屬性列出：

- **UserMailbox**：這些信箱會儲存雲端式 Teams 使用者的郵件資料。
- **MailUser**：這些信箱會儲存 [內部部署 Teams 使用者](search-cloud-based-mailboxes-for-on-premises-users.md)的郵件資料。
- **GroupMailbox**：這些信箱會儲存 Teams 標準頻道的訊息資料。

其他信箱類型 (例如用於 Teams 會議室的 RoomMailbox) 不支援使用 Teams 保留原則。

Teams 使用 Azure 支援的聊天服務作為其所有訊息 (聊天和頻道訊息) 的主要儲存空間。 如果您基於合規性理由需要刪除 Teams 訊息，Teams 的保留原則可以在一段特定期間之後，根據訊息建立的時間刪除訊息。 然後，訊息將從儲存用於合規性作業的 Exchange 信箱和 Azure 支援的基礎聊天服務使用的主要存儲空間中永久删除。 如需基礎架構的詳細資訊，請參閱 [Microsoft Teams 中的安全性與合規性](/MicrosoftTeams/security-compliance-overview)，特別是[資訊保護架構](/MicrosoftTeams/security-compliance-overview#information-protection-architecture)一節。

儘管此來自 Teams 聊天和頻道訊息的資料會儲存在信箱中，您必須為 **Teams 頻道訊息** 和 **Teams 聊天** 位置設定保留原則。 Teams 聊天和頻道訊息不包含於針對 Exchange 使用者或群組信箱設定的保留原則。

> [!NOTE]
> 如果使用者包含在保留 Teams 訊息的作用中保留原則中，且您刪除了包含在此原則中使用者的信箱，該信箱會轉換成[非作用中信箱](inactive-mailboxes-in-office-365.md)，以保留 Teams 資料。 如果您不需要為使用者保留此 Teams 資料，請在刪除其信箱之前先將該使用者帳戶從保留原則排除。

將保留原則設定為聊天和頻道訊息之後，Exchange 服務中的計時器工作就會針對儲存這些 Teams 訊息的隱藏資料夾，定期評估其中項目。 通常需要 1-7 天執行計時器工作。 當這些項目超過其保留期間時，就會移至 [SubstrateHolds] 資料夾 (進行永久刪除前，每個使用者或群組信箱中用來儲存「虛刪除」項目的另一個隱藏資料夾)。 

訊息在 [SubstrateHolds] 資料夾中至少保留 1 天，如果它們符合删除條件，計時器工作將在下次執行時永久删除它們。

> [!NOTE]
> 有鑑於[保留的首要原則](retention.md#the-principles-of-retention-or-what-takes-precedence)，若因為另一個保留原則而必須保留同一個項目，或因為法律或調查理由，而該項目在 eDiscovery 保留之下，則一律會暫停永久刪除。

針對聊天和頻道訊息設定保留原則後，內容的路徑會取決於保留原則為保留然後刪除、僅保留或僅刪除。

當保留原則為保留然後刪除時：

![Teams 聊天和頻道訊息的保留流程圖](../media/teamsretentionlifecycle.png)

針對圖表中的兩個路徑：

1. 如果在保留期間有使用者 **編輯或刪除某個聊天或頻道訊息**，系統就會複製原始訊息 (如果是編輯) 或將其移動 (如果是刪除) 到 [SubstrateHolds] 資料夾。 郵件在該處至少儲存 1 天。 保留到期後，下次執行計時器工作時 (通常在 1-7 天之間) 將永久删除訊息。

2. **如果使用者未刪除聊天或頻道訊息**，以及目前訊息經過編輯後，則會在保留期間到期後，將訊息移至 [SubstrateHolds] 資料夾。 此動作通常需要 1-7 天 (從到期日起) 執行。 訊息位於 [SubstrateHolds] 資料夾中時，它將在該處存儲至少 1 天，然後在下次執行計時器工作時 (通常在 1-7 天之間) 永久删除該訊息。 

> [!NOTE]
> 儲存在信箱中的郵件 (包括隱藏資料夾) 可透過電子文件探索工具進行搜尋。 在 [SubstrateHolds] 資料夾中訊息遭到永久刪除前，電子文件探索工具都可以搜尋到這些訊息。

當訊息從 [SubstrateHolds] 資料夾中被永久删除時，删除動作被傳遞到後端 Azure 聊天服務，然後該服務將相同的動作轉送到 Teams 用戶端應用程式。 此通訊或快取的延遲可以解釋在短時間內，使用者可能仍然在其 Teams 應用程式中看到這些訊息，但在電子文件探索搜尋中沒有退回這些訊息中的資料之原因。 在 Teams 應用程式中可見的訊息並不能準確反映它們是被保留還是被永久删除以滿足合規性要求。

當保留原則為僅保留或僅刪除時，內容路徑為保留和刪除的變化。

### <a name="content-paths-for-retain-only-retention-policy"></a>「僅保留」保留原則的內容路徑

1. 如果在保留期間有使用者 **編輯或刪除某個聊天或頻道訊息**，系統就會複製原始訊息 (如果是編輯) 或將其移動 (如果是刪除) 到 [SubstrateHolds] 資料夾，並保留至少 1 天。 如果保留原則設定為永久保留，則該項將保留在該處。 如果保留原則保留期具有結束日期，並且已過期，則下次執行計時器工作時 (通常在 1-7 天之間) 將永久删除該訊息。

2. **如果使用者未修改或刪除聊天或頻道訊息**，以及針對在保留期間經過編輯的目前訊息：保留期間前後不會有任何變化；訊息仍會保留在其原始位置。

### <a name="content-paths-for-delete-only-retention-policy"></a>僅刪除保留原則的內容路徑

1. 如果在保留期間有使用者 **編輯或刪除某個聊天或頻道訊息**：系統就會複製原始訊息 (如果是編輯) 或將其移動 (如果是刪除) 到 [SubstrateHolds] 資料夾。 訊息將在那裡保留至少 1 天，並在下次執行計時器工作永久删除 (通常在 1-7 天之間)。

2. **如果使用者未在保留期間刪除聊天或頻道訊息**：在保留期間結束時，系統會將訊息移至 SubstrateHolds 資料夾。 此動作通常需要 1-7 天 (從到期日起) 執行。 訊息將在該處保留至少 1 天，並在下次執行計時器工作永久删除 (通常在 1-7 天之間)。

#### <a name="example-flows-and-timings-for-retention-policies"></a>保留原則的流程和計時範例

使用以下範例可以了解上一節中介紹的流程和計時如何套用於具有以下設定的保留原則：

- [範例 1：只保留 7 年](#example-1-retain-only-for-7-years)
- [範例 2：保留 30 天，然後删除](#example-2-retain-for-30-days-and-then-delete)
- [範例 3：僅在 1 天后删除](#example-3-delete-only-after-1-day)

對於所有涉及永久删除的範例，根據[保留原則](retention.md#the-principles-of-retention-or-what-takes-precedence)，如果郵件受另一個保留原則的約束以保留該項目，或者受電子文件探索保留的約束，則此動作將暫止。

##### <a name="example-1-retain-only-for-7-years"></a>範例 1：只保留 7 年

在第 1 天，使用者建立一個聊天或頻道訊息。

在第 5 天，使用者編輯該訊息。

在第 30 天，使用者删除目前訊息。

保留結果：

- 對於原始訊息：
    - 在第 5 天，將複製訊息至 [SubstrateHolds] 資料夾，在該資料夾中，從第 1 天 (保留期) 起至少 7 年內仍可使用電子文件探索工具對其進行搜尋。

- 對於目前 (已編輯) 訊息：
    - 在第 30 天，訊息將移動至 [SubstrateHolds] 資料夾，在該資料夾中，從第 1 天 (保留期) 起至少 7 年內仍可使用電子文件探索工具對其進行搜尋。

如果使用者在指定保留期之後 (而不是在保留期內) 删除了目前訊息，則訊息仍將被移動到 [SubstrateHolds] 資料夾。 但是，現在保留期已過，訊息將在至少 1 天后 (通常在 1-7 天內) 被永久删除。

##### <a name="example-2-retain-for-30-days-and-then-delete"></a>範例 2：保留 30 天，然後删除

在第 1 天，使用者建立一個聊天或頻道訊息。

在第 10 天，使用者編輯該訊息。

使用者不進行進一步編輯，也不删除訊息。

保留結果：

- 對於原始訊息：
    - 在第 10 天，將複製訊息至 [SubstrateHolds] 資料夾，在該資料夾中仍可使用電子文件探索工具對其進行搜尋。
    - 在保留期結束時 (第 1 天算起的第 30 天)，訊息通常會在 1 天后 (通常 1-7 天内) 被永久删除，然後不會隨電子文件探索搜尋一起退回。

- 對於目前 (已編輯) 訊息：
    - 在保留期結束時 (從第 1 天算起的第 30 天)，訊息通常在 1-7 天內移動到 [SubstrateHolds] 資料夾，在該處仍然可以使用電子文件探索工具進行搜尋。
    - 然後訊息通常會在 1 天后 (通常 1-7 天内) 被永久删除，然後不會隨電子文件探索搜尋一起退回。

##### <a name="example-3-delete-only-after-1-day"></a>範例 3：僅在 1 天后刪除

> [!NOTE]
> 由於此設定和保留流程僅持續短短一天的時間，在 1-7 天的時間段內執行，因此本節顯示了一般時間範圍內的範例計時。

在第 1 天，使用者建立一個聊天或頻道訊息。

如果使用者不編輯或删除訊息，則保留結果範例：

- 第 5 天 (通常在第 2 天保留期開始後 1-7 天)：
    - 訊息將移動至 [SubstrateHolds] 資料夾，並在該資料夾中保留至少 1 天，在該資料夾中仍可使用電子文件探索工具進行搜尋。

- 第 9 天 (通常在 [SubstrateHolds] 資料夾中至少 1 天后算起的 1-7 天)：
    - 訊息將被永久删除，然後將不會隨電子文件探索搜尋退回。

如本例所示，儘管您可以將保留原則設定為僅在一天之後删除訊息，但該服務將經歷多個流程以確保合規的删除。 因此，1 天後執行的删除動作可能需要 16 天才能永久删除訊息，以便在電子文件探索搜尋中不再退回該訊息。

## <a name="skype-for-business-and-teams-interop-chats"></a>商務用 Skype 和 Teams Interop 聊天

商務用 Skype 聊天併入 Teams 後，會成為 Teams 聊天討論串中的訊息，並送到適當的信箱。 Teams 保留原則將套用至來自 Teams 討論串的這些訊息。 

不過，如果商務用 Skype 的聊天歷程記錄已開啟，且商務用 Skype 用戶端將這些歷程記錄儲存到信箱，則 Teams 保留原則不會處理這些聊天資料。針對此內容，請使用為商務用 Skype 設定的保留原則。

## <a name="meetings-and-external-users"></a>會議和外部使用者

頻道會議訊息的儲存方式與頻道訊息相同，因此，在您設定保留原則時，請針對此資料選取 [Teams 頻道訊息] 位置。

臨時和排程會議訊息的儲存方式與群組聊天相同，因此，在您設定保留原則時，請針對此資料選取 **Teams 聊天** 位置。

在您的組織管理的會議中包含外部使用者時：

- 如果外部使用者是使用您的租用戶中的來賓帳戶加入，則受限於您組織的 Teams 保留原則，此使用者會有一個陰影信箱。 來自會議的任何訊息都會同時儲存在使用者的信箱和陰影信箱中。 

- 如果外部使用者是使用來自另一個 Microsoft 365 組織的帳戶加入，您的保留原則就無法刪除該使用者的訊息，因為訊息是儲存在該使用者在另一個租用戶的信箱中。不過，針對相同會議，您的保留原則可以為您的使用者刪除訊息。

## <a name="when-a-user-leaves-the-organization"></a>當使用者離開組織時 

如果某位具有 Exchange Online 信箱的使用者離開您的組織，且其 Microsoft 365 帳戶被刪除，則其要保留的交談訊息會儲存在非作用中的信箱中。 交談訊息在他們的信箱被設成非作用中信箱之前，仍會受置於使用者之任何保留原則的制約，並可供電子文件探索搜尋。 如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](inactive-mailboxes-in-office-365.md)。 

如果使用者將所有檔案儲存在 Teams 中，請參閱適用于 SharePoint 和 OneDrive 的 [等效節](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。

## <a name="configuration-guidance"></a>配置指導方針

如果您才剛開始在 Microsoft 365 中進行設定保留，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。

如果您已準備好設定 Teams 保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。