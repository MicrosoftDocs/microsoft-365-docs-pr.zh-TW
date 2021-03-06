---
title: 為團隊設定高敏感性資料保護
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
recommendations: false
description: 了解如何為團隊部署高敏感性資料保護。
ms.openlocfilehash: a3f715cb05ad1d5acf3c93c58959f12ebec46978
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788339"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a>為團隊設定高敏感性資料保護

在本文中，我們將說明如何為團隊設定敏感度層級的保護。 在按照本文所述的步驟操作之前，請確定您已完成[為團隊部署基本保護](configure-teams-baseline-protection.md)中的步驟。 敏感性層級可提供基準層所未提供的下列額外保護：

- 適用於團隊的敏感度標籤可讓您開啟或關閉來賓共用，並將未受管理裝置的 SharePoint 內容存取權限制為僅限網頁。此標籤也可用來分類檔案。
- 限制更多的預設共用連結類型
- 只有小組擁有者可以建立私人頻道。

## <a name="video-demonstration"></a>影片示範

請觀看這段影片，以取得本文所述程序的逐步解說。
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NMS6]

## <a name="guest-sharing"></a>來賓共用

視貴公司的業務性質而定，您不一定會想要為包含敏感性資料的團隊啟用來賓共用。 如果您打算在團隊內與組織外的人員共同作業，建議您啟用來賓共用。 Microsoft 365 有各種安全性與合規性功能可協助您安全地共用敏感內容。 一般來說，這個選項的安全性高過直接用電子郵件將內容傳送給組織外的人員。

如需如何安全地與來賓共用的詳細資訊，請參閱下列資源：

- [在與組織外的人員共用檔案時，限制資訊意外暴露](./share-limit-accidental-exposure.md)
- [建立安全的來賓共用環境](./create-secure-guest-sharing-environment.md)

為了允許或封鎖來賓共用，我們會使用敏感度標籤 (適用於小組) 和網站層級共用控制 (適用於相關聯的 SharePoint 網站) 的組合，後面會有這兩種機制的討論。

## <a name="sensitivity-labels"></a>敏感度標籤

為了獲得敏感度層級的保護，我們會使用敏感度標籤來分類團隊。 此標籤也可用來分類此團隊或其他團隊中的個別檔案，或是其他檔案位置 (例如 SharePoint 或 OneDrive) 中的個別檔案。 

首先，您必須為 Teams 啟用敏感度標籤。 如需詳細資訊，請參閱[使用敏感度標籤來保護 Microsoft Teams、Office 365 群組和 SharePoint 網站中的內容](../compliance/sensitivity-labels-teams-groups-sites.md)。

如果組織已部署敏感度標籤，請考慮這個標籤與整體標籤策略的配合程度。 您可以視需要變更名稱或設定，以符合組織的需求。

在為 Teams 啟用敏感度標籤後，下一步是建立標籤。

