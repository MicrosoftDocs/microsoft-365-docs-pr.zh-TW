---
title: 組織中的漏洞-威脅和弱點管理
description: 列出常見的漏洞和披露 (CVE) 組織中執行的軟體弱點的識別碼。 由 Microsoft Defender ATP 威脅和弱點管理功能探索。
keywords: mdatp 威脅 & 漏洞管理、威脅和弱點管理、mdatp tvm 弱點頁面、透過 tvm 尋找弱點、tvm 弱點清單、tvm 中的弱點詳細資料
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b42e25c409ba19639e77e95fafc3d939514511ea
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060484"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a><span data-ttu-id="3dea4-105">組織中的漏洞-威脅和弱點管理</span><span class="sxs-lookup"><span data-stu-id="3dea4-105">Vulnerabilities in my organization - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3dea4-106">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="3dea4-106">**Applies to:**</span></span>
- [<span data-ttu-id="3dea4-107">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3dea4-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="3dea4-108">威脅與弱點管理</span><span class="sxs-lookup"><span data-stu-id="3dea4-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3dea4-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3dea4-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3dea4-110">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="3dea4-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3dea4-111">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="3dea4-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="3dea4-112">威脅和弱點管理會在 Defender 中使用相同的信號，以進行 Endpoint protection，以掃描及偵測到漏洞。</span><span class="sxs-lookup"><span data-stu-id="3dea4-112">Threat and vulnerability management uses the same signals in Defender for Endpoint's endpoint protection to scan and detect vulnerabilities.</span></span>

<span data-ttu-id="3dea4-113">**弱點** 頁面會列出常見的漏洞和披露 (CVE) ID，列出您的裝置所公開的軟體弱點。</span><span class="sxs-lookup"><span data-stu-id="3dea4-113">The **Weaknesses** page lists the software vulnerabilities your devices are exposed to by listing the Common Vulnerabilities and Exposures (CVE) ID.</span></span> <span data-ttu-id="3dea4-114">您也可以查看嚴重性、常見弱點計分系統 (CVSS) 分級、組織中的流行情況、相對應的破壞程度、威脅深入瞭解等等。</span><span class="sxs-lookup"><span data-stu-id="3dea4-114">You can also view the severity, Common Vulnerability Scoring System (CVSS) rating, prevalence in your organization, corresponding breach, threat insights, and more.</span></span>

>[!NOTE]
><span data-ttu-id="3dea4-115">如果沒有任何官方的 CVE 識別碼指派給一個弱點，該弱點名稱是由威脅和弱點管理所指派。</span><span class="sxs-lookup"><span data-stu-id="3dea4-115">If there is no official CVE-ID assigned to a vulnerability, the vulnerability name is assigned by threat and vulnerability management.</span></span>

>[!TIP]
><span data-ttu-id="3dea4-116">若要取得有關新弱點事件的電子郵件，請參閱 [在 Microsoft Defender For Endpoint 中設定弱點電子郵件通知](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="3dea4-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-weaknesses-page"></a><span data-ttu-id="3dea4-117">流覽至弱點頁面</span><span class="sxs-lookup"><span data-stu-id="3dea4-117">Navigate to the Weaknesses page</span></span>

<span data-ttu-id="3dea4-118">以幾種不同的方式存取弱點頁面：</span><span class="sxs-lookup"><span data-stu-id="3dea4-118">Access the Weaknesses page a few different ways:</span></span>

- <span data-ttu-id="3dea4-119">從 [Microsoft Defender Security Center](portal-overview.md)中的威脅和弱點管理導覽功能表中，選取 **弱點**</span><span class="sxs-lookup"><span data-stu-id="3dea4-119">Selecting **Weaknesses** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="3dea4-120">全域搜尋</span><span class="sxs-lookup"><span data-stu-id="3dea4-120">Global search</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="3dea4-121">流覽功能表</span><span class="sxs-lookup"><span data-stu-id="3dea4-121">Navigation menu</span></span>

<span data-ttu-id="3dea4-122">移至 [威脅與弱點管理] 導覽功能表並選取 [ **弱點** ]，以開啟 cve 清單。</span><span class="sxs-lookup"><span data-stu-id="3dea4-122">Go to the threat and vulnerability management navigation menu and select **Weaknesses** to open the list of CVEs.</span></span>

### <a name="vulnerabilities-in-global-search"></a><span data-ttu-id="3dea4-123">全域搜尋中的漏洞</span><span class="sxs-lookup"><span data-stu-id="3dea4-123">Vulnerabilities in global search</span></span>

1. <span data-ttu-id="3dea4-124">移至 [通用搜尋] 下拉式功能表。</span><span class="sxs-lookup"><span data-stu-id="3dea4-124">Go to the global search drop-down menu.</span></span>
2. <span data-ttu-id="3dea4-125">選取 [ **弱點** ] 和 [重要漏洞]，並 (您要尋找的 CVE) 識別碼]，然後選取 [搜尋] 圖示。</span><span class="sxs-lookup"><span data-stu-id="3dea4-125">Select **Vulnerability** and key-in the Common Vulnerabilities and Exposures (CVE) ID that you're looking for, then select the search icon.</span></span> <span data-ttu-id="3dea4-126">**弱點** 頁面隨即開啟，並顯示您要尋找的 CVE 資訊。</span><span class="sxs-lookup"><span data-stu-id="3dea4-126">The **Weaknesses** page opens with the CVE information that you're looking for.</span></span>
<span data-ttu-id="3dea4-127">![已選取下拉選項「弱點」的全域搜尋方塊和 CVE 的範例。](images/tvm-vuln-globalsearch.png)</span><span class="sxs-lookup"><span data-stu-id="3dea4-127">![Global search box with the dropdown option "vulnerability" selected and an example CVE.](images/tvm-vuln-globalsearch.png)</span></span>
3. <span data-ttu-id="3dea4-128">選取 CVE 以開啟彈出面板及詳細資訊，包括弱點描述、詳細資料、威脅洞察及公開的裝置。</span><span class="sxs-lookup"><span data-stu-id="3dea4-128">Select the CVE to open a flyout panel with more information, including the vulnerability description, details, threat insights, and exposed devices.</span></span>

<span data-ttu-id="3dea4-129">若要查看 **弱點** 頁面中的其餘弱點，請輸入 CVE，然後選取 [搜尋]。</span><span class="sxs-lookup"><span data-stu-id="3dea4-129">To see the rest of the vulnerabilities in the **Weaknesses** page, type CVE, then select search.</span></span>

## <a name="weaknesses-overview"></a><span data-ttu-id="3dea4-130">弱點概述</span><span class="sxs-lookup"><span data-stu-id="3dea4-130">Weaknesses overview</span></span>

<span data-ttu-id="3dea4-131">修正公開裝置中的漏洞，以降低資產和組織的風險。</span><span class="sxs-lookup"><span data-stu-id="3dea4-131">Remediate the vulnerabilities in exposed devices to reduce the risk to your assets and organization.</span></span> <span data-ttu-id="3dea4-132">如果 [ **公開的裝置** ] 欄顯示0，表示您沒有危險。</span><span class="sxs-lookup"><span data-stu-id="3dea4-132">If the **Exposed Devices** column shows 0, that means you aren't at risk.</span></span>

![弱點登陸頁面。](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a><span data-ttu-id="3dea4-134">破壞和威脅洞察力</span><span class="sxs-lookup"><span data-stu-id="3dea4-134">Breach and threat insights</span></span>

<span data-ttu-id="3dea4-135">當圖示色彩紅色時，請在 [ **威脅** ] 欄中查看任何相關的侵犯和威脅洞察力。</span><span class="sxs-lookup"><span data-stu-id="3dea4-135">View any related breach and threat insights in the **Threat** column when the icons are colored red.</span></span>

 >[!NOTE]
 > <span data-ttu-id="3dea4-136">永遠優先考慮與現行威脅相關聯的建議。</span><span class="sxs-lookup"><span data-stu-id="3dea4-136">Always prioritize recommendations that are associated with ongoing threats.</span></span> <span data-ttu-id="3dea4-137">這些建議是以威脅真知灼見圖示標示， ![ 紅色的錯誤的簡單繪製方式。](images/tvm_bug_icon.png)</span><span class="sxs-lookup"><span data-stu-id="3dea4-137">These recommendations are marked with the threat insight icon ![Simple drawing of a red bug.](images/tvm_bug_icon.png)</span></span> <span data-ttu-id="3dea4-138">和違規洞察力圖示 ![ 簡單的箭號的箭號擊中目標。 ](images/tvm_alert_icon.png)</span><span class="sxs-lookup"><span data-stu-id="3dea4-138">and breach insight icon ![Simple drawing of an arrow hitting a target.](images/tvm_alert_icon.png).</span></span>  

<span data-ttu-id="3dea4-139">如果您的組織中有弱點，則破壞 insights 圖示會反白顯示。</span><span class="sxs-lookup"><span data-stu-id="3dea4-139">The breach insights icon is highlighted if there's a vulnerability found in your organization.</span></span>
<span data-ttu-id="3dea4-140">![當懸停于圖示上方時，可能會顯示的破壞洞察力文字範例。</span><span class="sxs-lookup"><span data-stu-id="3dea4-140">![Example of a breach insights text that could show up when hovering over icon.</span></span> <span data-ttu-id="3dea4-141">這會顯示「可能的作用中警示與此建議相關聯。](images/tvm-breach-insights.png)</span><span class="sxs-lookup"><span data-stu-id="3dea4-141">This one says "possible active alert is associated with this recommendation.](images/tvm-breach-insights.png)</span></span>

<span data-ttu-id="3dea4-142">如果您的組織中有相關弱點的漏洞，便會反白顯示威脅洞察力圖示。</span><span class="sxs-lookup"><span data-stu-id="3dea4-142">The threat insights icon is highlighted if there are associated exploits in the vulnerability found in your organization.</span></span> <span data-ttu-id="3dea4-143">懸停于圖示上方會顯示威脅是否屬於利用性套件的一部分，或連線至特定的高級持續性活動或活動群組。</span><span class="sxs-lookup"><span data-stu-id="3dea4-143">Hovering over the icon shows whether the threat is a part of an exploit kit, or connected to specific advanced persistent campaigns or activity groups.</span></span> <span data-ttu-id="3dea4-144">當可用時，會有一個指向威脅分析報告的連結，其中包含零天的新聞、披露或相關的安全性通報。</span><span class="sxs-lookup"><span data-stu-id="3dea4-144">When available, there's a link to a Threat Analytics report with zero-day exploitation news, disclosures, or related security advisories.</span></span>  

![懸停于圖示上方時可能顯示的威脅洞察力文字。](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a><span data-ttu-id="3dea4-147">取得弱點深入瞭解</span><span class="sxs-lookup"><span data-stu-id="3dea4-147">Gain vulnerability insights</span></span>

<span data-ttu-id="3dea4-148">如果您選取 CVE，將會以詳細資訊（如弱點描述、詳細資料、威脅洞察及公開的裝置）開啟彈出面板。</span><span class="sxs-lookup"><span data-stu-id="3dea4-148">If you select a CVE, a flyout panel will open with more information such as the vulnerability description, details, threat insights, and exposed devices.</span></span>

- <span data-ttu-id="3dea4-149">"OS Feature" 類別會顯示在相關案例中</span><span class="sxs-lookup"><span data-stu-id="3dea4-149">The "OS Feature" category is shown in relevant scenarios</span></span>
- <span data-ttu-id="3dea4-150">您可以使用公開裝置的每個 CVE，移至相關的安全性建議</span><span class="sxs-lookup"><span data-stu-id="3dea4-150">You can go to the related security recommendation for every CVE with exposed device</span></span>

 ![弱點飛出範例。](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a><span data-ttu-id="3dea4-152">不支援的軟體</span><span class="sxs-lookup"><span data-stu-id="3dea4-152">Software that isn't supported</span></span>

<span data-ttu-id="3dea4-153">Cve 未受到威脅 & 漏洞管理所支援的軟體，仍然存在於劣勢頁面中。</span><span class="sxs-lookup"><span data-stu-id="3dea4-153">CVEs for software that isn't currently supported by threat & vulnerability management is still present in the Weaknesses page.</span></span> <span data-ttu-id="3dea4-154">由於不支援軟體，所以只有有限的資料可供使用。</span><span class="sxs-lookup"><span data-stu-id="3dea4-154">Because the software is not supported, only limited data will be available.</span></span>

<span data-ttu-id="3dea4-155">使用不受支援的軟體的 Cve，公開的裝置資訊將無法使用。</span><span class="sxs-lookup"><span data-stu-id="3dea4-155">Exposed device information will not be available for CVEs with unsupported software.</span></span> <span data-ttu-id="3dea4-156">在「公開的裝置」區段中，選取「無法使用」選項，以不受支援的軟體進行篩選。</span><span class="sxs-lookup"><span data-stu-id="3dea4-156">Filter by unsupported software by selecting the "Not available" option in the "Exposed devices" section.</span></span>

 ![公開的裝置篩選器。](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a><span data-ttu-id="3dea4-158">在其他位置查看常見的漏洞和弱點 (CVE) 專案</span><span class="sxs-lookup"><span data-stu-id="3dea4-158">View Common Vulnerabilities and Exposures (CVE) entries in other places</span></span>

### <a name="top-vulnerable-software-in-the-dashboard"></a><span data-ttu-id="3dea4-159">儀表板中的最常見漏洞軟體</span><span class="sxs-lookup"><span data-stu-id="3dea4-159">Top vulnerable software in the dashboard</span></span>

1. <span data-ttu-id="3dea4-160">移至 [ [威脅與弱點管理] 儀表板](tvm-dashboard-insights.md) ，然後向左下至 **最常見的軟體** 構件。</span><span class="sxs-lookup"><span data-stu-id="3dea4-160">Go to the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) and scroll down to the **Top vulnerable software** widget.</span></span> <span data-ttu-id="3dea4-161">您將會看到每個軟體中所發現的漏洞數量，以及威脅資訊，以及一段時間內的設備危險性的高階觀點。</span><span class="sxs-lookup"><span data-stu-id="3dea4-161">You will see the number of vulnerabilities found in each software, along with threat information and a high-level view of device exposure over time.</span></span>

    ![具有四欄的常見軟體卡：軟體、弱點、威脅、公開裝置。](images/tvm-top-vulnerable-software500.png)

2. <span data-ttu-id="3dea4-163">選取您要調查的軟體，以移至深入分析頁面。</span><span class="sxs-lookup"><span data-stu-id="3dea4-163">Select the software you want to investigate to go to a drilldown page.</span></span>
3. <span data-ttu-id="3dea4-164">選取 [已 **發現的漏洞** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="3dea4-164">Select the **Discovered vulnerabilities** tab.</span></span>
4. <span data-ttu-id="3dea4-165">選取您要調查的漏洞，以取得有關弱點詳細資料的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="3dea4-165">Select the vulnerability you want to investigate for more information on vulnerability details</span></span>

    ![Windows Server 2019 深入查看一覽。](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a><span data-ttu-id="3dea4-167">探索裝置頁面中的漏洞</span><span class="sxs-lookup"><span data-stu-id="3dea4-167">Discover vulnerabilities in the device page</span></span>

<span data-ttu-id="3dea4-168">在 [裝置] 頁面中查看相關弱點資訊。</span><span class="sxs-lookup"><span data-stu-id="3dea4-168">View related weaknesses information in the device page.</span></span>

1. <span data-ttu-id="3dea4-169">移至 Microsoft Defender 安全性中心導覽功能表列，然後選取裝置圖示。</span><span class="sxs-lookup"><span data-stu-id="3dea4-169">Go to the Microsoft Defender Security Center navigation menu bar, then select the device icon.</span></span> <span data-ttu-id="3dea4-170">[ **裝置] 清單** 頁面隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="3dea4-170">The **Devices list** page opens.</span></span>
2. <span data-ttu-id="3dea4-171">在 [ **裝置] 清單** 頁面上，選取您要調查的裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="3dea4-171">In the **Devices list** page, select the device name that you want to investigate.</span></span>

    ![包含要調查之選定裝置的裝置清單。](images/tvm_machinetoinvestigate.png)

3. <span data-ttu-id="3dea4-173">裝置頁面會開啟您要調查之裝置的詳細資料和回應選項。</span><span class="sxs-lookup"><span data-stu-id="3dea4-173">The device page will open with details and response options for the device you want to investigate.</span></span>
4. <span data-ttu-id="3dea4-174">選取 **發現的漏洞**。</span><span class="sxs-lookup"><span data-stu-id="3dea4-174">Select **Discovered vulnerabilities**.</span></span>

    ![包含詳細資料和回應選項的裝置頁面。](images/tvm-discovered-vulnerabilities.png)

5. <span data-ttu-id="3dea4-176">選取您要調查的漏洞，以開啟具有 CVE 詳細資料的飛出面板，例如：弱點描述、威脅洞察力和偵測邏輯。</span><span class="sxs-lookup"><span data-stu-id="3dea4-176">Select the vulnerability that you want to investigate to open up a flyout panel with the CVE details, such as: vulnerability description, threat insights, and detection logic.</span></span>

#### <a name="cve-detection-logic"></a><span data-ttu-id="3dea4-177">CVE 偵測邏輯</span><span class="sxs-lookup"><span data-stu-id="3dea4-177">CVE Detection logic</span></span>

<span data-ttu-id="3dea4-178">類似于軟體證據，我們現在會顯示我們在裝置上所套用的偵測邏輯，以表明其存在漏洞。</span><span class="sxs-lookup"><span data-stu-id="3dea4-178">Similar to the software evidence, we now show the detection logic we applied on a device in order to state that it's vulnerable.</span></span> <span data-ttu-id="3dea4-179">新的區段稱為「偵測邏輯」，在裝置頁面) 中發現的任何弱點中 (，並顯示偵測邏輯和來源。</span><span class="sxs-lookup"><span data-stu-id="3dea4-179">The new section is called "Detection Logic" (in any discovered vulnerability in the device page) and shows the detection logic and source.</span></span>

<span data-ttu-id="3dea4-180">"OS Feature" 類別也會顯示在相關案例中。</span><span class="sxs-lookup"><span data-stu-id="3dea4-180">The "OS Feature" category is also shown in relevant scenarios.</span></span> <span data-ttu-id="3dea4-181">CVE 會影響只有在特定作業系統元件啟用時才會執行有漏洞作業系統的裝置。</span><span class="sxs-lookup"><span data-stu-id="3dea4-181">A CVE would affect devices that run a vulnerable OS only if a specific OS component is enabled.</span></span> <span data-ttu-id="3dea4-182">假設 Windows Server 2019 在其 DNS 元件中有弱點。</span><span class="sxs-lookup"><span data-stu-id="3dea4-182">Let's say Windows Server 2019 has vulnerability in its DNS component.</span></span> <span data-ttu-id="3dea4-183">透過這項新功能，我們只會將此 CVE 附加到 Windows Server 2019 裝置，其作業系統中已啟用 DNS 功能。</span><span class="sxs-lookup"><span data-stu-id="3dea4-183">With this new capability, we’ll only attach this CVE to the Windows Server 2019 devices with the DNS capability enabled in their OS.</span></span>

![偵測邏輯範例，列出在裝置和 Kb 上偵測到的軟體。](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="3dea4-185">報表 inaccuracy</span><span class="sxs-lookup"><span data-stu-id="3dea4-185">Report inaccuracy</span></span>

<span data-ttu-id="3dea4-186">當您看到任何不清楚、不正確或不完整的資訊時，報告誤報。</span><span class="sxs-lookup"><span data-stu-id="3dea4-186">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="3dea4-187">您也可以報告已經修正的安全性建議。</span><span class="sxs-lookup"><span data-stu-id="3dea4-187">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="3dea4-188">開啟 [弱點] 頁面上的 CVE。</span><span class="sxs-lookup"><span data-stu-id="3dea4-188">Open the CVE on the Weaknesses page.</span></span>
2. <span data-ttu-id="3dea4-189">選取 [ **報表 inaccuracy** ]，隨即會開啟彈出窗格。</span><span class="sxs-lookup"><span data-stu-id="3dea4-189">Select **Report inaccuracy** and a flyout pane will open.</span></span>
3. <span data-ttu-id="3dea4-190">從下拉式功能表中選取 [inaccuracy] 類別，然後填入您的電子郵件地址和 inaccuracy 詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3dea4-190">Select the inaccuracy category from the drop-down menu and fill in your email address and inaccuracy details.</span></span>
4. <span data-ttu-id="3dea4-191">選取 **[提交]**。</span><span class="sxs-lookup"><span data-stu-id="3dea4-191">Select **Submit**.</span></span> <span data-ttu-id="3dea4-192">您的意見反應會立即傳送給威脅和弱點管理專家。</span><span class="sxs-lookup"><span data-stu-id="3dea4-192">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3dea4-193">相關文章</span><span class="sxs-lookup"><span data-stu-id="3dea4-193">Related articles</span></span>

- [<span data-ttu-id="3dea4-194">威脅和弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="3dea4-194">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="3dea4-195">安全性建議</span><span class="sxs-lookup"><span data-stu-id="3dea4-195">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="3dea4-196">軟體清查</span><span class="sxs-lookup"><span data-stu-id="3dea4-196">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="3dea4-197">儀表板 insights</span><span class="sxs-lookup"><span data-stu-id="3dea4-197">Dashboard insights</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="3dea4-198">查看和組織 Microsoft Defender for Endpoint Devices 清單</span><span class="sxs-lookup"><span data-stu-id="3dea4-198">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
