---
title: 在承租人允許/封鎖清單中管理您的允許和封鎖
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 系統管理員可以在安全性入口網站中瞭解如何在承租人允許/封鎖清單中設定允許和封鎖。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 270e38d65857de2f4d06460fb3bb77f72a165ecf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538960"
---
# <a name="manage-the-tenant-allowblock-list"></a>管理租用戶允許/封鎖清單中

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> 本文所述的功能都是在預覽中，可能會變更，而且無法在所有的組織中使用。  如果您的組織沒有如本文所述的欺騙功能，請參閱 [使用哄騙智慧原則管理冒牌寄件者的舊版欺騙管理經驗和 EOP 中的欺騙智慧洞察力](walkthrough-spoof-intelligence-insight.md)。
>
> 在此時間內，您無法在 [租使用者允許/封鎖] 清單中 **設定** 允許的 URL 或檔專案。

在 Microsoft 365 具有 Exchange Online 或獨立 Exchange Online Protection 中信箱的組織 (EOP) 組織沒有 Exchange Online 信箱，您可能會反對 EOP 篩選判定。 例如，良好的郵件可能會標示為壞的 (誤報) 或不良郵件可以透過 (誤報) 。

Security & 合規性中心內的承租人 Allow/封鎖清單，可讓您以手動方式覆寫 Microsoft 365 篩選 verdicts。 承租人允許/封鎖清單是在郵件流程期間和使用者按一下時使用。 您可以指定下列覆寫類型：

- 要封鎖的 URLs。
- 要封鎖的檔案。
- 允許的大宗郵件寄件者網域。 如需大宗郵件、大量信賴等級 (BCL) ，以及反垃圾郵件原則的大宗郵件篩選的詳細資訊，請參閱 [EOP 中的大量投訴 (BCL) ](bulk-complaint-level-values.md)。
- 要允許或封鎖的欺騙寄件者。 [！注意] 如果您在 [哄騙情報洞察力](learn-about-spoof-intelligence.md)中覆寫 allow 或 block 判定，則哄騙寄件者會變成隻會出現在 [租使用者允許/封鎖] 清單的 [ **哄騙** ] 索引標籤上的手動允許或封鎖專案。 您也可以在這裡，以欺騙的寄件者的方式手動建立允許或封鎖專案，以供欺詐情報偵測到。

本文說明如何在「安全性 & 合規性中心」或「PowerShell (Exchange Online PowerShell 中設定使用者在 Microsoft 365 中使用信箱的 Exchange Online 組織的專案。組織的獨立 EOP PowerShell，不 Exchange Online 信箱) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 您要在 <https://protection.office.com/> 開啟安全性與合規性中心。 若要直接移至「 **租使用者允許/封鎖清單** 」頁面，請使用 <https://protection.office.com/tenantAllowBlockList> 。

- 您可以使用檔案的 SHA256 雜湊值來指定檔案。 若要在 Windows 中尋找檔案的 SHA256 雜湊值，請在命令提示字元中執行下列命令：

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  例如，此值可能為 `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`。 不支援可感知雜湊 (pHash) 值。

