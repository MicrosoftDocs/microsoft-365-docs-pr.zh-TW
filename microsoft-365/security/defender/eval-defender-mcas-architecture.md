---
title: 複查架構需求和 Microsoft Cloud App Security 的結構，並透過瞭解雲端 App 安全性中的架構來規劃設定及設計 Microsoft 365 Defender
description: Microsoft Cloud App Security 技術圖表說明 Microsoft 365 Defender 中的架構，這會協助您建立試驗環境。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: a3fa9670262b90d1566c375680946a131bb9c78a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457608"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-cloud-app-security"></a><span data-ttu-id="9332e-103">回顧 Microsoft Cloud App Security 的架構需求和重要概念</span><span class="sxs-lookup"><span data-stu-id="9332e-103">Review architecture requirements and key concepts for Microsoft Cloud App Security</span></span>


<span data-ttu-id="9332e-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="9332e-104">**Applies to:**</span></span>

- <span data-ttu-id="9332e-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9332e-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="9332e-106">本文是為 Microsoft Cloud App Security 和 Microsoft 365 Defender 設定評估環境的程式中的[步驟1，共 3](eval-defender-mcas-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="9332e-106">This article is [Step 1 of 3](eval-defender-mcas-overview.md) in the process of setting up the evaluation environment for Microsoft Cloud App Security alongside Microsoft 365 Defender.</span></span> <span data-ttu-id="9332e-107">如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-identity-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="9332e-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="9332e-108">在啟用 Microsoft Cloud App Security 之前，請確定您瞭解架構，並且可以符合需求。</span><span class="sxs-lookup"><span data-stu-id="9332e-108">Before enabling Microsoft Cloud App Security, be sure you understand the architecture and can meet the requirements.</span></span> 

## <a name="understand-the-architecture"></a><span data-ttu-id="9332e-109">了解架構</span><span class="sxs-lookup"><span data-stu-id="9332e-109">Understand the architecture</span></span>

<span data-ttu-id="9332e-110">Microsoft Cloud App Security 是雲端存取安全性經紀人 (CASB) 。</span><span class="sxs-lookup"><span data-stu-id="9332e-110">Microsoft Cloud App Security is a Cloud Access Security Broker (CASB).</span></span> <span data-ttu-id="9332e-111">不論您的使用者位於何處，不論其所使用的裝置為何，CASBs 都會以即時從您的企業使用者與雲端資源之間的身分進入代理程式。</span><span class="sxs-lookup"><span data-stu-id="9332e-111">CASBs act a gatekeeper to broker access in real time between your enterprise users and cloud resources they use, wherever your users are located and regardless of the device they are using.</span></span> <span data-ttu-id="9332e-112">Microsoft Cloud App Security 原本會與 Microsoft 安全性功能（包括 Microsoft 365 Defender）整合。</span><span class="sxs-lookup"><span data-stu-id="9332e-112">Microsoft Cloud App Security natively integrates with Microsoft security capabilities, including Microsoft 365 Defender.</span></span> 

<span data-ttu-id="9332e-113">沒有雲端 App 安全性，您組織使用的雲端應用程式是非受管理及未受保護的，如圖例所示。</span><span class="sxs-lookup"><span data-stu-id="9332e-113">Without Cloud App Security, cloud apps that are used by your organization are unmanaged and unprotected, as illustrated.</span></span>

![Microsoft Cloud App Security 的架構](../../media/defender/m365-defender-mcas-architecture-a.png)

<span data-ttu-id="9332e-115">在此圖例中：</span><span class="sxs-lookup"><span data-stu-id="9332e-115">In the illustration:</span></span>
- <span data-ttu-id="9332e-116">組織使用雲端 app 的方式受到監控且不受保護。</span><span class="sxs-lookup"><span data-stu-id="9332e-116">The use of cloud apps by an organization is unmonitored and unprotected.</span></span> 
- <span data-ttu-id="9332e-117">這種用法會超出受管理組織內的保護。</span><span class="sxs-lookup"><span data-stu-id="9332e-117">This use falls outside the protections achieved within a managed organization.</span></span> 

#### <a name="discovering-cloud-apps"></a><span data-ttu-id="9332e-118">探索 cloud app</span><span class="sxs-lookup"><span data-stu-id="9332e-118">Discovering cloud apps</span></span>

