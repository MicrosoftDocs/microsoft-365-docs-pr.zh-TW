---
title: 在系統管理入口網站中新增和驗證系統管理連絡人
description: 告訴我們每個重點領域的連絡人。
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f592644b0aa2853839dd83025a112d0fd3c563df
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962610"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="734cd-104">在系統管理入口網站中新增和驗證系統管理連絡人</span><span class="sxs-lookup"><span data-stu-id="734cd-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="734cd-105">Microsoft 受管理的電腦服務有多種方式可與客戶溝通。</span><span class="sxs-lookup"><span data-stu-id="734cd-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="734cd-106">為了簡化溝通並確保我們與正確的人員一起檢查，您必須移工一組系統管理連絡人。</span><span class="sxs-lookup"><span data-stu-id="734cd-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="734cd-107">Microsoft 受管理的電腦 IT 作業將會連絡這些人員，以便為您的租用戶協助疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="734cd-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="734cd-108">您可能已經在系統管理入口網站新增這些連絡人。</span><span class="sxs-lookup"><span data-stu-id="734cd-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="734cd-109">如果是的話，現在請再次確認連絡人清單使ˋ否正確，因為 Microsoft 受管理的電腦**必須**在發生嚴重事件時能夠連絡到他們。</span><span class="sxs-lookup"><span data-stu-id="734cd-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="734cd-110">Azure Active Directory 存取 Microsoft 受管理電腦的系統管理入口網站</span><span class="sxs-lookup"><span data-stu-id="734cd-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="734cd-111">Microsoft 受管理電腦的系統管理入口網站要求存取入口網站的人員需要擁有以下其中一個 Azure Active Directory (AD) 角色：</span><span class="sxs-lookup"><span data-stu-id="734cd-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="734cd-112">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="734cd-112">Global Administrator</span></span>
- <span data-ttu-id="734cd-113">Intune 服務系統管理員</span><span class="sxs-lookup"><span data-stu-id="734cd-113">Intune Service Administrator</span></span>
- <span data-ttu-id="734cd-114">計費系統管理員</span><span class="sxs-lookup"><span data-stu-id="734cd-114">Billing administrator</span></span>
- <span data-ttu-id="734cd-115">服務支援系統管理員</span><span class="sxs-lookup"><span data-stu-id="734cd-115">Service Support Administrator</span></span>

