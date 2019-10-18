---
title: 您的 Microsoft 365 測試環境的身分識別與裝置存取
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 建立 Microsoft 365 環境以測試身分識別與裝置存取。
ms.openlocfilehash: c8d7aed1422f9d0c5891157e6fb7d3d30d976c4a
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981894"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a><span data-ttu-id="63e4c-103">您的 Microsoft 365 測試環境的身分識別與裝置存取</span><span class="sxs-lookup"><span data-stu-id="63e4c-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="63e4c-104">[身分識別與裝置存取組態](microsoft-365-policies-configurations.md)是一組功能和條件式存取原則，用來保護對與 Azure Active Directory (Azure AD) 整合之所有服務的存取，包括 Microsoft 365 企業版中的 Office 365 和 Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="63e4c-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="63e4c-105">若要建立具備這些原則的測試環境：</span><span class="sxs-lookup"><span data-stu-id="63e4c-105">To create a test environment that has these policies in place:</span></span>

1. <span data-ttu-id="63e4c-106">根據您所選擇的身分識別模型以及驗證方法，設定您的測試環境使其具備身分識別和安全性功能的先決條件：</span><span class="sxs-lookup"><span data-stu-id="63e4c-106">Configure your test environment with the prerequisite identity and security features based on your choice of identity model and authentication method:</span></span>

  - [<span data-ttu-id="63e4c-107">僅限雲端</span><span class="sxs-lookup"><span data-stu-id="63e4c-107">Cloud only</span></span>](cloud-only-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="63e4c-108">密碼雜湊同步處理 (PHS)</span><span class="sxs-lookup"><span data-stu-id="63e4c-108">Password hash sync (PHS)</span></span>](phs-prereqs-m365-test-environment.md)
  - [<span data-ttu-id="63e4c-109">傳遞驗證 (PTA)</span><span class="sxs-lookup"><span data-stu-id="63e4c-109">Pass-through authentication (PTA)</span></span>](pta-prereqs-m365-test-environment.md)

2. <span data-ttu-id="63e4c-110">使用[一般身分識別與裝置存取原則](identity-access-policies.md)來設定根據先決條件建置的原則，並測試身分識別與裝置的保護。</span><span class="sxs-lookup"><span data-stu-id="63e4c-110">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="63e4c-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="63e4c-111">See also</span></span>

[<span data-ttu-id="63e4c-112">其他身分識別測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="63e4c-112">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="63e4c-113">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="63e4c-113">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="63e4c-114">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="63e4c-114">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="63e4c-115">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="63e4c-115">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="63e4c-116">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="63e4c-116">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
