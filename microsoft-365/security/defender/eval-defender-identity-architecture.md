---
title: 檢查架構需求和 Microsoft Defender for Identity、架構圖表、MDI 的技術架構
description: Microsoft Defender for identity in Microsoft 365 Defender 的技術圖表可協助您在建立試用實驗室或試驗環境之前，先瞭解 Microsoft 365 中的身分識別。
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 8f0c736d07a2a66420416d30ae2dc45ae5fee37a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457888"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-identity"></a><span data-ttu-id="37b0e-103">審閱 Microsoft Defender 身分識別的架構需求和重要概念</span><span class="sxs-lookup"><span data-stu-id="37b0e-103">Review architecture requirements and key concepts for Microsoft Defender for Identity</span></span>


<span data-ttu-id="37b0e-104">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="37b0e-104">**Applies to:**</span></span>
- <span data-ttu-id="37b0e-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37b0e-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="37b0e-106">本文是設定 Microsoft Defender 身分識別的評估環境過程中的 [步驟1之 3](eval-defender-identity-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="37b0e-106">This article is [Step 1 of 3](eval-defender-identity-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Identity.</span></span> <span data-ttu-id="37b0e-107">如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-identity-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="37b0e-107">For more information about this process, see the [overview article](eval-defender-identity-overview.md).</span></span>

<span data-ttu-id="37b0e-108">在啟用 Microsoft Defender 身分識別之前，請確定您瞭解架構並可滿足需求。</span><span class="sxs-lookup"><span data-stu-id="37b0e-108">Before enabling Microsoft Defender for Identity, be sure you understand the architecture and can meet the requirements.</span></span>

<span data-ttu-id="37b0e-109">Microsoft Defender for Identity 使用 machine 教學和行為分析來識別內部部署網路中的攻擊，以及偵測和主動預防使用者登入與雲端身分識別相關聯的風險。</span><span class="sxs-lookup"><span data-stu-id="37b0e-109">Microsoft Defender for Identity uses machine learning and behavioral analytics to identify attacks across your on-premises network along with detecting and proactively preventing user sign-in risks associated with cloud identities.</span></span> <span data-ttu-id="37b0e-110">如需詳細資訊，請參閱 [什麼是 Microsoft Defender 身分識別？](/defender-for-identity/what-is)</span><span class="sxs-lookup"><span data-stu-id="37b0e-110">For more information, see [What is Microsoft Defender for Identity?](/defender-for-identity/what-is)</span></span>

