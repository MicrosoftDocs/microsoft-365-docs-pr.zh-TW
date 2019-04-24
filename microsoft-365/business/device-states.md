---
title: 裝置狀態
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: 了解 Microsoft 365 商務版中的裝置狀態。
ms.openlocfilehash: 15114835a5014f5bfac600eac79bcdffdaec481a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276957"
---
# <a name="device-states"></a><span data-ttu-id="a6ce2-103">裝置狀態</span><span class="sxs-lookup"><span data-stu-id="a6ce2-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="a6ce2-104">裝置狀態</span><span class="sxs-lookup"><span data-stu-id="a6ce2-104">Device states</span></span>

<span data-ttu-id="a6ce2-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span><span class="sxs-lookup"><span data-stu-id="a6ce2-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="a6ce2-107">**狀態**</span><span class="sxs-lookup"><span data-stu-id="a6ce2-107">**Status**</span></span>|<span data-ttu-id="a6ce2-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="a6ce2-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a6ce2-109">由 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="a6ce2-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="a6ce2-110">由 Microsoft 365 商務版 管理。</span><span class="sxs-lookup"><span data-stu-id="a6ce2-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="a6ce2-111">淘汰擱置中</span><span class="sxs-lookup"><span data-stu-id="a6ce2-111">Retire pending</span></span>  <br/> |<span data-ttu-id="a6ce2-112">Microsoft 365 商務版 準備好要從裝置移除公司資料。</span><span class="sxs-lookup"><span data-stu-id="a6ce2-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="a6ce2-113">淘汰進行中</span><span class="sxs-lookup"><span data-stu-id="a6ce2-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="a6ce2-114">Microsoft 365 商務版 目前正在從裝置移除公司資料。</span><span class="sxs-lookup"><span data-stu-id="a6ce2-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="a6ce2-115">淘汰失敗</span><span class="sxs-lookup"><span data-stu-id="a6ce2-115">Retire failed</span></span>  <br/> | <span data-ttu-id="a6ce2-116">移除公司資料的動作失敗。</span><span class="sxs-lookup"><span data-stu-id="a6ce2-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="a6ce2-117">已取消淘汰</span><span class="sxs-lookup"><span data-stu-id="a6ce2-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="a6ce2-118">已取消淘汰動作。</span><span class="sxs-lookup"><span data-stu-id="a6ce2-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="a6ce2-119">抹除擱置中</span><span class="sxs-lookup"><span data-stu-id="a6ce2-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="a6ce2-120">等待開始重設成出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="a6ce2-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="a6ce2-121">抹除進行中</span><span class="sxs-lookup"><span data-stu-id="a6ce2-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="a6ce2-122">已發出重設成出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="a6ce2-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="a6ce2-123">抹除失敗</span><span class="sxs-lookup"><span data-stu-id="a6ce2-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="a6ce2-124">無法執行重設成出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="a6ce2-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="a6ce2-125">已取消抹除</span><span class="sxs-lookup"><span data-stu-id="a6ce2-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="a6ce2-126">已取消重設成出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="a6ce2-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="a6ce2-127">狀況不良</span><span class="sxs-lookup"><span data-stu-id="a6ce2-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="a6ce2-128">這表示動作擱置中 (或進行中)，但裝置已超過 30 天未曾簽入。</span><span class="sxs-lookup"><span data-stu-id="a6ce2-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="a6ce2-129">刪除擱置中</span><span class="sxs-lookup"><span data-stu-id="a6ce2-129">Delete pending</span></span>  <br/> |<span data-ttu-id="a6ce2-130">刪除動作擱置中。</span><span class="sxs-lookup"><span data-stu-id="a6ce2-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="a6ce2-131">已探索</span><span class="sxs-lookup"><span data-stu-id="a6ce2-131">Discovered</span></span>  <br/> |<span data-ttu-id="a6ce2-132">Microsoft 365 商務版 偵測到裝置。</span><span class="sxs-lookup"><span data-stu-id="a6ce2-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
