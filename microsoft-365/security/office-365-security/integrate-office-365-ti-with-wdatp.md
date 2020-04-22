---
title: 使用 Microsoft Defender 高級威脅防護整合 Office 365 高級威脅防護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/13/2020
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
ms.openlocfilehash: e416d70baf7498b0163d5bd8aa8e923585a5e5a4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633806"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="ce0a5-103">使用 Microsoft Defender 高級威脅防護整合 Office 365 高級威脅防護</span><span class="sxs-lookup"><span data-stu-id="ce0a5-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="ce0a5-104">如果您是組織的安全性小組的一部分，您可以使用[Microsoft Defender 高級威脅防護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)來整合[Office 365 的高級威脅防護](office-365-atp.md)和相關的調查和回應功能。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-104">If you are part of your organization's security team, you can integrate [Office 365 Advanced Threat Protection](office-365-atp.md) and related investigation and response features with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span> <span data-ttu-id="ce0a5-105">這可協助您在調查 Office 365 中的威脅時，快速瞭解使用者的機器是否存在危險。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="ce0a5-106">例如，啟用整合後，您將可以查看偵測到之電子郵件的收件者所使用的機器清單，以及這些電腦在 Microsoft Defender 高級威脅防護中的最近通知數目。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Microsoft Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="ce0a5-107">下圖顯示您在啟用 Microsoft Defender ATP 整合時所看到的 [**裝置**] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="ce0a5-107">The following image shows the **Devices** tab that you'll see when have Microsoft Defender ATP integration enabled:</span></span>
  
![啟用 Microsoft Defender ATP 後，您可以看到具有警示的裝置清單。](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="ce0a5-109">在此範例中，您可以看到電子郵件的收件者有四個裝置，一個包含警示。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="ce0a5-110">按一下裝置的連結會在 Microsoft Defender 安全中心開啟其頁面。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="ce0a5-111">需求</span><span class="sxs-lookup"><span data-stu-id="ce0a5-111">Requirements</span></span>

- <span data-ttu-id="ce0a5-112">您的組織必須具有 Office 365 ATP Plan 2 （或 Office 365 E5）和 Microsoft Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-112">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="ce0a5-113">您必須是全域系統管理員，或具有安全性與[ &amp;合規性中心](https://protection.office.com)中所指派的安全性系統管理員角色（例如安全性管理員）。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-113">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="ce0a5-114">（請參閱[安全性&amp;與合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)）</span><span class="sxs-lookup"><span data-stu-id="ce0a5-114">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="ce0a5-115">您必須能夠在安全性 & 規範中心和 Microsoft Defender Security Center 中存取[瀏覽器（或即時偵測）](threat-explorer.md) 。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="ce0a5-116">將 Office 365 ATP 與 Microsoft Defender ATP 整合</span><span class="sxs-lookup"><span data-stu-id="ce0a5-116">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="ce0a5-117">使用安全性 & 規範中心和 Microsoft Defender 安全性中心，將 Office 365 ATP 整合至 Microsoft Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-117">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="ce0a5-118">以全域管理員或安全性管理員的身分，移至[https://protection.office.com](https://protection.office.com)並登入您的公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-118">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="ce0a5-119">選擇 [**威脅管理** \> **瀏覽器**]。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="ce0a5-120">![威脅管理功能表中的 Explorer](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="ce0a5-120">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="ce0a5-121">在螢幕的右上角，選擇 [ **WDATP 設定**]。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="ce0a5-122">在 [Microsoft Defender ATP connection] 對話方塊中，開啟 **[連線到 WINDOWS ATP**]。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-122">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="ce0a5-123">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="ce0a5-123">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="ce0a5-124">啟用 Microsoft Defender Security Center 中的連線（[https://securitycenter.windows.com](https://securitycenter.windows.com)）。</span><span class="sxs-lookup"><span data-stu-id="ce0a5-124">Enable the connection in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ce0a5-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="ce0a5-125">Related topics</span></span>

[<span data-ttu-id="ce0a5-126">Office 365 中的威脅調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="ce0a5-126">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="ce0a5-127">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="ce0a5-127">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

