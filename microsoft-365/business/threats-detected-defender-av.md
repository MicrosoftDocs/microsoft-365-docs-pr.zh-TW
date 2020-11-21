---
title: Microsoft Defender 防病毒偵測到的威脅
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 瞭解 Microsoft Defender 防毒軟體如何保護您的 Windows 裝置免受軟體威脅（如病毒、惡意程式碼和間諜軟體的威脅）。
ms.openlocfilehash: e3c8a1071625bba41af5f3cccd50f8484acac18d
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376680"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a><span data-ttu-id="49ea1-103">Microsoft Defender 防病毒偵測到的威脅</span><span class="sxs-lookup"><span data-stu-id="49ea1-103">Threats detected by Microsoft Defender Antivirus</span></span>

<span data-ttu-id="49ea1-104">Microsoft Defender 防毒軟體會保護您的 Windows 裝置免受軟體威脅，例如病毒、惡意程式碼和間諜軟體的威脅。</span><span class="sxs-lookup"><span data-stu-id="49ea1-104">Microsoft Defender Antivirus protects your Windows devices from software threats, such as viruses, malware, and spyware.</span></span>

- <span data-ttu-id="49ea1-105">病毒通常是透過將其程式碼附加到裝置或網路上的其他檔案來傳播，而且可能會造成受感染的程式無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="49ea1-105">Viruses typically spread by attaching their code to other files on your device or network and can cause infected programs to work incorrectly.</span></span>
- <span data-ttu-id="49ea1-106">惡意程式碼包含惡意的檔案、應用程式和程式碼，可能會造成損毀，並破壞正常使用裝置。</span><span class="sxs-lookup"><span data-stu-id="49ea1-106">Malware includes malicious files, applications, and code that can cause damage and disrupt normal use of devices.</span></span> <span data-ttu-id="49ea1-107">此外，惡意程式碼也可以允許未經授權的存取、使用系統資源、竊取密碼和帳戶資訊、封鎖您的電腦並要求 ransom 等等。</span><span class="sxs-lookup"><span data-stu-id="49ea1-107">Also, malware can allow unauthorized access, use system resources, steal passwords and account information, lock you out of your computer and ask for ransom, and more.</span></span>
- <span data-ttu-id="49ea1-108">間諜軟體會收集資料，例如網頁流覽活動，並將資料傳送至遠端伺服器。</span><span class="sxs-lookup"><span data-stu-id="49ea1-108">Spyware collects data, such as web-browsing activity, and sends the data to remote servers.</span></span>
 
<span data-ttu-id="49ea1-109">為了提供威脅防護，Microsoft Defender 防病毒會使用數種方法。</span><span class="sxs-lookup"><span data-stu-id="49ea1-109">To provide threat protection, Microsoft Defender Antivirus uses several methods.</span></span> <span data-ttu-id="49ea1-110">這些方法包括雲端提供的保護、即時保護和專用的保護更新。</span><span class="sxs-lookup"><span data-stu-id="49ea1-110">These methods include cloud-delivered protection, real-time protection, and dedicated protection updates.</span></span>

- <span data-ttu-id="49ea1-111">雲端提供的保護可協助提供接近即時的偵測，並封鎖新的和新興的威脅。</span><span class="sxs-lookup"><span data-stu-id="49ea1-111">Cloud-delivered protection helps provide near-instant detection and blocking of new and emerging threats.</span></span>
- <span data-ttu-id="49ea1-112">Always on 掃描使用檔案與處理常式行為監控和其他技術 (也稱為 *即時保護*) 。</span><span class="sxs-lookup"><span data-stu-id="49ea1-112">Always-on scanning uses file- and process-behavior monitoring and other techniques (also known as *real-time protection*).</span></span>
- <span data-ttu-id="49ea1-113">專用的保護更新是以機器學習、人工和自動化大量資料分析，以及深入威脅抵觸調查為基礎。</span><span class="sxs-lookup"><span data-stu-id="49ea1-113">Dedicated protection updates are based on machine learning, human and automated big-data analysis, and in-depth threat resistance research.</span></span> 

