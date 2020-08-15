---
title: 您的 Microsoft 365 測試環境的身分識別與裝置存取
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 建立 Microsoft 365 環境以測試身分識別與裝置存取。
ms.openlocfilehash: c5bc0fbbb3ae3839cb7aa71e8c840784ae4a4cad
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685851"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="87153-103">您的 Microsoft 365 測試環境的身分識別與裝置存取</span><span class="sxs-lookup"><span data-stu-id="87153-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="87153-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="87153-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="87153-105">身分[識別與裝置存取](microsoft-365-policies-configurations.md)設定是一組功能和條件式存取原則，可保護與 Azure Active Directory (azure AD) 整合的所有服務存取權。</span><span class="sxs-lookup"><span data-stu-id="87153-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD).</span></span>

<span data-ttu-id="87153-106">若要建立具備這些原則的測試環境：</span><span class="sxs-lookup"><span data-stu-id="87153-106">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="87153-107">根據您所選擇的身分識別模型以及驗證方法，設定您的測試環境使其具備身分識別和安全性功能的先決條件：</span><span class="sxs-lookup"><span data-stu-id="87153-107">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="87153-108">僅限雲端</span><span class="sxs-lookup"><span data-stu-id="87153-108">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="87153-109">密碼雜湊同步處理 (PHS)</span><span class="sxs-lookup"><span data-stu-id="87153-109">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="87153-110">傳遞驗證 (PTA)</span><span class="sxs-lookup"><span data-stu-id="87153-110">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="87153-111">使用[一般身分識別與裝置存取原則](identity-access-policies.md)來設定根據先決條件建置的原則，並測試身分識別與裝置的保護。</span><span class="sxs-lookup"><span data-stu-id="87153-111">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="87153-112">請參閱</span><span class="sxs-lookup"><span data-stu-id="87153-112">See also</span></span>

[<span data-ttu-id="87153-113">其他身分識別測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="87153-113">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="87153-114">身分識別藍圖</span><span class="sxs-lookup"><span data-stu-id="87153-114">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="87153-115">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="87153-115">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="87153-116">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="87153-116">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="87153-117">適用于企業的 Microsoft 365 檔</span><span class="sxs-lookup"><span data-stu-id="87153-117">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
