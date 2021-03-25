---
title: 在 Microsoft 365 中設定連接器以封存 Cisco Jabber) （MS SQL 資料）
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
description: 系統管理員可以設定連接器，以從 Microsoft 365 的 Veritas 匯入和封存 Cisco Jabber) 資料。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料。 封存此資料之後，您可以使用合規性功能（例如法律封存、內容搜尋及保留原則）來管理協力廠商資料。
ms.openlocfilehash: 7465d1f8d80d67e2a284200cbf1628178609b3c3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164404"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data"></a>設定連接器以封存 Cisco Jabber) 資料

使用 Microsoft 365 規範中心的 Veritas 連接器，將 Cisco Jabber) 平臺的資料匯入並封存至您的 Microsoft 365 組織中的使用者信箱。 Veritas 為您提供 [Cisco jabber) ](https://globanet.com/jabber/) 連接器，可設定為從 JABBER) 的 MS SQL 資料庫捕獲專案，例如1:1 聊天訊息和群組聊天，然後將這些專案匯入至 Microsoft 365。 連接器會從 Cisco Jabber) 的 MS SQL 資料庫中檢索資料，處理它，並將使用者的 Cisco Jabber) 帳戶內容轉換成電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的使用者信箱。

Cisco Jabber) 資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。 使用 Cisco Jabber) 連接器匯入和封存 Microsoft 365 中的資料，可協助您的組織遵守政府和法規原則。

## <a name="overview-of-archiving-cisco-jabber-data"></a>封存 Cisco Jabber) 資料一覽

下列概要說明如何使用連接器封存 Microsoft 365 中的 Cisco Jabber) 資料。

![Cisco Jabber) 資料的封存工作流程](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. 您的組織與 Cisco 搭配使用，以在 MS SQL 資料庫上安裝和設定 Cisco Jabber) 。

2. 每24小時一次，Cisco Jabber) 專案會從 MS SQL 資料庫複製到 Veritas Merge1 網站。 連接器也會將聊天訊息的內容轉換成電子郵件訊息格式。

3. 您在 Microsoft 365 規範中心建立的 Cisco Jabber) 連接器每天都會連線到 Veritas Merge1 網站，並將這些專案傳送至 Microsoft 雲端中的安全 Azure 儲存位置。

4. 自動使用者對應為連接器會使用 [步驟 3](#step-3-map-users-and-complete-the-connector-setup)中所述的 *Email* 屬性值，將專案匯入特定使用者的信箱。 在使用者信箱中建立名為 **Cisco jabber)** 的 [收件匣] 資料夾中的子資料夾，並將訊息項目匯入該資料夾。 連接器會使用 *Email* 屬性的值來決定要匯入專案的信箱。 每個 Cisco Jabber) 專案都包含此屬性，它會填入每個參與者的電子郵件地址。

## <a name="before-you-begin"></a>開始之前

- 建立 Microsoft 連接器的 Veritas Merge1 帳戶。 若要建立此帳戶，請與 [Veritas 客戶支援](https://www.veritas.com/content/support/)聯繫。 當您在步驟1中建立連接器時，您會登入此帳戶。

- 在步驟1中建立連接器之前，請先設定 MS SQL 資料庫，以取回 Jabber) 專案。 當您在步驟2中設定 Cisco Jabber) 連接器時，您會指定 MS SQL 資料庫的連線設定。 如需詳細資訊，請參閱 [Merge1 Third-Party 連接器使用者指南](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)。

- 在步驟1中建立 Cisco Jabber) 連接器的使用者 (，並在步驟 3) 中完成，必須將其指派給 Exchange Online 中的信箱匯入匯出角色。 在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。 根據預設，此角色不會指派給 Exchange Online 中的角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。

## <a name="step-1-set-up-the-cisco-jabber-connector"></a>步驟1：設定 Cisco Jabber) 連接器

第一步是存取 Microsoft 365 規範中心內的 **資料連線器** ，並在 MS SQL 資料上建立用於 Cisco jabber) 的連接器。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下  >  **[microsoft SQL] 上的**[資料連線器 Cisco jabber) ]。

2. 在 [ **MS SQL 產品的 Cisco jabber)** ] 描述頁面上，按一下 [ **新增連接器**]。

3. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

4. 輸入識別連接器的唯一名稱，然後按 **[下一步]**。

5. 登入您的 Merge1 帳戶以設定連接器。

## <a name="step-2-configure-the-cisco-jabber-connector-on-the-veritas-merge1-site"></a>步驟2：設定 Veritas Merge1 site 上的 Cisco Jabber) 連接器

第二個步驟是在 Veritas Merge1 site 上，設定 MS SQL connector 上的 Cisco Jabber) 。 如需如何設定 MS SQL connector 上 Cisco Jabber) 的相關資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)。

按一下 **[儲存] & 完成** 之後，就會顯示 Microsoft 365 規範中心內 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步驟3：對應使用者並完成連接器設定

若要在 Microsoft 365 規範中心內對應使用者並完成連接器設定，請遵循下列步驟：

1. 在 [將 **MS SQL 使用者上的 Cisco Jabber) 對應至 Microsoft 365 使用者** ] 頁面上，啟用 [自動使用者對應]。 MS SQL 專案上的 Cisco Jabber) 包含一個名為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。 如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。

2. 按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>步驟4：監控 Cisco Jabber) 連接器

在 MS SQL connector 上建立 Cisco Jabber) 後，您可以在 Microsoft 365 規範中心中查看連接器狀態。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。

2. 按一下 [ **連接器** ] 索引標籤，然後選取 [ **MS SQL connector] 上的 Cisco jabber)** ，以顯示飛入頁面。 此頁面包含連接器的屬性和資訊。

3. 在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。 此記錄檔包含已匯入至 Microsoft 雲端的資料。

## <a name="known-issues"></a>已知問題

- 此時，我們不支援匯入大於 10 MB 的附件或專案。 稍後將提供對較大專案的支援。