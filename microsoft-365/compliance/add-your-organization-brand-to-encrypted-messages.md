---
title: 將您的組織品牌新增至加密郵件
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 瞭解 Office 365 全域管理員如何將組織的署名套用至加密的電子郵件，& 加密入口網站的內容。
ms.openlocfilehash: 77fd5e08afa1a4d8ae5f6386fa65b88b6ea2be4d
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663230"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>將貴組織的品牌新增至 Microsoft 365，以進行商務郵件加密加密郵件

您可以套用公司品牌，以自訂群組織的電子郵件訊息和加密入口網站的外觀。 您必須先對您的公司或學校帳戶套用全域系統管理員許可權，才可開始使用。 一旦您具有這些許可權，請使用 Get-OMEConfiguration 和 Set-OMEConfiguration Windows PowerShell Cmdlet 來自訂這些加密電子郵件的這些部分：
  
- 簡介文字

- 免責聲明文字

- 組織之隱私權聲明的 URL

- OME 入口網站中的文字

- 出現在電子郵件和 OME 入口網站中的標誌，或是否要使用標誌

- 電子郵件訊息和 OME 入口網站中的背景色彩

您也可以隨時回復為預設的外觀與風格。

如果您想要更多控制，請使用 Office 365 Advanced Message Encryption，針對來自組織的加密電子郵件建立多個範本。 使用這些範本來控制使用者經驗的各個部分。 例如，指定收件者是否可以使用 Google、Yahoo 和 Microsoft 帳戶登入加密入口網站。 使用範本來滿足數個使用案例，例如：

- 個別部門，例如財務、銷售等等。

- 不同的產品

- 不同的地理區域或國家

- 您是否要允許吊銷電子郵件

- 您是否想要傳送給外部收件者的電子郵件在指定的天數後到期。

建立範本後，您可以使用 Exchange 郵件流程規則將其套用至加密的電子郵件。 如果您有 Office 365 Advanced Message Encryption，您可以使用這些範本撤銷所有已標記的電子郵件。

## <a name="work-with-ome-branding-templates"></a>使用 OME 品牌範本

您可以在品牌範本中修改數項功能。 您可以修改預設範本，但不要移除。 如果您有高級郵件加密，您也可以建立、修改及移除自訂範本。 使用 Windows PowerShell 一次可搭配一個署名範本。

- [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) -修改預設的署名範本或您建立的自訂商標範本。
- [Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) -建立新的署名範本，僅限高級郵件加密。
- [Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) -移除自訂品牌範本，僅限高級郵件加密。 您無法刪除預設的署名範本。
  
## <a name="modify-an-ome-branding-template"></a>修改 OME 署名範本

使用 Windows PowerShell 一次修改一個署名範本。 如果您有高級郵件加密，您也可以建立、修改及移除自訂範本。

1. 使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) 所述的 Set-OMEConfiguration 指令程式，或使用下圖及表格以取得指導方針。

![可自訂的電子郵件元件](../media/ome-template-breakout.png)

