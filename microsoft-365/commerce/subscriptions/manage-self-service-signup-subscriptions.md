---
title: 管理自助註冊訂閱
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 瞭解如何管理組織的免費自助註冊訂閱。
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376302"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>管理自助註冊訂閱

## <a name="what-are-self-service-sign-up-subscriptions"></a>何謂自助註冊訂閱？

您組織中的使用者可以使用有限數目的免費自助註冊訂閱來註冊。 使用者只能為自己註冊和使用自助註冊訂閱服務。 您可以封鎖使用者的註冊，以及刪除使用者已註冊的免費訂閱，以管理自助註冊訂閱。 如需自助註冊和可用訂閱的詳細資訊，請參閱 [在您的組織中使用自助註冊](../../admin/misc/self-service-sign-up.md)。

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>查看自助註冊訂閱清單

1. 在系統管理中心，移至 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">您的產品</a> 頁面。
2. 在 [ **產品** ] 索引標籤上，選取 [篩選] 圖示，然後選取 [ **自由**]。 隨即會顯示所有自助註冊訂閱清單。

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>這些訂閱與自助購買訂閱有何不同？

自助註冊訂閱是免費的，可提供更大的產品清單，而非自助購買訂閱。 當使用者註冊「自助購買」訂閱時，他們會負責支付服務。 自助購買訂閱只適用于電源平台產品 (Power BI、Power App 及 Power) 、Project 和 Visio 的自動功能。 如需詳細資訊，請參閱 [自助購買常見問題](self-service-purchase-faq.md)。

## <a name="block-users-from-signing-up"></a>封鎖使用者進行註冊

您可以搭配 **AllowAdHocSubscriptions** 參數使用 [**MsolCompanySettings 指令程式**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true)，控制使用者是否可以註冊自助註冊訂閱。 如需詳細資訊，請參閱 [如何控制自助設定？](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>刪除自助註冊訂閱

> [!IMPORTANT]
> 當您刪除自助註冊訂閱時，會封鎖所有使用者存取其資料和電子郵件，以及刪除所有的資料和電子郵件。

1. 在系統管理中心，移至 **[帳單]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">您的產品</a> 頁面。
2. 在 [ **產品** ] 索引標籤上，選取 [篩選] 圖示，然後選取 [ **自由**]。
3. 選取您要刪除的自我服務註冊訂閱。 
4. 在 [訂閱詳細資料] 頁面上，選取 [ **訂閱和付款設定** ] 區段中的 [ **刪除訂閱**]。
5. 在 [ **刪除訂閱** ] 窗格中，選取核取方塊，然後選取 [ **刪除訂閱**]。

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>我有封鎖目錄刪除的自助註冊訂閱

個別使用者可以註冊的自助註冊產品，也會建立來賓使用者，以便在 Azure AD 目錄中進行驗證。 為了避免資料遺失，這些自助產品會封鎖目錄刪除，直到完全從目錄中刪除。 它們只可由 Azure AD 系統管理員刪除。如需詳細資訊，請參閱 [刪除 Azure Active directory 中的目錄](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)。