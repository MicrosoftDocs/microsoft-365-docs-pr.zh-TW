---
title: Microsoft 受管理的桌面應用程式需求
description: ''
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 71952a8b073f002890cc95883e717aeb04c0cd68
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866103"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft 受管理的桌面應用程式需求

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreeement for MMD. do not delete.-->

<!--Application addendum -->
 
您想要部署至 Microsoft 受管理的桌上型電腦裝置的企業營運系統應用程式必須符合本主題中的需求。 

## <a name="application-condition"></a>應用程式的狀況

請務必應用程式不不良影響的 Microsoft 受管理的桌上型電腦環境。以下是應用程式必須符合為了讓 Microsoft 將其部署的需求。對於任何指定的應用程式或驅動程式，Microsoft 可能本指射提供任何需求。Microsoft 可能會決定要移除任何應用程式或造成負面影響效能與可靠性的 Microsoft 受管理的桌上型電腦裝置的驅動程式。

## <a name="deployable-using-microsoft-technologies"></a>可使用 Microsoft 技術部署

Microsoft 受管理的桌上型電腦使用 Intune、 Microsoft 存放區及 Microsoft Store for Business 部署應用程式。因此，應用程式必須封裝能夠部署由加上 then 目前版本的那些服務的方式。

## <a name="prohibited-app-classes"></a>禁止的 app 類別

Microsoft 受管理的桌上型電腦裝置上不允許的特定應用程式類型：
- 3rd 的廠商防毒、 安全性或稽核軟體
- 在 Office 365 Pro Plus 之前的 Microsoft Office 版本
- 安裝或將彙整其他 3rd 廠商軟體應用程式

## <a name="restricted-app-behaviors"></a>受限制的應用程式行為

某些應用程式的行為可以前者的使用者經驗或呈現 Microsoft 受管理的桌上型電腦裝置安全性風險。下列行為或特性，不應會呈現應用程式： 
- 安裝背景服務或即會衍生長時間執行背景處理程序
- 將其本身加入 Windows 啟動路徑
- 呼叫未記載之 Windows 或 Office Api 或採取內部 Windows 或 Office 資料結構相依性
- 做為應用程式商店或具有內建的擴充管理員
- 提高使用者的權限
- 有已知安全性弱點
- 使用不彙總為受信任的根憑證簽署
- 加密或限制存取使用者資料
- 在執行階段修改作業系統的程式碼

## <a name="driver-deployment"></a>驅動程式部署

除非驅動程式在 Windows Update 或分開簽署 Windows 硬體品質實驗室 (WHQL)、 Microsoft 必須在 Microsoft 會部署至 Microsoft 受管理的桌上型電腦裝置的驅動程式之前核准驅動程式。