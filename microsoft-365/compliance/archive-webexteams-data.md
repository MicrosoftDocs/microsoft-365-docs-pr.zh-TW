---
title: 設定 Microsoft 365 中的 Webex Teams 資料的連接器
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
description: 系統管理員可以設定連接器，以在 Microsoft 365 中從 Veritas 的 Webex Teams 連接器匯入及封存資料。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 654ca53fd4cd7c6091ff74360545ba335f753ffd
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163895"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>設定連接器以封存 Webex Teams 資料

在 Microsoft 365 規範中心使用 Veritas 連接器，將資料從 Webex Teams 匯入至 Microsoft 365 組織中的使用者信箱，並將其封存。 Veritas 會提供[webex Teams](https://globanet.com/webex-teams/)連接器，可設定用來捕獲 webex Teams 通訊專案，並將其匯入 Microsoft 365。 連接器會將內容從 webex Teams （例如1:1 聊天、群組交談、通道交談及附件）從組織的 webex Teams 帳戶轉換成電子郵件格式，然後再將這些專案匯入 Microsoft 365 中的使用者信箱。

在將 Webex Teams 資料儲存在使用者信箱中之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。 使用 Webex Teams connector 在 Microsoft 365 中匯入及封存資料，可協助您的組織遵守政府和法規原則。

## <a name="overview-of-archiving-webex-teams-data"></a>封存 Webex Teams 資料的概覽

下列概要說明如何使用連接器封存 Microsoft 365 中的 Webex Teams 資料。

![Webex Teams 資料的封存工作流程](../media/WebexTeamsConnectorWorkflow.png)

1. 您的組織可以搭配 webex Teams 來設定和設定 webex Teams 網站。

2. 每24小時一次，Webex Teams 專案會複製到 Veritas Merge1 網站。 連接器也會將 Webex Teams 專案轉換成電子郵件訊息格式。

3. 您在「Microsoft 365 規範中心」中建立的 Webex Teams 連接器，會每天連線到 Veritas Merge1，然後將 Webex Teams 專案傳送至 Microsoft 雲端中的安全 Azure 儲存體位置。

4. 連接器會使用自動使用者對應的 *電子郵件* 屬性值，將專案匯入至特定使用者的信箱，如 [步驟 3](#step-3-map-users-and-complete-the-connector-setup)所述。 在使用者信箱中建立名為 **Webex Teams** [收件匣] 資料夾中的子資料夾，並將這些專案匯入該資料夾。 連接器會使用 *Email* 屬性的值來執行此動作。 每個 Webex Teams 專案都包含此屬性，其會填入專案的每個參與者的電子郵件地址。

## <a name="before-you-begin"></a>開始之前

- 建立 Microsoft 連接器的 Veritas Merge1 帳戶。 若要建立此帳戶，請與 [Veritas 客戶支援](https://globanet.com/ms-connectors-contact)聯繫。 當您在步驟1中建立連接器時，您會登入此帳戶。

- 在中建立應用程式 [https://developer.webex.com/](https://developer.webex.com) 以從 Webex Teams 帳戶提取資料。 如需建立應用程式的逐步指示，請參閱[Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf) 。

   當您建立此應用程式時，Webex 平臺會產生一組唯一的認證。 當您設定全域 Merge1 網站上的 Webex Teams 連接器時，會在步驟2中使用這些認證。

- 在步驟 1 (中建立 Webex Teams 連接器，並在步驟3中完成) 的使用者必須指派給 Exchange Online 中的信箱匯入匯出角色。 在 [Microsoft 365 規範中心] 的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。 根據預設，此角色不會指派給 Exchange Online 中的角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。

## <a name="step-1-set-up-the-webex-teams-connector"></a>步驟1：設定 Webex Teams 連接器

第一步是取得 **資料連線器** 的存取權，並設定 [Webex Teams](https://globanet.com/webex-teams/)連接器。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**  >  **Webex Teams**]。

2. 在 [ **Webex Teams** 產品描述] 頁面上，按一下 [**新增連接器**]。

3. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

4. 輸入識別連接器的唯一名稱，然後按 **[下一步]**。

5. 登入您的 Merge1 帳戶以設定連接器。

## <a name="step-2-configure-the-webex-teams-connector-on-the-veritas-merge1-site"></a>步驟2：設定 Veritas Merge1 網站上的 Webex Teams 連接器

第二個步驟是設定 Merge1 網站上的 Webex Teams 連接器。 如需如何設定 Webex Teams 連接器的詳細資訊，請參閱[Merge1 Third-Party connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)。

按一下 **[儲存] & 完成** 之後，就會顯示「Microsoft 365 規範中心」的 [連接器] 中的 [**使用者對應**] 頁面。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步驟3：對應使用者並完成連接器設定

若要在 Microsoft 365 規範中心內對應使用者並完成連接器設定，請遵循下列步驟：

1. 在 [**對應 Webex Teams 使用者來 Microsoft 365 使用者**] 頁面上，啟用自動使用者對應。 Webex Teams 專案包括稱為「*電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。 如果連接器可以將此位址與 Microsoft 365 使用者相關聯，則會將這些專案匯入該使用者的信箱。

2. 按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。

## <a name="step-4-monitor-the-webex-teams-connector"></a>步驟4：監視 Webex Teams 連接器

在您建立 Webex Teams 連接器之後，您可以在 [Microsoft 365 規範中心] 中查看連接器狀態。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。

2. 按一下 [**連接器**] 索引標籤，然後選取 **Webex Teams** connector 以顯示飛出頁面。 此頁面包含連接器的屬性和資訊。

3. 在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。 此記錄檔包含已匯入至 Microsoft 雲端之資料的相關資訊。

## <a name="known-issues"></a>已知問題

- 此時，我們不支援匯入大於 10 MB 的附件或專案。 稍後將提供對較大專案的支援。