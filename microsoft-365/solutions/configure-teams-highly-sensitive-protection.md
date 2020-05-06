---
title: 為小組設定高敏感度資料保護
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
description: 了解如何為小組部署高敏感度資料保護。
ms.openlocfilehash: f044dd672d52db4100fcb4cfec2519a8605c7be8
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002793"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a>為小組設定高敏感度資料保護

在本文中，我們將說明如何為小組設定高敏感度層級的保護。 在按照本文所述的步驟操作之前，請確定您已完成[為小組部署基準保護](configure-teams-baseline-protection.md)中的步驟。

為了獲得這一層保護，我們會建立敏感度標籤以供整個組織用於高敏感度的小組和檔案。 只有貴組織的成員和您指定的來賓能夠解密使用了這個標籤的檔案。 如果您需要進一步隔離權限，以便只有特定小組的成員能夠解密檔案，請參閱[為小組部署安全性隔離](secure-teams-security-isolation.md)。

高敏感度層可提供基準層所未提供的下列額外保護：

- 適用於小組的敏感度標籤，此標籤可讓您開啟或關閉來賓共用，並將未受管理裝置的 SharePoint 內容存取權限制為僅限網頁版。 此標籤也可用來分類和加密檔案。
- 限制更多的預設共用連結類型
- 只有小組擁有者可以建立私人頻道。
- 已關閉相關聯 SharePoint 網站的存取要求。

## <a name="guest-sharing"></a>來賓共用

視貴公司的性質而定，您不一定會想要為包含高敏感度資料的小組啟用來賓共用。 如果您打算與小組內的非組織內部人員共同作業，建議您啟用來賓共用。 Microsoft 365 有各種安全性與合規性功能可協助您安全地共用敏感內容。 一般來說，這個選項的安全性高過直接用電子郵件將內容傳送給組織外的人員。

如需如何安全地與來賓共用的詳細資訊，請參閱下列資源：

