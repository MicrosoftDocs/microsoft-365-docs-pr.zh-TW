---
title: Office 365 群組命名原則
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: 了解如何建立 Office 365 群組命名原則。
ms.openlocfilehash: 50ea076e22680a444cb9acf04466a7e7d052bb7a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239226"
---
# <a name="office-365-groups-naming-policy"></a>Office 365 群組命名原則

您可以使用群組命名原則強制執行一致的命名策略，組織中使用者所建立的群組。 命名原則可協助您和您的使用者識別群組成員資格、 地理區域的函式或建立群組的人員。 命名原則也有助於分類在通訊錄中的群組。 您可以使用原則來封鎖特定字詞，防止正在使用中群組的名稱和別名。

命名原則會套用至跨所有群組工作負載 （例如 Outlook、 Microsoft Teams、 SharePoint、 規劃、 Yammer、 等等） 所建立的群組。 它會套用到的群組名稱和群組的別名。 它會取得套用當使用者建立的群組和群組名稱或別名時為編輯現有的群組。

> [!TIP]
> Office 365 群組命名原則僅適用於 Office 365 群組。 它不會套用至 Exchange Online 中建立的通訊群組。 若要建立通訊群組命名原則，請參閱[建立通訊群組命名原則](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)。

群組命名原則包含下列功能：

- **前置詞尾碼命名原則**： 您可以使用前置詞或尾碼至定義群組的命名慣例 (例如: 「 群組\_美國\_我的群組\_工程 」)。 會取得替代的使用者屬性像是 [部門] 根據建立群組的使用者或首碼/尾碼可以都是固定的字串。

- **自訂封鎖的文字**： 您可以將一組的封鎖特定的文字上傳至其會封鎖使用者所建立的群組中的組織。 (例如: 「 CEO、 薪資，人力資源 」)。

## <a name="licensing-requirements"></a>授權需求

使用 Azure AD 命名原則之 Office 365 群組需要您擁有，但不是一定是指派給 Azure Active Directory 進階版 P1 授權或 Azure AD 基本教育授權的每個唯一的使用者 （包括訪客） 是一或多個 Office 365 群組的成員。
這也是必要的系統管理員所建立的群組命名原則。

## <a name="prefix-suffix-naming-policy"></a>前置詞尾碼的命名原則

首碼和尾碼可以也被固定的字串或使用者屬性。

### <a name="fixed-strings"></a>固定的字串

