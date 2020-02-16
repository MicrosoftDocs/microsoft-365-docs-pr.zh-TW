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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: 了解 Microsoft 365 商務版中的裝置狀態。
ms.openlocfilehash: 26b218cb7b6a14f17e33d34a2e712b06ac814c0c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065752"
---
# <a name="device-states"></a><span data-ttu-id="33161-103">裝置狀態</span><span class="sxs-lookup"><span data-stu-id="33161-103">Device states</span></span>

<span data-ttu-id="33161-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span><span class="sxs-lookup"><span data-stu-id="33161-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="33161-106">**狀態**</span><span class="sxs-lookup"><span data-stu-id="33161-106">**Status**</span></span>|<span data-ttu-id="33161-107">**描述**</span><span class="sxs-lookup"><span data-stu-id="33161-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="33161-108">由 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="33161-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="33161-109">由 Microsoft 365 商務版 管理。</span><span class="sxs-lookup"><span data-stu-id="33161-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="33161-110">淘汰擱置中</span><span class="sxs-lookup"><span data-stu-id="33161-110">Retire pending</span></span>  <br/> |<span data-ttu-id="33161-111">Microsoft 365 商務版 準備好要從裝置移除公司資料。</span><span class="sxs-lookup"><span data-stu-id="33161-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="33161-112">淘汰進行中</span><span class="sxs-lookup"><span data-stu-id="33161-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="33161-113">Microsoft 365 商務版 目前正在從裝置移除公司資料。</span><span class="sxs-lookup"><span data-stu-id="33161-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="33161-114">淘汰失敗</span><span class="sxs-lookup"><span data-stu-id="33161-114">Retire failed</span></span>  <br/> | <span data-ttu-id="33161-115">移除公司資料的動作失敗。</span><span class="sxs-lookup"><span data-stu-id="33161-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="33161-116">已取消淘汰</span><span class="sxs-lookup"><span data-stu-id="33161-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="33161-117">淘汰已取消的動作。</span><span class="sxs-lookup"><span data-stu-id="33161-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="33161-118">抹除擱置中</span><span class="sxs-lookup"><span data-stu-id="33161-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="33161-119">等待開始重設成出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="33161-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="33161-120">抹除進行中</span><span class="sxs-lookup"><span data-stu-id="33161-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="33161-121">已發出重設成出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="33161-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="33161-122">抹除失敗</span><span class="sxs-lookup"><span data-stu-id="33161-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="33161-123">無法執行原廠重設。</span><span class="sxs-lookup"><span data-stu-id="33161-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="33161-124">已取消抹除</span><span class="sxs-lookup"><span data-stu-id="33161-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="33161-125">出廠已取消此事件。</span><span class="sxs-lookup"><span data-stu-id="33161-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="33161-126">狀況不良</span><span class="sxs-lookup"><span data-stu-id="33161-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="33161-127">動作擱置中 （或進行中），但裝置尚未超過 30 天未曾簽入。</span><span class="sxs-lookup"><span data-stu-id="33161-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="33161-128">刪除擱置中</span><span class="sxs-lookup"><span data-stu-id="33161-128">Delete pending</span></span>  <br/> |<span data-ttu-id="33161-129">刪除動作擱置中。</span><span class="sxs-lookup"><span data-stu-id="33161-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="33161-130">已探索</span><span class="sxs-lookup"><span data-stu-id="33161-130">Discovered</span></span>  <br/> |<span data-ttu-id="33161-131">Microsoft 365 商務版 偵測到裝置。</span><span class="sxs-lookup"><span data-stu-id="33161-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
