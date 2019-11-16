---
title: Azure AD Identity Protection，您的 Microsoft 365 企業版測試環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 設定 Azure AD Identity Protection 及分析您的 Microsoft 365 企業版測試環境中的目前的帳戶。
ms.openlocfilehash: bc98ebbdd45e06481e2d95687fb4eb8c986533a3
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673239"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b5ee2-103">Azure AD Identity Protection，您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="b5ee2-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b5ee2-104">*此測試實驗室指南僅可用於 Microsoft 365 企業版測試環境。*</span><span class="sxs-lookup"><span data-stu-id="b5ee2-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="b5ee2-105">Azure AD Identity Protection 可讓您偵測會影響組織身分識別的潛在弱點，設定自動式回應，並調查事件。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-105">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="b5ee2-106">本文說明如何啟用 Azure AD Identity Protection，並檢視您的測試環境帳戶的分析。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-106">This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="b5ee2-107">有兩個主要階段設定 Microsoft 365 企業版測試環境中的 Azure AD Identity Protection:</span><span class="sxs-lookup"><span data-stu-id="b5ee2-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="b5ee2-108">建立 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="b5ee2-109">啟用並使用 Azure AD Identity Protection。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-109">Enable and use Azure AD Identity Protection.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b5ee2-111">按一下[這裡](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)(英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b5ee2-112">階段 1：建置您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="b5ee2-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b5ee2-113">如果您只想以具有最小需求的輕量型方式測試 Azure AD Identity Protection，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b5ee2-114">如果您想要在模擬的企業中測試 Azure AD Identity Protection，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5ee2-115">測試 Azure AD Identity Protection 不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理 Active Directory 網域服務 (AD DS) 樹系中。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b5ee2-116">它提供了此選項，讓您可以測試 Azure AD Identity Protection，並代表典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="b5ee2-117">階段 2： 啟用，並使用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="b5ee2-117">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="b5ee2-118">開啟瀏覽器的私用執行個體並登入 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)以全域系統管理員帳戶的 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="b5ee2-119">在 Azure 入口網站中，按一下 [**所有服務 > 市集**]。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-119">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="b5ee2-120">輸入**Azure AD Identity Protection** ，然後按一下它。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-120">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="b5ee2-121">在 [**快速入門**] 刀鋒視窗上，按一下**Onboard** [**設定**] 下，按一下**釘選到儀表板**]，然後按一下 [**建立**。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-121">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="b5ee2-122">在 Azure 入口網站中，按一下 [儀表板上的**Azure AD Identity Protection** 。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-122">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="b5ee2-123">您應該會看到**Azure AD Identity Protection-概觀**] 刀鋒視窗中的儀表板。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-123">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard.</span></span> <span data-ttu-id="b5ee2-124">下**弱點**，請注意其決定不用多重要素驗證註冊的使用者帳戶的數目。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-124">Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration.</span></span> <span data-ttu-id="b5ee2-125">此數字會根據先前 Microsoft 365 企業版測試實驗室指南，您必須完成而有所不同。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-125">This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="b5ee2-126">[所有類別的**調查]** 若要查看是否有任何使用者或已偵測到的事件。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-126">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="b5ee2-127">進一步測試與試驗，請參閱[Simulating 風險事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="b5ee2-128">在身分識別階段中的資訊，以及部署在生產環境中的 Azure AD Identity Protection 的連結，請參閱[Protect 針對認證洩露](identity-secure-user-sign-ins.md#identity-ident-prot)步驟。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="b5ee2-129">下一步</span><span class="sxs-lookup"><span data-stu-id="b5ee2-129">Next step</span></span>

<span data-ttu-id="b5ee2-130">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="b5ee2-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5ee2-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b5ee2-131">See also</span></span>

[<span data-ttu-id="b5ee2-132">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="b5ee2-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="b5ee2-133">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="b5ee2-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b5ee2-134">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="b5ee2-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b5ee2-135">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="b5ee2-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
