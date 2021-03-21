---
title: Microsoft 365 中的租使用者隔離
ms.author: robmazz
author: robmazz
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
description: 本文摘要說明 Microsoft 如何在雲端服務（如 Microsoft 365）中強制執行租使用者隔離。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7c5be65186b75f6056a64b776e4f0d25bcd55eb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923073"
---
# <a name="tenant-isolation-in-microsoft-365"></a><span data-ttu-id="03070-103">Microsoft 365 中的租使用者隔離</span><span class="sxs-lookup"><span data-stu-id="03070-103">Tenant Isolation in Microsoft 365</span></span>

<span data-ttu-id="03070-104">雲端計算的其中一個主要優點是，許多客戶都有共同共同使用的共同基礎結構，進而可實現規模經濟效益。</span><span class="sxs-lookup"><span data-stu-id="03070-104">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale.</span></span> <span data-ttu-id="03070-105">這個概念稱為 *多重* 租用。</span><span class="sxs-lookup"><span data-stu-id="03070-105">This concept is called *multi-tenancy*.</span></span> <span data-ttu-id="03070-106">Microsoft 可以持續運作，以確保雲端服務的多承租人架構支援企業層級的安全性、機密性、隱私權、完整性及可用性標準。</span><span class="sxs-lookup"><span data-stu-id="03070-106">Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="03070-107">根據從「 [可信計算](https://www.microsoft.com/trust-center) 」和「 [安全性開發生命週期](https://www.microsoft.com/securityengineering/sdl/)」收集的重大投資和經驗，設計 Microsoft 雲端服務是為了避免所有租使用者可能會惡意處理其他租使用者，並已實施安全性措施，以避免一個承租人的動作影響其他租使用者的安全性或服務，或存取另一個租使用者的內容。</span><span class="sxs-lookup"><span data-stu-id="03070-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/trust-center) and the [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="03070-108">在多租使用者環境中維護租使用者隔離的兩個主要目標如下：</span><span class="sxs-lookup"><span data-stu-id="03070-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>

1.    <span data-ttu-id="03070-109">防止對承租人的客戶內容洩露或未經授權存取和</span><span class="sxs-lookup"><span data-stu-id="03070-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.    <span data-ttu-id="03070-110">防止一個承租人的動作對其他租使用者的服務造成不良影響</span><span class="sxs-lookup"><span data-stu-id="03070-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="03070-111">已在整個 Microsoft 365 中實施多種保護形式，以防止客戶損除 Microsoft 365 服務或應用程式，或未經授權存取其他承租人或 Microsoft 365 系統本身的資訊，包括：</span><span class="sxs-lookup"><span data-stu-id="03070-111">Multiple forms of protection have been implemented throughout Microsoft 365 to prevent customers from compromising Microsoft 365 services or applications or gaining unauthorized access to the information of other tenants or the Microsoft 365 system itself, including:</span></span>

- <span data-ttu-id="03070-112">Microsoft 365 服務各租使用者中的客戶內容邏輯隔離，是透過 Azure Active Directory 授權和以角色為基礎的存取控制來實現。</span><span class="sxs-lookup"><span data-stu-id="03070-112">Logical isolation of customer content within each tenant for Microsoft 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="03070-113">SharePoint 線上在儲存層級提供資料隔離機制。</span><span class="sxs-lookup"><span data-stu-id="03070-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="03070-114">Microsoft 使用嚴謹的實體安全性、背景篩選和多層次的加密策略，以保護客戶內容的機密性和完整性。</span><span class="sxs-lookup"><span data-stu-id="03070-114">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content.</span></span> <span data-ttu-id="03070-115">所有 Microsoft 365 資料中心都具有生物識別存取控制，大多數需要 palm 列印才能獲得實體存取權。</span><span class="sxs-lookup"><span data-stu-id="03070-115">All Microsoft 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access.</span></span> <span data-ttu-id="03070-116">此外，所有以美國為基礎的 Microsoft 員工都必須在聘用過程中成功完成標準背景檢查。</span><span class="sxs-lookup"><span data-stu-id="03070-116">In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process.</span></span> <span data-ttu-id="03070-117">如需 Microsoft 365 中用於管理存取之控制項的詳細資訊，請參閱 [microsoft 365 管理存取控制](/compliance/assurance/assurance-administrative-access-controls-overview)。</span><span class="sxs-lookup"><span data-stu-id="03070-117">For more information on the controls used for administrative access in Microsoft 365, see [Microsoft 365 Administrative Access Controls](/compliance/assurance/assurance-administrative-access-controls-overview).</span></span>
- <span data-ttu-id="03070-118">Microsoft 365 使用服務端技術，在靜止和傳輸中加密客戶內容，包括 BitLocker、每個檔案加密、傳輸層安全性 (TLS) 和網際網路通訊協定安全性 (IPsec) 。</span><span class="sxs-lookup"><span data-stu-id="03070-118">Microsoft 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="03070-119">如需 Microsoft 365 中加密的特定詳細資料，請參閱 [microsoft 365 中的資料加密技術](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="03070-119">For specific details about encryption in Microsoft 365, see [Data Encryption Technologies in Microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md).</span></span>

<span data-ttu-id="03070-120">以上所列的保護功能提供了可靠的邏輯隔離控制，可提供與獨立實體隔離所提供之威脅防護和緩解同等的威脅。</span><span class="sxs-lookup"><span data-stu-id="03070-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="03070-121">相關連結</span><span class="sxs-lookup"><span data-stu-id="03070-121">Related Links</span></span>

- [<span data-ttu-id="03070-122">Azure Active Directory 中的隔離與存取控制</span><span class="sxs-lookup"><span data-stu-id="03070-122">Isolation and Access Control in Azure Active Directory</span></span>](microsoft-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="03070-123">Office Graph 與 Delve 中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="03070-123">Tenant Isolation in the Office Graph and Delve</span></span>](microsoft-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="03070-124">Microsoft 365 搜尋中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="03070-124">Tenant Isolation in Microsoft 365 Search</span></span>](microsoft-365-isolation-in-microsoft-365-search.md)
- [<span data-ttu-id="03070-125">Office 365 影片中的租用戶隔離</span><span class="sxs-lookup"><span data-stu-id="03070-125">Tenant Isolation in Office 365 Video</span></span>](microsoft-365-isolation-in-microsoft-365-video.md)
- [<span data-ttu-id="03070-126">資源限制</span><span class="sxs-lookup"><span data-stu-id="03070-126">Resource Limits</span></span>](/compliance/assurance/assurance-resource-limits)
- [<span data-ttu-id="03070-127">監視及測試租用戶界限</span><span class="sxs-lookup"><span data-stu-id="03070-127">Monitoring and Testing Tenant Boundaries</span></span>](/compliance/assurance/assurance-monitoring-and-testing)
- [<span data-ttu-id="03070-128">Microsoft 365 中的隔離與存取控制</span><span class="sxs-lookup"><span data-stu-id="03070-128">Isolation and Access Control in Microsoft 365</span></span>](microsoft-365-isolation-in-microsoft-365.md)