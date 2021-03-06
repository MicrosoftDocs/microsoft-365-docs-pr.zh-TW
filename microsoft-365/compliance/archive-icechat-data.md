---
title: 設定連接器以封存「我的冰激淩」聊天資料
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
description: 系統管理員可以設定連接器，將「ICE 聊天」工具中的資料匯入並封存至 Microsoft 365。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，這樣您就可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 958a6dde0a4f23933ef6328719fbf43265420c7c
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2021
ms.locfileid: "52077298"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>設定連接器以封存「我的冰激淩」聊天資料

使用 Microsoft 365 規範中心內的原生連接器，從「ICE 聊天共同作業」工具匯入及封存金融服務聊天資料。 在您設定及設定連接器之後，它會連線到您組織的冰激淩聊天安全 FTP (SFTP) 網站一次，將聊天訊息的內容轉換成電子郵件格式，然後將這些專案匯入 Microsoft 365 中的信箱。

將「冰聊天」資料儲存在使用者信箱中之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、封存、審核、通訊合規性，以及 Microsoft 365 保留原則，以用於冰聊天資料。 例如，您可以使用內容搜尋來搜尋「ice 聊天」訊息，或在 Advanced eDiscovery 案例中，將包含 ICE 聊天資料的信箱與保管人產生關聯。 使用 ICE 聊天連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。

## <a name="overview-of-archiving-ice-chat-data"></a>封存的冰激淩聊天資料

下列概要說明如何使用連接器封存 Microsoft 365 中的「冰交談」資料。

![ICE 聊天封存工作流程](../media/ICEChatConnectorWorkflow.png)

1. 您的組織可以搭配「ICE 聊天」來設定冰激淩聊天的 SFTP 網站。 您也可以使用 ICE 聊天設定冰激淩聊天，將聊天訊息複製到您的 ICE 聊天網站。

2. 每24小時一次，聊天訊息會複製到您的 ICE 聊天網站。

3. 您在 Microsoft 365 合規性中心內建立的 ice 聊天連接器會每日連線到「ice 聊天 SFTP」網站，並將聊天訊息從過去24小時內傳送至 Microsoft 雲端中的安全 Azure 儲存體位置。 連接器也會將聊天室 massage 的內容轉換為電子郵件訊息格式。

4. 連接器會將聊天訊息項目匯入到特定使用者的信箱。 會在使用者信箱中建立名為「 **ICE 聊天** 」的新資料夾，並將聊天訊息項目匯入該資料夾。 連接器會使用 *SenderEmail* 和 *RecipientEmail* 屬性的值。 每個聊天訊息都包含這些內容，這些屬性會填入寄件者的電子郵件地址，以及聊天訊息的每個收件者/參與者。

   除了使用 *SenderEmail* 和 *RecipientEmail* (屬性之值的自動使用者對應，也意味著該連接器會將聊天訊息匯入寄件者的信箱，並將每個收件者) 的信箱匯入，您也可以透過上載 CSV 對應檔來定義自訂使用者對應。 這個對應檔案包含組織中每位使用者的「冰激淩聊天 *ImId* 」和對應的 Microsoft 365 信箱位址。 如果您啟用自動使用者對應，並提供自訂對應檔案，則每個聊天專案連接器都會先查看自訂對應檔案。 如果找不到與使用者的「交談」 ImId 相對應的有效 Microsoft 365 使用者帳戶，連接器會使用聊天室專案的 *SenderEmail* 和 *RecipientEmail* 屬性，將專案匯入聊天室參與者的信箱。 如果連接器在自訂對應檔或 *SenderEmail* 及 *RecipientEmail* 屬性中找不到有效的 Microsoft 365 使用者，則不會匯入該專案。

## <a name="before-you-set-up-a-connector"></a>在您設定連接器之前

封存「交談」資料所需的部分執行步驟是 Microsoft 365 外部的，必須先完成，您才能在規範中心建立連接器。

- 冰聊天會向客戶收取外部法規遵從性的費用。 您的組織應該聯繫「保密協定研討」銷售群組，以討論和簽署「保密協定聊天資料服務」合約，您可以在這裡取得 [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) 。 這種合約是在冰聊天和您的組織之間，不包含 Microsoft。 當您在步驟2中設定冰 Chat SFTP 網站之後，「ICE 聊天」會直接向您的組織提供 FTP 認證。 然後，當您在步驟3中設定連接器時，會將這些認證提供給 Microsoft。

