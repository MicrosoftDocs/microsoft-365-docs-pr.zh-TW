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
ROBOTS: NOINDEX, NOFOLLOW
description: 系統管理員可以設定連接器，將具有文字分隔的資料從 Globanet 匯入 Microsoft 365。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，因此您可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 989c0a657d9a30156e5991d5b09e389c0b044332
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47361858"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data-preview"></a>設定連接器以封存以文字分隔的資料 (預覽) 

使用 Microsoft 365 規範中心內的 Globanet 連接器，將以文字分隔的資料匯入至您的 Microsoft 365 組織中的使用者信箱，並將其封存。 [Globanet](https://globanet.com/merge1/) 提供文字分隔的連接器，可設定為定期從協力廠商資料來源捕獲專案 () 並將這些專案匯入至 Microsoft 365。 連接器會將內容從文字分隔的資料來源轉換為電子郵件訊息格式，然後將這些專案匯入至 Microsoft 365 中的使用者信箱。

以文字分隔的資料儲存在使用者信箱中之後，您可以套用 Microsoft 365 合規性功能，例如訴訟暫止、eDiscovery、保留原則和保留標籤，以及通訊法規遵從性。 在 Microsoft 365 中使用「縮放會議連接器」匯入和封存資料，可協助您的組織遵守政府和法規原則。

封存後，文字分隔來源通訊便可保留、受到法規遵從性的管制，並針對 eDiscovery 和內部資訊控管加以檢索。

## <a name="overview-of-archiving-the-text-delimited-source"></a>封存文字分隔的來源簡介

下列概要說明使用連接器封存 Microsoft 365 中的文字分隔來源資訊的程式。

![以文字分隔之資料的封存工作流程](../media/TextDelimitedConnectorWorkflow.png)

1. 您的組織可以搭配文字分隔的來源，設定及設定文字分隔的網站。

2. 每隔24小時，就會將從文字分隔之來源的聊天訊息複製到 Globanet Merge1 網站。 連接器也會將內容轉換成電子郵件訊息格式。

3. 您在 Microsoft 365 規範中心建立的文字分隔連接器，會每天連線到 Globanet Merge1 網站，並將郵件傳輸至 Microsoft 雲端中的安全 Azure 存放位置。

4. 連接器會使用 [步驟 3] 中所述之自動使用者對應的 *電子郵件* 屬性值，將已轉換的訊息項目匯入特定使用者的信箱。 會在使用者信箱中建立名為 **文字分隔** 的收件匣資料夾中的新子資料夾，訊息項目將會匯入到該資料夾中。 連接器會使用 *Email* 屬性的值來執行此動作。 每封郵件都包含此內容，它會填入郵件每一位參與者的電子郵件地址。

## <a name="before-you-begin"></a>在您開始之前

- 透過接受以文字分隔之連接線的條款及條件來建立 Globanet Merge1 帳戶。 若要這麼做，請與 [Globanet 客戶支援](https://globanet.com/contact-us)部門聯繫。 當您在步驟1中建立連接器時，您必須登入此帳戶。

- 在步驟1中建立以文字分隔的連接器 (並在步驟 3) 中完成的使用者，必須將其指派給 Exchange Online 中的信箱匯入匯出角色。 在 Microsoft 365 規範中心的 [ **資料連線器** ] 頁面上新增連接器時，此角色是必要的。 根據預設，此角色不會指派給 Exchange Online 中的任何角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [ [建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 或 [修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) ] 區段。

## <a name="step-1-set-up-the-text-delimited-connector"></a>步驟1：設定以文字分隔的連接線

第一步是存取 Microsoft 365 規範中心內的 **資料連線器** 頁面，並為以文字分隔的資料建立連接器。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [**資料連線器**]  >  **文字分隔**。

2. 在 [ **文字分隔** 的產品描述] 頁面上，按一下 [ **新增連接器**]。

3. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

4. 輸入識別連接器的唯一名稱，然後按 **[下一步]**。

5. 登入您的 Merge1 帳戶以設定連接器。

## <a name="step-2-configure-the-text-delimited-connector-on-the-globanet-merge1-site"></a>步驟2：在 Globanet Merge1 網站上設定以文字分隔的連接器

第二個步驟是在 Merge1 網站中設定文字分隔的連接器。 如需設定 Globanet Merge1 網站中以文字分隔的連接器的詳細資訊，請參閱 [Merge1 Third-Party Connector User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Text-Delimited%20User%20Guide%20.pdf)。

在您按一下 **[儲存] & 完成**之後，您會傳回 Microsoft 365 規範中心至 [連接器] 嚮導的 [ **使用者對應** ] 頁面。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>步驟3：對應使用者並完成連接器設定

若要在 Microsoft 365 規範中心內對應使用者並完成連接器設定，請遵循下列步驟：

1. 在 [將 **外部使用者對應至 Microsoft 365 使用者** ] 頁面上，啟用自動使用者對應。 文字分隔的來源專案會包含一個名為「 *電子郵件*」的屬性，其中包含組織中使用者的電子郵件地址。 如果連接器可以將此位址與 Microsoft 365 使用者產生關聯，這些專案就會匯入該使用者的信箱。

2. 在 [系統 **管理員同意** ] 頁面上，按一下 [ **提供同意** ] 按鈕。 您將會重新導向至 Microsoft 網站。 按一下 [ **接受** ] 以提供同意。

   您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。 若要提供系統管理員同意，您必須使用 Microsoft 365 全域管理員的認證登入，然後接受同意要求。 如果您未以全域系統管理員身分登入，您可以移至 [此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) ，並使用全域系統管理員認證登入，以接受要求。

3. 按 **[下一步]**，複查您的設定，然後移至 [ **資料連線器** ] 頁面，以查看新連接器的匯入程式的進度。

## <a name="step-4-monitor-the-text-delimited-connector"></a>步驟4：監視以文字分隔的連接線

建立以文字分隔的連接器之後，您可以在 Microsoft 365 規範中心中查看連接器狀態。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) 並按一下左側導覽中的 [ **資料連線器** ]。

2. 按一下 [ **連接器** ] 索引標籤，然後選取以 **文字分隔** 的連接線以顯示飛出頁面，該頁面包含連接器的屬性和資訊。

3. 在 [ **連接器狀態與來源**] 底下，按一下 [ **下載記錄** ] 連結，以開啟連接器的狀態記錄 (或儲存) 。 此記錄檔包含已匯入至 Microsoft 雲端之資料的相關資訊。

## <a name="known-issues"></a>已知問題

- 此時，我們不支援匯入大於 10 MB 的附件，但較大專案的支援將于之後提供。
