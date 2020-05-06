---
title: 將保護套用至個人資料
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 02/07/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
- SPO_Content
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 了解如何使用規範中心內的資料外洩防護 (DLP) 原則來保護 Office 365 中的個人資料。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f5c82a1f841cca1eea9a79d8f9dbcc1f81a3ad74
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035175"
---
# <a name="apply-protection-to-personal-data"></a>將保護套用至個人資料

Microsoft 365 中的個人資訊保護包括使用資料外洩防護功能。 透過合規性中心的資料外洩防護 (DLP) 原則，您可以識別、監視及自動保護整個 Microsoft 365 的敏感資訊。

本主題描述如何使用 DLP 保護個人資料。本主題也會列出可用來實現 GDPR 規範的其他保護功能，包括在 SharePoint 文件庫中設定權限，以及使用裝置存取原則。

## <a name="apply-protection-using-data-loss-prevention-in-microsoft-365"></a>使用 Microsoft 365 中的資料外洩防護來套用保護

使用 DLP 時，您可以：

-   識別各個位置中的敏感資訊。

-   防止意外共用敏感資訊。

-   協助使用者了解如何符合規範，而不中斷其工作流程。

-   檢視 DLP 報告以了解有哪些內容符合您的組織的 DLP 原則。

如需詳細資訊，請參閱[資料外洩防護原則概觀](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)。

![用於建立資料外洩防護原則的選項](../media/Apply-protection-to-personal-data-in-Office-365-image1.png)

下圖顯示用於建立 DLP 原則的選項：

-   選擇要套用的保護。保護可以包含：

    -   使用者的原則提示

    -   系統管理員的電子郵件報告

    -   防止外部共用、內部共用或兩者

-   選擇套用保護的準則。使用這種類型的內容，將保護套用至文件：您可以設定原則，來使用敏感資訊類型和/或標籤。

### <a name="using-dlp-for-gdpr-compliance"></a>對 GDPR 規範使用 DLP

Microsoft 365 DLP 的其中一個主要用途為識別 Microsoft 365 環境中與歐盟資料主旨相關的個人資料。Microsoft 365 DLP 可以通知規範小組，個人資訊在 SharePoint Online 和商務用 OneDrive 的儲存位置，或使用者何時傳送包含個人資訊的電子郵件。使用與歐盟居民相關的個人資訊時，DLP 也可以為您的員工提供原則提示。

教育並認知歐盟居民資料應儲存在您環境的何處中，以及允許您的員工如何處理這些資料，這代表一種使用 Microsoft 365 DLP 的資訊保護層級。通常，已有權存取這類資訊的員工需要這個存取權，才能進行其日常工作。實施 DLP 原則來協助遵循 GDPR，可能不需要限制存取。

不過，遵循 GDPR 通常包含組織的風險型評估，其依循法律與資訊安全觀點、何種類型與個人資訊儲存位置的識別，以及是否有儲存及處理該資訊的法律理由。根據此評估，實作原則來保護組織及遵循 GDPR，可能需要移除員工對文件的存取，而此文件包含歐盟資料主旨的個人資訊。若需要進一步保護，可以另外設定 DLP 保護。

下表列出三個使用 DLP 增加保護的設定。第一個設定 (認知).可以用作起點，以及 GDPR 的最低保護層級。

### <a name="example-protection-levels-that-can-be-configured-with-dlp-policies-and-used-for-gdpr-compliance"></a>可以使用 DLP 原則來設定及用於 GDPR 規範的保護層級範例