- [在與組織外的人員共用檔案時，限制資訊意外暴露](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [建立安全的來賓共用環境](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

為了允許或封鎖來賓共用，我們會使用敏感度標籤 (適用於小組) 和網站層級共用控制 (適用於相關聯的 SharePoint 網站) 的組合，後面會有這兩種機制的討論。

## <a name="sensitivity-labels"></a>敏感度標籤

為了獲得高敏感度層級的保護，我們會使用敏感度標籤來分類小組。 此標籤也可用來分類及加密此小組或其他小組中的個別檔案，或是其他檔案位置 (例如 SharePoint 或 OneDrive) 中的個別檔案。 

首先，您必須為 Teams 啟用敏感度標籤。 如需詳細資訊，請參閱[使用敏感度標籤來保護 Microsoft Teams、Office 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

如果貴組織已部署敏感度標籤，請考慮這個標籤與整體標籤策略的配適程度。 您可以視需要變更名稱或設定，以符合貴組織的需求。

在為 Teams 啟用敏感度標籤後，下一步是建立此標籤。

建立敏感度標籤
1. 開啟 [Microsoft 365 合規性中心](https://compliance.microsoft.com)。
2. 在 [解決方案]**** 底下，按一下 [資訊保護]****。
3. 按一下 [建立標籤]****。
4. 為標籤命名。 我們建議命名為**高敏感度**，但如果有已經使用的名稱，則可以選擇不同名稱。
5. 新增工具提示，然後按 [下一步]****。
6. 在 [加密]**** 頁面上，於 [加密]**** 下拉式清單中選擇 [套用]****。
7. 在 [指派權限給特定使用者和群組]**** 底下，按一下 [指派權限]****。
8. 按一下 [新增組織中的所有使用者和群組]****。
9. 如果有應該獲得解密檔案權限的來賓使用者，請按一下 [新增使用者或群組]**** 並新增這些使用者。
10.  按一下 [儲存]****，然後按 [下一步]****。
11. 如果您想要將頁首、頁尾或浮水印自動新增至以此標籤分類的檔案，請在 [內容標記]**** 頁面上開啟內容標記。
12. 在 [網站和群組設定]**** 頁面上，將 [網站和群組設定]**** 設為 [開啟]****。
13. 在 [Office 365 群組連線小組網站的隱私權]**** 下拉式清單中，選擇 [私人 - 只有成員可以存取網站]****。
14. 如果您想要允許來賓存取，請選取 [讓 Office 365 群組擁有者將貴組織外部的人員新增到群組]**** 核取方塊。 
15. 在 [未受管理的裝置]**** 底下，選擇 [封鎖存取]****。
16. 按 [下一步]****。
17. 在 [Office 應用程式的自動加上標籤]**** 頁面上按 [下一步]****。
18. 按一下 [提交]****，然後按一下 [完成]****。

在建立好標籤後，您必須將標籤發佈給將使用該標籤的使用者。 為了獲得敏感度保護，我們會將標籤提供給所有使用者使用。 您可以在 [資訊保護]**** 頁面的 [標籤原則]**** 索引標籤上發佈 Microsoft 365 合規性中心的標籤。 如果您有適用於所有使用者的現有原則，請將這個標籤新增至該原則。 如果您需要建立新原則，請參閱[建立標籤原則來發佈敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy)。

## <a name="create-a-team"></a>建立小組

我們會在與小組相關聯的 SharePoint 網站中進一步設定高敏感度的案例，因此下一步是建立小組。

為高敏感度資訊建立小組
1. 在 Teams 中，按一下應用程式左側的 [小組]****，然後按一下小組清單底部的 [加入或建立小組]****。
2. 按一下 [建立小組]**** (左上角的第一張卡片)。
3. 選擇 [從頭建置小組]****。
4. 在 [敏感度]**** 清單中，選擇您剛才建立的 [高敏感度]**** 標籤。
5. 在 [隱私權]**** 底下，按一下 [私人]****。
6. 輸入小組的名稱，然後按一下 [建立]****。
7. 將使用者新增至小組，然後按一下 [關閉]****。

## <a name="private-channel-settings"></a>私人頻道設定

在這一層中，我們會限制只有小組擁有者能夠建立私人頻道。

限制私人頻道的建立
1. 在該小組中，按一下 [更多選項]****，然後按一下 [管理小組]****。
2. 在 [設定]**** 索引標籤上展開 [成員權限]****。
3. 清除 [允許成員建立私人頻道]**** 核取方塊。

您也可以使用[小組原則](https://docs.microsoft.com/MicrosoftTeams/teams-policies)來控制可以建立私人頻道的人員。

## <a name="sharepoint-settings"></a>SharePoint 設定

每次使用高敏感度標籤建立新的小組時，都要在 SharePoint 中進行兩個步驟：

- 在 SharePoint 系統管理中心內更新網站的來賓共用設定，使其符合您在建立標籤時所選擇的設定，並將預設的共用連結更新為*擁有現有存取權的人員*。
- 更新網站本身的網站共用設定以防止成員共用檔案、資料夾或網站，並關閉存取要求。

### <a name="site-guest-sharing-settings"></a>網站的來賓共用設定

您在建立標籤時所選擇的來賓共用設定 (這只會影響小組成員資格) 應符合相關聯 SharePoint 網站的來賓共用設定，如下所示：

|標籤設定|SharePoint 網站設定|
|:------------|:----------------------|
|已選取**讓 Office 365 群組擁有者將貴組織外部的人員新增到群組**|**新的及現有的來賓** (新小組的預設值)|
|未選取**讓 Office 365 群組擁有者將貴組織外部的人員新增到群組**|**只有貴組織中的人員**|

更新網站設定
1. 開啟 [SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)。
2. 在 [網站]**** 底下，按一下 [使用中網站]****。
3. 按一下與小組相關聯的網站。
4. 在 [原則]**** 索引標籤的 [外部共用]**** 底下，按一下 [編輯]****。
5. 如果您在建立高敏感度標籤時允許來賓共用，請確定您已選取 [新的及現有的來賓]****。 如果您在建立標籤時未允許共用，請選擇 [只有貴組織中的人員]****。
6. 在 [預設的共用連結類型] 底下，清除 [與組織層級設定相同]**** 核取方塊，然後選取 [擁有現有存取權的人員]****。
7. 按一下 [儲存]****。

如果您想要將此作業編寫為小組建立程序的一部分，則可以使用 [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) 並搭配下列參數：

- `-SharingCapability Disabled`，以關閉來賓共用 (預設為開啟)
- `-DefaultSharingLinkType Internal`，以將預設共用連結變更為 [特定人員]**

#### <a name="private-channels"></a>私人頻道

如果您在小組中新增私人頻道，則每個私人頻道都會使用預設的共用設定建立一個新的 SharePoint 網站。 這些網站不會顯示在 SharePoint 系統管理中心內，因此您必須使用 Set-SPOSite PowerShell Cmdlet 來更新來賓共用設定。

### <a name="site-sharing-settings"></a>網站共用設定

為了協助確保 SharePoint 網站不會與非小組成員的人員共用，我們將這種共用功能限制為只有擁有者能使用。 我們也會將檔案和資料夾的共用功能限制為只有小組擁有者能使用。 這可協助您確保每次有檔案與非小組人員共用時，擁有者都會知情。

設定僅限擁有者使用的網站共用功能
1. 在 Teams 中，瀏覽至所要更新小組的 [一般]**** 索引標籤。
2. 在小組的工具列中，按一下 [檔案]****。
3. 按一下省略符號，然後按一下 [在 SharePoint 中開啟]****。
4. 在基礎 SharePoint 網站的工具列中，按一下設定圖示，然後按一下 [網站權限]****。
5. 在 [網站權限] 窗格的 [共用設定]**** 之下，按一下 [變更共用設定]****。
6. 在 [共用權限]**** 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]****。
7. 將 [允許存取要求]**** 設定為 [關閉]****，然後按一下 [儲存]****。

## <a name="see-also"></a>另請參閱

[建立及設定敏感度標籤及其原則](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)

