---
title: 開始使用應用程式控管
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 開始使用應用程式控管功能來控管您的應用程式。
ms.openlocfilehash: 58f3bab9f8c5e28ce921ab244b23c49682394795
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430705"
---
# <a name="get-started-with-app-governance-in-preview"></a><span data-ttu-id="eace2-103">開始使用應用程式控管 (預覽)</span><span class="sxs-lookup"><span data-stu-id="eace2-103">Get started with app governance (in preview)</span></span>

<span data-ttu-id="eace2-104">若要開始使用 Microsoft 雲端 App 安全性的應用程式控管附加元件：</span><span class="sxs-lookup"><span data-stu-id="eace2-104">To begin using the app governance add-on to Microsoft Cloud App Security:</span></span>

1. <span data-ttu-id="eace2-p101">確認您的帳戶具有適當的授權等級。應用程式控管是 Microsoft 雲端 App 安全性 (MCAS) 的附加元件功能，因此 MCAS 必須以獨立產品或屬於下列各種授權套件的一部分存在於您的帳戶中。</span><span class="sxs-lookup"><span data-stu-id="eace2-p101">Verify your account has the appropriate level of licensing. App governance is an add-on feature for Microsoft Cloud App Security (MCAS), and thus MCAS must be present in your account as either a standalone product or as part of the various license packages listed below.</span></span>
1. <span data-ttu-id="eace2-107">您必須具有下列其中一個系統管理員角色，才能存取入口網站中的應用程式控管頁面。</span><span class="sxs-lookup"><span data-stu-id="eace2-107">You must have one of the administrator roles listed below to access the app governance pages in the portal.</span></span>

## <a name="licensing-for-app-governance"></a><span data-ttu-id="eace2-108">應用程式控管的授權</span><span class="sxs-lookup"><span data-stu-id="eace2-108">Licensing for app governance</span></span>

<span data-ttu-id="eace2-109">開始使用應用程式控管之前，您應先確認 [Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)以及任何附加元件。</span><span class="sxs-lookup"><span data-stu-id="eace2-109">Before you get started with the app governance, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="eace2-110">若要存取並使用應用程式控管，貴組織必須具備下列其中一種訂閱或附加元件：</span><span class="sxs-lookup"><span data-stu-id="eace2-110">To access and use app governance, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="eace2-111">Microsoft 雲端 App 安全性</span><span class="sxs-lookup"><span data-stu-id="eace2-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="eace2-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="eace2-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="eace2-113">Microsoft 365 E5 合規性</span><span class="sxs-lookup"><span data-stu-id="eace2-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="eace2-114">Microsoft 365 E5 開發人員 (不含 Windows 和音訊會議)</span><span class="sxs-lookup"><span data-stu-id="eace2-114">Microsoft 365 E5 Developer (without Windows and Audio Conferencing)</span></span>
- <span data-ttu-id="eace2-115">Microsoft 365 E5 資訊保護和控管</span><span class="sxs-lookup"><span data-stu-id="eace2-115">Microsoft 365 E5 Information Protection and Governance</span></span>
- <span data-ttu-id="eace2-116">Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="eace2-116">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="eace2-117">Microsoft 365 E5 (含通話分鐘數)</span><span class="sxs-lookup"><span data-stu-id="eace2-117">Microsoft 365 E5 with Calling Minutes</span></span>
- <span data-ttu-id="eace2-118">Microsoft 365 E5 (不含音訊會議)</span><span class="sxs-lookup"><span data-stu-id="eace2-118">Microsoft 365 E5 without Audio Conferencing</span></span>
- <span data-ttu-id="eace2-119">教職員用 Microsoft 365 A5 合規性</span><span class="sxs-lookup"><span data-stu-id="eace2-119">Microsoft 365 A5 Compliance for faculty</span></span>
- <span data-ttu-id="eace2-120">學生用 Microsoft 365 A5 合規性</span><span class="sxs-lookup"><span data-stu-id="eace2-120">Microsoft 365 A5 Compliance for students</span></span>
- <span data-ttu-id="eace2-121">教職員用 Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="eace2-121">Microsoft 365 A5 for faculty</span></span>
- <span data-ttu-id="eace2-122">學生用 Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="eace2-122">Microsoft 365 A5 for students</span></span>
- <span data-ttu-id="eace2-123">教職員用 Microsoft 365 A5 資訊保護和控管</span><span class="sxs-lookup"><span data-stu-id="eace2-123">Microsoft 365 A5 Information Protection and Governance for faculty</span></span>
- <span data-ttu-id="eace2-124">學生用 Microsoft 365 A5 資訊保護和控管</span><span class="sxs-lookup"><span data-stu-id="eace2-124">Microsoft 365 A5 Information Protection and Governance for students</span></span>
- <span data-ttu-id="eace2-125">教職員用 Microsoft 365 A5 安全性</span><span class="sxs-lookup"><span data-stu-id="eace2-125">Microsoft 365 A5 Security for faculty</span></span>
- <span data-ttu-id="eace2-126">學生用 Microsoft 365 A5 安全性</span><span class="sxs-lookup"><span data-stu-id="eace2-126">Microsoft 365 A5 Security for students</span></span>
- <span data-ttu-id="eace2-127">Microsoft 365 A5 學生使用優惠</span><span class="sxs-lookup"><span data-stu-id="eace2-127">Microsoft 365 A5 student use benefits</span></span>
- <span data-ttu-id="eace2-128">教職員用 Microsoft 365 A5 (含通話分鐘數)</span><span class="sxs-lookup"><span data-stu-id="eace2-128">Microsoft 365 A5 with Calling Minutes for Faculty</span></span>
- <span data-ttu-id="eace2-129">學生用 Microsoft 365 A5 (含通話分鐘數)</span><span class="sxs-lookup"><span data-stu-id="eace2-129">Microsoft 365 A5 with Calling Minutes for Students</span></span>
- <span data-ttu-id="eace2-130">教職員用 Microsoft 365 A5 (不含音訊會議)</span><span class="sxs-lookup"><span data-stu-id="eace2-130">Microsoft 365 A5 without Audio Conferencing for faculty</span></span>
- <span data-ttu-id="eace2-131">學生用 Microsoft 365 A5 (不含音訊會議)</span><span class="sxs-lookup"><span data-stu-id="eace2-131">Microsoft 365 A5 without Audio Conferencing for students</span></span>
- <span data-ttu-id="eace2-132">學生用 Microsoft 365 A5 (不含音訊會議) 使用優惠</span><span class="sxs-lookup"><span data-stu-id="eace2-132">Microsoft 365 A5 without Audio Conferencing for students use benefit</span></span>