<table>
<thead>
<tr class="header">
<th align="left"><strong>保護層級</strong></th>
<th align="left"><strong>具有與歐盟資料主旨相關的個人資訊之文件的 DLP 設定</strong></th>
<th align="left"><strong>效益與風險</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">認知</td>
<td align="left"><p>在 SharePoint Online 和商務用 OneDrive 的文件中找到此資料時，將電子郵件通知傳送至規範小組。</p>
<p>存取包含此資料的文件時，在 SharePoint 和商務用 OneDrive 中自訂原則提示並向員工顯示。</p>
<p>共用此資料時偵測報告。</p></td>
<td align="left"><p>提高規範小組以及員工關於此資料儲存位置的認知。</p>
<p>教育員工關於處理包含此資料之文件的公司原則。</p>
<p>不阻止員工在內部或外部共用資料。</p>
<p>您可以檢閱共用資料的 DLP 報告，並決定是否需要增加保護。</p></td>
</tr>
<tr class="even">
<td align="left">阻止外部共用</td>
<td align="left"><p>當此資料與外部使用者共用時，即會限制存取 SharePoint 和商務用 OneDrive 中包含該內容的文件。</p>
<p>文件若包含此資料，即會阻止將具有該文件的電子郵件傳送至外部收件者。</p>
<p>共用此資料時偵測報告。</p></td>
<td align="left"><p>允許員工內部使用此資料時，即會阻止外部共用此資料。</p>
<p>您可以檢閱內部共用資料的 DLP 報告，並決定是否需要增加此保護。</p></td>
</tr>
<tr class="odd">
<td align="left">阻止內部及外部共用</td>
<td align="left"><p>在內部或外部共用此資料時，即會限制存取 SharePoint 和商務用 OneDrive 中包含該內容的文件。</p>
<p>阻止包含此資料的電子郵件同時傳送至內部和外部收件者。</p></td>
<td align="left"><p>阻止內部及外部共用此資料</p>
<p>員工可能會無法完成需要使用此資料的工作。</p>
<p>您可以檢閱內部或外部共用資料的 DLP 報告，並決定是否需要使用者訓練。</p></td>
</tr>
</tbody>
</table>

附註：當保護層級增加時，在某些情況下，使用者存取資訊的能力將會降低，而且可能會影響其生產力或完成日常工作的能力。實作影響員工的原則來增加保護層級，通常會伴隨使用者訓練、教育使用者關於新的安全性原則，以及協助他們在更安全的環境中繼續提高生產力。

### <a name="example-dlp-policy-for-gdpr--awareness"></a>GDPR 的外部 DLP 原則 — 認知 

名稱：受到 GDPR 約束之個人資料的認知。

描述：向員工顯示原則提示、在 SharePoint 和商務用 OneDrive 的文件中找到此資料時通知規範小組、在您組織之外共用此資料時偵測並回報。

<table>
<thead>
<tr class="header">
<th align="left"><strong>控制</strong></th>
<th align="left"><strong>設定</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">選擇要保護的資訊</td>
<td align="left">選取自訂原則範本。</td>
</tr>
<tr class="even">
<td align="left">位置</td>
<td align="left">Microsoft 365 中的所有位置</td>
</tr>
<tr class="odd">
<td align="left">尋找包含的內容</td>
<td align="left">按一下 [編輯]，然後新增所有您針對環境策劃的敏感資訊類型。</td>
</tr>
<tr class="even">
<td align="left">在共用此內容時偵測</td>
<td align="left">核取此方塊，然後選取 [與我組織外的人員]。</td>
</tr>
<tr class="odd">
<td align="left">在內容符合原則設定時通知使用者</td>
<td align="left"><p>核取此方塊 (「向使用者顯示原則提示並傳送電子郵件通知。」)</p>
<p>按一下 [自訂提示和電子郵件]，並針對您的環境更新這些項目。請參閱本文中的預設通知：<a href="https://support.office.com/article/Send-email-notifications-and-show-policy-tips-for-DLP-policies-87496bc5-9601-4473-8021-cb05c71369c1?ui=en-US&amp;rs=en-US&amp;ad=US">傳送電子郵件通知，並顯示 DLP 原則的原則提示</a>。</p></td>
</tr>
<tr class="even">
<td align="left">在一次共用特定數量的敏感資訊時偵測</td>
<td align="left"><p>[在共用的內容包含：至少 ___ 個執行個體，屬於相同的敏感資訊類型時偵測] — 將此項設為 1。</p>
<p>[以電子郵件傳送事件報告] — 請核取此方塊。按一下 [選擇要包含在報告中的項目以及接收者]。請務必新增您的合規性小組。</p>
<p>[限制誰可以存取的內容並覆寫原則] — 清除此核取方塊，以接收關於敏感資訊的通知，不阻止使用者存取該資訊。</p></td>
</tr>
</tbody>
</table>

所有位置包括

