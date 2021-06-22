---
title: 設定在 Microsoft 365 中封存 WeChat 資料的連接器
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
description: 在 Microsoft 365 合規性中心中設定和使用連接器，以匯入及封存 Microsoft 365 中的 WeChat 資料。
ms.openlocfilehash: e610b58421c2d84402010c9a5d5ad33ec6da5b04
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054623"
---
# <a name="set-up-a-connector-to-archive-wechat-data"></a>設定連接器以封存 WeChat 資料

使用 Microsoft 365 合規性中心中的 TeleMessage 連接器，匯入及封存 WeChat 和 WeCom 通話、聊天、附件、檔案及已召回的郵件。 在您設定及設定連接器之後，它會連線到您組織的 TeleMessage 帳戶，並使用 TeleMessage WeChat 歸檔人員，匯入 Microsoft 365 中信箱的員工行動通訊。

WeChat 歸檔器連接器資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、In-Place 封存、審核、通訊相容性，以及 Microsoft 365 保留原則，以 WeChat 通訊資料。 例如，您可以使用內容搜尋來搜尋 WeChat 通訊，或將包含 WeChat 歸檔程式資料的信箱與 Advanced eDiscovery 案例中的保管人相關聯。 在 Microsoft 365 中使用 WeChat 的「歸檔器連接器」匯入和封存資料，可協助您的組織遵守公司控管管理法規和法規原則。

## <a name="overview-of-archiving-wechat-communication-data"></a>封存 WeChat 通訊資料的概覽

下列概要說明如何使用連接器封存 Microsoft 365 中 WeChat 通訊資料的處理常式。

![WeChat 歸檔器資料的封存工作流程](../media/WeChatConnectorWorkflow.png)

1. 您的組織與 TeleMessage 搭配使用，以設定 WeChat 的歸檔器連接器。

2. 您的組織的 WeChat 資料是即時複製到 TeleMessage 網站。

3. 您在 Microsoft 365 合規性中心中建立的 WeChat 歸檔區連接器每天都會連線到 TeleMessage 網站，並將電子郵件訊息從過去24小時內傳送至 Microsoft 雲端中的安全 Azure 儲存體區域。

4. 連接器會將行動通訊專案匯入特定使用者的信箱。 會在特定使用者的信箱中建立名為 WeChat 的歸檔檔，並將這些專案匯入其中。 連接器會使用 *使用者的電子郵件地址* 屬性值進行對應。 每封電子郵件都包含此內容，該屬性會填入電子郵件的每個參與者的電子郵件地址。 除了使用 *使用者之電子郵件地址* 屬性值的自動使用者對應，您也可以透過上載 CSV 對應檔來定義自訂對應。 這個對應檔案應該包含使用者的行動電話號碼，以及每位使用者對應的 Microsoft 365 信箱位址。 如果您啟用自動使用者對應，並提供自訂對應，則每個電子郵件專案連接器都會先查看自訂對應檔案。 如果找不到有效的 Microsoft 365 使用者與使用者的行動電話號碼對應，連接器會使用該電子郵件專案的使用者電子郵件地址屬性。 如果連接器沒有在自訂對應檔案或電子郵件專案的 *使用者電子郵件地址* 屬性中找到有效的 Microsoft 365 使用者，則不會匯入該專案。

## <a name="before-you-set-up-a-connector"></a>在您設定連接器之前

- 與 TeleMessage 搭配使用，以設定 WeChat 的封存連接器。 如需詳細資訊，請參閱[啟用 Microsoft 365 的 TeleMessage WeChat 歸檔](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/)器。

- 設定 Microsoft 365 的 TeleMessage 連接器，並取得有效的公司管理帳戶。 如需詳細資訊，請參閱[Order Microsoft 365 Mobile](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/)封存。

- 以使用者 Microsoft 365 帳戶所用的相同電子郵件地址，註冊 TeleMessage 帳戶中需要 WeChat 封存的所有使用者。

- 您必須在組織中使用者的行動電話上安裝 Tencent WeCom 應用程式，並加以啟動。 WeCom 應用程式可讓使用者與其他 WeChat 和 WeCom 使用者通訊和聊天。

- 在 Microsoft 365 合規性中心中建立 WeChat 的歸檔器連接器的使用者，必須在 Exchange Online 中指派「信箱匯入匯出」角色。 在 [規範中心] 的 [ **資料連線器** ] 頁面中新增連接器時，這是必要的動作。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。

- 您可以在 Microsoft 365 美國政府雲端的 GCC 環境中使用此資料連線器。 協力廠商應用程式和服務可能會涉及在 Microsoft 365 基礎結構以外的協力廠商系統上儲存、傳送和處理組織的客戶資料，因此不會受到 Microsoft 365 法規遵從性和資料保護承諾。 Microsoft 沒有任何表示使用此產品連接至協力廠商應用程式，表示協力廠商應用程式 FEDRAMP 相容性。

## <a name="create-a-wechat-archiver-connector"></a>建立 WeChat 的歸檔器連接器

請遵循本節中的步驟，在 Microsoft 365 合規性中心中建立 WeChat 的歸檔器連接器。 連接器會使用您提供的資訊來連線至 TeleMessage 網站，並將 WeChat 通訊資料傳送至 Microsoft 365 中對應的使用者信箱。

1. 移至 <https://compliance.microsoft.com> ，然後按一下 [**資料連線器**]  >  **WeChat 的歸檔** 器。

2. 在 [ **WeChat 歸檔** 器產品描述] 頁面上，按一下 [**新增連接器**]

3. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

4. 在 [ **登入 TeleMessage** ] 頁面的 [步驟 3] 下，于下列方塊中輸入必要的資訊，然後按 **[下一步]**。

    - **Username**：您的 TeleMessage 使用者名稱。

    - **密碼**：您的 TeleMessage 密碼。

5. 建立連接器之後，您可以關閉快顯視窗，移至下一個頁面。

6. 在 [ **使用者對應** ] 頁面上，啟用自動使用者對應。 您也可以上傳自訂使用者對應 CSV 檔案。

7. 按 **[下一步]**，複查您的設定，然後按一下 **[完成]** 以建立連接器。

8. 移至 [**資料連線器**] 頁面上的 [**連接器**] 索引標籤，以查看新連接器的匯入程式的進度。

## <a name="known-issues"></a>已知問題

- 此時，我們不支援匯入大於 10 MB 的附件或專案。 稍後將提供對較大專案的支援。
