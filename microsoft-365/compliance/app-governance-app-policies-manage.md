---
title: 管理應用程式原則
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 管理您的應用程式控管原則。
ms.openlocfilehash: 756402f86d6b65d48afb02c49b3e5bfc4e73fe3d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420094"
---
# <a name="manage-app-policies"></a><span data-ttu-id="21b23-103">管理應用程式原則</span><span class="sxs-lookup"><span data-stu-id="21b23-103">Manage app policies</span></span>

><span data-ttu-id="21b23-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="21b23-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="21b23-105">為了跟上組織正在使用的最新應用程式、回應新的應用程式型攻擊以及應對應用程式合規性需求的持續變更，您可能需要透過以下方式管理您的應用程式原則：</span><span class="sxs-lookup"><span data-stu-id="21b23-105">To keep up with the latest apps your organization is using, respond to new app-based attacks, and for ongoing changes to your app compliance needs, you might need to manage your app policies in these ways:</span></span>

- <span data-ttu-id="21b23-106">建立針對新應用程式的新原則</span><span class="sxs-lookup"><span data-stu-id="21b23-106">Create new policies targeted at new apps</span></span>
- <span data-ttu-id="21b23-107">變更現有原則的狀態 (使用中、非使用中、稽核模式)</span><span class="sxs-lookup"><span data-stu-id="21b23-107">Change the status of an existing policy (active, inactive, audit mode)</span></span>
- <span data-ttu-id="21b23-108">變更現有原則的條件</span><span class="sxs-lookup"><span data-stu-id="21b23-108">Change the conditions of an existing policy</span></span>
- <span data-ttu-id="21b23-109">變更現有原則的動作，以自動補救警示</span><span class="sxs-lookup"><span data-stu-id="21b23-109">Change the actions of an existing policy for auto-remediation of alerts</span></span>

<span data-ttu-id="21b23-110">以下是管理現有原則的程序範例：</span><span class="sxs-lookup"><span data-stu-id="21b23-110">Here's an example of a process for managing an existing policy:</span></span>

1. <span data-ttu-id="21b23-111">編輯原則：</span><span class="sxs-lookup"><span data-stu-id="21b23-111">Edit the policy:</span></span>

  - <span data-ttu-id="21b23-112">變更原則的設定。</span><span class="sxs-lookup"><span data-stu-id="21b23-112">Change the settings of the policy.</span></span>
  - <span data-ttu-id="21b23-113">如有必要，將狀態變更為 **[稽核模式]** 以進行測試。</span><span class="sxs-lookup"><span data-stu-id="21b23-113">If needed, change the status to **Audit mode** for testing.</span></span>

2. <span data-ttu-id="21b23-114">檢查預期的行為，例如產生的警示。</span><span class="sxs-lookup"><span data-stu-id="21b23-114">Check for expected behavior, such as alerts generated.</span></span>
1. <span data-ttu-id="21b23-115">如果這是非預期的行為，請回到步驟 1。</span><span class="sxs-lookup"><span data-stu-id="21b23-115">If the behavior is not expected, go back to step 1.</span></span>
1. <span data-ttu-id="21b23-116">如果這是預期的行為，請編輯該原則，並將其狀態變更為使用中 (如果需要)。</span><span class="sxs-lookup"><span data-stu-id="21b23-116">If the behavior is expected, edit the policy and change its status to active (if needed).</span></span>

![管理應用程式原則工作流程](../media/manage-app-protection-governance/mapg-manage-policy-process.png)

## <a name="editing-an-app-policy-configuration"></a><span data-ttu-id="21b23-118">編輯應用程式原則設定</span><span class="sxs-lookup"><span data-stu-id="21b23-118">Editing an app policy configuration</span></span>

<span data-ttu-id="21b23-119">若要變更現有應用程式原則的設定：</span><span class="sxs-lookup"><span data-stu-id="21b23-119">To change the configuration of an existing app policy:</span></span>

