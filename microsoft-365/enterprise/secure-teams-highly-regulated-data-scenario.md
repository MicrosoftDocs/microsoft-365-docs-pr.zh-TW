---
title: 適用於高度管制資料的 Microsoft Teams
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 建立安全小組來儲存您最重要且最敏感的檔案。
ms.openlocfilehash: 5117d310ccd877a7377e6e538e7fba13daaad4ef
ms.sourcegitcommit: 80dc9ceb14e3eb3ae61b0fc2c8c3d73d564a7ef9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2019
ms.locfileid: "37617261"
---
# <a name="teams-for-highly-regulated-data"></a>適用於高度管制資料的 Microsoft Teams

本文提供在 Microsoft Teams 中設定私人小組的建議和步驟，讓您可以鎖定如聊天、會議和檔案等 Microsoft Teams 功能的存取權，僅供小組中 Office 365 群組的成員和擁有者使用。 

除了 Office 365 群組基本的私用存取外，本文還說明如何針對儲存高度管制資料所需的額外安全性，設定基礎的私人 SharePoint 小組網站，此網站可透過小組頻道的 [檔案]**** 區段進行存取。 在此 SharePoint 小組網站中，您可以對檔案、頁面、共用行事曆、工作、筆記本和清單進行儲存和共同作業。

針對高度管制資料，小組需要設定的元素有：

- 私人小組，具有對應的 Office 365 群組，群組中有擁有者和成員使用者帳戶。
- 小組的基礎 SharePoint 網站需要的額外安全性有：
  - 避免網站成員將存取權授與其他使用者。
  - 避免非網站成員要求網站的存取權。
- 基礎 SharePoint 網站的 Office 365 保留標籤，可自動套用到網站上的新檔案，作為定義保留原則的預設方法。
- 資料外洩防護 (DLP) 原則，利用保留標籤封鎖使用者對組織外部共用或傳送檔案。
- Office 365 敏感度標籤或高度管制標籤的子標籤，已啟用加密且對小組的 Office 365 群組具有共同撰寫權限。 使用者可以從 Word、Excel 和 PowerPoint 的 [敏感度] 功能表列，將標籤或子標籤套用到儲存在小組中 [檔案]**** 區段的檔案。

以下是使用敏感度標籤所產生的組態。

![安全小組案例的組態](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)
 
## <a name="configuration"></a>組態

安全小組的端對端組態包括下列步驟：

1. 設定身分識別和裝置存取。
2. 建立私人小組。
3. 設定基礎 SharePoint 網站的額外安全性。
4. 建立保留標籤和 DLP 原則。
5. 建立標籤或高度管制標籤的子標籤。

### <a name="step-1-configure-identity-and-device-access"></a>步驟 1：設定身分識別和裝置存取

