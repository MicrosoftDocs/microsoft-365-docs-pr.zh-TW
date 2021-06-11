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
ms.openlocfilehash: 63ae9f8c1136a973e4fccb63ecfbaee2639c3f6f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904077"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="8ba30-104">將 microsoft defender 用於 Office 365 搭配 microsoft defender for Endpoint 使用</span><span class="sxs-lookup"><span data-stu-id="8ba30-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8ba30-105">[microsoft defender for Office 365](defender-for-office-365.md)可以設定為搭配[Microsoft defender for Endpoint](/windows/security/threat-protection)使用。</span><span class="sxs-lookup"><span data-stu-id="8ba30-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="8ba30-106">整合 microsoft defender for Office 365 與 microsoft defender for Endpoint 可協助您的安全性運作小組監視，並在使用者的裝置面臨危險時快速採取行動。</span><span class="sxs-lookup"><span data-stu-id="8ba30-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="8ba30-107">例如，啟用整合後，您的安全性作業小組將能夠查看偵測到的電子郵件訊息可能影響的裝置，以及為 Microsoft Defender for Endpoint 中的裝置產生多少最近的提醒。</span><span class="sxs-lookup"><span data-stu-id="8ba30-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="8ba30-108">下圖說明當您已啟用 Microsoft Defender 端點整合時，[ **裝置** ] 索引標籤的外觀。</span><span class="sxs-lookup"><span data-stu-id="8ba30-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![啟用 Microsoft Defender for Endpoint 時，您可以看到具有警示的裝置清單。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="8ba30-110">在此範例中，您可以看到偵測到之電子郵件的收件者有四個裝置，一個有警示。</span><span class="sxs-lookup"><span data-stu-id="8ba30-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="8ba30-111">按一下裝置的連結會在[Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (中開啟其頁面（先前為 Microsoft Defender 資訊安全中心) ）。</span><span class="sxs-lookup"><span data-stu-id="8ba30-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="8ba30-112">Microsoft 365 Defender 入口網站會取代 Microsoft Defender 資訊安全中心。</span><span class="sxs-lookup"><span data-stu-id="8ba30-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="8ba30-113">[Microsoft 365 defender 中，請參閱 Microsoft defender for Endpoint](../defender/microsoft-365-security-center-mde.md)。</span><span class="sxs-lookup"><span data-stu-id="8ba30-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="8ba30-114">需求</span><span class="sxs-lookup"><span data-stu-id="8ba30-114">Requirements</span></span>

- <span data-ttu-id="8ba30-115">您的組織必須具有 Microsoft defender Office 365 (或 Office 365 E5) 和 Microsoft defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="8ba30-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="8ba30-116">您必須是全域系統管理員，或具有安全性系統管理員角色 (例如 Microsoft 365 中指派的安全性系統管理員) 。</span><span class="sxs-lookup"><span data-stu-id="8ba30-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="8ba30-117"> (參閱 [安全性 & 規範中心的許可權](permissions-in-the-security-and-compliance-center.md)) </span><span class="sxs-lookup"><span data-stu-id="8ba30-117">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="8ba30-118">您必須可以存取 [Explorer (或即時偵測) ](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="8ba30-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="8ba30-119">若要將 microsoft defender 用於 Office 365 與 microsoft defender for Endpoint 整合</span><span class="sxs-lookup"><span data-stu-id="8ba30-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="8ba30-120">整合 microsoft defender for Office 365 搭配 microsoft defender for endpoint 是在 defender for endpoint 和 defender for Office 365 中設定。</span><span class="sxs-lookup"><span data-stu-id="8ba30-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="8ba30-121">以全域管理員或安全性管理員為單位，請移至 [https://protection.office.com](https://protection.office.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="8ba30-121">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="8ba30-122"> (這會帶您前往 Office 365 安全性 & 規範中心。 ) </span><span class="sxs-lookup"><span data-stu-id="8ba30-122">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="8ba30-123">在功能窗格中，選擇 [ **威脅管理** \> **瀏覽器**]。</span><span class="sxs-lookup"><span data-stu-id="8ba30-123">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![威脅管理功能表中的 Explorer](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="8ba30-125">在螢幕右上角，選擇 [ **Defender For Endpoint 設定 (MDE 設定)**]。</span><span class="sxs-lookup"><span data-stu-id="8ba30-125">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="8ba30-126">在 [microsoft defender for endpoint connection] 對話方塊中，開啟 [microsoft defender for endpoint] 的 **連線**。</span><span class="sxs-lookup"><span data-stu-id="8ba30-126">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Microsoft Defender for Endpoint connection](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="8ba30-128">移至 Microsoft 365 Defender 入口網站 ([https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="8ba30-128">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="8ba30-129">在導覽列中，選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="8ba30-129">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="8ba30-130">然後，在 **[一般**] 下，選擇 [ **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="8ba30-130">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="8ba30-131">向下滾動至 **Office 365 威脅情報**]，然後開啟連線。</span><span class="sxs-lookup"><span data-stu-id="8ba30-131">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 威脅智慧連接](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="8ba30-133">相關文章</span><span class="sxs-lookup"><span data-stu-id="8ba30-133">Related articles</span></span>

[<span data-ttu-id="8ba30-134">Office 365 中的威脅調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="8ba30-134">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="8ba30-135">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8ba30-135">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="8ba30-136">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8ba30-136">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
