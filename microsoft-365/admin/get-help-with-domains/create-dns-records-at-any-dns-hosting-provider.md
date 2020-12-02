---
title: 新增 DNS 記錄以連接您的網域
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: 了解如何在 Microsoft 365 的任一 DNS 主機服務提供者上驗證您的網域並建立 DNS 記錄。
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: bc22dbd3a050516f518c9ddc9ccf5a3af9c76f12
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519290"
---
# <a name="add-dns-records-to-connect-your-domain"></a>新增 DNS 記錄以連接您的網域

如果您是透過協力廠商主機服務提供者購買網域，您可以更新註冊機構帳戶中的 DNS 記錄，將它連線到 Microsoft 365。

在這些步驟結束時，您的網域將會在您購買網域的主機中持續註冊，但 Microsoft 365 可以將它用於您的電子郵件地址 (例如 user@yourdomain.com) 和其他服務。

如果您沒有新增網域，組織中的人員將會使用 onmicrosoft.com 網域做為其電子郵件地址，直到您新增網域為止。 新增使用者之前，請務必先新增您的網域，這樣您就不需要再設定一次。

若您在下方找不到所需內容，請[查看網域常見問題集](../setup/domains-faq.md)。

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a>步驟 1: 新增 TXT 或 MX 記錄以驗證您擁有該網域

### <a name="recommended-verify-with-a-txt-record"></a>建議：使用 TXT 記錄進行驗證

首先，您必須證明您擁有要新增至 Microsoft 365 的網域。

1. 登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)，然後選取 **[顯示所有]** > **[設定]** > **[網域]**。
2. 在新的瀏覽器索引標籤或視窗中，登入您的 DNS 主機服務提供者，然後尋找您管理 DNS 設定的位置（例如 [區域檔案設定]、[管理網域]、[網域管理員]、[DNS 管理員]）。
3. 移至您提供者的 [DNS 管理員] 頁面，並將系統管理中心所指出的 TXT 記錄新增到您的網域。

新增此記錄不會影響您現有的電子郵件或其他服務，您只要將網域連線至 Microsoft 365，就能安全地將它移除。

範例：
- TXT 名稱: `@`
- TXT 值： MS = ms # # # # # # # # （[系統管理中心] 的唯一識別碼）
- TTL： `3600‎` （或您的提供者預設值）

4. 儲存記錄、返回系統管理中心，然後選取 **[驗證]**。 註冊記錄變更通常需要15分鐘的時間，但是有時候會需要更長的時間。 請稍候一段時間，並嘗試挑選變更。

在 Microsoft 找到正確的 TXT 記錄後，您的網域就完成驗證了。

### <a name="verify-with-an-mx-record"></a>使用 MX 記錄進行驗證

如果您的註冊機構不支援新增 TXT 記錄，您可以新增 MX 記錄以進行驗證。

1. 登入 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)，然後選取 **[顯示所有]** > **[設定]** > **[網域]**。
2. 在新的瀏覽器索引標籤或視窗中，登入您的 DNS 主機服務提供者，然後尋找您管理 DNS 設定的位置（例如 [區域檔案設定]、[管理網域]、[網域管理員]、[DNS 管理員]）。
3. 移至您提供者的 [DNS 管理員] 頁面，並將系統管理中心所指出的 MX 記錄新增到您的網域。

此 MX 記錄的「優先順序」必須是網域所有現有 MX 記錄的最高者。 否則，可能會干擾傳送和接收電子郵件。 當網域驗證完成後，您應該立即刪除這項記錄。

請確認欄位已設定為下列的值：

- 記錄類型: `MX`
- 優先順序: 設定為可用的最高值，通常為 `0`。
- 主機名稱: `@`
- 指向 [位址]: 從系統管理中心複製值並貼上。
- TTL：`3600‎` (或您的提供者預設值)

在 Microsoft 找到正確的 MX 記錄後，您的網域即完成驗證。

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a>步驟2：新增 DNS 記錄以連結 Microsoft 服務

在新的瀏覽器索引標籤或視窗中，登入您的 DNS 主機服務提供者，然後尋找您管理 DNS 設定的位置（例如 [區域檔案設定]、[管理網域]、[網域管理員]、[DNS 管理員]）。

視您要啟用的服務而定，您將新增多種不同類型的 DNS 記錄。 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a>新增電子郵件的 MX 記錄（Outlook、Exchange Online）
**開始之前：** 如果使用者已經擁有您網域的電子郵件（例如 user@yourdomain.com），請在設定 MX 記錄前，先在系統管理中心建立其帳戶。 這樣一來，他們就能繼續收到電子郵件。 當您更新網域的 MX 記錄時，使用您網域所有人的所有新電子郵件現在都會傳送至 Microsoft 365。 您已收到的任何電子郵件將會保留在目前的電子郵件主機中，除非您決定[將電子郵件和連絡人移轉至 Microsoft 365](../setup/migrate-email-and-contacts-admin.md)。

