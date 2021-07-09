---
title: 建立精確資料比對活動的通知
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何建立精確資料比對活動的通知。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 263dc319d7e7d3ee5f12ebe374e8f5bd44c4cc8c
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341673"
---
# <a name="create-notifications-for-exact-data-match-activities"></a>建立精確資料比對活動的通知

在[使用資料完全相符 (EDM) 建立自訂敏感性資訊類型時](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)，在[稽核記錄](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log)中會建立許多活動。 您可以使用 [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell Cmdlet建立通知，讓您知道這些活動何時發生：

- CreateSchema
- EditSchema
- RemoveSchema
- UploadDataFailed
- UploadDataCompleted

## <a name="pre-requisites"></a>先決條件

使用的帳戶必須屬於下列其中一個角色：

- 全域系統管理員
- 合規性系統管理員
- Exchange Online 系統管理員

若要進一步了解 DLP 權限，請參閱[權限](data-loss-prevention-policies.md#permissions)。

這些訂閱中包含 EDM 型分類:

- Office 365 E5
- Microsoft 365 E5
- Microsoft 365 E5 合規性
- Microsoft E5/A5 資訊保護和控管

如要深入了解 DLP 授權，請參閱 [Microsoft 365 安全性與合規性的授權指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。

## <a name="configure-notifications-for-edm-activities"></a>設定 EDM 活動的通知

1. 連線到[安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

2. 使用您想建立通知的活動執行 `New-ProtectionAlert` Cmdlet。  例如，如果您想要在 **UploadDataCompleted** 動作發生時收到通知，執行:

    ```powershell
    New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <address to send notification to> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
    ```
    
    如果是 **UploadDataFailed**，您可以執行:
    
    ```powershell
    New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <SMTP address to send notification to> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
    ```

## <a name="related-articles"></a>相關文章

- [使用資料完全相符 (EDM) 建立自訂敏感性資訊類型](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert)