---
title: Microsoft Defender 防毒軟體偵測到的威脅
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
description: 瞭解 Microsoft Defender 防毒軟體如何保護您的 Windows 裝置免受軟體威脅（如病毒、惡意程式碼和間諜軟體）的威脅。
ms.openlocfilehash: 7c5d000e2a8c30e17d1f890cef69fe88beed75bb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198360"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a><span data-ttu-id="4a084-103">Microsoft Defender 防毒軟體偵測到的威脅</span><span class="sxs-lookup"><span data-stu-id="4a084-103">Threats detected by Microsoft Defender Antivirus</span></span>

<span data-ttu-id="4a084-104">Microsoft Defender 防毒軟體會保護您的 Windows 裝置免受軟體威脅，例如病毒、惡意程式碼和間諜軟體的威脅。</span><span class="sxs-lookup"><span data-stu-id="4a084-104">Microsoft Defender Antivirus protects your Windows devices from software threats, such as viruses, malware, and spyware.</span></span>

- <span data-ttu-id="4a084-105">病毒通常是透過將其程式碼附加到裝置或網路上的其他檔案來傳播，而且可能會造成受感染的程式無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="4a084-105">Viruses typically spread by attaching their code to other files on your device or network and can cause infected programs to work incorrectly.</span></span>
- <span data-ttu-id="4a084-106">惡意程式碼包含惡意的檔案、應用程式和程式碼，可能會造成損毀，並破壞正常使用裝置。</span><span class="sxs-lookup"><span data-stu-id="4a084-106">Malware includes malicious files, applications, and code that can cause damage and disrupt normal use of devices.</span></span> <span data-ttu-id="4a084-107">此外，惡意程式碼也可以允許未經授權的存取、使用系統資源、竊取密碼和帳戶資訊、封鎖您的電腦並要求 ransom 等等。</span><span class="sxs-lookup"><span data-stu-id="4a084-107">Also, malware can allow unauthorized access, use system resources, steal passwords and account information, lock you out of your computer and ask for ransom, and more.</span></span>
- <span data-ttu-id="4a084-108">間諜軟體會收集資料，例如網頁流覽活動，並將資料傳送至遠端伺服器。</span><span class="sxs-lookup"><span data-stu-id="4a084-108">Spyware collects data, such as web-browsing activity, and sends the data to remote servers.</span></span>
 
<span data-ttu-id="4a084-109">若要提供威脅防護，Microsoft Defender 防毒軟體會使用數種方法。</span><span class="sxs-lookup"><span data-stu-id="4a084-109">To provide threat protection, Microsoft Defender Antivirus uses several methods.</span></span> <span data-ttu-id="4a084-110">這些方法包括雲端提供的保護、即時保護和專用的保護更新。</span><span class="sxs-lookup"><span data-stu-id="4a084-110">These methods include cloud-delivered protection, real-time protection, and dedicated protection updates.</span></span>

- <span data-ttu-id="4a084-111">雲端提供的保護可協助提供接近即時的偵測，並封鎖新的和新興的威脅。</span><span class="sxs-lookup"><span data-stu-id="4a084-111">Cloud-delivered protection helps provide near-instant detection and blocking of new and emerging threats.</span></span>
- <span data-ttu-id="4a084-112">Always on 掃描使用檔案與處理常式行為監控和其他技術 (也稱為 *即時保護*) 。</span><span class="sxs-lookup"><span data-stu-id="4a084-112">Always-on scanning uses file- and process-behavior monitoring and other techniques (also known as *real-time protection*).</span></span>
- <span data-ttu-id="4a084-113">專用的保護更新是以機器學習、人工和自動化大量資料分析，以及深入威脅抵觸調查為基礎。</span><span class="sxs-lookup"><span data-stu-id="4a084-113">Dedicated protection updates are based on machine learning, human and automated big-data analysis, and in-depth threat resistance research.</span></span> 

<span data-ttu-id="4a084-114">若要深入瞭解惡意程式碼和 Microsoft Defender 防毒軟體，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="4a084-114">To learn more about malware and Microsoft Defender Antivirus, see the following articles:</span></span> 