您將會從系統管理中心網域設定向導取得 MX 記錄的資訊。

在您的主機提供者的網站上，新增 MX 記錄。
請確認欄位已設定為下列的值：

- 記錄類型: `MX`
- 優先順序: 設定為可用的最高值，通常為 `0`。
- 主機名稱: `@`
- 指向 [位址]: 從系統管理中心複製值並貼上。
- TTL： `3600‎` （或您的提供者預設值）

儲存記錄，然後移除任何其他的 MX 記錄。

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a>新增 CNAME 記錄以連接其他服務 (Teams、Exchange Online、AAD、MDM)
您將會從系統管理中心網域設定向導取得 CNAME 記錄的資訊。

在您的宿主提供者的網站上，為您要連線的每個服務新增 CNAME 記錄。
請確認每個欄位皆已設定為下列的值：

- 記錄類型: `CNAME (Alias)`
- 主機: 從系統管理中心貼上您複製的值。
- 指向 [位址]: 從系統管理中心複製值並貼上。
- TTL： `3600‎` （或您的提供者預設值）


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a>新增或編輯 SPF TXT 記錄以協助防範垃圾郵件 (Outlook、Exchange Online)
**在您開始之前:** 如果網域已經有 SPF 記錄，請勿為 Microsoft 365 建立一個新的記錄。 請改為將所需的 Microsoft 365 值新增到您主機服務提供者網站的目前記錄中，這樣您就有了一份包含兩組值的 *單一* SPF 記錄。

在您的主機提供者網站上，編輯現有 SPF 記錄或建立 SPF 記錄。
請確認欄位已設定為下列的值：

- 記錄類型: `TXT (Text)`
- 主機: `@`
- TXT 值: `v=spf1 include:spf.protection.outlook.com -all`
- TTL： `3600‎` （或您的提供者預設值）

儲存記錄。

透過其中一個 [SPF 驗證工具](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) 以驗證您的 SPF 記錄

SPF 是設計來協助防止詐騙，但是仍有 SPF 無法防護的詐騙技術。 為了防範這些技術，設定 SPF 之後，您也應該為 Microsoft 365 設定 DKIM 和 DMARC。 

若要開始使用，請參閱[在 Microsoft 365 中使用 DKIM 驗證從您的網域傳送的外寄電子郵件](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) 和 [使用 DMARC 在 Microsoft 365 中驗證電子郵件](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx)。

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a>新增通訊服務的 SRV 記錄 ( Teams、商務用 Skype)

在您的主機提供者的網站上，為您要連線的每個服務新增 SRV 記錄。
請確認每個欄位皆已設定為下列的值：

- 記錄類型: `SRV (Service)`
- 名稱: `@`
- 目標: 從系統管理中心複製值並貼上。
- 通訊協定: 從系統管理中心複製值並貼上。
- 服務: 從系統管理中心複製值並貼上。
- 優先順序: `100`
- 加權: `1`
- 埠：從系統管理中心複製值並貼上。
- TTL： `3600‎` （或您的提供者預設值）

儲存記錄。

#### <a name="srv-record-field-restrictions-and-workarounds"></a>SRV 記錄欄位限制和因應措施
某些主機提供者會限制 SRV 記錄中的欄位值。 以下是這些限制的一些常見因應措施。

##### <a name="name"></a>姓名
如果您的主機服務提供者不允許將此欄位設定為 **@**，請將它保留為空白。 *只有* 當您的 DNS 主機服務者在服務和通訊協定值有不同的欄位時，才能使用此方法。 否則，請參閱下列服務和通訊協定附註。

##### <a name="service-and-protocol"></a>服務和通訊協定
如果您的主機提供者不提供這些用於 SRV 記錄的欄位，您必須在記錄的 **[名稱]** 欄位中指定 **[服務]** 和 **[通訊協定]** 值。 (附註：視您的主機提供者而定，**[名稱]** 欄位可能會是其他名稱，例如：**[主機]**、**[主機名稱]** 或 **[子網域]**) 若要新增這些值，您需建立一個字串，並用點分隔值。 

範例：`_sip._tls`

##### <a name="priority-weight-and-port-br"></a>優先順序、加權和連接埠 <br>
如果您的主機服務提供者未提供這些 SRV 記錄欄位，您必須在記錄的 **[目標]** 欄位中指定它們。 (注意: 視您的主機提供者而定，**[目標]** 欄位可能名為其他內容，例如: **[內容]**、**[IP 位址]**，或 **[目標主機]**。) 

若要新增這些值，請建立一個字串，並以空格分隔值，*有時候會以點* 結尾 (如果您不確定，請向您的提供者詢問)。 這些值必須按照以下列順序：Priority、Weight、Port、Target。 

- 範例1: `100 1 443 sipdir.online.lync.com.`
- 範例2: `100 1 443 sipdir.online.lync.com`
