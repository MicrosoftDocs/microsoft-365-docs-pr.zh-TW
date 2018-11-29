---
title: 新增 Microsoft 受管理的桌上型電腦管理入口網站中管理連絡人
description: 告訴我們要針對每個區域的焦點連絡的人。
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 65dd8709c469826e2696015c13823c58eb10e342
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866298"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="c2e7b-104">新增 Microsoft 受管理的桌上型電腦管理入口網站中管理連絡人</span><span class="sxs-lookup"><span data-stu-id="c2e7b-104">Add Admin contacts in Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="c2e7b-p101">有數種方式與客戶的 Microsoft 受管理的桌上型電腦服務通訊。若要簡化通訊並確定我們要檢查與最佳的連絡人，您需要提供一組管理連絡人。Microsoft 受管理的桌上型電腦 IT 作業將會連絡這些人員協助您的租用戶疑難排解問題。</span><span class="sxs-lookup"><span data-stu-id="c2e7b-p101">There are several ways that Microsoft Managed Desktop service communicates with customers. To streamline communication and ensure we’re checking with the best contacts, you need to provide a set of admin contacts. Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span> 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="c2e7b-108">Azure Active Directory 存取 Microsoft 受管理的桌上型電腦管理入口網站</span><span class="sxs-lookup"><span data-stu-id="c2e7b-108">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="c2e7b-109">Microsoft 受管理的桌上型電腦管理入口網站需要存取入口網站的人員可以其中一種 Azure Active Directory (AD) 角色：</span><span class="sxs-lookup"><span data-stu-id="c2e7b-109">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="c2e7b-110">全域管理員</span><span class="sxs-lookup"><span data-stu-id="c2e7b-110">Global Administrator</span></span>
- <span data-ttu-id="c2e7b-111">Intune 服務管理員</span><span class="sxs-lookup"><span data-stu-id="c2e7b-111">Intune Service Administrator</span></span>
- <span data-ttu-id="c2e7b-112">計費管理員</span><span class="sxs-lookup"><span data-stu-id="c2e7b-112">Billing Administrator</span></span>
- <span data-ttu-id="c2e7b-113">服務支援管理員</span><span class="sxs-lookup"><span data-stu-id="c2e7b-113">Service Support Administrator</span></span>

<span data-ttu-id="c2e7b-114">如需有關這些角色及其在 Azure AD 為其指派的詳細資訊，請參閱[在 Azure Active Directory 中的系統管理員角色權限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="c2e7b-114">For more information on these roles and assigning them in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-focus-areas"></a><span data-ttu-id="c2e7b-115">管理連絡人焦點區域</span><span class="sxs-lookup"><span data-stu-id="c2e7b-115">Admin contact focus areas</span></span>

<span data-ttu-id="c2e7b-p102">管理連絡人應最佳的人員或群組可回答的問題和進行不同的焦點區域的決策。這些區域包括：</span><span class="sxs-lookup"><span data-stu-id="c2e7b-p102">Admin contacts should be the best person or group that can answer questions and make decisions for different focus areas. These areas include:</span></span>

<span data-ttu-id="c2e7b-118">焦點區域</span><span class="sxs-lookup"><span data-stu-id="c2e7b-118">Focus area</span></span> | <span data-ttu-id="c2e7b-119">如需問題</span><span class="sxs-lookup"><span data-stu-id="c2e7b-119">For questions about</span></span>
--- | ---
<span data-ttu-id="c2e7b-120">應用程式</span><span class="sxs-lookup"><span data-stu-id="c2e7b-120">Apps</span></span> | <span data-ttu-id="c2e7b-121">疑難排解應用程式封裝</span><span class="sxs-lookup"><span data-stu-id="c2e7b-121">Troubleshooting App Packaging</span></span>
<span data-ttu-id="c2e7b-122">[裝置]</span><span class="sxs-lookup"><span data-stu-id="c2e7b-122">Devices</span></span> | <span data-ttu-id="c2e7b-123">裝置健康情況、 疑難排解與 Microsoft 受管理的桌上型電腦裝置</span><span class="sxs-lookup"><span data-stu-id="c2e7b-123">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="c2e7b-124">安全性</span><span class="sxs-lookup"><span data-stu-id="c2e7b-124">Security</span></span> | <span data-ttu-id="c2e7b-125">疑難排解 Microsoft 受管理的桌上型電腦裝置的安全性問題</span><span class="sxs-lookup"><span data-stu-id="c2e7b-125">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="c2e7b-126">其他</span><span class="sxs-lookup"><span data-stu-id="c2e7b-126">Other</span></span> | <span data-ttu-id="c2e7b-127">不涵蓋其他方面的問題</span><span class="sxs-lookup"><span data-stu-id="c2e7b-127">For issues not covered by other areas</span></span>

<span data-ttu-id="c2e7b-p103">凡是您選擇的這些連絡人必須擁有的知識和授權來決定 Microsoft 受管理的桌上型電腦環境。當您開始您的 Microsoft 受管理的桌上型電腦環境中，系統將提示您將連絡人新增本機服務台及安全性。</span><span class="sxs-lookup"><span data-stu-id="c2e7b-p103">Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment. When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="c2e7b-p104">管理連絡人所需何時您[提交支援要求](../working-with-managed-desktop/support.md)。您需要有焦點區的支援要求管理員連絡。</span><span class="sxs-lookup"><span data-stu-id="c2e7b-p104">Admin contacts are required when you [submit a Support request](../working-with-managed-desktop/support.md). You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="c2e7b-132">**若要新增管理連絡人**</span><span class="sxs-lookup"><span data-stu-id="c2e7b-132">**To add admin contacts**</span></span>

1.  <span data-ttu-id="c2e7b-133">登入[Microsoft 受管理的桌上型電腦管理入口網站](http://aka.ms/mwaasportal)。</span><span class="sxs-lookup"><span data-stu-id="c2e7b-133">Sign in to [Microsoft Managed Desktop admin portal](http://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="c2e7b-134">**支援**] 底下選取 [**系統管理連絡人**。</span><span class="sxs-lookup"><span data-stu-id="c2e7b-134">Under **Support**, select **Admin contacts**.</span></span> 

    ![支援] 功能表中管理連絡人](images/admincontacts.png)

3. <span data-ttu-id="c2e7b-136">選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c2e7b-136">Select **Add**.</span></span>

    ![Admin 入口網站新增] 按鈕](images/adminadd.png)

4.  <span data-ttu-id="c2e7b-138">選取**的焦點] 區域中**，輸入連絡人的資訊。</span><span class="sxs-lookup"><span data-stu-id="c2e7b-138">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![區域的焦點的清單](images/areaoffocus.png)

5. <span data-ttu-id="c2e7b-140">重複針對每個區域的焦點。</span><span class="sxs-lookup"><span data-stu-id="c2e7b-140">Repeat for each area of focus.</span></span> 