- SharePoint Online

- OneDrive for商務用帳戶

- Exchange 信箱

由於內容搜尋目前無法讓您利用電子郵件測試敏感資訊類型，請考慮為 Exchange 建立個別原則 (每一個原則中都有敏感資訊類型的子集)，以及監視這些原則的推出。

## <a name="additional-protection-you-can-apply-to-protect-personal-data-in-microsoft-365"></a>您可套用以對 Microsoft 365 中的個人資料進行保護的額外保護

敏感資訊類型、標籤和資料外洩防護原則可協助您識別包含特定資料的文件，並套用保護。不過，這些保護視將針對資料存取而設定的權限、具有未受連累之帳戶的使用者，以及狀況良好的裝置而定。

下圖詳述您可以套用以保護個人資料存取的額外保護。

![保護個人資料存取的額外保護](../media/Apply-protection-to-personal-data-in-Office-365-image2.png)

為了便於存取，下表會在圖例中提供相同的資訊。

<table>
<thead>
<tr class="header">
<th align="left"><strong>保護範圍</strong></th>
<th align="left"><strong>功能</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">文件和電子郵件層級保護 (包括傳輸中郵件，但不包括目前在信箱中處於靜態的郵件)</td>
<td align="left"><p>敏感資訊類型</p>
<p>Office 標籤</p>
<p>資料外洩防護原則</p>
<p>電子郵件的 Microsoft 365 郵件加密</p></td>
</tr>
<tr class="even">
<td align="left">網站和文件庫層級保護 (包括 SharePoint 和 OneDrive 網站)</td>
<td align="left"><p>SharePoint Online 和商務用 OneDrive 網站與文件庫的權限</p>
<p>SharePoint Online 和商務用 OneDrive 的外部共用原則 (網站層級)</p>
<p>網站層級裝置存取控制</p></td>
</tr>
<tr class="odd">
<td align="left">服務存取保護 (包括 Microsoft 365 中所有服務的存取)</td>
<td align="left"><p>企業行動力 + 安全性 (EMS) 套件的身分識別與裝置存取保護</p>
<p>特許存取管理</p>
<p>Windows 10 安全性功能</p></td>
</tr>
</tbody>
</table>

本文的其餘部分提供其中每一種保護類別的詳細資訊。

### <a name="capabilities-that-are-ok-to-use-with-gdpr"></a>可與 GDPR 搭配使用的功能

您可以在針對 GDPR 規範設定的環境中使用下列功能。GDPR 規範不一定需要這些功能，但可以使用它們，不會對您探索、保護、監視及報告與 GDPR 規範相關之資料的能力產生負面影響。

客戶金鑰 — 可讓客戶對用來在 Microsoft 365 內加密靜態資料的加密金鑰提供及保留控制權。此建議只適用於法規上需要管理其本身加密金鑰的客戶。

客戶加密箱 — 客戶加密箱可讓您控制 Microsoft 支援工程師如何存取您的資料，以在必要時根據具體情況解決技術問題。您可以控制是否要授與支援工程師存取您資料的權限。每個要求都會隨附到期時間。

## <a name="site-and-library-level-protection"></a>網站和文件庫層級保護

### <a name="permissions-for-sharepoint-and-onedrive-for-business-libraries"></a>SharePoint 和商務用 OneDrive 文件庫的權限

使用 SharePoint 中的權限，允許或限制使用者存取網站或其內容。將個別使用者或 Azure Active Directory 群組新增至預設的 SharePoint 群組。或者，建立自訂群組進行更細微的控制。

![從完全控制到僅檢視的權限層級](../media/Apply-protection-to-personal-data-in-Office-365-image3.png)

此圖描繪從完全控制到僅檢視的權限等級。下表包括相同的資訊。

<table>
<thead>
<tr class="header">
<th align="left"><strong>完全控制</strong></th>
<th align="left"><strong>設計</strong></th>
<th align="left"><strong>編輯</strong></th>
<th align="left"><strong>參與</strong></th>
<th align="left"><strong>讀取</strong></th>
<th align="left"><strong>僅檢視</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"></td>
<td align="left">參與 + 核准與自訂</td>
<td align="left">參與 + 新增、編輯和刪除清單 (不只是清單項目)</td>
<td align="left">檢視、新增、更新及刪除清單項目與文件</td>
<td align="left">檢視並下載</td>
<td align="left">檢視，不下載</td>
</tr>
</tbody>
</table>

