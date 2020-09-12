---
title: 準備將目錄同步處理至 Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 說明如何準備使用目錄同步處理將使用者布建至 Microsoft 365，以及使用此方法的長期優點。
ms.openlocfilehash: 790ea72879a40681447a2ca2ef883c7c601ba475
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546683"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>準備將目錄同步處理至 Microsoft 365

*本文適用于 Microsoft 365 Enterprise 和 Microsoft 365 企業版。*

組織的混合式身分識別與目錄同步處理帶來的好處包括：

- 減少組織中的系統管理程式
- 選擇性啟用單一登入案例
- 自動化 Microsoft 365 中的帳戶變更

如需使用目錄同步處理之優點的詳細資訊，請參閱[Microsoft 365](plan-for-directory-synchronization.md)的[目錄同步處理藍圖]( https://go.microsoft.com/fwlink/p/?LinkId=525398)和混合身分識別。

不過，目錄同步處理需要規劃及準備，以確保您的 Active Directory 網域服務 (AD DS) 會同步處理至您的 Microsoft 365 訂閱的 Azure Active Directory (Azure AD) 租使用者，至少有錯誤。

請遵循下列步驟，以取得最佳結果。

## <a name="1-directory-cleanup-tasks"></a>1. 目錄清理任務

將 AD DS 同步處理到 Azure AD 租使用者之前，您需要清理您的 AD DS。

> [!IMPORTANT]
> 如果您在同步處理之前未執行 AD DS 清除，則部署程式可能會有嚴重的負面影響。 可能需要數天甚至數周才能完成目錄同步處理的週期、識別錯誤，以及重新同步處理。

在您的 AD DS 中，針對每個將指派 Microsoft 365 授權的使用者帳戶，完成下列清理工作：

1. 請確定 **proxyAddresses** 屬性中有有效且唯一的電子郵件地址。

2. 移除 **proxyAddresses** 屬性中的任何重複值。

3. 如果可能的話，請確認使用者**使用者**物件中**userPrincipalName**屬性的有效且唯一的值。 為了獲得最佳同步處理體驗，請確定 AD DS UPN 符合 Azure AD UPN。 如果使用者沒有 **userPrincipalName** 屬性的值，則 **user** 物件必須包含 **sAMAccountName** 屬性的有效且唯一的值。 移除 **userPrincipalName** 屬性中的任何重複值。

4. 為 (GAL) 的全域通訊清單的最佳使用，請確定 AD DS 使用者帳戶的下列屬性資訊正確：

   - givenName
   - 姓
   - displayName
   - 職稱
   - 部門
   - 辦公室
   - 辦公室電話
   - 行動電話
   - 傳真號碼
   - 街道地址
   - 城市
   - 州/省
   - 郵遞區號
   - 國家或地區

## <a name="2-directory-object-and-attribute-preparation"></a>2. 目錄物件和屬性準備

在您的 AD DS 和 Microsoft 365 間成功的目錄同步處理，需要您的 AD DS 屬性已正確準備。 例如，您必須確定特定的字元沒有用於與 Microsoft 365 環境同步處理的某些屬性。 非預期的字元不會造成目錄同步處理失敗，但可能會傳回警告。 不正確字元會導致目錄同步處理失敗。

如果某些 AD DS 使用者有一個或多個重複的屬性，目錄同步處理也會失敗。 每個使用者都必須有唯一的屬性。

您需要準備的屬性如下所列：

- **displayName**

  - 如果屬性存在於使用者物件中，則會與 Microsoft 365 同步處理。
  - 如果此屬性存在於使用者物件中，則必須有一個值。 也就是說，屬性必須不是空白的。
  - 字元數上限：256

- **givenName**

  - 如果屬性存在於使用者物件中，則會與 Microsoft 365 同步處理，但是 Microsoft 365 不需要或使用它。
  - 字元數上限：64

- **mail**

  - 屬性值在目錄中必須是唯一的。

    > [!NOTE]
    > 如果有重複的值，則會同步處理第一個具有值的使用者。 後續的使用者將不會出現在 Microsoft 365 中。 您必須修改 Microsoft 365 中的值，或修改 AD DS 中的兩個值，這兩個使用者才能出現在 Microsoft 365 中。

- **mailNickname** (Exchange 別名) 

  - 屬性值不得以句點 ( 開頭。 ) 。
  - 屬性值在目錄中必須是唯一的。

    > [!NOTE]
    > 在同步處理名稱中 ( "_" ) 會指出此屬性的原始值包含不正確字元。 如需此屬性的詳細資訊，請參閱 [Exchange alias 屬性](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)。
    >

- **proxyAddresses**

  - 多重值屬性
  - 每個值的字元數上限：256
  - 屬性值不能包含空格。
  - 屬性值在目錄中必須是唯一的。
  - 無效字元： \< \> ( ) ;，[] "'

    請注意，不正確字元會套用到類型分隔符號後的字元和 "："，因此允許 SMTP:User@contso.com，但 SMTP:user:M@contoso.com 不是。

    > [!IMPORTANT]
    > 所有的簡易郵件傳輸通訊協定 (SMTP) 位址應該符合電子郵件訊息標準。 若存在重複或不需要的位址，請參閱協助主題 [移除 Exchange 中的重複和有害 proxy 位址](https://go.microsoft.com/fwlink/?LinkId=293860)。

- **sAMAccountName**

  - 字元數上限：20
  - 屬性值在目錄中必須是唯一的。
  - 無效字元： [\ "|，/： \< \> + =;？ \* ']
  - 如果使用者的 **sAMAccountName** 屬性無效，但是具有有效的 **userPrincipalName** 屬性，則會在 Microsoft 365 中建立使用者帳戶。
  - 如果 **sAMAccountName** 和 **userPrincipalName** 都無效，則必須更新 AD DS **userPrincipalName** 屬性。

- **sn** (姓) 

  - 如果屬性存在於使用者物件中，則會與 Microsoft 365 同步處理，但是 Microsoft 365 不需要或使用它。

- **targetAddress**

    需要 **targetAddress** 屬性 (例如，為使用者填入的 SMTP:tom@contoso.com) 必須出現在 MICROSOFT 365 GAL 中。 在協力廠商郵件遷移案例中，這需要 AD DS 的 Microsoft 365 架構擴充。 Microsoft 365 架構擴充也會新增其他有用的屬性，以管理從 AD DS 使用目錄同步處理工具填入的 Microsoft 365 物件。 例如，將會新增用以管理隱藏信箱或通訊群組的 **msExchHideFromAddressLists** 屬性。

  - 字元數上限：256
  - 屬性值不能包含空格。
  - 屬性值在目錄中必須是唯一的。
  - 無效字元： \ \< \> ( ) ;，[] "
  - 所有的簡易郵件傳輸通訊協定 (SMTP) 位址應該符合電子郵件訊息標準。

- **userPrincipalName**

  - **UserPrincipalName**屬性必須是網際網路樣式的登入格式，其中使用者名稱後面接 @ 符號 ( @ ) 和功能變數名稱：例如，user@contoso.com。 所有的簡易郵件傳輸通訊協定 (SMTP) 位址應該符合電子郵件訊息標準。
  - **UserPrincipalName**屬性的字元數上限為113。 在 sign ( @ ) 之前和之後均可使用特定的字元數，如下所示：
  - 在 sign ( @ ) 前面的使用者名稱字元數上限：64
  - At 符號 ( @ ) 所遵循的功能變數名稱字元數上限：48
  - 無效字元： \% &amp; \* +/=？ { } | \< \> ( ) ; : , [ ] " '
  - 母音變音符也是不正確字元。
  - 每個 **userPrincipalName** 值都需要 @ 字元。
  - 每個 **userPrincipalName** 值中不能是 @ 字元的第一個字元。
  - 使用者名稱不得以句點 ( ) 、& 符號 (&amp;) 、空格或 at 符號 ( @ ) 。
  - 使用者名稱不得包含任何空格。
  - 必須使用可路由的網域;例如，不能使用本機或內部網域。
  - Unicode 會轉換成底線字元。
  - **userPrincipalName** 不能包含目錄中的任何重複值。

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. 準備 userPrincipalName 屬性

Active Directory 的設計目的是讓您組織中的使用者可以使用 **sAMAccountName** 或 **userPrincipalName**登入您的目錄。 同樣地，使用者可以使用使用者主要名稱 (其工作或學校帳戶的 UPN) 登入 Microsoft 365。 目錄同步處理嘗試使用 AD DS 中的同一個 UPN，在 Azure Active Directory 中建立新的使用者。 UPN 的格式就像電子郵件地址。

在 Microsoft 365 中，UPN 是用來產生電子郵件地址的預設屬性。 在 AD DS 和 Azure AD) 中取得 **userPrincipalName** (很容易，將 **proxyAddresses** 中的主要電子郵件地址設定為不同的值。 當其設定為不同值時，系統管理員和使用者可能會混淆。

最好對齊這些屬性，以降低混淆。 為了符合使用 Active Directory Federation Services (AD FS) 2.0 的單一登入需求，您必須確定 Azure Active Directory 和您的 AD DS 中的 Upn 相符，且使用有效的網域命名空間。

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. 將替代的 UPN 尾碼新增至 AD DS

您可能需要新增其他 UPN 尾碼，以將使用者的公司認證與 Microsoft 365 環境產生關聯。 UPN 尾碼是 @ 字元右側的 UPN 部分。 用於單一登入的 UPN 可包含字母、數字、句號、虛線和底線，但不得包含其他字元類型。

如需如何將其他 UPN 尾碼新增至 Active Directory 的詳細資訊，請參閱 [Prepare for 目錄同步]( https://go.microsoft.com/fwlink/p/?LinkId=525430)處理。

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. 搭配使用 Microsoft 365 UPN 的 AD DS UPN

如果您已設定目錄同步處理，則 Microsoft 365 的使用者 UPN 可能不會符合您在 AD DS 中定義的使用者 AD DS UPN。 若使用者在網域經過驗證之前即獲得指派授權，就可能發生這種情形。 若要修正此問題，請使用 [PowerShell 修正重複的 upn](https://go.microsoft.com/fwlink/p/?LinkId=396730) 以更新使用者的 upn，以確保 MICROSOFT 365 UPN 符合公司使用者名稱和網域。 若要在 AD DS 中更新 UPN，並想要與 Azure Active Directory 身分識別同步，您必須先在 Microsoft 365 中移除使用者的授權，然後才能在 AD DS 中進行變更。

另請參閱 how [to prepare a 不可路由的網域 (例如，directory 同步處理的 local domain) ](prepare-a-non-routable-domain-for-directory-synchronization.md)。

## <a name="next-steps"></a>後續步驟

如果您已完成上述步驟1到5，請參閱 [設定目錄同步](set-up-directory-synchronization.md)處理。
