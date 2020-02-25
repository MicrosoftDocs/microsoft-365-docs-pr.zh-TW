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
description: 了解如何將授權指派給使用的群組中，與裝置。
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42239735"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="7a709-103">管理裝置的授權</span><span class="sxs-lookup"><span data-stu-id="7a709-103">Manage licenses for devices</span></span>

<span data-ttu-id="7a709-104">如果您有 Office 365 專業增強版的教育版 （裝置），您可以將授權指派給裝置，使用 Azure AD 群組。</span><span class="sxs-lookup"><span data-stu-id="7a709-104">If you have Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="7a709-105">當裝置有授權時，使用該裝置的任何人可以使用 Office 365。</span><span class="sxs-lookup"><span data-stu-id="7a709-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="7a709-106">例如，假設您有 20 膝上型電腦和平板電腦以供您組織中的人員。</span><span class="sxs-lookup"><span data-stu-id="7a709-106">For example, let’s say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="7a709-107">當您將授權指派給每個裝置時，每個登入到其中一個裝置的人會使用 Office 365，而不需要為他們自己的授權。</span><span class="sxs-lookup"><span data-stu-id="7a709-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a709-108">Office 365 專業增強版的教育版 （裝置） 才可教育版 A3 和 A5 大量授權客戶。</span><span class="sxs-lookup"><span data-stu-id="7a709-108">Office 365 ProPlus for Education (device) is only available to Education A3 and A5 volume licensing customers.</span></span>

<span data-ttu-id="7a709-109">若要開始，您會在 Azure Active Directory 系統管理中心中，建立群組，然後再指派給群組的 [裝置。</span><span class="sxs-lookup"><span data-stu-id="7a709-109">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="7a709-110">若要深入了解授權裝置，包括裝置需求，哪些類型的群組，您可以使用，以及如何設定 Office 365 專業增強版要使用的裝置授權，請參閱[裝置授權 Office 365 專業增強版的教育版客戶](https://go.microsoft.com/fwlink/p/?linkid=2094216)。</span><span class="sxs-lookup"><span data-stu-id="7a709-110">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device licensing for Office 365 ProPlus for Education customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a709-111">您必須是全域系統管理員，才能完成本文中的工作。</span><span class="sxs-lookup"><span data-stu-id="7a709-111">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="7a709-112">將授權指派給裝置</span><span class="sxs-lookup"><span data-stu-id="7a709-112">Assign licenses to devices</span></span>

<span data-ttu-id="7a709-113">當您將授權指派給群組時，您會將授權指派給群組內的所有裝置中。</span><span class="sxs-lookup"><span data-stu-id="7a709-113">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="7a709-114">您只能指定一個訂用帳戶至任何單一群組。</span><span class="sxs-lookup"><span data-stu-id="7a709-114">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="7a709-115">在 Microsoft 365 系統管理中心，移至**帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7a709-115">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="7a709-116">在 [**授權**] 頁面上，選擇 [ **Office 365 專業增強版的教育版 （裝置）**。</span><span class="sxs-lookup"><span data-stu-id="7a709-116">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="7a709-117">在**Office 365 專業增強版的教育版 （裝置）** 頁面上，選擇訂閱，然後選擇 [**指派授權**。</span><span class="sxs-lookup"><span data-stu-id="7a709-117">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="7a709-118">在**指派給群組的授權**] 窗格中，開始輸入群組名稱，，然後從結果，以將它新增至清單中選擇。</span><span class="sxs-lookup"><span data-stu-id="7a709-118">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
6. <span data-ttu-id="7a709-119">選擇 [**指派**，然後選擇 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="7a709-119">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="7a709-120">取消授權指派從裝置</span><span class="sxs-lookup"><span data-stu-id="7a709-120">Unassign licenses from devices</span></span>

<span data-ttu-id="7a709-121">當您取消授權指派從群組時時，請從群組中的所有裝置中移除授權。</span><span class="sxs-lookup"><span data-stu-id="7a709-121">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="7a709-122">所有應用程式和其相關聯的資料就唯讀屬性。</span><span class="sxs-lookup"><span data-stu-id="7a709-122">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="7a709-123">在 [系統管理中心中，移至**帳單** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7a709-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="7a709-124">在 [**授權**] 頁面上，選擇 [ **Office 365 專業增強版的教育版 （裝置）**。</span><span class="sxs-lookup"><span data-stu-id="7a709-124">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="7a709-125">在**Office 365 專業增強版的教育版 （裝置）** 頁面上，選擇 [訂用帳戶，選擇 [**更多動作**，然後選擇 [**解除指派授權**。</span><span class="sxs-lookup"><span data-stu-id="7a709-125">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
5. <span data-ttu-id="7a709-126">在 [**解除指派授權**] 對話方塊中，選擇 [**解除指派]**。</span><span class="sxs-lookup"><span data-stu-id="7a709-126">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>