---
title: 裝置狀態
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: 深入瞭解在商務用 Microsoft 365 中的 [系統管理] 的 [裝置動作] 清單中的各種裝置狀態。
ms.openlocfilehash: e6f1b428413d094e0a1ce3afb026528074038736
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578460"
---
# <a name="device-states"></a><span data-ttu-id="8d6c0-103">裝置狀態</span><span class="sxs-lookup"><span data-stu-id="8d6c0-103">Device states</span></span>

<span data-ttu-id="8d6c0-104">本文適用于 Microsoft 365 商務進階版。</span><span class="sxs-lookup"><span data-stu-id="8d6c0-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="8d6c0-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span><span class="sxs-lookup"><span data-stu-id="8d6c0-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="8d6c0-107">**狀態**</span><span class="sxs-lookup"><span data-stu-id="8d6c0-107">**Status**</span></span>|<span data-ttu-id="8d6c0-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="8d6c0-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8d6c0-109">由 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="8d6c0-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="8d6c0-110">由 Microsoft 365 商務進階版所管理。</span><span class="sxs-lookup"><span data-stu-id="8d6c0-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="8d6c0-111">淘汰擱置中</span><span class="sxs-lookup"><span data-stu-id="8d6c0-111">Retire pending</span></span>  <br/> |<span data-ttu-id="8d6c0-112">Microsoft 365 商務進階版即將準備好從裝置中移除公司資料。</span><span class="sxs-lookup"><span data-stu-id="8d6c0-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="8d6c0-113">淘汰進行中</span><span class="sxs-lookup"><span data-stu-id="8d6c0-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="8d6c0-114">Microsoft 365 商務進階版目前從裝置移除公司資料。</span><span class="sxs-lookup"><span data-stu-id="8d6c0-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="8d6c0-115">淘汰失敗</span><span class="sxs-lookup"><span data-stu-id="8d6c0-115">Retire failed</span></span>  <br/> | <span data-ttu-id="8d6c0-116">移除公司資料的動作失敗。</span><span class="sxs-lookup"><span data-stu-id="8d6c0-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="8d6c0-117">取消停用</span><span class="sxs-lookup"><span data-stu-id="8d6c0-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="8d6c0-118">取消停用動作。</span><span class="sxs-lookup"><span data-stu-id="8d6c0-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="8d6c0-119">抹除擱置中</span><span class="sxs-lookup"><span data-stu-id="8d6c0-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="8d6c0-120">等待開始重設成出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="8d6c0-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="8d6c0-121">抹除進行中</span><span class="sxs-lookup"><span data-stu-id="8d6c0-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="8d6c0-122">已發出重設成出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="8d6c0-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="8d6c0-123">抹除失敗</span><span class="sxs-lookup"><span data-stu-id="8d6c0-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="8d6c0-124">無法進行原始重設。</span><span class="sxs-lookup"><span data-stu-id="8d6c0-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="8d6c0-125">取消擦除</span><span class="sxs-lookup"><span data-stu-id="8d6c0-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="8d6c0-126">已取消工廠清除。</span><span class="sxs-lookup"><span data-stu-id="8d6c0-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="8d6c0-127">狀況不良</span><span class="sxs-lookup"><span data-stu-id="8d6c0-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="8d6c0-128">動作處於擱置狀態 (或正在進行中) ，但裝置尚未檢查30天以上的時間。</span><span class="sxs-lookup"><span data-stu-id="8d6c0-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="8d6c0-129">刪除擱置中</span><span class="sxs-lookup"><span data-stu-id="8d6c0-129">Delete pending</span></span>  <br/> |<span data-ttu-id="8d6c0-130">刪除動作擱置中。</span><span class="sxs-lookup"><span data-stu-id="8d6c0-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="8d6c0-131">已探索</span><span class="sxs-lookup"><span data-stu-id="8d6c0-131">Discovered</span></span>  <br/> |<span data-ttu-id="8d6c0-132">Microsoft 365 商務進階版偵測到裝置。</span><span class="sxs-lookup"><span data-stu-id="8d6c0-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
