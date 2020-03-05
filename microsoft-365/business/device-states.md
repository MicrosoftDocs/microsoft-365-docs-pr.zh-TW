---
title: 裝置狀態
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: 了解在裝置動作] 清單中系統管理員首頁 Microsoft 365 商務版中的各種裝置狀態。
ms.openlocfilehash: cb1e5172a6e2d0bfc5748fe982024ead26e8cd62
ms.sourcegitcommit: d6c871bf3f94d9299d22695f5dbaf25dc1bd6ff9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417309"
---
# <a name="device-states"></a><span data-ttu-id="08f33-103">裝置狀態</span><span class="sxs-lookup"><span data-stu-id="08f33-103">Device states</span></span>

<span data-ttu-id="08f33-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span><span class="sxs-lookup"><span data-stu-id="08f33-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="08f33-106">**狀態**</span><span class="sxs-lookup"><span data-stu-id="08f33-106">**Status**</span></span>|<span data-ttu-id="08f33-107">**描述**</span><span class="sxs-lookup"><span data-stu-id="08f33-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="08f33-108">由 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="08f33-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="08f33-109">由 Microsoft 365 商務版 管理。</span><span class="sxs-lookup"><span data-stu-id="08f33-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="08f33-110">淘汰擱置中</span><span class="sxs-lookup"><span data-stu-id="08f33-110">Retire pending</span></span>  <br/> |<span data-ttu-id="08f33-111">Microsoft 365 商務版 準備好要從裝置移除公司資料。</span><span class="sxs-lookup"><span data-stu-id="08f33-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="08f33-112">淘汰進行中</span><span class="sxs-lookup"><span data-stu-id="08f33-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="08f33-113">Microsoft 365 商務版 目前正在從裝置移除公司資料。</span><span class="sxs-lookup"><span data-stu-id="08f33-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="08f33-114">淘汰失敗</span><span class="sxs-lookup"><span data-stu-id="08f33-114">Retire failed</span></span>  <br/> | <span data-ttu-id="08f33-115">移除公司資料的動作失敗。</span><span class="sxs-lookup"><span data-stu-id="08f33-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="08f33-116">已取消淘汰</span><span class="sxs-lookup"><span data-stu-id="08f33-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="08f33-117">淘汰已取消的動作。</span><span class="sxs-lookup"><span data-stu-id="08f33-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="08f33-118">抹除擱置中</span><span class="sxs-lookup"><span data-stu-id="08f33-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="08f33-119">等待開始重設成出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="08f33-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="08f33-120">抹除進行中</span><span class="sxs-lookup"><span data-stu-id="08f33-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="08f33-121">已發出重設成出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="08f33-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="08f33-122">抹除失敗</span><span class="sxs-lookup"><span data-stu-id="08f33-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="08f33-123">無法執行原廠重設。</span><span class="sxs-lookup"><span data-stu-id="08f33-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="08f33-124">已取消抹除</span><span class="sxs-lookup"><span data-stu-id="08f33-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="08f33-125">出廠已取消此事件。</span><span class="sxs-lookup"><span data-stu-id="08f33-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="08f33-126">狀況不良</span><span class="sxs-lookup"><span data-stu-id="08f33-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="08f33-127">動作擱置中 （或進行中），但裝置尚未超過 30 天未曾簽入。</span><span class="sxs-lookup"><span data-stu-id="08f33-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="08f33-128">刪除擱置中</span><span class="sxs-lookup"><span data-stu-id="08f33-128">Delete pending</span></span>  <br/> |<span data-ttu-id="08f33-129">刪除動作擱置中。</span><span class="sxs-lookup"><span data-stu-id="08f33-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="08f33-130">已探索</span><span class="sxs-lookup"><span data-stu-id="08f33-130">Discovered</span></span>  <br/> |<span data-ttu-id="08f33-131">Microsoft 365 商務版 偵測到裝置。</span><span class="sxs-lookup"><span data-stu-id="08f33-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
