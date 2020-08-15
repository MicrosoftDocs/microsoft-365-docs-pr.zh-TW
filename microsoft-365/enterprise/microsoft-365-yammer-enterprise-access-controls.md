---
title: Microsoft 365 Yammer 企業版存取控制
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 本文包含在實際執行環境中 Yammer 企業存取控制的簡短摘要。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8bdf357ddd7f5c0b549d291fd4732924608085b9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695643"
---
# <a name="yammer-enterprise-access-controls"></a><span data-ttu-id="1d822-103">Yammer 企業存取控制</span><span class="sxs-lookup"><span data-stu-id="1d822-103">Yammer enterprise access controls</span></span> 

<span data-ttu-id="1d822-104">對 Yammer 實際執行環境所做的實際和邏輯存取，只限于一小組人員 (基礎結構和作業) 。</span><span class="sxs-lookup"><span data-stu-id="1d822-104">Physical and logical access to the Yammer production environment is restricted to a small set of people (infrastructure and operations).</span></span> <span data-ttu-id="1d822-105">與其他 Microsoft 365 工程師一樣，Yammer 工程師也可讓使用者存取客戶資料。</span><span class="sxs-lookup"><span data-stu-id="1d822-105">As with other Microsoft 365 engineers, Yammer engineers have zero standing access to customer data.</span></span> <span data-ttu-id="1d822-106">您必須使用具有有限的核准者的即時存取控制系統來要求存取，類似于密碼箱。</span><span class="sxs-lookup"><span data-stu-id="1d822-106">Access must be requested using an approval-based just-in-time access control system similar to Lockbox with a limited number of approvers.</span></span> <span data-ttu-id="1d822-107">核准者會驗證要求 (例如，他們會驗證要求是否根據需求、業務案例、時間等 ) 進行合法，然後核准或拒絕要求。</span><span class="sxs-lookup"><span data-stu-id="1d822-107">Approvers verify the request (for example, they verify whether the request is legitimate based on need, business case, time, etc.), and then approve or deny the request.</span></span> <span data-ttu-id="1d822-108">若要求遭到核准，就會將 JIT 存取權授與已定義和限制的時間。</span><span class="sxs-lookup"><span data-stu-id="1d822-108">If the request is approved, JIT access is granted for a defined and limited time.</span></span> <span data-ttu-id="1d822-109">超過存取時間之後，access 會自動到期。</span><span class="sxs-lookup"><span data-stu-id="1d822-109">After access time is exceeded, the access automatically expires.</span></span>

<span data-ttu-id="1d822-110">與其他 Microsoft 365 服務一樣，所有的 Yammer 實際執行環境存取都會使用多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="1d822-110">As with other Microsoft 365 services, all access to the Yammer production environment uses multi-factor authentication.</span></span> <span data-ttu-id="1d822-111">所有存取和命令歷史記錄都是由 Yammer 安全小組所交為使用者，並定期登入及檢查。</span><span class="sxs-lookup"><span data-stu-id="1d822-111">All access and command history is attributed to a user, and logged and reviewed regularly by the Yammer security team.</span></span>

<span data-ttu-id="1d822-112">如需 Yammer 管理和管理的詳細資訊，請參閱 [Yammer 系統管理](https://docs.microsoft.com/yammer/yammer-landing-page)說明。</span><span class="sxs-lookup"><span data-stu-id="1d822-112">For more information about Yammer administration and management, see [Yammer admin help](https://docs.microsoft.com/yammer/yammer-landing-page).</span></span>