<span data-ttu-id="9332e-119">管理雲端 app 使用的第一個步驟是探索您的組織所使用的雲端應用程式。</span><span class="sxs-lookup"><span data-stu-id="9332e-119">The first step to managing the use of cloud apps is to discover which cloud apps are used by your organization.</span></span> <span data-ttu-id="9332e-120">下圖說明 cloud discovery 如何與雲端 App 安全性搭配運作。</span><span class="sxs-lookup"><span data-stu-id="9332e-120">This next diagram illustrates how cloud discovery works with Cloud App Security.</span></span>

![Microsoft Cloud App Security-Cloud discovery 的架構](../../media/defender/m365-defender-mcas-architecture-b.png)

<span data-ttu-id="9332e-122">在此圖例中，有兩種方法可以用來監視網路流量，以及如何探索您的組織所使用的雲端應用程式。</span><span class="sxs-lookup"><span data-stu-id="9332e-122">In this illustration, there are two methods that can be used to monitor network traffic and discover cloud apps that are being used by your organization.</span></span>
- <span data-ttu-id="9332e-123">答：</span><span class="sxs-lookup"><span data-stu-id="9332e-123">A.</span></span> <span data-ttu-id="9332e-124">雲端應用程式探索與 Microsoft Defender for Endpoint 本來整合。</span><span class="sxs-lookup"><span data-stu-id="9332e-124">Cloud App Discovery integrates with Microsoft Defender for Endpoint natively.</span></span> <span data-ttu-id="9332e-125">Defender for Endpoint 報告從 IT 管理的 Windows 10 裝置存取的雲端應用程式和服務。</span><span class="sxs-lookup"><span data-stu-id="9332e-125">Defender for Endpoint reports cloud apps and services being accessed from IT-managed Windows 10 devices.</span></span> 
- <span data-ttu-id="9332e-126">B。</span><span class="sxs-lookup"><span data-stu-id="9332e-126">B.</span></span> <span data-ttu-id="9332e-127">若要在連接至網路的所有裝置上進行覆蓋率，雲端 App 安全性記錄收集器會安裝在防火牆和其他 proxy 上，以從端點收集資料。</span><span class="sxs-lookup"><span data-stu-id="9332e-127">For coverage on all devices connected to a network, the Cloud App Security log collector is installed on firewalls and other proxies to collect data from endpoints.</span></span> <span data-ttu-id="9332e-128">此資料會傳送至雲端 App 安全性以進行分析。</span><span class="sxs-lookup"><span data-stu-id="9332e-128">This data is sent to Cloud App Security for analysis.</span></span>

#### <a name="managing-cloud-apps"></a><span data-ttu-id="9332e-129">管理雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="9332e-129">Managing cloud apps</span></span>

<span data-ttu-id="9332e-130">在您探索 cloud app 並分析您的組織使用這些應用程式的行為後，即可開始管理所選擇的雲端應用程式。</span><span class="sxs-lookup"><span data-stu-id="9332e-130">After you discover cloud apps and analyze the behavior of how these are used by your organization, you can begin managing cloud apps that you choose.</span></span> 

![Microsoft Cloud App Security 管理雲端應用程式的架構](../../media/defender/m365-defender-mcas-architecture-c.png)

<span data-ttu-id="9332e-132">在此圖中：</span><span class="sxs-lookup"><span data-stu-id="9332e-132">In this illustration:</span></span>
- <span data-ttu-id="9332e-133">某些應用程式是 sanctioned 供使用。</span><span class="sxs-lookup"><span data-stu-id="9332e-133">Some apps are sanctioned for use.</span></span> <span data-ttu-id="9332e-134">這是一種開始管理應用程式的簡易方法。</span><span class="sxs-lookup"><span data-stu-id="9332e-134">This is a simple way of beginning to manage apps.</span></span>
- <span data-ttu-id="9332e-135">您可以將應用程式連接至應用程式連接器，以啟用更深入的洞察力和控制。</span><span class="sxs-lookup"><span data-stu-id="9332e-135">You can enable greater visibility and control by connecting apps with app connectors.</span></span> <span data-ttu-id="9332e-136">應用程式連接器會使用應用程式提供者的 APIs。</span><span class="sxs-lookup"><span data-stu-id="9332e-136">App connectors use the APIs of app providers.</span></span>


