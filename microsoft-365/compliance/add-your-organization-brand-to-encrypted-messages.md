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
description: 做為 Office 365 全域系統管理員，您可以將組織的署名套用至組織的加密電子郵件和加密入口網站的內容。
ms.openlocfilehash: 5a3f5426fecd6ce5df6ace5b0080de33fb50e21f
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106015"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>將貴組織的品牌新增至您的加密郵件

做為 Exchange Online 或 Exchange Online Protection 管理員，您可以套用公司品牌，以自訂群組織的 Office 365 郵件加密電子郵件和加密入口網站內容的外觀。 您可以使用 Get-OMEConfiguration 和 Set-OMEConfiguration Windows PowerShell Cmdlet，針對加密的電子郵件訊息收件者，自訂下列各項流覽體驗：
  
- 包含加密訊息的電子郵件簡介文字

- 包含加密訊息的電子郵件免責聲明文字

- 您組織之隱私權聲明的 URL

- 出現在 OME 入口網站中的文字

- 出現在電子郵件和 OME 入口網站中的標誌，或是否要使用標誌

- 電子郵件訊息和 OME 入口網站中的背景色彩

您也可以隨時回復為預設的外觀與風格。

如果您想要控制，您可以使用 Office 365 高級郵件加密，並建立多個範本，以用於來自組織的加密電子郵件。 使用這些範本，您不僅可以控制電子郵件的外觀與風格，還可以控制使用者經驗的各個部分。 例如，您可以指定是否已套用此範本的郵件收件者，以及使用 Google、Yahoo 和 Microsoft 帳戶的收件者，都可以使用這些帳戶登入 Office 365 郵件加密入口網站。 您可以使用範本來滿足數個使用案例，例如：

- 每個部門的範本，例如財務、銷售等等。

- 不同產品的範本

- 不同地理區域或國家/地區的範本

- 您是否要允許吊銷電子郵件

- 您是否想要傳送給外部收件者的電子郵件在指定的天數後到期。

建立範本後，您可以使用 Exchange 郵件流程規則將其套用至加密的電子郵件。 如果您有 Office 365 Advanced Message Encryption，您可以使用這些範本撤銷所有已標記的電子郵件。

## <a name="work-with-ome-branding-templates"></a>使用 OME 品牌範本

您可以在品牌範本中修改數項功能。 您可以修改預設範本，但不要移除。 如果您有高級郵件加密，您也可以建立、修改及移除自訂範本。 使用 Windows PowerShell 一次可搭配一個署名範本。 您需要具備 Office 365 組織中全域系統管理員許可權的工作或學校帳戶，才可使用這些 Cmdlet。

- [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-omeconfiguration) -修改預設的署名範本或您建立的自訂商標範本。
- [Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) -建立新的署名範本，僅限高級郵件加密。
- [Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/remove-omeconfiguration) -移除自訂品牌範本，僅限高級郵件加密。 您無法刪除預設的署名範本。
  
## <a name="modify-an-ome-branding-template"></a>修改 OME 署名範本

使用 Windows PowerShell 一次修改一個署名範本。 如果您有高級郵件加密，您也可以建立、修改及移除自訂範本。

1. 在您的 Office 365 組織中使用具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述的 Set-OMEConfiguration 指令程式修改範本，或使用下列圖形和表格以取得指導方針。

![可自訂的電子郵件元件](../media/ome-template-breakout.png)

|**若要自訂此加密經驗功能**|**使用這些命令**|
|:-----|:-----|
|背景色彩|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|標誌|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支援的檔案格式：.png、.jpg、.bmp 或 .tiff  <br/> 標誌檔案的最佳大小：小於 40 KB  <br/> 標誌影像的最佳大小：170x70 圖元。 如果您的影像超過這些尺寸，服務會重新調整您的徽標以在入口網站中顯示。 服務不會修改圖形檔案本身。 為了獲得最佳結果，請使用最佳大小。|
|寄件者名稱和電子郵件地址旁的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|出現在「讀取訊息」按鈕上的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|出現在 [閱讀郵件] 按鈕下方的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|隱私權聲明連結的 URL|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PrivacyStatementURL "<URL>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|包含加密訊息之電子郵件中的免責聲明|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|出現在加密郵件檢視入口網站上方的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|啟用或停用此自訂範本的一次性程式碼驗證|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **範例：** <br/>針對此自訂範本啟用一次 passcodes <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> 針對此自訂範本停用一次 passcodes <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|啟用或停用此自訂範本的 Microsoft、Google 或 Yahoo 識別碼驗證|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **範例：** <br/>啟用此自訂範本的社交 IDs <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> 停用此自訂範本的社交 IDs <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>建立 OME 署名範本（高級郵件加密）

