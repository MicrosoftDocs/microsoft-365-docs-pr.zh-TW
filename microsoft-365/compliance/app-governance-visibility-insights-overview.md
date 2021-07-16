---
title: 了解可見度與深入解析
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
description: 了解可見度與深入解析。
ms.openlocfilehash: ee485c972193c515bafec55f58a7a89aa1f567f1
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420062"
---
# <a name="learn-about-visibility-and-insights"></a><span data-ttu-id="d5632-103">了解可見度與深入解析</span><span class="sxs-lookup"><span data-stu-id="d5632-103">Learn about visibility and insights</span></span>

><span data-ttu-id="d5632-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="d5632-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="d5632-105">使用 Microsoft 應用程式控管，您可以快速取得 Microsoft 365 應用程式生態系統的可見度與有意義的深入解析。</span><span class="sxs-lookup"><span data-stu-id="d5632-105">With Microsoft app governance, you can quickly gain visibility and meaningful insights on your Microsoft 365 application ecosystem.</span></span> <span data-ttu-id="d5632-106">您從應用程式控管儀表板開始，其中提供需要系統管理員注意之租用戶中警示和應用程式的高層級摘要。</span><span class="sxs-lookup"><span data-stu-id="d5632-106">You start from the app governance dashboard that provides a high-level summary of the alerts and apps in your tenant that require administrator attention.</span></span>

<span data-ttu-id="d5632-107">使用應用程式控管可見度與深入解析，您可以查看：</span><span class="sxs-lookup"><span data-stu-id="d5632-107">With app governance visibility and insights, you can see:</span></span>

- <span data-ttu-id="d5632-108">透過 Microsoft Graph API 存取 Microsoft 365 資料的啟用 OAuth 應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="d5632-108">A list of the OAuth-enabled apps that access Microsoft 365 data via Microsoft Graph APIs.</span></span>
- <span data-ttu-id="d5632-109">豐富的應用程式活動檢視，因此您可以回應或回覆它們。</span><span class="sxs-lookup"><span data-stu-id="d5632-109">A rich view on app activities so that you can react or respond to them.</span></span>

>[!Note]
><span data-ttu-id="d5632-110">未獲授予權限存取 Microsoft 365 資源的僅 Azure 應用程式不會顯示在應用程式控管中。</span><span class="sxs-lookup"><span data-stu-id="d5632-110">Azure-only apps that are not granted permissions to access Microsoft 365 resources are not displayed in app governance.</span></span>
>

