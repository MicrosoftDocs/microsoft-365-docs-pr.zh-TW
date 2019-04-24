---
title: Microsoft 受管理的電腦系統管理入口網站中新增系統管理連絡人
description: 告訴我們人員連絡以取得焦點的每個區域。
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 014404ab38ff5871289be186dec150115c3be6ec
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277529"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="fbe29-104">Microsoft 受管理的桌上型電腦管理入口網站中新增系統管理連絡人</span><span class="sxs-lookup"><span data-stu-id="fbe29-104">Add Admin contacts in Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="fbe29-105">有幾種方式與客戶的 Microsoft 受管理的電腦服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="fbe29-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="fbe29-106">若要簡化的通訊，並確保我們正在檢查的最佳的連絡人，您需要提供一組系統管理員連絡人。</span><span class="sxs-lookup"><span data-stu-id="fbe29-106">To streamline communication and ensure we’re checking with the best contacts, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="fbe29-107">Microsoft 受管理的桌上型電腦 IT 作業將連絡這些人員，以協助疑難排解問題，您的租用戶。</span><span class="sxs-lookup"><span data-stu-id="fbe29-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span> 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="fbe29-108">Microsoft 受管理的桌上型電腦系統管理入口網站的 azure Active Directory 存取</span><span class="sxs-lookup"><span data-stu-id="fbe29-108">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="fbe29-109">Microsoft 受管理的桌上型電腦系統管理入口網站，必須具備存取入口網站的人員其中一種 Azure Active Directory (AD) 角色：</span><span class="sxs-lookup"><span data-stu-id="fbe29-109">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="fbe29-110">全域管理員</span><span class="sxs-lookup"><span data-stu-id="fbe29-110">Global Administrator</span></span>
- <span data-ttu-id="fbe29-111">Intune 服務管理員</span><span class="sxs-lookup"><span data-stu-id="fbe29-111">Intune Service Administrator</span></span>
- <span data-ttu-id="fbe29-112">計費系統管理員</span><span class="sxs-lookup"><span data-stu-id="fbe29-112">Billing Administrator</span></span>
- <span data-ttu-id="fbe29-113">服務支援系統管理員</span><span class="sxs-lookup"><span data-stu-id="fbe29-113">Service Support Administrator</span></span>

<span data-ttu-id="fbe29-114">全域系統管理員必須是要註冊 Microsoft 受管理電腦中的客戶一種。</span><span class="sxs-lookup"><span data-stu-id="fbe29-114">The Global Administrator must be the one to enroll the customer in Microsoft Managed Desktop.</span></span>  <span data-ttu-id="fbe29-115">所有的五個角色都相同的存取權，在系統管理入口網站中啟動和檢視工作。</span><span class="sxs-lookup"><span data-stu-id="fbe29-115">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span>  <span data-ttu-id="fbe29-116">如需有關如何在 Azure AD 中指派這些角色的詳細資訊，請參閱 < <b0>Azure Active Directory 中的系統管理員角色權限</b0>。</span><span class="sxs-lookup"><span data-stu-id="fbe29-116">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-focus-areas"></a><span data-ttu-id="fbe29-117">系統管理連絡人的重點領域</span><span class="sxs-lookup"><span data-stu-id="fbe29-117">Admin contact focus areas</span></span>

<span data-ttu-id="fbe29-118">系統管理連絡人應該是最佳的人員或群組，可以回答問題，並使不同的重點領域的決策。</span><span class="sxs-lookup"><span data-stu-id="fbe29-118">Admin contacts should be the best person or group that can answer questions and make decisions for different focus areas.</span></span>  <span data-ttu-id="fbe29-119">Microsoft 受管理的桌上型電腦作業會連絡這些系統管理連絡人的涉及歸檔由客戶支援要求的問題。</span><span class="sxs-lookup"><span data-stu-id="fbe29-119">Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.</span></span>  <span data-ttu-id="fbe29-120">這些系統管理連絡人會收到支援要求的更新和新郵件通知。</span><span class="sxs-lookup"><span data-stu-id="fbe29-120">These Admin contacts will receive notifications for support request updates and new messages.</span></span>  <span data-ttu-id="fbe29-121">這些區域，包括：</span><span class="sxs-lookup"><span data-stu-id="fbe29-121">These areas include:</span></span>