- 在本文稍後的 [承租人允許/封鎖清單區段的 url 語法](#url-syntax-for-the-tenant-allowblock-list) 中，會說明可用的 URL 值。

- 承租人允許/封鎖清單可為 URLs 和500專案提供檔案雜湊的最大值為500專案。

- 每個專案的字元數上限為：
  - 檔雜湊 = 64
  - URL= 250

- 專案應該在30分鐘內生效。

- 根據預設，承租人允許/封鎖清單中的專案會在30天后到期。 您可以指定日期或將其設為永不過期。

- 若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您必須已在 Exchange Online 中獲派權限，才能執行此文章中的程序：
  - **URLs、檔案及允許大量寄件者**：
    - 若要從 [承租人允許/封鎖] 清單中新增及移除值，您必須是「 **組織管理** 」或「 **安全性管理員** 」角色群組的成員。
    - 若要取得租使用者 Allow/封鎖清單的唯讀許可權，您必須是 **全域讀取** 者或 **安全性讀取器** 角色群組的成員。
  - **哄騙**：下列其中一個組合：
    - **組織管理**
    - **安全性管理員**<u>和</u> **View-Only** 設定或 **View-Only 組織管理**。

  如需詳細資訊，請參閱 [Exchange Online 中的權限](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  >
  > - 在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供所需的權限 _和_ Microsoft 365 中其他功能的權限。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a>使用安全性 & 規範中心在承租人允許/封鎖清單中建立封鎖 URL 專案

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。

2. 在 [**承租人允許/封鎖清單**] 頁面上，確認已選取 [ **URLs** ] 索引標籤，然後按一下 [**封鎖**]。

3. 在出現的 [ **封鎖 URLs** 浮出] 中，設定下列設定：

   - **新增封鎖 URLs**：每行輸入一個 URL，最多20個。 如需 URL 專案之語法的詳細資訊，請參閱本文稍後的 [承租人 Allow/封鎖清單區段的 URL 語法](#url-syntax-for-the-tenant-allowblock-list) 。

   - **永不過期**：執行下列其中一個步驟：

     - 確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。

       或

     - 將切換向右移動，將專案設定為永不到期： ![開啟](../../media/scc-toggle-on.png).

   - **選用附注**：輸入專案的描述性文字。

4. 完成後，按一下 **[新增]**。

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a>使用安全性 & 規範中心在承租人允許/封鎖清單中建立封鎖檔案專案

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。

2. 在 [ **承租人允許/封鎖清單** **] 頁面** 上，選取 [檔案] 索引標籤，然後按一下 [ **封鎖**]。

3. 在 [ **新增要封鎖** 浮出的浮出] 快顯視窗中，設定下列設定：

   - **新增檔案雜湊**：每行輸入一個 SHA256 雜湊值，最多20個。

   - **永不過期**：執行下列其中一個步驟：

     - 確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。

     或

     - 將切換向右移動，將專案設定為永不到期： ![開啟](../../media/scc-toggle-on.png).

   - **選用附注**：輸入專案的描述性文字。

4. 完成後，按一下 **[新增]**。

## <a name="use-the-security--compliance-center-to-create-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a>使用安全性 & 合規性中心建立承租人允許/封鎖清單中的允許大宗郵件寄件者網域專案

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。

2. 在 [ **承租人允許/封鎖清單** ] 頁面上，選取 [BCL 旁路] 索引標籤的 [ **寄件者網域** ]，然後按一下 [ **新增**]。

3. 在 [ **新增加入寄件者的網域** ] 中，出現出現的 BCL 略過浮出控制項，設定下列設定：

   - **新增地域略過的寄件者網域**：每行輸入一個適當大宗郵件的來源域，最多20個。

   - **永不過期**：執行下列其中一個步驟：

     - 確認已關閉此設定 (![ 切換 ](../../media/scc-toggle-off.png)) 並使用 [ **到期** 日] 方塊來指定專案的到期日。

     或

     - 將切換向右移動，將專案設定為永不到期： ![開啟](../../media/scc-toggle-on.png).

4. 完成後，按一下 **[新增]**。

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>使用安全性 & 規範中心在承租人允許/封鎖清單中建立允許或封鎖欺騙寄件者專案

**附註**：

- 只會明確允許或封鎖欺騙使用者 _與_ 網域對中所定義之傳送基礎結構的 _組合_。
- 當您設定網域對的 allow 或封鎖專案時，來自該網域對的郵件就不會再出現在欺騙性智慧洞察力中。
- 欺騙寄件者的專案永不過期。

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。

2. 在 [ **承租人允許/封鎖清單** ] 頁面上，選取 [ **哄騙** ] 索引標籤，然後按一下 [ **新增**]。

3. 在出現的 [ **新增網域配對** ] 浮出控制項中，設定下列設定：

   - **使用萬用字元新增網域配對**：每行輸入一個網域對，最多20個。 如需有關欺騙寄件者之語法的詳細資訊，請參閱本文稍後的 [承租人允許/封鎖清單區段中的欺騙寄件者專案的網域對語法](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) 。

   - **哄騙類型**：選取下列其中一個值：
     - **Internal**：哄騙寄件者位於屬於您組織 ([公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) 中的網域。
     - **外部**：冒牌寄件者位於外部網域。

   - **動作**：選取 [ **允許** ] 或 [ **封鎖**]。

4. 完成後，按一下 **[新增]**。

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>使用安全性 & 規範中心來查看承租人允許/封鎖清單中的專案

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。

2. 選取您想要的索引標籤。 可用的欄取決於您所選取的索引標籤：

   - **URLs**：
     - **值**： URL。
     - **動作**：值 **區塊**。
     - **上次更新日期**
     - **有效期**
     - **附註**

   - **Files**
     - **值**：檔雜湊。
     - **動作**：值 **區塊**。
     - **上次更新日期**
     - **有效期**
     - **附註**

   - **BCL 略過的寄件者網域**
     - **值**：大宗郵件寄件者的網域。
     - **上次更新日期**
     - **有效期**

   - **詐騙**
     - **偽裝的使用者**
     - **傳送基礎結構**
     - **哄騙類型**：值 **Internal** 或 **External**。
     - **動作**：值 **組塊** 或 **Allow**。

   您可以按一下欄標題，以遞增或遞減順序排序。

   您可以按一下 [ **群組** ] 以群組結果。 可用的值取決於您所選取的索引標籤：

   - **URLs**：您可以依 **動作** 將結果分組。
   - 檔案 **：您** 可以依 **動作** 將結果分組。
   - 在此索引標籤上無法使用 **群組****的寄件者網域**。
   - **哄騙**：您可以依 **動作** 或 **偽造類型** 來分組結果。

   按一下 [ **搜尋**]，輸入全部或部分的值，然後按 enter 以尋找特定值。 完成後，請按一下 [ **清除搜尋** ![ 清除搜尋] 圖示 ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) 。

   按一下 [ **篩選** ] 以篩選結果。 顯示的 [ **篩選** ] 浮出控制項中可用的值，取決於您所選取的索引標籤：

   - **URL**
     - **Action**
     - **永不到期**
     - **上次更新日期**
     - **有效期**

   - **Files**
     - **Action**
     - **永不到期**
     - **上次更新日期**
     - **有效期**

   - **BCL 略過的寄件者網域**
     - **永不到期**
     - **上次更新日期**
     - **有效期**

   - **詐騙**
     - **Action**
     - **哄騙類型**

   當您完成時 **，按一下 [** 套用]。 若要清除現有篩選，請按一下 [ **篩選**]，然後在出現的 [ **篩選** ] 浮出控制項中按一下 [ **清除篩選**]。

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>使用安全性 & 規範中心修改承租人允許/封鎖清單中的專案

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。

2. 選取 [包含您要修改之專案類型的] 索引標籤：
   - **URL**
   - **Files**
   - **BCL 略過的寄件者網域**
   - **詐騙**

3. 選取您要修改的專案，然後按一下 [ **編輯** ![ 編輯圖示] ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) 。 您可以在出現的浮出控制項中修改的值，取決於您在上一個步驟中選取的索引標籤：

   - **URL**
     - **永不到期** 及（或）到期日。
     - **選用附注**

   - **Files**
     - **永不到期** 及（或）到期日。
     - **選用附注**

   - **BCL 略過的寄件者網域**
     - **永不到期** 及（或）到期日。

   - **詐騙**
     - **動作**：您可以將值變更為 [ **允許** ] 或 [ **封鎖**]。

4. 完成後，按一下 ****[儲存]。

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>使用安全性 & 規範中心移除承租人允許/封鎖清單中的專案

1. 在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **承租人允許/封鎖清單**。

2. 選取 [包含您要移除之專案類型的] 索引標籤：
   - **URL**
   - **Files**
   - **BCL 略過的寄件者網域**
   - **詐騙**

3. 選取您要移除的專案，然後按一下 [ **刪除** ![ 刪除圖示] ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) 。

4. 在出現的警告對話方塊中，按一下 [ **刪除**]。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定承租人允許/封鎖清單

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a>使用 PowerShell 將封鎖檔案或 URL 專案新增至承租人允許/封鎖清單

若要在承租人允許/封鎖清單中新增封鎖檔或 URL 專案，請使用下列語法：

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

這個範例會為永不到期的指定檔案新增封鎖檔專案。

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

這個範例會新增 contoso.com 及所有子域 (的封鎖 URL 專案（例如，contoso.com、www.contoso.com 及 xyz.abc.contoso.com) ）。 因為我們未使用 ExpirationDate 或 NoExpiration 參數，所以專案會在30天后到期。

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="use-powershell-to-add-allow-bulk-mail-sender-domain-entries-to-the-tenant-allowblock-list"></a>使用 PowerShell 新增允許大宗郵件寄件者網域專案至租使用者允許/封鎖清單

若要新增「租使用者允許/封鎖」清單中的允許大宗郵件寄件者網域專案，請使用下列語法：

```powershell
New-TenantAllowBlockListItems -ListType BulkSender -Block:$false -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

此範例會為永不到期的指定網域新增允許的大量寄件者專案。

```powershell
New-TenantAllowBlockListItem -ListType BulkSender -Block:$false -Entries contosodailydeals.com
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a>使用 PowerShell 將允許或封鎖冒牌寄件者專案新增至承租人允許/封鎖清單

若要在承租人允許/封鎖清單中新增欺騙寄件者專案，請使用下列語法：

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 在承租人允許/封鎖清單中查看封鎖檔案或 URL 專案

若要在 [租使用者允許/封鎖] 清單中查看封鎖檔案或 URL 專案，請使用下列語法：

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

此範例會傳回指定之檔案雜湊值的資訊。

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

本範例會傳回所有封鎖的 URLs。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。

### <a name="use-powershell-to-view-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 以查看允許在承租人允許/封鎖清單中大宗郵件寄件者的網域專案

若要在 [租使用者允許/封鎖] 清單中查看 [允許大宗郵件寄件者網域專案]，請使用下列語法：

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender [-Entry <BulkSenderDomainValue>] [<-ExpirationDate Date | -NoExpiration>]
```

此範例會傳回所有允許的大宗郵件寄件者網域。

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender
```

此範例會傳回指定之大量寄件者網域的資訊。

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "contosodailydeals.com"
```

如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>在承租人允許/封鎖清單中使用 PowerShell 來查看允許或封鎖欺騙寄件者專案

若要在 [租使用者允許/封鎖] 清單中查看欺騙寄件者專案，請使用下列語法：

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

本範例會傳回 [承租人允許/封鎖] 清單中的所有冒牌寄件者專案。

```powershell
Get-TenantAllowBlockListSpoofItems
```

此範例會傳回所有內部皆為內部的寄件者專案。

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

此範例會傳回所有外部已封鎖的寄件者專案。

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems)。

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a>在承租人允許/封鎖清單中使用 PowerShell 修改區塊檔案與 URL 專案

若要修改承租人 Allow/封鎖清單中的封鎖檔案及 URL 專案，請使用下列語法：

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

本範例會變更指定的封鎖 URL 專案的到期日。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

如需詳細的語法及參數資訊，請參閱 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="use-powershell-to-modify-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a>在承租人允許/封鎖清單中使用 PowerShell 修改允許大宗郵件寄件者網域專案

若要修改允許租使用者/封鎖清單中的大宗郵件寄件者網域專案，請使用下列語法：

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

此範例會將指定之允許大宗郵件寄件者網域專案的到期變更為永不過期。

```powershell
Set-TenantAllowBlockListItems -ListType BulkSender -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -NoExpiration
```

如需詳細的語法及參數資訊，請參閱 [TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>使用 PowerShell 修改承租人 Allow/封鎖清單中的允許或封鎖欺騙寄件者專案

若要修改承租人 Allow/封鎖清單中的 [允許] 或 [封鎖欺騙的寄件者] 專案，請使用下列語法：

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

本範例會將冒牌寄件者專案從 allow 變更為封鎖。

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

如需詳細的語法及參數資訊，請參閱 [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems)。

### <a name="use-powershell-to-remove-bulk-mail-sender-domain-file-and-domain-entries-from-the-tenant-allowblock-list"></a>使用 PowerShell 從承租人允許/封鎖清單中移除大宗郵件寄件者網域、檔案及網域專案

若要從承租人允許/封鎖清單中移除 [允許大宗郵件寄件者網域專案]、[封鎖檔案專案] 及 [封鎖 URL] 專案，請使用下列語法：

```powershell
Remove-TenantAllowBlockListItems -ListType <BulkSender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

此範例會從承租人允許/封鎖清單中移除指定的封鎖 URL 專案。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

如需詳細的語法及參數資訊，請參閱 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)。

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>使用 PowerShell 從承租人允許/封鎖清單中移除允許或封鎖欺騙寄件者專案

若要從 [承租人允許/封鎖] 清單中移除 [允許] 或 [封鎖欺騙寄件者] 專案，請使用下列語法：

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

如需詳細的語法及參數資訊，請參閱 [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)。

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
  - www.contoso.com/q=a@contoso.com

- **Block match**：

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

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
  - contoso.com/a/?q=joe@t.com

- **允許不符合** 或 **不符合的封鎖**：

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

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

  - contoso.com/?q=whatever@fabrikam.com
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

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>承租人允許/封鎖清單中的欺騙寄件者專案的網域對語法

在承租人允許/封鎖清單中，欺騙寄件者的網域對使用下列語法： `<Spoofed user>, <Sending infrastructure>` 。

- **冒牌使用者**：此值包含欺騙使用者的電子郵件地址，顯示在電子郵件客戶程式的 [ **寄件者** ] 方塊中。 此位址也稱為 `5322.From` 位址。 有效值包括：
  - 個別的電子郵件地址 (例如，chris@contoso.com) 。
  - 電子郵件網域 (例如，contoso.com) 。
  - 通配字元 (例如， \*) 。

- 傳送 **基礎結構**：此值表示來自欺騙使用者的郵件來源。 有效值包括：
  - ) 來源電子郵件伺服器的 IP 位址的反向 DNS 查閱 (PTR 記錄中找到的網域 (例如，fabrikam.com) 。
  - 如果來源 IP 位址沒有 PTR 記錄，則會將傳送基礎結構識別為 \<source IP\> /24 (例如，192.168.100.100/24) 。

以下是有效網域組的一些範例，用以識別冒牌寄件者：

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

新增網域對只會允許或封鎖欺騙使用者 *和* 傳送基礎結構的 *組合*。 它不允許來自欺騙使用者的電子郵件來自任何來源，也不允許任何欺騙使用者的傳送基礎結構來源傳送電子郵件。

例如，您新增下列網域對的 allow 專案：

- **網域**： gmail.com
- **基礎結構**： tms.mx.com

只允許來自該網域 *和* 傳送基礎結構的郵件進行欺騙。 不允許其他企圖哄騙 gmail.com 的寄件者。 來自來自 tms.mx.com 的來自其他網域中寄件者的郵件會由哄騙情報檢查。
