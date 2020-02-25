---
title: 在 Office 365 中執行內部系統接管
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: 了解如何確認接管未受管理的租用戶，Office 365 中您電子郵件和網域擁有權
ms.openlocfilehash: e3c89e122264808e2a8631c07269ea263c87fdaa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42240359"
---
# <a name="perform-an-internal-admin-takeover-in-office-365"></a><span data-ttu-id="f4ff5-103">在 Office 365 中執行內部系統接管</span><span class="sxs-lookup"><span data-stu-id="f4ff5-103">Perform an internal admin takeover in Office 365</span></span>

 <span data-ttu-id="f4ff5-104">若您找不到所需功能，請**[檢查網域常見問題集](../setup/domains-faq.md)**。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="f4ff5-105">如果您是系統管理員，而且想要接管建立自助服務的使用者註冊受管理的租用戶，您可以將這運用內部系統接管。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="f4ff5-106">自助註冊使用 Azure AD 任何雲端服務會新增到未受管理的使用者或 「 陰影 「 Azure AD 目錄，並建立受管理的租用戶。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="f4ff5-107">未受管理的租用戶是全域系統管理員沒有目錄。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="f4ff5-108">若要判斷是否租用戶受管理或未受管理，請參閱[決定租用戶類型](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="f4ff5-109">步驟 1： 確認您的電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="f4ff5-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="f4ff5-110">如果您的租用戶中啟用自助，則使用者可以訂閱免費上的服務，例如 Power BI，自己。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="f4ff5-111">這些步驟假設自助服務使用者的訂閱已建立未受管理的租用戶，您想要接管，成為管理員]。在第一個步驟中您可以建立未受管理的租用戶，以說明系統接管路徑使用 Power BI 中的使用者內容。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="f4ff5-112">若要註冊 Power BI，移至[Power BI 網站](https://powerbi.com)，然後選取 [**開始免費** > （在 [共用對象] 方塊中 Power BI 專業人員） 的 [**開始免費試用版**。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="f4ff5-113">註冊的使用者使用之帳戶的組織的網域名稱 (例如`powerbiadmin@contoso.com`)。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="f4ff5-114">如果您的帳戶已在使用中，使用登入您目前的密碼。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="f4ff5-115">請檢查您的電子郵件**驗證碼**，並輸入程式碼來驗證您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="f4ff5-116">步驟 2： 建立新的帳戶</span><span class="sxs-lookup"><span data-stu-id="f4ff5-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="f4ff5-117">當您輸入驗證碼時，您將帶您可以在其中建立新的帳戶] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="f4ff5-118">填入您要使用的帳戶使用者名稱和密碼欄位，然後選取 [**啟動**]。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="f4ff5-119">步驟 3： 確認網域擁有權並成為系統管理員</span><span class="sxs-lookup"><span data-stu-id="f4ff5-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="f4ff5-120">**成為系統管理員**精靈會隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="f4ff5-121">如果精靈並未自動啟動，尋找 [**管理**] 磚並選取它。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="f4ff5-122">選取 [**是，我想成為系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="f4ff5-123">確認您擁有您想要接管將 TXT 記錄新增至您的網域註冊機構的網域。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="f4ff5-124">精靈會提供 TXT 記錄新增，以及提供您的註冊機構網站以及逐步指示連結。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="f4ff5-125">一旦您已經註冊機構網站新增 TXT 記錄，請回到精靈，然後選取 [**好的我已新增記錄**。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f4ff5-126">接管陰影租用戶將不會影響任何現有的資訊或服務。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="f4ff5-127">不過，如果網域中的任何使用者已經註冊需要授權的服務，系統會要求您為其作為接管系統管理員角色的一部分購買授權。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="f4ff5-128">您可以新增或移除授權，一旦完成管理安裝程序。</span><span class="sxs-lookup"><span data-stu-id="f4ff5-128">You can add or remove licenses once the admin setup process is finished.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="f4ff5-129">相關文章</span><span class="sxs-lookup"><span data-stu-id="f4ff5-129">Related articles</span></span>

<span data-ttu-id="f4ff5-130">Youtube：[接管 Power BI 和 Office 365 IT 系統管理員的 3 個步驟](https://www.youtube.com/watch?v=xt5EsrQBZZk) (英文)</span><span class="sxs-lookup"><span data-stu-id="f4ff5-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Office 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="f4ff5-131">在 Azure AD 中的系統管理員接管</span><span class="sxs-lookup"><span data-stu-id="f4ff5-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="f4ff5-132">取得 Office 365 網域的說明</span><span class="sxs-lookup"><span data-stu-id="f4ff5-132">Get help with Office 365 domains</span></span>](../get-help-with-domains/get-help-with-domains.md)

[<span data-ttu-id="f4ff5-133">組織中使用自助登</span><span class="sxs-lookup"><span data-stu-id="f4ff5-133">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="f4ff5-134">了解 Power BI 服務系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="f4ff5-134">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