## <a name="administrator-roles"></a><span data-ttu-id="eace2-133">系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="eace2-133">Administrator roles</span></span>

<span data-ttu-id="eace2-134">若要查看應用程式控管頁面或管理原則與設定，需要下列其中一個系統管理員角色：</span><span class="sxs-lookup"><span data-stu-id="eace2-134">One of the following administrator roles are required to see app governance pages or manage policies and settings:</span></span>

- <span data-ttu-id="eace2-135">應用程式系統管理員</span><span class="sxs-lookup"><span data-stu-id="eace2-135">Application Administrator</span></span>
- <span data-ttu-id="eace2-136">雲端應用程式系統管理員</span><span class="sxs-lookup"><span data-stu-id="eace2-136">Cloud Application Administrator</span></span>
- <span data-ttu-id="eace2-137">公司系統管理員</span><span class="sxs-lookup"><span data-stu-id="eace2-137">Company Administrator</span></span>
- <span data-ttu-id="eace2-138">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="eace2-138">Compliance Administrator</span></span>
- <span data-ttu-id="eace2-139">合規性資料系統管理員</span><span class="sxs-lookup"><span data-stu-id="eace2-139">Compliance Data Administrator</span></span>
- <span data-ttu-id="eace2-140">合規性讀取者 (唯讀)</span><span class="sxs-lookup"><span data-stu-id="eace2-140">Compliance Reader (read-only)</span></span>
- <span data-ttu-id="eace2-141">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="eace2-141">Global Reader</span></span>
- <span data-ttu-id="eace2-142">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="eace2-142">Security Administrator</span></span>
- <span data-ttu-id="eace2-143">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="eace2-143">Security Operator</span></span>
- <span data-ttu-id="eace2-144">安全性讀取者 (唯讀)</span><span class="sxs-lookup"><span data-stu-id="eace2-144">Security Reader (read-only)</span></span>

<span data-ttu-id="eace2-145">以下是每個角色的功能。</span><span class="sxs-lookup"><span data-stu-id="eace2-145">Here are the capabilities for each role.</span></span>