#### <a name="applying-session-controls-to-cloud-apps"></a><span data-ttu-id="9332e-137">將會話控制套用至雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="9332e-137">Applying session controls to cloud apps</span></span>

<span data-ttu-id="9332e-138">Microsoft Cloud App Security 充當反向 proxy，提供 sanctioned 雲端應用程式的 proxy 存取權。</span><span class="sxs-lookup"><span data-stu-id="9332e-138">Microsoft Cloud App Security serves as a reverse proxy, providing proxy access to sanctioned cloud apps.</span></span> <span data-ttu-id="9332e-139">這可讓雲端 App 安全性套用您所設定的會話控制。</span><span class="sxs-lookup"><span data-stu-id="9332e-139">This allows Cloud App Security to apply session controls that you configure.</span></span> 

![Microsoft Cloud App Security Proxy 存取會話控制的架構](../../media/defender/m365-defender-mcas-architecture-d.png)

<span data-ttu-id="9332e-141">在此圖中：</span><span class="sxs-lookup"><span data-stu-id="9332e-141">In this illustration:</span></span>
- <span data-ttu-id="9332e-142">從組織中的使用者和裝置 sanctioned 雲端應用程式的存取，都是透過雲端 App 安全性進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="9332e-142">Access to sanctioned cloud apps from users and devices in your organization is routed through Cloud App Security.</span></span>
- <span data-ttu-id="9332e-143">這種 proxy 存取允許套用會話控制。</span><span class="sxs-lookup"><span data-stu-id="9332e-143">This proxy access allows session controls to be applied.</span></span>
- <span data-ttu-id="9332e-144">您未 sanctioned 或明確 unsanctioned 的雲端應用程式不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="9332e-144">Cloud apps that you have not sanctioned or explicitly unsanctioned are not affected.</span></span>

<span data-ttu-id="9332e-145">會話控制可讓您將參數套用到您的組織使用雲端 app 的方式。</span><span class="sxs-lookup"><span data-stu-id="9332e-145">Session controls allow you to apply parameters to how cloud apps are used by your organization.</span></span> <span data-ttu-id="9332e-146">例如，如果您的組織使用的是 Salesforce，您可以設定只允許受管理的裝置存取 Salesforce 中組織之資料的會話原則。</span><span class="sxs-lookup"><span data-stu-id="9332e-146">For example, if your organization is using Salesforce, you can configure a session policy that allows only managed devices to access your organization's data in Salesforce.</span></span> <span data-ttu-id="9332e-147">較簡單的範例可能是設定原則，以監控來自未受管理裝置的流量，這樣您就可以在套用更嚴格的原則之前分析此流量的風險。</span><span class="sxs-lookup"><span data-stu-id="9332e-147">A simpler example could be configuring a policy to monitor traffic from unmanaged devices so you can analyze the risk of this traffic before applying stricter policies.</span></span>

#### <a name="integrating-with-azure-ad-with-conditional-access-app-control"></a><span data-ttu-id="9332e-148">使用條件式存取應用程式控制與 Azure AD 整合</span><span class="sxs-lookup"><span data-stu-id="9332e-148">Integrating with Azure AD with Conditional Access App Control</span></span>

<span data-ttu-id="9332e-149">您的 Azure AD 租使用者可能已加入 SaaS 應用程式，以強制執行多重要素驗證及其他條件式存取原則。</span><span class="sxs-lookup"><span data-stu-id="9332e-149">You might already have SaaS apps added to your Azure AD tenant to enforce multi-factor authentication and other conditional access policies.</span></span> <span data-ttu-id="9332e-150">Microsoft Cloud App Security 原本與 Azure AD 整合。</span><span class="sxs-lookup"><span data-stu-id="9332e-150">Microsoft Cloud App Security natively integrates with Azure AD.</span></span> <span data-ttu-id="9332e-151">您只需要設定 Azure AD 中的原則，即可在雲端 App 安全性中使用條件式存取應用程式控制。</span><span class="sxs-lookup"><span data-stu-id="9332e-151">All you have to do is configure a policy in Azure AD to use Conditional Access App Control in Cloud App Security.</span></span> <span data-ttu-id="9332e-152">這會透過雲端 App 安全性以 proxy 方式路由傳送這些受管理的 SaaS 應用程式的網路流量，這可讓雲端 App 安全性監視此流量，以及套用會話控制。</span><span class="sxs-lookup"><span data-stu-id="9332e-152">This routes network traffic for these managed SaaS apps through Cloud App Security as a proxy, which allows Cloud App Security to monitor this traffic and to apply session controls.</span></span> 

