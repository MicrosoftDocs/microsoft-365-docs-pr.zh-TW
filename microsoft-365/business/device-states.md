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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: 深入瞭解 Microsoft 365 for business 中的 [系統管理] 主裝置的 [裝置動作] 清單中的各種裝置狀態。
ms.openlocfilehash: 1a66e76dd3a74428923292427b01551db2449e48
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627239"
---
# <a name="device-states"></a><span data-ttu-id="d8a5d-103">裝置狀態</span><span class="sxs-lookup"><span data-stu-id="d8a5d-103">Device states</span></span>

<span data-ttu-id="d8a5d-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span><span class="sxs-lookup"><span data-stu-id="d8a5d-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="d8a5d-106">**狀態**</span><span class="sxs-lookup"><span data-stu-id="d8a5d-106">**Status**</span></span>|<span data-ttu-id="d8a5d-107">**描述**</span><span class="sxs-lookup"><span data-stu-id="d8a5d-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8a5d-108">由 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="d8a5d-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="d8a5d-109">由 Microsoft 365 商務版 Premium 所管理。</span><span class="sxs-lookup"><span data-stu-id="d8a5d-109">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="d8a5d-110">淘汰擱置中</span><span class="sxs-lookup"><span data-stu-id="d8a5d-110">Retire pending</span></span>  <br/> |<span data-ttu-id="d8a5d-111">Microsoft 365 商務版功能即將準備好從裝置中移除公司資料。</span><span class="sxs-lookup"><span data-stu-id="d8a5d-111">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="d8a5d-112">淘汰進行中</span><span class="sxs-lookup"><span data-stu-id="d8a5d-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="d8a5d-113">Microsoft 365 商務版 Premium 目前從裝置移除公司資料。</span><span class="sxs-lookup"><span data-stu-id="d8a5d-113">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="d8a5d-114">淘汰失敗</span><span class="sxs-lookup"><span data-stu-id="d8a5d-114">Retire failed</span></span>  <br/> | <span data-ttu-id="d8a5d-115">移除公司資料的動作失敗。</span><span class="sxs-lookup"><span data-stu-id="d8a5d-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="d8a5d-116">取消停用</span><span class="sxs-lookup"><span data-stu-id="d8a5d-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="d8a5d-117">取消停用動作。</span><span class="sxs-lookup"><span data-stu-id="d8a5d-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="d8a5d-118">抹除擱置中</span><span class="sxs-lookup"><span data-stu-id="d8a5d-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="d8a5d-119">等待開始重設成出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="d8a5d-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="d8a5d-120">抹除進行中</span><span class="sxs-lookup"><span data-stu-id="d8a5d-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="d8a5d-121">已發出重設成出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="d8a5d-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="d8a5d-122">抹除失敗</span><span class="sxs-lookup"><span data-stu-id="d8a5d-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="d8a5d-123">無法進行原始重設。</span><span class="sxs-lookup"><span data-stu-id="d8a5d-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="d8a5d-124">取消擦除</span><span class="sxs-lookup"><span data-stu-id="d8a5d-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="d8a5d-125">已取消工廠清除。</span><span class="sxs-lookup"><span data-stu-id="d8a5d-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="d8a5d-126">狀況不良</span><span class="sxs-lookup"><span data-stu-id="d8a5d-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="d8a5d-127">動作暫止（或進行中），但裝置尚未簽入時30天。</span><span class="sxs-lookup"><span data-stu-id="d8a5d-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="d8a5d-128">刪除擱置中</span><span class="sxs-lookup"><span data-stu-id="d8a5d-128">Delete pending</span></span>  <br/> |<span data-ttu-id="d8a5d-129">刪除動作擱置中。</span><span class="sxs-lookup"><span data-stu-id="d8a5d-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="d8a5d-130">已探索</span><span class="sxs-lookup"><span data-stu-id="d8a5d-130">Discovered</span></span>  <br/> |<span data-ttu-id="d8a5d-131">Microsoft 365 商務版 Premium 已偵測到裝置。</span><span class="sxs-lookup"><span data-stu-id="d8a5d-131">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
