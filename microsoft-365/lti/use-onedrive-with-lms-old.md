---
title: 使用 OneDrive Learning 工具互通性
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 建立及評分工作分派、組建及 curate 課程內容，並使用新的 OneDrive Learning 工具互通性應用程式即時共同作業。
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256937"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a>在畫布上使用 Microsoft OneDrive LTI

> [!IMPORTANT]
> 部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。 Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。

## <a name="integrate-with-canvas"></a>與畫布整合

執行這項整合的人員應該是畫布的系統管理員，以及 Microsoft 365 租使用者的系統管理員。

1. 使用租使用者系統管理員帳戶登入 Microsoft Azure 入口網站。 Azure 租使用者管理員也應具有「群組管理員」角色。

    ![群組管理員高亮顯示](../media/lti-media/lti-group-admin.png)

2. 登入 Microsoft [OneDrive LTI 入口網站](https://odltiappnl.azurewebsites.net/admin)。

3. 接受完成登入的許可權。

    ![接受許可權](../media/lti-media/lti-permissions.png)

4. 選取 [ **新增 LTI 租** 使用者]。

     ![新增 LTI 租使用者](../media/lti-media/lti-add-tenant.png)

5. 從下拉式清單中選取 [ **LTI 消費者平臺** ] 做為 **畫布** 。

6. 選取 [ **畫布基本 URL** ]，然後選取 **[下一步]**。

    ![選取 [畫布] 和 [新增基礎 URL]](../media/lti-media/lti-canvas-base-url.png)

   下一個畫面會顯示您的機密欄位。

7. 從 **[開始] 中選取 [下一步]** 網頁。 檢閱者是否可以在這裡填入空白？

8. 在畫面中選取 **[下一步]** ，顯示您的機密資訊。

   Azure 入口網站的最後一個畫面會顯示新增畫布實例的後續步驟。

9. 從此畫面複製開發人員機碼。 當您建立畫布實例時，您將會使用。

## <a name="add-the-canvas-instance"></a>新增畫布實例

1. 在您的畫布實例中，取消選取 [**管理**  >  **開發人員金鑰**]。

2. 在 [**開發人員**] 機碼的下拉式清單中選擇 **LTI 機碼**。

   ![取得 LTI 開發人員金鑰](../media/lti-media/lti-developer-keys.png)

3. 在這裡貼上開發人員機碼。

     ![貼上開發人員機碼](../media/lti-media/lti-developer-keys.png)

   索引鍵是以 **關閉** 模式建立

   ![在關閉模式中建立的開發人員機碼](../media/lti-media/lti-copy-developer-keys.png)

4. 複製反白顯示的文字。
    這在 Microsoft OneDrive LTI 入口網站中充當用戶端識別碼。

5. 將文字貼 Microsoft OneDrive LTI 入口網站的 [**用戶端識別碼**] 欄位中，然後選取 **[下一步]**。

6. 選取 ****[儲存]。

7. 選取 [ **VIEW LTI 承租人**] 以查看設定。
