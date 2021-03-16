---
title: Microsoft 365 租使用者對租使用者遷移
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: 瞭解如何遷移 Microsoft 365 承租人。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6e8277a7ca768db3a4a4acd2488859b7764a40c
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819711"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="87cca-103">Microsoft 365 租使用者對租使用者遷移</span><span class="sxs-lookup"><span data-stu-id="87cca-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="87cca-104">合併、收購、divestitures 及其他案例的一些架構方法可能會讓您將現有的 Microsoft 365 租使用者遷移至新的租使用者。</span><span class="sxs-lookup"><span data-stu-id="87cca-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="87cca-105">大部分的客戶都可以與 Microsoft 諮詢服務或 Microsoft 合作夥伴合作，以遷移承租人，包括使用協力廠商工具來遷移內容。</span><span class="sxs-lookup"><span data-stu-id="87cca-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="87cca-106">使用 [租使用者對租使用者遷移架構模型](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) ，瞭解如何規劃 Microsoft 365 租使用者對租使用者的遷移和遷移步驟。</span><span class="sxs-lookup"><span data-stu-id="87cca-106">Use the [Tenant-to-tenant migration architecture model](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="87cca-107">[![租使用者對租使用者遷移模型](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="87cca-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="87cca-108">您可以下載 [PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) 格式的此模型，並在 letter、法律或卡片 (11 x 17) 大小的紙上列印此模型。</span><span class="sxs-lookup"><span data-stu-id="87cca-108">You download this model in [PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="87cca-109">這種模型提供下列專案的指導方針和切入點：</span><span class="sxs-lookup"><span data-stu-id="87cca-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="87cca-110">商務案例與架構方法的對應</span><span class="sxs-lookup"><span data-stu-id="87cca-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="87cca-111">設計考量</span><span class="sxs-lookup"><span data-stu-id="87cca-111">Design considerations</span></span>

<span data-ttu-id="87cca-112">此模型也包含下列各項的詳細範例：</span><span class="sxs-lookup"><span data-stu-id="87cca-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="87cca-113">單一事件遷移流程</span><span class="sxs-lookup"><span data-stu-id="87cca-113">A single event migration flow</span></span>
- <span data-ttu-id="87cca-114">逐步遷移流程</span><span class="sxs-lookup"><span data-stu-id="87cca-114">A phased migration flow</span></span>
- <span data-ttu-id="87cca-115">承租人移動或分割流程</span><span class="sxs-lookup"><span data-stu-id="87cca-115">A tenant move or split flow</span></span>
