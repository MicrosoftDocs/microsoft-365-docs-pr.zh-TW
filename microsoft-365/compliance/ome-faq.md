---
title: 郵件加密常見問題
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: 有關新郵件保護功能的運作方式有疑問嗎？ 在這裡檢查答案。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1bb5e93b08b74f5691c76e9a59bf9fa970e08f36
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597193"
---
# <a name="message-encryption-faq"></a>郵件加密常見問題

有關新郵件保護功能的運作方式有疑問嗎？ 在這裡檢查答案。 此外，請參閱 [Azure 資訊保護中有關資料](https://docs.microsoft.com/information-protection/get-started/faqs-rms) 保護的常見問題解答，以取得 Azure 資訊保護中有關資料保護服務（Azure 版權管理）問題的答案。

## <a name="what-is-office-365-message-encryption-ome"></a>什麼是 Office 365 郵件加密 (OME) ？

OME 結合電子郵件加密和版權管理功能。 Rights management 功能由 Azure 資訊保護供電。

## <a name="who-can-use-ome"></a>誰可以使用 OME？

在下列情況下，您可以使用 OME 的新功能：
  
- 如果您從未在 Office 365 中設定 Exchange Online 的 OME 或 IRM。

- 如果您已設定 OME 和 IRM，則當您從 Azure 資訊保護使用 Azure Rights Management 服務時，您可以使用這些步驟。

- 如果您使用 Exchange Online 與 Active Directory Rights Management service (AD RMS) ，您就無法立即啟用這些新功能。 相反地，您必須先將 [AD RMS 遷移到 Azure 資訊保護](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) 。 當您完成遷移時，您可以成功設定 OME。

  如果您選擇繼續搭配使用內部部署 AD RMS 與 Exchange Online，而不是遷移至 Azure 資訊保護，您將無法使用這些新功能。

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>我需要哪些訂閱才能使用新的 OME 功能？

若要使用新的 OME 功能，您需要下列其中一個計畫：
  
- Office 365 郵件加密是以 Office 365 企業版 E3 和 E5 為一部分提供，Microsoft 企業版 E3 和 E5、Microsoft 365 商務版、Office 365 A1、A3 和 A5，以及 Office 365 政府 G3 和 G5。 客戶不需要其他授權，即可接收 Azure 資訊保護所支援的新保護功能。

- 您也可以將 Azure 資訊保護方案1新增至下列方案，以接收新的 Office 365 郵件加密功能： Exchange Online Plan 1、Exchange Online Plan 2、Office 365 F1、Microsoft 365 Business Basic、Microsoft 365 Business Standard 或 Office 365 Enterprise E1。

- 每個使用者從 Office 365 郵件加密中所受益的使用者，都必須經過授權才能享受功能。

- 如需完整清單，請參閱 Office 365 郵件加密的 [Exchange Online 服務說明](https://technet.microsoft.com/library/exchange-online-service-description.aspx) 。

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>我可以搭配使用 Exchange Online，在 Azure 資訊保護中引入您自己的金鑰 (BYOK) ？

可以！ Microsoft 建議您完成設定 BYOK 之前設定 OME 的步驟。
  
如需 BYOK 的詳細資訊，請參閱 [規劃及執行 Azure 資訊保護租使用者金鑰](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)。
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>使用 Azure 資訊保護執行 OME 和 BYOK 變更 Microsoft 對協力廠商資料要求的處理方式，例如 subpoenas？

否。 OME 和提供和控制您自己的加密金鑰（稱為 BYOK）的選項，Azure 資訊保護並非設計用來回應法律強制執行 subpoenas。 OME （搭配 BYOK for Azure 資訊保護）是專為以規範為重點的客戶而設計。 Microsoft 會非常認真地對客戶資料採取協力廠商要求。 作為雲端服務提供者，我們永遠提倡客戶資料的隱私權。 當我們取得傳票時，我們一定會嘗試將協力廠商重新導向至客戶以取得資訊。  (請閱讀 Brad Smith 的博客： [防止來自政府窺探) 的客戶資料](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) 。 我們會定期發佈我們所收到之要求的詳細資訊。 如需協力廠商資料要求的詳細資訊，請參閱 [回應政府和法律強制要求，以](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data) 在 Microsoft 信任中心存取客戶資料。 此外，請參閱 [線上服務條款 (OST) ](https://www.microsoft.com/Licensing/product-licensing/products.aspx)中的「客戶資料洩漏」。
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>如何與舊版 Office 365 郵件加密相關的此項功能 (OME) 和資訊版權管理 (IRM) 功能？

Office 365 郵件加密的新功能是現有 IRM 和舊版 OME 解決方案的演變。 下表提供更多詳細資料。
  
**傳統 OME、IRM 及新 OME 功能的比較**

| 功能 | 舊版本的 OME | IRM | 新的 OME 功能 |
|:-----|:-----|:-----|:-----|
|**傳送加密的電子郵件**|僅透過 Exchange 郵件流程規則|使用者從 Outlook for Windows、Outlook for Mac 或網頁型 Outlook 啟動;或透過 Exchange 郵件流程規則|使用者從 Outlook for Windows、Outlook for Mac 或網頁型 Outlook 啟動;或透過郵件流程規則|
|**版權管理**|-|[不要轉寄] 選項及自訂範本|[不要轉寄] 選項、[僅限加密] 選項、預設和自訂範本|
|**支援的收件者類型**|僅限外部收件者|僅限內部收件者|內部和外部收件者|
|**收件者的經驗**|外部收件者接收到的 HTML 郵件會在瀏覽器或下載的行動裝置應用程式中下載及開啟。|內部收件者只會接收 Outlook for Windows、Outlook for Mac 和網頁上的 outlook 中的加密電子郵件。|內部和外部收件者會在 Outlook for Windows、Mac 版 outlook、outlook on outlook、outlook （適用于 Android iOS）上，或透過網頁入口網站（不論其是否位於相同組織或任何組織中）來接收電子郵件。 OME 入口網站不需要個別下載。|
|**讓您擁有自己的主要支援**|無|無| 支援 BYOK|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>如何為組織啟用新的 OME 功能？

請參閱 [設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>舊版本的 OME 是否會被取代？

您仍然可以使用舊版的 OME，它現在不會被取代。 不過，我們強烈鼓勵組織使用新的和改良的 OME 解決方案。 尚未部署 OME 的客戶無法設定舊版本 OME 的新部署。
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>我的組織使用 Active Directory Rights Management，是否可以使用此功能？

否。 如果您使用 Exchange Online 與 Active Directory Rights Management service (AD RMS) ，您就無法立即啟用這些新功能。 相反地，您必須先將 [AD RMS 遷移到 Azure 資訊保護](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) 。
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>我的組織有 Exchange 混合式部署。 我可以使用此功能嗎？

內部部署使用者可以使用 Exchange Online 郵件流程規則傳送加密郵件。 為了達到此目的，您需要透過 Exchange Online 路由傳送電子郵件。 如需詳細資訊，請參閱 [第2部分：將郵件設定為從您的電子郵件伺服器流向 Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>我需要使用哪些電子郵件客戶程式才能建立 OME 加密郵件？ 傳送受保護的郵件支援哪些應用程式？

您可以從 Outlook 2016、Outlook 2013 for Windows 和 Mac，以及從網頁上的 Outlook 建立受保護的郵件。 如需傳送加密郵件的詳細資訊，請參閱 [在 Outlook 中傳送、查看和回復加密郵件的電腦](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-us&rs=en-us&ad=us)。
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>支援哪些電子郵件客戶程式來讀取及回復受保護的電子郵件？

Microsoft 365 使用者可以從 Outlook for Windows 和 Mac (2013 及 2016) 、網頁上的 Outlook，以及 Outlook mobile (Android 和 iOS) 閱讀和回應。 您也可以使用 iOS 原生郵件用戶端（如果您的組織允許的話）。 如果您不是 Microsoft 365 使用者，您可以透過網頁瀏覽器閱讀和回復網頁上的加密郵件。

## <a name="what-email-clients-support-the-encrypt-only-protected-emails"></a>哪些電子郵件客戶程式支援加密型的受保護電子郵件？

Microsoft 365 使用者可以使用 Outlook 版本2019和 Microsoft 365 的 Outlook，建立使用「僅限加密」原則保護的郵件。  這表示已套用新的「加密專用」原則的郵件，可以直接讀取于網頁型 outlook、在 Outlook 中 iOS 和 Android，而且現在是 Outlook 的電腦版本2019和 Microsoft 365。

## <a name="is-there-a-size-limit-for-messages-you-can-send-with-ome"></a>您可以使用 OME 來傳送的郵件是否有大小限制？

是。 您可以使用 OME 傳送的郵件大小上限（包括附件）為 25 MB。 如需詳細資訊，請參閱 [郵件限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits-1)。

## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>受保護電子郵件中的附件支援何種檔案類型？ 附件是否繼承與受保護的電子郵件相關聯的保護原則？

您可以將任何檔案類型附加到受保護的郵件。 只需一個例外狀況，保護原則只會套用至 [Azure 資訊保護用戶端支援的檔案類型](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)中所述的檔案格式。 OME 不支援下列 Office 程式的97-2003 版本： Word ( .doc) 、Excel ( .xls) 及 PowerPoint () 。

如果支援檔案格式（例如 Word、Excel 或 PowerPoint 檔案），檔案會永遠受到保護，即使收件者已下載附件也是一樣。 例如，假設附件的保護不是轉寄。 原始收件者會下載該檔案，並建立郵件給新的收件者，並附加該檔。 當新收件者收到檔案時，收件者將無法開啟受保護的檔案。
  
## <a name="are-pdf-file-attachments-supported"></a>是否支援 PDF 檔案附件？

這個簡短的答案是肯定！ PDF 加密可讓您透過安全通訊或安全共同作業來保護機密 PDF 檔。 當您傳送電子郵件時，Office 365 服務會加密 PDF 檔案附件而非 Outlook 用戶端。

針對網頁版 outlook、Outlook for iOS 和 Outlook for Android，您可以加密您傳送的 Pdf，而不需要任何其他步驟。 這些用戶端原本都支援 PDF 加密。

Outlook 桌面不會以本機方式支援 PDF 檔案附件的加密。 相反地，您必須設定 Exchange 郵件流程規則或 DLP，以先將加密套用至 PDF 附件。 當您使用 PDF 附件從 Outlook Desktop 傳送郵件時，用戶端會先將郵件與附件一起傳送給服務。 當服務接收到檔案時，服務會在 Exchange Online 中將 OME 保護的資料遺失防護 (DLP) 原則或郵件流程規則。 接下來，Exchange Online 會傳送包含受保護的 PDF 檔附件的郵件。

若要啟用 PDF 附件的加密，請在 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中執行下列命令：

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

PDF 加密可讓您透過安全通訊或安全共同作業來保護機密 PDF 檔。 針對所有 Outlook 用戶端，郵件和未受保護的 PDF 附件會繼承 OME 保護的資料遺失防護 (DLP) 原則或郵件流程規則在 Exchange Online 中。 此外，如果 web 使用者上的 Outlook 附加了未保護的 PDF 檔，並對郵件套用保護，郵件便會繼承郵件的保護。 使用者只能在支援受保護的 Pdf 的應用程式中開啟加密的附件 (例如，OME 入口網站和 Azure 資訊保護檢視器) 。

> [!IMPORTANT]
> Outlook 桌面用戶端不支援 PDF 加密。

## <a name="are-onedrive-for-business-attachments-supported"></a>是否 OneDrive 支援商務附件？

Not yet. 不支援商務附件的 OneDrive，使用者無法加密包含商務附件雲端 OneDrive 的郵件。
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>哪些電子郵件客戶程式支援在受保護的電子郵件中預覽加密附件？

當使用受保護的郵件保護附件時，Outlook 用戶端可讓您直接預覽檔的功能。 Outlook 支援預覽 Office 檔 (.docx、.xlsx、.pptx、doc、xls、ppt) 。 網頁上的 Outlook 支援 (.docx、.xlsx、.pptx) 和 PDF 的 Office 檔預覽。  

## <a name="what-email-clients-support-revocation-of-protected-emails"></a>哪些電子郵件客戶程式支援撤銷受保護的電子郵件？

網頁上的 Outlook 支援撤銷受保護的郵件。  請參閱 [如何撤銷您傳送的加密郵件](https://docs.microsoft.com/microsoft-365/compliance/revoke-ome-encrypted-mail?view=o365-worldwide#how-to-revoke-an-encrypted-message-that-you-sent) 以取得詳細資訊。


## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>我是否可以透過設定原則自動加密郵件？

是。 使用 Exchange Online 中的郵件流程規則，根據特定條件自動加密郵件。 例如，您可以建立以收件者識別碼、收件者網域或郵件內文或主旨的內容為基礎的原則。 請參閱 [定義郵件流程規則，以加密 Office 365 中的電子郵件](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>我可以自動移除傳入和傳出郵件的加密嗎？

系統管理員可以設定郵件流程規則，以移除外寄郵件的加密。 您無法設定規則來移除傳入郵件的加密。

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>是否可以透過安全性與合規性中心設定資料遺失防護 (DLP) 中的原則，自動加密郵件 &amp; ？

可以！ 您可以在 Exchange Online 中設定郵件流程規則，或在安全性與 &amp; 合規性中心使用 DLP。
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>我可以使用公司品牌來自訂加密郵件嗎？

可以！ 如需自訂電子郵件訊息與 OME 入口網站的詳細資訊，請參閱將組織的品牌新增至加密的郵件。 請參閱 [將貴組織的品牌新增至加密的郵件](add-your-organization-brand-to-encrypted-messages.md)。
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>是否有任何報告功能或加密電子郵件的洞察力？

在安全性與合規性中心有一個加密報告。 請參閱 [在安全性 & 規範中心中查看電子郵件安全性報告](../security/office-365-security/view-email-security-reports.md)。
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>是否可以使用郵件加密搭配電子檔探索等相容性功能？

是。 所有加密的電子郵件都可透過 Microsoft 365 符合性功能來發現。

## <a name="can-i-remove-encryption-from-email"></a>我可以從電子郵件移除加密嗎？

系統管理員可以設定郵件流程規則，以移除加密。 您無法從其他組織所套用的郵件中，使用郵件流程規則來移除加密，除非郵件是 enrypted 使用僅限加密的保護。

## <a name="is-delegated-access-supported"></a>是否支援委派存取？

不是在這個時候。

## <a name="can-i-send-as-a-shared-mailbox-and-encrypt-emails"></a>我可以傳送成共用信箱並加密電子郵件嗎？

當某人傳送符合加密郵件流程規則的電子郵件時，會先加密郵件，然後再傳送郵件。

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>我可以開啟已傳送至共用信箱的加密郵件嗎？

可以！ 共用信箱支援加密郵件。

- 使用者可以在共用信箱中，以通訊群組的一部分，在共用信箱中開啟受保護的郵件。

- 使用者可以在使用 Outlook for Windows、Mac 版 Outlook 和網頁版 Outlook 時，查看繼承電子郵件保護的附件。

下表列出共用信箱支援的用戶端。

| 平台 | 讀取郵件 | 查看電子郵件附件 |
|----------|-----------|------------------------|
| Outlook 網頁版 | 是 | 是                |
|  Outlook for Windows| 是 | 是                |
| Mac 版 Outlook    | 是 | 是                |
| Outlook for Android| 是 | 否                 |
| iOS 版 Outlook    | 是 | 否                 |
|

目前有兩個已知的限制：

- 您無法使用 Outlook mobile 開啟您在行動裝置上接收的電子郵件附件。

- 我們不支援使用啟用電子郵件功能的安全性群組的工作分派。 僅支援直接使用者指派至共用信箱的存取權，且自動對應已啟用 Exchange Online。 Exchange Online 預設會啟用自動對應。

**指派使用者至共用信箱**

1. [使用遠端 PowerShell 連接至 Exchange Online](https://technet.microsoft.com/library/jj984289?v=exchg.150%29.aspx)。

2. 使用自動對應參數執行 Add-MailboxPermission Cmdlet。 此範例會將 Ayla 的「完整存取」許可權授予支援信箱。

   ```powershell
   Add-MailboxPermission -Identity support@contoso.onmicrosoft.com -User ayla@contoso.com -AccessRights FullAccess -AutoMapping $true
   ```
   
 ## <a name="can-i-open-encrypted-messages-sent-to-another-users-mailbox-with-fullaccess"></a>我可以開啟使用 Fullaccess 傳送給另一個使用者信箱的加密郵件嗎？

使用者可以開啟加密的郵件，只要獲得直接存取和自動對應已開啟。 如果是透過已啟用電子郵件功能的安全性群組來授與存取權，則不允許存取。

## <a name="what-do-i-do-if-i-dont-receive-the-one-time-pass-code-after-i-requested-it"></a>我在要求它之後未收到一次性處理常式代碼時，該怎麼辦？

首先，檢查您的電子郵件用戶端中的垃圾郵件或垃圾郵件資料夾。 您組織的 DKIM 和 DMARC 設定可能會導致這些電子郵件結束篩選為垃圾郵件。

接下來，檢查安全性 & 規範中心內的隔離。 通常會包含一次性處理常式代碼的郵件，尤其是您的組織收到的第一個郵件，但會以隔離區結束。