建立敏感度標籤
1. 開啟 [Microsoft 365 合規性中心](https://compliance.microsoft.com)。
2. 在 **[解決方案]** 底下，按一下 **[資訊保護]**。
3. 按一下 **[建立標籤]**。
4. 為標籤命名。 我們建議命名為 **敏感度**，但如果該名稱已在使用中，則可以選擇不同名稱。
5. 新增顯示名稱和描述，然後按 [下一步 **]**。
6. 在 [定義此標籤頁面的範圍 **]** 上，選取 [檔案和電子郵件 **]** 和 [群組和網站 **]**，然後按 [下一步 **]**。
7. 在 [選擇檔案和電子郵件的保護設定 **]** 頁面上，按 [下一步 **]**。
8. 在 [自動為檔案和電子郵件加上標籤 *]* 頁面上按 [下一步 **]**。
9. 在 [定義群組及網站的保護設定 **]** 頁面上，選取 [隱私權和外部使用者存取權設定 **]** 和 [裝置存取權和外部共用設定 **]**，然後按 [下一步 **]**。
10. 在 [定義隱私權和外部使用者存取權設定 **]** 頁面上，於 [隱私權 **]** 底下選取 [私人 **]** 選項。
11. 如果您想要允許來賓存取，請在 [外部使用者存取權 **]** 底下，選取 [讓 Microsoft 365 群組擁有者將貴組織外部人員新增到群組做為來賓 **]** 群組。
12. 按 [下一步 **]**。
13. 在 [定義外部共用和裝置存取權設定 **]** 頁面上，選取 [從已套用標籤的 SharePoint 網站控制外部共用 **]**。
14. 如果您要允許來賓存取，在 [內容可以與誰共用 **]** 底下，選擇 [新的及現有的來賓 **]**，或如果您不要允許來賓存取，則選擇 [僅限組織中的人員 **]**。
15. 在 [存取未受管理的裝置 **]** 下，選擇 [允許受限的僅限 Web 存取 **]**。
16. 按 [下一步 **]**。
17. 在 [為資料庫資料行自動加上標籤 **]** 頁面上，按 [下一步 **]**。
18. 按一下 [建立標籤 **]**，然後按一下 [完成 **]**。

在建立好標籤後，您必須將標籤發佈給將使用該標籤的使用者。 為了獲得敏感度保護，我們會將標籤提供給所有使用者使用。 您可以在 **[資訊保護]** 頁面的 **[標籤原則]** 索引標籤上發佈 Microsoft 365 合規性中心的標籤。 如果您有適用於所有使用者的現有原則，請將這個標籤新增至該原則。 如果您需要建立新原則，請參閱[建立標籤原則來發佈敏感度標籤](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)。

## <a name="create-a-team"></a>建立團隊

我們會在與團隊相關聯的 SharePoint 網站中進一步設定敏感度案例，因此下一步是建立團隊。

為敏感性資訊建立團隊
1. 在 Teams 中，按一下應用程式左側的 **[團隊]**，然後按一下團隊清單底部的 **[加入或建立團隊]**。
2. 按一下 **[建立團隊]** (左上角的第一張卡片)。
3. 選擇 **[從頭建立團隊]**。
4. 在 **[敏感度]** 清單中，選擇您剛才建立的 **[敏感度]** 標籤。
5. 在 **[隱私權]** 下，按一下 **[私人]**。
6. 輸入團隊的名稱，然後按一下 **[建立]**。
7. 將使用者新增至團隊，然後按一下 **[關閉]**。

## <a name="private-channel-settings"></a>私人頻道設定

在這一層中，我們會限制只有團隊擁有者能夠建立私人頻道。

限制私人頻道的建立
1. 在該團隊中，按一下 **[更多選項]**，然後按一下 **[管理團隊]**。
2. 在 **[設定]** 索引標籤上展開 **[成員權限]**。
3. 清除 **[允許成員建立私人頻道]** 核取方塊。

您也可以使用[小組原則](/MicrosoftTeams/teams-policies)來控制可以建立私人頻道的人員。

## <a name="sharepoint-settings"></a>SharePoint 設定

每次使用敏感度標籤建立新的團隊時，都要在 SharePoint 中進行兩個步驟：

- 在 SharePoint 系統管理中心更新網站的來賓共用設定，以將預設共用連結更新為 *特定人員*。
- 更新網站本身的網站共用設定以防止成員共用網站。

### <a name="site-default-sharing-link-settings"></a>網站預設的共用連結設定

若要更新網站預設的共用連結設定

1. 開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。
2. 在 **[網站]** 底下，按一下 **[使用中網站]**。
3. 按一下與小組相關聯的網站。
4. 在 **[原則]** 索引標籤的 **[外部共用]** 底下，按一下 **[編輯]**。
5. 在 **[預設的共用連結類型] 底下，清除 [與組織層級設定相同]** 核取方塊，然後選取 **[特定人員 (只有使用者指定的人)]**。
6. 按一下 **[儲存]**。

如果您想要將此編寫為團隊建立程序的一部分，則可以使用 [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) 並搭配下列 `-DefaultSharingLinkType Direct` 參數以變更 *特定人員* 的預設共用連結。

#### <a name="private-channels"></a>私人頻道

如果您在小組中新增私人頻道，則每個私人頻道都會使用預設的共用設定建立一個新的 SharePoint 網站。 這些網站不會顯示在 SharePoint 系統管理中心內，因此您必須使用 Set-SPOSite PowerShell Cmdlet 來更新來賓共用設定。

### <a name="site-sharing-settings"></a>網站共用設定

為了協助確保 SharePoint 網站不會與非小組成員的人員共用，我們將這種共用功能限制為只有擁有者能使用。

若要設定僅限擁有者使用的網站共用功能
1. 在 Teams 中，瀏覽至所要更新團隊的 **[一般]** 索引標籤。
2. 在小組的工具列中，按一下 **[檔案]**。
3. 按一下省略符號，然後按一下 **[在 SharePoint 中開啟]**。
4. 在基礎 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 **[網站權限]**。
5. 在 **[網站權限]** 窗格的 **[網站共用]** 下，按一下 **[變更成員可以使用的共用方式]**。
6. 在 [共用權限] 底下，選擇 [網站擁有者和成員，以及擁有編輯權限的人員可以共用檔案與資料夾，但只有網站擁有者可以共用網站]，然後按一下 [儲存]。


## <a name="see-also"></a>另請參閱

[建立及設定敏感度標籤及其原則](../compliance/create-sensitivity-labels.md)
