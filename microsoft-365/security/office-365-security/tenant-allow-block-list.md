---
title: 在承租人允許/封鎖清單中管理您的允許和封鎖的 URLs
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何在安全性 & 合規性中心的承租人允許/封鎖清單中設定 URL 專案。
ms.openlocfilehash: 0fdfa23ba22b240032e7a6888948de180aa0f6ae
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614961"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a>管理租使用戶允許/封鎖清單中的 URL

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 本主題中所述的功能包括預覽、可能變更，而且無法在所有的組織中使用。

在使用 Exchange Online 或獨立 Exchange online (Protection 中信箱的 Microsoft 365 組織中，EOP) 組織沒有 Exchange Online 信箱，您可能會反對 EOP 篩選判定。 例如，良好的郵件可能會標示為壞的 (誤報) 或不良郵件可以透過 (誤報) 。

Security & 合規性中心內的承租人 Allow/封鎖清單可讓您手動覆寫 Microsoft 365 篩選 verdicts。 承租人允許/封鎖清單是在郵件流程期間和使用者按一下時使用。 您可以在 [承租人允許/封鎖] 清單中指定要允許或封鎖的 URLs。

本主題說明如何使用 Exchange Online 中的信箱，在 Security & 合規性中心或 PowerShell (Exchange Online PowerShell 中，設定 [安全性合規性中心] 或 [Exchange Online 365 中的專案。沒有 Exchange Online 信箱) 之組織的獨立 EOP PowerShell。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至「 **租使用者允許/封鎖清單** 」頁面，請使用 <https://protection.office.com/tenantAllowBlockList> 。

- 您可以在本主題稍後的 [承租人 Allow/封鎖清單區段之 url 語法](#url-syntax-for-the-tenant-allowblock-list) 中說明可用的 URL 值。

- 承租人允許/封鎖清單最多可以有500個專案可供 URLs。

- 專案應該在15分鐘內生效。

- 封鎖專案優先于允許專案。

- 根據預設，承租人允許/封鎖清單中的專案會在30天后到期。 您可以指定日期或將其設為永不過期。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必須在安全性 & 合規性中心指派許可權，才能執行本文中的程式：
  - 若要從 [承租人允許/封鎖] 清單中新增及移除值，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。
  - 若要取得租使用者 Allow/封鎖清單的唯讀許可權，您必須是 **全域讀取** 者或 **安全性讀取器** 角色群組的成員。

  如需詳細資訊，請參閱[安全性與合規性中心中的權限](permissions-in-the-security-and-compliance-center.md)。

  **附註**：

  - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供 [安全性與合規性中心] 所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[系統管理員角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>使用安全性 & 規範中心在承租人允許/封鎖清單中建立 URL 專案

如需 URL 專案之語法的詳細資訊，請參閱本主題稍後的 [承租人 Allow/封鎖清單區段的 URL 語法](#url-syntax-for-the-tenant-allowblock-list) 。

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。

2. 在 [**租使用者允許/封鎖清單**] 頁面上，確認已選取 [ **URLs** ] 索引標籤，然後按一下 [**新增**]

3. 在出現的 [ **新增 URLs** ] 浮出控制項中，設定下列設定：

   - **使用萬用字元新增 URLs**：每行輸入一個 URL，最多20個。

   - **封鎖/允許**：選取是否要 **允許** 或 **封鎖** 指定的 URLs。

   - **永不過期**：執行下列其中一個步驟：

     - 確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。

     或

     - 將切換向右移動，將專案設定為永不到期： ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **選用附注**：輸入專案的描述性文字。

4. 完成後，請按一下 [ **新增**]。

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>使用安全性 & 規範中心來查看承租人允許/封鎖清單中的專案

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。

2. 選取 [ **URLs** ] 索引標籤。

按一下下列欄標題，以遞增或遞減順序排序：

- **Value**
- **動作**： **封鎖** 或 **允許**。
- **上次更新日期**
- **有效期**
- **附註**

按一下 [ **群組** ]，依 **動作** 將專案群組 (**封鎖** 或 **允許**) 或 **無**。

按一下 [ **搜尋**]，輸入全部或部分的值，然後按 enter 以尋找特定值。 完成後，請按一下 [ **清除搜尋** ![ 清除搜尋] 圖示 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。

按一下 [ **篩選**]。 在出現的 [ **篩選** ] 浮出控制項中，設定下列任一設定：

- **動作**：選取 [ **允許**]、[ **封鎖** ] 或 [兩者]。

- **永不過期**：選取 [關閉] (![ 切換 ](../../media/scc-toggle-off.png)) 或 (![ 切換上的 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)) 。

- **上次更新**： **從**)  (的開始日期， (**為**) 或兩者的結束日期。

- **到期日**： **從**)  (的開始日期， (**為**) 或兩者的結束日期。

當您完成時 **，按一下 [** 套用]。

若要清除現有篩選，請按一下 [ **篩選**]，然後在出現的 [ **篩選** ] 浮出控制項中按一下 [ **清除篩選**]。

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>使用安全性 & 規範中心修改承租人允許/封鎖清單中的專案

您無法修改 URL 值本身。 相反地，您必須刪除該專案，然後重新建立。

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。

2. 選取 [ **URLs** ] 索引標籤。

3. 選取您要修改的專案，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。

4. 在出現的浮出控制項中，設定下列設定：

   - **封鎖/允許**：選取 [ **允許** ] 或 [ **封鎖**]。

   - **永不過期**：執行下列其中一個步驟：

     - 確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定輸入專案的到期日。

     或

     - 將切換向右移動，將專案設定為永不過期： ![開啟](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **選用附注**：輸入專案的描述性文字。

5. 完成後，按一下 **[儲存]**。

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>使用安全性 & 規範中心移除承租人允許/封鎖清單中的專案

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。

2. 選取 [ **URLs** ] 索引標籤。

3. 選取您要移除的專案，然後按一下 [ **刪除** ![ 刪除圖示] ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。

4. 在出現的警告對話方塊中，按一下 [ **刪除**]。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定承租人允許/封鎖清單

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 在承租人允許/封鎖清單中新增專案

若要在 [租使用者允許/封鎖] 清單中新增專案，請使用下列語法：

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

這個範例會新增 contoso.com 及所有子域 (的 URL 封鎖專案（例如，contoso.com、www.contoso.com 及 xyz.abc.contoso.com) ）。 因為我們未使用 ExpirationDate 或 NoExpiration 參數，所以專案會在30天后到期。

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 來查看承租人允許/封鎖清單中的專案

若要在 [租使用者允許/封鎖] 清單中查看專案，請使用下列語法：

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

本範例會傳回所有封鎖的 URLs。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems)。

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 修改承租人 Allow/封鎖清單中的專案

您無法修改 URL 值本身。 相反地，您必須刪除該專案，然後重新建立。

若要修改承租人 Allow/封鎖清單中的專案，請使用下列語法：

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

本範例會變更指定專案的到期日。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

如需詳細的語法及參數資訊，請參閱 [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>使用 PowerShell 從承租人允許/封鎖清單中移除專案

若要移除承租人允許/封鎖清單中的專案，請使用下列語法：

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

此範例會從承租人允許/封鎖清單中移除指定的 URL 專案。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

如需詳細的語法及參數資訊，請參閱 [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems)。

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>承租人允許/封鎖清單的 URL 語法

- 允許 IP4v 和 IPv6 位址，但不會 TCP/UDP 埠。

- 不允許使用副檔名 (例如，test.pdf) 。

- 不支援 Unicode，但 Punycode 是。

- 如果下列所有陳述皆為 true，則允許主機名稱：

  - 主機名稱包含句點。
  - 句點的左側至少有一個字元。
  - 句點右側至少有兩個字元。

  例如， `t.co` 允許; `.com` 或是 `contoso.` 不允許。

- 不暗含子路徑。

  例如，不 `contoso.com` 包括 `contoso.com/a` 。

- 在下列案例中，允許使用萬用字元 ( * ) ：

  - 左邊的萬用字元必須後接句點，以指定子域。

    例如， `*.contoso.com` 允許; `*contoso.com` 是不允許的。

  - 右萬用字元必須跟隨正斜線 (/) 來指定路徑。

    例如， `contoso.com/*` 允許; `contoso.com*` 或是 `contoso.com/ab*` 不允許。

  - 所有的子路徑都不是以右邊的萬用字元隱含。

    例如，不 `contoso.com/*` 包括 `contoso.com/a` 。

  - `*.com*` 無效 (不是可解析的網域，正確的萬用字元不遵循正斜線) 。

  - IP 位址中不允許使用萬用字元。

- 在下列案例中，顎化 (~) 字元是可用的：

  - 左波形符表示網域和所有子域。

    例如 `~contoso.com` ，包含 `contoso.com` 和 `*.contoso.com` 。

- 包含通訊協定 (的 URL 專案例如， `http://` 、 `https://` 或 `ftp://`) 會失敗，因為 url 專案適用于所有通訊協定。

- 不支援或不需要使用者名稱或密碼。

- 引號 ( ' 或 ") 是不正確字元。

- URL 應盡可能包括所有重新導向。

### <a name="url-entry-scenarios"></a>URL 專案案例

有效的 URL 專案及其結果將在下列各節中說明。

#### <a name="scenario-no-wildcards"></a>案例：沒有萬用字元

**專案**： `contoso.com`

- **允許相符**： contoso.com

- **允許不符合**：

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www .com/q = a@contoso .com

- **Block match**：

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www .com/q = a@contoso .com

- **不符合的區塊**： abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>案例：保留萬用字元 (子域) 

**專案**： `*.contoso.com`

- **允許相符** 和 **區塊相符**：

  - www.contoso.com
  - xyz.abc.contoso.com

- **允許不符合** 或 **不符合的封鎖**：

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>案例：路徑頂端的右萬用字元

**專案**： `contoso.com/a/*`

- **允許相符** 和 **區塊相符**：

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso/a/？ q = joe@t .com

- **允許不符合** 或 **不符合的封鎖**：

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www .com/q = a@contoso .com

#### <a name="scenario-left-tilde"></a>案例：左波形符

**專案**： `~contoso.com`

- **允許相符** 和 **區塊相符**：

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **允許不符合** 或 **不符合的封鎖**：

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>案例：右萬用字元尾碼

**專案**： `contoso.com/*`

- **允許相符** 和 **區塊相符**：

  - contoso （.com）/？ q = whatever@fabrikam .com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **允許不符合** 或 **不符合的封鎖**： contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>案例： Left 通配子域和右萬用字元尾碼

**專案**： `*.contoso.com/*`

- **允許相符** 和 **區塊相符**：

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **允許不符合** 或 **不符合的封鎖**： contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>案例：左和右顎化符

**專案**： `~contoso.com~`

- **允許相符** 和 **區塊相符**：

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **允許不符合** 或 **不符合的封鎖**：

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>案例： IP 位址

**專案**： `1.2.3.4`

- **允許** 比對和 **區塊相符**：1.2.3。4

- **允許不符合** 或 **不符合的封鎖**：

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>具有右萬用字元的 IP 位址

**專案**： `1.2.3.4/*`

- **允許相符** 和 **區塊相符**：

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>無效專案的範例

下列專案是不正確：

- **遺失或不正確網域值**：

  - 尚未
  - \*尚未.\*
  - \*.com
  - \*.pdf

- **文字上的萬用字元，或不含間距的字元**：

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **含埠的 IP 位址**：

  - contoso.com:443
  - abc.contoso.com:25

- **非描述萬用字元**：

  - \*
  - \*.\*

- **中間的萬用字元**：

  - conto \* so.com
  - conto ~ .com

- **兩個萬用字元**

  - contoso.com/\*\*
  - contoso.com/\*/\*
