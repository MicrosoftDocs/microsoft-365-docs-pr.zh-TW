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
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487705"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3996f-103">適用于 Microsoft 365 企業版測試環境的 Azure AD 身分識別保護</span><span class="sxs-lookup"><span data-stu-id="3996f-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3996f-104">*此測試實驗室指南僅可用於適用于企業測試環境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="3996f-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="3996f-105">您可以使用 Azure Active Directory (Azure AD) 身分識別保護，偵測影響組織身分識別的潛在弱點、設定自動回應，以及調查事件。</span><span class="sxs-lookup"><span data-stu-id="3996f-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="3996f-106">本文說明如何使用 Azure AD Identity Protection 來查看測試環境帳戶的分析。</span><span class="sxs-lookup"><span data-stu-id="3996f-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="3996f-107">在 Microsoft 365 for enterprise 測試環境中設定 Azure AD 身分識別保護包括兩個階段：</span><span class="sxs-lookup"><span data-stu-id="3996f-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="3996f-108">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="3996f-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="3996f-109">階段2：使用 Azure AD 身分識別保護</span><span class="sxs-lookup"><span data-stu-id="3996f-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Microsoft Cloud 的測試實驗室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="3996f-111">如需 Microsoft 365 for enterprise 測試實驗室指南堆疊中所有文章的視覺對應，請移至 [microsoft 365 for Enterprise Test Lab Guide 堆疊](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="3996f-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="3996f-112">階段1：組建您的 Microsoft 365 企業版測試環境</span><span class="sxs-lookup"><span data-stu-id="3996f-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="3996f-113">如果您只想以輕量的方式測試 Azure AD 身分識別保護，請依照 [輕量基本](lightweight-base-configuration-microsoft-365-enterprise.md)設定中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="3996f-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="3996f-114">如果您想要在模擬的企業中測試 Azure AD 身分識別保護，請依照 [傳遞驗證](pass-through-auth-m365-ent-test-environment.md)中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="3996f-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3996f-115">測試 Azure AD 身分識別保護不需要模擬企業測試環境，其中包括連線至網際網路的模擬內部網路與目錄同步處理，以及 (AD DS) 樹系中的 Active Directory 網域服務的目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="3996f-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="3996f-116">這裡是以選項形式提供的，可讓您測試 Azure AD 身分識別保護，並在代表一般組織的環境中進行試驗。</span><span class="sxs-lookup"><span data-stu-id="3996f-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="3996f-117">階段2：使用 Azure AD 身分識別保護</span><span class="sxs-lookup"><span data-stu-id="3996f-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="3996f-118">[https://portal.azure.com](https://portal.azure.com)使用 Microsoft 365 for enterprise 測試環境的全域系統管理員帳戶，開啟瀏覽器的私人實例，並登入 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="3996f-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="3996f-119">在 Azure 入口網站的搜尋方塊中，輸入 **identity protection** ，然後選取 **Azure AD identity protection**。</span><span class="sxs-lookup"><span data-stu-id="3996f-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="3996f-120">在 [身分 **識別保護-一覽表** ] 中，選取每個報告以查看其報告。</span><span class="sxs-lookup"><span data-stu-id="3996f-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="3996f-121">在 [ **通知**] 底下，選取 [ **使用者的風險偵測警示**]。</span><span class="sxs-lookup"><span data-stu-id="3996f-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="3996f-122">在 [偵測 **到風險的使用者警示** ] 窗格中，選取 [ **中**]。</span><span class="sxs-lookup"><span data-stu-id="3996f-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="3996f-123">**若要將電子郵件傳送給下列使用者**，請選取 [**包含**]，並確認您的全域系統管理員帳戶位於選取的成員清單中。</span><span class="sxs-lookup"><span data-stu-id="3996f-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="3996f-124">選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="3996f-124">Select **Save**.</span></span>

<span data-ttu-id="3996f-125">在 [ **保護**] 底下，選取 [各種原則] 以查看如何進行設定。</span><span class="sxs-lookup"><span data-stu-id="3996f-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="3996f-126">如果您建立並啟用原則，請確定其不會封鎖所有使用者的存取，否則您可能無法登入。</span><span class="sxs-lookup"><span data-stu-id="3996f-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="3996f-127">若要避免這種情況，請排除特定的使用者帳戶，例如全域管理員。</span><span class="sxs-lookup"><span data-stu-id="3996f-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="3996f-128">如需進一步的測試及實驗，請參閱 [模擬風險事件](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)。</span><span class="sxs-lookup"><span data-stu-id="3996f-128">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="3996f-129">下一步</span><span class="sxs-lookup"><span data-stu-id="3996f-129">Next step</span></span>

<span data-ttu-id="3996f-130">瀏覽測試環境中的其他[身分識別](m365-enterprise-test-lab-guides.md#identity)功能。</span><span class="sxs-lookup"><span data-stu-id="3996f-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="3996f-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3996f-131">See also</span></span>

[<span data-ttu-id="3996f-132">身分識別藍圖</span><span class="sxs-lookup"><span data-stu-id="3996f-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="3996f-133">Microsoft 365 企業版測試實驗室指南</span><span class="sxs-lookup"><span data-stu-id="3996f-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3996f-134">Microsoft 365 企業版概觀</span><span class="sxs-lookup"><span data-stu-id="3996f-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="3996f-135">適用于企業的 Microsoft 365 檔</span><span class="sxs-lookup"><span data-stu-id="3996f-135">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
