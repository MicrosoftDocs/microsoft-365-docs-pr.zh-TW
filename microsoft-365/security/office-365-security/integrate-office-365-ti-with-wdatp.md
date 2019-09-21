---
title: 整合 Office 365 進階的威脅防護與 Microsoft Defender 進階威脅防護
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/22/2019
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
description: 整合 Microsoft Defender 進階威脅防護來威脅管理的詳細的資訊請參閱 < Office 365 進階威脅防護。
ms.openlocfilehash: a4e96615cf0f132a43957a5885b5fb33a5e8f031
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076826"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="4cf8a-103">整合 Office 365 進階的威脅防護與 Microsoft Defender 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="4cf8a-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="4cf8a-104">如果您是貴組織的安全性小組的一部分，您可以將[Office 365 進階威脅防護](office-365-atp.md)和相關的調查和回應功能整合與[Microsoft Defender 進階威脅防護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-104">If you are part of your organization's security team, you can integrate [Office 365 Advanced Threat Protection](office-365-atp.md) and related investigation and response features with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span> <span data-ttu-id="4cf8a-105">這可協助您快速了解您正在調查 Office 365 中的威脅時是否使用者的電腦是否處於風險。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="4cf8a-106">例如，一旦啟用整合，您將能夠查看機器所使用的郵件收件者偵測到的電子郵件，以及如何在 Microsoft Defender 進階威脅防護中的許多最近的通知這些機器有。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Microsoft Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="4cf8a-107">下圖顯示 [**裝置**] 索引標籤，您會看到已啟用 Microsoft Defender ATP 整合的時機：</span><span class="sxs-lookup"><span data-stu-id="4cf8a-107">The following image shows the **Devices** tab that you'll see when have Microsoft Defender ATP integration enabled:</span></span>
  
![啟用 Microsoft Defender ATP 時，您可以看到機器警示的清單。](../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="4cf8a-109">在這個範例中，您可以看到電子郵件的收件者有四種裝置，以及其他有警示。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="4cf8a-110">按一下 [裝置] 連結會開啟其 Microsoft defender 資訊安全中心。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4cf8a-111">需求</span><span class="sxs-lookup"><span data-stu-id="4cf8a-111">Requirements</span></span>

- <span data-ttu-id="4cf8a-112">您的組織必須有 Office 365 ATP 計劃 2 （或 Office 365 E5） 和 Microsoft Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-112">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="4cf8a-113">您必須是 Office 365 全域管理員或具有安全性系統管理員角色 （例如安全性管理員） 中指派[安全性&amp;合規性中心](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-113">You must be an Office 365 Global Administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="4cf8a-114">(請參閱[中的 Office 365 安全性權限&amp;合規性中心](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="4cf8a-114">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="4cf8a-115">您必須擁有存取權這兩個[檔案總管] （或即時偵測的資訊）](threat-explorer.md)中的安全性 & 規範中心和 Microsoft defender 資訊安全中心。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="4cf8a-116">若要將 Microsoft Defender ATP 與整合 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="4cf8a-116">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="4cf8a-117">整合 Office 365 ATP 與 Microsoft Defender ATP 會設定使用安全 & 與規範中心和 Microsoft defender 資訊安全中心。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-117">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="4cf8a-118">為 Office 365 全域系統管理員或安全性系統管理員，請移至[https://protection.office.com](https://protection.office.com)並以 Office 365 您公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-118">As an Office 365 global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account for Office 365.</span></span>
    
2. <span data-ttu-id="4cf8a-119">選擇 [**威脅管理** \> **總管**。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="4cf8a-120">![威脅管理] 功能表中的 explorer](../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="4cf8a-120">![Explorer in Threat Management menu](../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="4cf8a-121">在螢幕的右上角，選擇 [ **WDATP 設定**。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="4cf8a-122">在 [Windows Defender ATP 連線] 對話方塊中，開啟連線到 Windows ATP。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-122">In the Windows Defender ATP connection dialog box, turn on Connect to Windows ATP.</span></span><br>![Microsoft Defender ATP 連線](../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. <span data-ttu-id="4cf8a-124">啟用 Microsoft defender 資訊安全中心中的連線。</span><span class="sxs-lookup"><span data-stu-id="4cf8a-124">Enable the connection in the Microsoft Defender Security Center.</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="4cf8a-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="4cf8a-125">Related topics</span></span>

[<span data-ttu-id="4cf8a-126">Office 365 威脅調查及回應</span><span class="sxs-lookup"><span data-stu-id="4cf8a-126">Office 365 Threat Investigation and Response</span></span>](office-365-ti.md)
  
[<span data-ttu-id="4cf8a-127">Office 365 進階威脅防護</span><span class="sxs-lookup"><span data-stu-id="4cf8a-127">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

