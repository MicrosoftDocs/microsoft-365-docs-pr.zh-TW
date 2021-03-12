---
title: Microsoft 365 安全性中心概觀
description: Microsoft 365 security center 中的優點，結合 Microsoft Defender for Office 365 (MDO) 和 Microsoft Defender for Endpoint (MDE) ，使用 Microsoft Defender for Identity (MDI) 和 Microsoft Cloud App Security (MCAS) 。 本文概述適用于系統管理員的 Microsoft 365 安全性中心提升。
keywords: 安全性，惡意程式碼，Microsoft 365，M365，security center，monitor，report，identity，data，裝置，應用程式
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 02/02/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 7db9b9762830384370a4bedf220d7a52112ab1ea
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727208"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a><span data-ttu-id="35cb5-105">整合的 Microsoft 365 安全性中心概述</span><span class="sxs-lookup"><span data-stu-id="35cb5-105">The unified Microsoft 365 security center overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="35cb5-106">適用於：</span><span class="sxs-lookup"><span data-stu-id="35cb5-106">**Applies to:**</span></span>

- [<span data-ttu-id="35cb5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35cb5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="35cb5-108">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="35cb5-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="35cb5-109">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="35cb5-109">Microsoft Defender for Office 365</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)

> <span data-ttu-id="35cb5-110">想要體驗 Microsoft 365 Defender？</span><span class="sxs-lookup"><span data-stu-id="35cb5-110">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="35cb5-111">您可以 [在實驗室環境中進行評估](https://aka.ms/mtp-trial-lab) ，或 [在實際執行中執行您的試驗專案](https://aka.ms/m365d-pilotplaybook)。</span><span class="sxs-lookup"><span data-stu-id="35cb5-111">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>

<span data-ttu-id="35cb5-112">改良的 **Microsoft 365 security center** ([https://security.microsoft.com](https://security.microsoft.com)) 會將保護、偵測、調查和回應，加入中央入口網站中的 *電子郵件*、共同作業、身分 *識別* 及 *裝置* 威脅。</span><span class="sxs-lookup"><span data-stu-id="35cb5-112">The improved **Microsoft 365 security center** ([https://security.microsoft.com](https://security.microsoft.com)) combines protection, detection, investigation, and response to *email*, *collaboration*, *identity*, and *device* threats, in a central portal.</span></span>

<span data-ttu-id="35cb5-113">Microsoft 365 的安全性中心會將現有 Microsoft 安全性入口網站的功能，例如 Microsoft Defender 安全性中心和 Office 365 安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="35cb5-113">Microsoft 365 security center brings together functionality from existing Microsoft security portals, like Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span> <span data-ttu-id="35cb5-114">[安全性中心] 強調快速存取訊號、簡化版面配置，以及將相關資訊放在一起，以方便使用。</span><span class="sxs-lookup"><span data-stu-id="35cb5-114">The security center emphasizes quick access to information, simpler layouts, and bringing related information together for easier use.</span></span> <span data-ttu-id="35cb5-115">此中心包括：</span><span class="sxs-lookup"><span data-stu-id="35cb5-115">This center includes:</span></span>

- <span data-ttu-id="35cb5-116">**[Microsoft Defender For Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender for Office 365 可協助組織使用一組預防、偵測、調查和搜尋功能保護其企業，以保護電子郵件和 Office 365 資源。</span><span class="sxs-lookup"><span data-stu-id="35cb5-116">**[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Microsoft Defender for Office 365 helps organizations secure their enterprise with a set of prevention, detection, investigation and hunting features to protect email, and Office 365 resources.</span></span>
- <span data-ttu-id="35cb5-117">**[Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** 會為組織中的裝置提供預防性保護、入侵後偵測、自動調查和回應。</span><span class="sxs-lookup"><span data-stu-id="35cb5-117">**[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** delivers preventative protection, post-breach detection, automated investigation, and response for devices in your organization.</span></span>
- <span data-ttu-id="35cb5-118">**[Microsoft 365 Defender](microsoft-threat-protection.md)** 是 Microsoft 的 *延伸偵測和回應* (XDR) 解決方案的一部分，利用 microsoft 365 安全性產品群組自動分析跨網域的威脅資料，並在單一儀表板上建立攻擊的圖片。</span><span class="sxs-lookup"><span data-stu-id="35cb5-118">**[Microsoft 365 Defender](microsoft-threat-protection.md)** is part of Microsoft’s *Extended Detection and Response* (XDR) solution that leverages the Microsoft 365 security portfolio to automatically analyze threat data across domains, and build a picture of an attack on a single dashboard.</span></span>

<span data-ttu-id="35cb5-119">如果您需要從 Office 365 Security & 合規性中心或 Microsoft Defender 安全中心變更之專案的相關資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="35cb5-119">If you need information about what's changed from the Office 365 Security & Compliance center or the Microsoft Defender Security Center, see:</span></span>

- [<span data-ttu-id="35cb5-120">Microsoft 365 安全性中心中的適用於 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="35cb5-120">Defender for Office 365 in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="35cb5-121">Microsoft 365 安全性中心中的適用於端點的 Defender</span><span class="sxs-lookup"><span data-stu-id="35cb5-121">Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a><span data-ttu-id="35cb5-122">預期的專案</span><span class="sxs-lookup"><span data-stu-id="35cb5-122">What to expect</span></span>

<span data-ttu-id="35cb5-123">您可以在 Office 365 安全性與合規性中心中使用的所有安全性內容 (protection.office.com) 和 Microsoft Defender security center (securitycenter.microsoft.com) 現在可以在 *microsoft 365 的安全性中心* 內找到。</span><span class="sxs-lookup"><span data-stu-id="35cb5-123">All the security content that you use in the Office 365 Security and Compliance Center (protection.office.com) and the Microsoft Defender security center (securitycenter.microsoft.com) can now be found in the *Microsoft 365 security center*.</span></span>

<span data-ttu-id="35cb5-124">Microsoft 365 的安全性中心可協助安全小組調查從不同工作負載的信號到單一整合體驗，以調查和回應攻擊 brining：</span><span class="sxs-lookup"><span data-stu-id="35cb5-124">Microsoft 365 security center helps security teams investigate and respond to attacks by brining in signals from different workloads into a single, unified experiences:</span></span>

- <span data-ttu-id="35cb5-125">事件 & 警示</span><span class="sxs-lookup"><span data-stu-id="35cb5-125">Incidents & alerts</span></span>
- <span data-ttu-id="35cb5-126">狩獵</span><span class="sxs-lookup"><span data-stu-id="35cb5-126">Hunting</span></span>
- <span data-ttu-id="35cb5-127">重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="35cb5-127">Action Center</span></span>
- <span data-ttu-id="35cb5-128">威脅分析</span><span class="sxs-lookup"><span data-stu-id="35cb5-128">Threat analytics</span></span>

<span data-ttu-id="35cb5-129">Microsoft 365 的安全性中心強調 *unity、清晰度及共同目標* ，因為它會合並 microsoft Defender for Office 365 和 microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="35cb5-129">The Microsoft 365 security center emphasizes *unity, clarity, and common goals* as it merges Microsoft Defender for Office 365 and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="35cb5-130">合併是以下列所列的優先順序為基礎，而不犧牲每個安全性套件加入組合的功能：</span><span class="sxs-lookup"><span data-stu-id="35cb5-130">The merge was based on the priorities listed below, and made without sacrificing the capabilities that each security suite brought to the combination:</span></span>

- <span data-ttu-id="35cb5-131">萬用群組建區塊</span><span class="sxs-lookup"><span data-stu-id="35cb5-131">common building blocks</span></span>
- <span data-ttu-id="35cb5-132">常見術語</span><span class="sxs-lookup"><span data-stu-id="35cb5-132">common terminology</span></span>
- <span data-ttu-id="35cb5-133">一般實體</span><span class="sxs-lookup"><span data-stu-id="35cb5-133">common entities</span></span>
- <span data-ttu-id="35cb5-134">與其他工作負載的功能同位</span><span class="sxs-lookup"><span data-stu-id="35cb5-134">feature parity with other workloads</span></span>

## <a name="unified-investigations"></a><span data-ttu-id="35cb5-135">整合調查</span><span class="sxs-lookup"><span data-stu-id="35cb5-135">Unified investigations</span></span>

<span data-ttu-id="35cb5-136">簡化安全性中心會建立單一窗格，以調查整個 Microsoft 365 組織中的任何事件。</span><span class="sxs-lookup"><span data-stu-id="35cb5-136">Streamlining security centers creates a single pane for investigating any incidents across a Microsoft 365 organization.</span></span> <span data-ttu-id="35cb5-137">主要範例是 Microsoft 365 安全性中心的快速啟動上的 [ **事件** ] 節點。</span><span class="sxs-lookup"><span data-stu-id="35cb5-137">A primary example is the **Incidents** node on the quick launch of the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="MDO 中的 [事件] 頁面。":::

<span data-ttu-id="35cb5-139">例如，按兩下具有 **高** 嚴重性的事件名稱，會帶您前往示範彙聚中心優勢的頁面。</span><span class="sxs-lookup"><span data-stu-id="35cb5-139">As an example, double-clicking on an incident name with **High** severity brings you to a page that demonstrates the advantage of converging centers.</span></span>

![針對多個端點的許可權提升的多階段事件，顯示查看16個受影響裝置和9個受影響的使用者。](../../media/converged-incident-info-3.png)

> [!TIP]
> <span data-ttu-id="35cb5-141">[收斂 **使用者** ] 索引標籤是開始查詢的好地方。</span><span class="sxs-lookup"><span data-stu-id="35cb5-141">The converged **Users** tab is a good place to begin your inquiries.</span></span> <span data-ttu-id="35cb5-142">這個單一頁面) 會從聚合工作負載 (Microsoft Defender for Endpoint，Microsoft Defender for Identity，以及 MCAS 的使用者呈現資訊，例如內部部署 Active Directory、Azure Active directory、同步處理、本機和協力廠商使用者等來源。</span><span class="sxs-lookup"><span data-stu-id="35cb5-142">This single page surfaces information for users from converged workloads (Microsoft Defender for Endpoint, Microsoft Defender for Identity, and MCAS, if you leverage it) and a range of sources such as on-premises Active Directory, Azure Active Directory, synced, local, and third-party users.</span></span> <span data-ttu-id="35cb5-143">深入瞭解 [新的使用者經驗](investigate-users.md)。</span><span class="sxs-lookup"><span data-stu-id="35cb5-143">Learn more about [the new Users experience](investigate-users.md).</span></span>

<span data-ttu-id="35cb5-144">事件資訊顯示使用者/身分識別資訊，以及存在風險的信箱旁的使用者/身分識別。</span><span class="sxs-lookup"><span data-stu-id="35cb5-144">Incident information shows user/identity specifics and at-risk devices, beside affected mailboxes.</span></span> <span data-ttu-id="35cb5-145">它也會與任何 **調查資訊** 及收集的 **證據** 相關。</span><span class="sxs-lookup"><span data-stu-id="35cb5-145">It also relates any **Investigation information** and gathered **Evidence**.</span></span> <span data-ttu-id="35cb5-146">這可讓系統管理員和安全性運作小組更輕鬆地從一個高風險的警示到受影響的使用者和信箱。</span><span class="sxs-lookup"><span data-stu-id="35cb5-146">This makes it easier for admins and security operation teams to pivot from one high-risk alert to the affected users and mailboxes.</span></span> <span data-ttu-id="35cb5-147">查看此頁面頂端的 [ **事件** ] 索引標籤，可從這個單一位置取得其他重要的安全性轉動。</span><span class="sxs-lookup"><span data-stu-id="35cb5-147">Looking at the **Incident** tabs at the top of this page, there are other key security pivots available from this single location.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35cb5-148">在特定事件的任何頁面上方，您都會看到 **摘要**、 **警示**、 **裝置**、 **使用者**、 **信箱**、 **調查** 和 **證據** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="35cb5-148">Along the top of any page for a specific Incident, you'll see the **Summary**, **Alerts**, **Devices**, **Users**, **Mailboxes**, **Investigations**, and **Evidence** tabs.</span></span>

<span data-ttu-id="35cb5-149">選取「 **調查** 」會開啟一個頁面，其中會提供分析所用的圖形，並列出狀態 (例如 **待決核准**) 以進行修正）。</span><span class="sxs-lookup"><span data-stu-id="35cb5-149">Selecting **Investigations** opens  a page that features a graphic of the analysis taking place and lists a status (such as **pending approval**) for remediation.</span></span> <span data-ttu-id="35cb5-150">花時間在您的環境中選取特定的事件，深入查看這些索引標籤，並練習建立不同類型威脅的設定檔。</span><span class="sxs-lookup"><span data-stu-id="35cb5-150">Take time to select specific incidents in your environment, drill down into these tabs, and practice building a profile for different kinds of threats.</span></span> <span data-ttu-id="35cb5-151">熟悉將會受益于以後的任何調查。</span><span class="sxs-lookup"><span data-stu-id="35cb5-151">Familiarity will benefit any later pressing investigations.</span></span>

## <a name="improved-processes"></a><span data-ttu-id="35cb5-152">改進的處理常式</span><span class="sxs-lookup"><span data-stu-id="35cb5-152">Improved processes</span></span>

<span data-ttu-id="35cb5-153">常見的控制項和內容會出現在相同的位置，或是壓縮成一個資料摘要，使其更容易尋找。</span><span class="sxs-lookup"><span data-stu-id="35cb5-153">Common controls and content either appear in the same place, or are condensed into one feed of data making it easier to find.</span></span> <span data-ttu-id="35cb5-154">例如，統一設定。</span><span class="sxs-lookup"><span data-stu-id="35cb5-154">For example, unified settings.</span></span>

### <a name="unified-settings"></a><span data-ttu-id="35cb5-155">統一設定</span><span class="sxs-lookup"><span data-stu-id="35cb5-155">Unified settings</span></span>

![已按一下「Role」，並開啟 [設定] 頁面，其中包含一般設定、許可權、APIs 及規則。](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a><span data-ttu-id="35cb5-159">許可權 & 角色</span><span class="sxs-lookup"><span data-stu-id="35cb5-159">Permissions & roles</span></span>

![& 角色] 頁面顯示端點角色的許可權 & 群組、角色和裝置群組。](../../media/converged-roles-5.png)

 <span data-ttu-id="35cb5-161">存取 Microsoft 365 的安全性中心是透過 Azure Active Directory 全域角色或使用自訂角色進行設定。</span><span class="sxs-lookup"><span data-stu-id="35cb5-161">Access the Microsoft 365 security center is configured with Azure Active Directory global roles or by using custom roles.</span></span> <span data-ttu-id="35cb5-162">若為 Defender for Endpoint，請參閱 [將使用者存取指派給 Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access)。</span><span class="sxs-lookup"><span data-stu-id="35cb5-162">For Defender for Endpoint, see [Assign user access to Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access).</span></span> <span data-ttu-id="35cb5-163">若為 Office 365 的 Defender，請參閱 [microsoft 365 規範中心和 microsoft 365 security center 中的許可權](../office-365-security/permissions-microsoft-365-compliance-security.md)。</span><span class="sxs-lookup"><span data-stu-id="35cb5-163">For Defender for Office 365, see [Permissions in the Microsoft 365 compliance center and Microsoft 365 security center](../office-365-security/permissions-microsoft-365-compliance-security.md).</span></span>

- <span data-ttu-id="35cb5-164">深入瞭解如何 [管理 Microsoft 365 Defender 的存取](mtp-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="35cb5-164">Learn more about how to [manage access to Microsoft 365 Defender](mtp-permissions.md)</span></span>
- <span data-ttu-id="35cb5-165">深入瞭解如何在 Microsoft 365 的安全性中心[建立自訂角色](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="35cb5-165">Learn more about how to [create custom roles](custom-roles.md) in Microsoft 365 security center</span></span>

> [!NOTE]
> <span data-ttu-id="35cb5-166">Microsoft 365 security center 中的 microsoft Defender for Endpoint 可將存取權授與 [受管理的安全性服務提供者。 (MSSPs) ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) 在 [microsoft Defender security center 中授](https://docs.microsoft.com/microsoft-365/security/mtp/mssp-access)與存取權的方式相同。</span><span class="sxs-lookup"><span data-stu-id="35cb5-166">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](https://docs.microsoft.com/microsoft-365/security/mtp/mssp-access).</span></span>

### <a name="integrated-reports"></a><span data-ttu-id="35cb5-167">整合報告</span><span class="sxs-lookup"><span data-stu-id="35cb5-167">Integrated reports</span></span>

<span data-ttu-id="35cb5-168">報表也是 Microsoft 365 安全中心的整合。</span><span class="sxs-lookup"><span data-stu-id="35cb5-168">Reports are also unified in the Microsoft 365 security center.</span></span> <span data-ttu-id="35cb5-169">系統管理員可以從一般的安全性報告開始，並在特定報告中分支至相關的端點、電子郵件 & 協同作業。</span><span class="sxs-lookup"><span data-stu-id="35cb5-169">Admins can start with a general security report, and branch into specific reports about endpoints, email & collaboration.</span></span> <span data-ttu-id="35cb5-170">此處的連結是根據工作負載設定動態產生。</span><span class="sxs-lookup"><span data-stu-id="35cb5-170">The links here are dynamically generated based upon workload configuration.</span></span>

### <a name="quickly-view-your-microsoft-365-environment"></a><span data-ttu-id="35cb5-171">快速查看您的 Microsoft 365 環境</span><span class="sxs-lookup"><span data-stu-id="35cb5-171">Quickly view your Microsoft 365 environment</span></span>

<span data-ttu-id="35cb5-172">**首頁** 會顯示許多安全小組需要的常見智慧卡。</span><span class="sxs-lookup"><span data-stu-id="35cb5-172">The **Home** page shows many of the common cards that security teams need.</span></span> <span data-ttu-id="35cb5-173">名片和資料的組成取決於使用者角色。</span><span class="sxs-lookup"><span data-stu-id="35cb5-173">The composition of cards and data is dependent on the user role.</span></span> <span data-ttu-id="35cb5-174">因為 Microsoft 365 的安全性中心使用角色型存取控制，所以不同的角色會在日常工作中看到更有意義的卡片。</span><span class="sxs-lookup"><span data-stu-id="35cb5-174">Because the Microsoft 365 security center uses role-based access control, different roles will see cards that are more meaningful to their day to day jobs.</span></span>  

<span data-ttu-id="35cb5-175">這種一覽的資訊可協助您維持組織中的最新活動。</span><span class="sxs-lookup"><span data-stu-id="35cb5-175">This at-a-glance information helps you keep up with the latest activities in your organization.</span></span> <span data-ttu-id="35cb5-176">Microsoft 365 的安全性中心將不同來源的信號彙集在一起，以呈現您的 Microsoft 365 環境的整體視圖。</span><span class="sxs-lookup"><span data-stu-id="35cb5-176">The Microsoft 365 security center brings together signals from different sources to present a holistic view of your Microsoft 365 environment.</span></span>

<span data-ttu-id="35cb5-177">這些卡片分為下列類別：</span><span class="sxs-lookup"><span data-stu-id="35cb5-177">The cards fall into these categories:</span></span>

- <span data-ttu-id="35cb5-178">身分 **識別-監視** 組織中的身分識別，並追蹤可疑或危險的行為。</span><span class="sxs-lookup"><span data-stu-id="35cb5-178">**Identities**- Monitor the identities in your organization and keep track of suspicious or risky behaviors.</span></span> <span data-ttu-id="35cb5-179">[深入瞭解身分識別保護](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)。</span><span class="sxs-lookup"><span data-stu-id="35cb5-179">[Learn more about identity protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>
- <span data-ttu-id="35cb5-180">**Data** -Help 追蹤可能會導致未經授權的資料洩漏的使用者活動。</span><span class="sxs-lookup"><span data-stu-id="35cb5-180">**Data** - Help track user activity that could lead to unauthorized data disclosure.</span></span>
- <span data-ttu-id="35cb5-181">**裝置** -在您的裝置上獲得最新資訊，提醒、違規活動及其他威脅。</span><span class="sxs-lookup"><span data-stu-id="35cb5-181">**Devices** - Get up-to-date information on alerts, breach activity, and other threats on your devices.</span></span>
- <span data-ttu-id="35cb5-182">**App** -深入瞭解您的組織中使用雲端應用程式的方式。</span><span class="sxs-lookup"><span data-stu-id="35cb5-182">**Apps** - Gain insight into how cloud apps are being used in your organization.</span></span> <span data-ttu-id="35cb5-183">[深入瞭解已探索 Cloud App Security 的應用程式](https://docs.microsoft.com/cloud-app-security/discovered-apps)。</span><span class="sxs-lookup"><span data-stu-id="35cb5-183">[Learn more about Cloud App Security discovered apps](https://docs.microsoft.com/cloud-app-security/discovered-apps).</span></span>

## <a name="threat-analytics-with-better-data-coverage"></a><span data-ttu-id="35cb5-184">更好的資料覆蓋率進行威脅分析</span><span class="sxs-lookup"><span data-stu-id="35cb5-184">Threat analytics with better data coverage</span></span>
<span data-ttu-id="35cb5-185">使用下列 Microsoft 365 Defender 威脅分析整合體驗，追蹤並回應新興威脅：</span><span class="sxs-lookup"><span data-stu-id="35cb5-185">Track and respond to emerging threats with the following Microsoft 365 Defender threat analytics integrated experience:</span></span>

- <span data-ttu-id="35cb5-186">在 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 之間提供更佳的資料覆蓋率，以盡可能進行綜合的事件管理、自動調查、修復，以及主動或被動威脅搜尋。</span><span class="sxs-lookup"><span data-stu-id="35cb5-186">Better data coverage between Microsoft Defender for Endpoint and Microsoft Defender for Office 365, making combined incident management, automatic investigation, remediation, and proactive or reactive threat hunting across-domain possible.</span></span> 
- <span data-ttu-id="35cb5-187">Microsoft Defender for Office 365 中的電子郵件相關偵測和緩解，除了 Microsoft Defender for Endpoint 中已提供的端點資料之外。</span><span class="sxs-lookup"><span data-stu-id="35cb5-187">Email-related detections and mitigations from Microsoft Defender for Office 365, in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="35cb5-188">威脅相關事件的觀點，可將提醒彙集至 Microsoft Defender for Endpoint 和 Microsoft Defender for Office 365 的端對端攻擊案例，以減少工作佇列，並簡化並加速您的調查。</span><span class="sxs-lookup"><span data-stu-id="35cb5-188">A view of threat-related incidents which aggregate alerts into end-to-end attack stories across Microsoft Defender for Endpoint and Microsoft Defender for Office 365 to reduce the work queue, as well as simplify and speed up your investigation.</span></span>
- <span data-ttu-id="35cb5-189">Microsoft 365 Defender 解決方案所偵測到和封鎖的攻擊嘗試。</span><span class="sxs-lookup"><span data-stu-id="35cb5-189">Attack attempts detected and blocked by Microsoft 365 Defender solutions.</span></span> <span data-ttu-id="35cb5-190">此外，您還可以使用可讓您用來驅動預防性動作的資料，緩解進一步披露及提高恢復的風險。</span><span class="sxs-lookup"><span data-stu-id="35cb5-190">There's also data that you can use to drive preventive actions that mitigate the risk of further exposure and increase resilience.</span></span> 
- <span data-ttu-id="35cb5-191">增強型設計可將可行動的資訊放在聚光燈中，協助您快速識別從報告中即時關注、調查和利用的資料。</span><span class="sxs-lookup"><span data-stu-id="35cb5-191">Enhanced design that puts actionable information in the spotlight to help you  quickly identify data to urgently focus on, investigate, and leverage from the reports.</span></span>

## <a name="a-centralized-learning-hub"></a><span data-ttu-id="35cb5-192">集中式學習中樞</span><span class="sxs-lookup"><span data-stu-id="35cb5-192">A centralized Learning Hub</span></span>

<span data-ttu-id="35cb5-193">Microsoft 365 的安全性中心包含一個教學中心，該中樞會從 Microsoft 安全性博客、YouTube 上的 Microsoft security 社區及官方檔，透過這些資源冒泡官方指導方針。</span><span class="sxs-lookup"><span data-stu-id="35cb5-193">The Microsoft 365 security center includes a learning hub that bubbles up official guidance from resources such as the Microsoft security blog, the Microsoft security community on YouTube, and the official documentation at docs.microsoft.com.</span></span>

<span data-ttu-id="35cb5-194">在學習中樞內，電子郵件 & 共同作業 (Microsoft Defender for Office 365 或 MDO) 指引是以端點 (Microsoft Defender for Endpoint 或 MDE) ，以及 Microsoft 365 Defender 教學資源的方式並排顯示。</span><span class="sxs-lookup"><span data-stu-id="35cb5-194">Inside the learning hub, Email & Collaboration (Microsoft Defender for Office 365 or MDO) guidance is side-by-side with Endpoint (Microsoft Defender for Endpoint or MDE), and Microsoft 365 Defender learning resources.</span></span>

<span data-ttu-id="35cb5-195">學習中心隨即開啟，其所組織的教學路徑，如「如何使用 Microsoft 365 Defender 進行調查？」主題。</span><span class="sxs-lookup"><span data-stu-id="35cb5-195">The learning hub opens with Learning paths organized around topics such as “How to Investigate Using Microsoft 365 Defender?”</span></span> <span data-ttu-id="35cb5-196">和「Microsoft Defender for Office 365 最佳作法」。</span><span class="sxs-lookup"><span data-stu-id="35cb5-196">and “Microsoft Defender for Office 365 Best Practices”.</span></span> <span data-ttu-id="35cb5-197">此區段目前是由 Microsoft 中的安全性產品群組策劃。</span><span class="sxs-lookup"><span data-stu-id="35cb5-197">This section is currently curated by the security Product Group inside Microsoft.</span></span> <span data-ttu-id="35cb5-198">每個學習路徑會反映所需的預測時間，以取得概念。</span><span class="sxs-lookup"><span data-stu-id="35cb5-198">Each Learning path reflects a projected time it takes to get through the concepts.</span></span> <span data-ttu-id="35cb5-199">例如，預計 Microsoft Defender for Office 365 使用者帳戶已受損時所採取的步驟，將需要8分鐘，而且可以即時學習。</span><span class="sxs-lookup"><span data-stu-id="35cb5-199">For example 'Steps to take when a Microsoft Defender for Office 365 user account is compromised' is projected to take 8 minutes, and is valuable learning on the fly.</span></span>

<span data-ttu-id="35cb5-200">按一下內容之後，將此網站做成書簽並將書簽組織至 ' Security ' 或 ' 嚴重」資料夾可能會很有用。</span><span class="sxs-lookup"><span data-stu-id="35cb5-200">After clicking through to the content, it may be useful to bookmark this site and organize bookmarks into a 'Security' or 'Critical' folder.</span></span> <span data-ttu-id="35cb5-201">若要查看所有學習路徑，請按一下主面板中的 [全部顯示] 連結。</span><span class="sxs-lookup"><span data-stu-id="35cb5-201">To see all Learning paths, click the Show all link in the main panel.</span></span>

> [!NOTE]
> <span data-ttu-id="35cb5-202">Microsoft 365 security center 教學中樞的最上層有一些有説明的 **篩選準則** ，可讓您在目前的 Microsoft 365 Defender、microsoft Defender for Endpoint 和 microsoft Defender for Office 365) 中，選擇 (的產品。</span><span class="sxs-lookup"><span data-stu-id="35cb5-202">There are helpful **filters** along the top of the Microsoft 365 security center learning hub that will let you choose between products (currently Microsoft 365 Defender, Microsoft Defender for Endpoint, and Microsoft Defender for Office 365).</span></span> <span data-ttu-id="35cb5-203">請注意，會列出每個區段的學習資源數目，可協助教學人員追蹤他們手頭的訓練和學習資源數目。</span><span class="sxs-lookup"><span data-stu-id="35cb5-203">Notice that the number of learning resources for each section is listed, which can help learners keep track of how many resources they have at hand for training and learning.</span></span>
>
> <span data-ttu-id="35cb5-204">除了產品篩選、目前主題、 (從影片到網路研討會的資源類型) 、熟悉或經驗的安全性區域、安全性角色及產品功能的層級。</span><span class="sxs-lookup"><span data-stu-id="35cb5-204">Along with the Product filter, current topics, types of resources (from videos to webinars), levels of familiarity or experience with security areas, security roles, and product features are listed.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="35cb5-205">將您的意見傳送給我們</span><span class="sxs-lookup"><span data-stu-id="35cb5-205">Send us your feedback</span></span>

<span data-ttu-id="35cb5-206">我們需要您的意見反應。</span><span class="sxs-lookup"><span data-stu-id="35cb5-206">We need your feedback.</span></span> <span data-ttu-id="35cb5-207">我們一定會尋求改進功能，因此，如果您想要看到任何內容，請 [傳送您的 Microsoft 365 Defender 意見](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)反應。</span><span class="sxs-lookup"><span data-stu-id="35cb5-207">We're always looking to improve, so if there's something you'd like to see, [send us your Microsoft 365 Defender feedback](https://www.microsoft.com/videoplayer/embed/RE4K5Ci).</span></span>

<span data-ttu-id="35cb5-208">您也可以留下本文的意見反應。</span><span class="sxs-lookup"><span data-stu-id="35cb5-208">You can also leave feedback from this article.</span></span> <span data-ttu-id="35cb5-209">在「提交並查看意見反應」下方的「意見反應」區段中，選項是 *此產品* 或 *此頁面*。</span><span class="sxs-lookup"><span data-stu-id="35cb5-209">In the 'Feedback' section at the end under 'Submit and view feedback for', the options are *This product*, or *This page*.</span></span>

<span data-ttu-id="35cb5-210">針對 *產品* 回饋使用 **此產品** 按鈕：</span><span class="sxs-lookup"><span data-stu-id="35cb5-210">Use the **This product** button for *product* feedback:</span></span>

1. <span data-ttu-id="35cb5-211">選取本文底部的 [ *本產品* ]。</span><span class="sxs-lookup"><span data-stu-id="35cb5-211">Select *This product* at the bottom of the article.</span></span>
    1. <span data-ttu-id="35cb5-212">如果您想要繼續閱讀這些指示，請在按鈕上按一下滑鼠右鍵，然後按一下 [在新索引標籤中開啟]。</span><span class="sxs-lookup"><span data-stu-id="35cb5-212">Right-click the button and 'Open in a new tab' if you want to keep reading these directions.</span></span>
2. <span data-ttu-id="35cb5-213">這會流覽至 **UserVoice 論壇**。</span><span class="sxs-lookup"><span data-stu-id="35cb5-213">This will navigate to the **UserVoice forum**.</span></span>
3. <span data-ttu-id="35cb5-214">您有2個選項：</span><span class="sxs-lookup"><span data-stu-id="35cb5-214">You have 2 options:</span></span>
    1. <span data-ttu-id="35cb5-215">向左下到文字方塊， *我們應如何改善相容性或保護您的使用者 Office 365 中的更好* ，並在 *Microsoft 365 的安全性中心* 貼上。</span><span class="sxs-lookup"><span data-stu-id="35cb5-215">Scroll down to the text box *How can we improve compliance or protect your users better in Office 365?* and paste in *Microsoft 365 security center*.</span></span> <span data-ttu-id="35cb5-216">您可以搜尋結果與您的觀點，並向上-投票，或使用按鈕 **發佈新的觀點**。</span><span class="sxs-lookup"><span data-stu-id="35cb5-216">You can search the results for an idea like yours and up-vote it, or use the button for **Post a new idea**.</span></span>
    1. <span data-ttu-id="35cb5-217">如果您認為已經報告此問題，而且想要使用投票 (或投票) 提升其設定檔，請使用 UserVoice 右側的 [ *提供意見* 反應] 方塊。</span><span class="sxs-lookup"><span data-stu-id="35cb5-217">If you feel certain this issue is already reported, and want to raise its profile with a vote (or votes), use the *Give Feedback* box on the right side of UserVoice.</span></span> <span data-ttu-id="35cb5-218">搜尋 *Microsoft 365 security center*， **找出問題，然後使用 [投票] 按鈕** 提升其狀態。</span><span class="sxs-lookup"><span data-stu-id="35cb5-218">Search for *Microsoft 365 security center*, **find the issue, and use the vote button** to raise its status.</span></span>

<span data-ttu-id="35cb5-219">使用 *此頁面* 以取得文章本身的回饋。</span><span class="sxs-lookup"><span data-stu-id="35cb5-219">Use *This page* for feedback on the article itself.</span></span> <span data-ttu-id="35cb5-220">感謝您的意見反應。</span><span class="sxs-lookup"><span data-stu-id="35cb5-220">Thanks for your feedback.</span></span> <span data-ttu-id="35cb5-221">您的語音可協助我們改進產品。</span><span class="sxs-lookup"><span data-stu-id="35cb5-221">Your voice helps us improve products.</span></span>

### <a name="explore-what-the-security-center-has-to-offer"></a><span data-ttu-id="35cb5-222">探索「安全性中心」所提供的功能</span><span class="sxs-lookup"><span data-stu-id="35cb5-222">Explore what the security center has to offer</span></span>

<span data-ttu-id="35cb5-223">繼續探索 Microsoft 365 security center 中的功能：</span><span class="sxs-lookup"><span data-stu-id="35cb5-223">Keep exploring the features and capabilities in the Microsoft 365 security center:</span></span>

- [<span data-ttu-id="35cb5-224">管理事件及警示</span><span class="sxs-lookup"><span data-stu-id="35cb5-224">Manage incidents and alerts</span></span>](manage-incidents.md)
- [<span data-ttu-id="35cb5-225">使用威脅分析追蹤並回應新興威脅</span><span class="sxs-lookup"><span data-stu-id="35cb5-225">Track and respond to emerging threats with threat analytics</span></span>](threat-analytics.md)
- [<span data-ttu-id="35cb5-226">重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="35cb5-226">The Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="35cb5-227">尋找跨裝置、電子郵件、應用程式和身分識別的威脅</span><span class="sxs-lookup"><span data-stu-id="35cb5-227">Hunt for threats across devices, emails, apps, and identities</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [<span data-ttu-id="35cb5-228">自訂偵測規則</span><span class="sxs-lookup"><span data-stu-id="35cb5-228">Custom detection rules</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [<span data-ttu-id="35cb5-229">電子郵件 & 共同作業警示</span><span class="sxs-lookup"><span data-stu-id="35cb5-229">Email & collaboration alerts</span></span>](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- <span data-ttu-id="35cb5-230">[建立網路釣魚攻擊模擬](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) ，並 [建立訓練您的小組的負載](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span><span class="sxs-lookup"><span data-stu-id="35cb5-230">[Create a phishing attack simulation](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) and [create a payload for training your teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)</span></span>
 
### <a name="related-information"></a><span data-ttu-id="35cb5-231">相關資訊</span><span class="sxs-lookup"><span data-stu-id="35cb5-231">Related information</span></span>
- [<span data-ttu-id="35cb5-232">Microsoft 365 安全性中心</span><span class="sxs-lookup"><span data-stu-id="35cb5-232">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="35cb5-233">Microsoft 365 security center 中的 microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="35cb5-233">Microsoft Defender for Office 365 in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mdo.md)
- [<span data-ttu-id="35cb5-234">Microsoft 365 security center 中的 microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="35cb5-234">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="35cb5-235">將帳戶從 Microsoft Defender for Endpoint 重新導向至 Microsoft 365 安全中心</span><span class="sxs-lookup"><span data-stu-id="35cb5-235">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)