- [<span data-ttu-id="4a084-115">瞭解惡意程式碼 & 其他威脅</span><span class="sxs-lookup"><span data-stu-id="4a084-115">Understanding malware & other threats</span></span>](/windows/security/threat-protection/intelligence/understanding-malware)
- [<span data-ttu-id="4a084-116">Microsoft 如何識別惡意程式碼和潛在的有害應用程式</span><span class="sxs-lookup"><span data-stu-id="4a084-116">How Microsoft identifies malware and potentially unwanted applications</span></span>](/windows/security/threat-protection/intelligence/criteria)
- [<span data-ttu-id="4a084-117">Windows 10 中的下一代保護</span><span class="sxs-lookup"><span data-stu-id="4a084-117">Next-generation protection in Windows 10</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a><span data-ttu-id="4a084-118">使用非 Microsoft 防病毒解決方案時會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="4a084-118">What happens when a non-Microsoft antivirus solution is used?</span></span> 

<span data-ttu-id="4a084-119">Microsoft Defender 防毒軟體是作業系統的一部分，且已在執行 Windows 10 的裝置上啟用。</span><span class="sxs-lookup"><span data-stu-id="4a084-119">Microsoft Defender Antivirus is part of the operating system and is enabled on devices that are running Windows 10.</span></span> <span data-ttu-id="4a084-120">不過，如果您使用非 microsoft 防病毒方案，而且不是使用[microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)，則 Microsoft Defender 防毒軟體會自動進入停用模式。</span><span class="sxs-lookup"><span data-stu-id="4a084-120">However, if you're using a non-Microsoft antivirus solution and you aren't using [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection), then Microsoft Defender Antivirus automatically goes into disabled mode.</span></span>  

<span data-ttu-id="4a084-121">在停用模式下，使用者和客戶仍然可以使用 Microsoft Defender 防毒軟體進行排程或隨選掃描，以找出威脅;不過，Microsoft Defender 防毒軟體將不再執行：</span><span class="sxs-lookup"><span data-stu-id="4a084-121">When in disabled mode, users and customers can still use Microsoft Defender Antivirus for scheduled or on-demand scans to identify threats; however, Microsoft Defender Antivirus will no longer:</span></span>

- <span data-ttu-id="4a084-122">用作預設的防病毒應用程式。</span><span class="sxs-lookup"><span data-stu-id="4a084-122">be used as the default antivirus app.</span></span>
- <span data-ttu-id="4a084-123">主動掃描檔案以取得威脅。</span><span class="sxs-lookup"><span data-stu-id="4a084-123">actively scan files for threats.</span></span>
- <span data-ttu-id="4a084-124">修正或解決威脅。</span><span class="sxs-lookup"><span data-stu-id="4a084-124">remediate, or resolve, threats.</span></span>

<span data-ttu-id="4a084-125">如果您卸載非 Microsoft 防病毒方案，Microsoft Defender 防毒軟體會自動進入主動模式，以保護您的 Windows 裝置免受威脅。</span><span class="sxs-lookup"><span data-stu-id="4a084-125">If you uninstall the non-Microsoft antivirus solution, Microsoft Defender Antivirus will automatically go into active mode to protect your Windows devices from threats.</span></span>

> [!TIP]
> - <span data-ttu-id="4a084-126">如果您使用的是 Microsoft 365，請考慮使用 Microsoft Defender 防毒軟體做為主要防病毒解決方案。</span><span class="sxs-lookup"><span data-stu-id="4a084-126">If you're using Microsoft 365, consider using Microsoft Defender Antivirus as your primary antivirus solution.</span></span> <span data-ttu-id="4a084-127">整合可提供更好的保護。</span><span class="sxs-lookup"><span data-stu-id="4a084-127">Integration can provide better protection.</span></span> <span data-ttu-id="4a084-128">[一起查看更佳： Microsoft Defender 防毒軟體和 Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="4a084-128">See [Better together: Microsoft Defender Antivirus and Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).</span></span>
> - <span data-ttu-id="4a084-129">請務必將 Microsoft Defender 防毒軟體保持在最新狀態，即使您使用非 Microsoft 防病毒方案也是一樣。</span><span class="sxs-lookup"><span data-stu-id="4a084-129">Make sure to keep Microsoft Defender Antivirus up to date, even if you're using a non-Microsoft antivirus solution.</span></span>

## <a name="what-to-expect-when-threats-are-detected"></a><span data-ttu-id="4a084-130">偵測到威脅時的預期行為</span><span class="sxs-lookup"><span data-stu-id="4a084-130">What to expect when threats are detected</span></span>

<span data-ttu-id="4a084-131">Microsoft Defender 防毒軟體偵測到威脅時，會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="4a084-131">When threats are detected by Microsoft Defender Antivirus, the following things happen:</span></span>

- <span data-ttu-id="4a084-132">使用者接收[Windows 中的通知](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e)。</span><span class="sxs-lookup"><span data-stu-id="4a084-132">Users receive [notifications in Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e).</span></span> 
- <span data-ttu-id="4a084-133">偵測列于 [**保護歷史記錄**] 頁面上的 [ [Windows 安全性] 應用程式](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)中。</span><span class="sxs-lookup"><span data-stu-id="4a084-133">Detections are listed in the [Windows Security app](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) on the **Protection history** page.</span></span>  
- <span data-ttu-id="4a084-134">如果您已 [保護 Windows 10 裝置](secure-win-10-pcs.md)，並已 [在 Intune 中註冊](/mem/intune/enrollment/windows-enrollment-methods)，而且您的組織已註冊800或更少的裝置，您會在 **威脅和防病毒** 頁面上的 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 系統管理中心</a>中看到威脅偵測和洞察力，您可以透過選取 **健康** 情況   >  **威脅 & 防病毒**) ，從首頁 (或流覽窗格中 Microsoft Defender 防毒軟體存取。</span><span class="sxs-lookup"><span data-stu-id="4a084-134">If you've [secured your Windows 10 devices](secure-win-10-pcs.md) and [enrolled them in Intune](/mem/intune/enrollment/windows-enrollment-methods), and your organization has 800 or fewer devices enrolled, you'll see threat detections and insights in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> on the **Threats and antivirus** page, which you can access from the **Microsoft Defender Antivirus** card on the **Home** page (or from the navigation pane by selecting **Health** > **Threats & antivirus**).</span></span>

    <span data-ttu-id="4a084-135">如果您的組織已在 Intune 中註冊超過800個裝置，系統會提示您從 [Microsoft 端點管理員](/mem/endpoint-manager-overview)，而不是從 [**威脅和防病毒**] 頁面中查看威脅偵測和真知灼見。</span><span class="sxs-lookup"><span data-stu-id="4a084-135">If your organization has more than 800 devices enrolled in Intune, you'll be prompted to view threat detections and insights from [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) instead of from the **Threats and antivirus** page.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="4a084-136">**Microsoft Defender 防毒軟體** 的卡片及 **威脅及防病毒** 頁面以分階段的方式展開，所以您可能不會立即存取它們。</span><span class="sxs-lookup"><span data-stu-id="4a084-136">The **Microsoft Defender Antivirus** card and **Threats and antivirus** page are being rolled out in phases, so you may not have immediate access to them.</span></span>

<span data-ttu-id="4a084-137">在大多數情況下，使用者不需要採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="4a084-137">In most cases, users don't need to take any further action.</span></span> <span data-ttu-id="4a084-138">在裝置上偵測到惡意檔或程式時，Microsoft Defender 防毒軟體會將它封鎖，並防止其執行。</span><span class="sxs-lookup"><span data-stu-id="4a084-138">As soon as a malicious file or program is detected on a device, Microsoft Defender Antivirus blocks it and prevents it from running.</span></span> <span data-ttu-id="4a084-139">此外，新偵測到的威脅也會新增至防毒軟體和反惡意程式碼引擎，讓其他裝置和使用者也受到保護。</span><span class="sxs-lookup"><span data-stu-id="4a084-139">Plus, newly detected threats are added to the antivirus and antimalware engine so that other devices and users are protected, as well.</span></span>  

<span data-ttu-id="4a084-140">如果有使用者需要採取的動作，例如核准移除惡意檔，他們會在收到的通知中看到。</span><span class="sxs-lookup"><span data-stu-id="4a084-140">If there's an action a user needs to take, such as approving the removal of a malicious file, they'll see that in the notification they receive.</span></span> <span data-ttu-id="4a084-141">若要深入瞭解 Microsoft Defender 防毒軟體會代表使用者採取的動作，或使用者可能需要採取的動作，請參閱[保護史](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)。</span><span class="sxs-lookup"><span data-stu-id="4a084-141">To learn more about actions that Microsoft Defender Antivirus takes on a user's behalf, or actions users might need to take, see [Protection History](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708).</span></span> <span data-ttu-id="4a084-142">若要瞭解如何以 IT 專業人員/系統管理員的身分管理威脅偵測，請參閱 [查看偵測到的威脅並採取動作](review-threats-take-action.md)。</span><span class="sxs-lookup"><span data-stu-id="4a084-142">To learn how to manage threat detections as an IT professional/admin, see [Review detected threats and take action](review-threats-take-action.md).</span></span>

<span data-ttu-id="4a084-143">若要深入瞭解不同的威脅，請流覽<a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft 安全情報威脅網站</a>，您可以在其中執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4a084-143">To learn more about different threats, visit the <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft Security Intelligence Threats site</a>, where you can perform the following actions:</span></span> 

- <span data-ttu-id="4a084-144">查看有關主要威脅的目前資訊。</span><span class="sxs-lookup"><span data-stu-id="4a084-144">View current information about top threats.</span></span>
- <span data-ttu-id="4a084-145">查看特定區域的最新威脅。</span><span class="sxs-lookup"><span data-stu-id="4a084-145">View the latest threats for a specific region.</span></span>
- <span data-ttu-id="4a084-146">搜尋威脅百科全書以取得特定威脅的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4a084-146">Search the threat encyclopedia for details about a specific threat.</span></span>

## <a name="related-content"></a><span data-ttu-id="4a084-147">相關內容</span><span class="sxs-lookup"><span data-stu-id="4a084-147">Related content</span></span>

<span data-ttu-id="4a084-148">[安全 Windows 10 裝置](secure-windows-10-devices.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="4a084-148">[Secure Windows 10 devices](secure-windows-10-devices.md) (article)</span></span>\
<span data-ttu-id="4a084-149">[評估 Microsoft Defender 防毒軟體](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (文章) </span><span class="sxs-lookup"><span data-stu-id="4a084-149">[Evaluate Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (article)</span></span>\
<span data-ttu-id="4a084-150">[如何開啟即時和雲端傳遞的防防毒保護](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (文章) </span><span class="sxs-lookup"><span data-stu-id="4a084-150">[How to turn on real-time and cloud-delivered antivirus protection](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (article)</span></span>\
<span data-ttu-id="4a084-151">[如何從 Windows 安全性應用程式開啟和使用 Microsoft Defender 防毒軟體](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (文章) </span><span class="sxs-lookup"><span data-stu-id="4a084-151">[How to turn on and use Microsoft Defender Antivirus from the Windows Security app](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (article)</span></span>\
<span data-ttu-id="4a084-152">[如何使用群組原則 (文章開啟 Microsoft Defender 防毒軟體](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender)) </span><span class="sxs-lookup"><span data-stu-id="4a084-152">[How to turn on Microsoft Defender Antivirus by using Group Policy](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (article)</span></span>\
<span data-ttu-id="4a084-153">[如何更新防病毒定義](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (文章) </span><span class="sxs-lookup"><span data-stu-id="4a084-153">[How to update your antivirus definitions](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (article)</span></span>\
<span data-ttu-id="4a084-154">[如何將惡意程式碼和非惡意程式碼提交給 Microsoft 進行分析](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (文章) </span><span class="sxs-lookup"><span data-stu-id="4a084-154">[How to submit malware and non-malware to Microsoft for analysis](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (article)</span></span>
