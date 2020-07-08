---
title: 了解 Teams 的保留原則
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
ms.openlocfilehash: ead16cf4d89b5dbea2fee4a6669f537a0338984e
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049847"
---
# <a name="learn-about-retention-policies-for-microsoft-teams"></a>了解 Microsoft Teams 的保留原則

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

本文中的資訊可補充[了解保留原則](retention-policies.md)，因為其包含 Microsoft Teams 專用的資訊。

## <a name="how-a-retention-policy-works-with-microsoft-teams"></a>保留原則如何與 Microsoft Teams 搭配使用

您可以使用保留原則來保留 Teams 中的聊天與頻道訊息。 Teams 聊天會儲存在聊天內每個使用者信箱的隱藏資料夾中，Teams 頻道訊息則會儲存在小組群組信箱中類似的隱藏資料夾內。 

請務必了解 Teams 使用的聊天服務是由 Azure 所提供，此服務也會儲存 Teams 的資料，且會根據預設永久保存。 基於這個原因，我們強烈建議您使用 Teams 位置來保留並刪除 Teams 的資料。 使用 Teams 位置將永久刪除 Exchange 信箱內和基礎 Azure 聊天服務中的資料。 如需詳細資訊，請參閱 [Microsoft Teams 中的安全性與合規性](https://go.microsoft.com/fwlink/?linkid=871258)，特別是[資訊保護架構](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture)一節。

Teams 聊天和頻道訊息不受針對使用者或群組信箱設定的保留原則影響。 儘管 Teams 聊天和頻道訊息會儲存在 Exchange 中，此 Teams 資料只會透過針對 **Teams 頻道訊息**和 **Teams 聊天**位置設定的保留原則包含。

> [!NOTE]
> 如果使用者包含在保留 Teams 資料的作用中保留原則中，且您刪除了包含在此原則中使用者的信箱，若要保留此 Teams 資料，該信箱會轉換成[非作用中信箱](inactive-mailboxes-in-office-365.md)。 如果您不需要為使用者保留此 Teams 資料，請在刪除其信箱之前先將該使用者帳戶從保留原則排除。

針對聊天和頻道訊息設定保留原則後，內容的路徑會取決於保留原則為保留和刪除、僅保留或僅刪除。

當保留原則為保留和刪除時：

![Teams 聊天和頻道訊息的保留流程圖](../media/TeamsRetentionLifecycle.png)

1. 如果使用者在保留期間**修改或刪除聊天或頻道訊息**，則會將該訊息移動 (或如果是編輯的情況下，則為複製) 至 SubstrateHolds 資料夾 (這是每個使用者或群組信箱中的隱藏資料夾)，並儲存在此資料夾中，直到保留期間到期為止。 訊息會在保留期間到期當日永久刪除。

2. 如果在保留期間**未刪除某個聊天或頻道訊息**，則該訊息會在保留期間到期後的一天內 (可能需要 0 到 24 小時的時間) 移至 SubstrateHolds 資料夾。 訊息會在移至 SubstrateHolds 資料夾的一天後永久刪除。 

> [!NOTE]
> SubstrateHolds 資料夾中的訊息可供電子文件探索工具搜尋。 永久刪除某個訊息後，電子文件探索搜尋中就不會傳回該訊息。

當保留原則為僅保留或僅刪除時，內容路徑為保留和刪除的變化。

### <a name="content-paths-for-retain-only-retention-policy"></a>「僅保留」保留原則的內容路徑

1. **如果在保留期間修改或刪除項目**：系統會在 SubstrateHolds 資料夾中建立原始訊息的複本，並保留到保留期間結束，然後在該項目到期後的一天永久刪除 SubstrateHolds 資料夾中的該複本。 

2. **如果未在保留期間修改或刪除項目**：保留期間前後沒有任何變化；訊息仍會保留在其原始位置。

### <a name="content-paths-for-delete-only-retention-policy"></a>僅刪除保留原則的內容路徑

1. **如果未在保留期間刪除訊息**：在保留期間結束時，系統會將訊息移至 SubstrateHolds 資料夾。 

2. **如果使用者在保留期間刪除項目**，系統會立即將項目移至 SubstrateHolds 資料夾。 如果使用者從該處刪除訊息或清空 SubstrateHolds 資料夾，就會永久刪除項目。 否則訊息會在處於 SubstrateHolds 資料夾的一天後永久刪除。


## <a name="skype-for-business-and-teams-interop-chats"></a>商務用 Skype 和 Teams Interop 聊天

商務用 Skype 和 Teams Interop 聊天也是相同的運作流程。 商務用 Skype 聊天併入 Teams 後，會成為 Teams 聊天討論串中的訊息，並送到適當的信箱。 Teams 保留原則會將這些訊息從 Teams 討論串中刪除。 

不過，如果商務用 Skype 的聊天歷程記錄已開啟，且商務用 Skype 用戶端將這些歷程記錄儲存到信箱，則 Teams 保留原則不會處理這些聊天資料。

## <a name="files-in-teams"></a>Teams 中的檔案

在 Teams 聊天中共用的檔案會儲存在共用檔案之使用者的 OneDrive 帳戶中。 上傳至頻道的檔案則會儲存在團隊的 SharePoint 網站中。 這表示要若保留或刪除 Teams 中的檔案，除了您為 Teams 所設定的任何保留原則以外，您必須再設定一或多個適用于 OneDrive 和 SharePoint 的保留原則。 如需有關保留原則如何適用這些位置的詳細資訊，請參閱[了解 SharePoint 和 OneDrive 的保留原則](retention-policies-sharepoint.md)。

> [!NOTE]
> 包含 Teams 頻道訊息或 Teams 聊天的保留原則只能包含 Teams 位置。 因此，若要在 Teams 中保留或刪除這些檔案，您必須建立個別的保留原則。
> 
> 如果想要套用保留原則至某個特定小組的檔案，您可以選擇該小組的 SharePoint 網站，以及該小組中使用者的 OneDrive 帳戶。

套用至 SharePoint 或 OneDrive 的保留原則有可能會刪除 Teams 聊天中參考的檔案，或在頻道訊息刪除前就將其刪除。 在這種情況下，檔案仍會顯示在 Teams 訊息中，但是當使用者按一下檔案時，會收到「找不到檔案」錯誤。 此行為並非保留原則特定，因此也可能在使用者從 SharePoint 或 OneDrive 中手動刪除檔案時發生。

## <a name="meetings-and-external-users"></a>會議和外部使用者

頻道會議訊息的儲存方式與頻道訊息相同，因此，在您設定保留原則時，請針對此資料選取 [Teams 頻道訊息]**** 位置。

臨時會議訊息的儲存方式與群組聊天相同，因此，在您設定保留原則時，請針對此資料選取 [Teams 聊天]**** 位置。

在您的組織管理的會議中包含外部使用者時：

- 如果外部使用者是使用您的租用戶中的來賓帳戶加入，則受限於您組織的 Teams 保留原則，此使用者會有一個陰影信箱。 來自會議的任何訊息都會同時儲存在使用者的信箱和陰影信箱中。 

- 如果外部使用者是使用來自另一個 Microsoft 365 組織的帳戶加入，您的保留原則就無法刪除該使用者的訊息，因為訊息是儲存在該使用者在另一個租用戶的信箱中。 不過，針對相同會議，您的保留原則可以為您的使用者刪除訊息。

## <a name="when-a-user-leaves-the-organization"></a>當使用者離開組織時 

如果某位使用者離開您的組織，且其 Office 365 帳戶被刪除，則其要保留的交談訊息會儲存在非作用中的信箱中。 交談訊息在他們的信箱被設成非作用中信箱之前，仍會受置於使用者之任何保留原則的制約，並可供電子文件探索搜尋。 如需詳細資訊，請參閱 [Exchange Online 中的非作用中信箱](inactive-mailboxes-in-office-365.md)。 

如果使用者將所有檔案儲存在 Teams 中，請參閱適用于 SharePoint 和 OneDrive 的 [等效節](retention-policies-sharepoint.md#when-a-user-leaves-the-organization)。

## <a name="limitations"></a>限制

我們持續努力將 Teams 中的保留功能最佳化。 在此同時，請留意以下所述的一些限制：
  
- **Teams 需要個別的保留原則**。 當您建立保留原則並將 Teams 位置切換為開啟時，其他所有位置都會切換為關閉。 包含 Teams 的保留原則只能包含 Teams 位置，不可包含其他位置。

- **Teams 不包含在全組織原則中**。 如果建立全組織原則，則不會包含 Teams，因為它們需要個別的保留原則。

- **Teams 不支援進階保留**。 建立保留原則時，如果您選擇 [用來識別符合特定條件內容的進階設定][](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions)，則無法使用 Teams 位置。 目前，當您選取這些位置時，會將 Teams 中的保留套用至所有聊天和頻道訊息內容。

- **當您為 Teams 團隊頻道訊息設定保留原則時，不會包含私人頻道的訊息**。 而是會為使用者將來自私人頻道的訊息包含為群組聊天，其中包含 [Teams 聊天]**** 選項。 
    
- **Teams 最多可能需要三天的時間來清理到期的訊息**。 保留期間到期時，套用至 Teams 的保留原則將會刪除聊天和頻道訊息。 不過，要清理並永久刪除這些訊息最多可能需要三天的時間。 同時，聊天和頻道訊息在保留期間到期後以及當訊息永久刪除時，仍可透過電子文件探索工具進行搜尋。
    
   > [!NOTE]
   > 過去，保留原則無法刪除少於 30 天的 Teams 內容，我們已移除此限制。 現在 Teams 內容的保留期間，可以是您選擇的任何天數，也可以是一天這麼短的時間。 如果您確實有一天的保留期間，在保留期間到期後，於永久刪除訊息之前，可能需要最長 3 天的時間。

- **Outlook 中顯示不正確的問題**。 如果您建立 Skype 或 Teams 位置的保留原則，當使用者在 Outlook 電腦版用戶端中檢視信箱資料夾的內容時，其中一個原則會顯示為預設資料夾原則。 這是 Outlook 中顯示不正確的問題，並且是[已知問題](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies)。 應顯示為預設資料夾原則的是套用至資料夾的信箱保留原則。 Skype 或 Teams 保留原則不會套用至使用者的信箱。

- **設定問題**：
    - 當您針對 [Teams 頻道訊息]**** 位置選取 [選擇小組]**** 時，您可能會看到也不是小組的 Office 365 群組。 請勿選取這些群組。
    
    - 當您針對 [Teams 聊天]**** 位置選取 [選擇使用者]**** 時，您可能會看到來賓和非信箱使用者。 保留原則並非為這些使用者設計，因此請不要選取他們。

## <a name="how-to-configure-a-retention-policy-for-microsoft-teams"></a>如何為 Microsoft Teams 設定保留原則

按照 [建立及設定保留原則][](create-retention-policies.md) 和 [選擇位置]**** 精靈頁面中的指示進行，選取下列其中一個選項：

- [讓我選擇特定位置]****  >  [Teams 頻道訊息]**** 和 [Teams 聊天]****

套用至 Teams 的保留原則可能會使用[保留鎖定](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements)，這可能為基於法規理由所需。

## <a name="related-information"></a>相關資訊

[Microsoft Teams 中的保留原則](https://docs.microsoft.com/microsoftteams/retention-policies)
