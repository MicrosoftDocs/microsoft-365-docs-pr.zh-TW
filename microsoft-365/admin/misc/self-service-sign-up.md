---
title: 在您的組織中使用自助註冊
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: seemg, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_signup
search.appverid: MET150
description: 深入瞭解 Microsoft 365 的自助註冊和可用自助服務程式，例如 Microsoft Power Apps、Microsoft Flow 和 Dynamics 365 （適用于財務）。
ms.date: 03/17/2021
ms.openlocfilehash: 7aec03abce468342cfeb23da490b1f950ecd7050
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286582"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>在您的組織中使用自助註冊

自助註冊可讓貴組織中的使用者更輕鬆地註冊 Microsoft 的線上服務。 我們呼叫這種註冊程式「自助註冊」，因為您的使用者可以註冊使用您訂閱所支付的服務，或是使用免費服務，而不需要代您採取動作。

## <a name="how-self-service-sign-up-works"></a>自助註冊的運作方式

下列範例說明如何自行註冊學校運作。 在其承租人中已啟用自助程式的任何組織，都能使用相同的處理常式。

1. 學生和教員成員具有學校電子郵件地址，表示與您的機構相關聯。 例如，電子郵件地址 jakob@uw.edu 可能會指出華盛頓大學的學生。
2. 學生和教員前往[我們的網站](https://go.microsoft.com/fwlink/p/?LinkId=536628)，並使用他們的電子郵件地址來註冊您的組織所提供的服務，例如 Microsoft 365 Apps 企業版。 他們也可以註冊其他我們提供的免費服務。
3. 我們會驗證他們的電子郵件地址，然後可以立即開始使用 Microsoft 365、Power BI 或其他服務。
4. 作為商務系統管理員，您可以在 Microsoft 365 系統管理中心中的 **授權** 頁面上選取訂閱，以查看誰已註冊訂閱。 如此一來，您就可以看到您租使用者中的服務是否有新增或無法辨識的授權。 若要控制使用者是否可以註冊自助訂閱，請使用 [MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings) PowerShell Cmdlet 搭配 **AllowAdHocSubscriptions** 參數。 如需詳細資訊，請參閱 [如何控制自助設定？](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>可用的自助服務程式

以下是目前可用的自助服務程式。 新增新程式時，此清單會隨之更新。

| 程式 <br/> | 說明 <br/> | 其他資訊 <br/> | 自助註冊的網站 <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1 * * * * <br/> |任何學生或教師都可以使用學校電子郵件地址來註冊免費的 Office 365，並取得 web 的 Office 應用程式、1 TB 的 OneDrive 雲端儲存區，以及 SharePoint 線上的類別、小組和專案網站。  <br/> |[Office 365 教育版技術常見問題](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 教育版](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1加** <br/> |合格的學生和教師可以註冊 Office 365 A1 加上，其中包括上述所有專案以及 Microsoft 365 Apps 企業版所述的專案。 Microsoft 365 Apps 企業版是生產力軟體，包括在您的桌上型電腦或筆記本電腦上安裝的 Word、PowerPoint、Excel、Outlook、OneNote、Publisher、Access 和商務用 Skype。  <br/> |[Office 365 教育版技術常見問題](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 教育版](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI 可讓使用者以直觀的方式呈現資料、分享發現和共同作業。 <br/> 如果您的組織已訂閱，您還可以查看「Power BI Pro 個別使用者試用版的授權」，其可提供使用者有限的高級功能存取權。  <br/> |[組織中的 Power BI](./power-bi-in-your-organization.md) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Rights Management Services (RMS)** <br/> |當組織中的使用者已傳送受 azure rights management)  (azure rights management 保護的敏感檔案，但其 IT 部門尚未執行 azure rights management (azure rms) 或 Active Directory Rights Management Services (AD RMS) 時，適用于個人的 RMS 是免費的自助訂閱。  <br/> |[適用于個人和 Azure 版權管理的 RMS](/azure/information-protection/rms-for-individuals) <br/> |[Microsoft Rights Management 入口網站](https://portal.azure.com/) ，讓您可以檢查是否可以開啟指定的許可權保護檔。  <br/> |
|**Microsoft Power Apps** <br/> |在 PowerApps 中，您可以執行您已建立的應用程式，或其他人建立並與您共用的應用程式，以管理組織資料。 在行動裝置（例如電話）上執行應用程式，也可以在瀏覽器中開啟 Dynamics 365，以執行這些應用程式。 您可以建立無限的應用程式-全部都不會瞭解程式設計語言（如 c #）。  <br/> |[自助服務註冊 PowerApps](/powerapps/maker/signup-for-powerapps) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**針對財務的 Dynamics 365** <br/> |取得適用于中小型企業的完整商務和財務管理解決方案。 Dynamics 365 for 金融可從第一天開始，進行排序、銷售、開具發票及報表工作變得更簡單。  <br/> |[適用于財務的 Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[適用于財務的 Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**適用于 Operations 的 Microsoft Dynamics 365** <br/> |提升您的經營速度。 Operations in Dynamics 365 中的完整 ERP 工具可提供全球可擴充性和數位智慧，以協助您在您的節奏時成長。  <br/> |[適用于 Operations 的 Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[適用于 Operations 的 Microsoft Dynamics 365](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |Microsoft AppSource 是在 Microsoft 雲端平臺上建立的軟體即服務商務應用程式目的地。 AppSource 的功能可擴充 Microsoft 產品（如 Azure、Dynamics 365、Office 365 及 Power BI）功能的數百個應用程式、附加元件和內容套件。  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Microsoft 合作夥伴獎勵** <br/> |Microsoft 合作夥伴網路提供三種類型的成員資格。 每種類型都提供一組優點，協助您的業務成長。 當您達到目標時，請以符合您獨特需求的層級，參與程式，以獲得更多權益，並與網路中的我們及其他合作夥伴合作。  <br/> |[Microsoft 合作夥伴獎勵](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Microsoft 合作夥伴獎勵](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft 商務中心** <br/> |Microsoft 商務中心是透過 Microsoft 產品和服務合約 (MPSA) 進行購買之客戶的入口網站。 <br/> |[快速入門：註冊 Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft 商務中心](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Microsoft 大量授權服務中心** <br/> |Microsoft 大量授權服務中心會顯示 Enterprise 所購買的授權，請選取、教育 (校園或 School) 、Open Value、open License 及 ISV 版稅協定。  <br/> |[VLSC 訓練和資源](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[大量授權服務中心](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft教育版** <br/> |透過使用 Minecraft 做為教學的平臺，教師可以鼓勵和鼓舞每個學生以取得更多，並 ignite 熱情的教學。 加入教育教育的群組如何使用 Minecraft 以解除對學生的潛力。  <br/> |[Minecraft教育版](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft教育版](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Upload 及共用整個組織的影片，以改善通訊、參與和學習。  <br/> |[註冊 &amp; 1 天的經驗](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automate 是一種產品，可協助您設定最喜歡的應用程式和服務之間的自動化工作流程，以同步處理檔案、取得通知、收集資料等等。  <br/> |[註冊並登入 Power Automate](/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Power Virtual Agent** <br/> |Power Virtual Agents 讓小組能夠使用無程式碼的圖形介面輕鬆建立功能強大的 bot，而不需要資料科學家或開發人員。 Power Virtual Agents 解決當今的 bot 組建許多主要問題。 它可以消除主題專家和建立 bot 的開發小組之間的缺口，以及識別問題和更新 bot 以解決問題的團隊間的長時間延遲。  <br/> |[授權和存取詳細資料](/power-virtual-agents/requirements-licensing) <br/> |[註冊 Power Virtual Agents](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Azure Active Directory (Azure AD) 企業對企業 (B2B) 共同作業可讓您邀請外部使用者 (或「來賓使用者」 ) 使用您付費的 Azure AD 服務。 有些功能是免費的，但是對於任何付費的 Azure AD 功能，您可以為您擁有的員工或您租使用者中的非來賓使用者的每個 Azure AD edition 授權，邀請最多五個來賓使用者。 <br/> |[Azure AD B2B 協同註冊的自助服務](/azure/active-directory/b2b/self-service-portal) <br/> |[Azure Active DirectoryB2B 共同作業授權指導方針](/azure/active-directory/b2b/licensing-guidance) <br/> |
