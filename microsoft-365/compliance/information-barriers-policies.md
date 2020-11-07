---
title: 定義資訊屏障原則
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
description: 瞭解如何在 Microsoft 小組中定義資訊障礙的原則。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ffeb1f1ca3296390fa10a636d3806127095712f8
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941428"
---
# <a name="define-information-barrier-policies"></a>定義資訊屏障原則

透過資訊障礙，您可以定義原則，以防止某些使用者區段進行通訊，或允許特定的區段只與特定其他的區段進行通訊。 資訊屏障原則可協助您的組織維持相關的行業標準與法規的遵從性，並避免潛在的利益衝突。 若要深入瞭解，請參閱 [資訊障礙](information-barriers.md)。 

本文說明如何規劃、定義、實施及管理資訊屏障原則。 包含數個步驟，且工作流程分為數個部分。 在您開始定義 (或編輯) 資訊屏障原則之前，請務必通讀 [必要條件](#prerequisites) 和整個程式。

> [!TIP]
> 本文包含 [範例案例](#example-contosos-departments-segments-and-policies) 和 [可下載的 Excel 活頁簿](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) ，可協助您規劃及定義資訊障礙原則。

## <a name="concepts-of-information-barrier-policies"></a>資訊屏障原則的概念

當您定義資訊障礙的原則時，您會使用使用者帳戶屬性、區段、「封鎖」和/或「允許」原則，以及原則應用程式。

- 使用者帳戶屬性是在 [Azure Active Directory (或 Exchange Online) 中定義。 這些屬性可包含部門、職稱、位置、小組名稱及其他工作設定檔詳細資料。 

- 區段是在安全性 & 合規性中心使用選取的 **使用者帳戶屬性** 定義的使用者集合。  (請參閱 [支援的屬性清單](information-barriers-attributes.md)。 )  

- 資訊屏障原則決定通訊限制或限制。 當您定義資訊屏障原則時，可以選擇兩種原則：
    - 「封鎖」原則防止一個區段與另一個區段通訊。
    - 「允許」原則允許一個區段只與特定其他的區段進行通訊。

- 原則應用程式是在定義所有資訊屏障原則之後完成，您準備好將它們套用到您的組織中。

## <a name="the-work-flow-at-a-glance"></a>工作流程概覽

|階段    |涉及的內容  |
|---------|---------|
|[請確定符合先決條件](#prerequisites)     |-確認您具備必要的 [授權和許可權](information-barriers.md#required-licenses-and-permissions)<br/>-確認您的目錄包含分割使用者的資料<br/>-針對 Microsoft 團隊啟用範圍型目錄搜尋<br/>-請確定已開啟審核記錄<br/>-確定沒有 Exchange 通訊錄原則已就緒<br/>-提供 (範例的使用 PowerShell) <br/>-提供 Microsoft 團隊的系統管理員同意 (步驟包括)           |
|[第1部分：分割組織中的使用者](#part-1-segment-users)     |-決定所需的原則<br/>-建立區段清單以定義<br/>-識別要使用的屬性<br/>-以原則篩選的條款定義區段        |
|[第2部分：定義資訊障礙原則](#part-2-define-information-barrier-policies)     |-定義您的原則 (未套用) <br/>-從兩種 (封鎖或允許) 選擇 |
|[第3部分：套用資訊障礙原則](#part-3-apply-information-barrier-policies)     |-將原則設為主動狀態<br/>-執行原則應用程式<br/>-查看原則狀態         |
| (視需要) [編輯區段或原則](information-barriers-edit-segments-policies.md)    |-編輯區段<br/>-編輯或移除原則<br/>-重新執行原則應用程式<br/>-查看原則狀態         |
| (視需要) [疑難排解](information-barriers-troubleshooting.md)|-當事情沒有如預期的運作時採取動作|

## <a name="prerequisites"></a>必要條件

除了 [必要的授權和許可權](information-barriers.md#required-licenses-and-permissions)之外，請確定符合下列需求： 
     
- 目錄資料-確保您的組織結構反映在目錄資料中。 若要這麼做，請確定在 Azure Active Directory (或 Exchange Online) 中正確填入使用者帳戶屬性（如群組成員資格、部門名稱等）。 若要深入了解，請參閱下列資源：
  - [資訊屏障原則的屬性](information-barriers-attributes.md)
  - [使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [使用 Office 365 PowerShell 中設定使用者帳戶屬性](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)

- 範圍型目錄搜尋-在您定義組織的第一個資訊障礙原則之前，您必須 [在 Microsoft 小組中啟用範圍型目錄搜尋](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)。 在您設定或定義資訊屏障原則之前，請先等候至少24小時後，再啟用範圍目錄搜尋。

- 審核記錄-為了查詢原則應用程式的狀態，必須開啟審核記錄。 在您開始定義區段或原則之前，我們建議您這麼做。 若要深入瞭解，請參閱 [開啟或關閉審核記錄搜尋](turn-audit-log-search-on-or-off.md)。

- 無通訊錄原則-在您定義及套用資訊屏障原則之前，請確定沒有任何 Exchange 通訊錄原則存在到位。 資訊障礙是以通訊錄原則為基礎，但這兩種原則不相容。 如果您有這類原則，請務必先 [移除您的通訊錄原則](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy) 。 一旦資訊障礙原則已啟用，且您已啟用階層式通訊錄，「資訊屏障」區段中的 [所有 *_未包含_* 的使用者] 都會看到 Exchange online 中的 [階層式通訊錄](https://docs.microsoft.com/exchange/address-books/hierarchical-address-books/hierarchical-address-books) 。

- 目前 PowerShell 中，資訊屏障原則是在 Office 365 安全性 & 規範中心使用 PowerShell Cmdlet 來定義及管理。 雖然本文提供了數個範例，但您需要熟悉 PowerShell Cmdlet 及參數。 您也會需要 Azure PowerShell 模組。
    - [連線到安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)
    - [安裝 Azure PowerShell 模組](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-2.3.2)

- 管理員對 Microsoft 小組資訊障礙的同意-當您的原則就緒時，資訊障礙可以從聊天會話中移除人員。 這可協助確保您的組織符合原則及規定。 使用下列程式可讓資訊障礙原則在 Microsoft 小組中如預期的方式運作。 

   1. 執行下列 PowerShell Cmdlet：

      ```powershell
      Connect-AzureAD 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. 出現提示時，使用您的公司或學校帳戶登入 Office 365。

   3. 在 [ *要求的許可權* ] 對話方塊中，複查資訊，然後選擇 [ **接受** ]。

當滿足所有必要條件時，請繼續進行下一節。

> [!TIP]
> 為了協助您準備方案，本文包含範例案例。 [請參閱 Contoso 的部門、區段和原則](#example-contosos-departments-segments-and-policies)。<p>此外，也可以使用可下載的 Excel 活頁簿，協助您規劃及定義您的區段和原則 (及建立 PowerShell Cmdlet) 。 [取得活頁簿](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)。 

## <a name="part-1-segment-users"></a>第1部分：區段使用者

在此階段中，您可以決定所需的資訊屏障原則、建立區段清單以加以定義，然後定義您的區段。

### <a name="determine-what-policies-are-needed"></a>決定所需的原則

考慮法律和行業法規，誰是組織內需要資訊屏障原則的群組？ 建立清單。 是否有任何群組應該禁止與另一個群組進行通訊？ 是否有任何群組應該允許只與一或兩個其他群組進行通訊？ 請考慮您需要的原則屬於兩個群組中的其中一個：
- 「封鎖」原則防止一個群組與另一個群組進行通訊。
- 「允許」原則允許群組只與特定其他特定群組進行通訊。

當您擁有群組和原則的初始清單時，請繼續識別您所需的區段。 

### <a name="identify-segments"></a>識別區段

除了您的初始原則清單之外，還請為您的組織製作一個段落清單。 將包含在資訊屏障原則中的使用者應屬於某個區段。 小心規劃您的區段，因為使用者只能在一個段落內。 每個區段只能套用一個資訊障礙原則。

> [!IMPORTANT]
> 使用者只能在一段內。

決定您的組織目錄資料中所要用來定義段落的屬性。 您可以使用 *部門* 、 *MemberOf* 或任何支援的屬性。 請確定您為使用者選取的屬性中有值。 [請參閱資訊障礙的支援屬性清單](information-barriers-attributes.md)。

> [!IMPORTANT]
> **繼續進行下一節之前，請確定您的目錄資料具有可用於定義區段之屬性的值** 。 如果您的目錄資料沒有您想要使用的屬性值，則必須更新使用者帳戶，以包含該資訊，然後再繼續進行資訊障礙。 若要取得這項協助，請參閱下列資源：<br/>- [使用 Office 365 PowerShell 設定使用者帳戶屬性](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)<br/>- [使用 Azure Active Directory 新增或更新使用者的設定檔資訊](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>使用 PowerShell 定義線段

定義區段不會影響使用者;它只會針對要定義並套用的資訊屏障原則，設定階段。

1. 使用 **OrganizationSegment 指令程式** 搭配 **UserGroupFilter** 參數，該參數會對應至您想要使用的 [屬性](information-barriers-attributes.md) 。

    |語法   |範例  |
    |---------|---------|
    |`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`     |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>在此範例中，稱為 *hr* 的區段是使用 *hr* ，以 [ *部門* ] 屬性中的值來定義。 Cmdlet 的 **-eq** 部分參照 "equals"。  (或者，您可以使用 **-ne** 表示 "not equals"。 請參閱 [片段定義中的 Using "equals" 和 "not equals"](#using-equals-and-not-equals-in-segment-definitions)。 )         |

    在您執行每個 Cmdlet 後，您應該會看到有關新區段的詳細資料清單。 詳細資料包含區段的類型、建立或上次修改者的類型等等。 

2. 針對您要定義的每個區段重複此程式。

    > [!IMPORTANT]
    > **請確定您的區段沒有重迭** 。 由資訊障礙影響的每位使用者應屬於一個 (，而且只有一個) 的區段。 任何使用者都不應屬於兩個以上的區段。  (請參閱 [範例： Contoso 在本文中定義的區段](#contosos-defined-segments) 。 ) 


在您定義好資料段後，請繼續 [定義資訊障礙原則](#part-2-define-information-barrier-policies)。

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>在段落定義中使用 "equals" 和 "not ="

在下列範例中，我們定義的是 "部門等於 HR" 的區段。 

|範例  |
|---------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>請注意，在此範例中，線段定義包含表示為 **-eq** 的 "equals" 參數。 
  |

您也可以使用 "not equals" 參數定義線段，以表示為 **-ne** ，如下表所示：

|語法  |範例  |
|---------|---------|
|`New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"`   | <p>在此範例中，我們會定義一個稱為 *NotSales* 的區段，其中包含不在 *銷售* 人員的任何人。 Cmdlet 的 **-ne** 部分參照 "not equals"。  |

除了使用 "equals" 或 "not equals" 定義區段之外，您還可以使用 "equals" 和 "not equals" 參數定義區段。 您也可以使用邏輯 *AND* 和 *OR* 運算子定義複雜的群組篩選。


|語法    |範例  |
|---------|---------|
|`New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` |<p>在此範例中，我們會定義一個稱為 *LocalFTE* 的區段，其中包含位於本機的使用者，且其位置並未列出為 *暫時* 的。    |
 |`New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`|  <p>在此範例中，我們會定義一個稱為 *Segment1* 的區段，其中包含 group1@contoso.com 成員的人員，而不是 group3@contoso.com 的成員。
|`New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | 在此範例中，我們會定義一個稱為 *Segment2* 的區段，其中包含 group2@contoso.com 成員的人員，而不是 group3@contoso.com 的成員。
|`New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`|  在此範例中，我們會定義一個稱為 *Segment1and2* 的區段，其中包含 group1@contoso.com 和 group2@contoso.com 的人員，而不是 group3@contoso.com 的成員。


> [!TIP]
> 如果可能的話，請使用包含 "-eq" 或 "-ne" 的區段定義。 請不要定義複雜的區段定義。

## <a name="part-2-define-information-barrier-policies"></a>第2部分：定義資訊障礙原則

決定您是否需要防止某些區段之間的通訊，或限制對特定的區段進行通訊。 理想狀況下，您會使用最低原則數目，以確保您的組織符合法律和行業的需求。

在您的使用者區段清單和您想要定義的資訊屏障原則中，選取案例，然後依照步驟執行。 

- [案例1：封鎖區段之間的通訊](#scenario-1-block-communications-between-segments)
- [案例2：允許區段只與其他一個段落通訊](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> 請 **務必在定義原則時，不要將多個原則指派給一個段落** 。 例如，如果您為一個稱為 *sales* 的區段定義一個原則，請勿為 *sales* 定義其他原則。<p>此外，在您定義資訊屏障原則時，請務必將這些原則設為非使用中狀態，直到您準備好套用這些原則為止。 定義 (或編輯) 原則不會影響使用者，除非這些原則設為 [使用中狀態]，然後套用。

 (請參閱 [範例： Contoso 的資訊屏障原則](#contosos-information-barrier-policies) 中的專案。 ) 

### <a name="scenario-1-block-communications-between-segments"></a>案例1：封鎖區段之間的通訊

當您想要封鎖彼此之間的通訊時，您會定義兩個原則：每個方向一個。 每個原則只會封鎖單向通訊。

例如，假設您想要封鎖段 A 與區段 B 之間的通訊。在此情況下，您會定義一個原則，讓區段 A 無法與段落 B 通訊，然後定義第二個原則，以防止 A 欄位 B 與 A 欄位進行通訊。

1. 若要定義您的第一個封鎖原則，請使用具有 **SegmentsBlocked** 參數的 **InformationBarrierPolicy** Cmdlet。 

    |語法  |範例  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"`     |`New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p>    在此範例中，我們為稱為 *sales* 的區段定義名為「 *銷售調研* 」的原則。 使用中並套用此原則，可防止 *銷售* 人員與稱為「 *調研* 」區段中的人員進行通訊。         |

2. 若要定義第二個封鎖段，請再次使用具有 **SegmentsBlocked** 參數的 **InformationBarrierPolicy 指令程式** ，這次會將段落顛倒。

    |範例  |
    |---------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p>    在此範例中，我們會定義稱為「 *調查銷售* 」的原則，以防止「 *調查* 」與「 *銷售* 」通訊。     |

2. 請繼續執行下列其中一項動作：

   - 如有需要， () [定義原則以允許區段只與其他一個網段進行通訊](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - 在定義所有原則之後 () 套用 [資訊屏障原則](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>案例2：允許區段只與其他一個段落通訊

1. 若要允許一個區段只與一個其他的區段進行通訊，請使用具有 **SegmentsAllowed** 參數的 **InformationBarrierPolicy** Cmdlet。 

    |語法  |範例  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"`     |`New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p>    在此範例中，我們為稱為「 *製造* 」的區段定義稱為「 *製造業-HR* 」的原則。 使用中並套用此原則時，可讓 *製造業* 中的人員只與稱為 *HR* 的區段中的人員進行通訊。  (在此案例中， *製造業* 無法與不屬於 *人力資源* 的使用者進行通訊。 )          |

    **如有需要，您可以使用此 Cmdlet 來指定多個區段，如下列範例所示。**

    |語法  |範例  |
    |---------|---------|
    |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"`     |`New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p>在此範例中，我們定義了一個原則，可讓 *調查* 區段只與 *HR* 和 *製造業* 通訊。        |

    針對您要定義的每個原則重複此步驟，以允許特定的區段只與特定的特定區段進行通訊。

2. 請繼續執行下列其中一項動作：

   - 如有需要，請 () [定義原則以封鎖區段之間的通訊](#scenario-1-block-communications-between-segments) 
   - 在定義所有原則之後 () 套用 [資訊屏障原則](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>第3部分：套用資訊障礙原則

資訊屏障原則除非您將其設定為 [使用中] 狀態，然後再套用原則，否則不會生效。

1. 使用 **InformationBarrierPolicy 指令程式** 來查看已定義的原則清單。 請注意每個原則的狀態及身分識別 (GUID) 。

    語法： `Get-InformationBarrierPolicy`

2. 若要將原則設定為作用中狀態，請使用 **InformationBarrierPolicy** 指令程式搭配 **Identity** 參數，並將 **State** 參數設定為 **active** 。 

    |語法  |範例  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Active`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p>    在此範例中，我們會設定具有 GUID *43c37853-ea10-4b90-a23d-ab8c93772471* 為 [使用中] 狀態的資訊屏障原則。   |

    請視需要針對每個原則重複此步驟。

3. 當您完成將資訊屏障原則設定為 [使用中狀態] 時，請使用安全性 & 規範中心中的 **Start-InformationBarrierPoliciesApplication** Cmdlet。

    語法： `Start-InformationBarrierPoliciesApplication`

    在您執行 `Start-InformationBarrierPoliciesApplication` 允許30分鐘之後，系統才開始套用原則。 系統會將原則使用者套用至使用者。 一般系統處理每小時大約5000的使用者帳戶。

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>查看使用者帳戶、區段、原則或原則應用程式的狀態

透過 PowerShell，您可以查看使用者帳戶、區段、原則及原則應用程式的狀態，如下表所列。

|若要查看此  |執行此動作  |
|---------|---------|
|使用者帳戶     |使用具有 Identity 參數的 **InformationBarrierRecipientStatus** Cmdlet。 <p>語法： `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>您可以使用唯一識別每個使用者的任何值，例如名稱、別名、辨別名稱、正常化功能變數名稱、電子郵件地址或 GUID。 <p>範例：`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>在此範例中，我們會參考 Office 365 中的兩個使用者帳戶： *meganb* for *Megan* 和 *alexw* for *Alex* 。 <p> (您也可以將此 Cmdlet 用於單一使用者： `Get-InformationBarrierRecipientStatus -Identity <value>`)  <p>此 Cmdlet 會傳回使用者的相關資訊，例如屬性值以及所套用的任何資訊屏障原則。|
|段     |使用 **OrganizationSegment** Cmdlet。<p>語法： `Get-OrganizationSegment` <p>這會顯示針對您組織所定義的所有區段清單。         |
|資訊屏障原則     |使用 **InformationBarrierPolicy** Cmdlet。 <p> 語法： `Get-InformationBarrierPolicy` <p>這會顯示已定義的資訊屏障原則清單，及其狀態。       |
|最新的資訊屏障原則應用程式     | 使用 **InformationBarrierPoliciesApplicationStatus** Cmdlet。 <p>語法： `Get-InformationBarrierPoliciesApplicationStatus`<p>    這會顯示原則應用程式已完成、失敗或進行中的相關資訊。       |
|所有資訊屏障原則應用程式|使用 `Get-InformationBarrierPoliciesApplicationStatus -All`<p>這會顯示原則應用程式已完成、失敗或進行中的相關資訊。|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>如果我需要移除或變更原則，該怎麼辦？

資源可協助您管理資訊屏障原則。

- 如果發生資訊障礙問題，請參閱 [疑難排解資訊障礙](information-barriers-troubleshooting.md)。

- 若要停止套用原則，請參閱 [停止原則應用程式](information-barriers-edit-segments-policies.md#stop-a-policy-application)。

- 若要移除資訊障礙原則，請參閱 [移除原則](information-barriers-edit-segments-policies.md#remove-a-policy)。

- 若要變更區段或原則，請參閱 [Edit (或 remove) 資訊關卡原則](information-barriers-edit-segments-policies.md)。

## <a name="example-contosos-departments-segments-and-policies"></a>範例： Contoso 的部門、區段和原則

若要查看組織如何使用定義區段和原則的方法，請考慮下列範例。

### <a name="contosos-departments-and-plan"></a>Contoso 的部門與計畫

Contoso 有五個部門： HR、Sales、Marketing、Research 及製造業。 為了維持與業界法規的相容性，某些部門中的人員不應該與其他部門通訊，如下表所列：

|段  |可以交談  |無法交談  |
|---------|---------|---------|
|人力資源     |所有人         | (無限制)          |
|銷售     |HR、行銷、製造業         |參考資料         |
|行銷     |所有人         | (無限制)          |
|參考資料     |HR、行銷、製造業        |銷售     |
|製造業 |人力資源、行銷 |HR 或 Marketing 以外的任何人員 |

考慮到這一點，Contoso 的計畫包括三項資訊障礙原則：

1. 一個原則，可防止銷售人員與調研 (及另一個原則通訊，以防止調查與銷售) 通訊
2. 原則設計，只允許製造業與 HR 和 Marketing 進行通訊 

不需要為 HR 或 Marketing 定義原則。

### <a name="contosos-defined-segments"></a>Contoso 的定義區段

Contoso 會使用 Azure Active Directory 中的部門屬性定義區段，如下所示：

|部門  |段定義  |
|---------|---------|
|人力資源     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|銷售     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|行銷     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|參考資料     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|製造業     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

在定義的區段中，Contoso 會繼續定義原則。 

### <a name="contosos-information-barrier-policies"></a>Contoso 的資訊屏障原則

Contoso 定義三個原則，如下表所述：

|原則  |原則定義  |
|---------|---------|
|原則1：防止銷售人員與調查進行通訊     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> 在此範例中，資訊屏障原則稱為「 *銷售-調研* 」。 當您使用並套用此原則時，會協助避免銷售資料段中的使用者與研究資料段中的使用者進行通訊。 這是單向原則;它不會防止「調查」與銷售進行通訊。 針對此，需要原則2。      |
|原則2：防止調查與銷售通訊     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> 在此範例中，資訊屏障原則稱為「 *調研-銷售* 」。 當您使用並套用此原則時，它會協助避免使用調查區段中的使用者與銷售部門中的使用者進行通訊。       |
|原則3：允許製造業只與 HR 和 Marketing 通訊     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p>在此情況下，資訊屏障原則稱為「 *製造-HRMarketing* 。 當您使用並套用此原則時，製造只能與 HR 和 Marketing 進行通訊。 請注意，HR 和 Marketing 不會受到限制，無法與其他的區段進行通訊。 |

在定義的區段和原則中，Contoso 會執行 **InformationBarrierPoliciesApplication** Cmdlet 來套用原則。 

當該完成時，Contoso 符合法律和行業的需求。

## <a name="related-articles"></a>相關文章

- [取得資訊障礙的概覽](information-barriers.md)

- [Microsoft 小組的資訊障礙](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
