---
title: 整合 Office 365 ATP 和 Microsoft Defender ATP
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: 使用 Microsoft Defender 高級威脅防護整合 Office 365 高級威脅防護，以查看更詳細的威脅管理資訊。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086704"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="1c88e-103">使用 Microsoft Defender 高級威脅防護整合 Office 365 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="1c88e-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="1c88e-104">[Office 365 Advanced 威脅防護](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)（OFFICE 365 ATP）可以設定為搭配[Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection)（Microsoft defender ATP）。</span><span class="sxs-lookup"><span data-stu-id="1c88e-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) can be configured to work with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span></span>

<span data-ttu-id="1c88e-105">將 Office 365 ATP 與 Microsoft Defender ATP 整合，可協助您的安全性運作小組監視並快速採取行動（如果使用者的裝置面臨危險）。</span><span class="sxs-lookup"><span data-stu-id="1c88e-105">Integrating Office 365 ATP with Microsoft Defender ATP can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="1c88e-106">例如，啟用整合後，您的安全性作業小組將能夠查看偵測到的電子郵件訊息可能影響的裝置，以及這些裝置在 Microsoft Defender ATP 中的最近通知數目。</span><span class="sxs-lookup"><span data-stu-id="1c88e-106">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts those devices have in Microsoft Defender ATP.</span></span> 

<span data-ttu-id="1c88e-107">下圖說明 [**裝置**] 索引標籤似乎已啟用 MICROSOFT Defender ATP 整合功能：</span><span class="sxs-lookup"><span data-stu-id="1c88e-107">The following image depicts what the **Devices** tab looks like have Microsoft Defender ATP integration enabled:</span></span>
  
![啟用 Microsoft Defender ATP 後，您可以看到具有警示的裝置清單。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="1c88e-109">在此範例中，您可以看到偵測到之電子郵件的收件者有四個裝置，一個有警示。</span><span class="sxs-lookup"><span data-stu-id="1c88e-109">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="1c88e-110">按一下裝置的連結會在 Microsoft Defender 安全中心（）中開啟其頁面 [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="1c88e-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="1c88e-111">**[深入瞭解 Microsoft Defender 安全中心](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)**（也稱為 MICROSOFT defender ATP 入口網站）。</span><span class="sxs-lookup"><span data-stu-id="1c88e-111">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="1c88e-112">需求</span><span class="sxs-lookup"><span data-stu-id="1c88e-112">Requirements</span></span>

- <span data-ttu-id="1c88e-113">您的組織必須具有 Office 365 ATP Plan 2 （或 Office 365 E5）和 Microsoft Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="1c88e-113">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="1c88e-114">您必須是全域系統管理員，或具有安全性與[ &amp; 合規性中心](https://protection.office.com)中所指派的安全性系統管理員角色（例如安全性管理員）。</span><span class="sxs-lookup"><span data-stu-id="1c88e-114">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="1c88e-115">（請參閱[安全性與 &amp; 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)）</span><span class="sxs-lookup"><span data-stu-id="1c88e-115">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="1c88e-116">您必須能夠在安全性 & 規範中心和 Microsoft Defender Security Center 中存取[瀏覽器（或即時偵測）](threat-explorer.md) 。</span><span class="sxs-lookup"><span data-stu-id="1c88e-116">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="1c88e-117">將 Office 365 ATP 與 Microsoft Defender ATP 整合</span><span class="sxs-lookup"><span data-stu-id="1c88e-117">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="1c88e-118">使用安全性 & 規範中心和 Microsoft Defender 安全性中心，將 Office 365 ATP 整合至 Microsoft Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="1c88e-118">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="1c88e-119">以全域管理員或安全性管理員為單位，請移至 [https://protection.office.com](https://protection.office.com) 並登入。</span><span class="sxs-lookup"><span data-stu-id="1c88e-119">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="1c88e-120">（這會帶您前往 Office 365 的安全性 & 規範中心）。</span><span class="sxs-lookup"><span data-stu-id="1c88e-120">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="1c88e-121">在功能窗格中，選擇 [**威脅管理**  >  **瀏覽器**]。</span><span class="sxs-lookup"><span data-stu-id="1c88e-121">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="1c88e-122">![威脅管理功能表中的 Explorer](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="1c88e-122">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="1c88e-123">在螢幕的右上角，選擇 [ **WDATP 設定**]。</span><span class="sxs-lookup"><span data-stu-id="1c88e-123">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="1c88e-124">在 [Microsoft Defender ATP connection] 對話方塊中，開啟 **[連線到 WINDOWS ATP**]。</span><span class="sxs-lookup"><span data-stu-id="1c88e-124">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="1c88e-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="1c88e-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="1c88e-126">移至 Microsoft Defender 安全中心（ [https://securitycenter.windows.com](https://securitycenter.windows.com) ）。</span><span class="sxs-lookup"><span data-stu-id="1c88e-126">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="1c88e-127">在導覽列中，選擇 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="1c88e-127">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="1c88e-128">然後，在 **[一般**] 下，選擇 [**高級功能**]。</span><span class="sxs-lookup"><span data-stu-id="1c88e-128">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="1c88e-129">向下滾動至**Office 365 威脅情報**連線，然後開啟連線。</span><span class="sxs-lookup"><span data-stu-id="1c88e-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="1c88e-130">![Office 365 威脅情報連接](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="1c88e-130">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="1c88e-131">相關文章</span><span class="sxs-lookup"><span data-stu-id="1c88e-131">Related articles</span></span>

[<span data-ttu-id="1c88e-132">Office 365 中的威脅調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="1c88e-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="1c88e-133">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="1c88e-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="1c88e-134">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="1c88e-134">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
