---
title: 設定您的 Microsoft 365 租使用者以提高安全性
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: 本主題將針對影響 Microsoft 365 環境安全性的全租使用者設定，引導您進行建議的設定。
ms.openlocfilehash: 3ef4fb00ca1e4a3e61cf0176308024b54baa287d
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399418"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>設定您的 Microsoft 365 租使用者以提高安全性

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


本主題將針對影響 Microsoft 365 環境安全性的全租使用者設定，引導您進行建議的設定。 您的安全性需求可能會高於或低於建議設定， 請使用這些建議做為調整的起始點。

## <a name="check-office-365-secure-score"></a>檢查 Office 365 安全分數

Office 365 安全分數會根據您的定期活動和安全性設定來分析貴組織的安全性，並指定分數。 請先記下您目前的分數。 調整某些全租用戶將能提高您的分數。 您的目標不是達到滿分，而是要留意能保護您的環境，又不會對使用者的生產力造成負面影響的機會。 請參閱 [Microsoft 安全分數](../mtp/microsoft-secure-score.md)。

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>調整 Microsoft 365 安全性中心的威脅管理原則

Microsoft 365 安全性中心包含的功能能夠保護您的環境。 同時，您也可以使用其中的報告和儀表板來進行監控並採取行動。 其中某些區域擁有預設的原則設定， 某些區域則不包含預設原則或規則。 請在威脅管理底下瀏覽以下原則，來調整威脅管理設定以營造更安全的環境。

****

