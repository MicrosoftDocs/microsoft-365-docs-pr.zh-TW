---
title: Microsoft 365 已告知網路路由
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/10/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 已告知網路路由
ms.openlocfilehash: 5275f8ea55afaf621555b440e7fae4a6d11cad91
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717587"
---
# <a name="microsoft-365-informed-network-routing-preview"></a><span data-ttu-id="db658-103">Microsoft 365 已 (預覽告知網路路由) </span><span class="sxs-lookup"><span data-stu-id="db658-103">Microsoft 365 informed network routing (preview)</span></span>

<span data-ttu-id="db658-104">已通知網路路由是一項功能，可整合各種 Microsoft 365 應用程式與協力廠商軟體定義的網路 (SD-WAN) 解決方案，以優化和提升 Microsoft 服務端點的網路連線能力。</span><span class="sxs-lookup"><span data-stu-id="db658-104">Informed network routing is a feature that integrates various Microsoft 365 applications with third party software defined network (SD-WAN) solutions in order to optimize and improve your network connectivity to Microsoft service endpoints.</span></span> <span data-ttu-id="db658-105">優化的 SD-WAN 連線可能會導致使用者體驗和效能提高。</span><span class="sxs-lookup"><span data-stu-id="db658-105">Optimized SD-WAN connectivity may result in improved user experiences and performance.</span></span>