您可以使用簡短的字串，可協助您區別 GAL] 和 [左導覽中的群組工作負載的群組。 一些常見前置詞尾碼是類似的關鍵字 '群組\_名稱 '、'\#名稱 '、'\_名稱 '

### <a name="attributes"></a>屬性

您可以使用屬性，可協助您識別人員建立像是 [部門] 群組，其中它所建立像是 [國家/地區]。

|||
|:-----|:-----|
|**範例**|原則 = 」 群組 [群組名稱] [部門]"|
||使用者的部門 = 工程|
||建立群組名稱 ="群組我群組工程 」|

支援的 Azure Active Directory (Azure AD) 屬性為 [部門]、 [公司]、 [Office]、 [StateOrProvince]，[CountryOrRegion]，[標題]

- 不支援的使用者屬性會被視為固定字串。 例如： "[郵遞區號]"

- 不支援延伸的屬性和自訂屬性。

建議您使用有值填入您的組織中的所有使用者的屬性，而且不使用有較長的值的屬性。

### <a name="things-to-look-out-for"></a>若要留意的事項

- 原則建立期間的總首碼和尾碼字串長度只有 53 的字元。

- 前置詞和尾碼可以包含群組名稱和群組的別名中支援的特殊字元。 當首碼和尾碼包含特殊字元。 不可用於群組別名時，他們會移除，並套用至群組的別名。 因此在此情況下，首碼和尾碼套用至群組名稱會是不同於套用至群組的別名。

- 如果您使用 Yammer Office 365 的連線群組，避免命名原則中使用下列字元: @， \#、 \[、 \]、 \<，和\>。 如果這些字元的命名原則中，一般的 Yammer 使用者將無法建立群組。

## <a name="custom-blocked-words"></a>自訂封鎖的文字

您可以輸入封鎖的文字，將會封鎖的逗號分隔清單中群組的名稱和別名。

[封鎖的文字] 核取是在使用者輸入群組名稱上執行。 因此，如果使用者在輸入 'darnit' 和 '前置詞\_' 已命名的原則，' 字首\_darnit' 將會失敗。

會不執行任何子字串搜尋;具體而言，輸入使用者名稱及自訂封鎖的文字完全相符，才能觸發失敗。 子字串搜尋未完成，這樣即使 '協助' 是封鎖的字，使用者可以使用一些常見的單字，如同 '類別'。

**若要留意的事項**：

- 封鎖的文字不區分大小寫。

- 當使用者在輸入封鎖的 word 時，群組用戶端會顯示錯誤訊息的已封鎖的字。

- 沒有使用封鎖的文字中的字元限制。

- 沒有上限 5000 文字的可設定為封鎖的文字。

## <a name="admin-override"></a>系統管理員覆寫

選擇性的系統管理員不需要這些原則，跨所有群組工作負載和端點，以便他們可以建立群組，這些封鎖的字詞與對其所需的命名慣例。 以下是系統管理員角色群組命名原則不受的清單。

- 全域系統管理員

- 合作夥伴第 1 層支援

- 合作夥伴第 2 層支援

- 使用者帳戶系統管理員

- 目錄作者

## <a name="how-to-set-up-the-naming-policy"></a>如何設定命名原則

若要設定的命名原則：

1. 在[Azure Active Directory](https://aad.portal.azure.com)中，按一下 [**管理**] 下的 [**群組**]。
2. 在 [**設定**] 下按一下 [**命名原則**]。
3. 選擇 [**群組命名原則**] 索引標籤。
4. 在**目前的原則**] 下選擇 [您是否需要前置詞或尾碼或以上兩者、，然後選取適當的核取方塊。
5. 選擇**屬性**和**字串**之間每一行，然後指定 [屬性] 或 [字串。
6. 當您已新增首碼和尾碼後，您需要時請按一下 [**儲存**]。

![群組命名原則 」 設定 Azure Active Directory 中的螢幕擷取畫面](../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a>不同 Office 365 應用程式的命名原則體驗

已更新的 Office 365 應用程式，以顯示預覽 （含前置詞和尾碼） 的命名原則群組名稱的使用者時輸入群組名稱和別名。 當使用者輸入封鎖的文字時，他們會看到一則錯誤訊息，讓他們可以移除封鎖的文字。

## <a name="outlook-on-the-web"></a>Outlook 網頁版

當使用者輸入群組名稱或群組的別名 （先前稱為 Outlook Web App 或 OWA） 網頁型 outlook 會顯示命名裝飾的原則名稱。 當使用者輸入自訂的封鎖的 word 時，錯誤訊息所示的封鎖的字以及 UI，讓使用者可以將它移除。 Outlook web 體驗快照集如下所示。

![並排檢視的群組命名原則在 Office 365 群組](../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a>Outlook 桌面

在 Outlook 桌面中建立的群組是相容命名原則。 Outlook 桌面應用程式尚未不會顯示預覽的命名原則，並不會傳回自訂封鎖的 word 錯誤，當使用者輸入群組名稱。 但是，命名原則會自動套用上選取 [建立/編輯，使用者將會出現錯誤如果有自訂封鎖的文字中的群組名稱或別名。

## <a name="microsoft-teams"></a>Microsoft Teams

使用者輸入的小組名稱時，Microsoft Teams 會顯示命名裝飾的原則名稱。 當使用者輸入自訂的封鎖的 word 時，會顯示錯誤訊息以及封鎖的字，讓使用者可以將它移除。

![Microsoft Teams 中的群組命名原則封鎖範例](../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a>SharePoint

當使用者所輸入網站的名稱或群組電子郵件地址，SharePoint 會顯示命名的原則名稱。 當使用者在輸入自訂的封鎖的 word，錯誤訊息會顯示，以及封鎖 word，讓使用者可以將它移除。

![群組命名原則-SharePoint 網站封鎖名稱](../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a>Microsoft Stream

使用者輸入群組名稱或群組電子郵件別名時，Microsoft Stream 顯示命名裝飾的原則名稱。 當使用者輸入自訂的封鎖的 word 時，錯誤訊息會顯示的已封鎖的字，讓使用者可以將它移除。

![群組命名原則會封鎖 Microsoft Stream 範例](../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a>Outlook iOS 和 Android 應用程式

在 Outlook 應用程式中建立的群組是相容命名原則。 輸入群組名稱時，outlook 行動裝置會顯示命名原則預覽]。 當使用者輸入自訂的封鎖的 word 時，錯誤訊息會顯示在建立群組，讓使用者可以移除封鎖的單字。

## <a name="planner"></a>Planner

Planner 已符合命名原則。 規劃顯示命名原則預覽時輸入計劃名稱。 當使用者輸入自訂的封鎖的 word 時，會顯示一則錯誤訊息建立計劃，讓使用者可以移除封鎖的單字。

![群組命名原則： 建立新的已封鎖的規劃範例](../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a>Dynamics 365 for Customer Engagement

Dynamics 365 for Customer Engagement 是相容命名原則。 Dynamics 365 顯示命名裝飾的原則名稱，當使用者輸入群組名稱或群組電子郵件別名。 當使用者輸入自訂的封鎖的 word 時，錯誤訊息會顯示的已封鎖的字，讓使用者可以將它移除。

![Dynamics 365](../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a>學校資料同步 (SDS)

透過 SDS 建立的群組遵守命名原則，但命名原則不會自動套用。 SDS 系統管理員必須將首碼和尾碼附加到其群組需要建立，然後上傳至 SDS 的類別名稱。 群組建立/編輯否則就會失敗。

## <a name="outlook-customer-manager-ocm"></a>Outlook Customer Manager (OCM)

Outlook Customer Manager 是相容命名原則。 命名原則會自動套用至建立 Outlook Customer Manager 中的群組。 如果任何內 「 所有銷售小組 」 文字定義為自訂的封鎖 word，將會封鎖 OCM 中的建立群組。 使用者將無法建立 OCM 群組，並將無法使用 OCM 應用程式。 」

## <a name="classroom-app"></a>教室應用程式

在教室應用程式中建立的群組遵守命名原則，但命名原則不會自動套用，命名原則預覽不會對使用者顯示時輸入教室群組名稱。 讓使用者必須輸入裝飾的教室的群組名稱具有前置詞和尾碼。 否則教室群組建立或編輯會失敗，錯誤。

## <a name="power-bi"></a>Power BI

在 Power BI 工作區中建立的群組遵守命名原則，但命名原則不會自動套用。 並命名原則預覽不會顯示給使用者時使用者輸入的 Power BI 工作區名稱。

建議的名稱-與套用-命名原則會顯示的錯誤的詳細資訊建立或編輯工作區中。 這表示使用者必須輸入裝飾工作區名稱具有前置詞和尾碼。 否則請在工作區建立或編輯會失敗，錯誤。

## <a name="yammer"></a>Yammer

當使用者與自己的 Azure Active Directory 帳戶登入 Yammer 建立的群組，或編輯群組名稱時，群組名稱會遵守命名原則。 這適用於同時連線的 Office 365 群組及所有其他的 Yammer 群組。

如果 Office 365 連線的群組命名原則會就地之前建立的群組名稱將不會自動追蹤的命名原則。 當使用者編輯的群組名稱時，系統會提示他們新增首碼和尾碼。

如果命名原則包含無法在 Yammer 群組名稱中的字元，僅限系統管理員將能夠在 Yammer 中建立的連線的群組。

## <a name="staffhub"></a>StaffHub

StaffHub teams 不適用的命名原則，但基礎的 Office 365 群組。 StaffHub 小組名稱不適用的首碼和尾碼，而且不會檢查自訂封鎖的文字。 但 StaffHub 並套用首碼和尾碼，並從基礎的 Office 365 群組中移除封鎖的文字。

## <a name="exchange-powershell"></a>Exchange PowerShell

Exchange PowerShell cmdlet 是相容命名原則。 如果中的群組名稱和群組的別名不會使用命名慣例，使用者會收到適當的錯誤訊息與建議的首碼和尾碼，以及自訂封鎖的文字。

## <a name="azure-active-directory-powershell-cmdlets"></a>Azure Active Directory PowerShell cmdlet

Azure Active Directory PowerShell cmdlet 是相容命名原則。 如果中的群組名稱和群組的別名不會使用命名慣例，使用者會收到適當的錯誤訊息與建議的首碼和尾碼，以及自訂封鎖的文字。

## <a name="exchange-admin-center"></a>Exchange 系統管理中心

在 Exchange 系統管理中心 (EAC) 是相容命名原則。 在建立或編輯動作，使用者會收到適當的錯誤訊息與建議的首碼和尾碼，以及自訂封鎖的文字，如果中的群組名稱和群組的別名不會使用命名慣例。

## <a name="microsoft-365-admin-center"></a>Microsoft 365 系統管理中心

在 Microsoft 365 系統管理中心是相容命名原則。 在建立或編輯動作，命名原則將會自動套用。 當使用者輸入自訂封鎖的文字時，使用者會收到適當的錯誤。 在 Microsoft 365 系統管理中心還不會顯示預覽的命名原則，並不會傳回自訂封鎖的 word 錯誤，當使用者輸入群組名稱。

## <a name="azure-active-directory-portal"></a>Azure Active Directory 入口網站

在 Azure Active Directory 入口網站是相容命名原則。 Azure Active Directory 入口網站中顯示的命名原則預覽時輸入群組名稱。 當使用者輸入自訂的封鎖的 word 時，錯誤訊息會顯示在建立群組，讓使用者可以移除封鎖的單字。

## <a name="more-articles-on-naming-policy"></a>更多文章命名原則

[強制執行 Azure Active Directory 中的 Office 365 群組命名原則](https://go.microsoft.com/fwlink/?linkid=868340)

[設定群組設定 azure Active Directory cmdlet](https://go.microsoft.com/fwlink/?linkid=868341)