<span data-ttu-id="d5632-111">請參閱 [系統管理員角色](app-governance-get-started.md#administrator-roles) ，以取得可見度與深入解析所需的系統管理員角色概觀。</span><span class="sxs-lookup"><span data-stu-id="d5632-111">See [administrator roles](app-governance-get-started.md#administrator-roles) for an overview of required administrator roles for visibility and insights.</span></span>

<!--
From messaging doc, page 21:

View M365 App List & Metadata
View M365 App List of Consented Users
View M365 App Permissions
View M365 App Permission Usage
View Over permissioned Apps
Aggregate M365 API Usage Data by Workload (count, download/upload)
Per-App M365 API Usage Data by Workload (count, download/upload)
Per-User M365 API Usage Data by Workload (count, download/upload)
M365 API Usage Data For High-Value/Classified Assets (count, download/upload)
M365 API Error Analysis per App
-->

<span data-ttu-id="d5632-112">使用應用程式控管，您可以看見：</span><span class="sxs-lookup"><span data-stu-id="d5632-112">With app governance, you can see:</span></span>

- <span data-ttu-id="d5632-113">所有深入解析的儀表板。</span><span class="sxs-lookup"><span data-stu-id="d5632-113">A dashboard of all insights.</span></span>
- <span data-ttu-id="d5632-114">使用工作負載和使用者層級深入解析的單一和所有應用程式存取的資料。</span><span class="sxs-lookup"><span data-stu-id="d5632-114">Data accessed by single and all apps with workload and user level insights.</span></span>
- <span data-ttu-id="d5632-115">應用程式資訊和中繼資料，例如權限、註冊日期和憑證。</span><span class="sxs-lookup"><span data-stu-id="d5632-115">App information and metadata, such as permissions, registration date, and certification.</span></span>
- <span data-ttu-id="d5632-116">發行者資訊和中繼資料，例如名稱和驗證狀態。</span><span class="sxs-lookup"><span data-stu-id="d5632-116">Publisher information and metadata, such as name and verification status.</span></span>
- <span data-ttu-id="d5632-117">租用戶之間的熱門資源（電子郵件和檔案）使用情況。</span><span class="sxs-lookup"><span data-stu-id="d5632-117">Usage of top resources (emails and files) across the tenant.</span></span>
- <span data-ttu-id="d5632-118">深入解析開啟：</span><span class="sxs-lookup"><span data-stu-id="d5632-118">Insights on:</span></span>

  - <span data-ttu-id="d5632-119">高權限應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5632-119">High-privileged apps.</span></span>
  - <span data-ttu-id="d5632-120">權限過高的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5632-120">Overprivileged apps.</span></span>
  - <span data-ttu-id="d5632-121">高使用率的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d5632-121">High-usage apps.</span></span>
  - <span data-ttu-id="d5632-122">特定應用程式可以存取其資料之最常同意的使用者。</span><span class="sxs-lookup"><span data-stu-id="d5632-122">Top consented users whose data a specific app can access.</span></span>
  - <span data-ttu-id="d5632-123">擁有特定應用程式可存取資料的優先帳戶。</span><span class="sxs-lookup"><span data-stu-id="d5632-123">Priority accounts who have data that a specific app can access.</span></span>

- <span data-ttu-id="d5632-124">使用者存取應用程式的累計檢視。</span><span class="sxs-lookup"><span data-stu-id="d5632-124">A cumulative view of users accessing apps.</span></span>
- <span data-ttu-id="d5632-125">警示深入解析。</span><span class="sxs-lookup"><span data-stu-id="d5632-125">Alerts insights.</span></span>
- <span data-ttu-id="d5632-126">原則清單深入解析。</span><span class="sxs-lookup"><span data-stu-id="d5632-126">Policy list insights.</span></span>
<span data-ttu-id="d5632-127"><!--></span><span class="sxs-lookup"><span data-stu-id="d5632-127"><!--></span></span>
- <span data-ttu-id="d5632-128">在應用程式控管入口網站中的 MCAS 中建立原則。</span><span class="sxs-lookup"><span data-stu-id="d5632-128">Policies created in MCAS in the app governance portal.</span></span>
-->
- <span data-ttu-id="d5632-129">在應用程式治理入口網站中的 MCAS 中產生的 OAuth 應用程式警示。</span><span class="sxs-lookup"><span data-stu-id="d5632-129">Alerts for OAuth apps generated in MCAS, in the app governance portal.</span></span>

<span data-ttu-id="d5632-130">您也可以：</span><span class="sxs-lookup"><span data-stu-id="d5632-130">You can also:</span></span>

- <span data-ttu-id="d5632-131">向下切入至具有所有關聯深入解析的單一應用程式（應用程式頁面）。</span><span class="sxs-lookup"><span data-stu-id="d5632-131">Drill down to a single app (app page) with all its associated insights.</span></span>
- <span data-ttu-id="d5632-132">根據資料向下切入至最熱門使用者，以及單一應用程式內的優先帳戶。</span><span class="sxs-lookup"><span data-stu-id="d5632-132">Drill-down into top users by data, and priority accounts within a single app.</span></span>

## <a name="next-step"></a><span data-ttu-id="d5632-133">後續步驟</span><span class="sxs-lookup"><span data-stu-id="d5632-133">Next step</span></span>

[<span data-ttu-id="d5632-134">開始使用應用程式深入解析。</span><span class="sxs-lookup"><span data-stu-id="d5632-134">Get started with application insights.</span></span>](app-governance-visibility-insights-get-started.md)