<span data-ttu-id="37b0e-111">用於身分識別的身分識別會保護您的內部部署 Active Directory 使用者和/或已同步處理至 Azure Active Directory (Azure AD) 的使用者。</span><span class="sxs-lookup"><span data-stu-id="37b0e-111">Defender for Identity protects your on-premises Active Directory users and/or users synced to your Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="37b0e-112">若要保護只由 Azure AD 使用者所組成的環境，請參閱 [AZURE Ad Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="37b0e-112">To protect an environment made up of only Azure AD users, see [Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

## <a name="understand-the-architecture"></a><span data-ttu-id="37b0e-113">了解架構</span><span class="sxs-lookup"><span data-stu-id="37b0e-113">Understand the architecture</span></span>

<span data-ttu-id="37b0e-114">下圖說明用於身分識別的 Defender 的基準架構。</span><span class="sxs-lookup"><span data-stu-id="37b0e-114">The following diagram illustrates the baseline architecture for Defender for Identity.</span></span> 

![Microsoft Defender 身分識別的架構](../../media/defender/m365-defender-identity-architecture.png)

<span data-ttu-id="37b0e-116">在此圖中：</span><span class="sxs-lookup"><span data-stu-id="37b0e-116">In this illustration:</span></span>
- <span data-ttu-id="37b0e-117">安裝在 AD 網域控制站上的感應器會剖析記錄和網路流量，並將其傳送至 Microsoft Defender 以供分析和報告識別。</span><span class="sxs-lookup"><span data-stu-id="37b0e-117">Sensors installed on AD domain controllers parse logs and network traffic and send them to Microsoft Defender for Identity for analysis and reporting.</span></span>
-  <span data-ttu-id="37b0e-118">當 Azure AD 設定為使用同盟驗證時，感應器也可以分析 Active Directory Federation Services (AD FS)  (圖例) 中的虛線點線。</span><span class="sxs-lookup"><span data-stu-id="37b0e-118">Sensors can also parse Active Directory Federation Services (AD FS) when Azure AD is configured to use federated authentication (dotted line in illustration).</span></span> 
- <span data-ttu-id="37b0e-119">Microsoft Defender 身分識別共用的信號，可 Microsoft 365 Defender (XDR) 的延伸偵測和回應。</span><span class="sxs-lookup"><span data-stu-id="37b0e-119">Microsoft Defender for Identity shares signals to Microsoft 365 Defender for extended detection and response (XDR).</span></span>


<span data-ttu-id="37b0e-120">您可以在下列伺服器上直接安裝身分識別感應器的 Defender：</span><span class="sxs-lookup"><span data-stu-id="37b0e-120">Defender for Identity sensors can be directly installed on the following servers:</span></span>

- <span data-ttu-id="37b0e-121">網域控制站：感應器會直接監視網域控制站流量，而不需要專用的伺服器或埠鏡像的設定。</span><span class="sxs-lookup"><span data-stu-id="37b0e-121">Domain controllers: The sensor directly monitors domain controller traffic, without the need for a dedicated server, or configuration of port mirroring.</span></span>
- <span data-ttu-id="37b0e-122">AD FS：感應器會直接監視網路流量和驗證事件。</span><span class="sxs-lookup"><span data-stu-id="37b0e-122">AD FS: The sensor directly monitors network traffic and authentication events.</span></span>

<span data-ttu-id="37b0e-123">若要深入瞭解身分識別的身分架構，包括與雲端 App 安全性整合，請參閱[Microsoft Defender for identity 架構](/defender-for-identity/architecture)。</span><span class="sxs-lookup"><span data-stu-id="37b0e-123">For a deeper look into the architecture of Defender for Identity, including integration with Cloud App Security, see [Microsoft Defender for Identity architecture](/defender-for-identity/architecture).</span></span>


## <a name="understand-key-concepts"></a><span data-ttu-id="37b0e-124">瞭解重要概念</span><span class="sxs-lookup"><span data-stu-id="37b0e-124">Understand key concepts</span></span>

<span data-ttu-id="37b0e-125">下清單格識別重要概念，在評估、設定及部署 Microsoft Defender 身分識別時，請務必瞭解。</span><span class="sxs-lookup"><span data-stu-id="37b0e-125">The following table identified key concepts that are important to understand when evaluating, configuring, and deploying Microsoft Defender for Identity.</span></span>


|<span data-ttu-id="37b0e-126">概念</span><span class="sxs-lookup"><span data-stu-id="37b0e-126">Concept</span></span>  |<span data-ttu-id="37b0e-127">描述</span><span class="sxs-lookup"><span data-stu-id="37b0e-127">Description</span></span> |<span data-ttu-id="37b0e-128">其他資訊</span><span class="sxs-lookup"><span data-stu-id="37b0e-128">More information</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="37b0e-129">受監視活動</span><span class="sxs-lookup"><span data-stu-id="37b0e-129">Monitored activities</span></span> | <span data-ttu-id="37b0e-130">用於身分識別的 Defender 監控組織內部產生的信號，可偵測可疑或惡意的活動，並協助您判斷每個潛在威脅的有效性，以有效進行會審和回應。</span><span class="sxs-lookup"><span data-stu-id="37b0e-130">Defender for Identity monitors signals generated from within your organization to detect suspicious or malicious activity and helps you determine the validity of each potential threat so that you can effectively triage and respond.</span></span>  |  [<span data-ttu-id="37b0e-131">適用于身分識別監控活動的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="37b0e-131">Microsoft Defender for Identity monitored activities</span></span>](/defender-for-identity/monitored-activities)       |
| <span data-ttu-id="37b0e-132">安全性警示</span><span class="sxs-lookup"><span data-stu-id="37b0e-132">Security alerts</span></span>    | <span data-ttu-id="37b0e-133">用於身分識別安全性警示的 Defender 會說明網路上的感應器所偵測到的可疑活動，以及每個威脅中所涉及的演員和電腦。</span><span class="sxs-lookup"><span data-stu-id="37b0e-133">Defender for Identity security alerts explain the suspicious activities detected by sensors on your network along with the actors and computers involved in each threat.</span></span>   | [<span data-ttu-id="37b0e-134">Microsoft Defender 身分識別安全性警示</span><span class="sxs-lookup"><span data-stu-id="37b0e-134">Microsoft Defender for Identity Security Alerts</span></span>](/defender-for-identity/suspicious-activity-guide?tabs=external)    |
| <span data-ttu-id="37b0e-135">實體設定檔</span><span class="sxs-lookup"><span data-stu-id="37b0e-135">Entity profiles</span></span>    | <span data-ttu-id="37b0e-136">實體設定檔提供使用者、電腦、裝置及資源及其存取歷程記錄的全面深入調查。</span><span class="sxs-lookup"><span data-stu-id="37b0e-136">Entity profiles provide a comprehensive deep-dive investigation of users, computers, devices, and resources along with their access history.</span></span>   | [<span data-ttu-id="37b0e-137">瞭解實體設定檔</span><span class="sxs-lookup"><span data-stu-id="37b0e-137">Understanding entity profiles</span></span>](/defender-for-identity/entity-profiles)  |
| <span data-ttu-id="37b0e-138">側向移動路徑</span><span class="sxs-lookup"><span data-stu-id="37b0e-138">Lateral movement paths</span></span>    | <span data-ttu-id="37b0e-139">MDI 安全性深入瞭解的一個重要元件，是找出一種橫向移動路徑，攻擊者使用非機密帳戶來存取整個網路中的機密帳戶或電腦。</span><span class="sxs-lookup"><span data-stu-id="37b0e-139">A key component of MDI security insights is identifying lateral movement paths in which an attacker uses non-sensitive accounts to gain access to sensitive accounts or machines throughout your network.</span></span>  | [<span data-ttu-id="37b0e-140">Microsoft Defender for Identity 橫向移動路徑 (LMPs) </span><span class="sxs-lookup"><span data-stu-id="37b0e-140">Microsoft Defender for Identity Lateral Movement Paths (LMPs)</span></span>](/defender-for-identity/use-case-lateral-movement-path)  |
| <span data-ttu-id="37b0e-141">網路名稱解析</span><span class="sxs-lookup"><span data-stu-id="37b0e-141">Network Name Resolution</span></span>    |  <span data-ttu-id="37b0e-142">網路名稱解析 (NNR) 是 MDI 功能的元件，它會根據網路流量、Windows 事件、ETW 等來捕獲活動，並將此原始資料關聯到每個活動中的相關電腦。</span><span class="sxs-lookup"><span data-stu-id="37b0e-142">Network Name Resolution (NNR) is a component of MDI functionality which captures activities based on network traffic, Windows events, ETW, etc. and correlates this raw data to the relevant computers involved in each activity.</span></span>       | [<span data-ttu-id="37b0e-143">何謂網路名稱解析？</span><span class="sxs-lookup"><span data-stu-id="37b0e-143">What is Network Name Resolution?</span></span>](/defender-for-identity/nnr-policy)      |
| <span data-ttu-id="37b0e-144">報告</span><span class="sxs-lookup"><span data-stu-id="37b0e-144">Reports</span></span>    | <span data-ttu-id="37b0e-145">用於身分識別報告的 Defender 可讓您排程或立即產生及下載提供系統和實體狀態資訊的報告。</span><span class="sxs-lookup"><span data-stu-id="37b0e-145">Defender for Identity reports allow you to schedule or immediately generate and download reports that provide system and entity status information.</span></span>  <span data-ttu-id="37b0e-146">您可以建立您環境中偵測到的系統健康情況、安全性警示及可能的側面移動路徑報告。</span><span class="sxs-lookup"><span data-stu-id="37b0e-146">You can create reports about system health, security alerts, and potential lateral movement paths detected in your environment.</span></span>   | [<span data-ttu-id="37b0e-147">Microsoft Defender 身分識別報告 </span><span class="sxs-lookup"><span data-stu-id="37b0e-147">Microsoft Defender for Identity Reports </span></span>](/defender-for-identity/reports)       |
| <span data-ttu-id="37b0e-148">角色群組</span><span class="sxs-lookup"><span data-stu-id="37b0e-148">Role groups</span></span>    | <span data-ttu-id="37b0e-149">當您組織的特定安全性和合規性需求（包括系統管理員、使用者和查看者）時，身分識別提供角色型群組和委派存取權，以保護資料。</span><span class="sxs-lookup"><span data-stu-id="37b0e-149">Defender for Identity offers role-based groups and delegated access to safeguard data according to your organization's specific security and compliance needs which includes Administrators, Users and Viewers.</span></span>        |  [<span data-ttu-id="37b0e-150">適用於身分識別的 Microsoft Defender 角色群組</span><span class="sxs-lookup"><span data-stu-id="37b0e-150">Microsoft Defender for Identity role groups</span></span>](/defender-for-identity/role-groups)       |
| <span data-ttu-id="37b0e-151">管理入口網站</span><span class="sxs-lookup"><span data-stu-id="37b0e-151">Administrative portal</span></span>    |  <span data-ttu-id="37b0e-152">除了 Microsoft 365 的安全性中心之外，身分識別入口網站的 Defender 也可以用來監視和回應可疑的活動。</span><span class="sxs-lookup"><span data-stu-id="37b0e-152">In addition to the Microsoft 365 Security Center, the Defender for Identity portal cab be used to monitor and respond to suspicious activity.</span></span>      | [<span data-ttu-id="37b0e-153">使用 Microsoft Defender for Identity 入口網站</span><span class="sxs-lookup"><span data-stu-id="37b0e-153">Working with the Microsoft Defender for Identity portal</span></span>](/defender-for-identity/workspace-portal)        |
| <span data-ttu-id="37b0e-154">Microsoft Cloud App Security 整合</span><span class="sxs-lookup"><span data-stu-id="37b0e-154">Microsoft Cloud App Security integration</span></span>   | <span data-ttu-id="37b0e-155">Microsoft Cloud App Security 會與 Microsoft Defender for Identity 整合，以在混合式環境中提供使用者實體行為分析 (UEBA) -Cloud App 和內部部署</span><span class="sxs-lookup"><span data-stu-id="37b0e-155">Microsoft Cloud App Security integrates with Microsoft Defender for Identity to provide user entity behavioral analytics (UEBA) across a hybrid environment - both cloud app and on-premises</span></span>   | <span data-ttu-id="37b0e-156">Microsoft Defender 用於身分識別整合</span><span class="sxs-lookup"><span data-stu-id="37b0e-156">Microsoft Defender for Identity integration</span></span>  |
| | | |


## <a name="review-prerequisites"></a><span data-ttu-id="37b0e-157">審查必要條件</span><span class="sxs-lookup"><span data-stu-id="37b0e-157">Review prerequisites</span></span>

<span data-ttu-id="37b0e-158">身分識別需要一些必要的工作，以確保您的內部部署身分識別和網路元件符合基本需求。</span><span class="sxs-lookup"><span data-stu-id="37b0e-158">Defender for Identity requires some prerequisite work to ensure that your on-premises identity and networking components meet minimum requirements.</span></span> <span data-ttu-id="37b0e-159">請使用本文做為檢查，以確保您的環境做好準備： [Microsoft Defender 的身分識別必要條件](/defender-for-identity/prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="37b0e-159">Use this article as a checklist to ensure your environment is ready: [Microsoft Defender for Identity prerequisites](/defender-for-identity/prerequisites).</span></span>


## <a name="next-steps"></a><span data-ttu-id="37b0e-160">後續步驟</span><span class="sxs-lookup"><span data-stu-id="37b0e-160">Next steps</span></span>

<span data-ttu-id="37b0e-161">步驟2之3： [啟用評估環境 Defender 身分識別](eval-defender-identity-enable-eval.md)</span><span class="sxs-lookup"><span data-stu-id="37b0e-161">Step 2 of 3: [Enable the evaluation environment Defender for Identity](eval-defender-identity-enable-eval.md)</span></span>

<span data-ttu-id="37b0e-162">回到概述以 [評估 Microsoft Defender 身分識別](eval-defender-identity-overview.md)</span><span class="sxs-lookup"><span data-stu-id="37b0e-162">Return to the overview for [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)</span></span>

<span data-ttu-id="37b0e-163">回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述</span><span class="sxs-lookup"><span data-stu-id="37b0e-163">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span> 