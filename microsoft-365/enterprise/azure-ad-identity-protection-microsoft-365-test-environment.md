---
title: Azure AD 身分識別保護您的 Microsoft 365 企業版的測試環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: 設定 Azure AD 身分識別保護及分析 Microsoft 365 企業版測試環境中目前的帳戶。
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866203"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="7de34-103">Azure AD 身分識別保護您的 Microsoft 365 企業版的測試環境</span><span class="sxs-lookup"><span data-stu-id="7de34-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="7de34-p101">Azure AD 身分識別保護可讓您偵測可能會影響您組織的身分識別的弱點、 設定自動的回覆，及調查事件。本文說明如何啟用 Azure AD 身分識別保護及檢視您的測試環境的帳戶的分析。</span><span class="sxs-lookup"><span data-stu-id="7de34-p101">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents. This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="7de34-106">有兩個階段來設定 Microsoft 365 企業版測試環境中的 Azure AD 身分識別保護：</span><span class="sxs-lookup"><span data-stu-id="7de34-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="7de34-107">建立 Microsoft 365 企業版的測試環境。</span><span class="sxs-lookup"><span data-stu-id="7de34-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="7de34-108">啟用並使用 Azure AD 身分識別保護。</span><span class="sxs-lookup"><span data-stu-id="7de34-108">Enable and use Azure AD Identity Protection.</span></span>

![Microsoft Cloud 的測試實驗室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="7de34-110">按一下[這裡](https://aka.ms/m365etlgstack) (英文)，可查看 Microsoft 365 企業版測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="7de34-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="7de34-111">階段 1： 建立您的 Microsoft 365 Enterprise 的測試環境</span><span class="sxs-lookup"><span data-stu-id="7de34-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="7de34-112">如果您只想要測試 Azure AD 身分識別保護的基本需求的輕量型方式，請遵循[輕量型的基本組態](lightweight-base-configuration-microsoft-365-enterprise.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="7de34-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7de34-113">如果您想要測試 Azure AD 身分識別保護模擬 enterprise 中，請遵循[通過驗證](pass-through-auth-m365-ent-test-environment.md)中的指示。</span><span class="sxs-lookup"><span data-stu-id="7de34-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7de34-p102">測試 Azure AD 身分識別保護不需要模擬的企業測試環境中，其中包含連線至網際網路模擬內部網路和 Windows Server AD 樹系目錄同步處理。它會提供這裡是做為選項可以測試 Azure AD 身分識別保護和代表的典型組織的環境中實驗。</span><span class="sxs-lookup"><span data-stu-id="7de34-p102">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="7de34-116">階段 2： 啟用及使用 Azure AD 身分識別保護</span><span class="sxs-lookup"><span data-stu-id="7de34-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="7de34-117">開啟瀏覽器中的私人執行個體，且在 Azure 入口網站登入[https://portal.azure.com](https://portal.azure.com)與 Microsoft 365 企業版測試環境的全域管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="7de34-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="7de34-118">在 Azure 入口網站中，按一下 [**所有服務 > 服務商場**。</span><span class="sxs-lookup"><span data-stu-id="7de34-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="7de34-119">輸入**Azure AD 身分識別保護**，然後按一下。</span><span class="sxs-lookup"><span data-stu-id="7de34-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="7de34-120">**快速入門**blade，在 [**設定**] 下按一下**Onboard** 、 按一下 [**儀表板的 Pin**，然後按一下 [**建立**。</span><span class="sxs-lookup"><span data-stu-id="7de34-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="7de34-121">在 Azure 入口網站中，按一下 [儀表板中的 [ **Azure AD 身分識別保護**]。</span><span class="sxs-lookup"><span data-stu-id="7de34-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="7de34-p103">您應該會看到的儀表板**Azure AD 身分識別保護-概觀 （英文)** blade。下**弱點**，請注意其決定不含多重要素驗證註冊的使用者帳戶的數目。此號碼會隨舊版 Microsoft 365 Enterprise 測試實驗室指南，您已完成。</span><span class="sxs-lookup"><span data-stu-id="7de34-p103">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard. Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration. This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="7de34-125">按一下 [透過**調查**] 以查看是否有任何使用者或已偵測到的事件類別。</span><span class="sxs-lookup"><span data-stu-id="7de34-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="7de34-126">進一步測試及試驗，請參閱[Simulating 風險事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。</span><span class="sxs-lookup"><span data-stu-id="7de34-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="7de34-127">請參閱[危害針對認證 Protect](identity-azure-ad-identity-protection.md)步驟的 「 身分識別 」 階段的資訊和部署 Azure AD 身分識別保護在生產環境中的連結。</span><span class="sxs-lookup"><span data-stu-id="7de34-127">See the [Protect against credential compromise](identity-azure-ad-identity-protection.md) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="7de34-128">下一步</span><span class="sxs-lookup"><span data-stu-id="7de34-128">Next step</span></span>

<span data-ttu-id="7de34-129">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="7de34-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7de34-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7de34-130">See also</span></span>

[<span data-ttu-id="7de34-131">階段 2：身分識別</span><span class="sxs-lookup"><span data-stu-id="7de34-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="7de34-132">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="7de34-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7de34-133">Microsoft 365 企業版部署</span><span class="sxs-lookup"><span data-stu-id="7de34-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="7de34-134">Microsoft 365 企業版文件</span><span class="sxs-lookup"><span data-stu-id="7de34-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