![Microsoft Cloud App Security SaaS 應用程式的架構](../../media/defender/m365-defender-mcas-architecture-e.png)

<span data-ttu-id="9332e-154">在此圖中：</span><span class="sxs-lookup"><span data-stu-id="9332e-154">In this illustration:</span></span>
- <span data-ttu-id="9332e-155">SaaS 應用程式會與 Azure AD 租使用者整合。</span><span class="sxs-lookup"><span data-stu-id="9332e-155">SaaS apps are integrated with the Azure AD tenant.</span></span> <span data-ttu-id="9332e-156">這可讓 Azure AD 強制執行條件式存取原則，包括多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="9332e-156">This allows Azure AD to enforce conditional access policies, including multi-factor authentication.</span></span>
- <span data-ttu-id="9332e-157">原則會新增至 Azure Active Directory，以將 SaaS 應用程式的流量導向雲端 App 安全性。</span><span class="sxs-lookup"><span data-stu-id="9332e-157">A policy is added to Azure Active Directory to direct traffic for SaaS apps to Cloud App Security.</span></span> <span data-ttu-id="9332e-158">原則會指定要套用此原則 SaaS 應用程式。</span><span class="sxs-lookup"><span data-stu-id="9332e-158">The policy specifies which SaaS apps to apply this policy to.</span></span> <span data-ttu-id="9332e-159">因此，azure ad 強制執行套用到這些 SaaS 應用程式的任何條件式存取原則之後，azure ad 便會透過雲端 App 安全性將會話流量導向 (proxy) 。</span><span class="sxs-lookup"><span data-stu-id="9332e-159">Consequently, after Azure AD enforces any conditional access policies that apply to these SaaS apps, Azure AD then directs (proxies) the session traffic through Cloud App Security.</span></span>
- <span data-ttu-id="9332e-160">雲端 App 安全性會監控這種流量，並套用系統管理員所設定的任何會話控制原則。</span><span class="sxs-lookup"><span data-stu-id="9332e-160">Cloud App Security monitors this traffic and applies any session control policies that have been configured by administrators.</span></span> 

<span data-ttu-id="9332e-161">您可能已使用尚未新增至 Azure AD 的雲端 App 安全性發現並 sanctioned 雲端應用程式。</span><span class="sxs-lookup"><span data-stu-id="9332e-161">You might have discovered and sanctioned cloud apps using Cloud App Security that have not been added to Azure AD.</span></span> <span data-ttu-id="9332e-162">您可以將這些雲端應用程式新增至您的 Azure AD 租使用者和條件式存取規則的範圍，以充分利用條件式存取應用程式控制。</span><span class="sxs-lookup"><span data-stu-id="9332e-162">You can take advantage of Conditional Access App Control by adding these cloud apps to your Azure AD tenant and the scope of your conditional access rules.</span></span>

#### <a name="protecting-your-organization-from-hackers"></a><span data-ttu-id="9332e-163">保護您的組織不受駭客攻擊</span><span class="sxs-lookup"><span data-stu-id="9332e-163">Protecting your organization from hackers</span></span>

<span data-ttu-id="9332e-164">雲端 App 安全性自行提供強大的保護。</span><span class="sxs-lookup"><span data-stu-id="9332e-164">Cloud App Security provides powerful protection on its own.</span></span> <span data-ttu-id="9332e-165">不過，與 Microsoft 365 Defender 的其他功能一起使用時，雲端 App 安全性會將資料提供給共用信號，以協助停止攻擊。</span><span class="sxs-lookup"><span data-stu-id="9332e-165">However, when combined with the other capabilities of Microsoft 365 Defender, Cloud App Security provides data into the shared signals which, together, helps stop attacks.</span></span>

<span data-ttu-id="9332e-166">您有必要將此圖例從概述中重複此 Microsoft 365 Defender 評估與試驗指南。</span><span class="sxs-lookup"><span data-stu-id="9332e-166">It's worth repeating this illustration from the overview to this Microsoft 365 Defender evaluation and pilot guide.</span></span> 

![Microsoft 365 Defender 如何停止威脅鏈](../../media/defender/m365-defender-eval-threat-chain.png)