<span data-ttu-id="fbe29-122">焦點區域</span><span class="sxs-lookup"><span data-stu-id="fbe29-122">Focus area</span></span> | <span data-ttu-id="fbe29-123">如需問題</span><span class="sxs-lookup"><span data-stu-id="fbe29-123">For questions about</span></span>
--- | ---
<span data-ttu-id="fbe29-124">App</span><span class="sxs-lookup"><span data-stu-id="fbe29-124">Apps</span></span> | <span data-ttu-id="fbe29-125">疑難排解應用程式封裝</span><span class="sxs-lookup"><span data-stu-id="fbe29-125">Troubleshooting App Packaging</span></span>
<span data-ttu-id="fbe29-126">裝置</span><span class="sxs-lookup"><span data-stu-id="fbe29-126">Devices</span></span> | <span data-ttu-id="fbe29-127">裝置健全狀況，使用 Microsoft 受管理的電腦裝置進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="fbe29-127">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="fbe29-128">安全性</span><span class="sxs-lookup"><span data-stu-id="fbe29-128">Security</span></span> | <span data-ttu-id="fbe29-129">疑難排解安全性問題的 Microsoft 受管理的電腦裝置</span><span class="sxs-lookup"><span data-stu-id="fbe29-129">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="fbe29-130">其他</span><span class="sxs-lookup"><span data-stu-id="fbe29-130">Other</span></span> | <span data-ttu-id="fbe29-131">未涵蓋之其他方面的問題</span><span class="sxs-lookup"><span data-stu-id="fbe29-131">For issues not covered by other areas</span></span>

<span data-ttu-id="fbe29-132">無論您選擇讓知識和授權來決定 Microsoft 受管理的桌上型電腦環境這些連絡人需求。</span><span class="sxs-lookup"><span data-stu-id="fbe29-132">Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="fbe29-133">當您上架您 Microsoft 受管理的桌上型電腦環境中，系統會提示您將連絡人新增本機服務台和安全性。</span><span class="sxs-lookup"><span data-stu-id="fbe29-133">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="fbe29-134">系統管理連絡人都是必要時您[提交支援要求](../working-with-managed-desktop/support.md)。</span><span class="sxs-lookup"><span data-stu-id="fbe29-134">Admin contacts are required when you [submit a Support request](../working-with-managed-desktop/support.md).</span></span> <span data-ttu-id="fbe29-135">您需要有支援要求的 [焦點] 區域的系統管理員連絡。</span><span class="sxs-lookup"><span data-stu-id="fbe29-135">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="fbe29-136">**若要新增系統管理連絡人**</span><span class="sxs-lookup"><span data-stu-id="fbe29-136">**To add admin contacts**</span></span>

1.  <span data-ttu-id="fbe29-137">登入[Microsoft 受管理的電腦系統管理入口網站](http://aka.ms/mwaasportal)。</span><span class="sxs-lookup"><span data-stu-id="fbe29-137">Sign in to [Microsoft Managed Desktop admin portal](http://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="fbe29-138">**支援**] 底下選取 [**系統管理連絡人**]。</span><span class="sxs-lookup"><span data-stu-id="fbe29-138">Under **Support**, select **Admin contacts**.</span></span> 

    ![支援] 功能表中，系統管理連絡人](images/admincontacts.png)

3. <span data-ttu-id="fbe29-140">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="fbe29-140">Select **Add**.</span></span>

    ![系統管理員入口網站加入] 按鈕](images/adminadd.png)

4.  <span data-ttu-id="fbe29-142">選取**的焦點] 區域**，然後輸入連絡人的資訊。</span><span class="sxs-lookup"><span data-stu-id="fbe29-142">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![[] 清單中的焦點的區域](images/areaoffocus.png)

5. <span data-ttu-id="fbe29-144">重複的每個區域的焦點。</span><span class="sxs-lookup"><span data-stu-id="fbe29-144">Repeat for each area of focus.</span></span> 