|**若要自訂此加密經驗功能**|**使用這些命令**|
|:-----|:-----|
|背景色彩|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> 如需背景色彩的詳細資訊，請參閱本文稍後的 [ [背景色彩](#background-color-reference) ] 區段。|
|標誌|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支援的檔案格式：.png、.jpg、.bmp 或 .tiff  <br/> 標誌檔案的最佳大小：小於 40 KB  <br/> 標誌影像的最佳大小：170x70 圖元。 如果您的影像超過這些尺寸，服務會重新調整您的徽標以在入口網站中顯示。 服務不會修改圖形檔案本身。 為了獲得最佳結果，請使用最佳大小。|
|寄件者名稱和電子郵件地址旁的文字|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|出現在「讀取訊息」按鈕上的文字|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|出現在 [閱讀郵件] 按鈕下方的文字|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|隱私權聲明連結的 URL|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|包含加密訊息之電子郵件中的免責聲明|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|出現在加密郵件檢視入口網站上方的文字|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|啟用或停用此自訂範本的一次性程式碼驗證|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **範例：** <br/>針對此自訂範本啟用一次 passcodes <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> 針對此自訂範本停用一次 passcodes <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|啟用或停用此自訂範本的 Microsoft、Google 或 Yahoo 識別碼驗證|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **範例：** <br/>啟用此自訂範本的社交 IDs <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> 停用此自訂範本的社交 IDs <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a> (高級郵件加密建立 OME 署名範本) 

如果您有 Office 365 Advanced Message Encryption，您可以使用 [set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) Cmdlet 為您的組織建立自訂商標範本。 建立範本之後，您可以使用 Set-OMEConfiguration Cmdlet 修改範本，如 [modify a OME 署名範本](#modify-an-ome-branding-template)所述。 您可以建立多個範本。

若要建立新的自訂品牌範本：

1. 使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 [set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) Cmdlet 來建立新的範本。

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   例如：

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>將預設署名範本傳回其原始值

若要從預設範本移除所有修改（包括品牌自訂專案）等等，請完成下列步驟：
  
1. 使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration)中所述的 **Set-OMEConfiguration** Cmdlet。 若要從 DisclaimerText、EmailText 及 PortalText 值中移除組織的署名自訂，請將值設為空字串 `""` 。 針對所有影像值，例如 [標誌]，將值設為  `"$null"` 。

   下表說明加密自訂選項的預設值。

   **將加密體驗的這項功能回復為預設文字和影像**|**使用這些命令**|
   |:-----|:-----|
   |附帶加密電子郵件的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |包含加密訊息之電子郵件中的免責聲明|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |出現在加密郵件檢視入口網站上方的文字|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **範例回復為預設值：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |標誌|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **範例回復為預設值：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |背景色彩|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **範例回復為預設值：** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a> (高級郵件加密移除自訂商標範本) 

您只可以移除或刪除您所做的品牌範本。 您無法移除預設的署名範本。

若要移除自訂商標範本：
  
1. 使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 **Remove-set-omeconfiguration 指令程式** ，如下所示：

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   例如：

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   如需詳細資訊，請參閱 [Remove-set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration)。

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>建立將自訂品牌套用至加密電子郵件的 Exchange 郵件流程規則

修改預設範本或建立新的品牌範本之後，您可以建立 Exchange 郵件流程規則，以根據特定條件套用您的自訂品牌。 這類規則會在下列情況中套用自訂品牌：

- 如果使用者使用 Outlook 或網頁上的 outlook 來手動加密電子郵件，則為 Outlook Web App

- 如果電子郵件已由 Exchange 郵件流程規則或資料遺失防護原則自動加密

如需如何建立可套用加密之 Exchange 郵件流程規則的詳細資訊，請參閱 [定義郵件流程規則，以在 Office 365 中加密電子郵件訊息](define-mail-flow-rules-to-encrypt-email.md)。

1. 在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登 [入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 選擇 [ **管理** ] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [系統 **管理中心**] [ \> **Exchange**]。

4. 在 EAC 中，移至 [ **郵件流程** \> **規則** ]，然後選取 [ **新增** 新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。 如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 [ **名稱**] 中，輸入規則的名稱，例如「銷售部門的商標」。

6. 在 [套用 **此規則** 條件] 中，選取 **寄件者位於組織內部的** 條件，以及您在可用條件清單中所需的其他條件。 例如，您可能想要將特定的署名範本套用到：

   - 從財務部門的成員傳送的所有加密電子郵件
   - 以特定關鍵字（如 "External" 或 "Partner"）傳送的加密電子郵件
   - 傳送至特定網域的加密電子郵件

7. 從 **執行下列** 動作，選取 **[修改郵件安全性** 套用 \> **自訂品牌] 以 OME 郵件**。 接下來，從下拉式清單中選取商標範本。

8.  (選用) 您可以設定郵件流程規則套用加密和自訂商標。 從 **執行下列** 動作，選取 **[修改郵件安全性**]，然後選擇 [套用 **Office 365 郵件加密和許可權保護**]。 從清單中選取 RMS 範本，然後選擇 [ **儲存**]，然後選擇 **[確定]**。
  
   範本清單包含預設範本和選項，以及您建立的任何自訂範本。 如果清單是空的，請確定您已使用新功能設定 Office 365 郵件加密。 如需相關指示，請參閱 [Set up New Office 365 Message Encryption 功能](set-up-new-message-encryption-capabilities.md)。 如需預設範本的相關資訊，請參閱設定 [及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。 如需有關 [ **不要轉寄** ] 選項的詳細資訊，請參閱 [請勿轉寄選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 如需只供 **加密** 之選項的詳細資訊，請參閱 [僅限加密選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   如果您想要指定另一個動作，請選擇 [ **新增動作** ]。

## <a name="background-color-reference"></a>背景色彩參考

您可以用於背景色彩的色彩名稱是有限的。 您可以使用十六進位代碼值 ( # RRGGBB 格式) 來代替色彩名稱。 您可以使用對應于色彩名稱的十六進位代碼值，也可以使用自訂的十六進位代碼值。 請務必以引號括住十六進位代碼值 (例如， `"#f0f8ff"`) 。

下表說明可用的背景色彩名稱及其對應的十六進位代碼值。

|||
|---|---|
|**色彩名稱**|**色彩代碼**|
|`aliceblue`|#f0f8ff|
|`antiquewhite`|#faebd7|
|`aqua`|#00ffff|
|`aquamarine`|#7fffd4|
|`azure`|#f0ffff|
|`beige`|#f5f5dc|
|`bisque`|#ffe4c4|
|`black`|#000000|
|`blanchedalmond`|#ffebcd|
|`blue`|#0000ff|
|`blueviolet`|#8a2be2|
|`brown`|#a52a2a|
|`burlywood`|#deb887|
|`cadetblue`|#5f9ea0|
|`chartreuse`|#7fff00|
|`chocolate`|#d2691e|
|`coral`|#ff7f50|
|`cornflowerblue`|#6495ed|
|`cornsilk`|#fff8dc|
|`crimson`|#dc143c|
|`cyan`|#00ffff|
|`darkblue`|#00008b|
|`darkcyan`|#008b8b|
|`darkgoldenrod`|#b8860b|
|`darkgray`|#a9a9a9|
|`darkgreen`|#006400|
|`darkkhaki`|#bdb76b|
|`darkmagenta`|#8b008b|
|`darkolivegreen`|#556b2f|
|`darkorange`|#ff8c00|
|`darkorchid`|#9932cc|
|`darkred`|#8b0000|
|`darksalmon`|#e9967a|
|`darkseagreen`|#8fbc8f|
|`darkslateblue`|#483d8b|
|`darkslategray`|#2f4f4f|
|`darkturquoise`|#00ced1|
|`darkviolet`|#9400d3|
|`deeppink`|#ff1493|
|`deepskyblue`|#00bfff|
|`dimgray`|#696969|
|`dodgerblue`|#1e90ff|
|`firebrick`|#b22222|
|`floralwhite`|#fffaf0|
|`forestgreen`|#228b22|
|`fuchsia`|#ff00ff|
|`gainsboro`|#dcdcdc|
|`ghostwhite`|#f8f8ff|
|`gold`|#ffd700|
|`goldenrod`|#daa520|
|`gray`|#808080|
|`green`|#008000|
|`greenyellow`|#adff2f|
|`honeydew`|#f0fff0|
|`hotpink`|#ff69b4|
|`indianred`|#cd5c5c|
|`indigo`|#4b0082|
|`ivory`|#fffff0|
|`khaki`|#f0e68c|
|`lavender`|#e6e6fa|
|`lavenderblush`|#fff0f5|
|`lawngreen`|#7cfc00|
|`lemonchiffon`|#fffacd|
|`lightblue`|#add8e6|
|`lightcoral`|#f08080|
|`lightcyan`|#e0ffff|
|`lightgoldenrodyellow`|#fafad2|
|`lightgray`|#d3d3d3|
|`lightgrey`|#d3d3d3|
|`lightgreen`|#90ee90|
|`lightpink`|#ffb6c1|
|`lightsalmon`|#ffa07a|
|`lightseagreen`|#20b2aa|
|`lightskyblue`|#87cefa|
|`lightslategray`|#778899|
|`lightsteelblue`|#b0c4de|
|`lightyellow`|#ffffe0|
|`lime`|#00ff00|
|`limegreen`|#32cd32|
|`linen`|#faf0e6|
|`magenta`|#ff00ff|
|`maroon`|#800000|
|`mediumaquamarine`|#66cdaa|
|`mediumblue`|#0000cd|
|`mediumorchid`|#ba55d3|
|`mediumpurple`|#9370db|
|`mediumseagreen`|#3cb371|
|`mediumslateblue`|#7b68ee|
|`mediumspringgreen`|#00fa9a|
|`mediumturquoise`|#48d1cc|
|`mediumvioletred`|#c71585|
|`midnightblue`|#191970|
|`mintcream`|#f5fffa|
|`mistyrose`|#ffe4e1|
|`moccasin`|#ffe4b5|
|`navajowhite`|#ffdead|
|`navy`|#000080|
|`oldlace`|#fdf5e6|
|`olive`|#808000|
|`olivedrab`|#6b8e23|
|`orange`|#ffa500|
|`orangered`|#ff4500|
|`orchid`|#da70d6|
|`palegoldenrod`|#eee8aa|
|`palegreen`|#98fb98|
|`paleturquoise`|#afeeee|
|`palevioletred`|#db7093|
|`papayawhip`|#ffefd5|
|`peachpuff`|#ffdab9|
|`peru`|#cd853f|
|`pink`|#ffc0cb|
|`plum`|#dda0dd|
|`powderblue`|#b0e0e6|
|`purple`|#800080|
|`red`|#ff0000|
|`rosybrown`|#bc8f8f|
|`royalblue`|#4169e1|
|`saddlebrown`|#8b4513|
|`salmon`|#fa8072|
|`sandybrown`|#f4a460|
|`seagreen`|#00ff00|
|`seashell`|#fff5ee|
|`sienna`|#a0522d|
|`silver`|#c0c0c0|
|`skyblue`|#87ceeb|
|`slateblue`|#6a5acd|
|`slategray`|#708090|
|`snow`|#fffafa|
|`springgreen`|#00ff7f|
|`steelblue`|#4682b4|
|`tan`|#d2b48c|
|`teal`|#008080|
|`thistle`|#d8bfd8|
|`tomato`|#ff6347|
|`turquoise`|#40e0d0|
|`violet`|#ee82ee|
|`wheat`|#f5deb3|
|`white`|#ffffff|
|`whitesmoke`|#f5f5f5|
|`yellow`|#ffff00|
|`yellowgreen`|#9acd32|
