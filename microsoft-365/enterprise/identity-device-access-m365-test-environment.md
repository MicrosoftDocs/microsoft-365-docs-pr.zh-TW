---
title: 您的 Microsoft 365 測試環境的身分識別與裝置存取
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 建立 Microsoft 365 環境以測試身分識別與裝置存取。
ms.openlocfilehash: 427b0589da0347008cca0e2004bc23f494bebb29
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907465"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="964c6-103">您的 Microsoft 365 測試環境的身分識別與裝置存取</span><span class="sxs-lookup"><span data-stu-id="964c6-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="964c6-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="964c6-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="964c6-105">身分[識別與裝置存取](../security/office-365-security/microsoft-365-policies-configurations.md)設定是一組建議的設定和條件式存取原則，可保護對與 Azure Active Directory (azure AD) 整合的所有服務的存取。</span><span class="sxs-lookup"><span data-stu-id="964c6-105">[Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) are a set of recommended configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="964c6-106">若要建立具備通用身分識別和裝置存取設定的測試環境：</span><span class="sxs-lookup"><span data-stu-id="964c6-106">To create a test environment that has the common identity and device access configurations in place:</span></span>

1. <span data-ttu-id="964c6-107">根據您所選擇的身分識別模型以及驗證方法，設定您的測試環境使其具備身分識別和安全性功能的先決條件：</span><span class="sxs-lookup"><span data-stu-id="964c6-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="964c6-108">僅限雲端</span><span class="sxs-lookup"><span data-stu-id="964c6-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="964c6-109">密碼雜湊同步處理 (PHS) </span><span class="sxs-lookup"><span data-stu-id="964c6-109">Password hash synchronization (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="964c6-110">傳遞驗證 (PTA)</span><span class="sxs-lookup"><span data-stu-id="964c6-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="964c6-111">使用 [通用身分識別和裝置存取原則](../security/office-365-security/identity-access-policies.md) ，設定針對測試環境所設定的必要條件建立的原則，並探索及驗證身分識別及裝置的保護。</span><span class="sxs-lookup"><span data-stu-id="964c6-111">Use [Common identity and device access policies](../security/office-365-security/identity-access-policies.md) to configure the policies that build on the prerequisites configured for your test environment and explore and verify protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="964c6-112">請參閱</span><span class="sxs-lookup"><span data-stu-id="964c6-112">See also</span></span>

[<span data-ttu-id="964c6-113">其他身分識別測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="964c6-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="964c6-114">身分識別藍圖</span><span class="sxs-lookup"><span data-stu-id="964c6-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="964c6-115">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="964c6-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="964c6-116">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="964c6-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="964c6-117">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="964c6-117">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)