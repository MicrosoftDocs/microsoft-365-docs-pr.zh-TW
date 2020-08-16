---
title: Microsoft 365 隔離控制
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
description: 瞭解隔離控制在 Microsoft 365 內的運作方式，允許服務在必要的情況下運作或保持自治。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15805c2fb57cbcaa33c5ba24dcbcaa378feea4bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688589"
---
# <a name="microsoft-365-isolation-controls"></a><span data-ttu-id="04c45-103">Microsoft 365 隔離控制</span><span class="sxs-lookup"><span data-stu-id="04c45-103">Microsoft 365 isolation controls</span></span> 

<span data-ttu-id="04c45-104">Microsoft 連續運作，以確保 Microsoft 365 的多承租人架構支援企業層級的安全性、機密性、隱私權、完整性、本機、國際和可用性 [標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)。</span><span class="sxs-lookup"><span data-stu-id="04c45-104">Microsoft continuously works to ensure that the multi-tenant architecture of Microsoft 365 supports enterprise-level security, confidentiality, privacy, integrity, local, international, and availability [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span></span> <span data-ttu-id="04c45-105">由 Microsoft 提供的服務規模和範圍，可讓您在使用重要人工互動功能的情況中管理 Microsoft 365，使其非常困難，非經濟。</span><span class="sxs-lookup"><span data-stu-id="04c45-105">The scale and the scope of services provided by Microsoft make it difficult and non-economical to manage Microsoft 365 with significant human interaction.</span></span> <span data-ttu-id="04c45-106">Microsoft 365 服務是透過多個全域分散式資料中心提供，每個都具有許多要求人工觸控或任何對客戶內容的作業。</span><span class="sxs-lookup"><span data-stu-id="04c45-106">Microsoft 365 services are provided through multiple globally distributed data centers, each highly automated with few operations requiring a human touch or any access to customer content.</span></span> <span data-ttu-id="04c45-107">我們的員工使用自動工具和高安全性的遠端存取，支援這些服務和資料中心。</span><span class="sxs-lookup"><span data-stu-id="04c45-107">Our staff supports these services and data centers using automated tools and highly secure remote access.</span></span> 

<span data-ttu-id="04c45-108">Microsoft 365 是由多種服務所組成，可提供重要的商務功能，並可促進整個 Microsoft 365 的體驗。</span><span class="sxs-lookup"><span data-stu-id="04c45-108">Microsoft 365 is composed of multiple services that provide important business functionality and contribute to the entire Microsoft 365 experience.</span></span> <span data-ttu-id="04c45-109">每個服務都是自包含的，且設計為彼此整合。</span><span class="sxs-lookup"><span data-stu-id="04c45-109">Each of these services is self-contained and designed to integrate with one another.</span></span>

<span data-ttu-id="04c45-110">Microsoft 365 的設計原則如下：</span><span class="sxs-lookup"><span data-stu-id="04c45-110">Microsoft 365 is designed with the following principles:</span></span>

 - <span data-ttu-id="04c45-111">以**[服務為導向的架構](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10))：** 以互通性服務的形式設計和開發軟體，以提供完善定義的商務功能。</span><span class="sxs-lookup"><span data-stu-id="04c45-111">**[Service-Oriented Architecture](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10)):** designing and developing software in the form of interoperable services providing well-defined business functionality.</span></span>
 - <span data-ttu-id="04c45-112">**[運作安全性保證](https://www.microsoft.com/download/details.aspx?id=40872)：** 一種架構，包含透過 microsoft 獨有的各種功能所取得的知識，包括 Microsoft [安全性開發週期](https://www.microsoft.com/sdl/default.aspx)、 [microsoft 安全回應中心](https://technet.microsoft.com/library/dn440717.aspx)，以及 cybersecurity 威脅形勢的深入認知。</span><span class="sxs-lookup"><span data-stu-id="04c45-112">**[Operational Security Assurance](https://www.microsoft.com/download/details.aspx?id=40872):** a framework that incorporates the knowledge gained through various capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.</span></span>

<span data-ttu-id="04c45-113">Microsoft 365 服務間相互運作，但會加以設計及實施，使其能獨立于自治服務進行部署及運作。</span><span class="sxs-lookup"><span data-stu-id="04c45-113">Microsoft 365 services inter-operate with each other, but are designed and implemented so they can be deployed and operated as autonomous services, independent of each other.</span></span> <span data-ttu-id="04c45-114">Microsoft segregates Microsoft 365 的責任和責任範圍，以減少未授權或無意修改或誤用組織資產的機會。</span><span class="sxs-lookup"><span data-stu-id="04c45-114">Microsoft segregates duties and areas of responsibility for Microsoft 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets.</span></span> <span data-ttu-id="04c45-115">Microsoft 365 小組已定義角色，成為綜合角色存取控制機制的一部分。</span><span class="sxs-lookup"><span data-stu-id="04c45-115">Microsoft 365 teams have defined roles as part of a comprehensive role-based access control mechanism.</span></span>

## <a name="customer-content-isolation"></a><span data-ttu-id="04c45-116">客戶內容隔離</span><span class="sxs-lookup"><span data-stu-id="04c45-116">Customer content isolation</span></span>

<span data-ttu-id="04c45-117">租使用者中的所有客戶內容，都與其他承租人和 Microsoft 365 管理中所使用的作業和系統資料隔離。</span><span class="sxs-lookup"><span data-stu-id="04c45-117">All customer content in a tenant is isolated from other tenants and from operations and systems data used in the management of Microsoft 365.</span></span> <span data-ttu-id="04c45-118">您可以在整個 Microsoft 365 中實施多種保護形式，以最大限度降低任何 Microsoft 365 服務或應用程式的威脅。</span><span class="sxs-lookup"><span data-stu-id="04c45-118">Multiple forms of protection are implemented throughout Microsoft 365 to minimize the risk of compromise of any Microsoft 365 service or application.</span></span> <span data-ttu-id="04c45-119">多種保護表單也可防止未經授權的存取承租人或 Microsoft 365 系統本身的資訊。</span><span class="sxs-lookup"><span data-stu-id="04c45-119">Multiple forms of protection also prevent unauthorized access to the information of tenants or the Microsoft 365 system itself.</span></span>

<span data-ttu-id="04c45-120">如需 Microsoft 如何在 Microsoft 365 內實現租使用者資料邏輯隔離的詳細資訊，請參閱 [microsoft 365 中的承租人隔離](microsoft-365-tenant-isolation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="04c45-120">For information about how Microsoft implements logical isolation of tenant data within Microsoft 365, see [Tenant Isolation in Microsoft 365](microsoft-365-tenant-isolation-overview.md).</span></span>