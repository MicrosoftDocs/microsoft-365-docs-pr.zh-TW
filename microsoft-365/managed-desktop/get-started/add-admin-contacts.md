---
title: 新增 Microsoft 受管理的桌上型電腦管理入口網站中管理連絡人
description: 告訴我們要針對每個區域的焦點連絡的人。
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 31984609681b6e3b1b6de9996eb8fb0fcf6f5624
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866298"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="d8911-104">新增 Microsoft 受管理的桌上型電腦管理入口網站中管理連絡人</span><span class="sxs-lookup"><span data-stu-id="d8911-104">Add Admin contacts in Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="d8911-p101">有數種方式與客戶的 Microsoft 受管理的桌上型電腦服務通訊。若要簡化通訊並確定我們要檢查與最佳的連絡人，您需要提供一組管理連絡人。Microsoft 受管理的桌上型電腦 IT 作業將會連絡這些人員協助您的租用戶疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="d8911-p101">There are several ways that Microsoft Managed Desktop service communicates with customers. To streamline communication and ensure we’re checking with the best contacts, you need to provide a set of admin contacts. Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span> 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="d8911-108">Azure Active Directory 存取 Microsoft 受管理的桌上型電腦管理入口網站</span><span class="sxs-lookup"><span data-stu-id="d8911-108">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="d8911-109">Microsoft 受管理的桌上型電腦管理入口網站需要存取入口網站的人員可以其中一種 Azure Active Directory (AD) 角色：</span><span class="sxs-lookup"><span data-stu-id="d8911-109">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="d8911-110">全域管理員</span><span class="sxs-lookup"><span data-stu-id="d8911-110">Global Administrator</span></span>
- <span data-ttu-id="d8911-111">Intune 服務管理員</span><span class="sxs-lookup"><span data-stu-id="d8911-111">Intune Service Administrator</span></span>
- <span data-ttu-id="d8911-112">計費管理員</span><span class="sxs-lookup"><span data-stu-id="d8911-112">Billing Administrator</span></span>
- <span data-ttu-id="d8911-113">服務支援管理員</span><span class="sxs-lookup"><span data-stu-id="d8911-113">Service Support Administrator</span></span>

<span data-ttu-id="d8911-p102">全域管理員必須是一個以註冊 Microsoft 受管理的桌上型電腦的客戶。 所有五個角色具有相同的存取權來初始化和檢視工作管理入口網站內。 如需有關如何將這些角色指派的 Azure AD 的詳細資訊，請參閱[在 Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="d8911-p102">The Global Administrator must be the one to enroll the customer in Microsoft Managed Desktop.  All five roles have the same access within the Admin portal to initiate and view tasks.  For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-focus-areas"></a><span data-ttu-id="d8911-117">管理連絡人焦點區域</span><span class="sxs-lookup"><span data-stu-id="d8911-117">Admin contact focus areas</span></span>

<span data-ttu-id="d8911-p103">管理連絡人應最佳的人員或群組可回答的問題和進行不同的焦點區域的決策。 Microsoft 受管理的桌上型電腦作業將會連絡這些管理連絡人涉及歸檔由客戶支援要求的問題。 這些管理連絡人將會收到通知的支援要求更新和新的訊息。 這些區域包括：</span><span class="sxs-lookup"><span data-stu-id="d8911-p103">Admin contacts should be the best person or group that can answer questions and make decisions for different focus areas.  Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.  These Admin contacts will receive notifications for support request updates and new messages.  These areas include:</span></span>

<span data-ttu-id="d8911-122">焦點區域</span><span class="sxs-lookup"><span data-stu-id="d8911-122">Focus area</span></span> | <span data-ttu-id="d8911-123">如需問題</span><span class="sxs-lookup"><span data-stu-id="d8911-123">For questions about</span></span>
--- | ---
<span data-ttu-id="d8911-124">應用程式</span><span class="sxs-lookup"><span data-stu-id="d8911-124">Apps</span></span> | <span data-ttu-id="d8911-125">疑難排解應用程式封裝</span><span class="sxs-lookup"><span data-stu-id="d8911-125">Troubleshooting App Packaging</span></span>
<span data-ttu-id="d8911-126">[裝置]</span><span class="sxs-lookup"><span data-stu-id="d8911-126">Devices</span></span> | <span data-ttu-id="d8911-127">裝置健康情況、 疑難排解與 Microsoft 受管理的桌上型電腦裝置</span><span class="sxs-lookup"><span data-stu-id="d8911-127">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="d8911-128">安全性</span><span class="sxs-lookup"><span data-stu-id="d8911-128">Security</span></span> | <span data-ttu-id="d8911-129">疑難排解 Microsoft 受管理的桌上型電腦裝置的安全性問題</span><span class="sxs-lookup"><span data-stu-id="d8911-129">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="d8911-130">其他</span><span class="sxs-lookup"><span data-stu-id="d8911-130">Other</span></span> | <span data-ttu-id="d8911-131">不涵蓋其他方面的問題</span><span class="sxs-lookup"><span data-stu-id="d8911-131">For issues not covered by other areas</span></span>

<span data-ttu-id="d8911-p104">凡是您選擇的這些連絡人必須擁有的知識和授權來決定 Microsoft 受管理的桌上型電腦環境。當您開始您的 Microsoft 受管理的桌上型電腦環境中，系統將提示您將連絡人新增本機服務台及安全性。</span><span class="sxs-lookup"><span data-stu-id="d8911-p104">Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment. When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="d8911-p105">管理連絡人所需何時您[提交支援要求](../working-with-managed-desktop/support.md)。您需要有焦點區的支援要求管理員連絡。</span><span class="sxs-lookup"><span data-stu-id="d8911-p105">Admin contacts are required when you [submit a Support request](../working-with-managed-desktop/support.md). You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="d8911-136">**若要新增管理連絡人**</span><span class="sxs-lookup"><span data-stu-id="d8911-136">**To add admin contacts**</span></span>

1.  <span data-ttu-id="d8911-137">登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)。</span><span class="sxs-lookup"><span data-stu-id="d8911-137">Sign in to [Microsoft Managed Desktop admin portal](http://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="d8911-138">**支援**] 底下選取 [**系統管理連絡人**。</span><span class="sxs-lookup"><span data-stu-id="d8911-138">Under **Support**, select **Admin contacts**.</span></span> 

    ![支援] 功能表中管理連絡人](images/admincontacts.png)

3. <span data-ttu-id="d8911-140">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d8911-140">Select **Add**.</span></span>

    ![Admin 入口網站新增] 按鈕](images/adminadd.png)

4.  <span data-ttu-id="d8911-142">選取**的焦點] 區域中**，輸入連絡人的資訊。</span><span class="sxs-lookup"><span data-stu-id="d8911-142">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![區域的焦點的清單](images/areaoffocus.png)

5. <span data-ttu-id="d8911-144">重複針對每個區域的焦點。</span><span class="sxs-lookup"><span data-stu-id="d8911-144">Repeat for each area of focus.</span></span> 

