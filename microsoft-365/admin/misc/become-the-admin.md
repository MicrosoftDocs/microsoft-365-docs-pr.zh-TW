---
title: 執行內部系統管理員接管
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: 瞭解如何驗證您的電子郵件和網域擁有權，以接管由自助使用者登錄 Microsoft 365 所建立的非管理租使用者。
ms.openlocfilehash: aa44023ffdc2b59e4db024706323c5b872566260
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635983"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="3768f-103">執行內部系統管理員接管</span><span class="sxs-lookup"><span data-stu-id="3768f-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="3768f-104">若您找不到所需功能，請 **[檢查網域常見問題集](../setup/domains-faq.yml)**。</span><span class="sxs-lookup"><span data-stu-id="3768f-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="3768f-105">如果您是系統管理員，而且想要接管自助使用者註冊所建立的非管理租使用者，您可以使用內部系統管理員接管。</span><span class="sxs-lookup"><span data-stu-id="3768f-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="3768f-106">使用 Azure AD 的任何雲端服務註冊的自助服務，會將使用者新增至未受管理或「陰影」 Azure AD 目錄，並建立未受管理的租使用者。</span><span class="sxs-lookup"><span data-stu-id="3768f-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="3768f-107">未受管理的租使用者是沒有全域管理員的目錄。</span><span class="sxs-lookup"><span data-stu-id="3768f-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="3768f-108">若要判斷承租人是否受管理或未受管理，請參閱 [決定租使用者類型](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type)。</span><span class="sxs-lookup"><span data-stu-id="3768f-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="3768f-109">步驟1：確認您的電子郵件地址</span><span class="sxs-lookup"><span data-stu-id="3768f-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="3768f-110">如果您的承租人中已啟用自助，使用者可以自行訂閱免費服務，例如 Power BI。</span><span class="sxs-lookup"><span data-stu-id="3768f-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="3768f-111">這些步驟假設自助使用者訂閱已建立您想要當作系統管理員接管的非管理租使用者。在第一個步驟中，您會在未受管理的承租人中建立使用者內容，使用 Power BI 來說明管理接管路徑。</span><span class="sxs-lookup"><span data-stu-id="3768f-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="3768f-112">若要註冊 Power BI，請移至 [Power BI 網站](https://powerbi.com)，然後選取 [與 Power BI Pro 方塊共用] 方塊中的 [**開始免費**  >  **開始免費試用版** (]) 。</span><span class="sxs-lookup"><span data-stu-id="3768f-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="3768f-113">使用組織的功能變數名稱 (，如) ，註冊使用您組織的功能變數名稱的使用者帳戶 `powerbiadmin@contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="3768f-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="3768f-114">若您的帳戶已在使用中，請使用您目前的密碼登入。</span><span class="sxs-lookup"><span data-stu-id="3768f-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="3768f-115">請檢查您的電子郵件是否有 **驗證碼** ，並輸入驗證電子郵件地址的程式碼。</span><span class="sxs-lookup"><span data-stu-id="3768f-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="3768f-116">步驟2：建立新帳戶</span><span class="sxs-lookup"><span data-stu-id="3768f-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="3768f-117">當您輸入驗證碼時，您會進入可讓您建立新帳戶的頁面。</span><span class="sxs-lookup"><span data-stu-id="3768f-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="3768f-118">在 [使用者名稱] 和 [密碼] 欄位中填入您要使用的帳戶，然後選取 [ **啟動**]。</span><span class="sxs-lookup"><span data-stu-id="3768f-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="3768f-119">步驟3：確認網域擁有權並成為系統管理員</span><span class="sxs-lookup"><span data-stu-id="3768f-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="3768f-120">隨即會開啟 [ **管理員** ] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="3768f-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="3768f-121">如果該嚮導未啟動，請尋找 [系統 **管理** ] 磚，然後選取它。</span><span class="sxs-lookup"><span data-stu-id="3768f-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="3768f-122">選取 **[是，我要成為系統管理員]**。</span><span class="sxs-lookup"><span data-stu-id="3768f-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="3768f-123">將 TXT 記錄新增至您的網域註冊機構，以確認您擁有要接管的網域。</span><span class="sxs-lookup"><span data-stu-id="3768f-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="3768f-124">嚮導將會提供您要新增的 TXT 記錄，並提供您註冊機構網站的連結，並提供逐步指示的連結。</span><span class="sxs-lookup"><span data-stu-id="3768f-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="3768f-125">將 TXT 記錄新增至註冊網站後，請回到嚮導並選取 [確定] **，我已新增記錄**。</span><span class="sxs-lookup"><span data-stu-id="3768f-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3768f-126">接管陰影租使用者不會影響任何現有的資訊或服務。</span><span class="sxs-lookup"><span data-stu-id="3768f-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="3768f-127">不過，如果網域中的任何使用者已註冊需要授權的服務，系統就會要求您購買其授權，作為接管系統管理員角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="3768f-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="3768f-128">您可以在系統管理員設定程式完成後，購買或移除授權。</span><span class="sxs-lookup"><span data-stu-id="3768f-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="3768f-129">相關內容</span><span class="sxs-lookup"><span data-stu-id="3768f-129">Related content</span></span>

<span data-ttu-id="3768f-130">YouTube：[針對 Power BI 和 Microsoft 365 (影片進行 IT 系統管理員接管的3個步驟](https://www.youtube.com/watch?v=xt5EsrQBZZk)) </span><span class="sxs-lookup"><span data-stu-id="3768f-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (video)</span></span>\
<span data-ttu-id="3768f-131">[AZURE AD 中的系統管理接管](/azure/active-directory/users-groups-roles/domains-admin-takeover) (文章) </span><span class="sxs-lookup"><span data-stu-id="3768f-131">[Admin takeover in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (article)</span></span>\
<span data-ttu-id="3768f-132">[在您的組織中使用「自助註冊](self-service-sign-up.md) 」 (文章) </span><span class="sxs-lookup"><span data-stu-id="3768f-132">[Using self-service sign up in your organization](self-service-sign-up.md) (article)</span></span>\
<span data-ttu-id="3768f-133">[瞭解 Power BI 服務系統管理員角色](/power-bi/service-admin-role) (文章) </span><span class="sxs-lookup"><span data-stu-id="3768f-133">[Understanding the Power BI service administrator role](/power-bi/service-admin-role) (article)</span></span>