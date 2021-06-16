---
title: 雲端解決方案供應商的其他資訊
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：與從 Microsoft Cloud Deutschland 進行遷移相關的雲端解決方案提供者的其他資訊。
ms.openlocfilehash: 7a7c377d8e0b72a0179ff28a93018f88d22a5325
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52931044"
---
# <a name="additional-information-for-cloud-solution-providers"></a><span data-ttu-id="7b30d-103">雲端解決方案供應商的其他資訊</span><span class="sxs-lookup"><span data-stu-id="7b30d-103">Additional information for Cloud Solution Providers</span></span>

<span data-ttu-id="7b30d-104">雲端解決方案供應商 (Csp) 支援客戶必須在從 Microsoft Cloud Deutschland 遷移至新的德國資料中心區域時採取額外的步驟。</span><span class="sxs-lookup"><span data-stu-id="7b30d-104">Cloud Solution Providers (CSPs) supporting customers  need to take additional steps during the migration from Microsoft Cloud Deutschland to the new German datacenter region.</span></span>

## <a name="partner-tenant-migration"></a><span data-ttu-id="7b30d-105">合作夥伴租使用者遷移</span><span class="sxs-lookup"><span data-stu-id="7b30d-105">Partner tenant migration</span></span>

<span data-ttu-id="7b30d-106">將不會遷移協力廠商 Microsoft Cloud Deutschland 承租人。</span><span class="sxs-lookup"><span data-stu-id="7b30d-106">Partner Microsoft Cloud Deutschland tenants won't be migrated.</span></span> <span data-ttu-id="7b30d-107">相反地，會為新的德國資料中心區域中的每個 Microsoft 合作夥伴建立新的 Office 365 服務租使用者。</span><span class="sxs-lookup"><span data-stu-id="7b30d-107">Instead, a new Office 365 services tenant will be created for each Microsoft Partner in the new German datacenter region.</span></span>

<span data-ttu-id="7b30d-108">CSP 客戶租使用者將遷移至新的德國資料中心區域，並連結至相同合作夥伴的新 Office 365 服務租使用者。</span><span class="sxs-lookup"><span data-stu-id="7b30d-108">CSP customer tenants will be migrated to the new German datacenter region and be linked to the new Office 365 services tenant of the same partner.</span></span> <span data-ttu-id="7b30d-109">客戶轉換後，合作夥伴可以使用德國資料中心區域的新 Office 365 服務租使用者管理客戶。</span><span class="sxs-lookup"><span data-stu-id="7b30d-109">After customer transition, the partner can manage the customer using the new Office 365 services tenant in the German datacenter region.</span></span>

## <a name="missing-subscriptions-in-azure"></a><span data-ttu-id="7b30d-110">Azure 中遺失訂閱</span><span class="sxs-lookup"><span data-stu-id="7b30d-110">Missing subscriptions in Azure</span></span>

<span data-ttu-id="7b30d-111">[訂閱和授權轉換 (階段 3) ](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)完成之後，雲端方案提供者將無法存取 Azure 訂閱。</span><span class="sxs-lookup"><span data-stu-id="7b30d-111">After [the subscription and license transition (phase 3)](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed, Cloud Solution Providers will not have access to the Azure subscription anymore.</span></span>

<span data-ttu-id="7b30d-112">若要復原存取權，請遵循下列步驟，以 [提升管理所有 Azure 訂閱和管理群組的存取權](/azure/role-based-access-control/elevate-access-global-admin)。</span><span class="sxs-lookup"><span data-stu-id="7b30d-112">To recover access, follow these steps to [elevate access to manage all Azure subscriptions and management groups](/azure/role-based-access-control/elevate-access-global-admin).</span></span>
