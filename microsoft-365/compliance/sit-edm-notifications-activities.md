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
# <a name="create-notifications-for-exact-data-match-activities"></a><span data-ttu-id="115f7-103">建立精確資料比對活動的通知</span><span class="sxs-lookup"><span data-stu-id="115f7-103">Create notifications for exact data match activities</span></span>

<span data-ttu-id="115f7-104">在[使用資料完全相符 (EDM) 建立自訂敏感性資訊類型時](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)，在[稽核記錄](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log)中會建立許多活動。</span><span class="sxs-lookup"><span data-stu-id="115f7-104">When you [create custom sensitive information types with exact data match (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) there are a number of activities that are created in the [audit log](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log).</span></span> <span data-ttu-id="115f7-105">您可以使用 [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell Cmdlet建立通知，讓您知道這些活動何時發生：</span><span class="sxs-lookup"><span data-stu-id="115f7-105">You can use the [New-ProtectionAlert](/powershell/module/exchange/new-protectionalert) PowerShell cmdlet to create notifications that let you know when these activities occur:</span></span>

- <span data-ttu-id="115f7-106">CreateSchema</span><span class="sxs-lookup"><span data-stu-id="115f7-106">CreateSchema</span></span>
- <span data-ttu-id="115f7-107">EditSchema</span><span class="sxs-lookup"><span data-stu-id="115f7-107">EditSchema</span></span>
- <span data-ttu-id="115f7-108">RemoveSchema</span><span class="sxs-lookup"><span data-stu-id="115f7-108">RemoveSchema</span></span>
- <span data-ttu-id="115f7-109">UploadDataFailed</span><span class="sxs-lookup"><span data-stu-id="115f7-109">UploadDataFailed</span></span>
- <span data-ttu-id="115f7-110">UploadDataCompleted</span><span class="sxs-lookup"><span data-stu-id="115f7-110">UploadDataCompleted</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="115f7-111">先決條件</span><span class="sxs-lookup"><span data-stu-id="115f7-111">Pre-requisites</span></span>

<span data-ttu-id="115f7-112">使用的帳戶必須屬於下列其中一個角色：</span><span class="sxs-lookup"><span data-stu-id="115f7-112">The account you use must be one of the following:</span></span>

- <span data-ttu-id="115f7-113">全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="115f7-113">a global admin</span></span>
- <span data-ttu-id="115f7-114">合規性系統管理員</span><span class="sxs-lookup"><span data-stu-id="115f7-114">compliance administrator</span></span>
- <span data-ttu-id="115f7-115">Exchange Online 系統管理員</span><span class="sxs-lookup"><span data-stu-id="115f7-115">Exchange Online administrator</span></span>

<span data-ttu-id="115f7-116">若要進一步了解 DLP 權限，請參閱[權限](data-loss-prevention-policies.md#permissions)。</span><span class="sxs-lookup"><span data-stu-id="115f7-116">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="115f7-117">這些訂閱中包含 EDM 型分類:</span><span class="sxs-lookup"><span data-stu-id="115f7-117">EDM-based classification is included in these subscriptions:</span></span>

- <span data-ttu-id="115f7-118">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="115f7-118">Office 365 E5</span></span>
- <span data-ttu-id="115f7-119">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="115f7-119">Microsoft 365 E5</span></span>
- <span data-ttu-id="115f7-120">Microsoft 365 E5 合規性</span><span class="sxs-lookup"><span data-stu-id="115f7-120">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="115f7-121">Microsoft E5/A5 資訊保護和控管</span><span class="sxs-lookup"><span data-stu-id="115f7-121">Microsoft E5/A5 Information Protection and Governance</span></span>

<span data-ttu-id="115f7-122">如要深入了解 DLP 授權，請參閱 [Microsoft 365 安全性與合規性的授權指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)。</span><span class="sxs-lookup"><span data-stu-id="115f7-122">To learn more about DLP licensing, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

## <a name="configure-notifications-for-edm-activities"></a><span data-ttu-id="115f7-123">設定 EDM 活動的通知</span><span class="sxs-lookup"><span data-stu-id="115f7-123">Configure notifications for EDM activities</span></span>

1. <span data-ttu-id="115f7-124">連線到[安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="115f7-124">Connect to the [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="115f7-125">使用您想建立通知的活動執行 `New-ProtectionAlert` Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="115f7-125">Run the `New-ProtectionAlert` cmdlet using the activity that you want to create the notification for.</span></span>  <span data-ttu-id="115f7-126">例如，如果您想要在 **UploadDataCompleted** 動作發生時收到通知，執行:</span><span class="sxs-lookup"><span data-stu-id="115f7-126">For example, if you want to be notified when the **UploadDataCompleted** action occurred, run:</span></span>

    ```powershell
    New-ProtectionAlert -Name "EdmUploadCompleteAlertPolicy" -Category Others -NotifyUser <address to send notification to> -ThreatType Activity -Operation UploadDataCompleted -Description "Custom alert policy to track when EDM upload Completed" -AggregationType None
    ```
    
    <span data-ttu-id="115f7-127">如果是 **UploadDataFailed**，您可以執行:</span><span class="sxs-lookup"><span data-stu-id="115f7-127">for the **UploadDataFailed** you can run:</span></span>
    
    ```powershell
    New-ProtectionAlert -Name "EdmUploadFailAlertPolicy" -Category Others -NotifyUser <SMTP address to send notification to> -ThreatType Activity -Operation UploadDataFailed -Description "Custom alert policy to track when EDM upload Failed" -AggregationType None -Severity High
    ```

## <a name="related-articles"></a><span data-ttu-id="115f7-128">相關文章</span><span class="sxs-lookup"><span data-stu-id="115f7-128">Related articles</span></span>

- [<span data-ttu-id="115f7-129">使用資料完全相符 (EDM) 建立自訂敏感性資訊類型</span><span class="sxs-lookup"><span data-stu-id="115f7-129">Create custom sensitive information types with exact data match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [<span data-ttu-id="115f7-130">New-ProtectionAlert</span><span class="sxs-lookup"><span data-stu-id="115f7-130">New-ProtectionAlert</span></span>](/powershell/module/exchange/new-protectionalert)