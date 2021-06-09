---
title: '設定連接器以在 Microsoft 365 的 Oracle 資料上封存 Cisco Jabber) '
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
description: 瞭解如何在 Microsoft 365 規範中心內設定和使用連接器，以從 Oracle 到 Microsoft 365 中的 Cisco jabber) 匯入及封存資料。
ms.openlocfilehash: d8e1ba27c4277916614deaa042214ae592bceff2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842755"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-oracle-data-preview"></a>設定連接器以封存 Oracle 資料 (預覽中的 Cisco Jabber) ) 

在 Microsoft 365 規範中心使用 Veritas 連接器，將 Oracle 平臺上 Cisco jabber) 的資料匯入並封存至您 Microsoft 365 組織中的使用者信箱。 Veritas 會在[Oracle 連接器上提供 Cisco jabber) ](https://www.veritas.com/insights/merge1/jabber) ，以設定為定期捕獲協力廠商資料來源中的專案 () 並將這些專案匯入 Microsoft 365。 連接器會將 Oracle Jabber) 中的檔案和檔案作業、批註和共用內容等內容轉換成電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的使用者信箱。

Oracle 資料上的 Cisco jabber) 儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則及保留標籤。 使用 Oracle 連接器上的 Cisco jabber) ，在 Microsoft 365 中匯入及封存資料，可協助您的組織遵守政府和法規原則。

## <a name="overview-of-archiving-cisco-jabber-on-oracle-data"></a>Oracle 資料上封存 Cisco Jabber) 的概覽

下列概要說明如何使用連接器封存 Microsoft 365 中 Oracle 資料上的 Cisco Jabber) 。

![Oracle 資料上的 Cisco Jabber) 封存工作流程](../media/CiscoJabberOnOracleConnectorWorkflow.png)

1. 您的組織可以搭配 Oracle 的 Cisco Jabber) ，在 Oracle 網站上設定和設定 Cisco Jabber) 。

2. 每隔24小時，Oracle 專案上的 Cisco Jabber) 都會複製到 Veritas Merge1 site。 連接器也會將 Oracle 專案上的 Cisco Jabber) 轉換成電子郵件訊息格式。

3. 您在 Microsoft 365 規範中心建立的 Oracle 連接器上的 Cisco jabber) ，會每天連線到 Veritas Merge1 網站，並將 jabber) 內容傳送至 Microsoft 雲端中的安全 Azure 儲存體位置。

4. 連接器會使用 [[步驟 3](#step-3-map-users-and-complete-the-connector-setup)] 中所述之自動使用者對應的 *電子郵件* 屬性值，將轉換後的專案匯入至特定使用者的信箱。 在使用者信箱中建立名為 **Cisco jabber)** 的 [收件匣] 資料夾中的子資料夾，並將專案匯入該資料夾。 連接器會使用 *Email* 屬性的值來執行此動作。 每個 Jabber) 專案都包含此屬性，它會填入專案的每個參與者的電子郵件地址。

## <a name="before-you-begin"></a>開始之前

- 建立 Microsoft 連接器的 Merge1 帳戶。 若要這麼做，請與 [Veritas 客戶支援](https://www.veritas.com/content/support/en_US)聯繫。 當您在步驟1中建立連接器時，您必須登入此帳戶。

- 在步驟 (1 中的 Oracle 連接器上建立 Cisco Jabber) 的使用者，在步驟3中建立 Cisco，) 必須指派給 Exchange Online 中的「信箱匯入匯出」角色。 在 [Microsoft 365 規範中心] 的 [**資料連線器**] 頁面上新增連接器時，此角色是必要的。 根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。

## <a name="step-1-set-up-the-cisco-jabber-on-oracle-connector"></a>步驟1：設定 Oracle 連接器上的 Cisco Jabber) 

第一步是存取「Microsoft 365 規範中心」中的 [**資料連線器**] 頁面，並建立 jabber) 資料的連接器。

1. 移至 <https://compliance.microsoft.com> ，然後按一下 Oracle 上的 [**資料連線器**  >  **Cisco jabber)**]。

2. 在 [Oracle 產品描述] 頁面上的 **Cisco jabber)** 中，按一下 [ **新增連接器**]。

3. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

4. 輸入識別連接器的唯一名稱，然後按 **[下一步]**。

5. 登入您的 Merge1 帳戶以設定連接器。

## <a name="step-2-configure-the-cisco-jabber-on-oracle-on-the-veritas-merge1-site"></a>步驟2：在 Veritas Merge1 網站上的 Oracle 上設定 Cisco Jabber) 

第二個步驟是在 Veritas Merge1 網站上的 Oracle 連接器上設定 Cisco Jabber) 。 如需如何設定 Oracle 連接器上 Cisco Jabber) 的詳細資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf)。

按一下 **[儲存] & 完成** 之後，就會顯示「Microsoft 365 規範中心」的 [連接器] 中的 [**使用者對應**] 頁面。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步驟3：對應使用者並完成連接器設定

若要在 Microsoft 365 規範中心內對應使用者並完成連接器設定，請遵循下列步驟：

1. 在 [將 **Oracle 使用者上的 Cisco jabber) 對應至 Microsoft 365 使用者**] 頁面上，啟用 [自動使用者對應]。 Oracle 專案上的 Cisco Jabber) 包含一個名為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。 如果連接器可以將此位址與 Microsoft 365 使用者相關聯，則會將這些專案匯入該使用者的信箱。

2. 按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。

## <a name="step-4-monitor-the-cisco-jabber-on-oracle-connector"></a>步驟4：監視 Oracle 連接器上的 Cisco Jabber) 

在 Oracle 連接器上建立 Cisco jabber) 之後，您可以在 [Microsoft 365 規範中心] 中查看連接器狀態。

1. 移至 <https://compliance.microsoft.com/> 並按一下左側導覽中的 [ **資料連線器** ]。

2. 按一下 [ **連接器** ] 索引標籤，然後選取 [Oracle 連接器] **上的 Cisco jabber)** ，以顯示飛入頁面，該頁面包含連接器的屬性和資訊。

3. 在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。 此記錄檔包含已匯入至 Microsoft 雲端的資料。

## <a name="known-issues"></a>已知問題

- 此時，我們不支援匯入超過 10 MB 的附件或專案，但較大專案的支援將于之後提供。
