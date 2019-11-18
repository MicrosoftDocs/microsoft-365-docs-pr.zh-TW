---
title: Skype、 OneDrive、 SharePoint 和 Exchange 的 office 365 加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
description: 摘要： 說明的 Skype、 OneDrive、 SharePoint 和 Exchange Online 的加密。
ms.openlocfilehash: 220f3060bd9581b22183bbb56e68c3ec930d0c24
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/12/2019
ms.locfileid: "38690304"
---
# <a name="office-365-encryption-for-skype-for-business-onedrive-for-business-sharepoint-online-and-exchange-online"></a>商務用 Skype、 OneDrive for Business、 SharePoint Online 和 Exchange Online 的 office 365 加密

Office 365 是安全性非常高的環境，在多個層級中提供廣泛的保護，包括：實體資料中心安全性、網路安全性、存取安全性、應用程式安全性以及資料安全性。

## <a name="skype-for-business"></a>商務用 Skype

Skype 商務客戶資料可能會儲存在檔案或已上傳的會議參與者的簡報的表單中的其餘部分。 Web 會議伺服器加密使用 AES 256 位元金鑰與客戶資料。 加密的客戶資料會儲存在檔案共用上。 使用不同的隨機產生的 256 位元金鑰加密每一筆客戶資料。 在會議中共用的客戶資料時，Web 會議伺服器會指示下載透過 HTTPS 的加密的客戶資料的會議用戶端。 用戶端中，如此才能將其解密的客戶資料，它會傳送對應的索引鍵。 Web 會議伺服器也會驗證會議用戶端之前它可讓用戶端會議客戶資料的存取權。 加入 Web 會議時, 每個會議用戶端會與會議焦點元件執行前端伺服器內透過 TLS 先建立 SIP] 對話方塊。 會議將焦點傳給會議用戶端 Web 會議伺服器所產生驗證 cookie。 會議用戶端然後連接至呈現驗證 cookie，以由伺服器進行驗證的 Web 會議伺服器。

## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 和商務用 OneDrive

在 SharePoint Online 中的所有客戶檔案都受到永遠都會侷限在單一租用戶的唯一的每個檔案機碼。 機碼會建立及管理 SharePoint Online 服務，或是使用客戶金鑰時，所建立和管理客戶。 當檔案上傳時，加密 SharePoint online 內容中的上傳要求之前，先執行傳送至 Azure 儲存體。 當下載檔案後時，SharePoint Online 擷取加密的客戶根據獨特的文件識別碼及解密的客戶資料傳送給使用者前，從 Azure 儲存體資料。 Azure 儲存體有沒有解密，或甚至是識別或了解客戶資料的能力。 所有加密和解密，即會都發生的相同系統強制執行的租用戶隔離，也就是 Azure Active Directory 和 SharePoint Online 中。

在 Office 365 中的數個工作負載將資料儲存在 SharePoint Online，包括 Microsoft Teams，儲存在 SharePoint Online 和 OneDrive for Business，其儲存為使用 SharePoint Online 中的所有檔案。 儲存在 SharePoint Online 中的所有客戶資料會加密 （具有一或多個 AES 256 位元索引鍵），並分散於資料中心，如下所示。 （此加密程序的每一個步驟是的 FIPS 140-2 層級 2 進行驗證。 如需 FIPS 140-2 相容性的詳細資訊，請參閱[FIPS 140-2 相容性](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105))）。

- 每個檔案分割成一或多個區塊，視檔案大小而定。 每個區塊會使用其專屬唯一的 AES 256 位元金鑰來加密。
- 當更新檔案時，更新會處理相同的方式： 變更分割成一或多個區塊，且每個區塊加密與不同的唯一索引鍵。
- 這些區塊 – 檔案、 檔案及更新的差異部分 – 儲存為 Azure 儲存體中會隨機分散到多個 Azure 儲存體帳戶的 blob。
- 這些區塊的客戶資料的加密金鑰組是本身加密。

    - 用來加密 blob 的機碼會儲存在 SharePoint Online 內容資料庫。
    - 內容資料庫受到資料庫的存取控制及靜態加密。 加密被執行[Azure SQL 資料庫](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview)中使用[透明資料加密](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-tde)（tde） >。 （azure SQL 資料庫是在支援如關聯式資料、 JSON，空間和 XML 結構的 Microsoft Azure 中的一般用途的關聯式資料庫服務）。這些密碼會在服務層級的 SharePoint Online 中，不在租用戶層級。 （有時稱為主索引鍵） 這些密碼會儲存在不同的安全存放庫，以稱為索引鍵存放區。 TDE 提供安全性，請參閱作用中的資料庫和資料庫的備份和交易記錄檔的其餘部分。
    - 當客戶提供的選用的索引鍵時，客戶金鑰會儲存在 Azure Key Vault 和服務使用金鑰來加密租用戶金鑰，是用來加密網站金鑰，然後用來加密檔案層級索引鍵。 基本上，客戶提供按鍵時，被引進新的金鑰階層。
