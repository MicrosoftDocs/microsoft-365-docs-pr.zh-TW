---
title: 裝置用 Microsoft 安全分數
description: 您的裝置得分會顯示跨應用程式、作業系統、網路、帳戶及安全性控制裝置的集合安全性設定狀態。
keywords: 適用于裝置的 microsoft 安全分數、microsoft Defender for 裝置的端點 microsoft 安全評分、安全分數、設定分數、威脅與弱點管理、安全性控制、改進機遇、安全性設定分數，一段時間，安全性狀況，基準
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f2c799d477c400482c16b09b4d8a5cdc01106dfa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934078"
---
# <a name="microsoft-secure-score-for-devices"></a><span data-ttu-id="2d76a-104">裝置用 Microsoft 安全分數</span><span class="sxs-lookup"><span data-stu-id="2d76a-104">Microsoft Secure Score for Devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2d76a-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2d76a-105">**Applies to:**</span></span>

- [<span data-ttu-id="2d76a-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2d76a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="2d76a-107">威脅及弱點管理</span><span class="sxs-lookup"><span data-stu-id="2d76a-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="2d76a-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2d76a-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2d76a-109">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="2d76a-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2d76a-110">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="2d76a-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> <span data-ttu-id="2d76a-111">設定分數現在是裝置威脅與弱點管理的一部分，成為裝置的 Microsoft 安全分數。</span><span class="sxs-lookup"><span data-stu-id="2d76a-111">Configuration score is now part of threat and vulnerability management as Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="2d76a-112">您的裝置得分會顯示在 Microsoft Defender 資訊安全中心的[威脅與弱點管理儀表板](tvm-dashboard-insights.md)中。</span><span class="sxs-lookup"><span data-stu-id="2d76a-112">Your score for devices is visible in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="2d76a-113">針對裝置的 Microsoft 安全分數較高表示您的端點對 cybersecurity 威脅攻擊的彈性程度較高。</span><span class="sxs-lookup"><span data-stu-id="2d76a-113">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> <span data-ttu-id="2d76a-114">它會反映各類裝置的集合安全性設定狀態，其方式如下：</span><span class="sxs-lookup"><span data-stu-id="2d76a-114">It reflects the collective security configuration state of your devices across the following categories:</span></span>

- <span data-ttu-id="2d76a-115">應用程式</span><span class="sxs-lookup"><span data-stu-id="2d76a-115">Application</span></span>
- <span data-ttu-id="2d76a-116">作業系統</span><span class="sxs-lookup"><span data-stu-id="2d76a-116">Operating system</span></span>
- <span data-ttu-id="2d76a-117">網路</span><span class="sxs-lookup"><span data-stu-id="2d76a-117">Network</span></span>
- <span data-ttu-id="2d76a-118">帳戶</span><span class="sxs-lookup"><span data-stu-id="2d76a-118">Accounts</span></span>
- <span data-ttu-id="2d76a-119">安全性控制</span><span class="sxs-lookup"><span data-stu-id="2d76a-119">Security controls</span></span>

<span data-ttu-id="2d76a-120">選取類別以移至 [ [**安全性建議**](tvm-security-recommendation.md) ] 頁面，然後查看相關的建議。</span><span class="sxs-lookup"><span data-stu-id="2d76a-120">Select a category to go to the [**Security recommendations**](tvm-security-recommendation.md) page and view the relevant recommendations.</span></span>

## <a name="turn-on-the-microsoft-secure-score-connector"></a><span data-ttu-id="2d76a-121">開啟 Microsoft Secure 得分連接器</span><span class="sxs-lookup"><span data-stu-id="2d76a-121">Turn on the Microsoft Secure Score connector</span></span>

<span data-ttu-id="2d76a-122">轉寄 Microsoft Defender for Endpoint 信號，讓 Microsoft 安全分數能夠看到裝置安全狀況。</span><span class="sxs-lookup"><span data-stu-id="2d76a-122">Forward Microsoft Defender for Endpoint signals, giving Microsoft Secure Score visibility into the device security posture.</span></span> <span data-ttu-id="2d76a-123">轉寄的資料會與您的 Microsoft 安全分數資料儲存在相同的位置。</span><span class="sxs-lookup"><span data-stu-id="2d76a-123">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

<span data-ttu-id="2d76a-124">變更可能需要數小時的時間，才能在儀表板中反映。</span><span class="sxs-lookup"><span data-stu-id="2d76a-124">Changes might take up to a few hours to reflect in the dashboard.</span></span>

1. <span data-ttu-id="2d76a-125">在功能窗格中，移至 **設定**  >  **高級功能**</span><span class="sxs-lookup"><span data-stu-id="2d76a-125">In the navigation pane, go to **Settings** > **Advanced features**</span></span> 

2. <span data-ttu-id="2d76a-126">向左下往 **Microsoft 安全分數** ，將設定切換為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="2d76a-126">Scroll down to **Microsoft Secure Score** and toggle the setting to **On**.</span></span>

3. <span data-ttu-id="2d76a-127">選取 [ **儲存喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="2d76a-127">Select **Save preferences**.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="2d76a-128">運作方式</span><span class="sxs-lookup"><span data-stu-id="2d76a-128">How it works</span></span>

>[!NOTE]
> <span data-ttu-id="2d76a-129">目前裝置的 Microsoft 安全評分支援透過「群組原則」設定的設定。</span><span class="sxs-lookup"><span data-stu-id="2d76a-129">Microsoft Secure Score for Devices currently supports configurations set via Group Policy.</span></span> <span data-ttu-id="2d76a-130">由於目前的部分 Intune 支援，可能已透過 Intune 設定的設定會因設定錯誤而顯示。</span><span class="sxs-lookup"><span data-stu-id="2d76a-130">Due to the current partial Intune support, configurations which might have been set through Intune might show up as misconfigured.</span></span> <span data-ttu-id="2d76a-131">當您的組織使用 Intune 進行安全設定管理時，請與您的 IT 系統管理員聯繫，以確認實際的設定狀態。</span><span class="sxs-lookup"><span data-stu-id="2d76a-131">Contact your IT Administrator to verify the actual configuration status in case your organization is using Intune for secure configuration management.</span></span>

<span data-ttu-id="2d76a-132">[裝置的 Microsoft 安全計分] 中的資料是 meticulous 和日常弱點探索程式的產品。</span><span class="sxs-lookup"><span data-stu-id="2d76a-132">The data in the Microsoft Secure Score for Devices card is the product of meticulous and ongoing vulnerability discovery process.</span></span> <span data-ttu-id="2d76a-133">它會以持續進行的設定探索評估進行匯總：</span><span class="sxs-lookup"><span data-stu-id="2d76a-133">It is aggregated with configuration discovery assessments that continuously:</span></span>

- <span data-ttu-id="2d76a-134">比較收集的基準與收集的基準，以發現配置錯誤的資產</span><span class="sxs-lookup"><span data-stu-id="2d76a-134">Compare collected configurations to the collected benchmarks to discover misconfigured assets</span></span>
- <span data-ttu-id="2d76a-135">將設定對應至可修正或部分修正的漏洞 (風險降低) </span><span class="sxs-lookup"><span data-stu-id="2d76a-135">Map configurations to vulnerabilities that can be remediated or partially remediated (risk reduction)</span></span>
- <span data-ttu-id="2d76a-136">收集及維護最佳作法設定基準 (廠商、安全性摘要、內部研究小組) </span><span class="sxs-lookup"><span data-stu-id="2d76a-136">Collect and maintain best practice configuration benchmarks (vendors, security feeds, internal research teams)</span></span>
- <span data-ttu-id="2d76a-137">從所有資產收集及監視安全性控制設定狀態的變更</span><span class="sxs-lookup"><span data-stu-id="2d76a-137">Collect and monitor changes of security control configuration state from all assets</span></span>

## <a name="improve-your-security-configuration"></a><span data-ttu-id="2d76a-138">提升您的安全性設定</span><span class="sxs-lookup"><span data-stu-id="2d76a-138">Improve your security configuration</span></span>

<span data-ttu-id="2d76a-139">修正安全性建議清單中的問題，以改善安全性設定。</span><span class="sxs-lookup"><span data-stu-id="2d76a-139">Improve your security configuration by remediating issues from the security recommendations list.</span></span> <span data-ttu-id="2d76a-140">當您這麼做時，裝置的 Microsoft 安全評分會提升，而且您的組織會變得更具彈性，以防禦 cybersecurity 威脅和弱點。</span><span class="sxs-lookup"><span data-stu-id="2d76a-140">As you do so, your Microsoft Secure Score for Devices improves and your organization becomes more resilient against cybersecurity threats and vulnerabilities.</span></span>

1. <span data-ttu-id="2d76a-141">從威脅與弱點管理儀表板中的 [裝置] 的 [Microsoft Secure 得分] 中，選取其中一個類別。</span><span class="sxs-lookup"><span data-stu-id="2d76a-141">From the Microsoft Secure Score for Devices card in the threat and vulnerability management dashboard, select the one of the categories.</span></span> <span data-ttu-id="2d76a-142">您將會看到與該類別相關的建議清單。</span><span class="sxs-lookup"><span data-stu-id="2d76a-142">You'll view the list of recommendations related to that category.</span></span> <span data-ttu-id="2d76a-143">將會帶您前往 [ [**安全性建議**](tvm-security-recommendation.md) ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="2d76a-143">It will take you to the [**Security recommendations**](tvm-security-recommendation.md) page.</span></span> <span data-ttu-id="2d76a-144">如果您想要查看所有安全性建議，只要您到達 [安全性建議] 頁面，就會清除 [搜尋] 欄位。</span><span class="sxs-lookup"><span data-stu-id="2d76a-144">If you want to see all security recommendations, once you get to the Security recommendations page, clear the search field.</span></span>

2. <span data-ttu-id="2d76a-145">選取清單中的專案。</span><span class="sxs-lookup"><span data-stu-id="2d76a-145">Select an item on the list.</span></span> <span data-ttu-id="2d76a-146">隨即會開啟彈出面板，其中會顯示與建議相關的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2d76a-146">The flyout panel will open with details related to the recommendation.</span></span> <span data-ttu-id="2d76a-147">選取 [ **修復選項**]。</span><span class="sxs-lookup"><span data-stu-id="2d76a-147">Select **Remediation options**.</span></span>

   ![安全性控制相關的安全性建議](images/tvm_security_controls.png)

3. <span data-ttu-id="2d76a-149">閱讀描述以瞭解問題的內容及下一步的工作。</span><span class="sxs-lookup"><span data-stu-id="2d76a-149">Read the description to understand the context of the issue and what to do next.</span></span> <span data-ttu-id="2d76a-150">選取 [到期日]、[新增附注]，然後選取 [將 **所有修復活動資料匯出至 CSV** ]，以便將其附加至電子郵件進行後續工作。</span><span class="sxs-lookup"><span data-stu-id="2d76a-150">Select a due date, add notes, and select **Export all remediation activity data to CSV** so you can attach it to an email for follow-up.</span></span>

4. <span data-ttu-id="2d76a-151">**提交要求**。</span><span class="sxs-lookup"><span data-stu-id="2d76a-151">**Submit request**.</span></span> <span data-ttu-id="2d76a-152">您會看到一則確認訊息，表明已建立修復工作。</span><span class="sxs-lookup"><span data-stu-id="2d76a-152">You'll see a confirmation message that the remediation task has been created.</span></span>
   <span data-ttu-id="2d76a-153">![修正任務建立確認](images/tvm_remediation_task_created.png)</span><span class="sxs-lookup"><span data-stu-id="2d76a-153">![Remediation task creation confirmation](images/tvm_remediation_task_created.png)</span></span>

5. <span data-ttu-id="2d76a-154">儲存 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="2d76a-154">Save your CSV file.</span></span>
   <span data-ttu-id="2d76a-155">![儲存 csv 檔案](images/tvm_save_csv_file.png)</span><span class="sxs-lookup"><span data-stu-id="2d76a-155">![Save csv file](images/tvm_save_csv_file.png)</span></span>

6. <span data-ttu-id="2d76a-156">傳送追蹤電子郵件給您的 IT 系統管理員，並允許您為修正所分派的時間傳播至系統。</span><span class="sxs-lookup"><span data-stu-id="2d76a-156">Send a follow-up email to your IT Administrator and allow the time that you've allotted for the remediation to propagate in the system.</span></span>

7. <span data-ttu-id="2d76a-157">再次檢查儀表板上的 [ **裝置的 Microsoft 安全計分** ] 卡片。</span><span class="sxs-lookup"><span data-stu-id="2d76a-157">Review the **Microsoft Secure Score for Devices** card again on the dashboard.</span></span> <span data-ttu-id="2d76a-158">安全性控制建議的數目會減少。</span><span class="sxs-lookup"><span data-stu-id="2d76a-158">The number of security controls recommendations will decrease.</span></span> <span data-ttu-id="2d76a-159">當您選取 [ **安全性控制** 措施回到 **安全性建議** ] 頁面時，您所寄出的專案將不再列出。</span><span class="sxs-lookup"><span data-stu-id="2d76a-159">When you select **Security controls** to go back to the **Security recommendations** page, the item that you've addressed won't be listed there anymore.</span></span> <span data-ttu-id="2d76a-160">您的裝置的 Microsoft 安全評分應該會增加。</span><span class="sxs-lookup"><span data-stu-id="2d76a-160">Your Microsoft Secure Score for Devices should increase.</span></span>

>[!IMPORTANT]
><span data-ttu-id="2d76a-161">若要提升您的漏洞評估偵測率，請下載下列強制執行的安全性更新，並在您的網路中加以部署：</span><span class="sxs-lookup"><span data-stu-id="2d76a-161">To boost your vulnerability assessment detection rates, download the following mandatory security updates and deploy them in your network:</span></span>
>- <span data-ttu-id="2d76a-162">19H1 客戶 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span><span class="sxs-lookup"><span data-stu-id="2d76a-162">19H1 customers | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span></span>
>- <span data-ttu-id="2d76a-163">RS5 客戶 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span><span class="sxs-lookup"><span data-stu-id="2d76a-163">RS5 customers | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span></span>
>- <span data-ttu-id="2d76a-164">RS4 客戶 | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="2d76a-164">RS4 customers | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
>- <span data-ttu-id="2d76a-165">RS3 客戶 | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="2d76a-165">RS3 customers | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
>
><span data-ttu-id="2d76a-166">若要下載安全性更新：</span><span class="sxs-lookup"><span data-stu-id="2d76a-166">To download the security updates:</span></span>
>1. <span data-ttu-id="2d76a-167">移至 [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2d76a-167">Go to [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span></span>
>2. <span data-ttu-id="2d76a-168">在您需要下載的安全性更新 KB 編號中，按一下 [機碼]，然後按一下 [ **搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="2d76a-168">Key-in the security update KB number that you need to download, then click **Search**.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="2d76a-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="2d76a-169">Related topics</span></span>

- [<span data-ttu-id="2d76a-170">威脅與弱點管理概述</span><span class="sxs-lookup"><span data-stu-id="2d76a-170">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="2d76a-171">儀表板</span><span class="sxs-lookup"><span data-stu-id="2d76a-171">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="2d76a-172">暴險分數</span><span class="sxs-lookup"><span data-stu-id="2d76a-172">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="2d76a-173">安全性建議</span><span class="sxs-lookup"><span data-stu-id="2d76a-173">Security recommendations</span></span>](tvm-security-recommendation.md)