若要保護小組及其基礎 SharePoint 網站的存取權，請確定您已設定[身分識別與裝置存取原則](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies)和建議的 [SharePoint Online 存取原則](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。

### <a name="step-2-create-a-private-team"></a>步驟 2：建立私人小組

利用[以下指示](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b)建立私人小組。

當您建立私人小組時，預設權限如下：

- 小組的 Office 365 群組 (以下稱「小組群組」) 有群組擁有者和群組成員
- 針對小組的基礎 SharePoint 網站 (以下稱「小組網站」)：
  - 網站集合系統管理員會設定為「小組群組」擁有者
  - 針對「小組網站」： 
    - 「小組網站」擁有者的 SharePoint 群組 (具有「完全控制」權限層級) 會設定為「小組群組」擁有者
    - 「小組網站」成員的 SharePoint 群組 (具有「編輯」權限層級) 會設定為「小組群組」成員
    - 「小組網站」訪客的 SharePoint 群組 (具有「讀取」權限層級) 沒有群組或使用者帳戶

以下是「小組網站」的預設權限。

![小組網站的預設權限](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
>如果您檢視 \<小組名稱> 擁有者的 SharePoint 群組的「編輯」權限層級，系統不會顯示 \<小組名稱> 擁有者。
>

所產生的權限允許：

- 「小組群組」擁有者可以管理網站並對網站內容擁有完全控制的權限。
- 「小組群組」成員可以建立和編輯網站上的檔案。 

權限的維護與小組成員及擁有者的維護相同。

以下是目前所產生的組態。

![安全小組案例的組態步驟 2](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a>步驟 3：設定基礎 SharePoint 網站的額外安全性

從「小組網站」設定這些權限設定。

1. 在工具列中，按一下設定圖示，然後按一下 [網站權限]****。
2. 在 [網站權限]**** 窗格的 [共用設定]**** 之下，按一下 [變更共用設定]****。
3. 在 [共用權限]**** 之下，選擇 [只有網站擁有者可以共用檔案、資料夾及網站]****。
4. 關閉 [允許存取要求]****，然後按一下 [儲存]****。

透過這些設定，「網站群組」成員要求「小組網站」存取權以與其他成員或非成員共用「小組網站」的功能將會停用。

以下是目前所產生的組態。

![安全小組案例的組態步驟 3](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a>步驟 4：建立保留標籤和 DLP 原則

利用[以下指示](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp)：

1. 建立和發佈高度管制資料的保留標籤 (如有需要的話)。
2. 針對步驟 1 中建立的保留標籤設定「小組網站」。
3. 使用在步驟 2 中建立的保留標籤建立高度管制資料的 DLP 原則，封鎖使用者對組織外部傳送檔案。 您也可以 [DLP 原則範本](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates)為基礎，針對其他要求設定原則，例如健康和金融業法規的要求。

以下是目前所產生的組態。

![安全小組案例的組態步驟 4](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a>步驟 5：建立標籤或高度管制標籤的子標籤

適用於高度管制資料的敏感度標籤可讓任何人套用至任何檔案，但是安全小組不同，安全小組需要自己的標籤或子標籤，使指派到的檔案都能：

- 受到加密，且加密會隨檔案移動。
- 包含自訂權限，因此只有「小組群組」成員能夠開啟檔案。

若要針對儲存在「小組網站」中的檔案完成這項額外的安全性層級，您必須設定一個新的敏感度標籤，這個標籤不是自有標籤就是一般標籤的子標籤，適用於高度管制檔案。 只有「小組群組」成員可以在標籤清單中看到這個標籤。

當您的需求是少量標籤、可同時用於全域使用和個別的私人小組時，請使用敏感度標籤。 當您有大量標籤或想要將私人小組的標籤整理在高度管制標籤之下時，請使用敏感度子標籤。

[使用下列指示](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)設定包含下列設定的不同標籤或子標籤：

- 標籤名稱包含有小組名稱
- 已啟用加密
- 「小組群組」具有共同撰寫權限

以下是新標籤所產生的組態。

![安全小組案例的組態步驟 5](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

以下是敏感度標籤和「小組群組」之間的關係。

![小組群組和標籤權限之間的關係](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
>如果您將敏感度標籤或子標籤設定為使用者定義的權限或設定有到期日，您將無法從 Microsoft Teams 或 SharePoint Online 開啟檔案。 您必須使用 Office 應用程式。
>

## <a name="using-the-team-and-a-sensitivity-label"></a>使用小組和敏感度標籤

「小組群組」成員可以存取小組及其所有資源，包括聊天、會議及其他應用程式。 使用頻道中 [檔案]**** 區段的檔案時，「小組群組」成員必須將敏感度標籤或子標籤指派給針對安全小組建立的檔案。 請見以下範例。

![將標籤套用到安全小組的檔案範例](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
當標籤套用到受保護的檔案時。 「小組群組」成員可以在 Microsoft Teams 中開啟，並即時進行共同作業。 檔案已加密，且包含有設定給「小組群組」成員的共同撰寫權限。 如果檔案離開網站並轉寄給惡意使用者，這些使用者必須提供「小組群組」成員的使用者帳戶認證，才能開啟檔案並檢視其內容。 

您可以在 SharePoint Online 檢視資料夾，然後透過 [新增欄]**** 的 [顯示/隱藏欄]**** 選項新增 [敏感度]**** 欄，查看哪些檔案有被指派標籤。

## <a name="custom-permissions"></a>自訂權限

您也可以針對「小組網站」設定自訂 SharePoint 網站權限和對應的敏感度標籤 (如有需要的話)。 以下列出兩個範例。

### <a name="example-1-delegating-sharepoint-site-administration"></a>範例 1：委派 SharePoint 網站的系統管理

如果小組擁有者沒有 SharePoint 系統管理經驗或是想要委派「小組網站」的系統管理，小組擁有者可以將 SharePoint 系統管理員的使用者帳戶新增至小組擁有者清單。 但是接下來，SharePoint 系統管理員會擁有小組及其所有資源的完整存取權，並且能夠開啟已套用敏感度標籤的檔案。 

為防止這種過度授與權限的情況發生，請在網站的進階權限設定中，將 SharePoint 系統管理員的使用者帳戶新增至「小組網站」擁有者的 SharePoint 群組。 SharePoint 系統管理員可以管理網站，但是無法存取小組及其任何資源，或是無法開啟已指派敏感度標籤的檔案。

### <a name="example-2-allowing-view-only-access-to-labeled-files"></a>範例 2：允許唯讀存取已加標籤的檔案

如果有部分人員只需要查看「小組網站」中已加標籤的檔案內容，請將這些人員的個人使用者帳戶新增至：

- \<小組名稱> 訪客的 SharePoint 群組，這個群組依預設擁有「讀取」權限層級。 
- 具有檢視者權限的敏感度標籤。

以下是標籤上所產生的權限。

![可檢視已加標籤的檔案的自訂權限範例](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
網站訪客將可以直接存取「小組網站」，並查看已套用子標籤的檔案內容。 但是，由於訪客不是「小組群組」成員，因此訪客無法存取小組或其任何資源。

## <a name="see-also"></a>另請參閱

[適用於高度管制資料的 SharePoint 網站](teams-sharepoint-online-sites-highly-regulated-data.md)

[部署指南](deploy-microsoft-365-enterprise.md)
