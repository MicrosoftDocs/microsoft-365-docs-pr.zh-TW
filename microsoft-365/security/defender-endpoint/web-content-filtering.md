---
title: Web 內容篩選
description: 使用 Microsoft Defender for Endpoint 中的 web 內容篩選，以根據內容類別別來追蹤和控制網站的存取權。
keywords: web 保護，網頁威脅防護，網頁流覽，監控，報表，卡片，網域清單，安全性，網路釣魚，惡意程式碼，exploit，網站，網路保護，Edge，Internet Explorer，Chrome，Firefox，網頁瀏覽器
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a16e3eb8f6f7eae9fbaa82c9fd978f4fef429818
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822319"
---
# <a name="web-content-filtering"></a><span data-ttu-id="b47d2-104">Web 內容篩選</span><span class="sxs-lookup"><span data-stu-id="b47d2-104">Web content filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b47d2-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="b47d2-105">**Applies to:**</span></span>
- [<span data-ttu-id="b47d2-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b47d2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b47d2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b47d2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="b47d2-108">**Web 內容篩選目前是公開預覽**</span><span class="sxs-lookup"><span data-stu-id="b47d2-108">**Web content filtering is currently in public preview**</span></span><br>
> <span data-ttu-id="b47d2-109">此預覽版本提供時沒有服務等級協定，不建議用於實際執行工作負載。</span><span class="sxs-lookup"><span data-stu-id="b47d2-109">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="b47d2-110">某些功能可能不受支援，或可能具有有限的功能。</span><span class="sxs-lookup"><span data-stu-id="b47d2-110">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="b47d2-111">如需詳細資訊，請參閱 [Microsoft Defender For Endpoint preview 功能](preview.md)。</span><span class="sxs-lookup"><span data-stu-id="b47d2-111">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

> [!TIP]
> <span data-ttu-id="b47d2-112">想要體驗適用於端點的 Microsoft Defender 嗎？</span><span class="sxs-lookup"><span data-stu-id="b47d2-112">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b47d2-113">注册免費試用版。</span><span class="sxs-lookup"><span data-stu-id="b47d2-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="b47d2-114">Web 內容篩選是 Microsoft Defender for Endpoint 中的 [web 保護](web-protection-overview.md) 功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="b47d2-114">Web content filtering is part of [Web protection](web-protection-overview.md) capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b47d2-115">它可讓您的組織根據其內容類別別來追蹤和控制網站的存取權。</span><span class="sxs-lookup"><span data-stu-id="b47d2-115">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="b47d2-116">許多這類網站雖然並非惡意，但因相容性法規、頻寬使用量或其他考慮而可能會造成問題。</span><span class="sxs-lookup"><span data-stu-id="b47d2-116">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

<span data-ttu-id="b47d2-117">設定各裝置群組中的原則，以封鎖特定類別。</span><span class="sxs-lookup"><span data-stu-id="b47d2-117">Configure policies across your device groups to block certain categories.</span></span> <span data-ttu-id="b47d2-118">封鎖類別，可防止指定裝置群組中的使用者存取與類別相關聯的 URLs。</span><span class="sxs-lookup"><span data-stu-id="b47d2-118">Blocking a category prevents users within specified device groups from accessing URLs associated with the category.</span></span> <span data-ttu-id="b47d2-119">對於任何未封鎖的類別，會自動對 URLs 進行審核。</span><span class="sxs-lookup"><span data-stu-id="b47d2-119">For any category that's not blocked, the URLs are automatically audited.</span></span> <span data-ttu-id="b47d2-120">您的使用者可以存取沒有中斷的 URLs，您會收集存取統計資料，以協助建立更多自訂的原則決定。</span><span class="sxs-lookup"><span data-stu-id="b47d2-120">Your users can access the URLs without disruption, and you'll gather access statistics to help create a more custom policy decision.</span></span> <span data-ttu-id="b47d2-121">如果您正在查看的頁面上的元素是撥打封鎖的資源，您的使用者就會看到封鎖通知。</span><span class="sxs-lookup"><span data-stu-id="b47d2-121">Your users will see a block notification if an element on the page they're viewing is making calls to a blocked resource.</span></span>

<span data-ttu-id="b47d2-122">web 內容篩選在主要網頁瀏覽器上提供，Windows Defender SmartScreen (Microsoft Edge) 和網路保護 (Chrome、Firefox、Brave 及 Opera) 。</span><span class="sxs-lookup"><span data-stu-id="b47d2-122">Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Brave and Opera).</span></span> <span data-ttu-id="b47d2-123">如需瀏覽器支援的相關資訊，請參閱必要條件一節。</span><span class="sxs-lookup"><span data-stu-id="b47d2-123">For more information about browser support, see the prerequisites section.</span></span>