<span data-ttu-id="734cd-116">全域系統管理員必須是在 Microsoft 受管理的電腦中註冊貴組織的人員。</span><span class="sxs-lookup"><span data-stu-id="734cd-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="734cd-117">所有五個角色在系統管理入口網站都擁有相同存取權，以初始化和檢視工作。</span><span class="sxs-lookup"><span data-stu-id="734cd-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="734cd-118">如需有關在 Azure AD 中指派這些角色的詳細資訊，請參閱[在 Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="734cd-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="734cd-119">系統管理連絡人重點領域</span><span class="sxs-lookup"><span data-stu-id="734cd-119">Admin contact areas of focus</span></span>

<span data-ttu-id="734cd-120">系統管理連絡人必須是最佳人員或群組，可回答問題並做出不同重點領域的決策。</span><span class="sxs-lookup"><span data-stu-id="734cd-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="734cd-121">**Microsoft 受管理的電腦作業將會連絡這些系統管理連絡人，以解決客戶支援要求的問題。**</span><span class="sxs-lookup"><span data-stu-id="734cd-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="734cd-122">這些系統管理連絡人將會收到支援要求更新和新訊息的通知。</span><span class="sxs-lookup"><span data-stu-id="734cd-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="734cd-123">這些領域包括：</span><span class="sxs-lookup"><span data-stu-id="734cd-123">These areas include:</span></span>

<span data-ttu-id="734cd-124">重點領域</span><span class="sxs-lookup"><span data-stu-id="734cd-124">Area of focus</span></span> | <span data-ttu-id="734cd-125">相關問題</span><span class="sxs-lookup"><span data-stu-id="734cd-125">For questions about</span></span>
--- | ---
<span data-ttu-id="734cd-126">應用程式封裝</span><span class="sxs-lookup"><span data-stu-id="734cd-126">App packaging</span></span> | <span data-ttu-id="734cd-127">疑難排解應用程式封裝</span><span class="sxs-lookup"><span data-stu-id="734cd-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="734cd-128">裝置</span><span class="sxs-lookup"><span data-stu-id="734cd-128">Devices</span></span> | <span data-ttu-id="734cd-129">裝置健康情況、透過 Microsoft 受管理的電腦裝置進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="734cd-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="734cd-130">安全性</span><span class="sxs-lookup"><span data-stu-id="734cd-130">Security</span></span> | <span data-ttu-id="734cd-131">透過 Microsoft 受管理的電腦裝置疑難排解安全性問題</span><span class="sxs-lookup"><span data-stu-id="734cd-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="734cd-132">IT 技術支援</span><span class="sxs-lookup"><span data-stu-id="734cd-132">IT help desk</span></span> | <span data-ttu-id="734cd-133">如果我們的支援人員將使用者票證交給 Microsoft 受管理的電腦支援領域之外</span><span class="sxs-lookup"><span data-stu-id="734cd-133">in cases where our Support staff hands over end-user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="734cd-134">其他</span><span class="sxs-lookup"><span data-stu-id="734cd-134">Other</span></span> | <span data-ttu-id="734cd-135">其他領域未涵蓋的問題</span><span class="sxs-lookup"><span data-stu-id="734cd-135">For issues not covered by other areas</span></span>

<span data-ttu-id="734cd-136">**無論您選擇誰做為這些連絡人，都必須擁有知識和授權，以便為您的 Microsoft 受管理的電腦環境做出決策。**</span><span class="sxs-lookup"><span data-stu-id="734cd-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="734cd-137">當您上線 Microsoft 受管理的電腦環境時，系統會提示您為本地技術支援和安全性新增連絡人。</span><span class="sxs-lookup"><span data-stu-id="734cd-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="734cd-138">需要系統管理連絡人才能[提交支援要求](../working-with-managed-desktop/support.md)。</span><span class="sxs-lookup"><span data-stu-id="734cd-138">Admin contacts are required when you [submit a Support request](../working-with-managed-desktop/support.md).</span></span> <span data-ttu-id="734cd-139">您必須擁有針對支援要求之重點領域的系統管理連絡人。</span><span class="sxs-lookup"><span data-stu-id="734cd-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="734cd-140">**若要新增系統管理連絡人**</span><span class="sxs-lookup"><span data-stu-id="734cd-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="734cd-141">登入 [Microsoft 受管理電腦的入口網站](https://aka.ms/mwaasportal)。</span><span class="sxs-lookup"><span data-stu-id="734cd-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="734cd-142">在 [支援]\*\*\*\* 底下，選取 [系統管理連絡人]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="734cd-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![在支援功能表，接近頂端選取的系統管理連絡人](images/admincontacts.png)

3. <span data-ttu-id="734cd-144">選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="734cd-144">Select Add</span></span>

    ![在系統管理入口網站 [匯出並重新整理] 左方的 [新增]按鈕](images/adminadd.png)

4.  <span data-ttu-id="734cd-146">選取 [重點領域]\*\*\*\* 並輸入連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="734cd-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![重點領域清單，例如 [其他]、[應用程式] 和 [安全性]](images/areaoffocus.png)

5. <span data-ttu-id="734cd-148">每個重點領域的重複。</span><span class="sxs-lookup"><span data-stu-id="734cd-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="734cd-149">開始使用 Microsoft 受管理電腦的步驟</span><span class="sxs-lookup"><span data-stu-id="734cd-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="734cd-150">在系統管理入口網站中新增和驗證系統管理連絡人 (此主題)</span><span class="sxs-lookup"><span data-stu-id="734cd-150">Add and verify admin contacts in the Admin portal</span></span>
2. [<span data-ttu-id="734cd-151">調整條件式存取</span><span class="sxs-lookup"><span data-stu-id="734cd-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="734cd-152">指派授權</span><span class="sxs-lookup"><span data-stu-id="734cd-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="734cd-153">在裝置上安裝 Intune 公司入口網站</span><span class="sxs-lookup"><span data-stu-id="734cd-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="734cd-154">啟用企業狀態漫遊</span><span class="sxs-lookup"><span data-stu-id="734cd-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="734cd-155">設定 Microsoft 受管理的電腦裝置</span><span class="sxs-lookup"><span data-stu-id="734cd-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="734cd-156">讓您的使用者準備好使用裝置</span><span class="sxs-lookup"><span data-stu-id="734cd-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="734cd-157">將應用程式部署至裝置</span><span class="sxs-lookup"><span data-stu-id="734cd-157">Deploy apps to devices</span></span>](deploy-apps.md)