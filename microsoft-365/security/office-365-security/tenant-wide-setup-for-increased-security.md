---
title: 設定 Microsoft 365 租用戶以提高安全性
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: 本主題將引導您瞭解會影響 Microsoft 365 環境安全性的全租使用者設定的建議配置。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b1bb3f9bf6507e41d8b927137a9ab9ea8803637c
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105521"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>設定 Microsoft 365 租用戶以提高安全性

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

本主題將引導您瞭解會影響 Microsoft 365 環境安全性的全租使用者設定的建議配置。 您的安全性需求可能會高於或低於建議設定， 請使用這些建議做為調整的起始點。

## <a name="check-office-365-secure-score"></a>檢查 Office 365 安全分數

Office 365安全分數會根據您的定期活動和安全性設定來分析貴組織的安全性，並指定分數。 請先記下您目前的分數。 調整某些全租用戶將能提高您的分數。 您的目標不是達到滿分，而是要留意能保護您的環境，又不會對使用者的生產力造成負面影響的機會。 請參閱 [Microsoft 安全分數](../defender/microsoft-secure-score.md)。

## <a name="tune-threat-management-policies-in-the-microsoft-365-defender-portal"></a>調整 Microsoft 365 Defender 入口網站中的威脅管理原則

Microsoft 365 Defender 入口網站包含保護您環境的功能。 同時，您也可以使用其中的報告和儀表板來進行監控並採取行動。 其中某些區域擁有預設的原則設定， 某些區域則不包含預設原則或規則。 在 **電子郵件 &** 共同作業 \> **原則 & 規則** \> **威脅原則** ，以調整更安全的環境的威脅管理設定，請造訪下列原則。

<br>

****

