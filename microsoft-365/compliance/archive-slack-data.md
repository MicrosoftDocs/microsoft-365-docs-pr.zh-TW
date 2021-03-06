---
title: 在 Microsoft 365 中設定可封存時差的電子檔探索資料的連接器
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
description: 系統管理員可以設定連接器，將資料從 Veritas 時差 eDiscovery 匯入至 Microsoft 365。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料。 封存此資料之後，您可以使用合規性功能（例如法律封存、內容搜尋及保留原則）來管理協力廠商資料。
ms.openlocfilehash: 48b0a6d4d5e8f6eafaaf900aa5c773cf4f99fe72
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163954"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data"></a>設定連接器以封存可寬限電子檔探索資料

在 Microsoft 365 規範中心使用 Veritas 連接器，將協力廠商資料從社交媒體、立即訊息及檔共同作業平臺匯入並封存到您 Microsoft 365 組織中的信箱。 Veritas 會提供一個[寬延時間](https://globanet.com/slack/)連接器，設定為定期捕獲協力廠商資料來源中的專案 () 然後將這些專案匯入 Microsoft 365。 時差會從寬限 API 提取郵件和檔案，並將其轉換成電子郵件格式，然後將該專案匯入至使用者信箱。

當寬限電子檔探索資料儲存在使用者信箱之後，您就可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。 使用時差連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。

## <a name="overview-of-archiving-slack-ediscovery-data"></a>封存寬限電子檔探索資料的概覽

下列概要說明使用連接器封存 Microsoft 365 中的時差資訊的程式。

![寬限時間封存工作流程](../media/SlackConnectorWorkflow.png)

1. 您的組織使用可寬延時間設定和設定寬限網站。

2. 每隔24小時，便會將來自時差 eDiscovery 的聊天訊息複製到 Veritas Merge1 網站。 連接器也會將聊天訊息的內容轉換為電子郵件訊息格式。

3. 您在「Microsoft 365 規範中心」中建立的寬延電子檔探索連接器每天會連線至 Veritas Merge1 網站，並將聊天訊息傳送至 Microsoft 雲端中的安全 Azure 儲存體位置。

4. 連接器會使用 *電子郵件* 屬性和自動使用者對應的值，將已轉換的交談訊息項目匯入至特定使用者的信箱，如步驟3所述。 在使用者信箱中建立名為「 **寬延時間 eDiscovery** 的收件匣資料夾中的新子資料夾，並且會將聊天訊息專案匯入該資料夾。 連接器會使用 *Email* 屬性的值來決定要匯入專案的信箱。 每個聊天訊息都包含此內容，該屬性會填入聊天訊息每一位參與者的電子郵件地址。

## <a name="before-you-begin"></a>開始之前

- 建立 Microsoft 連接器的 Veritas Merge1 帳戶。 若要建立帳戶，請與 [Veritas 客戶支援](https://globanet.com/ms-connectors-contact)聯繫。 當您在步驟1中建立連接器時，您會登入此帳戶。

- 取得組織的寬限時間企業帳戶的使用者名稱和密碼。 當您設定寬限時間時，您必須在步驟2中登入此帳戶。

- 在步驟1中建立時差電子檔探索連接器的使用者 (，並在步驟 3) 中完成，必須指派 Exchange Online 中的「信箱匯入匯出」角色。 在 [Microsoft 365 規範中心] 的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。 根據預設，此角色不會指派給 Exchange Online 中的角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a>步驟1：設定時差電子檔探索連接器

第一步是存取「Microsoft 365 規範中心」中的 [**資料連線器**] 頁面，並建立用於寬限時間資料的連接器。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**  >  **時差] eDiscovery**。

2. 在 [ **時差 eDiscovery** 產品說明] 頁面上，按一下 [ **新增連接器**]。

3. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

4. 輸入識別連接器的唯一名稱，然後按 **[下一步]**。

5. 登入您的 Merge1 帳戶以設定連接器。

## <a name="step-2-configure-slack-ediscovery"></a>步驟2：設定寬延時間 eDiscovery

第二個步驟是設定 Merge1 網站上的寬延時間 eDiscovery 連接器。 如需如何在 Veritas Merge1 網站上設定時差電子檔探索連接器的詳細資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf)。

按一下 **[儲存] & 完成** 之後，就會顯示「Microsoft 365 規範中心」的 [連接器] 中的 [**使用者對應**] 頁面。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步驟3：對應使用者並完成連接器設定

1. 在 [將 **外部使用者對應至 Microsoft 365 使用者**] 頁面上，啟用 [自動使用者對應]。

   時差 eDiscovery 專案包括稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。 如果連接器可以將此位址與 Microsoft 365 使用者相關聯，則會將這些專案匯入該使用者的信箱。

2. 按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a>步驟4：監控時差電子檔探索連接器

在您建立時差電子檔探索連接器之後，您可以在 [Microsoft 365 規範中心] 中查看連接器狀態。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。

2. 按一下 [ **連接器** ] 索引標籤，然後選取 [ **時差] eDiscovery** 連接器以顯示飛出頁面。 此頁面包含連接器的屬性和資訊。

3. 在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。 此記錄檔包含已匯入至 Microsoft 雲端之資料的相關資訊。

## <a name="known-issues"></a>已知問題

- 此時，我們不支援匯入大於 10 MB 的附件或專案。 稍後將提供對較大專案的支援。