---
title: EOP 中的功能權限
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: 執行工作以管理 Microsoft Exchange Online Protection (EOP) 所需的權限會視您正在管理的功能而異。
ms.openlocfilehash: 146bf34f157eb30e680ad9e0c3e53501d6e7b425
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638115"
---
# <a name="feature-permissions-in-eop"></a><span data-ttu-id="c0b88-103">EOP 中的功能權限</span><span class="sxs-lookup"><span data-stu-id="c0b88-103">Feature permissions in EOP</span></span>

<span data-ttu-id="c0b88-104">執行工作以管理 Exchange Online Protection （EOP）所需的許可權會視您正在管理的功能而異。</span><span class="sxs-lookup"><span data-stu-id="c0b88-104">The permissions required to perform tasks to manage Exchange Online Protection (EOP) vary depending on the feature you are managing.</span></span>

<span data-ttu-id="c0b88-105">若要設定 EOP，您必須是全域管理員或 Exchange 公司管理員（組織管理角色群組）。</span><span class="sxs-lookup"><span data-stu-id="c0b88-105">To set up EOP, you must be a global admin, or an Exchange Company Administrator (the Organization Management role group).</span></span>

## <a name="exchange-online-protection-permissions"></a><span data-ttu-id="c0b88-106">Exchange Online Protection 權限</span><span class="sxs-lookup"><span data-stu-id="c0b88-106">Exchange Online Protection permissions</span></span>

<span data-ttu-id="c0b88-p101">若要找出管理 EOP 功能需要什麼權限，請參閱下表。如果某項功能列出一個以上的角色群組，您只需要被指派其中一個角色群組即可使用此功能。</span><span class="sxs-lookup"><span data-stu-id="c0b88-p101">To find out what permissions you need to manage EOP features, see the following table. If a feature lists more than one role group, you only need to be assigned one of the role groups to use the feature.</span></span>

|<span data-ttu-id="c0b88-109">**功能**</span><span class="sxs-lookup"><span data-stu-id="c0b88-109">**Feature**</span></span>|<span data-ttu-id="c0b88-110">**必要的權限**</span><span class="sxs-lookup"><span data-stu-id="c0b88-110">**Permissions required**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0b88-111">反惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="c0b88-111">Anti-malware</span></span>|<span data-ttu-id="c0b88-112">組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-112">Organization Management</span></span> <br/><br/> <span data-ttu-id="c0b88-113">檢疫管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-113">Hygiene Management</span></span>|
|<span data-ttu-id="c0b88-114">反垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="c0b88-114">Anti-spam</span></span>|<span data-ttu-id="c0b88-115">組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-115">Organization Management</span></span> <br/><br/> <span data-ttu-id="c0b88-116">檢疫管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-116">Hygiene Management</span></span>|
|<span data-ttu-id="c0b88-117">郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="c0b88-117">Mail flow rules</span></span>|<span data-ttu-id="c0b88-118">組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-118">Organization Management</span></span> <br/><br/> <span data-ttu-id="c0b88-119">記錄管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-119">Records Management</span></span>|
|<span data-ttu-id="c0b88-120">網域</span><span class="sxs-lookup"><span data-stu-id="c0b88-120">Domains</span></span>|<span data-ttu-id="c0b88-121">組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-121">Organization Management</span></span> <br/><br/> <span data-ttu-id="c0b88-122">僅限檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-122">View-Only Organization Management</span></span>|
|<span data-ttu-id="c0b88-123">進階威脅防護 (ATP)</span><span class="sxs-lookup"><span data-stu-id="c0b88-123">Advanced Threat Protection (ATP)</span></span>|<span data-ttu-id="c0b88-124">組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-124">Organization Management</span></span> <br/><br/> <span data-ttu-id="c0b88-125">檢疫管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-125">Hygiene Management</span></span>|
|<span data-ttu-id="c0b88-126">Microsoft 365 連接器</span><span class="sxs-lookup"><span data-stu-id="c0b88-126">Microsoft 365 connectors</span></span>|<span data-ttu-id="c0b88-127">組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-127">Organization Management</span></span>|
|<span data-ttu-id="c0b88-128">郵件追蹤</span><span class="sxs-lookup"><span data-stu-id="c0b88-128">Message trace</span></span>|<span data-ttu-id="c0b88-129">組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-129">Organization Management</span></span> <br/><br/> <span data-ttu-id="c0b88-130">僅限檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-130">View-Only Organization Management</span></span>|
|<span data-ttu-id="c0b88-131">組織組態</span><span class="sxs-lookup"><span data-stu-id="c0b88-131">Organization configuration</span></span>|<span data-ttu-id="c0b88-132">組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-132">Organization Management</span></span>|
|<span data-ttu-id="c0b88-133">隔離</span><span class="sxs-lookup"><span data-stu-id="c0b88-133">Quarantine</span></span>|<span data-ttu-id="c0b88-134">組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-134">Organization Management</span></span> <br/><br/> <span data-ttu-id="c0b88-135">僅限檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-135">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="c0b88-136">檢疫管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-136">Hygiene Management</span></span>|
|<span data-ttu-id="c0b88-137">使用者、連絡人及角色群組</span><span class="sxs-lookup"><span data-stu-id="c0b88-137">Users, Contacts, and Role Groups</span></span>|<span data-ttu-id="c0b88-138">組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-138">Organization Management</span></span> <br/><br/> <span data-ttu-id="c0b88-139">僅限檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-139">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="c0b88-140">檢疫管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-140">Hygiene Management</span></span>|
|<span data-ttu-id="c0b88-141">通訊群組和安全性群組</span><span class="sxs-lookup"><span data-stu-id="c0b88-141">Distribution Groups and Security Groups</span></span>|<span data-ttu-id="c0b88-142">組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-142">Organization Management</span></span> <br/><br/> <span data-ttu-id="c0b88-143">僅限檢視組織管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-143">View-Only Organization Management</span></span> <br/><br/> <span data-ttu-id="c0b88-144">檢疫管理</span><span class="sxs-lookup"><span data-stu-id="c0b88-144">Hygiene Management</span></span>|
|<span data-ttu-id="c0b88-145">檢視報告</span><span class="sxs-lookup"><span data-stu-id="c0b88-145">View reports</span></span>|<span data-ttu-id="c0b88-146">組織管理：存取郵件保護報告。</span><span class="sxs-lookup"><span data-stu-id="c0b88-146">Organization Management: Access to mail protection reports.</span></span> <br/><br/> <span data-ttu-id="c0b88-147">View-Only 收件者：存取郵件保護報告。</span><span class="sxs-lookup"><span data-stu-id="c0b88-147">View-Only Recipients: Access to mail protection reports.</span></span>  <br/><br/> <span data-ttu-id="c0b88-148">規範管理：存取郵件保護報告及資料遺失防護（DLP）報告（如果您的訂閱具有 DLP 功能）。</span><span class="sxs-lookup"><span data-stu-id="c0b88-148">Compliance Management: Access to mail protection reports and Data Loss Prevention (DLP) reports (if your subscription has DLP capabilities).</span></span>|
