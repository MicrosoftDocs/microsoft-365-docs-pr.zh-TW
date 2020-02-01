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
ms.openlocfilehash: 02b4eebac62a48e3ddd53d362db2d60067ac05eb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593964"
---
# <a name="device-states"></a>裝置狀態

Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**狀態**|**描述**|
|:-----|:-----|
|由 Intune 管理  <br/> |由 Microsoft 365 商務版 管理。  <br/> |
|淘汰擱置中  <br/> |Microsoft 365 商務版 準備好要從裝置移除公司資料。  <br/> |
|淘汰進行中  <br/> |Microsoft 365 商務版 目前正在從裝置移除公司資料。  <br/> |
|淘汰失敗  <br/> | 移除公司資料的動作失敗。  <br/> |
|已取消淘汰  <br/> |淘汰已取消的動作。  <br/> |
|抹除擱置中  <br/> |等待開始重設成出廠預設值。  <br/> |
|抹除進行中  <br/> |已發出重設成出廠預設值。  <br/> |
|抹除失敗  <br/> |無法執行原廠重設。  <br/> |
|已取消抹除  <br/> |出廠已取消此事件。  <br/> |
|狀況不良  <br/> |動作擱置中 （或進行中），但裝置尚未超過 30 天未曾簽入。  <br/> |
|刪除擱置中  <br/> |刪除動作擱置中。  <br/> |
|已探索  <br/> |Microsoft 365 商務版 偵測到裝置。  <br/> |
   
