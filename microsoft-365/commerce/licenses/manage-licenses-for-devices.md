---
title: 管理裝置的授權
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: 瞭解如何將授權指派給群組，以用於裝置。
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: a29465e9425694f8913cc09d1b8a0c761c79803c
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826276"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="1ffd1-103">管理裝置的授權</span><span class="sxs-lookup"><span data-stu-id="1ffd1-103">Manage licenses for devices</span></span>

<span data-ttu-id="1ffd1-104">如果您有 Office 365 ProPlus （裝置）或 Office 365 ProPlus 教育版（裝置），您可以使用 Azure AD 群組將授權指派給裝置。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-104">If you have Office 365 ProPlus (device) or Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="1ffd1-105">當裝置具有授權時，使用該裝置的任何人都可以使用 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="1ffd1-106">例如，假設您有20個可擕式電腦及您組織中的人員所使用的平板電腦。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="1ffd1-107">當您指派授權給每個裝置時，登入其中一個裝置的每個人都使用 Office 365，而不需要自己的授權。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ffd1-108">Office 365 ProPlus 的裝置型授權，只會做為部分 commerical 客戶和某些教育客戶的附加元件授權。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-108">Device-based licensing for Office 365 ProPlus is available only as an add-on license for some commerical customers and some education customers.</span></span> <span data-ttu-id="1ffd1-109">針對商業客戶，授權是*Office 365 ProPlus （裝置）* ，只能透過 enterprise 合約/Enterprise 合約訂閱使用。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-109">For commercial customers, the license is *Office 365 ProPlus (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="1ffd1-110">針對教育版客戶，授權是*Office 365 ProPlus 教育版（裝置）* ，而且只能透過註冊教育版解決方案（EES）使用。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-110">For education customers, the license is *Office 365 ProPlus for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="1ffd1-111">如需詳細資訊，請閱讀「[教育](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)版上的博客文章。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="1ffd1-112">如需商用，請與您的 Microsoft 客戶代表聯繫。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="1ffd1-113">若要開始，請在 Azure Active Directory 系統管理中心建立群組，然後將裝置指派至群組。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="1ffd1-114">若要深入瞭解裝置授權（包括裝置需求、您可以使用的群組類型及如何設定 Office 365 ProPlus 以使用裝置授權），請參閱以[裝置為基礎的授權 For office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216)。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device-based licensing for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ffd1-115">您必須是全域系統管理員，才可完成本文中的工作。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="1ffd1-116">指派授權給裝置</span><span class="sxs-lookup"><span data-stu-id="1ffd1-116">Assign licenses to devices</span></span>

<span data-ttu-id="1ffd1-117">當您指派授權給群組時，您可以將授權指派給群組中的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="1ffd1-118">您只可以將一個預訂指派給任何單一群組。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="1ffd1-119">在 Microsoft 365 系統管理中心中，移至 [**帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="1ffd1-120">在 [**授權**] 頁面上，選擇 [**教育版（裝置）** 或**office ProPlus （裝置）** 的 office 365 ProPlus。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-120">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="1ffd1-121">在下一個頁面上，選擇訂閱，然後選擇 [**指派授權**]。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="1ffd1-122">在 [**將授權指派給群組**] 窗格中，開始輸入組名，然後從結果中加以選擇以將其新增至清單。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="1ffd1-123">選擇 [**指派**]，然後選擇 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="1ffd1-124">從裝置取消指派授權</span><span class="sxs-lookup"><span data-stu-id="1ffd1-124">Unassign licenses from devices</span></span>

<span data-ttu-id="1ffd1-125">當您取消指派群組中的授權時，會從群組內的所有裝置中移除授權。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="1ffd1-126">所有應用程式及其相關聯的資料都是唯讀的。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="1ffd1-127">在系統管理中心中，移至 [**帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="1ffd1-128">在 [**授權**] 頁面上，選擇 [**教育版（裝置）** 或**office ProPlus （裝置）** 的 office 365 ProPlus。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-128">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="1ffd1-129">在下一個頁面上，選擇訂閱，選擇 [**其他動作**]，然後選擇 [未**指派授權**]。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="1ffd1-130">在 [未**指派的授權**] 對話方塊中，選擇 [**取消指派**]。</span><span class="sxs-lookup"><span data-stu-id="1ffd1-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>