- 在步驟3中建立連接器之前，您必須先設定 ICE 聊天 SFTP 網站。 在使用「ICE 聊天」設定 SFTP 網站之後，每日會將 ICE 聊天中的資料上傳到 SFTP 網站。 您在步驟3中建立的連接器會連接到此 SFTP 網站，並將聊天資料傳送至 Microsoft 365 信箱。 SFTP 也會加密在傳輸過程中傳送至信箱的 ICE 聊天資料。

- 若要設定 ICE 聊天連接器，您必須使用金鑰和金鑰密碼短語，以取得非常好的隱私權 (PGP) 和安全命令介面 (SSH) 。 這些機碼是用來設定冰激淩聊天 SFTP 網站，並由連接器用來連接到「ICE 聊天 SFTP」網站，將資料匯入 Microsoft 365。 PGP 金鑰是用來設定從「ICE 聊天 SFTP」網站傳輸到 Microsoft 365 的資料加密。 SSH 金鑰是用來設定安全命令介面，以在連接器連線至 ICE 聊天 SFTP 網站時，啟用安全的遠端登入。

  當您設定連接器時，可以選擇使用 Microsoft 提供的公開金鑰和金鑰密碼，也可以使用您自己的私密金鑰和密碼。 建議您使用 Microsoft 提供的公用金鑰。 不過，如果您的組織已使用私密金鑰設定了 ICE 聊天 SFTP 網站，則可以使用這些相同的私密金鑰建立連接器。

- 「ICE 聊天連接器」可以在一天內匯入200000項總計。 如果 SFTP 網站上的專案超過200000個，將不會將這些專案匯入至 Microsoft 365。

- 在步驟 3 (及下載步驟 1) 中的公開金鑰及 IP 位址的系統管理員，必須在 Exchange Online 中指派「信箱匯入匯出」角色。 在 [Microsoft 365 規範中心] 的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。

## <a name="set-up-a-connector-using-public-keys"></a>使用公開金鑰設定連接器

本節中的步驟將告訴您如何使用適用于極佳隱私權 (PGP) 和安全命令介面 (SSH) 的公開金鑰來設定 ICE 聊天連接器。

### <a name="step-1-obtain-pgp-and-ssh-public-keys"></a>步驟1：取得 PGP 和 SSH 公開金鑰

