---
title: 板載非 Windows 裝置至 Microsoft Defender for Endpoint service
description: 設定非 Windows 裝置，使其可將感應器資料傳送至 Microsoft Defender ATP 服務。
keywords: 板載非 Windows 裝置，macos，linux，裝置管理，設定 Windows ATP 裝置，設定 Microsoft Defender for Endpoint 裝置
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c292c57c179a832728b03a7fc94fb7085d3ea0ec
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166074"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="24a69-104">板載非 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="24a69-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="24a69-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="24a69-105">**Applies to:**</span></span>
- [<span data-ttu-id="24a69-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="24a69-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="24a69-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24a69-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="24a69-108">**平臺**</span><span class="sxs-lookup"><span data-stu-id="24a69-108">**Platforms**</span></span>
- <span data-ttu-id="24a69-109">macOS</span><span class="sxs-lookup"><span data-stu-id="24a69-109">macOS</span></span>
- <span data-ttu-id="24a69-110">Linux</span><span class="sxs-lookup"><span data-stu-id="24a69-110">Linux</span></span>

><span data-ttu-id="24a69-111">想要體驗 Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="24a69-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="24a69-112">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="24a69-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="24a69-113">Defender for Endpoint 提供 Windows 和非 Windows 平臺的集中式安全性作業體驗。</span><span class="sxs-lookup"><span data-stu-id="24a69-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="24a69-114">您可以在 Microsoft Defender Security Center 中查看不同支援作業系統 (OS) 中的警示，並更好地保護組織的網路。</span><span class="sxs-lookup"><span data-stu-id="24a69-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> 

<span data-ttu-id="24a69-115">您將需要知道與 distros 的 Defender for Endpoint 相容的確切 Linux 和 macOS 版本，以供整合運作。</span><span class="sxs-lookup"><span data-stu-id="24a69-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="24a69-116">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="24a69-116">For more information, see:</span></span>
- [<span data-ttu-id="24a69-117">適用于 Linux 系統需求的 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="24a69-117">Microsoft Defender for Endpoint for Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="24a69-118">[Mac 系統需求的 Microsoft Defender 端點](microsoft-defender-endpoint-mac.md#system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="24a69-118">[Microsoft Defender for Endpoint for Mac system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="24a69-119">上架非 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="24a69-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="24a69-120">您必須對板載非 Windows 裝置採取下列步驟：</span><span class="sxs-lookup"><span data-stu-id="24a69-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="24a69-121">選取您慣用的上架方式：</span><span class="sxs-lookup"><span data-stu-id="24a69-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="24a69-122">若為 macOS 裝置，您可以選擇透過 Microsoft Defender ATP 或透過協力廠商解決方案進行板載。</span><span class="sxs-lookup"><span data-stu-id="24a69-122">For macOS devices, you can choose to onboard through Microsoft Defender ATP or through a third-party solution.</span></span> <span data-ttu-id="24a69-123">如需詳細資訊，請參閱 [Microsoft Defender For Mac 的 Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)。</span><span class="sxs-lookup"><span data-stu-id="24a69-123">For more information, see [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).</span></span>
   - <span data-ttu-id="24a69-124">如果是其他非 Windows 裝置，請 **透過協力廠商整合選擇板載非 Windows 裝置**。</span><span class="sxs-lookup"><span data-stu-id="24a69-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
       
     1. <span data-ttu-id="24a69-125">在功能窗格中，選取 [**互通性**  >  **夥伴**]。</span><span class="sxs-lookup"><span data-stu-id="24a69-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="24a69-126">請確定已列出協力廠商解決方案。</span><span class="sxs-lookup"><span data-stu-id="24a69-126">Make sure the third-party solution is listed.</span></span>

        2. <span data-ttu-id="24a69-127">在 [ **夥伴應用程式** ] 索引標籤中，選取支援非 Windows 裝置的合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="24a69-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>

        3. <span data-ttu-id="24a69-128">選取 [ **開啟夥伴頁面** ] 以開啟夥伴的頁面。</span><span class="sxs-lookup"><span data-stu-id="24a69-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="24a69-129">依照頁面上提供的指示進行。</span><span class="sxs-lookup"><span data-stu-id="24a69-129">Follow the instructions provided on the page.</span></span>

        4. <span data-ttu-id="24a69-130">建立帳戶或訂閱夥伴解決方案之後，您應該會進入一個階段，您的組織中的承租人全域管理員要求接受來自夥伴應用程式的許可權要求。</span><span class="sxs-lookup"><span data-stu-id="24a69-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="24a69-131">請仔細閱讀許可權要求，確定它已與您所需的服務對齊。</span><span class="sxs-lookup"><span data-stu-id="24a69-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="24a69-132">遵循協力廠商解決方案的指示執行偵測測試。</span><span class="sxs-lookup"><span data-stu-id="24a69-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="24a69-133">下架非 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="24a69-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="24a69-134">遵循協力廠商的檔，以中斷協力廠商解決方案與 Microsoft Defender for Endpoint 的連線。</span><span class="sxs-lookup"><span data-stu-id="24a69-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="24a69-135">在您的 Azure AD 租使用者中移除協力廠商解決方案的許可權。</span><span class="sxs-lookup"><span data-stu-id="24a69-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="24a69-136">登入 [Azure 入口網站](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="24a69-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="24a69-137">選取 [ **Azure Active Directory > 企業應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="24a69-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="24a69-138">選取您想要下架的應用程式。</span><span class="sxs-lookup"><span data-stu-id="24a69-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="24a69-139">選取 [ **刪除** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="24a69-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="24a69-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="24a69-140">Related topics</span></span>
- [<span data-ttu-id="24a69-141">板載 Windows 10 裝置</span><span class="sxs-lookup"><span data-stu-id="24a69-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="24a69-142">上架伺服器</span><span class="sxs-lookup"><span data-stu-id="24a69-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="24a69-143">設定 proxy 和網際網路連線設定</span><span class="sxs-lookup"><span data-stu-id="24a69-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="24a69-144">疑難排解 Microsoft Defender 的端點上架問題</span><span class="sxs-lookup"><span data-stu-id="24a69-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