- 用來重新組合檔案的地圖儲存在內容資料庫以及加密金鑰，分開解密他們所需的主要金鑰。
- 每個 Azure 儲存體帳戶有其專屬唯一的認證，每個存取類型 （讀取、 寫入、 列舉和刪除）。 每個認證集都會保留在安全的金鑰存放區中，且會定期重新整理。 如前所述，有三種不同的存放區各有不同的功能：
    - 客戶資料會儲存為 Azure 儲存體中的加密 blob。 客戶資料的每個區塊的金鑰會加密並分開儲存在內容資料庫中。 本身的客戶資料會保留任何線索如何進行解密。
    - 內容資料庫是 SQL Server 資料庫。 它會保留找出與重組這些資料保留在 Azure 儲存體，以及加密這些 blob 所需的金鑰客戶資料 blob 所需的對應。 不過的索引鍵集本身是加密 （如前所述），並保留在個別的機碼存放區。
    - 索引鍵儲存區是從內容資料庫和 Azure 儲存體實體分開。 它會保留每個 Azure 儲存體容器和主要金鑰的認證以保留內容資料庫中的加密金鑰組。

每個 – Azure blob 存放區、 內容資料庫及金鑰存放區 – 這三個儲存體元件是實體分開。 保留在其中一個元件的資訊是在其本身不穩定。 沒有存取所有三個時，就無法擷取區塊按鍵，解密按鍵，以將他們設為可用、 索引鍵關聯及其對應的區塊、 解密每個區塊或重建來自其所屬的區塊文件。

BitLocker 憑證，保護資料中心裡的機器上的實體磁碟區，會儲存在安全存放庫 （SharePoint Online 秘密存放區） 所保護的伺服器陣列索引鍵。

保護每個 blob 金鑰 TDE 機碼會儲存在兩個位置：

- 安全存放庫中，以存放 BitLocker 憑證，以及受保護的伺服器陣列使用機碼。和
- 在 [安全的存放庫，由 Azure SQL Database 管理。

在 SharePoint Online 中的機密儲存及委派給每個 SharePoint Online 的伺服器陣列視需要也會保留用來存取 Azure 儲存體容器的認證。 這些認證是 Azure 儲存體 SAS 簽章，用來讀取或寫入資料，個別認證與對原則套用，讓他們自動過期每 60 天。 不同的認證用來讀取或寫入資料 （不能兩者同時） 和 SharePoint Online 的伺服器陣列不會授與列舉權限。

> [!NOTE]
> Office 365 US Government 的客戶，資料 blob 儲存在 Azure 美國政府存放區中。 此外，存取 SharePoint Online 中 Office 365 US Government 的機碼僅限於已特別遮蔽的 Office 365 人員。 Azure US Government 操作人員不需要用來加密資料 blob 的 SharePoint Online 重要存放區的存取。

如需有關 SharePoint Online 和商務用 OneDrive 中的資料加密的詳細資訊，請參閱[商務用 OneDrive 和 SharePoint Online 中的資料加密](https://technet.microsoft.com/library/dn905447.aspx)。

### <a name="list-items-in-sharepoint-online"></a>SharePoint Online 中的清單項目

清單項目是較小的區塊，建立臨機操作或的資料可以更動態 live 網站，例如建立使用者的清單中的列、 SharePoint Online 的部落格或 SharePoint Online 的 wiki 頁面內的項目中的個別文章中的客戶。 清單項目儲存在內容資料庫 (Azure SQL Database)，並且使用 TDE 保護。

## <a name="encryption-of-data-in-transit"></a>傳輸中資料的加密

在OneDrive for Business 和 SharePoint Online 中，資料進出資料中心的方式有兩種。

- **用戶端與伺服器進行通訊**，在網際網路上的商務用 OneDrive 的通訊會使用 SSL/TLS 連線。 所有 SSL 連線都是使用 2048 位元機碼加以建立。
- **資料中心之間的資料移動**到資料中心之間移動資料的主要原因是地理複寫啟用嚴重損壞修復。 例如，SQL Server交易記錄和 Blob 儲存體差異會隨時此管道流動。 若己使用私人網路傳輸資料，則系統會進一步以業界領先的加密方式保護資料。

## <a name="exchange-online"></a>Exchange Online

Exchange Online 使用 BitLocker 的所有信箱資料，而 BitLocker 組態會說明[BitLocker 加密](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)。 服務層級加密來加密在信箱層級的所有信箱資料。 

除了服務加密，Office 365 支援客戶金鑰服務加密掌握內建。 客戶金鑰是 Exchange Online 服務加密，同時也是在 Microsoft 的藍圖，Microsoft 受管理的主要選項。 此方法的加密提供加強的保護，因為它提供的伺服器管理員及解密的資料，所需的密碼編譯金鑰的區隔，也因為加密直接套用至 （中的資料不提供 BitLocker使用 BitLocker，適用於加密的邏輯磁碟區對比） 從 Exchange 伺服器複製任何客戶資料保持加密狀態。

Exchange Online 服務加密的範圍是儲存在 Exchange Online 內的靜態的客戶資料。 （商務用 Skype 幾乎所有使用者產生的內容，都儲存在使用者的 Exchange Online 信箱內與因此繼承的 Exchange Online 服務加密功能）。
