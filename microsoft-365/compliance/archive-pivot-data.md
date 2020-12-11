---
title: 設定在 Microsoft 365 中封存樞紐分析表的連接器
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
description: 系統管理員可以在 Microsoft 365 中設定從 Globanet 匯入及封存樞紐分析表的連接器。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 23badcb2a8d2873f03b86499ccfd4c9a96b81090
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620370"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a>設定用於封存樞紐分析表的連接器

使用 Microsoft 365 規範中心內的 Globanet 連接器，將資料從 Pivot 平臺匯入至您的 Microsoft 365 組織中的使用者信箱。 Globanet 為您提供設定成定期從協力廠商資料來源捕獲專案 (的 [Pivot](https://globanet.com/pivot/) 連接器) ，然後將這些專案匯入至 Microsoft 365。 Pivot 是一種立即訊息平臺，可與金融市場參與者共同作業。 連接器會將聊天訊息等專案從使用者的樞紐分析表轉換為電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的使用者信箱。

將樞紐分析表儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。 使用資料透視連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。

## <a name="overview-of-archiving-pivot-data"></a>封存樞紐分析表的概覽

下列概要說明如何使用連接器封存 Microsoft 365 中的樞紐分析表資料。

![樞紐分析表的封存工作流程](../media/PivotConnectorWorkflow.png)

1. 您的組織與 Pivot 搭配使用，以設定及設定資料透視來源網站。

2. 每隔24小時會將 Pivot 專案複製到 Globanet Merge1 網站。 連接器也會將資料透視專案轉換為電子郵件訊息格式。

3. 您在 Microsoft 365 規範中心建立的 Pivot 連接器會每天連線到 Globanet Merge1 網站，並將資料透視專案傳送至 Microsoft 雲端中的安全 Azure 存放位置。

4. 連接器會使用 [[步驟 3](#step-3-map-users-and-complete-the-connector-setup)] 中所述的自動使用者對應的 *電子郵件* 屬性值，將資料透視專案匯入至特定使用者的信箱。 在使用者信箱中建立名為 **Pivot** 之 [收件匣] 資料夾中的子資料夾，而且會將這些專案匯入該資料夾。 連接器會使用 *Email* 屬性的值來執行此動作。 每個 Pivot 專案都包含此屬性，其會填入專案的每個參與者的電子郵件地址。

## <a name="before-you-begin"></a>開始之前

- 為 Microsoft connector 建立 Globanet Merge1 帳戶。 若要建立此帳戶，請與 [Globanet 客戶支援](https://globanet.com/ms-connectors-contact/)人員聯繫。 當您在步驟1中建立連接器時，您會登入此帳戶。

- 在步驟1中建立 Pivot 連接器的使用者 (，並在步驟 3) 中完成，必須將其指派給 Exchange Online 中的信箱匯入匯出角色。 在 Microsoft 365 規範中心的 [資料連線器] 頁面上新增連接器時，此角色是必要的。 根據預設，此角色不會指派給 Exchange Online 中的角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。

## <a name="step-1-set-up-the-pivot-connector"></a>步驟1：設定 Pivot connector

第一步是存取 Microsoft 規範中心的 [ **資料連線器** ] 頁面，並建立樞紐分析表的連接器。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器] [資料**  >  **中心**]。

2. 在 [ **樞紐分析表** 產品描述] 頁面上，按一下 [ **新增連接器**]。

3. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

4. 輸入識別連接器的唯一名稱，然後按 **[下一步]**。

5. 登入您的 Merge1 帳戶以設定連接器。

## <a name="step-2-configure-the-pivot-connector-on-the-globanet-merge1-site"></a>步驟2：設定 Globanet Merge1 網站上的 Pivot 連接器

第二個步驟是設定 Merge1 網站上的 Pivot 連接器。 如需如何在 Globanet Merge1 網站上設定 Pivot connector 的詳細資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf)。

按一下 **[儲存] & 完成** 之後，就會顯示 Microsoft 365 規範中心內 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步驟3：對應使用者並完成連接器設定

若要對應使用者，並完成 Microsoft 356 規範中心內的連接器設定，請遵循下列步驟：

1. 在 [將 **Pivot 使用者對應至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。 [資料透視專案] 包含稱為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。 如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。

2. 按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。

## <a name="step-4-monitor-the-pivot-connector"></a>步驟4：監視 Pivot 連接器

在您建立 Pivot 連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。

2. 按一下 [ **連接器** ] 索引標籤，然後選取 [ **樞紐分析表** 連接線] 以顯示飛出頁面。 此頁面包含連接器的屬性和資訊。

3. 在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。 此記錄檔包含已匯入至 Microsoft 雲端的資料。

## <a name="known-issues"></a>已知問題

- 此時，我們不支援匯入大於 10 MB 的附件或專案。 稍後將提供對較大專案的支援。