- <span data-ttu-id="21b23-120">在原則清單中選取原則，然後選取應用程式原則窗格上的 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="21b23-120">Select the policy in the policy list, and then select **Edit** on the app policy pane.</span></span>
- <span data-ttu-id="21b23-121">在清單中選取原則的垂直省略號，然後選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="21b23-121">Select the vertical ellipses for the policy in the list, and then select **Edit**.</span></span>

<span data-ttu-id="21b23-122">在 **[編輯原則]** 頁面，請逐步瀏覽頁面，然後進行適當的變更：</span><span class="sxs-lookup"><span data-stu-id="21b23-122">For the **Edit policy** page, step through the pages and make the appropriate changes:</span></span>

- <span data-ttu-id="21b23-123">**描述**：變更描述，以便更容易了解此原則的用途。</span><span class="sxs-lookup"><span data-stu-id="21b23-123">**Description**: Change the description to make it easier to understand the policy's purpose.</span></span>
- <span data-ttu-id="21b23-124">**嚴重性**</span><span class="sxs-lookup"><span data-stu-id="21b23-124">**Severity**</span></span>
- <span data-ttu-id="21b23-125">**原則設定**： 變更要套用原則的應用程式集。</span><span class="sxs-lookup"><span data-stu-id="21b23-125">**Policy settings**: Change the set of apps to which the policy applies.</span></span> <span data-ttu-id="21b23-126">您也可以選擇使用現有條件或修改條件</span><span class="sxs-lookup"><span data-stu-id="21b23-126">You can also choose to use the existing conditions or modify the conditions</span></span>
- <span data-ttu-id="21b23-127">**動作**：變更由該原則產生之警示的自動補救動作。</span><span class="sxs-lookup"><span data-stu-id="21b23-127">**Actions**: Change the auto-remediation action for alerts generated by the policy.</span></span>
- <span data-ttu-id="21b23-128">**狀態**：變更原則狀態。</span><span class="sxs-lookup"><span data-stu-id="21b23-128">**Status**: Change the policy status.</span></span>

## <a name="deleting-an-app-policy"></a><span data-ttu-id="21b23-129">刪除應用程式原則</span><span class="sxs-lookup"><span data-stu-id="21b23-129">Deleting an app policy</span></span>

<span data-ttu-id="21b23-130">若要刪除應用程式原則，您可以：</span><span class="sxs-lookup"><span data-stu-id="21b23-130">To delete an app policy, you can:</span></span>

- <span data-ttu-id="21b23-131">在原則清單中選取原則，然後選取應用程式原則窗格上的 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="21b23-131">Select the policy in the policy list, and then select **Delete** on the app policy pane.</span></span>
- <span data-ttu-id="21b23-132">在清單中選取原則的垂直省略號，然後選取 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="21b23-132">Select the vertical ellipses for the policy in the list, and then select **Delete**.</span></span>

<span data-ttu-id="21b23-133">刪除應用程式原則的替代方法是將其狀態變更為非使用中。</span><span class="sxs-lookup"><span data-stu-id="21b23-133">An alternative to deleting an app policy is to change its status to inactive.</span></span> <span data-ttu-id="21b23-134">處於非使用中後，它將不會產生警示。</span><span class="sxs-lookup"><span data-stu-id="21b23-134">Once inactive, it will not generate alerts.</span></span> <span data-ttu-id="21b23-135">例如，與其刪除具有一組對未來原則有用之特定條件的應用程式的應用程式原則，不如重命名應用程式原則，以表明其有用性並將其狀態設定為非使用中。</span><span class="sxs-lookup"><span data-stu-id="21b23-135">For example, rather than deleting an app policy for an app with a specific set of conditions that are useful for a future policy, rename the app policy to indicate its usefulness and set its status to inactive.</span></span> <span data-ttu-id="21b23-136">您可以稍後返回到該原則並針對類似應用程式修改該原則，並將其狀態設定為稽核模式或非使用中狀態。</span><span class="sxs-lookup"><span data-stu-id="21b23-136">You can later return to the policy and modify it for a similar app and set its status to audit mode or inactive.</span></span>
