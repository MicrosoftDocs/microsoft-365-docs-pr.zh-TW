---
title: 將 microsoft defender 用於 Office 365 搭配 microsoft defender for Endpoint 使用
f1.keywords:
- NOCSH
keywords: 整合，Microsoft defender，Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 使用 microsoft defender for Office 365 搭配 microsoft defender for Endpoint，以取得對您的裝置和電子郵件內容的威脅相關的詳細資訊。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fed3a04a7a699b4689cd9d6d9d335a8ba51d2fd8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083376"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="53b15-104">將 microsoft defender 用於 Office 365 搭配 microsoft defender for Endpoint 使用</span><span class="sxs-lookup"><span data-stu-id="53b15-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="53b15-105">[microsoft defender for Office 365](defender-for-office-365.md)可以設定為搭配[Microsoft defender for Endpoint](/windows/security/threat-protection)使用。</span><span class="sxs-lookup"><span data-stu-id="53b15-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="53b15-106">整合 microsoft defender for Office 365 與 microsoft defender for Endpoint 可協助您的安全性運作小組監視，並在使用者的裝置面臨危險時快速採取行動。</span><span class="sxs-lookup"><span data-stu-id="53b15-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="53b15-107">例如，啟用整合後，您的安全性作業小組將能夠查看偵測到的電子郵件訊息可能影響的裝置，以及為 Microsoft Defender for Endpoint 中的裝置產生多少最近的提醒。</span><span class="sxs-lookup"><span data-stu-id="53b15-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="53b15-108">下圖說明當您已啟用 Microsoft Defender 端點整合時，[ **裝置** ] 索引標籤的外觀。</span><span class="sxs-lookup"><span data-stu-id="53b15-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![啟用 Microsoft Defender for Endpoint 時，您可以看到具有警示的裝置清單。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="53b15-110">在此範例中，您可以看到偵測到之電子郵件的收件者有四個裝置，一個有警示。</span><span class="sxs-lookup"><span data-stu-id="53b15-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="53b15-111">按一下裝置的連結會在[Microsoft 365 Defender 入口網站](../defender-endpoint/microsoft-defender-security-center.md)中開啟其頁面 (先前為 Microsoft Defender security center) 。</span><span class="sxs-lookup"><span data-stu-id="53b15-111">Clicking the link for a device opens its page in [the Microsoft 365 Defender portal](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender security center).</span></span>

> [!TIP]
> <span data-ttu-id="53b15-112">Microsoft 365 Defender 入口網站會取代 Microsoft Defender 資訊安全中心。</span><span class="sxs-lookup"><span data-stu-id="53b15-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="53b15-113">[在 Microsoft 365 Defender 中查看 Microsoft Defender For Endpoint](../defender/microsoft-365-security-center-mde.md)。</span><span class="sxs-lookup"><span data-stu-id="53b15-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="53b15-114">需求</span><span class="sxs-lookup"><span data-stu-id="53b15-114">Requirements</span></span>

- <span data-ttu-id="53b15-115">您的組織必須具有 Microsoft defender Office 365 (或 Office 365 E5) 和 Microsoft defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="53b15-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="53b15-116">您必須是全域系統管理員，或具有安全性系統管理員角色 (例如 Microsoft 365 中指派的安全性系統管理員) 。</span><span class="sxs-lookup"><span data-stu-id="53b15-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="53b15-117">如需詳細資訊，請參閱 [Microsoft 365 Defender 入口網站中的權限](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="53b15-117">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="53b15-118">您必須可以存取 [Explorer (或即時偵測) ](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="53b15-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="53b15-119">若要將 microsoft defender 用於 Office 365 與 microsoft defender for Endpoint 整合</span><span class="sxs-lookup"><span data-stu-id="53b15-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="53b15-120">整合 microsoft defender for Office 365 搭配 microsoft defender for endpoint 是在 defender for endpoint 和 defender for Office 365 中設定。</span><span class="sxs-lookup"><span data-stu-id="53b15-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="53b15-121">以全域管理員或安全性管理員的身分開啟 Microsoft 365 Defender 入口網站 (<https://security.microsoft.com>) 然後移至 **電子郵件 & 協同** \> **瀏覽器**。</span><span class="sxs-lookup"><span data-stu-id="53b15-121">As a global administrator or a security administrator, open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Email & collaboration** \> **Explorer**.</span></span> <span data-ttu-id="53b15-122">若要直接移至 **瀏覽器** 頁面，請使用 <https://security.microsoft.com/threatexplorer> 。</span><span class="sxs-lookup"><span data-stu-id="53b15-122">To go directly to the **Explorer** page, use <https://security.microsoft.com/threatexplorer>.</span></span>

2. <span data-ttu-id="53b15-123">在 [ **Explorer** ] 頁面上，按一下螢幕右上角的 [ **MDE 設定**]。</span><span class="sxs-lookup"><span data-stu-id="53b15-123">On the **Explorer** page, in the upper right corner of the screen, click **MDE Settings**.</span></span>

3. <span data-ttu-id="53b15-124">在出現的 [ **microsoft defender for endpoint connection** 浮出] 中，連線開啟) 上的 [microsoft **defender for endpoint** ] (![ 切換] ](../../media/scc-toggle-on.png) ，然後按一下 [關閉圖示] [ ![ ](../../media/m365-cc-sc-close-icon.png) **關閉**]。</span><span class="sxs-lookup"><span data-stu-id="53b15-124">In the **Microsoft Defender for Endpoint connection** flyout that appears, turn on **Connect to Microsoft Defender for Endpoint** (![Toggle on](../../media/scc-toggle-on.png)) and then click ![Close icon](../../media/m365-cc-sc-close-icon.png) **Close**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE 連接":::

4. <span data-ttu-id="53b15-126">回到功能窗格中，選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="53b15-126">Back in the navigation pane, choose **Settings**.</span></span> <span data-ttu-id="53b15-127">在 [**設定**] 頁面上，選擇 [**端點**]</span><span class="sxs-lookup"><span data-stu-id="53b15-127">On the **Settings** page, choose **Endpoints**</span></span>

5. <span data-ttu-id="53b15-128">在開啟的 [ **端點** ] 頁面上，選擇 [ **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="53b15-128">On the **Endpoints** page that opens, choose **Advanced features**.</span></span>

6. <span data-ttu-id="53b15-129">向下滾動至 **Office 365 威脅情報**]，然後在) 上 (切換開啟此介面 ![ ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="53b15-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn it on (![Toggle on](../../media/scc-toggle-on.png)).</span></span>

   <span data-ttu-id="53b15-130">完成後，按一下 [ **儲存喜好** 設定]。</span><span class="sxs-lookup"><span data-stu-id="53b15-130">When you're finished, click **Save preferences**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="53b15-131">相關文章</span><span class="sxs-lookup"><span data-stu-id="53b15-131">Related articles</span></span>

[<span data-ttu-id="53b15-132">Office 365 中的威脅調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="53b15-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="53b15-133">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="53b15-133">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="53b15-134">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="53b15-134">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
