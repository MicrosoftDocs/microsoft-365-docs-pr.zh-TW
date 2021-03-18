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
ms.openlocfilehash: ec4ca9a79ee3b5674e1837d14cea4ee504cb57d5
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838208"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>了解 Microsoft Teams 的保留

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

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

使用 Teams 保留原則可以保留和删除以下 Teams 項目：聊天訊息和頻道訊息 (包括内嵌影像、表格、超文字連結、指向其他 Teasm 訊息和檔案的連結以及[卡片内容](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards))。 聊天訊息包括聊天中所有人的姓名，頻道訊息包括小組名稱和訊息標題 (如有)。 

> [!NOTE]
> 包括卡片內容是最近新增的，且目前已完全向租用戶推出。 有關更多資訊，請參閱[透過 Teams 中應用程式之針對調適型卡片內容的 Microsoft 365 合規性功能已上線](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869)。

保留原則目前不支援私人頻道中的 Teams 訊息。 當您對 Teams 使用保留原則時，系統不會包含程式碼片段、來自 Teams 行動用戶端的錄製語音備忘錄、縮圖、宣告影像，以及來自其他人表情符號形式的反應。

Teams 保留原則中不包括與 Teams 一起使用的電子郵件和檔案。 這些項目有各自的保留原則。

## <a name="how-retention-works-with-microsoft-teams"></a>保留如何與 Microsoft Teams 搭配使用

您可以使用保留原則來保留和刪除 Teams 中的聊天與頻道訊息之資料。 在幕後，會使用 Exchange 信箱來儲存這些訊息。 來自 Teams 聊天的資料會儲存在聊天內包含的每個使用者信箱的隱藏資料夾中，且會將群組信箱中的一個類似的隱藏資料夾用於 Teams 頻道訊息。

這些信箱是依其 RecipientTypeDetails 屬性列出：

- **MailUser**：這些信箱會儲存雲端式 Teams 使用者的郵件。
- **UserMailbox**：這些信箱會儲存 [內部部屬 Teams 使用者](search-cloud-based-mailboxes-for-on-premises-users.md)的郵件。
- **GroupMailbox**：這些信箱會儲存 Teams 頻道的訊息。

Teams 保留原則不支援的其他信箱類型，例如用於 Teams 會議室的 RoomMailbox。