| <span data-ttu-id="eace2-146">角色</span><span class="sxs-lookup"><span data-stu-id="eace2-146">Role</span></span> | <span data-ttu-id="eace2-147">讀取儀表板</span><span class="sxs-lookup"><span data-stu-id="eace2-147">Read the dashboard</span></span> | <span data-ttu-id="eace2-148">讀取所有應用程式</span><span class="sxs-lookup"><span data-stu-id="eace2-148">Read all apps</span></span> |<span data-ttu-id="eace2-149">讀取原則</span><span class="sxs-lookup"><span data-stu-id="eace2-149">Read policies</span></span> | <span data-ttu-id="eace2-150">建立、更新或刪除原則</span><span class="sxs-lookup"><span data-stu-id="eace2-150">Create, update, or delete policies</span></span> | <span data-ttu-id="eace2-151">讀取警示</span><span class="sxs-lookup"><span data-stu-id="eace2-151">Read alerts</span></span> | <span data-ttu-id="eace2-152">更新警示</span><span class="sxs-lookup"><span data-stu-id="eace2-152">Update alerts</span></span> | <span data-ttu-id="eace2-153">讀取設定</span><span class="sxs-lookup"><span data-stu-id="eace2-153">Read settings</span></span> | <span data-ttu-id="eace2-154">更新設定</span><span class="sxs-lookup"><span data-stu-id="eace2-154">Update settings</span></span> | <span data-ttu-id="eace2-155">讀取補救</span><span class="sxs-lookup"><span data-stu-id="eace2-155">Read Remediation</span></span> | <span data-ttu-id="eace2-156">更新補救</span><span class="sxs-lookup"><span data-stu-id="eace2-156">Update Remediation</span></span> |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="eace2-157">應用程式系統管理員</span><span class="sxs-lookup"><span data-stu-id="eace2-157">Application Administrator</span></span> | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |
| <span data-ttu-id="eace2-168">雲端應用程式系統管理員</span><span class="sxs-lookup"><span data-stu-id="eace2-168">Cloud Application Administrator</span></span> | ![核取記號](..\media\checkmark.png) | | | | | | | | | |
| <span data-ttu-id="eace2-170">公司系統管理員</span><span class="sxs-lookup"><span data-stu-id="eace2-170">Company Administrator</span></span> | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |
| <span data-ttu-id="eace2-181">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="eace2-181">Compliance Administrator</span></span> | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | |
| <span data-ttu-id="eace2-190">合規性資料系統管理員</span><span class="sxs-lookup"><span data-stu-id="eace2-190">Compliance Data Administrator</span></span> | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | |
| <span data-ttu-id="eace2-199">合規性讀取者</span><span class="sxs-lookup"><span data-stu-id="eace2-199">Compliance Reader</span></span> | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) |  | | |
| <span data-ttu-id="eace2-205">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="eace2-205">Global Reader</span></span>  | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) |  | | |
| <span data-ttu-id="eace2-211">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="eace2-211">Security Administrator</span></span> | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | |
| <span data-ttu-id="eace2-220">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="eace2-220">Security Operator</span></span> | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | |
| <span data-ttu-id="eace2-230">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="eace2-230">Security Reader</span></span>  | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) |  | ![核取記號](..\media\checkmark.png) | |
|||||||||| | |

<span data-ttu-id="eace2-237">如需每個角色的其他資訊，請參閱[系統管理員角色權限](/azure/active-directory/roles/permissions-reference)。</span><span class="sxs-lookup"><span data-stu-id="eace2-237">For additional information about each role, see [Administrator role permissions](/azure/active-directory/roles/permissions-reference).</span></span>

## <a name="add-app-governance-to-your-microsoft-365-account"></a><span data-ttu-id="eace2-238">將應用程式控管新增至您的 Microsoft 365 帳戶</span><span class="sxs-lookup"><span data-stu-id="eace2-238">Add app governance to your Microsoft 365 account</span></span>

<span data-ttu-id="eace2-239">針對現有 Microsoft 365 客戶：</span><span class="sxs-lookup"><span data-stu-id="eace2-239">For existing Microsoft 365 customers:</span></span>