如果您有 Office 365 Advanced Message Encryption，您可以使用[set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) Cmdlet 為您的組織建立自訂商標範本。 建立範本之後，您可以使用 Set-OMEConfiguration Cmdlet 修改範本，如[modify a OME 署名範本](#modify-an-ome-branding-template)所述。 您可以建立多個範本。

若要建立新的自訂品牌範本：

1. 在您的 Office 365 組織中使用具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用[set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/new-omeconfiguration) Cmdlet 來建立新的範本。

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   For example,

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>將預設署名範本傳回其原始值

若要從預設範本移除所有修改（包括品牌自訂專案）等等，請完成下列步驟：
  
1. 在您的 Office 365 組織中使用具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述的**Set-OMEConfiguration** Cmdlet。 若要從 DisclaimerText、EmailText 及 PortalText 值中移除組織的署名自訂，請將值設為空字串`""`。 針對所有影像值，例如 [標誌]，將值設`"$null"`為。

   下表說明加密自訂選項的預設值。

   **將加密體驗的這項功能回復為預設文字和影像**|**使用這些命令**|
   |:-----|:-----|
   |加密電子郵件隨附的預設文字  <br/> 預設文字會出現在檢視加密郵件的指示上方。|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |包含加密訊息之電子郵件中的免責聲明|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **範例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |出現在加密郵件檢視入口網站上方的文字|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **範例回復為預設值：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |標誌|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **範例回復為預設值：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |背景色彩|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **範例回復為預設值：** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>移除自訂商標範本（高級郵件加密）

您只可以移除或刪除您所做的品牌範本。 您無法移除預設的署名範本。

若要移除自訂商標範本：
  
1. 在您的 Office 365 組織中使用具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用**Remove-set-omeconfiguration 指令程式**，如下所示：

   ```powershell
   Remove-OMEConfiguration -Identity "<OMEConfigurationIdParameter>
   ```

   For example,

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   如需詳細資訊，請參閱[Remove-set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/remove-omeconfiguration)。

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>建立將自訂品牌套用至加密電子郵件的 Exchange 郵件流程規則

修改預設範本或建立新的品牌範本之後，您可以建立 Exchange 郵件流程規則，以根據特定條件套用您的自訂品牌。 這類規則會在下列情況中套用自訂品牌：

- 如果最終使用者從 Outlook 或網頁版 outlook （先前稱為 Outlook Web App）用戶端手動加密電子郵件

- 如果電子郵件已由 Exchange 郵件流程規則或 Office 365 資料遺失防護原則自動加密

如需如何建立可套用加密之 Exchange 郵件流程規則的詳細資訊，請參閱[定義郵件流程規則，以在 Office 365 中加密電子郵件訊息](define-mail-flow-rules-to-encrypt-email.md)。

1. 在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 選擇 [**管理**] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [系統**管理中心** \> ] [ **Exchange**]。

4. 在 EAC 中，移至 [**郵件流程** \> **規則**]，然後選取](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> [**新增** ![新圖示] 以**建立新的規則**。 如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 [**名稱**] 中，輸入規則的名稱，例如「銷售部門的商標」。

6. 在 [套用**此規則**條件] 中，選取**寄件者位於組織內部**的條件，以及您在可用條件清單中所需的其他條件。 例如，您可能想要將特定的署名範本套用到：

   - 從財務部門的成員傳送的所有加密電子郵件
   - 以特定關鍵字（如 "External" 或 "Partner"）傳送的加密電子郵件
   - 傳送至特定網域的加密電子郵件

7. 從**執行下列**動作，選取 **[修改郵件安全性** > 套用**自訂品牌] 以 OME 郵件**。 接下來，從下拉式清單中，選取您建立或修改的品牌範本。

8. 選如果您除了自訂商標之外，您也想要將郵件流程規則套用加密，請選取 **[****修改郵件安全性**]，然後選擇 [套用**Office 365 郵件加密和許可權保護**]。 從清單中選取 RMS 範本，然後選擇 [**儲存**]，然後選擇 **[確定]**。
  
   範本清單包括所有預設範本和選項，以及您已建立供 Office 365 使用的任何自訂範本。 如果清單是空的，請確定您已使用[設定新的 office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)中所述的新功能，來設定 Office 365 郵件加密。 如需預設範本的相關資訊，請參閱設定[及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。 如需有關 [**不要轉寄**] 選項的詳細資訊，請參閱[請勿轉寄選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 如需只供**加密**之選項的詳細資訊，請參閱[僅限加密選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   如果您想要指定另一個動作，請選擇 [**新增動作**]。
