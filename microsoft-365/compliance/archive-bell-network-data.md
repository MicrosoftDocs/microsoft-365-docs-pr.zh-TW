---
title: 設定連接器以封存鈴聲簡訊/MMS 網路資料
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
description: 系統管理員可以設定 TeleMessage 連接器，以匯入及封存來自電鈴網路的簡訊和 MMS 資料。 這可讓您在 Microsoft 365 中封存協力廠商資料來源的資料，這樣您就可以使用法規遵從性功能（例如法律封存、內容搜尋及保留原則）來管理組織的協力廠商資料。
ms.openlocfilehash: 7cfdb4556c19261b7e377df72ebe96b9cf20c992
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822211"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>設定連接器以進行封存鈴聲網路資料

使用 Microsoft 365 規範中心內的 TeleMessage 連接器，匯入及封存短消息服務 (簡訊) 及多媒體郵件服務 (彩信) 來自電鈴網路的郵件。 在您設定及設定連接器之後，它每天會連線到您組織的震鈴網路一次，然後將簡訊和 MMS 郵件匯入 Microsoft 365 中的信箱。

簡訊和 MMS 郵件儲存在使用者信箱之後，您可以套用 Microsoft 365 規範功能（例如訴訟暫止、內容搜尋）和 Microsoft 365 保留原則，以震鈴網路資料。 例如，您可以使用內容搜尋來搜尋鈴聲網路簡訊/MMS，或將包含電鈴網路連接器資料的信箱與 Advanced eDiscovery 案例中的系統管理員相關聯。 在 Microsoft 365 中使用震鈴網路連接器匯入和封存資料，可協助您的組織遵守政府和法規原則。

## <a name="overview-of-archiving-bell-network-data"></a>封存鈴聲網路資料的概覽

下列概要說明如何使用連接器封存 Microsoft 365 中的震鈴網路資料。

![鈴聲網路封存工作流程](../media/BellNetworkConnectorWorkflow.png)

1. 您的組織與 TeleMessage 和電鈴搭配使用，以設定電鈴網路連接器。 如需詳細資訊，請參閱 [鈴聲網路存檔](https://www.telemessage.com/office365-activation-for-bell-network-archiver)器。

2. 從組織的鈴聲網路中簡訊和 MMS 郵件會複製到 TeleMessage 網站。

3. 您在 Microsoft 365 規範中心建立的電鈴網路連接器每天會連線至 TeleMessage 網站，並將過去24小時的簡訊和 MMS 郵件傳送至 Microsoft 雲端中的安全 Azure 儲存體位置。 連接器也會將簡訊和 MMS 郵件的內容轉換成電子郵件訊息格式。

4. 連接器會將行動通訊專案匯入至特定使用者的信箱。 在特定使用者的信箱中建立一個名為 **電鈴簡訊** 的新資料夾，並將這些專案匯入該資料夾。 連接器會使用 *使用者的電子郵件地址* 屬性值來進行對應。 每個簡訊和彩信都包含此內容，該屬性會填入郵件每一位參與者的電子郵件地址。

   除了使用 *使用者之電子郵件地址* 屬性值的自動使用者對應，您也可以透過上載 CSV 對應檔來定義自訂對應。 此對應檔包含組織中使用者的行動電話號碼和對應的 Microsoft 365 電子郵件地址。 如果您為每個電鈴網路專案啟用自動使用者對應及自訂對應，連接器會先查看自訂對應檔案。 如果找不到有效的 Microsoft 365 使用者與使用者的行動電話號碼對應，連接器會使用嘗試匯入之專案的電子郵件地址屬性值。 如果連接器在自訂對應檔或 [電鈴網路專案] 的 [電子郵件地址] 屬性中找不到有效的 Microsoft 365 使用者，則不會匯入該專案。

## <a name="before-you-set-up-a-connector"></a>在您設定連接器之前

封存震鈴網路資料所需的部分執行步驟是 Microsoft 365 外部的，必須先完成，您才能在規範中心建立連接器。

- [從 TeleMessage 定購電鈴網路歸檔服務](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/)，並取得組織的有效管理帳戶。 當您在規範中心建立連接器時，您必須登入此帳戶。

- 取得您的鈴聲網路帳戶和計費連絡人詳細資料，以便您可以填寫 TeleMessage 上架表單，並從電鈴訂購郵件封存服務。

- 在 TeleMessage 帳戶中，註冊所有需要電鈴簡訊/MMS 網路封存的使用者。 註冊使用者時，請務必使用與其 Microsoft 365 帳戶相同的電子郵件地址。

- 您的員工在鈴行動網路上必須擁有公司擁有和公司的行動電話。 在 Microsoft 365 中封存郵件無法供員工擁有，或「 (BYOD) 裝置使用您自己的裝置。

- 建立電鈴網路連接器的使用者，必須在 Exchange Online 中指派「信箱匯入匯出」角色。 在 [Microsoft 365 規範中心] 的 [**資料連線器**] 頁面中新增連接器時，這是必要的。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。

- 您可以在 Microsoft 365 美國政府雲端的 GCC 環境中使用此資料連線器。 協力廠商應用程式和服務可能會涉及在 Microsoft 365 基礎結構以外的協力廠商系統上儲存、傳送和處理組織的客戶資料，因此不會受到 Microsoft 365 法規遵從性和資料保護承諾。 Microsoft 沒有任何表示使用此產品連接至協力廠商應用程式，表示協力廠商應用程式 FEDRAMP 相容性。

## <a name="create-a-bell-network-connector"></a>建立電鈴網路連接器

最後一個步驟是在 Microsoft 365 規範中心建立電鈴網路連接器。 連接器會使用您提供的資訊來連線至 TeleMessage 網站，並將簡訊/MMS 郵件傳送至 Microsoft 365 中對應的使用者信箱方塊。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然後按一下 [**資料連線器**  >  **鈴聲] 簡訊/MMS 網路** 記錄。

2. 在 [**鈴聲網路** 產品描述] 頁面上，按一下 [**新增連接器**]

3. 在 [ **服務條款** ] 頁面上，按一下 [ **接受**]。

4. 在 [ **登入 TeleMessage** ] 頁面的 [步驟 3] 下，于下列方塊中輸入必要的資訊，然後按 **[下一步]**。

   - 使用者 **名稱：** 您的 TeleMessage 使用者名稱。

   - **密碼：** 您的 TeleMessage 密碼。

5. 建立連接器之後，您可以關閉快顯視窗，然後移至下一個頁面。

6. 在 [ **使用者對應** ] 頁面上，啟用自動使用者對應。 若要啟用自訂對應，請上傳包含使用者對應資訊的 CSV 檔案，然後按 **[下一步]**。

7. 請複查您的設定，然後按一下 **[完成]** 以建立連接器。

8. 移至「規範中心」的 [**資料連線器**] 頁面上的 [**連接器**] 索引標籤，以查看新連接器的匯入程式的處理進度。

## <a name="known-issues"></a>已知問題

- 此時，我們不支援匯入大於 10 MB 的附件或專案。 稍後將提供對較大專案的支援。
