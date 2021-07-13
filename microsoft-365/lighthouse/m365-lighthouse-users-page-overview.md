---
title: Microsoft 365 Lighthouse使用者頁面概述
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 針對受管理的服務提供者 (MSPs) 使用 Microsoft 365 Lighthouse，瞭解使用者頁面。
ms.openlocfilehash: 795e387850bd2945c4019cbb467de87fecc15f86
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395063"
---
# <a name="microsoft-365-lighthouse-users-page-overview"></a><span data-ttu-id="92617-103">Microsoft 365 Lighthouse使用者頁面概述</span><span class="sxs-lookup"><span data-stu-id="92617-103">Microsoft 365 Lighthouse Users page overview</span></span> 

> [!NOTE]
> <span data-ttu-id="92617-104">本文所述的功能都是在預覽中進行變更，而且只有符合 [需求](m365-lighthouse-requirements.md)的合作夥伴才能使用。</span><span class="sxs-lookup"><span data-stu-id="92617-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="92617-105">如果您的組織沒有 Microsoft 365 Lighthouse，請參閱[註冊 Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md)。</span><span class="sxs-lookup"><span data-stu-id="92617-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="92617-106">Microsoft 365 Lighthouse 可讓您在不同租使用者帳戶中，選取 [**使用者**] 以開啟 [使用者] 頁面，以管理各租使用者帳戶的使用者。</span><span class="sxs-lookup"><span data-stu-id="92617-106">Microsoft 365 Lighthouse lets you manage users across tenant accounts by selecting **Users** in the left navigation pane to open the Users page.</span></span> <span data-ttu-id="92617-107">您可以從這個頁面搜尋使用者，並評估使用者帳戶的安全性狀態並採取行動。</span><span class="sxs-lookup"><span data-stu-id="92617-107">From this page, you can search for users and assess and act on the security state of your user accounts.</span></span> <span data-ttu-id="92617-108">您也可以查看深入瞭解危險的使用者，以及多重要素驗證和自助密碼重設的狀態。</span><span class="sxs-lookup"><span data-stu-id="92617-108">You can also view insights into risky users and the status of multifactor authentication and self-service password reset.</span></span>  
  
## <a name="search-users-tab"></a><span data-ttu-id="92617-109">搜尋使用者] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="92617-109">Search users tab</span></span>  
  
<span data-ttu-id="92617-110">您可以從 [搜尋使用者] 索引標籤，針對特定使用者快速搜尋各個承租人，並執行基本的使用者管理動作，例如重設帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="92617-110">From the Search users tab, you can quickly search across tenants for specific users and perform basic user management actions such as resetting an account password.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-search-users-tab.png" alt-text="[搜尋使用者] 索引標籤的螢幕擷取畫面。":::

## <a name="risky-users-tab"></a><span data-ttu-id="92617-112">危險使用者] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="92617-112">Risky users tab</span></span>

<span data-ttu-id="92617-113">[危險的使用者] 索引標籤會顯示您的承租人中已標示為危險行為的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="92617-113">The Risky Users tab shows user accounts across your tenants that have been flagged for risky behavior.</span></span> <span data-ttu-id="92617-114">選取任何使用者，以查看偵測到之風險的詳細資訊，或重設使用者的密碼或封鎖登入，以減輕風險。</span><span class="sxs-lookup"><span data-stu-id="92617-114">Select any of the users to view more information on a detected risk or to mitigate a risk by resetting a user's password or blocking sign-in.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-risky-users-tab.png" alt-text="危險使用者] 索引標籤的螢幕擷取畫面。":::

## <a name="multifactor-authentication-tab"></a><span data-ttu-id="92617-116">多重因素驗證] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="92617-116">Multifactor Authentication tab</span></span>

<span data-ttu-id="92617-117">[多重要素驗證] 索引標籤提供有關多因素驗證狀態的詳細資訊，請 (MFA) 在您的承租人中啟用。</span><span class="sxs-lookup"><span data-stu-id="92617-117">The Multifactor Authentication tab provides detailed information on the status of multifactor authentication (MFA) enablement across your tenants.</span></span> <span data-ttu-id="92617-118">選取清單中的任何租使用者，以查看該租使用者的詳細資訊，包括已設定需要 MFA 的條件式存取原則，以及哪些使用者尚未為 MFA 註冊。</span><span class="sxs-lookup"><span data-stu-id="92617-118">Select any tenant in the list to see more details for that tenant, including which Conditional Access policies requiring MFA are already configured and which users have not yet registered for MFA.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-mfa-tab.png" alt-text="多重因素驗證] 索引標籤的螢幕擷取畫面。":::

## <a name="password-reset-tab"></a><span data-ttu-id="92617-120">重設密碼] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="92617-120">Password reset tab</span></span>

<span data-ttu-id="92617-121">[密碼重設] 索引標籤會顯示在您的承租人內啟用自助密碼重設狀態的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="92617-121">The Password reset tab shows detailed information on the status of self-service password reset enablement across your tenants.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-password-reset-tab.png" alt-text="[密碼重設] 索引標籤的螢幕擷取畫面。":::

## <a name="related-content"></a><span data-ttu-id="92617-123">相關內容</span><span class="sxs-lookup"><span data-stu-id="92617-123">Related content</span></span>

<span data-ttu-id="92617-124">[Microsoft 365 Lighthouse 裝置符合性頁面概述](m365-lighthouse-device-compliance-page-overview.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="92617-124">[Microsoft 365 Lighthouse device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="92617-125">[Microsoft 365 Lighthouse 常見問題](m365-lighthouse-faq.yml) (文章) </span><span class="sxs-lookup"><span data-stu-id="92617-125">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