|區域|預設原則？|建議|
|---|---|---|
|**防網路釣魚**|是|設定預設的反網路釣魚原則，如下所述：[在 EOP 中設定反網路釣魚防護設定和 Office 365 的 Defender](protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365)。 <p> 詳細資訊： <ul><li>[Microsoft 365 中的反網路釣魚原則](set-up-anti-phishing-policies.md)</li><li>[Microsoft Defender 中 Office 365 的建議反網路釣魚原則設定](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</li><li> [模擬深入解析](impersonation-insight.md)</li><li>[EOP 中的欺騙智慧洞察力](learn-about-spoof-intelligence.md)</li><li>[管理承租人允許/封鎖清單](tenant-allow-block-list.md)。</li></ul>|
|**反惡意程式碼引擎**|是|依照如下所述，設定預設的反惡意程式碼原則： [在 EOP 中設定反惡意程式碼保護設定](protect-against-threats.md#part-1---anti-malware-protection-in-eop)。 <p> 詳細資訊： <ul><li>[Anti-malware protection](anti-malware-protection.md)</li><li>[建議的反惡意程式碼原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)</li><li>[設定反惡意程式碼原則](configure-anti-malware-policies.md)</li></ul>|
|**適用於 Office 365 的 Defender 中的安全附件**|否|設定保管庫附件的全域設定，並建立保管庫附件原則，如下所述：[設定 Microsoft Defender for Office 365 的保管庫附件設定](protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)。 <p> 詳細資訊： <ul><li>[建議的保管庫附件設定](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</li><li>[保管庫Microsoft Defender 中 Office 365 的附件](safe-attachments.md)</li><li>[設定安全附件原則](set-up-safe-attachments-policies.md)</li><li>[適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件](mdo-for-spo-odb-and-teams.md)</li><li>[Microsoft 365 E5 中的安全文件](safe-docs.md)</li></ul>|
|**保管庫Microsoft Defender 中 Office 365 的連結**|否|設定保管庫連結的全域設定，並建立保管庫連結原則，如下所述：[設定 Microsoft Defender for Office 365 的保管庫連結設定](protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)。 <p> 詳細資訊： <ul><li>[建議的保管庫連結設定](recommended-settings-for-eop-and-office365.md#safe-links-settings)</li><li>[設定安全連結原則](set-up-safe-links-policies.md)</li><li>[保管庫Microsoft Defender 中 Office 365 的連結](safe-links.md)</li><li>[針對 Office 365 設定 Microsoft Defender 中保管庫連結的全域設定](configure-global-settings-for-safe-links.md)</li></ul>|
|**反垃圾郵件 (郵件篩選)**|是|設定如下所述的預設反垃圾郵件原則： [在 EOP 中設定反垃圾郵件保護設定](protect-against-threats.md#part-3---anti-spam-protection-in-eop) <p> 詳細資訊： <ul><li>[建議的反垃圾郵件原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</li><li>[EOP 中的反垃圾郵件保護](anti-spam-protection.md)</li><li>[在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)</li></ul>|
|***電子郵件驗證***|是|電子郵件驗證使用 DNS 記錄，將可驗證的資訊新增至有關郵件來源和寄件者的電子郵件訊息。 Microsoft 365 會自動設定其預設網域 (onmicrosoft.com) 的電子郵件驗證，但是 Microsoft 365 系統管理員也可以設定自訂網域的電子郵件驗證。 使用的三種驗證方法： <ul><li>寄件者原則框架 (或 SPF) 。</li><ul><li>如需安裝程式，請參閱[在 Microsoft 365 中設定 SPF 以協助防止欺詐](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</li></ul> <li>網域認證金鑰識別郵件 (DKIM)。</li><ul><li>請參閱 [使用 DKIM 驗證從您的自訂網域傳送的輸出電子郵件](use-dkim-to-validate-outbound-email.md)。</li><li>在您設定 DKIM 後，請在 Microsoft 365 Defender 入口網站中加以啟用。</li></ul><li>以網域為基礎的訊息認證、報告與一致性 (DMARC)。</li><ul><li>若為 DMARC 安裝，[請使用 DMARC 驗證 Microsoft 365 中的電子郵件](use-dmarc-to-validate-email.md)。</li></ul></ul>|
|

> [!NOTE]
> 如果是非標準部署的 SPF、混合式部署及疑難排解： [Microsoft 365 如何使用寄件者原則框架 (SPF) 以避免欺騙](how-office-365-uses-spf-to-prevent-spoofing.md)。

## <a name="view-dashboards-and-reports-in-the-microsoft-365-defender-portal"></a>在 Microsoft 365 Defender 入口網站中查看儀表板與報表

請瀏覽以下報告與儀表板來深入了解您環境的健康狀況。 若您的組織使用 Office 365 服務，這些報告中的資料會變得更豐富。 現在，請先熟悉您可以監控與採取動作的項目。

<br>

****

|儀表板|說明|
|---|---|
|電子郵件安全性報告|這些報告可在 Exchange Online Protection 中取得。 如需詳細資訊，請參閱[在 Microsoft 365 Defender 入口網站中查看電子郵件安全性報告](view-email-security-reports.md)。|
|Office 365 報告的 Defender|報告只適用于 Office 365 的 Defender。 如需詳細資訊，請參閱[在 Microsoft 365 Defender 入口網站中查看 Office 365 報表的 Defender](view-reports-for-mdo.md)。|
|郵件流程報告和洞察力|您可以在 Exchange 系統管理中心 (EAC) 取得這些報告和洞察力。 如需詳細資訊，請參閱 [郵件流程報告](/exchange/monitoring/mail-flow-reports/mail-flow-reports) 和 [郵件流程 insights](/exchange/monitoring/mail-flow-insights/mail-flow-insights)。|
|[威脅總管 (或即時偵測)](threat-explorer.md)|如果您要調查或遭受對租使用者的攻擊，請使用 Explorer (或即時偵測) 來分析威脅。 總管 (或即時偵測) 能顯示隨時間受到的攻擊量，而您可以依照威脅系列、攻擊者的基礎結構等項目來分析這份資料。 您也可以將任何可疑的電子郵件標記為 [事件清單]。|
|

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>設定其他 Exchange Online 全租用戶設定

以下是建議的設定。

<br>

****

|區域|建議|
|---|---|
|**郵件流程規則** (也稱為傳輸規則) |透過封鎖可執行檔案類型和包含宏的 Office 檔案類型，新增郵件流程規則，以協助抵禦勒索軟體。 如需詳細資訊，請參閱[在 Exchange Online 中使用郵件流程規則檢查郵件附件](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)。 <p> 請參閱下列其他主題： <ul><li>[防範勒索軟體](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Microsoft 365 中的惡意程式碼和勒索軟體防護](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[從 Office 365 中復原勒索軟體攻擊](recover-from-ransomware.md)</li></ul> <p> 建立郵件流程規則來防止郵件自動轉寄至外部網域。 如需詳細資訊，請參閱[含有安全分數的用戶端外部轉寄降低風險規則](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) (英文)。 <p> 其他資訊：[Exchange Online 中的郵件流程規則 (傳輸規則)](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**新式驗證**|新式驗證是使用多重要素驗證 (MFA) 的必要條件。 MFA 是保護雲端資源存取權 (包括電子郵件) 的建議選項。 <p> 請參閱這些主題： <ul><li>[啟用或停用 Exchange Online 中的新式驗證](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[商務用 Skype線上：針對新式驗證啟用租使用者](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> Office 2016 用戶端、SharePoint Online 和商務用 OneDrive 預設會啟用新式驗證。 <p> 其他資訊：[Office 2013 和 Office 2016 用戶端應用程式的新式驗證運作方式](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>設定 SharePoint 系統管理中心的全租用戶共用原則

Microsoft 建議您從基礎保護開始，逐漸提高 SharePoint 小組網站的保護層級設定。 如需詳細資訊，請參閱[保護 SharePoint 網站和檔案的原則建議](sharepoint-file-access-policies.md)。

設定為基礎層級的 SharePoint 小組網站可讓您使用匿名存取連結，來與所有外部使用者共用檔案。 建議您採用此方法，而不要在電子郵件中傳送檔案。

為了支援基礎保護達到目標，請依以下建議設定全租用戶共用原則。 請為個別網站設定比此全租用戶原則更嚴格 (而非更寬鬆) 的共用設定。

<br>

****

|區域|包含預設原則|建議|
|---|---|---|
|**共用** (SharePoint Online 和商務用 OneDrive)|是|外部共用預設為啟用狀態。 這些為建議設定： <ul><li>允許共用已驗證的外部使用者，並使用匿名存取連結 (預設設定) 。</li><li>匿名存取連結會在數天后到期。 如有需要，請輸入一個數字，例如 30 天。</li><li>預設連結類型—選取 [只) 組織中的內部 (人員]。 想要以匿名連結進行共用的使用者必須從共用功能表中選擇此選項。</li></ul> <p> 其他資訊：[外部共用概觀](/sharepoint/external-sharing-overview)|
|

SharePoint 系統管理中心與商務用 OneDrive 系統管理中心包含同樣的設定。 任一系統管理中心內的設定都適用於兩者。

## <a name="configure-settings-in-azure-active-directory"></a>在 Azure Active Directory 中進行設定

請務必在 Azure Active Directory 中瀏覽以下兩個區域以完成全租用戶設定，以獲得更安全的環境。

### <a name="configure-named-locations-under-conditional-access"></a>設定具名位置 (使用條件式存取)

如果貴組織內有辦公室擁有安全網路存取權，請將信任的 IP 位址範圍新增為 Azure Active Directory 中的具名位置。 這項功能可協助減少誤判為登入風險事件的次數。

請參閱：[Azure Active Directory 中的具名位置](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>封鎖不支援新式驗證的應用程式

應用程式必須支援新式驗證才能使用多重要素驗證。 您無法使用條件式存取規則來封鎖不支援新式驗證的 App。

為了環境安全，請務必停用不支援新式驗證之 App 的驗證。 您可以在 Azure Active Directory 中使用即將推出的控制項完成這項作業。

在此同時，請使用下列其中一項方法，來為 SharePoint Online 和商務用 OneDrive 完成這項作業：

- 使用 PowerShell，請參閱 [封鎖未使用新式驗證的應用程式 (ADAL) ](/mem/intune/protect/app-modern-authentication-block)。
- 請在 SharePoint 系統管理中心內的 [裝置存取權] 頁面 - [控制不使用新式驗證的應用程式存取權] 進行此設定。 選擇 [封鎖]。

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>開始使用雲端 App 安全性或 Office 365 雲端 App 安全性

使用 Office 365 雲端 App 安全性來評估風險、警示可疑活動，並自動採取行動。 需要 Office 365 E5 方案。

或使用 Microsoft Cloud App Security，讓您即便在授與存取權後，也能讓所有雲端應用程式獲得更清楚的檢視、綜合性的控制權與更好的保護，包括 Office 365。

由於此解決方案建議使用 EMS E5 方案，我們建議您開始使用雲端 App 安全性，以便您可以搭配環境中的其他 SaaS 應用程式使用此功能。 請以預設原則與設定開始使用。

詳細資訊：

- [部署 Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)
- [Microsoft Cloud App Security 的詳細資訊](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [什麼是 Cloud App Security？](/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security 儀表板](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>其他資源

這些文章和指南提供保護 Microsoft 365 環境的其他規範性資訊：

- [適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) (您可以在任何環境中使用這些建議，特別是僅使用雲端的環境)

- [適用於身分識別與裝置的建議安全原則與設定](microsoft-365-policies-configurations.md) (這些建議包括 AD FS 環境說明)
