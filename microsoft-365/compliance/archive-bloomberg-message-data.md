---
title: 設定連接器以封存 Bloomberg 郵件資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 管理員可以設定資料連線器，將 Bloomberg 郵件電子郵件工具中的資料匯入和封存至 Microsoft 365。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: cc14bd9d76e04fe3e285f63b5dce9dbb1f680794
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200226"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>設定連接器以封存 Bloomberg 郵件資料

使用 Microsoft 365 規範中心的資料連線器，從 [Bloomberg 郵件](https://www.bloomberg.com/professional/product/collaboration/) 共同作業工具匯入及封存金融服務電子郵件資料。 在您設定及設定連接器之後，它會連線到您組織的 Bloomberg secure FTP (SFTP) 網站一次，並將電子郵件專案匯入 Microsoft 365 中的信箱。

將 Bloomberg 郵件資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、內容搜尋、就地封存、審核、通訊法規遵從性，以及 Microsoft 365 保留原則，以 Bloomberg 郵件資料。 例如，您可以使用內容搜尋工具搜尋 Bloomberg 郵件電子郵件，或在高級 eDiscovery 案例中關聯包含 Bloomberg 郵件資料與保管人的信箱。 使用 Bloomberg 郵件連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。

## <a name="overview-of-archiving-bloomberg-message-data"></a>封存 Bloomberg 訊息資料的概覽

下列概要說明如何使用連接器封存 Microsoft 365 中的 Bloomberg 郵件資料。

![Bloomberg 郵件匯入和封存處理常式](../media/BloombergMessageArchiving.png)

1. 您的組織與 Bloomberg 搭配使用，以設定 Bloomberg SFTP 網站。 您也可以使用 Bloomberg 設定 Bloomberg 郵件，將電子郵件傳送至 Bloomberg SFTP 網站。

2. 每24小時一次，Bloomberg 郵件的電子郵件會複製到 Bloomberg SFTP 網站。

3. 您在 Microsoft 365 合規性中心建立的 Bloomberg 郵件連接器每天會連線至 Bloomberg SFTP 網站，並將電子郵件訊息從過去24小時傳送至 Microsoft 雲端中的 secure Azure Storage 區域。

4. 連接器會將電子郵件專案匯入特定使用者的信箱。 會在特定使用者的信箱中建立名為 BloombergMessage 的新資料夾，並將這些專案匯入該資料夾。 

   連接器會使用 CorporateEmailAddress 屬性的值來執行此動作。 每封電子郵件都包含此內容，該屬性會填入電子郵件的每個參與者的電子郵件地址。 除了使用 *CorporateEmailAddress* 屬性的值進行自動使用者對應之外，您也可以透過上載 CSV 對應檔來定義自訂對應。 此對應檔包含組織中每位使用者的 Bloomberg UUID 和對應的 Microsoft 365 信箱位址。 如果您啟用自動使用者對應，並提供自訂對應，則每個電子郵件專案連接器都會先查看自訂對應檔案。 如果找不到對應至使用者 Bloomberg UUID 的有效 Microsoft 365 使用者，連接器會使用電子郵件專案的 *CorporateEmailAddress* 屬性。 如果連接器在自訂對應檔案或電子郵件專案的 *CorporateEmailAddress* 屬性中找不到有效的 Microsoft 365 使用者，則不會匯入該專案。

## <a name="before-you-begin"></a>開始之前

封存 Bloomberg 郵件資料所需的部分執行步驟是 Microsoft 365 的外部，必須先完成，您才能在規範中心建立連接器。

- 您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。 若要同意此要求，請移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Office 365 全域管理員的認證登入，然後接受要求。 您必須先完成此步驟，才能在步驟3中成功建立 Bloomberg 郵件連接器。

- 訂閱 [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA)。 這是必要的，讓您可以登入 Bloomberg 無所不在，以存取您必須設定及設定的 Bloomberg SFTP 網站。

- 設定 Bloomberg SFTP (安全檔案傳輸通訊協定) 網站。 使用 Bloomberg 來設定 SFTP 網站後，每日會將 Bloomberg 郵件的資料上傳到 SFTP 網站。 您在步驟2中建立的連接器會連接到此 SFTP 網站，並將電子郵件資料傳送至 Microsoft 365 信箱。 在傳輸過程中，SFTP 也會加密傳送至信箱的 Bloomberg 郵件資料。

  如需 Bloomberg SFTP (也稱為 *BB-SFTP*) 的詳細資訊：

  - 請參閱 [Bloomberg 支援部門](https://www.bloomberg.com/professional/support/documentation/)的「SFTP Connectivity 標準」檔。

  - 請與 [Bloomberg 客戶支援](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)人員聯繫。

   > [!NOTE]
   > 如果您的組織已部署一個連接器，以封存立即 Bloomberg 資料，您不需要設定另一個 SFTP 網站。 您可以使用相同的 SFTP 網站來 Bloomberg 消息連接器。

- 當您使用 Bloomberg 設定 SFTP 網站後，Bloomberg 會在您回應 Bloomberg 的實施電子郵件訊息之後，為您提供一些資訊。 儲存下列資訊的複本。 您可以使用它在步驟3中設定連接器。

  - 公司的程式碼，也就是您組織的識別碼，用來登入 Bloomberg SFTP 網站。

  - Bloomberg SFTP 網站的密碼

  - Bloomberg SFTP 網站 (的 URL，例如，sftp.bloomberg.com) 。 此外，Bloomberg 也可以為 Bloomberg SFTP 網站提供對應的 IP 位址，也可以用來設定連接器。

  - Bloomberg SFTP 網站的埠號碼

- 在步驟 3 (中建立 Bloomberg 郵件連接器，並在步驟 1) 中下載公開金鑰及 IP 位址的使用者，必須在 Exchange Online 中指派「信箱匯入匯出」角色。 在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面中新增連接器時，這是必要的。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。


## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>步驟1：取得 SSH 和 PGP 公開金鑰

第一步是取得公開金鑰的副本，以取得安全命令介面 (SSH) 和非常好的隱私權 (PGP) 。 您可以在步驟2中使用這些機碼來設定 Bloomberg SFTP 網站，以允許您在步驟3中建立的連接器 () 連線到 SFTP 網站，以及將 Bloomberg 郵件電子郵件資料轉移至 Microsoft 365 信箱。 您也可以在此步驟中取得 IP 位址，當您設定 Bloomberg SFTP 網站時，您可以使用此位址。

1. 移至 [ https://compliance.microsoft.com\ ] (https://compliance.microsoft.com) ，然後按一下左導覽中的 [ **資料連線器** ]。

2. 在 [ **Bloomberg 郵件**] 底下的 [**資料連線器**] 頁面上，按一下 [ **View**]。

3. 在 [ **Bloomberg 訊息**產品描述] 頁面上，按一下 [**新增連接器**]

4. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

5. 在 [步驟 1] 底下的 [ **新增 BLOOMBERG SFTP 網站認證** ] 中，按一下 [ **下載 SSH 金鑰**]、[ **下載 PGP 金鑰**] 和 [ **下載 IP 位址** ] 連結，將每個檔案的副本儲存到本機電腦。 這些檔案包含下列專案，可用來設定步驟2中的 Bloomberg SFTP 網站：

   - SSH 公開金鑰：此機碼用來設定安全命令介面 (SSH) ，以在連接器連線至 Bloomberg SFTP 網站時，啟用安全的遠端登入。

   - PGP 公開金鑰：此機碼是用來設定從 Bloomberg SFTP 網站傳輸至 Microsoft 365 的資料加密。

   - IP 位址： Bloomberg SFTP 網站已設定為只接受來自此 IP 位址的連線要求，該要求是由您在步驟3中建立的 Bloomberg 郵件連接器所使用。

6. 按一下 [ **取消** ] 關閉嚮導。 您會回到步驟3中的這個嚮導，以建立連接器。

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>步驟2：設定 Bloomberg SFTP 網站

> [!NOTE]
> 如先前所述，如果您的組織先前已設定 Bloomberg SFTP 網站封存立即 Bloomberg 資料，您就不需要設定另一個。 當您在步驟3中建立連接器時，您可以指定相同的 SFTP 網站。

下一步是使用 SSH 和 PGP 公開金鑰和您在步驟1中取得的 IP 位址，為 Bloomberg SFTP 網站設定 SSH 驗證和 PGP 加密。 這可讓您在步驟3中建立的 Bloomberg 郵件連接器連線至 Bloomberg SFTP 網站，並將 Bloomberg 郵件資料傳輸至 Microsoft 365。 您需要與 Bloomberg 客戶支援合作，以設定 Bloomberg SFTP 網站。 請與 [Bloomberg 客戶支援](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) 部門聯繫以取得協助。

> [!IMPORTANT]
> Bloomberg 建議您將您在步驟1中下載的三個檔案附加到電子郵件訊息，並將其傳送給他們的客戶支援小組，以設定 Bloomberg SFTP 網站時使用這些檔案。

## <a name="step-3-create-a-bloomberg-message-connector"></a>步驟3：建立 Bloomberg 郵件連接器

最後一個步驟是在 Microsoft 365 規範中心建立 Bloomberg 郵件連接器。 連接器會使用您提供的資訊來連線至 Bloomberg SFTP 網站，並將電子郵件傳送至 Microsoft 365 中對應的使用者信箱方塊。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。

2. 在 [ **Bloomberg 郵件**] 底下的 [**資料連線器**] 頁面上，按一下 [ **View**]。

3. 在 [ **Bloomberg 訊息**產品描述] 頁面上，按一下 [**新增連接器**]

4. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

5. 在 [ **新增 BLOOMBERG SFTP 網站的認證** ] 頁面的 [步驟 3] 下，于下列方塊中輸入必要的資訊，然後按 **[下一步]**。

      - **確認程式碼：** 組織的識別碼，用作 Bloomberg SFTP 網站的使用者名稱。

      - **密碼：** 組織之 Bloomberg SFTP 網站的密碼。

      - **SFTP URL:** Bloomberg SFTP 網站的 URL (例如，sftp.bloomberg.com) 。

      - **SFTP 埠：** Bloomberg SFTP 網站的埠號碼。 連接器會使用此埠連接到 SFTP 網站。

6. 在 [ **使用者對應** ] 頁面上，啟用自動使用者對應，並視需要提供自訂使用者對應

7. 按 **[下一步]**，複查您的設定，然後按一下 [準備] 以建立連接器。

8. 移至 [ **資料連線器** ] 頁面，查看新連接器的匯入程式的進度。

## <a name="known-issues"></a>已知問題

- 不支援匯入 Bloomberg 郵件電子郵件至 Microsoft 365 的執行緒。 傳送給個人的個別郵件會匯入，但不會出現線上程交談中。 Microsoft 正致力於支援 Bloomberg 郵件資料連線器的後續版本中的執行緒。
