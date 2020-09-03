---
title: Microsoft 365 中的隔離與存取控制
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: 摘要： Microsoft 365 的各個應用程式內隔離和存取控制的說明。
ms.openlocfilehash: 53f60c09b94bdcc2515bcc5ff70dfbcd47f42bb4
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332325"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Microsoft 365 中的隔離與存取控制

Azure Active Directory (Azure AD) 和 Microsoft 365 使用高度複雜的資料模型，其中包含數十項服務、數百個實體、成千上萬的關聯性，以及數十個屬性。 在高層級，Azure AD 和服務目錄是承租人和收件者的容器，並使用以狀態型複寫通訊協定保持同步。 除了 Azure AD 中持有的目錄資訊之外，每個服務工作負載都有自己的目錄服務基礎結構。
 
![Microsoft 365 租使用者資料同步處理](../media/office-365-isolation-tenant-data-sync.png)

在此模型中，不會有單一的目錄資料來源。 特定系統擁有個別的資料，但沒有任何單一系統可容納所有的資料。 在此資料模型中，Microsoft 365 服務與 Azure AD 共同合作。 Azure AD 是共用資料的「實際系統」，這通常是每項服務所使用的小型和靜態資料。 Microsoft 365 和 Azure AD 內使用的同盟模型會提供資料的共用檢視。

Microsoft 365 同時使用實體儲存區和 Azure 雲端儲存空間。 Exchange Online (包括 Exchange Online Protection) 和商務用 Skype 為客戶資料使用自己的存放區。 SharePoint 線上同時使用 SQL Server 儲存區和 Azure 存放區，因此需要在儲存層級額外隔離客戶資料。

## <a name="exchange-online"></a>Exchange Online

Exchange Online 會將客戶資料儲存在信箱中。 信箱主控于可擴展的儲存體引擎中 (ESE) 稱為信箱資料庫的資料庫。 這包括使用者信箱、連結的信箱、共用信箱和公用資料夾信箱。 使用者信箱包括已儲存的商務用 Skype 內容，例如交談記錄。

使用者信箱內容包括：

- 電子郵件和電子郵件附件
- 行事曆和空閒/忙碌資訊
- 聯絡人
- 工作
- 注意事項
- 群組
- 推斷資料

Exchange Online 中的每個信箱資料庫包含多個承租人的信箱。 授權碼可保護每個信箱，包括租用內。 根據預設，只有指派的使用者可以存取信箱。 保護信箱的存取控制清單 (ACL) 包含租使用者層級上由 Azure AD 驗證的身分識別。 每個租使用者的信箱，只限于針對租使用者驗證提供者（僅包括來自該租使用者的使用者）驗證的身分識別。 承租人 A 中的內容無法以任何方式透過租使用者 B 中的使用者取得，除非租使用者 A 明確認可。

## <a name="skype-for-business"></a>商務用 Skype

商務用 Skype 會將資料儲存在不同的位置：

- 使用者和帳戶資訊，其中包括連接端點、租使用者 IDs、撥號對應表、漫遊設定、目前狀態、連絡人清單等等，都儲存在商務用 skype Active Directory 伺服器及各種商務用 Skype 資料庫伺服器中。 如果使用者已為這兩種產品或商務用 Skype server 啟用使用者，則連絡人清單會儲存在使用者的 Exchange Online 信箱中。 商務用 Skype 資料庫伺服器不會分割每個租使用者，但是會透過以角色為基礎的存取控制 (RBAC) 強制執行多重租用隔離。
- 會議內容和上傳的資料會儲存在分散式檔案系統 (DFS) 共用上。 在 Exchange Online 中也可以封存此內容（如果已啟用）。 DFS 共用不會依每個租使用者分割。 內容會受到 ACLs，而多重租用會透過 RBAC 強制執行。
- 詳細通話記錄（如通話記錄、IM 會話、應用程式共用、IM 記錄等）也可以儲存在 Exchange Online 中，但大部分的詳細通話記錄會暫時儲存在「 (CDR) 伺服器的通話詳細資料記錄中。 內容不會依每個租使用者分割，但是會透過 RBAC 強制執行多重租用。

## <a name="sharepoint-online"></a>SharePoint Online

線上 SharePoint 有數個獨立的機制，可提供資料隔離。 它會將物件儲存為應用程式資料庫中的抽象程式碼。 例如，當使用者將檔案上傳至 SharePoint 線上時，該檔案會分解、轉譯成應用程式代碼，並儲存在多個資料庫的多個資料表中。

如果使用者可以直接存取包含資料的儲存區，則內容不會 interpretable 至 SharePoint Online 以外的人或任何系統。 這些機制包括安全存取控制和屬性。 所有 SharePoint 線上資源都是由授權碼和 RBAC 原則所保護，包含在租用內。 保護資源 (ACL) 的存取控制清單包含在租使用者層級上驗證的身分識別。 針對承租人的 SharePoint 線上資料，僅限受租使用者驗證提供者驗證的身分識別。

除了 ACLs 之外，指定驗證提供者 (（即租使用者特有的 Azure AD) ）的租使用者層級屬性，只會寫入一次，而且一旦設定便無法變更。 針對租使用者設定驗證提供者租使用者屬性後，就無法使用任何公開給租使用者的 APIs 變更。

每個租使用者都使用唯一的 *SubscriptionId* 。 所有客戶網站均歸租使用者所有，並指派給租使用者特有的 *SubscriptionId* 。 網站上的 *SubscriptionId* 屬性會寫入一次，而且是永久的。 一旦指派給租使用者，便無法將網站移至不同的承租人。 *SubscriptionId*是用來建立驗證提供者的安全性範圍，並受限於租使用者的金鑰。

線上 SharePoint 會使用 SQL Server 和 Azure 儲存體進行內容中繼資料存放區。 內容存放區的分割碼是在 SQL 中 *SiteId* 。 執行 SQL 查詢時，SharePoint 線上使用 *SiteId* 驗證成為租使用者層級 *SubscriptionId* 檢查的一部分。

SharePoint 線上將加密檔內容儲存在 Microsoft Azure blob 中。 每個 SharePoint 線上伺服器陣列都有自己的 Microsoft Azure 帳戶，而且所有儲存于 Azure 中的 blob 都會以儲存在 SQL 內容存放區中的金鑰個別加密。 加密金鑰受授權層級的程式碼保護，而不是直接公開給使用者。 線上 SharePoint 已即時監控 HTTP 要求何時讀取或寫入超過一個承租人的資料。 要求身分識別 *subscriptionid* 會針對存取資源的 *subscriptionid* 進行追蹤。 存取超過一個承租人的資源的要求永遠不應該由使用者執行。 多租使用者環境中的服務要求是唯一例外。 例如，搜尋編目程式一次會同時提取整個資料庫的內容變更。 這通常包含在單一服務要求中查詢多個租使用者的網站，這是出於效能原因而進行的。

## <a name="teams"></a>Teams

根據內容類型而定，小組資料會以不同的方式儲存。 

若要深入討論，請參閱 [Microsoft 小組架構上的 Ignite 專題討論授課](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) 。

### <a name="core-teams-customer-data"></a>核心團隊客戶資料

如果您的租使用者是在澳大利亞、加拿大、歐盟、法國、德國、印度、日本、南非、韓國、瑞士 (，其中包括列支敦斯登) 、阿拉伯阿拉伯聯合大公國、英國或美國，Microsoft 只會將下列客戶資料儲存在該位置內：

- 小組聊天、小組和頻道交談、影像、語音信箱訊息和連絡人。
- SharePoint Online 站台內容和儲存在該站台內的檔案。
- 上傳至工作或學校 OneDrive 的檔案。

#### <a name="chat-channel-messages-team-structure"></a>聊天、通道訊息、小組結構

小組中的每一個小組都是由 Microsoft 365 群組及其 SharePoint 的網站和 Exchange 信箱來備份。 私人聊天 (包括群組聊天) 、以通道中的交談的一部分傳送的郵件，以及小組和通道的結構，都是儲存在 Azure 中執行的 chat service 中。 資料也會儲存在使用者和群組信箱的隱藏資料夾中，以啟用資訊保護功能。

#### <a name="voicemail-and-contacts"></a>語音信箱和連絡人

語音信箱儲存在 Exchange 中。 連絡人儲存于以 Exchange 為基礎的雲端資料儲存區。 Exchange 和以 Exchange 為基礎的雲端存放區已提供每個全球資料中心 geos 中的資料派駐服務。 針對所有小組，語音信箱和連絡人會儲存于國內、加拿大、法國、德國、印度、日本、阿拉伯阿拉伯聯合大公國、英國、南非、南非和瑞士 (，其中包括列支敦斯登) 及美國。 對於所有其他國家/地區，檔案會根據租使用者親近性儲存在 US、歐洲或亞洲位置。

#### <a name="images-and-media"></a>影像和媒體

在聊天 (中使用的媒體除了 Giphy Gif （未儲存但屬於原始 Giphy 服務 URL 的參考連結）之外，Giphy 是一種非 Microsoft 服務) 儲存在與聊天服務部署于相同位置的 Azure 媒體服務中。

#### <a name="files"></a>檔案

檔案 (包括 OneNote 和 Wiki) ，該中的人員會儲存在該小組的 SharePoint 網站中。 在會議或通話期間，私人聊天或聊天中共用的檔案，會上載並儲存在共用該檔案之使用者的工作或學校帳戶的 OneDrive 中。 Exchange、SharePoint 和 OneDrive 已提供每個全球資料中心 geos 中的資料派駐服務。 因此，針對現有的客戶，所有檔案、OneNote 筆記本、小組 wiki 內容，以及屬於小組經驗一部分的信箱，都已根據您的租使用者關聯性儲存在位置。 檔案儲存于國內、加拿大，法國，德國，印度，日本，阿拉伯阿拉伯聯合大公國，英國，南非，南非，韓國，及瑞士 (包括列支敦斯登) 。 對於所有其他國家/地區，檔案會根據租使用者親近性儲存在 US、歐洲或亞太地區位置。
