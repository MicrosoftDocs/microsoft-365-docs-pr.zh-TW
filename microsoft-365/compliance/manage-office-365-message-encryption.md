---
title: 管理 Office 365 郵件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 當您完成設定 Office 365 郵件加密（OME）後，您可以採用多種方式自訂部署的設定。 例如，您可以設定是否要啟用一次性傳送碼，在 Outlook 網頁版中顯示 [保護] 按鈕，等等。 本文中的工作會說明如何進行這項作業。
ms.openlocfilehash: dd69266cccb1d04bc9ed3938b16bac45ca68b4a9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635883"
---
# <a name="manage-office-365-message-encryption"></a>管理 Office 365 郵件加密

當您完成設定 Office 365 郵件加密（OME）後，您可以採用多種方式自訂部署的設定。 例如，您可以設定是否要啟用一次性傳送碼，在 Outlook 網頁版中顯示 [**加密**] 按鈕，等等。 本文中的工作會說明如何進行這項作業。

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>管理 Google、Yahoo 和 Microsoft 帳戶收件者是否可以使用這些帳戶登入 Office 365 郵件加密入口網站

當您設定新的 Office 365 郵件加密功能時，您組織中的使用者可以傳送郵件給組織外部的收件者。 如果收件者使用的*社交識別碼*，例如 Google Account、Yahoo 帳戶或 Microsoft 帳戶，收件者便可使用社交識別碼登入 OME 入口網站。 如有需要，您可以選擇不允許收件者使用社交 IDs 登入 OME 入口網站。
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>管理收件者是否可以使用社交 IDs 登入 OME 入口網站
  
