---
title: 設定從 MS SQL Database 封存資料的連接器
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
description: 系統管理員可以設定從 MS SQL Database 匯入及封存資料的連接器。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料。 封存此資料之後，您可以使用合規性功能（例如法律封存、內容搜尋及保留原則）來管理協力廠商資料。
ms.openlocfilehash: 494e91085494ba027a80480faba3cfb189cbd928
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164211"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a>設定從 MS SQL Database 封存資料的連接器

在 Microsoft 365 規範中心使用 Veritas connector，匯入 MS SQL Database 中的資料，並將其封存至 Microsoft 365 組織中的使用者信箱。 Veritas 為您提供 MS SQL Database 進口商連接器，該連接器設定為使用 XML 設定檔從資料庫捕獲專案，並將這些專案匯入 Microsoft 365。 連接器會將內容從 MS SQL Database 轉換成電子郵件訊息格式，然後將這些專案匯入 Microsoft 365 中的使用者信箱。

從 MS SQL Database 儲存在使用者信箱中的內容之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則及保留標籤。 使用 MS SQL Database connector 在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。

## <a name="overview-of-archiving-the-ms-sql-data"></a>封存 MS SQL 資料的概覽

下列概要說明使用連接器在 Microsoft 365 中封存 MS SQL 資料的程式。

![MS SQL 資料的封存工作流程](../media/MSSQLDatabaseConnectorWorkflow.png)

1. 您的組織可以使用 ms SQL Database 提供者來設定和設定 ms SQL Database 網站。

2. 每24小時一次，MS SQL Database 專案會複製到 Veritas Merge1 網站。 連接器也會將此內容轉換為電子郵件訊息格式。

3. 您在「Microsoft 365 規範中心」中建立的 MS SQL Database 進口商連接器，會每天連線到 Veritas Merge1 網站，並將郵件傳輸至 Microsoft 雲端中的安全 Azure 儲存體位置。

4. 連接器會使用 [[步驟 3](#step-3-map-users-and-complete-the-connector-setup)] 中所述的自動使用者對應的 *電子郵件* 屬性值，將已轉換的 MS SQL Database 專案匯入特定使用者的信箱。 在使用者信箱中建立名為 **MS SQL Database 進口商** 的收件匣資料夾中的子資料夾，並將這些專案匯入該資料夾。 連接器會使用 *Email* 屬性的值來決定要匯入專案的信箱。 MS SQL Database 中的每個專案都包含此屬性，這個屬性會填入專案的每個參與者的電子郵件地址。

## <a name="before-you-begin"></a>開始之前

- 建立 Microsoft 連接器的 Veritas Merge1 帳戶。 若要建立帳戶，請與 [Veritas 客戶支援](https://www.veritas.com/content/support/)聯繫。 當您在步驟1中建立連接器時，您必須登入此帳戶。

- 在步驟 1 (中建立 MS SQL Database 進口商連接器，並在步驟3中完成) 必須指派給 Exchange Online 中的信箱匯入匯出角色的使用者。 在 [Microsoft 365 規範中心] 的 [資料連線器] 頁面上新增連接器時，此角色是必要的。 根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>步驟1：設定 MS SQL Database 進口商連接器

第一步是存取 Microsoft365 規範中心內的 **資料連線器** 頁面，並為 MS SQL Database 建立連接器。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然後按一下 [**資料連線器**  >  **毫秒 SQL Database 進口商**]。

2. 在 [ **MS SQL Database 進口商** 產品描述] 頁面上，按一下 [**新增連接器**]。

3. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

4. 輸入識別連接器的唯一名稱，然後按 **[下一步]**。

5. 登入您的 Merge1 帳戶以設定連接器。

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-veritas-merge1-site"></a>步驟2：在 Veritas Merge1 網站上設定 MS SQL Database 進口商 connector

第二個步驟是在 Merge1 網站上設定 MS SQL Database 進口商連接器。 如需如何設定 MS SQL Database 進口商的詳細資訊，請參閱[Merge1 Third-Party 連接器 User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf)。

按一下 **[儲存] & 完成** 之後，就會顯示「Microsoft 365 規範中心」的 [連接器] 中的 [**使用者對應**] 頁面。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步驟3：對應使用者並完成連接器設定

若要對應使用者並完成連接器設定，請遵循下列步驟：

1. 在 [**地圖 MS SQL Database 進口商使用者] 以 Microsoft 365 使用者**] 頁面上，啟用 [自動使用者對應]。 MS SQL Database 專案包括稱為「*電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。 如果連接器可以將此位址與 Microsoft 365 使用者相關聯，則會將這些專案匯入該使用者的信箱。

2. 按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>步驟4：監視 MS SQL Database 進口商連接器

在您建立 MS SQL Database 進口商連接器之後，您可以在 [Microsoft 365 規範中心] 中查看連接器狀態。

1. 移至 <https://compliance.microsoft.com/> 並按一下左側導覽中的 [ **資料連線器** ]。

2. 按一下 [**連接器**] 索引標籤，然後選取 **MS SQL Database** **進口商** connector 以顯示飛入頁面，該頁面包含連接器的屬性和資訊。

3. 在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。 此記錄檔包含已匯入至 Microsoft 雲端的資料。

## <a name="known-issues"></a>已知問題

- 此時，我們不支援匯入大於 10 MB 的附件或專案。 稍後將提供對較大專案的支援。