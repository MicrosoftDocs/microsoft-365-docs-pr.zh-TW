---
title: 管理授權要求
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: 瞭解如何針對您的 Microsoft 365 訂閱，複查和核准或拒絕來自使用者的授權要求。
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597649"
---
# <a name="manage-license-requests"></a>管理授權要求

> [!NOTE]
> 本文中的資訊僅適用于自助購買產品。 若要深入瞭解，請參閱[自助購買常見問題](../subscriptions/self-service-purchase-faq.md)。

如果您在組織中停用自助購買，您可以使用授權要求來管理使用者的授權要求。 當使用者嘗試為已封鎖的產品進行自助購買時，他們可以將授權要求送出給您，以供系統管理員使用。當他們提出要求時，他們可以新增也需要產品授權的其他使用者名稱。

> [!NOTE]
> 如果您封鎖使用者進行自助購買，Microsoft 不會傳送行銷電子郵件。 此外，如果他們使用產品的試用版，他們就不會看到要購買的提示。 若要深入瞭解，請參閱[管理自助購買 (系統管理) ](../subscriptions/manage-self-service-purchases-admins.md)。

若要查看及管理授權要求，系統管理員會使用**授權**頁面上的 [**要求**] 索引標籤。 清單會顯示要求的產品名稱、要求授權的人員名稱、要求的日期，以及要求的狀態。 系統管理員可以篩選清單，以顯示擱置或已完成的要求。 要求會保留30天。

## <a name="before-you-begin"></a>開始之前

您必須是全域系統管理員，才可執行本文中的工作。 如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。

## <a name="use-your-own-request-process"></a>使用您自己的要求程式

如果您的組織有其自己的要求程式，您可以改為使用它。 當使用者要求授權時，您會建立要向使用者顯示的訊息。

> [!IMPORTANT]
> 如果您使用自己的要求程式，[**要求**] 索引標籤上不會顯示任何要求。您新增郵件之前的現有要求仍會出現，直到您核准或拒絕。

1. 在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面，然後選取 [**要求**] 索引標籤。
2. 選取 [**使用現有的要求處理常式**]。
3. 在右窗格的 [**消息**] 方塊中，輸入您希望使用者在要求授權時看到的訊息。 如果您也想要包含組織原則或其他檔的連結，請在 [檔的連結] 中，輸入 URL ** (選用) ** ] 文字方塊。
4. 選取 **[儲存]**。

當您回到 [**要求**] 清單時，您會看到**您使用的是您自己的授權要求程式**的訊息。 若要對傳送給使用者的郵件進行變更，請選取 [**使用現有的要求處理常式**]。

## <a name="stop-using-your-own-request-process"></a>停止使用您自己的要求過程

1. 在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面，然後選取 [**要求**] 索引標籤。
2. 選取 [**使用現有的要求處理常式**]。
3. 在右窗格中，清除 [**使用我的組織的要求處理**程式] 核取方塊。
4. 選取 **[儲存]**。

## <a name="approve-or-deny-a-license-request"></a>核准或拒絕授權要求

1. 在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面，然後選取 [**要求**] 索引標籤。
2. 選取包含您要審閱之要求的列。 右窗格會顯示使用者要授權的產品詳細資料。
3. 若要拒絕整個要求，請選取 [**不核准**]，然後在對話方塊中，選取 [**不核准**]。
4. 若要拒絕某些使用者要求，但核准其他使用者，請依您要移除的使用者名稱選取 X。 其名稱會在 [不**指派給這些使用者**] 下移動。
5. 如果您有一個以上的產品，請在 [**選取產品**] 底下，選取您要用來指派授權的一種產品。
6. 若要拒絕使用者存取特定的應用程式和服務，請展開 [**開啟或關閉應用程式和服務**]，然後清除您要排除的應用程式和服務核取方塊。
7. 在窗格的底部，于文字方塊中輸入選用的訊息。
8. 完成後，請選取 [**核准**]。 右窗格會顯示要求的詳細資料。
9. 關閉右窗格。
    使用者會收到一封電子郵件，告知其要求已核准或遭到拒絕。

## <a name="related-content"></a>相關內容

 (篇文章) \[中指派授權給使用者](../../admin/manage/assign-licenses-to-users.md)
[將使用者移至其他訂閱](../subscriptions/move-users-different-subscription.md) (文章) \
 (文章) [購買或移除訂閱授權](buy-licenses.md)