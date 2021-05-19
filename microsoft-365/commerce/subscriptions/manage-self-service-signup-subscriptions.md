---
title: 管理自助註冊訂閱
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: 瞭解如何管理組織的免費自助註冊訂閱。
ms.date: 03/17/2021
ms.openlocfilehash: 741c9e0b45f127ffc0753b34982073f90c525d5b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536067"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>管理自助註冊訂閱

## <a name="what-are-self-service-sign-up-subscriptions"></a>何謂自助註冊訂閱？

您組織中的使用者可以使用有限數目的免費自助註冊訂閱來註冊。 使用者只能為自己註冊和使用自助註冊訂閱服務。 您可以封鎖使用者的註冊，以及刪除使用者已註冊的免費訂閱，以管理自助註冊訂閱。 如需自助註冊和可用訂閱的詳細資訊，請參閱 [在您的組織中使用自助註冊](../../admin/misc/self-service-sign-up.md)。

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>查看自助註冊訂閱清單

1. 在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。
2. 在 [ **產品** ] 索引標籤上，選取 [篩選] 圖示，然後選取 [ **自由**]。 隨即會顯示所有自助註冊訂閱清單。

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>這些訂閱與自助購買訂閱有何不同？

自助註冊訂閱是免費的，可提供更大的產品清單，而非自助購買訂閱。 當使用者註冊「自助購買」訂閱時，他們會負責支付服務。 自助購買訂閱只適用于電源平台產品 (Power BI、Power Apps 和 Power Automate) 、Project 和 Visio。 如需詳細資訊，請參閱 [自助購買常見問題](self-service-purchase-faq.yml)。

## <a name="block-users-from-signing-up"></a>封鎖使用者進行註冊

您可以搭配 **AllowAdHocSubscriptions** 參數使用 [**MsolCompanySettings 指令程式**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0)，控制使用者是否可以註冊自助註冊訂閱。 如需詳細資訊，請參閱 [如何控制自助設定？](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>刪除自助註冊訂閱

> [!IMPORTANT]
> 當您刪除自助註冊訂閱時，會封鎖所有使用者存取其資料和電子郵件，以及刪除所有的資料和電子郵件。

1. 在系統管理中心，移至 [帳單 **]**  >  [您的產品 <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">]</a> 頁面。
2. 在 [ **產品** ] 索引標籤上，選取 [篩選] 圖示，然後選取 [ **自由**]。
3. 選取您要刪除的自我服務註冊訂閱。 
4. 在 [訂閱詳細資料] 頁面上，選取 [ **訂閱和付款設定** ] 區段中的 [ **刪除訂閱**]。
5. 在 [ **刪除訂閱** ] 窗格中，選取核取方塊，然後選取 [ **刪除訂閱**]。

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>我有封鎖目錄刪除的自助註冊訂閱

個別使用者可以註冊的自助註冊產品，也會建立來賓使用者，以便在 Azure AD 目錄中進行驗證。 為了避免資料遺失，這些自助產品會封鎖目錄刪除，直到完全從目錄中刪除。 它們只可由 Azure AD 系統管理員刪除。如需詳細資訊，請參閱[Delete directory in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto)。