第一步是取得正確隱私權的公開金鑰複本 (PGP) 和安全命令介面 (SSH) 。 您可以在步驟2中使用這些機碼，將「ice 聊天 SFTP」網站設定為允許您在步驟) 3 中建立的連接器 (，以連線到 SFTP 網站，並將「ICE 聊天」資料轉接至 Microsoft 365 信箱。 您也會在此步驟中取得 IP 位址，當您設定 ICE 聊天 SFTP 網站時，您可以使用此位址。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。

2. 在 [**冰激淩聊天**] 底下的 [**資料連線器**] 頁面上，按一下 [ **View**]。

3. 在 [ **ICE 聊天** ] 頁面上，按一下 [ **新增連接器**]。

4. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

5. 在 [ **新增內容來源的認證** ] 頁面上，按一下 [ **我想要使用 MICROSOFT 提供的 PGP 和 SSH 公開金鑰**]。

   ![選取使用公開金鑰的選項](../media/ICEChatPublicKeysOption.png)

6. 在 [步驟 1] 下，按一下 [ **下載 SSH 金鑰**]、[ **下載 PGP 金鑰**] 和 [ **下載 IP 位址** ] 連結，將每個檔案的副本儲存到本機電腦。

   ![下載公開金鑰及 IP 位址的連結](../media/ICEChatPublicKeyDownloadLinks.png)

   這些檔案包含下列專案，可用來設定步驟2中的 ICE 聊天 SFTP 網站：

   - PGP 公開金鑰：此機碼是用來設定從「ICE 聊天 SFTP」網站傳輸到 Microsoft 365 的資料加密。

   - SSH 公開金鑰：此機碼用於設定安全的 SSH，以在連接器連線至 ICE 聊天 SFTP 網站時，啟用安全的遠端登入。

   - IP 位址：「ICE 聊天 SFTP」網站已設定為只接受來自此 IP 位址的連線要求，該要求是由您在步驟3中建立的 ICE 聊天連接器所使用。

7. 按一下 [ **取消** ] 關閉嚮導。 您會回到步驟3中的這個嚮導，以建立連接器。

### <a name="step-2-configure-the-ice-chat-sftp-site"></a>步驟2：設定 ICE 聊天 SFTP 網站

下一個步驟是使用您在步驟1中取得的 PGP 和 SSH 公開金鑰及 IP 位址，來設定用於 ICE 聊天室網站的 PGP 加密和 SSH 驗證。 這可讓您在步驟3中建立的 ICE 聊天連接器連線到「ICE 聊天 SFTP」網站，並將「冰交談」資料轉接至 Microsoft 365。 您必須使用 [ICE 聊天] 客戶支援來設定您的冰激淩聊天網站。

### <a name="step-3-create-an-ice-chat-connector"></a>步驟3：建立 ICE 聊天連接器

最後一個步驟是在 Microsoft 365 規範中心建立 ICE 聊天連接器。 連接器會使用您提供的資訊來連線至「ICE 聊天 SFTP」網站，並將交談郵件轉接至 Microsoft 365 中對應的使用者信箱方塊。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。

2. 在 [**冰激淩聊天**] 底下的 [**資料連線器**] 頁面上，按一下 [ **View**]。

3. 在 [ **ICE 聊天** ] 頁面上，按一下 [ **新增連接器**]。

4. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

5. 在 [ **新增內容來源的認證** ] 頁面上，按一下 [ **我想要使用 PGP 和 SSH 公開金鑰**]。

6. 在 [步驟 3] 底下的下列方塊中，輸入必要的資訊，然後按一下 [ **驗證** 連線]。

   - **確認程式碼：** 您的組織的識別碼，用來做為 ICE 聊天 SFTP 網站的使用者名稱。

   - **密碼：** 您的 ICE 聊天 SFTP 網站的密碼。

   - **SFTP URL:** 「冰聊天 SFTP」網站的 URL (例如， `sftp.theice.com`) 。 您也可以使用此值的 IP 位址。

   - **SFTP 埠：** ICE 聊天 SFTP 網站的埠號碼。 連接器會使用此埠連接到 SFTP 網站。

7. 成功驗證成功後，請按 **[下一步]**。

8. 在 [將 **外部使用者對應至 Microsoft 365 使用者**] 頁面上，啟用 [自動使用者對應]，並視需要提供自訂使用者對應。 您可以在此頁面上下載使用者對應的 CSV 檔案複本。 您可以將使用者對應新增至檔案，然後將其上傳。

   > [!NOTE]
   > 如先前所述，自訂對應檔 CSV 檔案包含每位使用者的「ICE 聊天 imid」和對應的 Microsoft 365 信箱位址。 如果您啟用自動使用者對應，並提供每個聊天室專案的自訂對應，連接器會先查看自訂對應檔案。 如果找不到與使用者的「交談」 imid 相對應的有效 Microsoft 365 使用者，連接器會將該專案匯入至聊天室專案的 *SenderEmail* 和 *RecipientEmail* 屬性中所指定之使用者的信箱。 如果連接器沒有透過自動或自訂使用者對應找到有效的 Microsoft 365 使用者，則不會匯入該專案。

9. 按 **[下一步]**，複查您的設定，然後按一下 **[完成]** 以建立連接器。

10. 移至 [ **資料連線器** ] 頁面，查看新連接器的匯入程式的進度。

## <a name="set-up-a-connector-using-private-keys"></a>使用私密金鑰設定連接器

本節中的步驟說明如何使用 PGP 和 SSH 私密金鑰設定 ICE 聊天連接器。 此連接器設定選項適用于已使用私密金鑰設定冰聊天 SFTP 網站的組織。

### <a name="step-1-obtain-an-ip-address-to-configure-the-ice-chat-sftp-site"></a>步驟1：取得 IP 位址以設定 ICE 聊天 SFTP 網站

如果您的組織已使用 PGP 和 SSH 私密金鑰來設定 ICE 聊天室網站，則您必須取得 IP 位址，並提供給「ICE 聊天客戶支援」。 必須將「ICE 聊天 SFTP」網站設定為接受來自此 IP 位址的連線要求。 「ICE 聊天連接器」會使用相同的 IP 位址來連線到 SFTP 網站，並將「ICE 聊天」資料轉接至 Microsoft 365。

若要取得 IP 位址：

1. 移至 <https://compliance.microsoft.com> 並按一下左側導覽中的 [ **資料連線器** ]。

2. 在 [**冰激淩聊天**] 底下的 [**資料連線器**] 頁面上，按一下 [ **View**]。

3. 在 [ **ICE 聊天** 產品描述] 頁面上，按一下 [**新增連接器**]

4. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

5. 在 [ **新增內容來源的認證** ] 頁面上，按一下 [ **我想要使用 PGP 和 SSH 私密金鑰**]。

   ![選取使用私密金鑰的選項](../media/ICEChatPrivateKeysOption.png)

6. 在 [步驟 1] 底下，按一下 [ **下載 ip 位址** ]，將 ip 位址檔案的副本儲存到本機電腦。

   ![下載 IP 位址](../media/ICEChatConnectorIPAddress.png)

7. 按一下 [ **取消** ] 關閉嚮導。 您會回到步驟2中的這個嚮導，以建立連接器。

您必須使用 ICE 聊天客戶支援，設定您的 ICE 聊天 SFTP 網站，以接受來自此 IP 位址的連線要求。

### <a name="step-2-create-an-ice-chat-connector"></a>步驟2：建立 ICE 聊天連接器

設定您的 ICE 聊天 SFTP 網站後，下一步是在 Microsoft 365 規範中心建立 ICE 聊天連接器。 連接器會使用您提供的資訊來連線至「ICE 聊天 SFTP」網站，並將電子郵件傳送至 Microsoft 365 中對應的使用者信箱方塊。 若要完成此步驟，請務必具有您用來設定您的冰激淩聊天 SFTP 網站之相同私密金鑰和金鑰密碼的副本。

1. 移至 <https://compliance.microsoft.com> 並按一下左側導覽中的 [ **資料連線器** ]。

2. 在 [**冰激淩聊天**] 底下的 [**資料連線器**] 頁面上，按一下 [ **View**]。

3. 在 [ **ICE 聊天** 產品描述] 頁面上，按一下 [**新增連接器**]

4. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

5. 在 [ **新增內容來源的認證** ] 頁面上，按一下 [ **我想要使用 PGP 和 SSH 私密金鑰**]。

6. 在 [步驟 3] 底下的下列方塊中，輸入必要的資訊，然後按一下 [ **驗證** 連線]。

      - **名稱：** 連接器的名稱。 它在您的組織中必須是唯一的。

      - **確認程式碼：** 組織的識別碼，用來做為冰激淩的「聊天 SFTP」網站的使用者名稱。

      - **密碼：** 組織的冰激淩聊天網站的密碼。

      - **SFTP URL:** 「冰聊天 SFTP」網站的 URL (例如， `sftp.theice.com`) 。 您也可以使用此值的 IP 位址。

      - **SFTP 埠：** ICE 聊天 SFTP 網站的埠號碼。 連接器會使用此埠連接到 SFTP 網站。

      - **PGP 私密金鑰：** 冰激淩聊天室網站的 PGP 私密金鑰。 請務必加入整個私密金鑰值，包括按鍵區塊的開始和結束行。

      - **PGP 金鑰複雜密碼：** PGP 私密金鑰的複雜密碼。

      - **SSH 私密金鑰：** ICE 聊天室網站的 SSH 私密金鑰。 請務必加入整個私密金鑰值，包括按鍵區塊的開始和結束行。

      - **SSH 金鑰密碼短語：** SSH 私密金鑰的複雜密碼。

7. 成功驗證成功後，請按 **[下一步]**。

8. 在 [將 **ICE 聊天使用者 Microsoft 365 使用者**] 頁面上，啟用 [自動使用者對應]，並視需要提供自訂使用者對應。

   > [!NOTE]
   > 如先前所述，自訂對應檔 CSV 檔案包含每位使用者的「ICE 聊天 imid」和對應的 Microsoft 365 信箱位址。 如果您啟用自動使用者對應，並提供每個聊天室專案的自訂對應，連接器會先查看自訂對應檔案。 如果找不到與使用者的「交談」 imid 相對應的有效 Microsoft 365 使用者，連接器會將該專案匯入至聊天室專案的 *SenderEmail* 和 *RecipientEmail* 屬性中所指定之使用者的信箱。 如果連接器沒有透過自動或自訂使用者對應找到有效的 Microsoft 365 使用者，則不會匯入該專案。

9. 按 **[下一步]**，複查您的設定，然後按一下 **[完成]** 以建立連接器。

10. 移至 [ **資料連線器** ] 頁面，查看新連接器的匯入程式的進度。 按一下連接線以顯示飛出頁面，該頁面包含連接器的相關資訊。
