---
title: 設定連接器以封存 Redtail 在 Microsoft 365 中朗讀資料
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
description: 系統管理員可以設定連接器，以匯入和封存 Redtail 朗讀資料從 Globanet 至 Microsoft 365。 此連接器可讓您在 Microsoft 365 中封存協力廠商資料來源的資料。 封存此資料之後，您可以使用合規性功能（例如法律封存、內容搜尋及保留原則）來管理協力廠商資料。
ms.openlocfilehash: 546298288e69746856a1250cc4b87643dd479c91
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722964"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data-preview"></a>設定連接器以封存 Redtail 朗讀資料 (預覽) 

使用 Microsoft 365 規範中心內的 Globanet 連接器，將 Redtail 中的資料匯入並封存至您的 Microsoft 365 組織中的使用者信箱。 Globanet 為您提供了 [Redtail](https://globanet.com/redtail/) 的使用連接器，可將其設定為從您的組織的 SFTP 伺服器捕獲專案，而這些專案會從 Redtail 接收。 連接器會將內容從 Redtail 朗讀為電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的使用者信箱。

Redtail 說資料儲存在使用者信箱之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則及保留標籤。 使用 Redtail 講話連接器在 Microsoft 365 中匯入和封存資料，可協助您的組織遵守政府和法規原則。

## <a name="overview-of-archiving-the-redtail-speak-data"></a>封存 Redtail 朗讀資料

下列概要說明使用連接器封存 Microsoft 365 中資料的 Redtail 的程式。

![Redtail 朗讀資料的封存工作流程](../media/RedtailSpeakConnectorWorkflow.png)

1. 您的組織可以搭配 Redtail 講話來設定和設定 SMTP 閘道，其中每日郵件會從 Redtail 轉送到您的組織 SFTP 伺服器。

2. 每24小時一次，Redtail 會將專案複製到 Globanet Merge1 網站。 連接器也會將 Redtail 朗讀專案轉換為電子郵件訊息格式。

3. 您在 Microsoft 365 合規性中心建立的 Redtail 講話連接器每天會連線到 Globanet Merge1 網站，並將郵件傳輸至 Microsoft 雲端中的安全 Azure 存放位置。

4. 連接器會使用 [[步驟 3](#step-3-map-users-and-complete-the-connector-setup)] 中所述的自動使用者對應的 *電子郵件* 屬性值，將已轉換的 Redtail 朗讀專案給特定使用者的信箱。 在使用者信箱中建立名為 **Redtail** 的 [收件匣] 資料夾中的子資料夾，並將這些專案匯入該資料夾。 連接器會使用 *Email* 屬性的值來決定要匯入專案的信箱。 每個 Redtail 的「朗讀」專案都包含此內容，它會填入專案的每個參與者的電子郵件地址。

## <a name="before-you-begin"></a>開始之前

- 為 Microsoft connector 建立 Globanet Merge1 帳戶。 若要建立帳戶，請與 [Globanet 客戶支援](https://globanet.com/contact-us/)人員聯繫。 當您在步驟1中建立連接器時，您必須登入此帳戶。

- 在步驟中，您必須指定組織的 SFTP 伺服器。 您必須這麼做，Globanet Merge1 才能聯繫它，以收集 Redtail 透過 SFTP 來朗讀資料。

- 在步驟1中建立 Redtail 朗讀進口商 connector (，並在步驟 3) 中完成的使用者，必須指派給 Exchange Online 中的信箱匯入匯出角色。 在 Microsoft 365 規範中心的 [資料連線器] 頁面上新增連接器時，此角色是必要的。 根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。

## <a name="step-1-set-up-the-redtail-speak-connector"></a>步驟1：設定 Redtail 講話連接器

第一步是存取 Microsoft 365 規範中心內的 **資料連線器** 頁面，並為 Redtail 朗讀資料建立連接器。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 並按一下 [ **資料連線器**] &gt; **Redtail 朗讀**]。

2. 在 [ **Redtail 講話** 產品描述] 頁面上，按一下 [ **新增連接器**]。

3. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

4. 輸入識別連接器的唯一名稱，然後按 **[下一步]**。

5. 登入您的 Merge1 帳戶以設定連接器。

## <a name="step-2-configure-the-redtail-speak-connector-on-the-globanet-merge1-site"></a>步驟2：設定 Globanet Merge1 網站上的 Redtail 通話連接器

第二個步驟是設定 Merge1 網站上的 Redtail 講話連接器。 如需如何設定 Redtail 講話連接器的詳細資訊，請參閱 [Merge1 Third-Party 連接器 User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf)。

按一下 **[儲存] & 完成** 之後，就會顯示 Microsoft 365 規範中心內 [連接器] 嚮導中的 [ **使用者對應** ] 頁面。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步驟3：對應使用者並完成連接器設定

若要對應使用者並完成連接器設定，請遵循下列步驟：

1. 在 [ **對應 Redtail 說使用者至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。 [Redtail 朗讀專案] 包含名為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。 如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。

2. 按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。

## <a name="step-4-monitor-the-redtail-speak-connector"></a>步驟4：監控 Redtail 講話連接器

在您建立 Redtail 講話連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 並按一下左側導覽中的 [ **資料連線器** ]。

2. 按一下 [ **連接器** ] 索引標籤，然後選取 [ **Redtail 說** 連接器] 以顯示飛出頁面。 此頁面會顯示連接器的屬性和資訊。

3. 在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。 此記錄檔包含已匯入至 Microsoft 雲端的資料。

## <a name="known-issues"></a>已知問題

- 此時，我們不支援匯入大於 10 MB 的附件或專案。 稍後將提供對較大專案的支援。