<span data-ttu-id="9332e-168">著重于此圖的右側，Microsoft Cloud App Security 會發現反常行為，例如不可能的旅行、認證存取，以及不尋常的下載、檔案共用或郵件轉寄活動，並向安全小組報告這些行為。</span><span class="sxs-lookup"><span data-stu-id="9332e-168">Focusing on the right side of this illustration, Microsoft Cloud App Security notices anomalous behavior like impossible-travel, credential access, and unusual download, file share, or mail forwarding activity and reports these to the security team.</span></span> <span data-ttu-id="9332e-169">因此，雲端 App 安全性協助防止駭客和機密資料 exfiltration 的側向移動。</span><span class="sxs-lookup"><span data-stu-id="9332e-169">Consequently, Cloud App Security helps prevent lateral movement by hackers and exfiltration of sensitive data.</span></span> <span data-ttu-id="9332e-170">Microsoft 356 Defender 會將所有元件的信號關聯起來，以提供完整的攻擊案例。</span><span class="sxs-lookup"><span data-stu-id="9332e-170">Microsoft 356 Defender correlates the signals from all the components to provide the full attack story.</span></span>

## <a name="understand-key-concepts"></a><span data-ttu-id="9332e-171">瞭解重要概念</span><span class="sxs-lookup"><span data-stu-id="9332e-171">Understand key concepts</span></span>

<span data-ttu-id="9332e-172">下表識別重要概念，在評估、設定及部署 Microsoft Cloud App Security 時，請務必瞭解。</span><span class="sxs-lookup"><span data-stu-id="9332e-172">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Cloud App Security.</span></span>


|<span data-ttu-id="9332e-173">概念</span><span class="sxs-lookup"><span data-stu-id="9332e-173">Concept</span></span>  |<span data-ttu-id="9332e-174">描述</span><span class="sxs-lookup"><span data-stu-id="9332e-174">Description</span></span> |<span data-ttu-id="9332e-175">其他資訊</span><span class="sxs-lookup"><span data-stu-id="9332e-175">More information</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="9332e-176">雲端 App 安全性儀錶 板</span><span class="sxs-lookup"><span data-stu-id="9332e-176">Cloud App Security Dashboard</span></span> | <span data-ttu-id="9332e-177">提供組織最重要資訊的概述，並提供更深入調查的連結。</span><span class="sxs-lookup"><span data-stu-id="9332e-177">Presents an overview of the most important information about your organization and gives links to deeper investigation.</span></span>        | [<span data-ttu-id="9332e-178">使用儀表板 </span><span class="sxs-lookup"><span data-stu-id="9332e-178">Working with the dashboard </span></span>](/cloud-app-security/daily-activities-to-protect-your-cloud-environment)       |
| <span data-ttu-id="9332e-179">條件式存取應用程式控制</span><span class="sxs-lookup"><span data-stu-id="9332e-179">Conditional Access App Control</span></span>    | <span data-ttu-id="9332e-180">與您的身分識別提供者整合的反向 proxy 架構 (IdP) 提供 Azure AD 條件式存取原則，並選擇性地強制執行會話控制。</span><span class="sxs-lookup"><span data-stu-id="9332e-180">Reverse proxy architecture that integrates with your Identity Provider (IdP) to give Azure AD conditional access policies and selectively enforce session controls.</span></span>        |  [<span data-ttu-id="9332e-181">使用 Microsoft Cloud App Security 條件式存取應用程式控制來保護應用程式</span><span class="sxs-lookup"><span data-stu-id="9332e-181">Protect apps with Microsoft Cloud App Security Conditional Access App Control</span></span>](/cloud-app-security/proxy-intro-aad)       |
|  <span data-ttu-id="9332e-182">雲端應用程式目錄</span><span class="sxs-lookup"><span data-stu-id="9332e-182">Cloud App Catalog</span></span>   | <span data-ttu-id="9332e-183">雲端應用程式目錄可讓您根據超過80個風險因素的排名及計分的 Microsoft Catalog over 16000 雲端 app 的完整圖片。</span><span class="sxs-lookup"><span data-stu-id="9332e-183">The Cloud App Catalog gives you a full picture against Microsoft catalog of over 16,000 cloud apps that are ranked and scored based on more than 80 risk factors.</span></span>    |  [<span data-ttu-id="9332e-184">使用應用程式風險分數</span><span class="sxs-lookup"><span data-stu-id="9332e-184">Working with App risk scores</span></span>](/cloud-app-security/risk-score)       |
| <span data-ttu-id="9332e-185">雲端探索儀表板</span><span class="sxs-lookup"><span data-stu-id="9332e-185">Cloud Discovery Dashboard</span></span>    | <span data-ttu-id="9332e-186">雲端探索會分析流量記錄檔，其設計目的是讓您更深入地瞭解如何在組織中使用雲端應用程式，以及提供警示和風險層級。</span><span class="sxs-lookup"><span data-stu-id="9332e-186">Cloud Discovery analyzes your traffic logs and is designed to give more insight into how cloud apps are being used in your organization as well as give alerts and risk levels.</span></span>     |  [<span data-ttu-id="9332e-187">使用探索的應用程式   </span><span class="sxs-lookup"><span data-stu-id="9332e-187">Working with discovered apps   </span></span>](/cloud-app-security/discovered-apps)    |
|<span data-ttu-id="9332e-188">連線的應用程式</span><span class="sxs-lookup"><span data-stu-id="9332e-188">Connected Apps</span></span> |<span data-ttu-id="9332e-189">雲端 App 安全性使用「雲端對雲端整合」、「API 連接器」和「即時存取」和「會話」控制，利用我們的條件式應用程式存取控制，為連接的應用程式提供端對端保護。</span><span class="sxs-lookup"><span data-stu-id="9332e-189">Cloud App Security provides end-to-end protection for connected apps using Cloud-to-Cloud integration, API connectors, and real-time access and session controls leveraging our Conditional App Access Controls.</span></span> |[<span data-ttu-id="9332e-190">保護連線的應用程式</span><span class="sxs-lookup"><span data-stu-id="9332e-190">Protecting connected apps</span></span>](/cloud-app-security/protect-connected-apps) |
| | | |

