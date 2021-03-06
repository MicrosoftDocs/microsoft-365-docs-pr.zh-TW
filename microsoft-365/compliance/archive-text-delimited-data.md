---
title: 設定連接器以在 Microsoft 365 中封存以文字分隔的資料
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
description: 管理員可以設定連接器，將 Veritas 的文字分隔資料匯入 Microsoft 365。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料。 封存此資料之後，您可以使用合規性功能（例如法律封存、內容搜尋及保留原則）來管理協力廠商資料。
ms.openlocfilehash: 9a8265766dd08a78c3f218710a3bc4b623f7f670
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163934"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data"></a>設定連接器以封存以文字分隔的資料

在 Microsoft 365 規範中心使用 Veritas 連接器，將以文字分隔的資料匯入並封存 Microsoft 365 組織中的使用者信箱。 Veritas 會提供以[文字分隔的連接器](https://globanet.com/text-delimited)，將其設定為定期捕獲協力廠商資料來源中的專案 () 並將這些專案匯入 Microsoft 365。 連接器會將內容從文字分隔的資料來源轉換為電子郵件訊息格式，然後將這些專案匯入 Microsoft 365 中的使用者信箱。

將文字分隔的資料儲存在使用者信箱之後，您就可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery 及保留原則和保留標籤。 在 Microsoft 365 中使用以文字分隔的資料連線器，以匯入和封存資料，可協助您的組織遵守政府和法規原則。

## <a name="overview-of-archiving-the-text-delimited-data"></a>封存以文字分隔的資料

下列概要說明使用連接器在 Microsoft 365 中封存以文字分隔之來源資訊的處理常式。

![以文字分隔之資料的封存工作流程](../media/TextDelimitedConnectorWorkflow.png)

1. 您的組織可以搭配文字分隔的來源，設定及設定文字分隔的網站。

2. 每隔24小時，就會將從文字分隔之來源的聊天訊息複製到 Veritas Merge1 網站。 連接器也會將內容轉換成電子郵件訊息格式。

3. 您在 Microsoft 365 合規性中心建立的文字分隔連接器每天會連線至 Veritas Merge1 網站，並將郵件傳輸至 Microsoft 雲端中的安全 Azure 儲存體位置。

4. 連接器會使用 [步驟 3] 中所述之自動使用者對應的 *電子郵件* 屬性值，將已轉換的訊息項目匯入特定使用者的信箱。 在使用者信箱中，會建立名為 **文字分隔** 之收件匣資料夾中的新子資料夾，然後將訊息項目匯入該資料夾。 連接器會使用 *Email* 屬性的值來決定要匯入專案的信箱。 每封郵件都包含此內容，該屬性會填入每位參與者的電子郵件地址。

## <a name="before-you-begin"></a>開始之前

- 建立 Microsoft 連接器的 Veritas Merge1 帳戶。 若要建立此帳戶，請與 [Veritas 客戶支援](https://globanet.com/ms-connectors-contact)聯繫。 當您在步驟1中建立連接器時，您會登入此帳戶。

- 在步驟1中建立以文字分隔的連接器 (，並在步驟 3) 中完成，則必須將 Exchange Online 中的信箱匯入匯出角色指派給該使用者。 在 [Microsoft 365 規範中心] 的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。 根據預設，此角色不會指派給 Exchange Online 中的角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。

## <a name="step-1-set-up-the-text-delimited-connector"></a>步驟1：設定以文字分隔的連接線

第一步是存取「Microsoft 365 規範中心」中的 [**資料連線器**] 頁面，並為以文字分隔的資料建立連接器。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**]  >  **文字分隔**。

2. 在 [ **文字分隔** 的產品描述] 頁面上，按一下 [ **新增連接器**]。

3. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

4. 輸入識別連接器的唯一名稱，然後按 **[下一步]**。

5. 登入您的 Merge1 帳戶以設定連接器。

## <a name="step-2-configure-the-text-delimited-connector-on-the-veritas-merge1-site"></a>步驟2：在 Veritas Merge1 網站上設定以文字分隔的連接器

第二個步驟是在 Merge1 網站上設定文字分隔的連接器。 如需在 Veritas Merge1 網站上設定文字分隔連接器的詳細資訊，請參閱 [Merge1 Third-Party 連接器 User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf)。

按一下 **[儲存] & 完成** 之後，就會顯示「Microsoft 365 規範中心」的 [連接器] 中的 [**使用者對應**] 頁面。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步驟3：對應使用者並完成連接器設定

若要在 Microsoft 365 規範中心內對應使用者並完成連接器設定，請遵循下列步驟：

1. 在 [將 **外部使用者對應至 Microsoft 365 使用者**] 頁面上，啟用 [自動使用者對應]。 文字分隔的來源專案會包含一個名為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。 如果連接器可以將此位址與 Microsoft 365 使用者相關聯，則會將這些專案匯入該使用者的信箱。

2. 按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。

## <a name="step-4-monitor-the-text-delimited-connector"></a>步驟4：監視以文字分隔的連接線

建立以文字分隔的連接器之後，您可以在 [Microsoft 365 規範中心] 中查看連接器狀態。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。

2. 按一下 [ **連接器** ] 索引標籤，然後選取以 **文字分隔** 的連接線以顯示飛出頁面。 此頁面包含連接器的屬性和資訊。

3. 在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。 此記錄檔包含已匯入至 Microsoft 雲端之資料的相關資訊。

## <a name="known-issues"></a>已知問題

- 此時，我們不支援匯入大於 10 MB 的附件或專案。 稍後將提供對較大專案的支援。