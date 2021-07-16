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
# <a name="learn-about-app-policies"></a><span data-ttu-id="e32fa-103">了解應用程式原則</span><span class="sxs-lookup"><span data-stu-id="e32fa-103">Learn about app policies</span></span>

><span data-ttu-id="e32fa-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="e32fa-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="e32fa-105">Microsoft 應用程式控管會偵測您 Microsoft 365 租用戶中的異常應用程式行為，並產生警示並讓您可以進行查看、調查及解決。</span><span class="sxs-lookup"><span data-stu-id="e32fa-105">Microsoft app governance detects anomalous app behavior in your Microsoft 365 tenant and generates alerts that you can see, investigate, and resolve.</span></span> <span data-ttu-id="e32fa-106">除了這個內建的偵測功能之外，您還可以使用一組預設範本以建立自己的應用程式原則，以產生其他警示。</span><span class="sxs-lookup"><span data-stu-id="e32fa-106">Beyond this built-in detection capability, you can use a set of default templates to create your own app policies that generate other alerts.</span></span>

<span data-ttu-id="e32fa-107">這些適用於應用程式、使用者模式及行為的原則可保護您的使用者，避免使用不符合規範或惡意的應用程式，並限制危險應用程式存取您的租用戶資料。</span><span class="sxs-lookup"><span data-stu-id="e32fa-107">These policies for app and user patterns and behaviors can protect your users from using non-compliant or malicious apps and limit the access of risky apps to your tenant data.</span></span>

<span data-ttu-id="e32fa-108">以下是應用程式原則管理所需的系統管理員角色的快速檢視。</span><span class="sxs-lookup"><span data-stu-id="e32fa-108">Here's a quick review of required administrator roles for app policy management.</span></span>

| <span data-ttu-id="e32fa-109">角色</span><span class="sxs-lookup"><span data-stu-id="e32fa-109">Role</span></span> | <span data-ttu-id="e32fa-110">讀取原則</span><span class="sxs-lookup"><span data-stu-id="e32fa-110">Read policies</span></span> | <span data-ttu-id="e32fa-111">建立、更新或刪除原則</span><span class="sxs-lookup"><span data-stu-id="e32fa-111">Create, update, or delete policies</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="e32fa-112">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="e32fa-112">Compliance Administrator</span></span> | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |
| <span data-ttu-id="e32fa-115">合規性讀取者</span><span class="sxs-lookup"><span data-stu-id="e32fa-115">Compliance Reader</span></span> | ![核取記號](..\media\checkmark.png) |  |
| <span data-ttu-id="e32fa-117">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="e32fa-117">Global Administrator</span></span> | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |
| <span data-ttu-id="e32fa-120">全域讀取者</span><span class="sxs-lookup"><span data-stu-id="e32fa-120">Global Reader</span></span>  | ![核取記號](..\media\checkmark.png) |  |
| <span data-ttu-id="e32fa-122">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="e32fa-122">Security Administrator</span></span> | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |
| <span data-ttu-id="e32fa-125">安全性讀取者</span><span class="sxs-lookup"><span data-stu-id="e32fa-125">Security Reader</span></span>  | ![核取記號](..\media\checkmark.png) |  |
| <span data-ttu-id="e32fa-127">安全性操作員</span><span class="sxs-lookup"><span data-stu-id="e32fa-127">Security Operator</span></span> | ![核取記號](..\media\checkmark.png) | ![核取記號](..\media\checkmark.png) |
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

## <a name="next-step"></a><span data-ttu-id="e32fa-130">後續步驟</span><span class="sxs-lookup"><span data-stu-id="e32fa-130">Next step</span></span>

[<span data-ttu-id="e32fa-131">開始使用應用程式原則。</span><span class="sxs-lookup"><span data-stu-id="e32fa-131">Get started with app policies.</span></span>](app-governance-app-policies-get-started.md)