## <a name="review-architecture-requirements"></a><span data-ttu-id="9332e-191">評審架構需求</span><span class="sxs-lookup"><span data-stu-id="9332e-191">Review architecture requirements</span></span>

### <a name="discovering-cloud-apps"></a><span data-ttu-id="9332e-192">探索 cloud app</span><span class="sxs-lookup"><span data-stu-id="9332e-192">Discovering cloud apps</span></span>

<span data-ttu-id="9332e-193">若要探索您環境中使用的雲端應用程式，您可以執行下列其中一項或兩項操作：</span><span class="sxs-lookup"><span data-stu-id="9332e-193">To discover cloud apps used in your environment, you can do one or both of the following:</span></span>

- <span data-ttu-id="9332e-194">與 Microsoft Defender for Endpoint 整合，透過雲端探索快速取得並執行。</span><span class="sxs-lookup"><span data-stu-id="9332e-194">Get up and running quickly with Cloud Discovery by integrating with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="9332e-195">這種原生整合可讓您立即開始在網路上的 Windows 10 裝置之間收集雲端流量的資料。</span><span class="sxs-lookup"><span data-stu-id="9332e-195">This native integration enables you to immediately start collecting data on cloud traffic across your Windows 10 devices, on and off your network.</span></span>
- <span data-ttu-id="9332e-196">若要探索所有連接至網路之裝置存取的所有雲端應用程式，請在防火牆和其他 proxy 上部署雲端 App 安全性的記錄收集器。</span><span class="sxs-lookup"><span data-stu-id="9332e-196">To discover all cloud apps accessed by all devices connected to your network, deploy the Cloud App Security log collector on your firewalls and other proxies.</span></span> <span data-ttu-id="9332e-197">這樣會從您的端點收集資料，並將其傳送至雲端 App 安全性以進行分析。</span><span class="sxs-lookup"><span data-stu-id="9332e-197">This collects data from your endpoints and sends it to Cloud App Security for analysis.</span></span> <span data-ttu-id="9332e-198">雲端 App 安全性原本會與某些協力廠商 proxy 整合，以取得更多功能。</span><span class="sxs-lookup"><span data-stu-id="9332e-198">Cloud App Security natively integrates with some third-party proxies for even more capabilities.</span></span>