>[!IMPORTANT]
><span data-ttu-id="db658-106">Microsoft 365 已告知網路路由目前處於預覽狀態。</span><span class="sxs-lookup"><span data-stu-id="db658-106">Microsoft 365 informed network routing is currently in preview status.</span></span> <span data-ttu-id="db658-107">如需此預覽的詳細資訊，包括接收協助的指引，請參閱 [Microsoft 365 已通知的網路路由公開預覽](https://go.microsoft.com/fwlink/?linkid=2151565)。</span><span class="sxs-lookup"><span data-stu-id="db658-107">For more information on this preview including guidance for receiving assistance, see [Microsoft 365 informed network routing Public Preview](https://go.microsoft.com/fwlink/?linkid=2151565).</span></span>

## <a name="overview"></a><span data-ttu-id="db658-108">概觀</span><span class="sxs-lookup"><span data-stu-id="db658-108">Overview</span></span>

<span data-ttu-id="db658-109">已獲悉網路路由會在 Microsoft 與您的 SD-WAN 解決方案之間提供雙向資料共用通道。</span><span class="sxs-lookup"><span data-stu-id="db658-109">Informed network routing provides a bi-directional data sharing channel between Microsoft and your SD-WAN solution.</span></span> <span data-ttu-id="db658-110">針對您設定的每個辦公室位置和網際網路電路，Microsoft 會定期與 SD-WAN 解決方案共用意見反應，以供每個特定網際網路電路相關聯之網路流量所選取之 Microsoft 365 應用程式的品質。</span><span class="sxs-lookup"><span data-stu-id="db658-110">For every office location and Internet circuit that you configure, Microsoft periodically shares feedback with the SD-WAN solution on the quality of selected Microsoft 365 application experiences for network traffic associated with each specific Internet circuit.</span></span> <span data-ttu-id="db658-111">使用此意見反應，SD-WAN 方案可以透過透過其他可用連結路由傳送 Microsoft 365 應用程式流量來採取智慧復原動作。</span><span class="sxs-lookup"><span data-stu-id="db658-111">Using this feedback, the SD-WAN solution may then take smart recovery actions by routing Microsoft 365 application traffic through alternate available links.</span></span> 

<span data-ttu-id="db658-112">特定網際網路電路（如增加延遲或高封包遺失）路徑中的服務品質到很難定期偵測到。</span><span class="sxs-lookup"><span data-stu-id="db658-112">Quality of service degradations in the path of a particular Internet circuit such as increased latency or high packet loss are difficult to detect on a continuous basis.</span></span> <span data-ttu-id="db658-113">這些到對 Exchange Online、SharePoint、OneDrive 和 Microsoft 小組等應用程式的使用者體驗可能會造成不利的損害。</span><span class="sxs-lookup"><span data-stu-id="db658-113">These degradations may be detrimental to user experiences for applications such as Exchange Online, SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="db658-114">常見的情況包括對 Exchange 內容的搜尋速度很慢、在與 SharePoint 或 OneDrive 文件庫互動時，或在 Microsoft 小組中與通話或會議品質不良。</span><span class="sxs-lookup"><span data-stu-id="db658-114">Common symptoms include slow search of Exchange content, high transfer times when interacting with SharePoint or OneDrive document libraries, or poor call or meeting quality in Microsoft Teams.</span></span>

<span data-ttu-id="db658-115">網路中的意見反應和復原機制，已通知路由搜尋會動態偵測這類問題，並通知部署的 SD-WAN 解決方案採取自動復原動作。</span><span class="sxs-lookup"><span data-stu-id="db658-115">The feedback and recovery mechanism within network informed routing seeks to dynamically detect such issues in near real time and informs the deployed SD-WAN solution to take automatic recovery actions.</span></span>

<span data-ttu-id="db658-116">資料共用通道也可用於定期接收來自 SD-WAN 解決方案的網路層級光學資料，包括與裝置及連接電路相關聯的設定資訊和使用統計資料。</span><span class="sxs-lookup"><span data-stu-id="db658-116">The data sharing channel is also used to periodically receive network-level optics data from the SD-WAN solution, including configuration information and usage statistics associated with the device and attached circuits.</span></span> <span data-ttu-id="db658-117">不會收集或儲存任何個人資訊。</span><span class="sxs-lookup"><span data-stu-id="db658-117">No personal information is collected or stored.</span></span> <span data-ttu-id="db658-118">所有收集的資訊都會匯總到辦公室位置和連線的網際網路電路。</span><span class="sxs-lookup"><span data-stu-id="db658-118">All collected information is aggregated to office locations and connected Internet circuits.</span></span> <span data-ttu-id="db658-119">這項資訊可協助 Microsoft 使用 Microsoft 365 服務和應用程式，更有效率地解決已報告的問題。</span><span class="sxs-lookup"><span data-stu-id="db658-119">This information can help Microsoft more efficiently and effectively resolve reported issues with your use of Microsoft 365 services and applications.</span></span>

>[!NOTE]
><span data-ttu-id="db658-120">Microsoft 365 已通知網路路由支援 WW 商業雲端中的承租人，但不支援 GCC 中、GCC 高、DoD、德國或中國雲彩。</span><span class="sxs-lookup"><span data-stu-id="db658-120">Microsoft 365 informed network routing supports tenants in WW Commercial cloud but not the GCC Moderate, GCC High, DoD, Germany, or China clouds.</span></span>

## <a name="requirements"></a><span data-ttu-id="db658-121">需求</span><span class="sxs-lookup"><span data-stu-id="db658-121">Requirements</span></span>

### <a name="integrated-sd-wan-solutions"></a><span data-ttu-id="db658-122">整合的 SD-WAN 解決方案</span><span class="sxs-lookup"><span data-stu-id="db658-122">Integrated SD-WAN solutions</span></span>

<span data-ttu-id="db658-123">Microsoft 正與不同的合作夥伴合作，以啟用與 Microsoft 365 的網路路由通知的整合。</span><span class="sxs-lookup"><span data-stu-id="db658-123">Microsoft is working with various partners to enable integration with Microsoft 365 informed network routing.</span></span> <span data-ttu-id="db658-124">目前啟用的解決方案包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="db658-124">Currently enabled solutions include the following:</span></span>

| <span data-ttu-id="db658-125">Device Maker</span><span class="sxs-lookup"><span data-stu-id="db658-125">Device Maker</span></span> | <span data-ttu-id="db658-126">方案名稱</span><span class="sxs-lookup"><span data-stu-id="db658-126">Solution Name</span></span> | <span data-ttu-id="db658-127">最低版本</span><span class="sxs-lookup"><span data-stu-id="db658-127">Minimum Version</span></span> |
| --- | --- | --- |
| <span data-ttu-id="db658-128">Cisco</span><span class="sxs-lookup"><span data-stu-id="db658-128">Cisco</span></span> | [<span data-ttu-id="db658-129">IOS XE SD-WAN</span><span class="sxs-lookup"><span data-stu-id="db658-129">IOS XE SD-WAN</span></span>](https://go.microsoft.com/fwlink/?linkid=2151460) | <span data-ttu-id="db658-130">20.4/17.4</span><span class="sxs-lookup"><span data-stu-id="db658-130">20.4/17.4</span></span> |

### <a name="network-topology"></a><span data-ttu-id="db658-131">網路拓撲</span><span class="sxs-lookup"><span data-stu-id="db658-131">Network topology</span></span>

<span data-ttu-id="db658-132">已告知網路路由根據用來將網路流量傳送給 Microsoft 的公用 IP 位址，來識別與特定 office 位置和網際網路電路相關聯的流量。</span><span class="sxs-lookup"><span data-stu-id="db658-132">Informed network routing currently identifies traffic associated with a specific office location and Internet circuit based on the public IP address used to send network traffic to Microsoft.</span></span> 

<span data-ttu-id="db658-133">如果在分支地點沒有至少一部網路電路提供直接網際網路存取的情況下，網路傳送可能無法提供重要的價值。</span><span class="sxs-lookup"><span data-stu-id="db658-133">In the case where there is not at least one network circuit providing direct Internet access at a branch location, network informed routing may not provide significant value.</span></span>

### <a name="application-usage"></a><span data-ttu-id="db658-134">應用程式使用</span><span class="sxs-lookup"><span data-stu-id="db658-134">Application usage</span></span>

<span data-ttu-id="db658-135">透過透過特定 Microsoft 用戶端應用程式的使用來收集透過網路品質計量) 所反映的應用程式經驗資料 (。</span><span class="sxs-lookup"><span data-stu-id="db658-135">Application experience data (reflected through network quality metrics) is collected through usage of specific Microsoft client applications.</span></span> <span data-ttu-id="db658-136">Exchange 度量會反映 Outlook 用戶端的使用方式，以及一些 Outlook Web App 的使用方式。</span><span class="sxs-lookup"><span data-stu-id="db658-136">Exchange metrics reflect usage of the Outlook client as well as some Outlook Web App usage.</span></span> <span data-ttu-id="db658-137">SharePoint 和 OneDrive 度量會反映租使用者特定 SharePoint 端點的使用方式，不論用戶端應用程式為何。</span><span class="sxs-lookup"><span data-stu-id="db658-137">SharePoint and OneDrive metrics reflect usage of the tenant-specific SharePoint endpoints, regardless of client application.</span></span> <span data-ttu-id="db658-138">小組度量會反映小組桌面用戶端的使用狀況。</span><span class="sxs-lookup"><span data-stu-id="db658-138">Teams metrics reflect usage of the Teams desktop client.</span></span> <span data-ttu-id="db658-139">評估網路電路的健康情況時，並不會考慮其他應用程式流量。</span><span class="sxs-lookup"><span data-stu-id="db658-139">Other application traffic is not considered when evaluating the health of a network circuit.</span></span>

## <a name="enabling-informed-network-routing"></a><span data-ttu-id="db658-140">啟用已通知的網路路由</span><span class="sxs-lookup"><span data-stu-id="db658-140">Enabling informed network routing</span></span>

<span data-ttu-id="db658-141">啟用已通知的網路路由需要多個步驟，有些步驟則必須在 SD-WAN 解決方案的設定介面內執行。</span><span class="sxs-lookup"><span data-stu-id="db658-141">Enabling informed network routing requires multiple steps, some of which will need to be performed within the configuration interface of your SD-WAN solution.</span></span> <span data-ttu-id="db658-142">請諮詢您的 SD-WAN 解決方案廠商，以取得如何在使用 Microsoft 365 系統管理中心進行設定之前，啟動在 SD-WAN 解決方案內啟用網路通知之程式的指導方針。</span><span class="sxs-lookup"><span data-stu-id="db658-142">Consult your SD-WAN solution vendor for guidance on how to initiate the process of enabling network informed routing within the SD-WAN solution before proceeding with configuration in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="db658-143">當您準備好在 Microsoft 365 系統管理中心中啟用已通知的網路路由功能之後，請確定您具備必要的全域系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="db658-143">Once you are ready to enable informed network routing in the Microsoft 365 admin center, ensure you have the necessary global administrator permissions.</span></span>

>[!IMPORTANT]
><span data-ttu-id="db658-144">為了提供所選 SD-WAN 解決方案所需的承租人層級應用程式許可權，以存取已通知的網路路由資料共用通道，您必須以全域系統管理員身分執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="db658-144">In order to provide the necessary tenant-level applications permissions consent for the selected SD-WAN solution to access the informed network routing data sharing channel, you must perform the following steps as a global administrator.</span></span>


### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="db658-145">步驟1：開啟 SD-WAN 方案設定選項</span><span class="sxs-lookup"><span data-stu-id="db658-145">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="db658-146">在 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)的左側流覽窗格中，選取 [ **健康 > 網路** 連線]。</span><span class="sxs-lookup"><span data-stu-id="db658-146">In the [Microsoft 365 admin center](https://admin.microsoft.com/), select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="db658-147">本章節為您的組織提供匯總的網路連線度量，以及如何改善連線的指導方針。</span><span class="sxs-lookup"><span data-stu-id="db658-147">This section of the admin center provides aggregated network connectivity metrics for your organization and guidance on how to improve your connectivity.</span></span> <span data-ttu-id="db658-148">請參閱 [Microsoft 365 系統管理中心的網路連線 (預覽) ](office-365-network-mac-perf-overview.md) ，以取得系統管理中心內可用之功能的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="db658-148">See [Network connectivity in the Microsoft 365 Admin Center (preview)](office-365-network-mac-perf-overview.md) for additional information on these features available within the admin center.</span></span>

<span data-ttu-id="db658-149">選取 [ **設定] > SD-WAN 解決方案** ] 以開啟 [已通知的網路路由設定] 窗格。</span><span class="sxs-lookup"><span data-stu-id="db658-149">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span> <span data-ttu-id="db658-150">[ **設定** ] 底下顯示的其他選項適用于系統管理中心的一般網路連線指導方針，而且不需要啟用已通知的網路路由。</span><span class="sxs-lookup"><span data-stu-id="db658-150">The other options that appear under **Settings** are applicable to the general network connectivity guidance in the admin center and are not required to enable informed network routing.</span></span>

<span data-ttu-id="db658-151">在 [設定] 窗格中，選取 [ **新增您的 SD-WAN 方案 (Preview)**]。</span><span class="sxs-lookup"><span data-stu-id="db658-151">In the configuration pane, select **Add your SD-WAN solution (Preview)**.</span></span>

### <a name="step-2-select-your-sd-wan-solution-and-data-storage-location"></a><span data-ttu-id="db658-152">步驟2：選取您的 SD-WAN 方案和資料儲存位置</span><span class="sxs-lookup"><span data-stu-id="db658-152">Step 2: Select your SD-WAN solution and data storage location</span></span>

<span data-ttu-id="db658-153">在下拉式方塊中，選取您已部署的 SD-WAN 方案，以及您想要將其相關聯的資料儲存在網路上的位置。</span><span class="sxs-lookup"><span data-stu-id="db658-153">In the drop-down boxes, select the SD-WAN solution you have deployed and the location where you wish to have the data associated with network informed routing stored.</span></span> <span data-ttu-id="db658-154">如需詳細資訊，請參閱 [資料存放區](#data-storage) 一節。</span><span class="sxs-lookup"><span data-stu-id="db658-154">See the [data storage](#data-storage) section for additional information.</span></span>

<span data-ttu-id="db658-155">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="db658-155">Select **Next**.</span></span>

### <a name="step-3-accept-terms-for-sharing-of-data"></a><span data-ttu-id="db658-156">步驟3：接受共用資料的字詞</span><span class="sxs-lookup"><span data-stu-id="db658-156">Step 3: Accept terms for sharing of data</span></span>

<span data-ttu-id="db658-157">請仔細閱讀並認可與在 Microsoft 和您所選的 SD-WAN 方案中共用資料相關聯的提供字詞，然後選取指出的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="db658-157">Carefully read and acknowledge the provided terms associated with sharing data between Microsoft and your selected SD-WAN solution, and then select the indicated checkbox.</span></span>

<span data-ttu-id="db658-158">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="db658-158">Select **Next**.</span></span>

### <a name="step-4-grant-permissions-to-the-sd-wan-solution"></a><span data-ttu-id="db658-159">步驟4：將許可權授與 SD-WAN 方案</span><span class="sxs-lookup"><span data-stu-id="db658-159">Step 4: Grant permissions to the SD-WAN solution</span></span>

<span data-ttu-id="db658-160">這個步驟將會啟動使用 Azure Active Directory (Azure AD) 的許可權授與要求。</span><span class="sxs-lookup"><span data-stu-id="db658-160">This step will initiate a permissions grant request with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="db658-161">您將會被要求授與承租人層級的許可權，允許您選取的 SD-WAN 方案存取已通知的網路路由資料存放區，以及與租使用者相關聯的服務健康情況資訊。</span><span class="sxs-lookup"><span data-stu-id="db658-161">You will be requested to grant tenant-level permissions that allow your selected SD-WAN solution access to the informed network routing data storage and the service health information associated with your tenant.</span></span> <span data-ttu-id="db658-162">此動作需要全域系統管理員角色許可權。</span><span class="sxs-lookup"><span data-stu-id="db658-162">This action requires global administrator role permissions.</span></span>

<span data-ttu-id="db658-163">選取 [ **授與此應用程式的許可權** ] 連結，並遵循 Azure AD 要求。</span><span class="sxs-lookup"><span data-stu-id="db658-163">Select the **Give permission to this application** link and follow the Azure AD requests.</span></span>

<span data-ttu-id="db658-164">當您完成許可權授與後，請選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="db658-164">Once you have completed the permissions grant, select **Next**.</span></span>

### <a name="step-5-confirm-your-configuration-settings"></a><span data-ttu-id="db658-165">步驟5：確認您的設定設定</span><span class="sxs-lookup"><span data-stu-id="db658-165">Step 5: Confirm your configuration settings</span></span>

<span data-ttu-id="db658-166">為您的租使用者啟用網路通知之路由的最後一個步驟是確認頁面，顯示您所提供的設定。</span><span class="sxs-lookup"><span data-stu-id="db658-166">The final step in enabling network informed routing for your tenant is a confirmation page that displays the settings you've provided.</span></span> 

<span data-ttu-id="db658-167">現在已為您的租使用者啟用已通知的網路路由。</span><span class="sxs-lookup"><span data-stu-id="db658-167">Informed network routing is now enabled for your tenant.</span></span>

<span data-ttu-id="db658-168">選取 [ **完成** ]，然後關閉 [SD-WAN 方案設定] 窗格。</span><span class="sxs-lookup"><span data-stu-id="db658-168">Select **Done** and then close the SD-WAN solution configuration pane.</span></span>

## <a name="configuring-network-informed-routing"></a><span data-ttu-id="db658-169">設定網路通知的路由</span><span class="sxs-lookup"><span data-stu-id="db658-169">Configuring network informed routing</span></span>

<span data-ttu-id="db658-170">您將在 SD-WAN 解決方案內，針對已通知的網路路由執行許多設定，例如設定如何在正常情況下路由傳送流量，以及在偵測到問題時，應使用的替代路徑。</span><span class="sxs-lookup"><span data-stu-id="db658-170">You will perform much of the configuration for informed network routing within your SD-WAN solution, such as configuring how your traffic should be routed under normal circumstances and the alternate paths that should be used if issues are detected.</span></span> <span data-ttu-id="db658-171">如需這些設定步驟的詳細資訊，請參閱您的 SD-WAN 解決方案提供者。</span><span class="sxs-lookup"><span data-stu-id="db658-171">Consult your SD-WAN solution provider for details on these configuration steps.</span></span>

<span data-ttu-id="db658-172">每個辦公室位置都必須在 Microsoft 365 系統管理中心中設定，以告知網路路由可正確識別與網路線路相關聯的流量，以提供與這些位置的連線能力。</span><span class="sxs-lookup"><span data-stu-id="db658-172">Each office location must be configured in the Microsoft 365 admin center so that informed network routing can properly identify traffic associated with the network circuits providing connectivity to these locations.</span></span>

<span data-ttu-id="db658-173">在 Microsoft 正在進行的網路遙測集合中，可能會自動偵測到 Office 位置。</span><span class="sxs-lookup"><span data-stu-id="db658-173">Office locations may be auto-detected as part of Microsoft's ongoing collection of network telemetry.</span></span> <span data-ttu-id="db658-174">因此，有些位置可能會預先填入租使用者的系統管理員中心。</span><span class="sxs-lookup"><span data-stu-id="db658-174">As a result, some locations may be pre-populated in the admin center for your tenant.</span></span> 

<span data-ttu-id="db658-175">如果這些位置是正確的，您只需要為每個必要的位置啟用已通知的網路路由功能，並設定網際網路電路及其公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="db658-175">If these locations are accurate, you will simply need to enable the informed network routing feature for each desired location and configure the Internet circuits and their public IP addresses.</span></span> 

<span data-ttu-id="db658-176">如果自動偵測位置不正確，或您的租使用者中沒有預先填入的位置，您必須手動新增或編輯位置，以反映組織的準確拓撲。</span><span class="sxs-lookup"><span data-stu-id="db658-176">If the auto-detected locations are not accurate, or there are no locations pre-populated in your tenant, you will have to add or edit locations manually to reflect an accurate topology of your organization.</span></span>

### <a name="updating-locations"></a><span data-ttu-id="db658-177">更新位置</span><span class="sxs-lookup"><span data-stu-id="db658-177">Updating locations</span></span>

<span data-ttu-id="db658-178">您租使用者的位置可在 [ **位置** ] 索引標籤下找到。位置可以直接在清單中編輯，或使用 CSV 檔案更新。</span><span class="sxs-lookup"><span data-stu-id="db658-178">Locations for your tenant can be found under the **Locations** tab. Locations may be edited directly in the list or updated using a CSV file.</span></span>

<span data-ttu-id="db658-179">確定您想要啟用通知網路路由的每個辦公室位置都存在於此清單中。</span><span class="sxs-lookup"><span data-stu-id="db658-179">Ensure that each office location where you wish to enable informed network routing is present in this list.</span></span>

>[!NOTE]
><span data-ttu-id="db658-180">收集樣本及其他評估相關資訊的 [ **位置** ] 清單中的欄與已通知的網路路由功能並不相關。</span><span class="sxs-lookup"><span data-stu-id="db658-180">The columns in the **Locations** list for samples collected and other assessment-related information are not related to the informed network routing feature.</span></span>

### <a name="enabling-a-location-for-informed-network-routing"></a><span data-ttu-id="db658-181">啟用通知網路路由的位置</span><span class="sxs-lookup"><span data-stu-id="db658-181">Enabling a location for informed network routing</span></span>

1. <span data-ttu-id="db658-182">在 [ **位置** ] 清單中，從 [快速動作] 功能表中選取 [ **編輯** ]，以開啟 [位置設定] 窗格。</span><span class="sxs-lookup"><span data-stu-id="db658-182">In the **Locations** list, select **Edit** from the quick actions menu to open the location configuration pane.</span></span>

2. <span data-ttu-id="db658-183">選取 [ **使用 Microsoft 365 告知網路路由的位置**]。</span><span class="sxs-lookup"><span data-stu-id="db658-183">Select **Use Microsoft 365 informed network routing at this location**.</span></span>

3. <span data-ttu-id="db658-184">在 **此辦公室位置的 [出局 IP 位址範圍** ] 區段中，新增所有可提供網際網路連線到此 office 位置的網路電路。</span><span class="sxs-lookup"><span data-stu-id="db658-184">Add all network circuits providing Internet connectivity to this office location in the **Egress IP Address ranges at this office location** section.</span></span> <span data-ttu-id="db658-185">確定每個電路都與代表網路流量的唯一公用 IP 位址子網相關聯。</span><span class="sxs-lookup"><span data-stu-id="db658-185">Ensure that each circuit is associated with the unique public IP address subnets representing your network traffic.</span></span>

4. <span data-ttu-id="db658-186">選取 [儲存 **]** 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="db658-186">Select **Save** to save your changes.</span></span>

## <a name="disabling-network-informed-routing"></a><span data-ttu-id="db658-187">停用網路通知路由</span><span class="sxs-lookup"><span data-stu-id="db658-187">Disabling network informed routing</span></span>

<span data-ttu-id="db658-188">您可以透過重設 SD-WAN 方案設定，對整個租使用者停用已通知的網路路由功能。</span><span class="sxs-lookup"><span data-stu-id="db658-188">The informed network routing feature may be disabled for the entire tenant by resetting your SD-WAN solution settings.</span></span> <span data-ttu-id="db658-189">雖然這會停止所有在 Microsoft 365 中處理的資料，您也應停用系統管理中心內網路通知的路由傳送。</span><span class="sxs-lookup"><span data-stu-id="db658-189">While this will stop all processing of data within Microsoft 365, you should also disable network informed routing within the admin center.</span></span>

### <a name="step-1-open-sd-wan-solution-configuration-options"></a><span data-ttu-id="db658-190">步驟1：開啟 SD-WAN 方案設定選項</span><span class="sxs-lookup"><span data-stu-id="db658-190">Step 1: Open SD-WAN solution configuration options</span></span>

<span data-ttu-id="db658-191">在 [Microsoft 365 系統管理中心](https://admin.microsoft.com/) 中，選取左導覽窗格中的 [ **健康情況 > 網路連線能力** 。</span><span class="sxs-lookup"><span data-stu-id="db658-191">In the [Microsoft 365 admin center](https://admin.microsoft.com/) select **Health > Network connectivity** in the left-hand navigation pane.</span></span>

<span data-ttu-id="db658-192">選取 [ **設定] > SD-WAN 解決方案** ] 以開啟 [已通知的網路路由設定] 窗格。</span><span class="sxs-lookup"><span data-stu-id="db658-192">Select **Settings > SD-WAN solution** to open the informed network routing configuration pane.</span></span>

<span data-ttu-id="db658-193">設定窗格會顯示您目前設定的 SD-WAN 解決方案摘要。</span><span class="sxs-lookup"><span data-stu-id="db658-193">The configuration pane shows a summary of your currently configured SD-WAN solution.</span></span>

### <a name="step-2-reset-your-configuration"></a><span data-ttu-id="db658-194">步驟2：重設您的設定</span><span class="sxs-lookup"><span data-stu-id="db658-194">Step 2: Reset your configuration</span></span>

<span data-ttu-id="db658-195">在 [設定] 窗格中，選取 [ **重設您的 SD-WAN 方案設定**]。</span><span class="sxs-lookup"><span data-stu-id="db658-195">In the configuration pane, select **Reset your SD-WAN solution settings**.</span></span>

<span data-ttu-id="db658-196">您的設定現在已重設，且已停用網路路由通知。</span><span class="sxs-lookup"><span data-stu-id="db658-196">Your settings have now been reset and informed network routing has been disabled.</span></span> <span data-ttu-id="db658-197">您可以隨時依照 [啟用已告知網路路由](#enabling-informed-network-routing)的步驟，隨時重新啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="db658-197">You can re-enable it at any time by following the steps in [Enabling informed network routing](#enabling-informed-network-routing).</span></span>

## <a name="data-storage"></a><span data-ttu-id="db658-198">資料儲存</span><span class="sxs-lookup"><span data-stu-id="db658-198">Data storage</span></span>

<span data-ttu-id="db658-199">在 Microsoft 與 SD-WAN 解決方案提供者之間交換的資料會儲存在初次啟用網路通知的位置時選取的資料儲存位置。</span><span class="sxs-lookup"><span data-stu-id="db658-199">Data exchanged between Microsoft and the SD-WAN solution provider is stored in the data storage location selected during the initial enablement of network informed routing.</span></span> <span data-ttu-id="db658-200">資料儲存位置選項代表地理區域，其中包含儲存資料的 Microsoft Azure 地區。</span><span class="sxs-lookup"><span data-stu-id="db658-200">The data storage location options represent geographical areas containing Microsoft Azure regions where the data is stored.</span></span>

>[!NOTE]
><span data-ttu-id="db658-201">在預覽階段， **北美** 唯一可用的資料儲存位置。</span><span class="sxs-lookup"><span data-stu-id="db658-201">During the Preview phase, the only available data storage location is **North America**.</span></span> <span data-ttu-id="db658-202">在有通知的網路路由的一般可用性之前，將會提供額外的資料儲存位置。</span><span class="sxs-lookup"><span data-stu-id="db658-202">Additional data storage locations will become available prior to the general availability of informed network routing.</span></span>

<span data-ttu-id="db658-203">資料會保留在此位置，最多30天。</span><span class="sxs-lookup"><span data-stu-id="db658-203">Data is retained in this location for up to 30 days.</span></span> <span data-ttu-id="db658-204">停用時，會在此30天保留時段內移除所有剩餘的資料。</span><span class="sxs-lookup"><span data-stu-id="db658-204">When disabled, all remaining data is removed within this 30-day retention window.</span></span>

## <a name="related-topics"></a><span data-ttu-id="db658-205">相關主題</span><span class="sxs-lookup"><span data-stu-id="db658-205">Related topics</span></span>

[<span data-ttu-id="db658-206">Microsoft 365 系統管理中心的網路連線 (預覽) </span><span class="sxs-lookup"><span data-stu-id="db658-206">Network connectivity in the Microsoft 365 admin center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="db658-207">Microsoft 365 Network Connectivity Location 服務 (預覽) </span><span class="sxs-lookup"><span data-stu-id="db658-207">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)