1. [使用遠端 PowerShell 連接至 Exchange Online](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。

2. 使用 SocialIdSignIn 參數執行 Set-OMEConfiguration Cmdlet，如下所示：

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   例如，若要停用社交 IDs：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   啟用社交 IDs：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>管理 Office 365 郵件加密入口網站的一次性傳送碼使用

如果由 OME 加密之郵件的收件者不會使用 Outlook，不論收件者使用的帳戶為何，收件者都會收到限制時間的 web view 連結，讓他們可以讀取郵件。 此連結包含一次的傳遞碼。 以系統管理員的身分，您可以決定收件者是否可以使用一次性傳送碼登入 OME 入口網站。
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>若要管理 OME 是否會產生一次的傳遞碼
  
1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，並啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 OTPEnabled 參數執行 Set-OMEConfiguration Cmdlet：

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   例如，若要停用一次性處理常式代碼：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   啟用一次性處理常式代碼：

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>管理網頁版 Outlook 中的 [加密] 按鈕的顯示

您可以以系統管理員的身分，管理是否要將此按鈕顯示給使用者。
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>若要管理 [加密] 按鈕是否顯示于網頁上的 Outlook
  
1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，並啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用-SimplifiedClientAccessEnabled 參數執行 Set-IRMConfiguration Cmdlet：

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   例如，若要停用 [**加密**] 按鈕：

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   啟用 [**加密**] 按鈕：

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>為 iOS 郵件 app 使用者啟用電子郵件的服務端解密

IOS 的郵件應用程式無法解密使用 Office 365 郵件加密保護的郵件。 做為 Microsoft 365 系統管理員，您可以對傳送至 iOS 郵件應用程式的郵件套用服務端解密。 當您選擇使用服務端解密時，服務會將郵件的解密複本傳送至 iOS 裝置。 用戶端裝置會儲存郵件的解密複本。 即使 iOS 的郵件應用程式不會對使用者套用用戶端使用許可權，郵件也會保留使用權利的相關資訊。 使用者可以複製或列印郵件，即使他們最初並未具有這麼做的權力。 不過，如果使用者嘗試完成需要 Microsoft 365 郵件伺服器的動作（例如轉寄郵件），如果使用者原來未使用此方法，則伺服器將不會允許執行該動作。 不過，使用者可以從 iOS 郵件應用程式內的不同帳戶轉送郵件，以解決「不要轉寄」使用限制。 不論您是否設定郵件的服務端解密，加密和受版權保護的郵件附件都無法在 iOS 郵件應用程式中查看。
  
如果您選擇 [不允許將解密的郵件傳送至 iOS 郵件 app 使用者]，使用者會收到訊息，指出他們沒有查看郵件的許可權。 根據預設，不會啟用電子郵件的服務端解密。
  
如需詳細資訊，以及用戶端經驗的觀點，請參閱[在 iPhone 或 iPad 上查看加密的郵件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)。
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>若要管理 iOS 郵件應用程式使用者是否可以查看 Office 365 郵件加密所保護的郵件
  
1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，並啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 AllowRMSSupportForUnenlightenedApps 參數執行 ActiveSyncOrganizations Cmdlet：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   例如，若要設定服務，在將郵件傳送至 unenlightened 應用程式（如 iOS 的郵件應用程式）之前，解密郵件：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   或者，若要設定服務不要將解密的郵件傳送至 unenlightened 應用程式：

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> 個別信箱原則（OWA/ActiveSync）覆寫這些設定（例如，IRMEnabled 如果在各自的 OWA 信箱原則中設定為 False，或 ActiveSync 信箱原則，則不會套用這些設定）。

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>啟用 web 瀏覽器郵件用戶端的電子郵件附件的服務端解密

在一般情況下，當您使用 Office 365 郵件加密時，會自動加密附件。 身為管理員，您可以對使用者從網頁瀏覽器下載的電子郵件附件套用服務端解密。
  
當您使用服務端解密時，服務會將檔的解密複本傳送至裝置。 郵件仍加密。 電子郵件附件也會保留使用權利的相關資訊，即使瀏覽器並未對使用者套用用戶端使用許可權。 使用者可以複製或列印電子郵件附件，即使他們最初並未具有這麼做的權力。 不過，如果使用者嘗試完成需要 Microsoft 365 郵件伺服器的動作（例如轉寄附件），如果使用者原來未使用此方法，則伺服器將不會允許執行該動作。
  
不論是否設定附件的服務端解密，使用者都無法在 iOS 郵件應用程式中查看加密和受版權保護之郵件的任何附件。
  
如果您選擇不允許解密的電子郵件附件，也就是預設值，使用者會收到訊息，指出他們沒有查看附件的許可權。
  
如需 Microsoft 365 如何使用僅限「加密」選項對電子郵件和電子郵件附件進行加密的詳細資訊，請參閱[電子郵件的唯讀選項。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>管理從網頁瀏覽器下載電子郵件附件是否解密
  
1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，並啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 DecryptAttachmentForEncryptOnly 參數執行 Set-IRMConfiguration Cmdlet：

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   例如，若要設定在使用者從網頁瀏覽器下載時，解密電子郵件附件的服務：

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   若要設定服務在下載時保留加密的電子郵件附件：

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>確定所有外部收件者都使用 OME 入口網站來讀取加密的郵件

您可以使用自訂品牌範本，強制收件者收到可在 OME 入口網站中讀取加密電子郵件的包裝郵件，而不是使用 Outlook 或 web 上的 Outlook。 如果您想要更進一步控制收件者如何使用其所收到的郵件，您可能想要這麼做。 例如，如果外部收件者查看網頁入口網站中的電子郵件，您可以設定電子郵件的到期日，也可以撤銷電子郵件。 只有透過 OME 入口網站支援這些功能。 您可以在建立郵件流程規則時，使用 [加密] 選項和 [不要轉寄] 選項。

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>使用自訂範本強制所有外部收件者都使用 OME 入口網站和加密的電子郵件

1. 使用組織中具有全域系統管理員許可權的工作或學校帳戶，並啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 執行 New-TransportRule Cmdlet：

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    其中：

   - `mail flow rule name`是您要用於新郵件流程規則的名稱。

   - `option name`可以`Encrypt`是或`Do Not Forward`。

   - `template name`是您為自訂商標範本所提供的名稱， `OME Configuration`例如。

   若要使用「「OME 設定」範本加密所有外部電子郵件，並套用 [僅限加密] 選項：

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   若要使用「「OME 設定」範本加密所有外部電子郵件，並套用 [不要轉寄] 選項：

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>自訂電子郵件和 OME 入口網站的外觀

如需如何為組織自訂 OME 的詳細資訊，請參閱[將組織的品牌新增至加密的郵件](add-your-organization-brand-to-encrypted-messages.md)。
  
## <a name="disable-the-new-capabilities-for-ome"></a>停用 OME 的新功能

建議您不要這樣做，但是如果您需要，停用 OME 的新功能會非常直接。 首先，您必須移除您已建立的任何郵件流程規則，以使用新的 OME 功能。 如需移除郵件流程規則的相關資訊，請參閱[管理郵件流程規則](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)。 然後，在 Exchange Online PowerShell 中完成這些步驟。
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>停用 OME 的新功能
  
1. 使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。 如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 如果您已在網頁上的 Outlook 中啟用 [**加密**] 按鈕，請使用 SimplifiedClientAccessEnabled 參數執行 Set-IRMConfiguration Cmdlet 以將其停用。 否則，請略過此步驟。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. 在 AzureRMSLicensingEnabled 參數設為 false 的情況執行 Set-IRMConfiguration Cmdlet，以停用 OME 的新功能：

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