請務必了解 Teams 使用的聊天服務是由 Azure 所提供，此服務也會儲存 Teams 的資料，且會根據預設永久保存。 因此，如果您因合規性原因而需要刪除 Teams 訊息，建議您使用能夠永久從 Exchange 信箱和基礎 Azure 提供的交談服務中刪除該資料的 Teams 保留原則。 如需詳細資訊，請參閱 [Microsoft Teams 中的安全性與合規性](https://go.microsoft.com/fwlink/?linkid=871258)，特別是[資訊保護架構](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture)一節。

儘管 Teams 聊天和頻道訊息會儲存在信箱中，此 Teams 資料只會透過針對 **Teams 頻道訊息** 和 **Teams 聊天** 位置設定的保留原則包含。 Teams 聊天和頻道訊息不受針對 Exchange 使用者或群組信箱設定的保留原則影響。

> [!NOTE]
> 如果使用者包含在保留 Teams 資料的作用中保留原則中，且您刪除了包含在此原則中使用者的信箱，若要保留此 Teams 資料，該信箱會轉換成[非作用中信箱](inactive-mailboxes-in-office-365.md)。 如果您不需要為使用者保留此 Teams 資料，請在刪除其信箱之前先將該使用者帳戶從保留原則排除。

將保留原則設定為聊天和頻道訊息之後，Exchange 服務中的計時器工作就會針對儲存這些 Teams 訊息的隱藏資料夾，定期評估其中項目。 計時器工作最多需要七天的時間來執行。 當這些項目超過其保留期間時，就會移至 [SubstrateHolds] 資料夾 (進行永久刪除前，每個使用者或群組信箱中用來儲存「虛刪除」項目的另一個隱藏資料夾)。

針對聊天和頻道訊息設定保留原則後，內容的路徑會取決於保留原則為保留然後刪除、僅保留或僅刪除。

當保留原則為保留然後刪除時：

![Teams 聊天和頻道訊息的保留流程圖](../media/teamsretentionlifecycle.png)

針對圖表中的兩個路徑：

1. 如果在保留期間有使用者 **編輯或刪除某個聊天或頻道訊息**，系統就會在 21 天内複製原始訊息 (如果是編輯) 或將其移動 (如果是刪除) 到 [SubstrateHolds] 資料夾。 訊息會在那裡儲存到保留期間到期為止，然後在 24 小時內永久刪除訊息。

2. **如果不刪除聊天或頻道訊息**，以及目前訊息經過編輯後，則會在保留期間到期後，將訊息移至 [SubstrateHolds] 資料夾。 此動作最多可在到期日起 7 天內完成。 當訊息位於 [SubstrateHolds] 資料夾時，其會在 24 小時內永久刪除。 

> [!NOTE]
> SubstrateHolds 資料夾中的訊息可供電子文件探索工具搜尋。 在 [SubstrateHolds] 資料夾中訊息遭到永久刪除前，電子文件探索工具都可以搜尋到這些訊息。

當保留原則為僅保留或僅刪除時，內容路徑為保留和刪除的變化。

### <a name="content-paths-for-retain-only-retention-policy"></a>「僅保留」保留原則的內容路徑

1. **如果聊天或頻道訊息為 [已編輯] 或 [已刪除]**：系統會在 21 天内在 [SubstrateHolds] 資料夾中建立原始訊息的複本，並保留在該處，直到保留期間到期為止。 然後訊息會在 24 小時內從 [SubstrateHolds] 資料夾中永久刪除。

2. **如果未在保留期間修改或刪除項目**，以及目前訊息經過編輯後：保留期間前後沒有任何變化；訊息仍會保留在其原始位置。

### <a name="content-paths-for-delete-only-retention-policy"></a>僅刪除保留原則的內容路徑

1. **如果未在保留期間刪除訊息**：在保留期間結束時，系統會將訊息移至 SubstrateHolds 資料夾。 此動作最多可在到期日起七天內完成。 然後訊息會在 24 小時內從 [SubstrateHolds] 資料夾中永久刪除。

2. **如果使用者在保留期間刪除項目**，系統會在 21 天内將項目移至 [SubstrateHolds] 資料夾，並在 24 小時內永久刪除該項目。


## <a name="skype-for-business-and-teams-interop-chats"></a>商務用 Skype 和 Teams Interop 聊天

商務用 Skype 聊天併入 Teams 後，會成為 Teams 聊天討論串中的訊息，並送到適當的信箱。 Teams 保留原則將套用至來自 Teams 討論串的這些訊息。 

不過，如果商務用 Skype 的聊天歷程記錄已開啟，且商務用 Skype 用戶端將這些歷程記錄儲存到信箱，則 Teams 保留原則不會處理這些聊天資料。 針對此內容，請使用為商務用 Skype 設定的保留原則。

## <a name="meetings-and-external-users"></a>會議和外部使用者

頻道會議訊息的儲存方式與頻道訊息相同，因此，在您設定保留原則時，請針對此資料選取 [Teams 頻道訊息] 位置。

臨時和排程會議訊息的儲存方式與群組聊天相同，因此，在您設定保留原則時，請針對此資料選取 **Teams 聊天** 位置。

在您的組織管理的會議中包含外部使用者時：

- 如果外部使用者是使用您的租用戶中的來賓帳戶加入，則受限於您組織的 Teams 保留原則，此使用者會有一個陰影信箱。 來自會議的任何訊息都會同時儲存在使用者的信箱和陰影信箱中。 

- 如果外部使用者是使用來自另一個 Microsoft 365 組織的帳戶加入，您的保留原則就無法刪除該使用者的訊息，因為訊息是儲存在該使用者在另一個租用戶的信箱中。 不過，針對相同會議，您的保留原則可以為您的使用者刪除訊息。

## <a name="when-a-user-leaves-the-organization"></a>當使用者離開組織時 

如果某位具有 Exchange Online 信箱的使用者離開您的組織，且其 Microsoft 365 帳戶被刪除，則其要保留的交談訊息會儲存在非作用中的信箱中。 交談訊息在他們的信箱被設成非作用中信箱之前，仍會受置於使用者之任何保留原則的制約，並可供電子文件探索搜尋。 如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](inactive-mailboxes-in-office-365.md)。 

如果使用者將所有檔案儲存在 Teams 中，請參閱適用于 SharePoint 和 OneDrive 的 [等效節](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。

## <a name="limitations"></a>限制

我們持續努力將 Teams 中的保留功能最佳化。 在此同時，當您使用保留 Teams 頻道訊息和交談時，請注意以下幾個限制：

- **Outlook 中顯示不正確的問題**。 如果您建立 Skype 或 Teams 位置的保留原則，當使用者在 Outlook 電腦版用戶端中檢視信箱資料夾的內容時，其中一個原則會顯示為預設資料夾原則。 這是 Outlook 中顯示不正確的問題，並且是[已知問題](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)。 應顯示為預設資料夾原則的是套用至資料夾的信箱保留原則。 Skype 或 Teams 保留原則不會套用至使用者的信箱。

- **設定問題**： 
    - 當您針對 [Teams 頻道訊息] 位置選取 [選擇小組] 時，您可能會看到也不是小組的 Microsoft 365 群組。 請勿選取這些群組。
    
    - 當您針對 [Teams 聊天] 位置選取 [選擇使用者] 時，您可能會看到來賓和非信箱使用者。 保留原則並非為這些使用者設計，因此請不要選取他們。

## <a name="configuration-guidance"></a>配置指導方針

如果您才剛開始在 Microsoft 365 中進行設定保留，請參閱 [開始使用保留原則及保留標籤](get-started-with-retention.md)。

如果您已準備好設定 Teams 保留原則，請參閱[建立及設定保留原則](create-retention-policies.md)。
