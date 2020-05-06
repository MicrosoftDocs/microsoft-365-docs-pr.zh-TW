---
title: 設定連接器來封存 LinkedIn 資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 設定連接器，將 LinkedIn 的資料匯入 Microsoft 365，這樣您就可以使用規範工具（例如法律封存、內容搜尋和保留原則）。
ms.openlocfilehash: 7d88d366ea19be7d158a04edc7d7fb11dca7bab9
ms.sourcegitcommit: e55e4747d3b838baacab8985aefc24aac245c431
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44043344"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>設定連接器來封存 LinkedIn 資料

使用 Microsoft 365 規範中心內的連接器，從 LinkedIn 公司頁面匯入及封存資料。 在您設定及設定連接器之後，它會每隔24小時連線到特定 LinkedIn 公司] 頁面的帳戶。 連接器會將張貼到公司頁面的郵件轉換為電子郵件，然後將這些專案匯入至 Microsoft 365 中的信箱。

LinkedIn 公司頁面資料儲存在信箱中之後，您可以將 Microsoft 365 規範功能（例如訴訟暫止、內容搜尋、In-Place 封存、審核和 Microsoft 365 保留原則）套用至 LinkedIn 資料。 例如，您可以使用內容搜尋來搜尋這些專案，或在高級 eDiscovery 案例中將儲存信箱與保管人建立關聯。 建立連接器，以在 Microsoft 365 中匯入和封存 LinkedIn 資料，可協助您的組織遵守政府和法規原則。

## <a name="before-you--begin"></a>開始之前

- 您的組織必須同意允許 Office 365 匯入服務存取您組織中的信箱資料。 若要同意此要求，請移至[此頁面](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)，使用 Microsoft 365 全域管理員的認證登入，然後接受要求。

- 建立 LinkedIn 公司頁面連接器的使用者，必須在 Exchange Online 中指派「信箱匯入匯出」角色。 在 Microsoft 365 規範中心的 [**資料連線器**] 頁面中新增連接器時，這是必要的。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「管理 Exchange Online 中的角色群組」一文中的 [[建立角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色群組](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)] 區段。

- 您必須具有 LinkedIn 使用者帳戶的登入認證（電子郵件地址或電話號碼和密碼），該使用者帳戶是您要封存之 LinkedIn 公司] 頁面的管理員。 當您設定連接器時，您可以使用這些認證登入 LinkedIn。

## <a name="create-a-linkedin-connector"></a>建立 LinkedIn 連接器

1. 移至<https://compliance.microsoft.com> ，然後按一下 [**資料連線器** > ]**LinkedIn 公司頁面**。

2. 在 [ **LinkedIn 公司頁面**產品] 頁面上，按一下 [**新增連接器**]。

3. 在 [**服務條款**] 頁面上，選取 [**接受**]。

4. 在 [**使用 LinkedIn 登入**] 頁面上，按一下 [以**LinkedIn 登入**]。

   隨即會顯示 [LinkedIn 登入] 頁面。

   ![LinkedIn 登入頁面](../media/LinkedInSigninPage.png)

5. 在 [LinkedIn 登入] 頁面上，輸入與您要封存之公司頁面相關聯之 LinkedIn 帳戶的電子郵件地址（或電話號碼）和密碼，然後按一下 [登**入**]。

   隨即會顯示一個嚮導頁面，其中列出所有與您登入之帳戶相關聯的 LinkedIn 公司頁面。 只可為一個公司頁面設定連接器。 如果您的組織有多個 LinkedIn 公司頁面，您必須為每個頁面建立一個連接器。

   ![隨即會顯示一個包含 LinkedIn 公司頁面清單的頁面](../media/LinkedInSelectCompanyPage.png)

6. 選取您要封存專案的公司頁面，然後按 **[下一步]**。

7. 在 [**選擇儲存位置**] 頁面上，按一下方塊，選取要匯入 LinkedIn 專案的 Microsoft 365 信箱的電子郵件地址，然後按 **[下一步]**。 將專案匯入此信箱中的 [收件匣] 資料夾。

8. 在 [**提供管理員同意**] 中，按一下 [**提供同意**]，然後依照步驟進行。 您必須是全域系統管理員，才可對您組織中的資料提供 Office 365 匯入服務的同意。

9. 按 **[下一步]** 以查看連接器設定，然後按一下 **[完成]** 以完成連接器設定。

建立連接器之後，您可以回到 [**資料連線器**] 頁面，以查看新連接器的匯入程式的進度（**如有必要，請選取 [** 重新整理] 以更新連接器清單）。 [**狀態**] 欄中的值正**等候開始**。 開始進行初始匯入程式需要長達24小時的時間。 在連接器第一次執行並匯入 LinkedIn 專案之後，連接器會每隔24小時執行一次，並匯入在前24小時內，在 LinkedIn 公司頁面上建立的任何新專案。

若要查看更多詳細資料，請選取 [**資料連線器**] 頁面上清單中的連接器以顯示飛入頁面。 在 [**狀態**] 下，顯示的日期範圍會指出建立連接器時所選取的年齡篩選。

## <a name="more-information"></a>詳細資訊

LinkedIn 項會匯入至 Microsoft 365 中儲存信箱收件匣的 LinkedIn 子資料夾。 它們會顯示為電子郵件訊息。
