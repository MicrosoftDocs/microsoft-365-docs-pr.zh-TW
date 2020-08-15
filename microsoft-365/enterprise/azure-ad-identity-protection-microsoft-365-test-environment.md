---
title: 適用于 Microsoft 365 企業版測試環境的 Azure AD 身分識別保護
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
description: 設定 Azure AD 身分識別保護，並分析您 Microsoft 365 for enterprise 測試環境中目前的帳戶。
ms.openlocfilehash: bd1e7560e978b13d24e9e93a99a2567adca95c75
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694987"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7ffd6-103">適用于 Microsoft 365 企業版測試環境的 Azure AD 身分識別保護</span><span class="sxs-lookup"><span data-stu-id="7ffd6-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7ffd6-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="7ffd6-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7ffd6-105">Azure Active Directory (Azure AD) 身分識別保護可讓您偵測影響組織身分識別的潛在弱點、設定自動回應，以及調查事件。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="7ffd6-106">本文說明如何使用 Azure AD Identity Protection 來查看測試環境帳戶的分析。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="7ffd6-107">在 Microsoft 365 企業版測試環境中設定 Azure AD 身分識別保護有兩個階段：</span><span class="sxs-lookup"><span data-stu-id="7ffd6-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="7ffd6-108">建立適用于企業測試環境的 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-108">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="7ffd6-109">使用 Azure AD Identity Protection。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-109">Use Azure AD Identity Protection.</span></span>

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="7ffd6-111">按一下[這裡](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，可查看企業用 Microsoft 365 測試實驗室指南堆疊中所有文章的視覺對應。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7ffd6-112">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="7ffd6-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7ffd6-113">如果您只想以具有最低需求的輕量方式測試 Azure AD 身分識別保護，請遵循 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7ffd6-114">如果您想要在模擬的企業中測試 Azure AD 身分識別保護，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7ffd6-115">測試 Azure AD 身分識別保護不需要模擬的企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 Active Directory 網域服務 (AD DS) 樹系的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="7ffd6-116">這裡是以選項形式提供的，可讓您測試 Azure AD 身分識別保護，並在代表一般組織的環境中進行試驗。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="7ffd6-117">階段2：使用 Azure AD 身分識別保護</span><span class="sxs-lookup"><span data-stu-id="7ffd6-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="7ffd6-118">[https://portal.azure.com](https://portal.azure.com)使用 Microsoft 365 for enterprise 測試環境的全域系統管理員帳戶，開啟瀏覽器的私人實例，並登入 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="7ffd6-119">在 Azure 入口網站的搜尋方塊中，輸入 **identity protection** ，然後按一下 [ **Azure AD identity protection**]。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="7ffd6-120">在 [身分 **識別保護-一覽表** ] 中，按一下每個報告以查看報告的內容。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="7ffd6-121">在 [ **通知**] 底下，按一下 [ **使用者時檢查警示**]。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="7ffd6-122">在 [偵測 **到風險的使用者警示** ] 窗格中，選取 [ **中**]。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="7ffd6-123">針對 **電子郵件傳送給下列使用者**，請按一下 [ **包含** ]，並確認您的全域系統管理員帳戶位於選取的成員清單中。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="7ffd6-124">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-124">Click **Save**.</span></span>

<span data-ttu-id="7ffd6-125">按一下 [ **保護** ] 底下的不同原則，以查看如何進行設定。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="7ffd6-126">如果您建立及啟動原則，請確定它不會封鎖太寬的條件範圍，否則您可能無法登入，即使是全域管理員也是一樣。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="7ffd6-127">如需進一步的測試及實驗，請參閱 [模擬風險事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="7ffd6-128">下一步</span><span class="sxs-lookup"><span data-stu-id="7ffd6-128">Next step</span></span>

<span data-ttu-id="7ffd6-129">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="7ffd6-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ffd6-130">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7ffd6-130">See also</span></span>

[<span data-ttu-id="7ffd6-131">身分識別藍圖</span><span class="sxs-lookup"><span data-stu-id="7ffd6-131">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="7ffd6-132">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="7ffd6-132">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7ffd6-133">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="7ffd6-133">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7ffd6-134">適用于企業的 Microsoft 365 檔</span><span class="sxs-lookup"><span data-stu-id="7ffd6-134">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
