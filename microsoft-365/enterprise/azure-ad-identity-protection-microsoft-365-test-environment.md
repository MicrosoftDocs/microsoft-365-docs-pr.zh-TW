---
title: Azure AD Identity Protection，您的 Microsoft 365 企業版測試環境
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 設定 Azure AD Identity Protection 及分析您的 Microsoft 365 企業版測試環境中的目前的帳戶。
ms.openlocfilehash: 3f3740e42c7ec909f44a3c761dfc743359b3f030
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068490"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="fc029-103">Azure AD Identity Protection，您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="fc029-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="fc029-104">*這個測試實驗室指南只能用於 Microsoft 365 企業版測試環境。*</span><span class="sxs-lookup"><span data-stu-id="fc029-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="fc029-105">Azure Active Directory (Azure AD) 身分識別保護可讓您偵測會影響組織身分識別的潛在弱點，設定自動式回應，並調查事件。</span><span class="sxs-lookup"><span data-stu-id="fc029-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="fc029-106">本文說明如何使用 Azure AD Identity Protection 來檢視您的測試環境帳戶的分析。</span><span class="sxs-lookup"><span data-stu-id="fc029-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="fc029-107">有兩個主要階段設定 Microsoft 365 企業版測試環境中的 Azure AD Identity Protection:</span><span class="sxs-lookup"><span data-stu-id="fc029-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="fc029-108">建立 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="fc029-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="fc029-109">使用 Azure AD Identity Protection。</span><span class="sxs-lookup"><span data-stu-id="fc029-109">Use Azure AD Identity Protection.</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="fc029-111">按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="fc029-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="fc029-112">階段 1：建置您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="fc029-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="fc029-113">如果您只想以具有最小需求的輕量型方式測試 Azure AD Identity Protection，請遵循[輕量型基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="fc029-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="fc029-114">如果您想要在模擬的企業中測試 Azure AD Identity Protection，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)的指示進行。</span><span class="sxs-lookup"><span data-stu-id="fc029-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc029-115">測試 Azure AD Identity Protection 不需要模擬的企業測試環境，其中包含連線至網際網路的模擬內部網路和目錄同步處理的 Active Directory 網域服務 (AD DS) 樹系。</span><span class="sxs-lookup"><span data-stu-id="fc029-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="fc029-116">它提供了此選項，讓您可以測試 Azure AD Identity Protection，並代表典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="fc029-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="fc029-117">階段 2： 使用 Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="fc029-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="fc029-118">開啟瀏覽器的私用執行個體並登入 Azure 入口網站，網址[https://portal.azure.com](https://portal.azure.com)以全域系統管理員帳戶的 Microsoft 365 企業版測試環境。</span><span class="sxs-lookup"><span data-stu-id="fc029-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="fc029-119">在 Azure 入口網站中，在 [搜尋] 方塊中，輸入**identity protection** ，然後按一下 [ **Azure AD Identity Protection**。</span><span class="sxs-lookup"><span data-stu-id="fc029-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="fc029-120">在 [ **Identity Protection-概觀**] 刀鋒視窗中，按一下 [在每一份報告來查看他們已回報。</span><span class="sxs-lookup"><span data-stu-id="fc029-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="fc029-121">[**通知**，按一下 [**使用者風險偵測到的警示**。</span><span class="sxs-lookup"><span data-stu-id="fc029-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="fc029-122">在 [**使用者風險偵測到提醒**] 窗格中，選取 [**中等**]。</span><span class="sxs-lookup"><span data-stu-id="fc029-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="fc029-123">針對**電子郵件傳送給下列的使用者**，按一下 [ **Included**並確認您的全域系統管理員帳戶是在清單中選取的成員。</span><span class="sxs-lookup"><span data-stu-id="fc029-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="fc029-124">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="fc029-124">Click **Save**.</span></span>

<span data-ttu-id="fc029-125">按一下 [**保護**，查看如何將其設定不同的原則。</span><span class="sxs-lookup"><span data-stu-id="fc029-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="fc029-126">如果您建立並啟動原則，請確定它不會封鎖存取太寬範圍的條件，或您可能無法登入，即使為全域系統管理員。</span><span class="sxs-lookup"><span data-stu-id="fc029-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="fc029-127">進一步測試與試驗，請參閱[Simulating 風險事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。</span><span class="sxs-lookup"><span data-stu-id="fc029-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="fc029-128">在身分識別階段中的資訊，以及部署在生產環境中的 Azure AD Identity Protection 的連結，請參閱[Protect 針對認證洩露](identity-secure-user-sign-ins.md#identity-ident-prot)步驟。</span><span class="sxs-lookup"><span data-stu-id="fc029-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="fc029-129">下一步</span><span class="sxs-lookup"><span data-stu-id="fc029-129">Next step</span></span>

<span data-ttu-id="fc029-130">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="fc029-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc029-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fc029-131">See also</span></span>

[<span data-ttu-id="fc029-132">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="fc029-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="fc029-133">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="fc029-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="fc029-134">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="fc029-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="fc029-135">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="fc029-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
