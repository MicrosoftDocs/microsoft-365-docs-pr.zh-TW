---
title: 使用適用于 Office 365 的 Microsoft Defender 搭配 Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
keywords: 整合，Microsoft Defender，ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 搭配使用 Microsoft Defender for Office 365 與 Microsoft Defender for Endpoint，以取得對您的裝置和電子郵件內容的威脅相關的詳細資訊。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 035834e1e4855c0e47defed06043a5fdbd0e63bd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166084"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="05bb0-104">使用適用于 Office 365 的 Microsoft Defender 搭配 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="05bb0-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="05bb0-105">[Microsoft defender For Office 365](office-365-atp.md) 可以設定為搭配 [Microsoft defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection)使用。</span><span class="sxs-lookup"><span data-stu-id="05bb0-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="05bb0-106">整合 Microsoft Defender for Office 365 搭配 Microsoft Defender for Endpoint 可協助您的安全性運作小組監視並快速採取行動（如果使用者的裝置面臨危險）。</span><span class="sxs-lookup"><span data-stu-id="05bb0-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="05bb0-107">例如，啟用整合後，您的安全性作業小組將能夠查看偵測到的電子郵件訊息可能影響的裝置，以及為 Microsoft Defender for Endpoint 中的裝置產生多少最近的提醒。</span><span class="sxs-lookup"><span data-stu-id="05bb0-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="05bb0-108">下圖說明當您已啟用 Microsoft Defender 端點整合時，[ **裝置** ] 索引標籤的外觀。</span><span class="sxs-lookup"><span data-stu-id="05bb0-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![啟用 Microsoft Defender for Endpoint 時，您可以看到具有警示的裝置清單。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="05bb0-110">在此範例中，您可以看到偵測到之電子郵件的收件者有四個裝置，一個有警示。</span><span class="sxs-lookup"><span data-stu-id="05bb0-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="05bb0-111">按一下裝置的連結會在 Microsoft Defender Security Center () 中開啟其頁面 <https://securitycenter.windows.com> 。</span><span class="sxs-lookup"><span data-stu-id="05bb0-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="05bb0-112">**[深入瞭解 Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (也稱為「microsoft Defender for Endpoint 入口網站」。 ) </span><span class="sxs-lookup"><span data-stu-id="05bb0-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="05bb0-113">需求</span><span class="sxs-lookup"><span data-stu-id="05bb0-113">Requirements</span></span>

- <span data-ttu-id="05bb0-114">您的組織必須具有 Microsoft Defender for Office 365 (或 Office 365 E5) 和 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="05bb0-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="05bb0-115">您必須是全域系統管理員或具有安全性系統管理員角色 (例如，安全性系統管理員) 在 [安全性 & 合規性中心](https://protection.office.com)內指派。</span><span class="sxs-lookup"><span data-stu-id="05bb0-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="05bb0-116"> (參閱 [安全性 & 規範中心的許可權](permissions-in-the-security-and-compliance-center.md)) </span><span class="sxs-lookup"><span data-stu-id="05bb0-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="05bb0-117">您必須能夠存取 [Explorer (或即時偵測) ](threat-explorer.md) 在安全性 & 規範中心和 Microsoft Defender Security center 中。</span><span class="sxs-lookup"><span data-stu-id="05bb0-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="05bb0-118">整合 Microsoft Defender for Office 365 與 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="05bb0-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="05bb0-119">整合 Microsoft Defender for Office 365 與 Microsoft Defender for Endpoint 是透過安全性 & 規範中心和 Microsoft Defender Security Center 來設定。</span><span class="sxs-lookup"><span data-stu-id="05bb0-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="05bb0-120">以全域管理員或安全性管理員為單位，請移至 <https://protection.office.com> 並登入。</span><span class="sxs-lookup"><span data-stu-id="05bb0-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="05bb0-121"> (這會帶您前往 Office 365 安全性 & 相容性中心。 ) </span><span class="sxs-lookup"><span data-stu-id="05bb0-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="05bb0-122">在功能窗格中，選擇 [ **威脅管理** \> **瀏覽器**]。</span><span class="sxs-lookup"><span data-stu-id="05bb0-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![威脅管理功能表中的 Explorer](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="05bb0-124">在螢幕右上角，選擇 [ **(MDE 設定)** 的 [Defender]。</span><span class="sxs-lookup"><span data-stu-id="05bb0-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="05bb0-125">在 [Microsoft Defender for Endpoint connection] 對話方塊中，開啟 **[連線至 Microsoft defender For endpoint**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="05bb0-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Microsoft Defender for Endpoint connection](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="05bb0-127">移至 Microsoft Defender Security Center (<https://securitycenter.windows.com>) 。</span><span class="sxs-lookup"><span data-stu-id="05bb0-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="05bb0-128">在導覽列中，選擇 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="05bb0-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="05bb0-129">然後，在 **[一般**] 下，選擇 [ **高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="05bb0-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="05bb0-130">向下滾動至 **Office 365 威脅情報** 連線，然後開啟連線。</span><span class="sxs-lookup"><span data-stu-id="05bb0-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 威脅情報連接](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="05bb0-132">相關文章</span><span class="sxs-lookup"><span data-stu-id="05bb0-132">Related articles</span></span>

[<span data-ttu-id="05bb0-133">Office 365 中的威脅調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="05bb0-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="05bb0-134">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="05bb0-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="05bb0-135">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="05bb0-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
