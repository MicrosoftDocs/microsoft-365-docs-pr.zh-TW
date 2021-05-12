---
title: 管理裝置的授權
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: 瞭解如何將授權指派給群組，以用於裝置。
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: 67bd0734953c64f51390aac949a7da477914c7b4
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331655"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="dcafe-103">管理裝置的授權</span><span class="sxs-lookup"><span data-stu-id="dcafe-103">Manage licenses for devices</span></span>

<span data-ttu-id="dcafe-104">如果您有 Microsoft 365 Apps for enterprise (device) 或 Microsoft 365 Apps for 教育版 (裝置) ，您可以使用 Azure AD 群組將授權指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="dcafe-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="dcafe-105">當裝置具有授權時，使用該裝置的任何人都可以使用 Microsoft 365 Apps for enterprise (先前命名為 Office 365 ProPlus) 。</span><span class="sxs-lookup"><span data-stu-id="dcafe-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="dcafe-106">例如，假設您有20個可擕式電腦及您組織中的人員所使用的平板電腦。</span><span class="sxs-lookup"><span data-stu-id="dcafe-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="dcafe-107">當您指派授權給每個裝置時，登入其中一個裝置的每一位使用者都使用 Microsoft 365 應用程式的企業版，而不需要自己的授權。</span><span class="sxs-lookup"><span data-stu-id="dcafe-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcafe-108">適用于企業的 Microsoft 365 應用程式的裝置型授權，只會做為部分商業客戶和某些教育客戶的附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="dcafe-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="dcafe-109">針對商業客戶，授權是 *Microsoft 365 應用程式的 enterprise (device)* ，且只能透過 enterprise 合約/Enterprise 合約訂閱使用。</span><span class="sxs-lookup"><span data-stu-id="dcafe-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="dcafe-110">針對教育版客戶，授權是 *Microsoft 365 應用程式教育版 (裝置)* ，且只能透過註冊教育版解決方案 (EES) 。</span><span class="sxs-lookup"><span data-stu-id="dcafe-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="dcafe-111">如需詳細資訊，請閱讀「 [教育](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education)版上的博客文章。</span><span class="sxs-lookup"><span data-stu-id="dcafe-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education).</span></span> <span data-ttu-id="dcafe-112">如需商用，請與您的 Microsoft 客戶代表聯繫。</span><span class="sxs-lookup"><span data-stu-id="dcafe-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="dcafe-113">若要開始，請在 Azure Active Directory 系統管理中心建立群組，然後將裝置指派至群組。</span><span class="sxs-lookup"><span data-stu-id="dcafe-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="dcafe-114">若要深入瞭解裝置授權（包括裝置需求、您可以使用的群組類型，以及如何設定 Microsoft 365 應用程式以使用裝置授權），請參閱 [適用于企業的 microsoft 365 應用程式的裝置型授權](/deployoffice/device-based-licensing)。</span><span class="sxs-lookup"><span data-stu-id="dcafe-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcafe-115">您必須是全域系統管理員，才可完成本文中的工作。</span><span class="sxs-lookup"><span data-stu-id="dcafe-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="dcafe-116">指派授權給裝置</span><span class="sxs-lookup"><span data-stu-id="dcafe-116">Assign licenses to devices</span></span>

<span data-ttu-id="dcafe-117">當您指派授權給群組時，您可以將授權指派給群組中的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="dcafe-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="dcafe-118">您只可以將一個預訂指派給任何單一群組。</span><span class="sxs-lookup"><span data-stu-id="dcafe-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="dcafe-119">在 Microsoft 365 系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="dcafe-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="dcafe-120">在 [ **授權** ] 頁面上，選擇 [ **用於教育版的 Microsoft 365 應用程式] (裝置)** 或 **microsoft 365 應用程式 (裝置)**。</span><span class="sxs-lookup"><span data-stu-id="dcafe-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="dcafe-121">在下一個頁面上，選擇訂閱，然後選擇 [ **指派授權**]。</span><span class="sxs-lookup"><span data-stu-id="dcafe-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="dcafe-122">在 [ **將授權指派給群組** ] 窗格中，開始輸入組名，然後從結果中加以選擇以將其新增至清單。</span><span class="sxs-lookup"><span data-stu-id="dcafe-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="dcafe-123">選擇 [ **指派**]，然後選擇 [ **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="dcafe-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="dcafe-124">從裝置取消指派授權</span><span class="sxs-lookup"><span data-stu-id="dcafe-124">Unassign licenses from devices</span></span>

<span data-ttu-id="dcafe-125">當您取消指派群組中的授權時，會從群組內的所有裝置中移除授權。</span><span class="sxs-lookup"><span data-stu-id="dcafe-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="dcafe-126">所有應用程式及其相關聯的資料都是唯讀的。</span><span class="sxs-lookup"><span data-stu-id="dcafe-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="dcafe-127">在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="dcafe-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="dcafe-128">在 [ **授權** ] 頁面上，選擇 [ **用於教育版的 Microsoft 365 應用程式] (裝置)** 或 **microsoft 365 應用程式 (裝置)**。</span><span class="sxs-lookup"><span data-stu-id="dcafe-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="dcafe-129">在下一個頁面上，選擇訂閱，選擇 [ **其他動作**]，然後選擇 [未 **指派授權**]。</span><span class="sxs-lookup"><span data-stu-id="dcafe-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="dcafe-130">在 [未 **指派的授權** ] 對話方塊中，選擇 [ **取消指派**]。</span><span class="sxs-lookup"><span data-stu-id="dcafe-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>