1. <span data-ttu-id="eace2-240">在 [Microsoft 365 系統管理中心][](https://admin.microsoft.com) 中，瀏覽至 [計費 - 購買服務]，然後按一下 [附加元件]。</span><span class="sxs-lookup"><span data-stu-id="eace2-240">In your [Microsoft 365 admin center](https://admin.microsoft.com), navigate to **Billing - Purchase services** and click **Add-ons**.</span></span>
1. <span data-ttu-id="eace2-241">在應用程式控管卡片中，按一下 [詳細資料]。</span><span class="sxs-lookup"><span data-stu-id="eace2-241">In the app governance card, click **Details**.</span></span>
1. <span data-ttu-id="eace2-242">按一下 [開始免費試用]。</span><span class="sxs-lookup"><span data-stu-id="eace2-242">Click **Start free trial**.</span></span>
1. <span data-ttu-id="eace2-243">填寫要求的資訊，將應用程式控管新增到您選取的租用戶。</span><span class="sxs-lookup"><span data-stu-id="eace2-243">Complete the requested information to add app governance to your selected tenant.</span></span> <span data-ttu-id="eace2-244">如果您是新的客戶，您必須先提供資訊以建立帳戶並建立試用期的租用戶。</span><span class="sxs-lookup"><span data-stu-id="eace2-244">I you are a new customer, you must first provide information to establish an account and create a tenant for your trial period.</span></span> <span data-ttu-id="eace2-245">完成之後，就可以將應用程式控管新增到試用版。</span><span class="sxs-lookup"><span data-stu-id="eace2-245">Once this is done you can add app governance to the trial.</span></span>

<span data-ttu-id="eace2-246">針對新 Microsoft 365 客戶：</span><span class="sxs-lookup"><span data-stu-id="eace2-246">For new Microsoft 365 customers:</span></span>

1. <span data-ttu-id="eace2-247">在此頁面頂端，按一下 [免費帳戶] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="eace2-247">At the top of this page, click the **Free Account** button.</span></span>
1. <span data-ttu-id="eace2-248">在 [試用商務用 Microsoft 365] 下按一下 [免費試用 1 個月]。</span><span class="sxs-lookup"><span data-stu-id="eace2-248">Under **Try Microsoft 365 for business** click **Try 1 month free**.</span></span>

<span data-ttu-id="eace2-249">針對這兩種客戶：</span><span class="sxs-lookup"><span data-stu-id="eace2-249">For both:</span></span>

1. <span data-ttu-id="eace2-250">在註冊入口網站中，提供您的電子郵件地址以用於試用版。</span><span class="sxs-lookup"><span data-stu-id="eace2-250">In the sign-up portal, provide your email address to use for the trial.</span></span> <span data-ttu-id="eace2-251">如果您是現有的客戶，請使用與您的帳戶相關聯的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="eace2-251">If you are an existing customer, use the email associated with your account.</span></span> <span data-ttu-id="eace2-252">按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="eace2-252">Click **Next**</span></span>
1. <span data-ttu-id="eace2-253">完成註冊後，請按一下 [立即試用] 以取得免費試用版。</span><span class="sxs-lookup"><span data-stu-id="eace2-253">Once you have signed in, click **Try now** to get the free trial.</span></span>
1. <span data-ttu-id="eace2-254">按一下 [繼續] 以關閉頁面並開始試用版設定。</span><span class="sxs-lookup"><span data-stu-id="eace2-254">Click **Continue** to close page and begin trial setup.</span></span> <span data-ttu-id="eace2-255">對於新的應用程式控管客戶，您的應用程式控管執行個體最多需要兩個小時才可供使用。</span><span class="sxs-lookup"><span data-stu-id="eace2-255">For new app governance customers, it will take up to two hours for your app governance instance to become available.</span></span> <span data-ttu-id="eace2-256">對於現有客戶，現有的服務不會中斷。</span><span class="sxs-lookup"><span data-stu-id="eace2-256">For existing customers, there will be no interruption of existing services.</span></span>
  > [!NOTE]
<span data-ttu-id="eace2-257">如果您還沒有帳戶，系統會提示您設定新帳戶，才能繼續試用。</span><span class="sxs-lookup"><span data-stu-id="eace2-257">If you do not already have an account you will be prompted to set up a new account before you can proceed with the trial.</span></span>

1. <span data-ttu-id="eace2-258">輸入您 AAD 租用戶可用的網域名稱，然後按一下 [檢查可用性]。</span><span class="sxs-lookup"><span data-stu-id="eace2-258">Enter in an available domain name for your AAD tenant and click **Check availability**.</span></span> <span data-ttu-id="eace2-259">系統會自動將系統管理員角色指派給您 (如果您沒有應用程式控管的現有角色)，而且您之後隨時都可以透過 Microsoft 365 系統管理中心變更網域名稱和/或購買更多租用戶。</span><span class="sxs-lookup"><span data-stu-id="eace2-259">You will automatically be assigned an Admin role (if you don’t have an existing role for app governance) and can always change the domain name and/or purchase more tenants later through the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="eace2-260">輸入要用於登入帳戶的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="eace2-260">Enter the username and password you would like to use to login to your account.</span></span> <span data-ttu-id="eace2-261">按一下 [註冊]。</span><span class="sxs-lookup"><span data-stu-id="eace2-261">Click **Sign up**.</span></span>
1. <span data-ttu-id="eace2-262">按一下 [開始使用] 以前往應用程式控管入口網站，或按一下 [管理您的訂閱]，以前往 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="eace2-262">Click **Get started** to go to the app governance portal or **Manage your subscription** to go to the Microsoft 365 admin center.</span></span>