<span data-ttu-id="9332e-199">這些選項包含在 [步驟2。啟用評估環境](eval-defender-mcas-enable-eval.md)。</span><span class="sxs-lookup"><span data-stu-id="9332e-199">These options are included in [Step 2. Enable the evaluation environment](eval-defender-mcas-enable-eval.md).</span></span> 

### <a name="applying-azure-ad-conditional-access-policies-to-cloud-apps"></a><span data-ttu-id="9332e-200">將 Azure AD 條件式存取原則套用至雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="9332e-200">Applying Azure AD Conditional Access policies to cloud apps</span></span>

<span data-ttu-id="9332e-201">條件式存取應用程式控制 (將條件式存取原則套用至雲端 app) 需要與 Azure AD 整合的功能。</span><span class="sxs-lookup"><span data-stu-id="9332e-201">Conditional Access App Control (the ability to apply Conditional Access policies to cloud apps) requires integration with Azure AD.</span></span> <span data-ttu-id="9332e-202">這不是雲端 App 安全性開始使用的必要條件。</span><span class="sxs-lookup"><span data-stu-id="9332e-202">This isn't a requirement for getting started with Cloud App Security.</span></span> <span data-ttu-id="9332e-203">這是我們建議您在試驗階段（步驟3）嘗試的步驟[。試驗 Microsoft Cloud App Security](eval-defender-mcas-pilot.md)。</span><span class="sxs-lookup"><span data-stu-id="9332e-203">It is a step we encourage you to try out during the pilot phase — [Step 3. Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md).</span></span>

## <a name="siem-integration"></a><span data-ttu-id="9332e-204">SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="9332e-204">SIEM integration</span></span>

<span data-ttu-id="9332e-205">您可以將 Microsoft Cloud App Security 與一般 SIEM server 或 Azure Sentinel 整合，以啟用來自已連線應用程式之警示和活動的集中式監視。</span><span class="sxs-lookup"><span data-stu-id="9332e-205">You can integrate Microsoft Cloud App Security with your generic SIEM server or with Azure Sentinel to enable centralized monitoring of alerts and activities from connected apps.</span></span> 

<span data-ttu-id="9332e-206">此外，Azure sentinel 包含的 Microsoft Cloud App Security 連接器，可提供與 Azure Sentinel 的深度整合。</span><span class="sxs-lookup"><span data-stu-id="9332e-206">Additionally, Azure Sentinel includes a Microsoft Cloud App Security connector to provide deeper integration with Azure Sentinel.</span></span> <span data-ttu-id="9332e-207">這可讓您不僅能看到您的雲端應用程式，還可取得複雜的分析，以識別及抗擊 cyberthreats，以及控制資料的移動方式。</span><span class="sxs-lookup"><span data-stu-id="9332e-207">This enables you to not only gain visibility into your cloud apps but to also get sophisticated analytics to identify and combat cyberthreats and to control how your data travels.</span></span>

- [<span data-ttu-id="9332e-208">一般 SIEM 整合</span><span class="sxs-lookup"><span data-stu-id="9332e-208">Generic SIEM integration</span></span>](/cloud-app-security/siem)
- [<span data-ttu-id="9332e-209">從 MCAS 到 Azure Sentinel 的資料流程警示和雲端探索記錄</span><span class="sxs-lookup"><span data-stu-id="9332e-209">Stream alerts and Cloud Discovery logs from MCAS into Azure Sentinel</span></span>](/azure/sentinel/connect-cloud-app-security)

### <a name="next-steps"></a><span data-ttu-id="9332e-210">後續步驟</span><span class="sxs-lookup"><span data-stu-id="9332e-210">Next steps</span></span>

<span data-ttu-id="9332e-211">步驟2之3：[為 Microsoft Cloud App Security 啟用評估環境](eval-defender-mcas-enable-eval.md)</span><span class="sxs-lookup"><span data-stu-id="9332e-211">Step 2 of 3: [Enable the evaluation environment for Microsoft Cloud App Security](eval-defender-mcas-enable-eval.md)</span></span>

<span data-ttu-id="9332e-212">回到 [[評估 Microsoft Cloud App Security](eval-defender-mcas-overview.md)的總覽</span><span class="sxs-lookup"><span data-stu-id="9332e-212">Return to the overview for [Evaluate Microsoft Cloud App Security](eval-defender-mcas-overview.md)</span></span>

<span data-ttu-id="9332e-213">回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述</span><span class="sxs-lookup"><span data-stu-id="9332e-213">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>