|範圍|包含預設原則|建議|
|---|---|---|
|**防網路釣魚**|是|如果您有自訂網域，請設定預設的反網路釣魚原則，以保護您最有價值之使用者的電子郵件帳戶，例如 CEO，並保護您的網域。 [在 office 365 中查看反網路釣魚原則](set-up-anti-phishing-policies.md)，並參閱[設定 EOP 中的反網路釣魚原則](configure-anti-phishing-policies-eop.md)，或[設定 Office 365 中的 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。|
|**反惡意程式碼引擎**|是| 編輯預設原則： <br/> &ensp;&ensp;* 常見附件類型篩選—選取 [開啟] <br/><br/> 您也可以建立自訂的惡意程式碼篩選原則，並將其套用至貴組織中的指定使用者、群組或網域。 <br/><br/> 詳細資訊： <br/> &ensp;&ensp;* [反惡意程式碼保護](anti-malware-protection.md) <br/> &ensp;&ensp;* [設定反惡意程式碼原則](configure-anti-malware-policies.md)|
|**Office 365 ATP 安全附件**|否|在 [安全附件] 的主要頁面上，按一下 [ **通用設定** ]，然後開啟此設定： <br/> &ensp;&ensp;**為 SharePoint、OneDrive 和 Microsoft 團隊開啟 ATP** <br/><br/> 使用下列設定來建立安全附件原則： <br/> &ensp;&ensp;* **封鎖**：選取 [ **封鎖** ] 作為未知的惡意程式碼回應。 <br/> &ensp;&ensp;* **啟用重新導向**：請選取此方塊並輸入電子郵件地址，例如系統管理員或隔離帳戶。 <br/> &ensp;&ensp;* **若惡意程式碼掃描附件超時或發生錯誤，請套用上述選取範圍**：請選取此方塊。 <br/> &ensp;&ensp;* **適用**于： **收件者網域是** \> 選取您的網域。 <br/><br/> 詳細資訊： [SharePoint、OneDrive 和 Microsoft 小組的 ATP](atp-for-spo-odb-and-teams.md) ，以及 [設定安全附件原則](set-up-atp-safe-attachments-policies.md)|
|**Office 365 ATP 安全連結**|是|在 [安全連結] 的主要頁面上，按一下 [ **通用設定**]。 <br/> &ensp;&ensp;* **使用下列專案中的安全連結： Office 365 應用程式**：確認已開啟此設定。 <br/> &ensp;&ensp;* **當使用者按一下安全連結時，請勿追蹤**：關閉此設定以追蹤使用者按一下。<br/><br/>使用下列設定建立安全連結原則： <br/> &ensp;&ensp;* **在郵件中選取未知可能惡意 URLs 的動作**：確認此設定為 **開啟**。 <br/> &ensp;&ensp;* **選取 Microsoft 小組中未知或可能惡意的 URLs 的動作**：確認此設定已 **開啟**。 <br/> &ensp;&ensp;* **對指向檔案的可疑連結和連結套用即時 URL 掃描**：請選取此方塊。 <br/> &ensp;&ensp;&ensp;&ensp;* **等候 URL 掃描完成後，才能傳遞郵件**：請選取此方塊。 <br/> &ensp;&ensp;* 套用**安全連結至組織內傳送的電子郵件**：複選此方塊。 <br/> &ensp;&ensp;* **不允許使用者依序按一下原始 URL**：請選取此方塊。 <br/> &ensp;&ensp;* **適用**于： **收件者網域是** \> 選取您的網域。 <br/><br/> 詳細資訊： [設定安全連結原則](set-up-atp-safe-links-policies.md)。|
|**反垃圾郵件 (郵件篩選)**|是| 想要處理的情況： <br/> &ensp;&ensp;* 垃圾郵件太多-選擇 [自訂設定]，然後編輯預設垃圾郵件篩選原則。 <br/> &ensp;&ensp;* 欺騙性智慧-查看哄騙您網域的寄件者。 封鎖或允許這些寄件者。 <br/><br/>詳細資訊： [Microsoft 365 電子郵件 Anti-Spam 保護](anti-spam-protection.md)。|
|***電子郵件驗證***|是|電子郵件驗證使用網域名稱系統 (DNS) 將可驗證的資訊新增到某電子郵件寄件者的電子郵件。 Microsoft 365 會為其預設網域 (onmicrosoft.com) 設定電子郵件驗證，但 Microsoft 365 系統管理員也可以使用自訂網域的電子郵件驗證。 使用的三種驗證方法： <br/><br/> &ensp;&ensp;* 寄件者原則框架 (或 SPF) 。<br/>&ensp;&ensp;&ensp;&ensp;-如需安裝，請參閱 [在 Microsoft 365 中設定 SPF 以協助防止欺騙](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 <br/> &ensp;&ensp;* DomainKeys 識別的郵件 (DKIM) 。 <br/> &ensp;&ensp;&ensp;&ensp;-請參閱 [USE DKIM 以驗證從您的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。 <br/>&ensp;&ensp;&ensp;&ensp;- 設定完成 DKIM 後，請在安全性中心中啟用。<br/> &ensp;&ensp;* 以網域為基礎的郵件驗證、報告及符合性 (DMARC) 。 <br/> &ensp;&ensp;&ensp;&ensp;-適用于 DMARC 安裝程式 [使用 DMARC 驗證 Microsoft 365 中的電子郵件](use-dmarc-to-validate-email.md)。|
|

> [!NOTE]
> 在非標準部署的 SPF、混合式部署及疑難排解中： [Microsoft 365 如何使用寄件者原則框架 (SPF) 以避免欺騙](how-office-365-uses-spf-to-prevent-spoofing.md)。

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>請檢視安全性與合規性中心的儀表板和報告

請瀏覽以下報告與儀表板來深入了解您環境的健康狀況。 若您的組織使用 Office 365 服務，這些報告中的資料會變得更豐富。 現在，請先熟悉您可以監控與採取動作的項目。 如需詳細資訊，請參閱：[Microsoft 365 安全性與合規性中心的報告](../../compliance/reports-in-security-and-compliance.md)。

****

|儀表板|描述|
|---|---|
|[威脅管理儀表板](security-dashboard.md)|在安全性中心的 **[威脅管理]** 區段中，使用此儀表板來查看已經處理過的威脅，並將它視為一項實用工具，以此向商業決策者報告威脅調查和回應功能做了哪些舉動來保護貴企業。|
|[威脅總管 (或即時偵測)](threat-explorer.md)|此功能同樣位於安全性中心的 **[威脅管理]** 區段中。 如果您要調查或遭受對租使用者的攻擊，請使用 Explorer (或即時偵測) 來分析威脅。 總管 (或即時偵測) 能顯示隨時間受到的攻擊量，而您可以依照威脅系列、攻擊者的基礎結構等項目來分析這份資料。 您也可以將任何可疑的電子郵件標記為 [事件清單]。|
|報告 - 儀表板|在安全性中心的 **[報告]** 區段中，檢視您的 SharePoint Online 和 Exchange Online 組織的報告。 您也可以從 **[檢視報告]** 頁面存取 Azure Active Directory (Azure AD) 使用者登入報告、使用者活動報告和 Azure AD 稽核記錄。|
|

![安全性中心儀表板](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>設定其他 Exchange Online 全租用戶設定

Exchange 系統管理中心中有許多安全性與保護控制項同時也包含在安全性中心中。 您不需要在這兩個地方都進行設定。 以下是建議的設定。

****

|範圍|包含預設原則|建議|
|---|---|---|
|**郵件流程** (郵件流程規則，又稱為傳輸規則)|否|透過封鎖可執行檔案類型和包含宏的 Office 檔案類型，新增郵件流程規則，以協助抵禦勒索軟體。 如需詳細資訊，請參閱 [在 Exchange Online 中使用郵件流程規則檢查郵件附件](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)。 <br/><br/> 請參閱下列其他主題： <br/>* [防護勒索軟體](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)<br/>* [Office 365 中的惡意程式碼和勒索軟體防護](https://docs.microsoft.com/Office365/Enterprise/office-365-malware-and-ransomware-protection) <br/>* [從 Office 365 復原勒索軟體攻擊](recover-from-ransomware.md) <br/><br/> 建立郵件流程規則來防止郵件自動轉寄至外部網域。 如需詳細資訊，請參閱[含有安全分數的用戶端外部轉寄降低風險規則](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) (英文)。 <br/><br/> 其他資訊：[Exchange Online 中的郵件流程規則 (傳輸規則)](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**啟用新式驗證**|否|新式驗證是使用多重要素驗證 (MFA) 的必要條件。 MFA 是保護雲端資源存取權 (包括電子郵件) 的建議選項。 <br/><br/> 請參閱這些主題： <br/>* [啟用或停用 Exchange Online 中的新式驗證](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) <br/>* [商務用 Skype Online：針對新式驗證啟用租使用者](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) <br/><br/> Office 2016 用戶端、SharePoint Online 和商務用 OneDrive 預設會啟用新式驗證。 <br/><br/> 其他資訊：[Office 2013 和 Office 2016 用戶端應用程式的新式驗證運作方式](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>設定 SharePoint 系統管理中心的全租用戶共用原則

Microsoft 建議您從基礎保護開始，逐漸提高 SharePoint 小組網站的保護層級設定。 如需詳細資訊，請參閱[保護 SharePoint Online 網站與檔案](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files)

設定為基礎層級的 SharePoint 小組網站可讓您使用匿名存取連結，來與所有外部使用者共用檔案。 建議您採用此方法，而不要在電子郵件中傳送檔案。

為了支援基礎保護達到目標，請依以下建議設定全租用戶共用原則。 請為個別網站設定比此全租用戶原則更嚴格 (而非更寬鬆) 的共用設定。

****

|範圍|包含預設原則|建議|
|---|---|---|
|**共用** (SharePoint Online 和商務用 OneDrive)|是|外部共用預設為啟用狀態。 這些為建議設定： <br/>* 允許共用至已驗證的外部使用者，並使用匿名存取連結 (預設設定) 。 <br/> * 匿名存取連結會在數天后到期。 如有需要，請輸入一個數字，例如 30 天。 <br/>* 預設連結類型-選取 [只有) 組織中的內部 (人員]。 想要以匿名連結進行共用的使用者必須從共用功能表中選擇此選項。 <br/><br/> 其他資訊：[外部共用概觀](https://docs.microsoft.com/sharepoint/external-sharing-overview)|
|

SharePoint 系統管理中心與商務用 OneDrive 系統管理中心包含同樣的設定。 任一系統管理中心內的設定都適用於兩者。

## <a name="configure-settings-in-azure-active-directory"></a>在 Azure Active Directory 中進行設定

請務必在 Azure Active Directory 中瀏覽以下兩個區域以完成全租用戶設定，以獲得更安全的環境。

### <a name="configure-named-locations-under-conditional-access"></a>設定具名位置 (使用條件式存取)

如果貴組織內有辦公室擁有安全網路存取權，請將信任的 IP 位址範圍新增為 Azure Active Directory 中的具名位置。 這項功能可協助減少誤判為登入風險事件的次數。

請參閱：[Azure Active Directory 中的具名位置](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>封鎖不支援新式驗證的應用程式

應用程式必須支援新式驗證才能使用多重要素驗證。 您無法使用條件式存取規則來封鎖不支援新式驗證的 App。

為了環境安全，請務必停用不支援新式驗證之 App 的驗證。 您可以在 Azure Active Directory 中使用即將推出的控制項完成這項作業。

在此同時，請使用下列其中一項方法，來為 SharePoint Online 和商務用 OneDrive 完成這項作業：

- 使用 PowerShell，請參閱 [封鎖未使用新式驗證的應用程式 (ADAL) ](https://docs.microsoft.com/mem/intune/protect/app-modern-authentication-block)。

- 請在 SharePoint 系統管理中心內的 [裝置存取權] 頁面 - [控制不使用新式驗證的應用程式存取權] 進行此設定。 選擇 [封鎖]。

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>開始使用雲端 App 安全性或 Office 365 雲端 App 安全性

使用 Office 365 雲端 App 安全性來評估風險、警示可疑活動，並自動採取行動。 需要 Office 365 E5 方案。

或使用 Microsoft Cloud App Security，讓您即便在授與存取權後，也能讓所有雲端應用程式獲得更清楚的檢視、綜合性的控制權與更好的保護，包括 Office 365。

由於此解決方案建議使用 EMS E5 方案，我們建議您開始使用雲端 App 安全性，以便您可以搭配環境中的其他 SaaS 應用程式使用此功能。 請以預設原則與設定開始使用。

詳細資訊：

- [部署 Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [Microsoft Cloud App Security 的詳細資訊](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [什麼是 Cloud App Security？](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security 儀表板](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>其他資源

這些文章和指南提供加強 Microsoft 365 環境安全的其他規範性資訊：

- [適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南](https://docs.microsoft.com/microsoft-365/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o) (您可以在任何環境中使用這些建議，特別是僅使用雲端的環境)

- [適用於身分識別與裝置的建議安全原則與設定](microsoft-365-policies-configurations.md) (這些建議包括 AD FS 環境說明)
