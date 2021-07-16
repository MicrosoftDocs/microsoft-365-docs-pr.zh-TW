---
title: 了解應用程式原則
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
description: 了解應用程式原則。
ms.openlocfilehash: 6d4ff23ca0e09f5e410d32d6ced144afc0c4bb15
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420081"
---
# <a name="learn-about-app-policies"></a>了解應用程式原則

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*

Microsoft 應用程式控管會偵測您 Microsoft 365 租用戶中的異常應用程式行為，並產生警示並讓您可以進行查看、調查及解決。 除了這個內建的偵測功能之外，您還可以使用一組預設範本以建立自己的應用程式原則，以產生其他警示。

這些適用於應用程式、使用者模式及行為的原則可保護您的使用者，避免使用不符合規範或惡意的應用程式，並限制危險應用程式存取您的租用戶資料。

以下是應用程式原則管理所需的系統管理員角色的快速檢視。

| 角色 | 讀取原則 | 建立、更新或刪除原則 |
|:-------|:-----|:-------|
| 合規性系統管理員 | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |
| 合規性讀取者 | ![核取記號](..\media\checkmark.png) |  |
| 全域系統管理員 | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |
| 全域讀取者  | ![核取記號](..\media\checkmark.png) |  |
| 安全性系統管理員 | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |
| 安全性讀取者  | ![核取記號](..\media\checkmark.png) |  |
| 安全性操作員 | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |
||||

<!--
How app policies are the method by which MAPG detects app anomolies resulting in detection (alerts) and remediation (manual or automatic) 


CFA #2 Scenario 1: As an admin, I can quickly set up policies to govern M365 apps in my tenant using MAPG out-of-the-box templates
CFA #2 Scenario 2: As an admin, I can create customized policies to govern M365 apps in my tenant to meet my organizations requirements.
CFA #2 Scenario 3: As an admin or policy reviewer, I can view all policies created in my environment and quickly see which policies have associated alerts. 
CFA #2 Scenario 4: As an admin, I can adjust policies efficiently to meet changing needs.

App policy templates

- Basic info
- Policy settings and conditions
- Actions
- Status

--> 

## <a name="next-step"></a>後續步驟

[開始使用應用程式原則。](app-governance-app-policies-get-started.md)