<span data-ttu-id="49ea1-114">若要深入瞭解惡意程式碼和 Microsoft Defender 防病毒，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="49ea1-114">To learn more about malware and Microsoft Defender Antivirus, see the following articles:</span></span> 

- [<span data-ttu-id="49ea1-115">瞭解惡意程式碼 & 其他威脅</span><span class="sxs-lookup"><span data-stu-id="49ea1-115">Understanding malware & other threats</span></span>](/windows/security/threat-protection/intelligence/understanding-malware)
- [<span data-ttu-id="49ea1-116">Microsoft 如何識別惡意程式碼和潛在的有害應用程式</span><span class="sxs-lookup"><span data-stu-id="49ea1-116">How Microsoft identifies malware and potentially unwanted applications</span></span>](/windows/security/threat-protection/intelligence/criteria)
- [<span data-ttu-id="49ea1-117">Windows 10 中的下一代保護</span><span class="sxs-lookup"><span data-stu-id="49ea1-117">Next-generation protection in Windows 10</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a><span data-ttu-id="49ea1-118">使用非 Microsoft 防病毒解決方案時會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="49ea1-118">What happens when a non-Microsoft antivirus solution is used?</span></span> 

<span data-ttu-id="49ea1-119">Microsoft Defender 防病毒是作業系統的一部分，且已在執行 Windows 10 的裝置上啟用。</span><span class="sxs-lookup"><span data-stu-id="49ea1-119">Microsoft Defender Antivirus is part of the operating system and is enabled on devices that are running Windows 10.</span></span> <span data-ttu-id="49ea1-120">不過，如果您使用非 Microsoft 防病毒方案，而且不是使用 [Microsoft defender For Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)，則 Microsoft Defender 防毒程式會自動進入停用模式。</span><span class="sxs-lookup"><span data-stu-id="49ea1-120">However, if you're using a non-Microsoft antivirus solution and you aren't using [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection), then Microsoft Defender Antivirus automatically goes into disabled mode.</span></span>  

<span data-ttu-id="49ea1-121">在停用模式下，使用者和客戶仍然可以使用 Microsoft Defender 防毒程式進行排程或隨選即用掃描，以找出威脅;不過，Microsoft Defender 防毒程式將不再執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="49ea1-121">When in disabled mode, users and customers can still use Microsoft Defender Antivirus for scheduled or on-demand scans to identify threats; however, Microsoft Defender Antivirus will no longer:</span></span>

- <span data-ttu-id="49ea1-122">用作預設的防病毒應用程式。</span><span class="sxs-lookup"><span data-stu-id="49ea1-122">be used as the default antivirus app.</span></span>
- <span data-ttu-id="49ea1-123">主動掃描檔案以取得威脅。</span><span class="sxs-lookup"><span data-stu-id="49ea1-123">actively scan files for threats.</span></span>
- <span data-ttu-id="49ea1-124">修正或解決威脅。</span><span class="sxs-lookup"><span data-stu-id="49ea1-124">remediate, or resolve, threats.</span></span>

<span data-ttu-id="49ea1-125">如果您卸載非 Microsoft 防病毒方案，Microsoft Defender 防毒程式將會自動進入主動模式，以保護您的 Windows 裝置免受威脅。</span><span class="sxs-lookup"><span data-stu-id="49ea1-125">If you uninstall the non-Microsoft antivirus solution, Microsoft Defender Antivirus will automatically go into active mode to protect your Windows devices from threats.</span></span>

> [!TIP]
> - <span data-ttu-id="49ea1-126">如果您使用的是 Microsoft 365，請考慮使用 Microsoft Defender 防病毒做為您的主要防病毒解決方案。</span><span class="sxs-lookup"><span data-stu-id="49ea1-126">If you're using Microsoft 365, consider using Microsoft Defender Antivirus as your primary antivirus solution.</span></span> <span data-ttu-id="49ea1-127">整合可提供更好的保護。</span><span class="sxs-lookup"><span data-stu-id="49ea1-127">Integration can provide better protection.</span></span> <span data-ttu-id="49ea1-128">[一起查看： Microsoft Defender 防病毒和 Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="49ea1-128">See [Better together: Microsoft Defender Antivirus and Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).</span></span>
> - <span data-ttu-id="49ea1-129">請務必將 Microsoft Defender 防病毒保持在最新狀態，即使您使用非 Microsoft 防病毒方案也是一樣。</span><span class="sxs-lookup"><span data-stu-id="49ea1-129">Make sure to keep Microsoft Defender Antivirus up to date, even if you're using a non-Microsoft antivirus solution.</span></span>

## <a name="what-to-expect-when-threats-are-detected"></a><span data-ttu-id="49ea1-130">偵測到威脅時的預期行為</span><span class="sxs-lookup"><span data-stu-id="49ea1-130">What to expect when threats are detected</span></span>

<span data-ttu-id="49ea1-131">當 Microsoft Defender 防病毒偵測到威脅時，會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="49ea1-131">When threats are detected by Microsoft Defender Antivirus, the following things happen:</span></span>

- <span data-ttu-id="49ea1-132">使用者 [在 Windows 中接收通知](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e)。</span><span class="sxs-lookup"><span data-stu-id="49ea1-132">Users receive [notifications in Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e).</span></span> 
- <span data-ttu-id="49ea1-133">偵測列于 [**保護歷史記錄**] 頁面上的 [ [Windows 安全性] 應用程式](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)中。</span><span class="sxs-lookup"><span data-stu-id="49ea1-133">Detections are listed in the [Windows Security app](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) on the **Protection history** page.</span></span>  
- <span data-ttu-id="49ea1-134">如果您已 [保護 Windows 10 裝置](secure-win-10-pcs.md)，並已 [在 Intune 中註冊](/mem/intune/enrollment/windows-enrollment-methods)，您會在 [作用中 **威脅**] 頁面上看到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">microsoft 365 系統管理中心</a>的威脅偵測和洞察力，您可以透過選取 **健康** 情況 **Home** 威脅 & 防病毒) ，從首頁上的 **microsoft Defender 防病毒** 卡 (或流覽窗格中存取  >  **Threats & antivirus** 。</span><span class="sxs-lookup"><span data-stu-id="49ea1-134">If you've [secured your Windows 10 devices](secure-win-10-pcs.md) and [enrolled them in Intune](/mem/intune/enrollment/windows-enrollment-methods), you'll see threat detections and insights in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> on the **Active threats** page, which you can access from the **Microsoft Defender Antivirus** card on the **Home** page (or from the navigation pane by selecting **Health** > **Threats & antivirus**).</span></span>
    > [!NOTE]
    > <span data-ttu-id="49ea1-135">**Microsoft Defender 防毒軟體** 卡和作用中 **威脅** 頁面會以分階段的方式展開，所以您可能無法立即進行存取。</span><span class="sxs-lookup"><span data-stu-id="49ea1-135">The **Microsoft Defender Antivirus** card and **Active threats** page are being rolled out in phases, so you may not have immediate access to them.</span></span>

<span data-ttu-id="49ea1-136">在大多數情況下，使用者不需要採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="49ea1-136">In most cases, users don't need to take any further action.</span></span> <span data-ttu-id="49ea1-137">在裝置上偵測到惡意檔或程式之後，Microsoft Defender 防毒程式會封鎖它，並防止其執行。</span><span class="sxs-lookup"><span data-stu-id="49ea1-137">As soon as a malicious file or program is detected on a device, Microsoft Defender Antivirus blocks it and prevents it from running.</span></span> <span data-ttu-id="49ea1-138">此外，新偵測到的威脅也會新增至防毒軟體和反惡意程式碼引擎，讓其他裝置和使用者也受到保護。</span><span class="sxs-lookup"><span data-stu-id="49ea1-138">Plus, newly detected threats are added to the antivirus and antimalware engine so that other devices and users are protected, as well.</span></span>  

<span data-ttu-id="49ea1-139">如果有使用者需要採取的動作，例如核准移除惡意檔，他們會在收到的通知中看到。</span><span class="sxs-lookup"><span data-stu-id="49ea1-139">If there's an action a user needs to take, such as approving the removal of a malicious file, they'll see that in the notification they receive.</span></span> <span data-ttu-id="49ea1-140">若要深入瞭解 Microsoft Defender 防病毒在使用者上採取的動作，或使用者可能需要採取的動作，請參閱 [保護史](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)。</span><span class="sxs-lookup"><span data-stu-id="49ea1-140">To learn more about actions that Microsoft Defender Antivirus takes on a user's behalf, or actions users might need to take, see [Protection History](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708).</span></span> <span data-ttu-id="49ea1-141">若要瞭解如何以 IT 專業人員/系統管理員的身分管理威脅偵測，請參閱 [查看偵測到的威脅並採取動作](review-threats-take-action.md)。</span><span class="sxs-lookup"><span data-stu-id="49ea1-141">To learn how to manage threat detections as an IT professional/admin, see [Review detected threats and take action](review-threats-take-action.md).</span></span>

<span data-ttu-id="49ea1-142">若要深入瞭解不同威脅，請造訪 <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft Security 情報威脅網站</a>，以供您執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="49ea1-142">To learn more about different threats, visit the <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft Security Intelligence Threats site</a>, where you can perform the following actions:</span></span> 

- <span data-ttu-id="49ea1-143">查看有關主要威脅的目前資訊。</span><span class="sxs-lookup"><span data-stu-id="49ea1-143">View current information about top threats.</span></span>
- <span data-ttu-id="49ea1-144">查看特定區域的最新威脅。</span><span class="sxs-lookup"><span data-stu-id="49ea1-144">View the latest threats for a specific region.</span></span>
- <span data-ttu-id="49ea1-145">搜尋威脅百科全書以取得特定威脅的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="49ea1-145">Search the threat encyclopedia for details about a specific threat.</span></span>

## <a name="related-content"></a><span data-ttu-id="49ea1-146">相關內容</span><span class="sxs-lookup"><span data-stu-id="49ea1-146">Related content</span></span>

<span data-ttu-id="49ea1-147">[保護 Windows 10 裝置](secure-windows-10-devices.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="49ea1-147">[Secure Windows 10 devices](secure-windows-10-devices.md) (article)</span></span>\
<span data-ttu-id="49ea1-148">[評估 Microsoft Defender 防病毒](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (文章) </span><span class="sxs-lookup"><span data-stu-id="49ea1-148">[Evaluate Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (article)</span></span>\
<span data-ttu-id="49ea1-149">[如何開啟即時和雲端傳遞的防防毒保護](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (文章) </span><span class="sxs-lookup"><span data-stu-id="49ea1-149">[How to turn on real-time and cloud-delivered antivirus protection](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (article)</span></span>\
<span data-ttu-id="49ea1-150">[如何在 Windows 安全性 app 中開啟及使用 Microsoft Defender 防病毒](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (文章) </span><span class="sxs-lookup"><span data-stu-id="49ea1-150">[How to turn on and use Microsoft Defender Antivirus from the Windows Security app](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (article)</span></span>\
<span data-ttu-id="49ea1-151">[如何使用群組原則開啟 Microsoft Defender 防病毒](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (文章) </span><span class="sxs-lookup"><span data-stu-id="49ea1-151">[How to turn on Microsoft Defender Antivirus by using Group Policy](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (article)</span></span>\
<span data-ttu-id="49ea1-152">[如何更新防病毒定義](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (文章) </span><span class="sxs-lookup"><span data-stu-id="49ea1-152">[How to update your antivirus definitions](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (article)</span></span>\
<span data-ttu-id="49ea1-153">[如何將惡意程式碼和非惡意程式碼提交給 Microsoft 進行分析](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (文章) </span><span class="sxs-lookup"><span data-stu-id="49ea1-153">[How to submit malware and non-malware to Microsoft for analysis](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (article)</span></span>