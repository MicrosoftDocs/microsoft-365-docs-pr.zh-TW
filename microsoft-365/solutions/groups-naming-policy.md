---
title: Microsoft 365 群組命名原則
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: 瞭解如何為 Microsoft 365 群組建立命名原則。
ms.openlocfilehash: acf660375508760bd2e9874a07454709849929b0
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759821"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 群組命名原則

您可以使用群組命名原則，針對組織中使用者所建立的群組強制執行一致的命名策略。 命名原則可協助您和您的使用者識別群組、成員資格、地理區域的功能，或群組的建立者。 命名原則也可協助分類通訊錄中的群組。 您可以使用原則來封鎖群組名稱和別名中所用的特定字詞。

命名原則會套用至所有群組工作負載 (例如 Outlook、Microsoft 團隊、SharePoint、Planner、Yammer 等 ) 上建立的群組。 它會套用至群組名稱和群組別名。 當使用者建立群組時，以及在編輯現有群組的組名、別名、描述或頭像時，也會套用此方式。

> [!TIP]
> Microsoft 365 群組命名原則只適用于 Microsoft 365 群組。 這不適用於 Exchange Online 中所建立的通訊群組。 若要建立通訊群組的命名原則，請參閱 [建立通訊群組命名原則](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)。

群組命名原則包含下列功能：

- **前置詞尾碼命名原則**：您可以使用首碼或尾碼來定義群組的命名慣例 (例如：「US \_ My Group 工程」 \_ ) 。 首碼/尾碼可以是固定字串或像是 [部門] 的使用者屬性，會根據建立群組的使用者進行取代。

- **自訂封鎖的字**：您可以上傳組織中特定的封鎖文字集合，這些文字會在使用者建立的群組中封鎖。  (例如： "CEO，工資表，HR" ) 。

## <a name="licensing-requirements"></a>授權需求

使用 Microsoft 365 群組的 Azure AD 命名原則，您必須擁有但不一定要為每個唯一的使用者 (（包括一或多個 Microsoft 365 群組成員的來賓) ）指派 Azure Active Directory Premium P1 授權或 Azure AD 基本 EDU 授權。

這對於建立群組命名原則的系統管理員也是必要的。

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix 命名原則

首碼和尾碼可以是固定字串或使用者屬性。

### <a name="fixed-strings"></a>固定字串

您可以使用簡短字串，協助您區分 GAL 中的群組和群組工作負載的左側導覽。 部分常見的首碼尾碼為 "Grp \_ Name"、" \# name"、" \_ name" 等關鍵字

### <a name="attributes"></a>屬性

您可以使用屬性來識別建立群組的人員，例如 [部門]，以及從 [Country] 建立群組的位置。

範例:

- Policy = "GRP [GroupName] [部門]"
- 使用者的部門 = 工程
- 建立的組名 = "GRP My Group 工程"

支援的 Azure Active Directory (Azure AD) 屬性為 [部門]、[公司]、[Office]、[StateOrProvince]、[CountryOrRegion] 和 [Title]。

- 不支援的使用者屬性被視為固定字串，例如 [郵遞區號]。

- 不支援擴充屬性和自訂屬性。

建議您使用為組織中所有使用者填寫值的屬性，而不要使用具有較長值的屬性。

### <a name="things-to-look-out-for"></a>要查看的專案

- 在建立原則時，總的首碼和尾碼字串長度限制為53個字元。

- 首碼和尾碼可以包含組名和群組別名中支援的特殊字元。 當前綴和尾碼包含不允許在群組別名中使用的特殊字元時，它們只適用于組名。 因此，在此情況下，套用至群組名稱的首碼和尾碼會與套用至群組別名的首碼和尾碼不同。

  > [!NOTE]
  > 句點 (。 ) 或連字號 ( ) 允許在組名中的任何位置，但名稱的開頭或結尾除外。 在群組名稱中的任何地方（包括名稱的開頭或結尾）都允許有底線 (_) 。

- 如果您使用 Yammer Office 365 連接的群組，請避免在您的命名原則中使用下列字元： @、、、、 \# \[ \] \<, and \> 。 如果這些字元是在命名原則中，一般 Yammer 使用者將無法建立群組。

> [!Tip]
> - 使用簡短字串做為尾碼。
> - 使用具有值的屬性。
> - 不太創造性，總名稱長度的最大值為264個字元。
> - 上傳組織的特定封鎖文字，以限制使用。

## <a name="custom-blocked-words"></a>自訂封鎖的字詞

您可以輸入將會在群組名稱和別名中封鎖的封鎖文字，以逗號分隔的清單。

不會執行任何子字串搜尋;具體說來，使用者輸入名稱和自訂封鎖字詞之間的完全相符，會觸發失敗。

**要查看的專案**：

- 封鎖的文字不區分大小寫。

- 當使用者輸入封鎖的單字時，群組用戶端將會以封鎖的字詞顯示錯誤訊息。

- 使用的封鎖字中沒有字元限制。

- 5000個字的限制可設為封鎖字。

## <a name="admin-override"></a>管理員覆寫

有些管理員會在所有群組的工作負載和端點中免除這些原則，讓他們可以使用這些封鎖的字和其所需的命名慣例來建立群組。 以下是免除群組命名原則之系統管理員角色的清單。

- 全域系統管理員

- 合作夥伴第1層支援

- 合作夥伴第2層支援

- 使用者帳戶管理員

## <a name="how-to-set-up-the-naming-policy"></a>如何設定命名原則

若要設定命名原則：

1. 在 [Azure Active Directory](https://aad.portal.azure.com)的 [ **管理**] 下，按一下 [ **群組**]。
2. 在 [ **設定**] 底下，按一下 [ **命名原則**]。
3. 選擇 [ **群組命名原則** ] 索引標籤。
4. 在 [ **目前原則**] 底下，選擇您是否要要求前置詞或尾碼或兩者，然後選取適當的核取方塊。
5. 選擇每一行的 **屬性** 及 **字串** ，然後指定屬性或字串。
6. 當您已新增所需的首碼和尾碼後，請按一下 [ **儲存**]。

![Azure Active Directory 中群組命名原則設定的螢幕擷取畫面](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>相關主題

[共同作業管理規劃逐步](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[建立共同作業管理計畫](collaboration-governance-first.md)

[用於設定群組設定的 Azure Active Directory Cmdlet](https://go.microsoft.com/fwlink/?linkid=868341)
