---
title: Office 365 郵件加密的舊版資訊
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何將舊版檔案轉換成 Office 365 (OME) 組織的郵件加密。
ms.openlocfilehash: eabf655b6fa92a6f502ebe1e071d41f394f78929
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051825"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Office 365 郵件加密的舊版資訊

如果您尚未將組織移至新的 OME 功能，但您已部署 OME，則本文中的資訊適用于您的組織。 Microsoft 建議您在組織合理的情況時，安排移至新的 OME 功能。 如需相關指示，請參閱 [設定以 Azure 資訊保護為基礎的新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。 如果您想要進一步瞭解新功能的運作方式，請參閱 [Office 365 Message Encryption](ome.md)。 本文的其餘部分是在發行新的 OME 功能之前，OME 行為。
  
透過 Office 365 郵件加密，您的組織可以在組織內部和外部的人員之間傳送和接收加密的電子郵件。 Office 365 郵件加密可與 Outlook.com、Yahoo、Gmail 及其他電子郵件服務搭配使用。 電子郵件加密可協助確保只有預定的收件者可以查看郵件內容。
  
以下為一些範例：
  
- 銀行員工將信用卡對帳單傳送給客戶

- 保險業公司代表為客戶提供原則詳細資料

- 抵押經紀人要求來自客戶的貸款申請財務資訊

- 保健服務提供者將健康情況護理資訊傳送給患者

- 律師將機密資訊傳送給客戶或其他律師

## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>如何在未使用新功能的情況下運作 Office 365 郵件加密

Office 365 郵件加密是一種線上服務，可在 Microsoft Azure Rights Management (Azure RMS) 上建立。 使用 Azure RMS 時，系統管理員可以定義郵件流程規則，以判斷加密的條件。 例如，規則可以要求所有寄給特定收件者的郵件加密。
  
當某人在 Exchange Online 中傳送符合加密規則的電子郵件時，郵件會以 HTML 附件傳送。 收件者會開啟 HTML 附件，並遵循指示，在 Office 365 郵件加密入口網站上查看加密郵件。 收件者可以選擇透過與 Office 365 相關聯的 Microsoft 帳戶或工作或學校登入，或是使用一次性的傳遞碼來查看郵件。 這兩個選項可協助確保只有預定的收件者可以查看加密的郵件。 此程式在新的 OME 功能上有很大的差異。
  
下圖摘要說明透過加密和解密過程的電子郵件訊息。
  
![顯示加密電子郵件路徑的圖表](../media/O365-Office365MessageEncryption-Concept.png)
  
如需詳細資訊，請參閱 [舊版 Office 365 郵件加密的服務資訊，然後再發行新的 OME 功能](legacy-information-for-message-encryption.md#LegacyServiceInfo)。
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>定義不使用新 OME 功能之 Office 365 郵件加密的郵件流程規則

若要在沒有新功能的情況下啟用 Office 365 郵件加密，Exchange Online 和 Exchange Online Protection 系統管理員會定義 Exchange 郵件流程規則。 這些規則會判斷應如何加密電子郵件，以及移除郵件加密的條件。 為規則設定加密動作時，服務會對符合規則條件的任何郵件執行動作，然後再傳送郵件。

郵件流程規則是彈性的，可讓您結合條件，讓您在單一規則中符合特定的安全性需求。 例如，您可以建立規則來加密所有包含指定關鍵字的郵件，並將其寄給外部收件者。 Office 365 郵件加密也會加密來自加密電子郵件收件者的回復，而且您可以建立規則來解密這些回復，以方便您的電子郵件使用者使用。 如此一來，您組織中的使用者不需要登入加密入口網站來查看回復。
  
如需如何建立 Exchange 郵件流程規則的相關資訊，請參閱 [Define rules For Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)。
  
### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>使用 EAC 來建立郵件流程規則，以加密不含新 OME 功能的電子郵件

1. 在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登 [入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 選擇 [ **管理** ] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [系統 **管理中心**] [ \> **Exchange**]。

4. 在 EAC 中，移至 [ **郵件流程** \> **規則** ]，然後選取 [ **新增** 新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。 如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](/exchange/exchange-admin-center)。

5. 在 [ **名稱**] 中，輸入規則的名稱，例如 [加密 DrToniRamos@hotmail.com 的郵件]。

6. 在 [套用 **此規則** ] 選取條件時，必要時輸入值。 例如，若要加密要 DrToniRamos@hotmail.com 的郵件：

   1. 在 [套用 **此規則 if**] 中，選取 **收件者為**。

   2. 從連絡人清單中選取現有名稱，或在 [ **檢查名稱** ] 方塊中輸入新的電子郵件地址。

      - 若要選取現有名稱，請從清單中進行選取，然後按一下 **[確定]**。

      - 若要輸入新名稱，請在 [ **檢查名稱** ] 方塊中輸入電子郵件地址，然後選取 [ **檢查名稱** \> **]**。

7. 若要新增更多條件，請選擇 [ **更多選項** ]，然後選取 [ **新增條件** ]，然後從清單中選取。

   例如，若要在組織外部的收件者之外套用規則，請選取 [**新增條件**]，然後選取收件者在組織外 **外部/內部的收件** 者 \>  \> ****。

8. 若要在不使用新 OME 功能的情況下啟用加密，請在 **執行下列** 動作中，選取 **[修改郵件安全性**] 套用 \> **舊版的 OME**，然後選擇 [ **儲存**]。

   如果您收到未啟用 IRM 授權的錯誤，則表示您不是使用舊版 OME。

9.  (選用) 選擇 [ **新增動作** ] 以指定另一個動作。

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>使用 Exchange Online PowerShell 建立郵件流程規則，以加密不含新 OME 功能的電子郵件

1. 連線至 Exchange Online PowerShell。 如需詳細資訊，請參閱＜[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)＞。

2. 使用 **New-TransportRule** Cmdlet 來建立規則，並將 _ApplyOME_ 參數設為 `$true` 。

   本範例要求所有傳送至 DrToniRamos@hotmail.com 的電子郵件都必須加密。

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   其中：

   - 新規則的唯一名稱是「Dr Toni Ramos 的加密規則」。
   - _SentTo_ 參數會指定收件者 (以名稱、電子郵件地址、辨識名稱等等所識別的收件者 ) 。 在此範例中，收件者會透過電子郵件地址 "DrToniRamos@hotmail.com" 加以識別。
   - _SentToScope_ 參數會指定郵件收件者的位置。 在此範例中，收件者的信箱是在 hotmail 中，而且不是組織的一部分，因此 `NotInOrganization` 會使用此值。

   如需詳細的語法和參數資訊，請參閱 [New-TransportRule](/powershell/module/exchange/New-TransportRule)。

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>從加密的電子郵件回復中移除加密，但不含新的 OME 功能

當您的電子郵件使用者傳送加密郵件時，這些郵件的收件者便可使用加密的回復來回應。 您可以建立郵件流程規則，以自動移除回復的加密，使組織中的電子郵件使用者不必登入加密入口網站以進行查看。 您可以使用 EAC 或 Windows PowerShell Cmdlet 來定義這些規則。 您可以解密組織內所傳送的郵件，或郵件回復從組織內傳送的郵件。 您無法解密來自組織外部的加密郵件。

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>使用 EAC 來建立刪除電子郵件回復加密的規則，而不使用新的 OME 功能

1. 在網頁瀏覽器中，使用已獲授與系統管理員許可權的公司或學校帳戶登 [入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 選擇 [ **管理** ] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [系統 **管理中心**] [ \> **Exchange**]。

4. 在 EAC 中，移至 [ **郵件流程** \> **規則** ]，然後選取 [ **新增** 新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。 如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](/exchange/exchange-admin-center)。

5. 在 [ **名稱**] 中，輸入規則的名稱，例如 [移除來自傳入郵件的加密]。

6. 在 [套用 **此規則** ] 中，選取應該從郵件中移除加密的情況，例如 **收件者位於** \> **組織內**。

7. 在 **執行下列** 動作中，選取 **[修改郵件安全性** \> **移除舊版 OME**]。

8. 選取 [儲存]。

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>使用 Exchange Online PowerShell 建立規則，以從加密的電子郵件回復中移除加密，但不使用新的 OME 功能

1. 連線至 Exchange Online PowerShell。 如需詳細資訊，請參閱＜[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)＞。

2. 使用 **New-TransportRule** Cmdlet 來建立規則，並將 _RemoveOME_ 參數設為 `$true` 。

   此範例會移除傳送給組織中收件者的所有郵件的加密。

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   其中：

   - 新規則的唯一名稱是「移除來自傳入郵件的加密」。
   - _SentToScope_ 參數會指定郵件收件者的位置。 在此範例中， `InOrganization` 會使用 value 值，這會指出下列其中一項：
     - 收件者是組織中的信箱、郵件使用者、群組或擁有郵件功能的公用資料夾。
     - 收件者的電子郵件地址位於已設定為授權網域或組織內部轉送網域的公認網域中， _且_ 透過已驗證的連線來傳送或接收郵件。

如需詳細的語法和參數資訊，請參閱 [New-TransportRule](/powershell/module/exchange/New-TransportRule)。

## <a name="sending-viewing-and-replying-to-messages-encrypted-without-the-new-capabilities"></a>傳送、查看和回復未用新功能加密的郵件

透過 Office 365 郵件加密，電子郵件訊息會根據系統管理員定義的規則自動加密。 帶有已加密郵件的電子郵件會以附加的 HTML 檔案送達收件者的收件匣。
  
收件者按郵件中的指示來開啟附件，並使用 Microsoft 帳戶或與 Office 365 關聯的工作或學校進行驗證。 如果收件者沒有任何帳戶，他們會被導向建立 Microsoft 帳戶，讓他們登入以查看加密郵件。 另外，收件者可以選擇取得一次的傳遞碼以查看郵件。 登入或使用一次性密碼後，收件者可以查看已解密的郵件，並傳送加密的回復。
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>使用 Office 365 郵件加密自訂加密郵件

做為 Exchange Online 和 Exchange Online Protection 管理員，您可以自訂加密的郵件。 例如，您可以新增公司的商標和標誌、指定簡介，以及在加密郵件中和在收件者查看加密郵件的入口網站中新增免責聲明文字。 您可以使用 Windows PowerShell 指令程式，自訂以下方面的加密電子郵件收件者視覺體驗：

- 包含加密訊息的電子郵件簡介文字

- 包含加密訊息的電子郵件免責聲明文字

- 將會出現在訊息檢視入口網站的入口網站文字

- 將會出現在電子郵件和檢視入口網站的標誌

您也可以隨時回復為預設的外觀與風格。
  
下列範例顯示 ContosoPharma 在電子郵件附件中的自訂標誌：

> [!div class="mx-imgBorder"]
> ![已加密郵件頁面的檢視範例](../media/TA-OME-3attachment2.jpg)
  
**自訂加密電子郵件和加密入口網站與貴組織的品牌**
  
1. 使用遠端 PowerShell 連接至 Exchange Online （如 [使用遠端 PowerShell 連線到 Exchange online](/powershell/exchange/connect-to-exchange-online-powershell)中所述）。

2. 依照如下所述使用 Set-OMEConfiguration Cmdlet： [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) 或使用下表取得指導方針。

   **加密自訂選項**

   | 若要自訂此加密經驗功能 | 請使用這些 Windows PowerShell 命令 |
   |:-----|:-----|
   |加密電子郵件隨附的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **範例：** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
   |包含加密訊息之電子郵件中的免責聲明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **範例：** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
   |出現在加密郵件檢視入口網站上方的文字  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **範例：** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
   |標誌  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **範例：** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支援的檔案格式：.png、.jpg、.bmp 或 .tiff  <br/> 標誌檔案的最佳大小：小於 40 KB  <br/> 標誌影像的最佳大小：170x70 像素  <br/> |

**從加密電子郵件和加密入口網站移除品牌自訂**
  
1. 使用遠端 PowerShell 連接至 Exchange Online （如 [使用遠端 PowerShell 連線到 Exchange online](/powershell/exchange/connect-to-exchange-online-powershell)中所述）。

2. 使用如下所述的 Set-OMEConfiguration Cmdlet： [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration)。 若要從 DisclaimerText、EmailText 及 PortalText 值中移除組織的署名自訂，請將值設為空字串  `""` 。 針對所有影像值，例如 [標誌]，將值設為  `"$null"` 。

   **加密自訂選項**

   | 將加密體驗的這項功能回復為預設文字和影像 | 請使用這些 Windows PowerShell 命令 |
   |:-----|:-----|
   |加密電子郵件隨附的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **範例：** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
   |包含加密訊息之電子郵件中的免責聲明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **範例：** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
   |出現在加密郵件檢視入口網站上方的文字  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **範例回復為預設值：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
   |標誌  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **範例回復為預設值：**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |

## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>發行新的 OME 功能之前，舊版 Office 365 郵件加密的服務資訊
<a name="LegacyServiceInfo"> </a>

下表提供 Office 365 Message Encryption service 在發行新 OME 功能之前的技術詳細資料。
  
| 服務詳細資料 | 描述 |
|:-----|:-----|
|用戶端裝置需求  <br/> |您可以在任何用戶端裝置上查看已加密的郵件，只要 HTML 附件可以在支援表單文章的新式瀏覽器中開啟。  <br/> |
| (FIPS) 相容性的加密演算法和聯邦資訊處理標準  <br/> |Office 365 郵件加密使用的加密金鑰與 Windows Azure Information Rights Management (IRM) ，且支援 SHA-1 系統) 的 RSA 和 256 bits 機碼的加密模式 2 (2K 金鑰。 如需基礎 IRM 加密模式的詳細資訊，請參閱 [AD RMS 密碼編譯模式](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))。  <br/> |
|支援的郵件類型  <br/> |只有具有「IPM」郵件類別識別碼的專案才支援 Office 365 郵件加密 **。附注**。 如需詳細資訊，請參閱 [專案類型和郵件類別](/office/vba/outlook/Concepts/Forms/item-types-and-message-classes)。  <br/> |
|郵件大小限制  <br/> |Office 365 郵件加密可將郵件加密為 25 mb。 如需郵件大小限制的詳細資訊，請參閱 [Exchange Online 限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)。  <br/> |
|Exchange Online 電子郵件保留原則  <br/> |Exchange Online 不會儲存加密的郵件。  <br/> |
|Office 365 郵件加密的語言支援  <br/> | Office 365 郵件加密支援 Microsoft 365 語言，如下所示：  <br/>  傳入的電子郵件和附加的 HTML 檔案會根據寄件者的語言設定進行當地語系化。  <br/>  根據收件者的瀏覽器設定來當地語系化查看入口網站。  <br/>  加密郵件的本文 (內容) 並未當地語系化。  <br/> |
|OME 入口網站和 OME Viewer 應用程式的隱私權資訊  <br/> |[Office 365 郵件加密入口網站隱私權聲明](https://privacy.microsoft.com/privacystatement)提供 Microsoft 對您私人資訊的處理方式及不會有什麼作用的詳細資訊。  <br/> |

## <a name="frequently-asked-questions-about-legacy-ome"></a>有關舊版 OME 的常見問題
<a name="LegacyServiceInfo"> </a>

有關于 Office 365 郵件加密的問題嗎？ 以下是一些解答。 如果您找不到所需的專案，請檢查 [Office 365 的 Microsoft 技術人員論壇](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365)。
  
 **問。我的使用者將加密的電子郵件傳送給我們組織之外的收件者。外部收件者是否必須這麼做才能閱讀和回復使用 Office 365 郵件加密所加密的電子郵件？**
  
組織外部收件者收到 Microsoft 365 加密郵件的收件者可以透過下列其中一種方式加以查看：
  
- 使用與 Office 365 相關聯的 Microsoft 帳戶或工作或學校帳戶登入。

- 使用一次性處理常式代碼。

 **問。是否有儲存在雲端或 Microsoft 伺服器上的 Microsoft 365 加密郵件？**
  
否，已加密的郵件會保留在收件者的電子郵件系統上，當收件者開啟郵件時，它會暫時張貼以供在 Microsoft 伺服器上查看。 郵件並不會儲存於該處。
  
 **問：我可以使用自己的品牌自訂加密電子郵件嗎？**
  
是。 您可以使用 Windows PowerShell Cmdlet 自訂加密電子郵件頂端顯示的預設文字、免責聲明文字，及要用於電子郵件和加密入口網站的標誌。 此功能現在可在 OMEv2 中使用。 如需詳細資訊，請參閱[Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md)。
  
 **問：我組織內每位使用者是否皆需備有服務授權？**
  
組織中傳送加密電子郵件的每位使用者皆需有授權。
  
 **問：外部收件者需要訂閱嗎？**
  
否，外部收件者不需要訂閱即可讀取或回覆加密郵件。
  
 **問。Office 365 郵件加密與 Rights Management Services (RMS) 有何不同？**
  
RMS 提供內建的範本，可提供組織內部電子郵件的資訊版權保護功能（例如：請勿轉寄及公司機密）。 Office 365 郵件加密支援傳送至外部收件者和內部收件者之郵件的電子郵件加密。
  
 **問。Office 365 郵件加密與 S/MIME 有何不同？**
  
S/MIME 基本上是一種用戶端加密技術，需要複雜的憑證管理與發佈基礎結構。 Office 365 郵件加密使用郵件流程 (規則（也稱為傳輸) 規則），而不是取決於憑證發行。
  
 **問：我可以透過行動裝置閱讀加密郵件嗎？**
  
是的，您可以透過從 Google Play 商店和 Apple 應用程式存放區下載 OME Viewer 應用程式來查看 Android 和 iOS 上的郵件。 在 OME 檢視器應用程式中開啟 HTML 附件，然後依照指示開啟加密的郵件。 對其他行動裝置而言，只要郵件用戶端支援表單張貼，您便能夠開啟 HTML 附件。
  
 **問：回覆和轉寄郵件皆會加密嗎？**
  
是的。在整個執行緒期間都會對回應持續加密。
  
 **問。Office 365 郵件加密是否提供當地語系化？**
  
內送電子郵件和 HTML 內容均依據寄件者電子郵件設定進行當地語系化。檢視入口網站會依據收件者的瀏覽器設定進行當地語系化。不過，加密郵件的實際內文 (內容) 不會進行當地語系化。
  
 **問。Office 365 郵件加密所使用的加密方法為何？**
  
Office 365 郵件加密使用 Rights Management Services (RMS) 作為其加密基礎結構。 使用的加密方法取決於您在哪裡取得用來加密及解密郵件的 RMS 金鑰。
  
- 如果您使用 Microsoft Azure RMS 取得機碼，則會使用加密模式2。 密碼編譯模式 2 是已更新並增強的 AD RMS 密碼編譯實作。 它支援使用 RSA 2048 進行簽章和加密，也支援使用 SHA-256 進行簽章。

- 如果您使用 Active Directory (AD) RMS 來取得金鑰，則會使用密碼編譯模式 1 或密碼編譯模式 2。使用的方法取決於內部部署 AD RMS 部署。密碼編譯模式 1 是原始的 AD RMS 密碼編譯實作。它支援使用 RSA 1024 進行簽章和加密，也支援使用 SHA-1 進行簽章。這個模式會繼續受到 RMS 所有目前的版本支援。

如需詳細資訊，請參閱 [AD RMS 密碼編譯模式](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))。
  
**Q。為何有些加密郵件會告訴他們來自** Office365@messaging.microsoft.com？
  
從加密入口網站或透過 OME 檢視器應用程式傳送加密的回覆時，傳送方的電子郵件地址會設為 Office365@messaging.microsoft.com，因為加密的郵件是透過 Microsoft 端點傳送。這有助於避免加密的郵件被標示為垃圾郵件。因為有此標示，加密入口網站中顯示的電子郵件名稱和地址不會變更。此外，此標示只會套用到透過入口網站傳送的郵件，而不會套用到透過任何其他電子郵件用戶端傳送的郵件。
  
 **問。我是 Exchange Hosted Encryption (EHE) 訂閱者。在哪裡可以深入瞭解 Office 365 郵件加密的升級？**
  
所有 EHE 客戶都已升級至 Office 365 郵件加密。 如需詳細資訊，請造訪 [Exchange Hosted Encryption Upgrade Center](../security/defender-365-security/exchange-online-protection-overview.md)。
  
 **問。我需要開啟組織防火牆中的任何 URLs、IP 位址或埠，以支援 Office 365 郵件加密？**
  
是。 您必須將 Exchange Online URLs 新增至您組織的允許清單，才能對 Office 365 郵件加密所加密的郵件啟用驗證。 如需 Exchange Online URLs 的清單，請參閱 [Microsoft 365 URLs 和 IP 位址範圍](../enterprise/urls-and-ip-address-ranges.md)。
  
 **問。我可以傳送 Microsoft 365 加密郵件的收件者人數為何？**
  
收件者限制是每封郵件500位收件者，或是在通訊群組清單展開後加上11980字元（以第一次 **為** 准）。
  
 **問：是否可以撤銷傳送給特定收件者的郵件？**
  
否。 郵件傳送後，您無法將郵件撤銷給特定的使用者。
  
 **問：是否可以檢視已接收和讀取的加密郵件的報表？**
  
不會顯示已查看加密郵件的報表，但有可用的 Microsoft 365 報告，您可以利用這些報告來判斷符合特定郵件流程規則的郵件數目 (也稱為傳輸規則) （例如）。
  
 **問：Microsoft 會如何利用透過 OME 入口網站和 OME 檢視器應用程式所取得我的資訊？**
  
[Office 365 郵件加密入口網站隱私權聲明](https://privacy.microsoft.com/privacystatement)提供 Microsoft 對您私人資訊的處理方式及不會有什麼作用的詳細資訊。

**問。我在要求它之後未收到一次性處理常式代碼時，該怎麼辦？**

首先，檢查您的電子郵件用戶端中的垃圾郵件或垃圾郵件資料夾。 您組織的 DKIM 和 DMARC 設定可能會導致這些電子郵件結束篩選為垃圾郵件。

接下來，檢查安全性 & 規範中心內的隔離。 通常會包含一次性處理常式代碼的郵件，尤其是您的組織收到的第一個郵件，但會以隔離區結束。