<span data-ttu-id="b47d2-124">摘要優點：</span><span class="sxs-lookup"><span data-stu-id="b47d2-124">Summarizing the benefits:</span></span>

- <span data-ttu-id="b47d2-125">使用者無法存取封鎖類別中的網站，不論他們是在內部部署還是離開流覽</span><span class="sxs-lookup"><span data-stu-id="b47d2-125">Users are prevented from accessing websites in blocked categories, whether they're browsing on-premises or away</span></span>
- <span data-ttu-id="b47d2-126">您的安全小組可以使用 Microsoft Defender 中定義的裝置群組，輕鬆地將原則部署至使用者群組 [，以用於以端點角色為基礎的存取控制設定](/microsoft-365/security/defender-endpoint/rbac)</span><span class="sxs-lookup"><span data-stu-id="b47d2-126">Your security team can conveniently deploy policies to groups of users using device groups defined in [Microsoft Defender for Endpoint role-based access control settings](/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="b47d2-127">您的安全小組可以存取相同中央位置的 web 報表，並透過實際區塊和 web 使用狀況進行查看</span><span class="sxs-lookup"><span data-stu-id="b47d2-127">Your security team can access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="user-experience"></a><span data-ttu-id="b47d2-128">使用者體驗</span><span class="sxs-lookup"><span data-stu-id="b47d2-128">User experience</span></span>

<span data-ttu-id="b47d2-129">支援協力廠商瀏覽器的封鎖體驗是由網路保護提供，其可提供系統層級 toast，通知使用者封鎖的連線。</span><span class="sxs-lookup"><span data-stu-id="b47d2-129">The blocking experience for 3rd party supported browsers is provided by Network Protection, which provides a system-level toast notifying the user of a blocked connection.</span></span> <span data-ttu-id="b47d2-130">若要讓使用者更友好，在瀏覽器中的體驗，請考慮使用 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b47d2-130">For a more user-friendly, in-browser experience, consider using Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b47d2-131">必要條件</span><span class="sxs-lookup"><span data-stu-id="b47d2-131">Prerequisites</span></span>

<span data-ttu-id="b47d2-132">在嘗試此功能之前，請確定您符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="b47d2-132">Before trying out this feature, make sure you meet the following requirements:</span></span>

- <span data-ttu-id="b47d2-133">Windows 10 企業版E5、Microsoft 365 E5、Microsoft 365 E5 安全性、Microsoft 365 E3 + Microsoft 365 E5 安全性附加元件或 Microsoft Defender for Endpoint 獨立授權。</span><span class="sxs-lookup"><span data-stu-id="b47d2-133">Windows 10 Enterprise E5, Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security add-on or the Microsoft Defender for Endpoint standalone license.</span></span> 
- <span data-ttu-id="b47d2-134">存取 Microsoft Defender 資訊安全中心入口網站 (https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="b47d2-134">Access to Microsoft Defender Security Center portal (https://securitycenter.windows.com).</span></span>
- <span data-ttu-id="b47d2-135">執行 Windows 10 周年紀念日的裝置會以最新的 Microsoft Defender 反惡意程式碼引擎更新 (版本 1607) 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b47d2-135">Devices running Windows 10 Anniversary Update (version 1607) or later with the latest Microsoft Defender antimalware engine update.</span></span>

## <a name="data-handling"></a><span data-ttu-id="b47d2-136">資料處理</span><span class="sxs-lookup"><span data-stu-id="b47d2-136">Data handling</span></span>

<span data-ttu-id="b47d2-137">資料儲存在 [Microsoft Defender For Endpoint data 處理設定](data-storage-privacy.md)的一部分中所選取的區域。</span><span class="sxs-lookup"><span data-stu-id="b47d2-137">Data is stored in the region that was selected as part of your [Microsoft Defender for Endpoint data handling settings](data-storage-privacy.md).</span></span> <span data-ttu-id="b47d2-138">您的資料不會離開該地區的資料中心。</span><span class="sxs-lookup"><span data-stu-id="b47d2-138">Your data will not leave the data center in that region.</span></span> <span data-ttu-id="b47d2-139">此外，所有協力廠商都不會共用您的資料，包括我們的資料提供者。</span><span class="sxs-lookup"><span data-stu-id="b47d2-139">In addition, your data will not be shared with any third-parties, including our data providers.</span></span>

## <a name="turn-on-web-content-filtering"></a><span data-ttu-id="b47d2-140">開啟 web 內容篩選</span><span class="sxs-lookup"><span data-stu-id="b47d2-140">Turn on web content filtering</span></span>

<span data-ttu-id="b47d2-141">從左導覽功能表中，選取 [**設定**  >  **一般**  >  **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="b47d2-141">From the left-hand navigation menu, select **Settings** > **General** > **Advanced Features**.</span></span> <span data-ttu-id="b47d2-142">向左下向後，直到您看到 **Web 內容篩選** 的專案。</span><span class="sxs-lookup"><span data-stu-id="b47d2-142">Scroll down until you see the entry for **Web content filtering**.</span></span> <span data-ttu-id="b47d2-143">切換到 [ **開啟** ] 和 [ **儲存] 偏好** 設定。</span><span class="sxs-lookup"><span data-stu-id="b47d2-143">Switch the toggle to **On** and **Save preferences**.</span></span>

### <a name="configure-web-content-filtering-policies"></a><span data-ttu-id="b47d2-144">設定 web 內容篩選原則</span><span class="sxs-lookup"><span data-stu-id="b47d2-144">Configure web content filtering policies</span></span>

<span data-ttu-id="b47d2-145">Web 內容篩選原則會指定哪些網站類別會封鎖在哪些裝置群組上。</span><span class="sxs-lookup"><span data-stu-id="b47d2-145">Web content filtering policies specify which site categories are blocked on which device groups.</span></span> <span data-ttu-id="b47d2-146">若要管理原則，請移至 **設定**  >  **規則**  >  **Web 內容篩選**。</span><span class="sxs-lookup"><span data-stu-id="b47d2-146">To manage the policies, go to **Settings** > **Rules** > **Web content filtering**.</span></span>

<span data-ttu-id="b47d2-147">使用篩選器來尋找包含某些封鎖類別或套用至特定裝置群組的原則。</span><span class="sxs-lookup"><span data-stu-id="b47d2-147">Use the filter to locate policies that contain certain blocked categories or are applied to specific device groups.</span></span>

### <a name="create-a-policy"></a><span data-ttu-id="b47d2-148">建立原則</span><span class="sxs-lookup"><span data-stu-id="b47d2-148">Create a policy</span></span>

<span data-ttu-id="b47d2-149">若要新增新的原則：</span><span class="sxs-lookup"><span data-stu-id="b47d2-149">To add a new policy:</span></span>

1. <span data-ttu-id="b47d2-150">在 **設定** 中的 [ **Web 內容篩選**] 頁面上，選取 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="b47d2-150">Select **Add policy** on the **Web content filtering** page in **Settings**.</span></span>

2. <span data-ttu-id="b47d2-151">指定名稱。</span><span class="sxs-lookup"><span data-stu-id="b47d2-151">Specify a name.</span></span>

3. <span data-ttu-id="b47d2-152">選取要封鎖的類別。</span><span class="sxs-lookup"><span data-stu-id="b47d2-152">Select the categories to block.</span></span> <span data-ttu-id="b47d2-153">使用展開圖示可完整展開每個上層類別，並選取 [特定 web 內容類別別]。</span><span class="sxs-lookup"><span data-stu-id="b47d2-153">Use the expand icon to fully expand each parent category and select specific web content categories.</span></span>

4. <span data-ttu-id="b47d2-154">指定原則範圍。</span><span class="sxs-lookup"><span data-stu-id="b47d2-154">Specify the policy scope.</span></span> <span data-ttu-id="b47d2-155">選取 [裝置群組]，以指定要套用原則的位置。</span><span class="sxs-lookup"><span data-stu-id="b47d2-155">Select the device groups to specify where to apply the policy.</span></span> <span data-ttu-id="b47d2-156">只有選定裝置群組中的裝置會無法存取選取類別中的網站。</span><span class="sxs-lookup"><span data-stu-id="b47d2-156">Only devices in the selected device groups will be prevented from accessing websites in the selected categories.</span></span>

5. <span data-ttu-id="b47d2-157">請複查摘要並儲存原則。</span><span class="sxs-lookup"><span data-stu-id="b47d2-157">Review the summary and save the policy.</span></span> <span data-ttu-id="b47d2-158">原則更新最多可能需要2個小時才能套用至您選取的裝置。</span><span class="sxs-lookup"><span data-stu-id="b47d2-158">The policy refresh may take up to 2 hours to apply to your selected devices.</span></span>

> [!NOTE]
> - <span data-ttu-id="b47d2-159">您可以部署原則，而不需要選取裝置群組上的任何類別。</span><span class="sxs-lookup"><span data-stu-id="b47d2-159">You can deploy a policy without selecting any category on a device group.</span></span> <span data-ttu-id="b47d2-160">此巨集指令只會建立一個審核原則，以協助您在建立封鎖原則之前瞭解使用者行為。</span><span class="sxs-lookup"><span data-stu-id="b47d2-160">This action will create an audit only policy, to help you understand user behavior before creating a block policy.</span></span>
> - <span data-ttu-id="b47d2-161">如果您要同時移除原則或變更裝置群組，這可能會導致原則部署延遲。</span><span class="sxs-lookup"><span data-stu-id="b47d2-161">If you are removing a policy or changing device groups at the same time, this might cause a delay in policy deployment.</span></span>
> - <span data-ttu-id="b47d2-162">封鎖 "未分類" 類別可能會導致意外的和不想要的結果。</span><span class="sxs-lookup"><span data-stu-id="b47d2-162">Blocking the "Uncategorized" category may lead to unexpected and undesired results.</span></span>  

### <a name="allow-specific-websites"></a><span data-ttu-id="b47d2-163">允許特定網站</span><span class="sxs-lookup"><span data-stu-id="b47d2-163">Allow specific websites</span></span>

<span data-ttu-id="b47d2-164">您可以透過建立自訂指示器原則，覆寫 web 內容篩選中封鎖的類別以允許單一網站。</span><span class="sxs-lookup"><span data-stu-id="b47d2-164">It's possible to override the blocked category in web content filtering to allow a single site by creating a custom indicator policy.</span></span> <span data-ttu-id="b47d2-165">自訂指示器原則會在將 web 內容篩選原則套用至有問題的裝置群組時，取代該原則。</span><span class="sxs-lookup"><span data-stu-id="b47d2-165">The custom indicator policy will supersede the web content filtering policy when it's applied to the device group in question.</span></span>

1. <span data-ttu-id="b47d2-166">前往 **設定** 指標  >    >  **URL/網域**  >  **新增專案**，以在 Microsoft Defender 資訊安全中心中建立自訂指示器。</span><span class="sxs-lookup"><span data-stu-id="b47d2-166">Create a custom indicator in the Microsoft Defender Security Center by going to **Settings** > **Indicators** > **URL/Domain** > **Add Item**.</span></span>

2. <span data-ttu-id="b47d2-167">輸入網站的網域。</span><span class="sxs-lookup"><span data-stu-id="b47d2-167">Enter the domain of the site.</span></span>

3. <span data-ttu-id="b47d2-168">將 [原則動作] 設定為 [ **允許**]。</span><span class="sxs-lookup"><span data-stu-id="b47d2-168">Set the policy action to **Allow**.</span></span>  

### <a name="reporting-inaccuracies"></a><span data-ttu-id="b47d2-169">報告不准確性</span><span class="sxs-lookup"><span data-stu-id="b47d2-169">Reporting inaccuracies</span></span>

<span data-ttu-id="b47d2-170">如果您遇到的網域分類不正確，您可以從 [Web 內容篩選報告] 頁面直接向我們報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="b47d2-170">If you encounter a domain that has been incorrectly categorized, you can report inaccuracies directly to us from the Web Content Filtering reports page.</span></span> <span data-ttu-id="b47d2-171">此功能僅適用于新的 Microsoft 365 security center (security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="b47d2-171">This feature is available only in the new Microsoft 365 security center (security.microsoft.com).</span></span>

<span data-ttu-id="b47d2-172">若要報告 inaccuracy，請流覽至 [**報表**  >  **web protection**  >  **web 內容篩選] 詳細資料**  >  **域**。</span><span class="sxs-lookup"><span data-stu-id="b47d2-172">To report an inaccuracy, navigate to **Reports** > **Web protection** > **Web Content Filtering Details** > **Domains**.</span></span> <span data-ttu-id="b47d2-173">在我們 Web 內容篩選報告的 [網域] 索引標籤上，您會在每個網域旁看到省略號。</span><span class="sxs-lookup"><span data-stu-id="b47d2-173">On the domains tab of our Web Content Filtering reports, you will see an ellipsis beside each of the domains.</span></span> <span data-ttu-id="b47d2-174">將游標移到這個省略號上，然後選取 [ **報表 Inaccuracy**]。</span><span class="sxs-lookup"><span data-stu-id="b47d2-174">Hover over this ellipsis and select **Report Inaccuracy**.</span></span>

<span data-ttu-id="b47d2-175">隨即會開啟一個面板，您可以在其中選取優先順序，並新增其他詳細資料，例如用於重新分類的建議類別。</span><span class="sxs-lookup"><span data-stu-id="b47d2-175">A panel will open where you can select the priority and add additional details such as the suggested category for re-categorization.</span></span> <span data-ttu-id="b47d2-176">完成表單之後，請選取 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="b47d2-176">Once you complete the form, select **Submit**.</span></span> <span data-ttu-id="b47d2-177">我們的團隊會在一部工作日內檢查要求。</span><span class="sxs-lookup"><span data-stu-id="b47d2-177">Our team will review the request within one business day.</span></span> <span data-ttu-id="b47d2-178">若要立即解除阻隔，請建立 [自訂允許指標](indicator-ip-domain.md)。</span><span class="sxs-lookup"><span data-stu-id="b47d2-178">For immediate unblocking, create a [custom allow indicator](indicator-ip-domain.md).</span></span>

## <a name="web-content-filtering-cards-and-details"></a><span data-ttu-id="b47d2-179">Web 內容篩選卡片和詳細資料</span><span class="sxs-lookup"><span data-stu-id="b47d2-179">Web content filtering cards and details</span></span>

<span data-ttu-id="b47d2-180">選取 [**報告**  >  **web 保護**] 以查看卡片，以查看有關 web 內容篩選和網頁威脅防護的資訊。</span><span class="sxs-lookup"><span data-stu-id="b47d2-180">Select **Reports** > **Web protection** to view cards with information about web content filtering and web threat protection.</span></span> <span data-ttu-id="b47d2-181">下列卡片提供有關 web 內容篩選的摘要資訊。</span><span class="sxs-lookup"><span data-stu-id="b47d2-181">The following cards provide summary information about web content filtering.</span></span>

### <a name="web-activity-by-category"></a><span data-ttu-id="b47d2-182">依類別的網頁活動</span><span class="sxs-lookup"><span data-stu-id="b47d2-182">Web activity by category</span></span>

<span data-ttu-id="b47d2-183">此卡片會列出具有最大增加或減少訪問嘗試次數的父項 web 內容類別別。</span><span class="sxs-lookup"><span data-stu-id="b47d2-183">This card lists the parent web content categories with the largest increase or decrease in the number of access attempts.</span></span> <span data-ttu-id="b47d2-184">瞭解貴組織中從過去30天、3個月或6個月之網頁活動模式產生的重大變更。</span><span class="sxs-lookup"><span data-stu-id="b47d2-184">Understand drastic changes in web activity patterns in your organization from last 30 days, 3 months, or 6 months.</span></span> <span data-ttu-id="b47d2-185">選取類別名稱以查看詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b47d2-185">Select a category name to view more information.</span></span>

<span data-ttu-id="b47d2-186">在使用此功能的前30天內，您的組織可能沒有足夠的資料可顯示此資訊。</span><span class="sxs-lookup"><span data-stu-id="b47d2-186">In the first 30 days of using this feature, your organization might not have enough data to display this information.</span></span>

![依類別卡片的 web 活動影像](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a><span data-ttu-id="b47d2-188">Web 內容篩選摘要卡</span><span class="sxs-lookup"><span data-stu-id="b47d2-188">Web content filtering  summary card</span></span>

<span data-ttu-id="b47d2-189">這張牌會顯示跨不同父項 web 內容類別別的封鎖存取嘗試散佈。</span><span class="sxs-lookup"><span data-stu-id="b47d2-189">This card displays the distribution of blocked access attempts across the different parent web content categories.</span></span> <span data-ttu-id="b47d2-190">選取其中一個彩色橫條圖，以查看特定上層網頁類別的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b47d2-190">Select one of the colored bars to view more information about a specific parent web category.</span></span>

![Web 內容篩選摘要卡的影像](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a><span data-ttu-id="b47d2-192">網頁活動摘要卡</span><span class="sxs-lookup"><span data-stu-id="b47d2-192">Web activity summary card</span></span>

<span data-ttu-id="b47d2-193">這張牌會顯示所有 URLs 中的 web 內容要求總數目。</span><span class="sxs-lookup"><span data-stu-id="b47d2-193">This card displays the total number of requests for web content in all URLs.</span></span>

![Web 活動摘要卡的影像](images/web-activity-summary.png)

### <a name="view-card-details"></a><span data-ttu-id="b47d2-195">查看卡片詳細資料</span><span class="sxs-lookup"><span data-stu-id="b47d2-195">View card details</span></span>

<span data-ttu-id="b47d2-196">您可以從卡片中的圖表選取表格列或彩色的橫條圖，以存取每張卡片的 **報告詳細資料** 。</span><span class="sxs-lookup"><span data-stu-id="b47d2-196">You can access the **Report details** for each card by selecting a table row or colored bar from the chart in the card.</span></span> <span data-ttu-id="b47d2-197">每張卡片的「報告詳細資料」頁面包含有關 web 內容類別別、網站網域和裝置群組的大量統計資料。</span><span class="sxs-lookup"><span data-stu-id="b47d2-197">The report details page for each card contains extensive statistical data about web content categories, website domains, and device groups.</span></span>

![Web 保護報告詳細資料的影像](images/web-protection-report-details.png)

- <span data-ttu-id="b47d2-199">**網頁類別**：列出在您的組織中有存取嘗試的 Web 內容類別別。</span><span class="sxs-lookup"><span data-stu-id="b47d2-199">**Web categories**: Lists the web content categories that have had access attempts in your organization.</span></span> <span data-ttu-id="b47d2-200">選取特定類別以開啟 [摘要] 飛出狀態。</span><span class="sxs-lookup"><span data-stu-id="b47d2-200">Select a specific category to open a summary flyout.</span></span>

- <span data-ttu-id="b47d2-201">**網域**：列出組織中已存取或封鎖的網頁網域。</span><span class="sxs-lookup"><span data-stu-id="b47d2-201">**Domains**: Lists the web domains that have been accessed or blocked in your organization.</span></span> <span data-ttu-id="b47d2-202">選取特定網域，以查看該網域的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b47d2-202">Select a specific domain to view detailed information about that domain.</span></span>

- <span data-ttu-id="b47d2-203">**裝置群組**：列出組織中已產生 web 活動的所有裝置群組</span><span class="sxs-lookup"><span data-stu-id="b47d2-203">**Device groups**: Lists all the device groups that have generated web activity in your organization</span></span>

<span data-ttu-id="b47d2-204">使用頁面左上角的 [時間範圍] 篩選，選取時段。</span><span class="sxs-lookup"><span data-stu-id="b47d2-204">Use the time range filter at the top left of the page to select a time period.</span></span> <span data-ttu-id="b47d2-205">您也可以篩選資訊或自訂欄位。</span><span class="sxs-lookup"><span data-stu-id="b47d2-205">You can also filter the information or customize the columns.</span></span> <span data-ttu-id="b47d2-206">選取資料列，以開啟彈出窗格，以及更多有關所選取專案的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b47d2-206">Select a row to open a flyout pane with even more information about the selected item.</span></span>

## <a name="errors-and-issues"></a><span data-ttu-id="b47d2-207">錯誤和問題</span><span class="sxs-lookup"><span data-stu-id="b47d2-207">Errors and issues</span></span>

### <a name="limitations-and-known-issues-in-this-preview"></a><span data-ttu-id="b47d2-208">此預覽中的限制與已知問題</span><span class="sxs-lookup"><span data-stu-id="b47d2-208">Limitations and known issues in this preview</span></span>

- <span data-ttu-id="b47d2-209">只有在裝置的 os 設定為 Server (**cmd**  >  **Systeminfo**  >  **OS** 設定) 時，才支援 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b47d2-209">Only Microsoft Edge is supported if your device's OS configuration is Server (**cmd** > **Systeminfo** > **OS Configuration**).</span></span> <span data-ttu-id="b47d2-210">網路保護只支援在伺服器裝置上的 [檢查] 模式，其負責保護支援的協力廠商瀏覽器之間的流量。</span><span class="sxs-lookup"><span data-stu-id="b47d2-210">Network Protection is only supported in Inspect mode on Server devices, which is responsible for securing traffic across supported 3rd party browsers.</span></span>

- <span data-ttu-id="b47d2-211">未指派的裝置會在報告中顯示不正確的資料。</span><span class="sxs-lookup"><span data-stu-id="b47d2-211">Unassigned devices will have incorrect data shown within the report.</span></span> <span data-ttu-id="b47d2-212">在 [**報告詳細**  >  資料]**設備群組** 中，您可能會看到 [列有空白的裝置群組] 欄位。</span><span class="sxs-lookup"><span data-stu-id="b47d2-212">In the **Report details** > **Device groups** pivot, you might see a row with a blank Device Group field.</span></span> <span data-ttu-id="b47d2-213">在進入指定群組之前，此群組包含未指派的裝置。</span><span class="sxs-lookup"><span data-stu-id="b47d2-213">This group contains your unassigned devices before they get put into your specified group.</span></span> <span data-ttu-id="b47d2-214">此列的報表可能不包含正確的裝置或存取計數。</span><span class="sxs-lookup"><span data-stu-id="b47d2-214">The report for this row might not contain an accurate count of devices or access counts.</span></span>

- <span data-ttu-id="b47d2-215">「Web 內容篩選」報告目前僅限於顯示前5000記錄。</span><span class="sxs-lookup"><span data-stu-id="b47d2-215">Web Content Filtering reports are currently limited to showing the top 5000 records.</span></span> <span data-ttu-id="b47d2-216">例如，[網域] 報告只會針對指定的篩選器查詢顯示最上層的5000網域（如果適用）。</span><span class="sxs-lookup"><span data-stu-id="b47d2-216">For example, the Domains report will only show a maximum of the top 5000 domains for a given filter query, if applicable.</span></span> 