詳細資訊：

-   [瞭解 SharePoint 中的權限層級](https://support.office.com/zh-TW/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)

-   [了解 SharePoint 群組](https://support.office.com/zh-TW/article/Understanding-SharePoint-groups-94d9b261-161e-4ace-829e-eca1c8cd2eb8)

### <a name="external-sharing-policies-for-sharepoint-and-onedrive-for-business-libraries"></a>SharePoint 和商務用 OneDrive 文件庫的外部共用原則

許多組織允許外部共用以支援分工合作。了解如何設定您租用戶的整個設定。然後，檢閱包含個人資料之網站的外部共用設定。

外部使用者是您組織外的人員，受邀存取您的 SharePoint 網站和文件，但沒有您的 SharePoint Online 或 Microsoft 365 訂閱的授權。

外部共用原則同時適用於 SharePoint Online 和商務用 OneDrive

-   您必須是 SharePoint Online 管理員，才能設定共用原則。

-   您必須是網站擁有者或具備完全控制權限，才能與外部使用者共用網站或文件。

下表彙總您可以設定的控制權。

<table>
<thead>
<tr class="header">
<th align="left"><strong>控制類別</strong></th>
<th align="left"><strong>選項</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">共用類型</td>
<td align="left"><p>不允許組織外共用 (可以針對個別網站集合設定)</p>
<p>僅允許與經過驗證的外部使用者共用 (允許新的使用者或限制為現有的使用者，也可以針對個別網站集合設定)*</p>
<p>允許利用匿名存取連結與外部使用者共用 (也可以針對個別網站集合設定)</p>
<p>使用網域限制外部共用 (允許和拒絕清單)</p>
<p>選擇預設連結類型 (匿名、公司可共用或受限制)</p>
</td>
</tr>
<tr class="even">
<td align="left">外部使用者可以做什麼</td>
<td align="left"><p>阻止外部使用者共用他們未擁有的檔案、資料夾、網站</p>
<p>要求外部使用者接受具有邀請傳送至其中之相同帳戶的共用邀請</p></td>
</tr>
<tr class="odd">
<td align="left">通知</td>
<td align="left"><p>目前僅適用於商務用 OneDrive。下列情況時通知擁有者：</p>
- <p>使用者邀請其他外部使用者共用檔案</p>
- <p>外部使用者接受存取檔案的邀請</p>
- <p>已建立或變更匿名存取連結</p></td>
</tr>
</tbody>
</table>

詳細資訊：

-   [管理您的 SharePoint Online 環境外部共用](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&rs=en-US&ad=US)

-   [與您組織外的人員共用網站或文件](https://support.office.com/zh-TW/article/Share-sites-or-documents-with-people-outside-your-organization-80e49744-e30f-44db-8d51-16661b1d4232)

### <a name="site-level-device-access-policies"></a>網站層級裝置存取控制

SharePoint Online 和商務用 OneDrive 可讓您在網站層級設定裝置存取原則。這可讓您針對具有敏感資料的網站設定更多的保護。

如果您設定網站層級的裝置存取原則，請務必利用下列原則協調這些原則：租用戶層級原則，以及在 Azure Active Directory、Intune 和 Intune App Management 中設定的原則。

SharePoint 和商務用 OneDrive 的裝置存取原則需要 Azure Active Directory 和 Microsoft Intune 中的支援原則，視視您正要實作的情節而定。下表彙總您可以使用裝置存取原則來達成的目標，並指出哪些產品需要支援原則。

<table>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">只允許從特定 IP 位址位置存取</th>
<th align="left">阻止使用者將檔案下載至非網域聯結的裝置</th>
<th align="left">封鎖對非網域聯結之裝置的存取</th>
<th align="left">阻止使用者將檔案下載至不相容的裝置</th>
<th align="left">封鎖對不相容裝置的存取</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">SharePoint 系統管理中心</td>
<td align="left">是</td>
<td align="left">是</td>
<td align="left">是</td>
<td align="left">是</td>
<td align="left">是</td>
</tr>
<tr class="even">
<td align="left">Azure Active Directory</td>
<td align="left"></td>
<td align="left">是</td>
<td align="left">是</td>
<td align="left">是</td>
<td align="left">是</td>
</tr>
<tr class="odd">
<td align="left">Microsoft Intune</td>
<td align="left"></td>
<td align="left"></td>
<td align="left"></td>
<td align="left">是</td>
<td align="left">是</td>
</tr>
</tbody>
</table>

詳細資訊：[SharePoint Online 管理中心：控制從未受管理裝置的存取](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622?ui=en-US&rs=en-US&ad=US)。

## <a name="service-access-protection-for-identities-and-devices"></a>身分識別與裝置的服務存取保護

Microsoft 建議您針對存取服務的身分識別與裝置設定保護。您用於保護 Microsoft 365 服務存取的工作也可用來保護其他 SaaS 服務、PaaS 服務，甚至是其他雲端提供者中應用程式的存取。

身分識別與裝置的存取保護提供保護的底線，以確保身分識別不會受到連累、裝置安全無虞，且裝置上存取的組織資料遭到隔離並受到保護。

如需起點建議與指引，請參閱[適用於政治活動、非營利組織和其他彈性組織的 Microsoft 安全性指南](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance)。

如需搭配 AD FS 的混合式身分識別環境，請參閱[建議的安全性原則和設定](https://docs.microsoft.com/microsoft-365-enterprise/microsoft-security-guidance)。

下圖描述雲端服務 (SaaS、PaaS)、帳戶類型 (租用戶網域帳戶與 B2B 帳戶)，以及服務存取功能如何相關。請務必注意可與 B2B 帳戶搭配使用的功能。

![雲端服務、帳戶類型和存取功能](../media/Apply-protection-to-personal-data-in-Office-365-image4.png)

為了便於存取，本節的其餘部分描述此圖。

### <a name="cloud-services"></a>雲端服務

Azure Active Directory 可讓您的身分識別存取任何雲端服務，包括非 Microsoft 提供者，例如 Amazon Web 服務。此圖顯示 Microsoft 365、「其他 SaaS 應用程式」和「PaaS 應用程式」。箭號從 Azure Active Directory 指向其中每一個服務，這顯示 Azure Active Directory 可用於所有這類應用程式類型的驗證。

### <a name="types-of-accounts"></a>帳戶類型

租用戶網域帳戶是您新增至租用戶並直接管理的帳戶。B2B 帳戶是組織外受邀與您合作之使用者的帳戶。這些可以是其他 Microsoft 365 帳戶、其他組織帳戶或消費者帳戶 (例如 Gmail)。此圖顯示 Azure Active Directory 內的兩種帳戶類型。

### <a name="capabilities"></a>功能

下表中的功能可保護身分識別與裝置。該表指出也可以與 B2B 帳戶搭配使用的功能，與此圖類似。

<table>
<thead>
<tr class="header">
<th align="left"><strong>功能</strong></th>
<th align="left"><strong>使用租用戶網域帳戶</strong></th>
<th align="left"><strong>使用 Azure B2B 帳戶 (不需額外授權)</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">多重要素驗證和條件式存取</td>
<td align="left">是</td>
<td align="left">是</td>
</tr>
<tr class="even">
<td align="left">Azure AD Identity Protection</td>
<td align="left">是</td>
<td align="left">是</td>
</tr>
<tr class="odd">
<td align="left">Azure AD Privileged Identity Management</td>
<td align="left">是</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Mobile Application Management (MAM)</td>
<td align="left">是</td>
<td align="left"></td>
</tr>
<tr class="odd">
<td align="left">裝置註冊和管理</td>
<td align="left">是</td>
<td align="left">只有一個組織可以管理裝置</td>
</tr>
<tr class="even">
<td align="left">Windows 10 安全性功能 (根據裝置相容性的條件式存需要裝置管理)</td>
<td align="left">是</td>
<td align="left">是</td>
</tr>
</tbody>
</table>

您可以將授權新增至 B2B 帳戶，提供這些使用者額外的功能，以在需要時保護您環境中的個人資料存取。
