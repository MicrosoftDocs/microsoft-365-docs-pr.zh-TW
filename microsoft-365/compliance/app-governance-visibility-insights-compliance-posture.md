---
title: 判斷您的應用程式合規性狀況
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
description: 判斷您的應用程式合規性狀況。
ms.openlocfilehash: 152f68e8fe0e7d7340d2e048bc73684bc079386f
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438021"
---
# <a name="determine-your-app-compliance-posture"></a><span data-ttu-id="1c4eb-103">判斷您的應用程式合規性狀況</span><span class="sxs-lookup"><span data-stu-id="1c4eb-103">Determine your app compliance posture</span></span>

><span data-ttu-id="1c4eb-104">*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="1c4eb-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="1c4eb-105">Microsoft 應用程式控管可讓您從 [Microsoft 365 合規性中心](https://aka.ms/appgovernance) 的應用程式控管概觀頁面，快速評估協力廠商應用程式的合規性狀況，及其對於您 Microsoft 365 租用戶中的資料存取權。</span><span class="sxs-lookup"><span data-stu-id="1c4eb-105">Microsoft app governance allows you to quickly assess the compliance posture of the third-party apps and their access to data in your Microsoft 365 tenant from the app governance Overview page in the [Microsoft 365 Compliance Center](https://aka.ms/appgovernance).</span></span>

![Microsoft 365 合規性中心的應用程式控管概觀頁面](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> <span data-ttu-id="1c4eb-107">您的登入帳戶必須具有 [這些角色](app-governance-get-started.md#administrator-roles) 的其中一個，才能檢視任何應用程式控管資料。</span><span class="sxs-lookup"><span data-stu-id="1c4eb-107">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="1c4eb-108">從此頁面，您可以查看：</span><span class="sxs-lookup"><span data-stu-id="1c4eb-108">From this page, you can see:</span></span>

- <span data-ttu-id="1c4eb-109">對於使用 Microsoft Graph API 的啟用 OAuth 應用程式：</span><span class="sxs-lookup"><span data-stu-id="1c4eb-109">For OAuth-enabled apps that use the Microsoft Graph API:</span></span>

  - <span data-ttu-id="1c4eb-110">您的租用戶中有多少</span><span class="sxs-lookup"><span data-stu-id="1c4eb-110">How many are in your tenant</span></span>
  - <span data-ttu-id="1c4eb-111">擁有過度授權的人員可能有多少</span><span class="sxs-lookup"><span data-stu-id="1c4eb-111">How many might be overprivileged</span></span>
  - <span data-ttu-id="1c4eb-112">具有高權限的人員有多少</span><span class="sxs-lookup"><span data-stu-id="1c4eb-112">How many are high privilege</span></span>

  <span data-ttu-id="1c4eb-113">從這項資訊中，您可以利用過度授權和高度權限應用程式來判斷貴組織的風險層級。</span><span class="sxs-lookup"><span data-stu-id="1c4eb-113">From this information, you can determine the level of risk to your organization by overprivileged and high privilege apps.</span></span>

- <span data-ttu-id="1c4eb-114">針對警示：</span><span class="sxs-lookup"><span data-stu-id="1c4eb-114">For alerts:</span></span>

  - <span data-ttu-id="1c4eb-115">您的租用戶有多少個作用中警示？</span><span class="sxs-lookup"><span data-stu-id="1c4eb-115">How many active alerts your tenant has</span></span>
  - <span data-ttu-id="1c4eb-116">有多少警示是以應用程式控管偵測（**威脅警示**）為依據</span><span class="sxs-lookup"><span data-stu-id="1c4eb-116">How many are based on app governance detections (**Threat alerts**)</span></span>
  - <span data-ttu-id="1c4eb-117">有多少警示是以您目前使用的應用程式原則（**原則警示**）為依據</span><span class="sxs-lookup"><span data-stu-id="1c4eb-117">How many are based on app policies you have in place (**Policy alerts**)</span></span>
  - <span data-ttu-id="1c4eb-118">10 個最新警示</span><span class="sxs-lookup"><span data-stu-id="1c4eb-118">The 10 latest alerts</span></span>

  <span data-ttu-id="1c4eb-119">從此資訊中，您可以判斷產生警示的速度有多快，以及偵測到和以原則為依據的警示相對數目。</span><span class="sxs-lookup"><span data-stu-id="1c4eb-119">From this information, you can determine how quickly alerts are being generated and the relative number of detected and policy-based alerts.</span></span>

- <span data-ttu-id="1c4eb-120">資料與資源存取：</span><span class="sxs-lookup"><span data-stu-id="1c4eb-120">For data and resources access:</span></span>

  - <span data-ttu-id="1c4eb-121">於目前和前三個行事曆月份，租用戶中的應用程式透過圖形 API 存取的資料總計。</span><span class="sxs-lookup"><span data-stu-id="1c4eb-121">Total data accessed by apps in the tenant through Graph API over the current and previous three calendar months.</span></span> <span data-ttu-id="1c4eb-122">(目前僅包含郵件和檔案上傳和下載使用情況)</span><span class="sxs-lookup"><span data-stu-id="1c4eb-122">(Currently only includes Mail and File upload and download usage)</span></span>
  - <span data-ttu-id="1c4eb-123">目前和前三個行事曆月份的資料使用情況，按資源類型細分。</span><span class="sxs-lookup"><span data-stu-id="1c4eb-123">Data usage over the current and previous three calendar months, broken down by resource type.</span></span> <span data-ttu-id="1c4eb-124">(目前僅包含郵件和檔案上傳和下載使用情況)</span><span class="sxs-lookup"><span data-stu-id="1c4eb-124">(Currently only includes Mail and File upload and download usage)</span></span>

  <span data-ttu-id="1c4eb-125">從此資訊中，您可以判斷 Microsoft 365 租用戶的資料存取是否有異常高峰。</span><span class="sxs-lookup"><span data-stu-id="1c4eb-125">From this information, you can determine if there are anomalous spikes in access to the data in your Microsoft 365 tenant.</span></span>