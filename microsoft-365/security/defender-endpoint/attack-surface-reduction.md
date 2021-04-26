---
title: 使用攻擊面減少規則，以防止惡意程式碼感染
description: 攻擊面減少規則可協助防止利用應用程式和腳本感染具有惡意程式碼的裝置。
keywords: 攻擊面減少規則，asr，hips，主機入侵防護系統，保護規則，反侵入，antiexploit，exploit，感染防護，Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 461bc7c8d4d8d5c9bb8c905f3b160d0af226b077
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023222"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a><span data-ttu-id="dc26d-104">使用攻擊面減少規則，以防止惡意程式碼感染</span><span class="sxs-lookup"><span data-stu-id="dc26d-104">Use attack surface reduction rules to prevent malware infection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dc26d-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="dc26d-105">**Applies to:**</span></span>
- [<span data-ttu-id="dc26d-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="dc26d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="dc26d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc26d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="why-attack-surface-reduction-rules-are-important"></a><span data-ttu-id="dc26d-108">攻擊面減少規則為何很重要</span><span class="sxs-lookup"><span data-stu-id="dc26d-108">Why attack surface reduction rules are important</span></span>

<span data-ttu-id="dc26d-109">組織的攻擊麵包括攻擊者可能會損害組織之裝置或網路的所有地方。</span><span class="sxs-lookup"><span data-stu-id="dc26d-109">Your organization's attack surface includes all the places where an attacker could compromise your organization's devices or networks.</span></span> <span data-ttu-id="dc26d-110">減少攻擊面是指保護您組織的裝置和網路，這可讓攻擊者以較少的方式執行攻擊。</span><span class="sxs-lookup"><span data-stu-id="dc26d-110">Reducing your attack surface means protecting your organization's devices and network, which leaves attackers with fewer ways to perform attacks.</span></span> <span data-ttu-id="dc26d-111">在 Microsoft Defender for Endpoint 中設定攻擊面降低規則可協助！</span><span class="sxs-lookup"><span data-stu-id="dc26d-111">Configuring attack surface reduction rules in Microsoft Defender for Endpoint can help!</span></span>

<span data-ttu-id="dc26d-112">攻擊面減少規則會以特定的軟體行為為目標，例如：</span><span class="sxs-lookup"><span data-stu-id="dc26d-112">Attack surface reduction rules target certain software behaviors, such as:</span></span>

- <span data-ttu-id="dc26d-113">啟動可執行檔及腳本，以嘗試下載或執行檔;</span><span class="sxs-lookup"><span data-stu-id="dc26d-113">Launching executable files and scripts that attempt to download or run files;</span></span>
- <span data-ttu-id="dc26d-114">執行已模糊處理或其他可疑的腳本;和</span><span class="sxs-lookup"><span data-stu-id="dc26d-114">Running obfuscated or otherwise suspicious scripts; and</span></span>
- <span data-ttu-id="dc26d-115">執行在正常的日常工作中，應用程式通常不會啟動的行為。</span><span class="sxs-lookup"><span data-stu-id="dc26d-115">Performing behaviors that apps don't usually initiate during normal day-to-day work.</span></span>

<span data-ttu-id="dc26d-116">這類軟體行為有時會出現在合法的應用程式中;不過，這些行為通常會被視為危險，因為它們通常是透過惡意程式碼被攻擊者濫用。</span><span class="sxs-lookup"><span data-stu-id="dc26d-116">Such software behaviors are sometimes seen in legitimate applications; however, these behaviors are often considered risky because they are commonly abused by attackers through malware.</span></span> <span data-ttu-id="dc26d-117">攻擊面減少規則可限制危險的行為，並協助保護您的組織安全。</span><span class="sxs-lookup"><span data-stu-id="dc26d-117">Attack surface reduction rules can constrain risky behaviors and help keep your organization safe.</span></span>

<span data-ttu-id="dc26d-118">如需設定攻擊面減少規則的相關資訊，請參閱 [啟用攻擊面降減規則](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="dc26d-118">For more information about configuring attack surface reduction rules, see [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

## <a name="assess-rule-impact-before-deployment"></a><span data-ttu-id="dc26d-119">在部署之前評估規則影響</span><span class="sxs-lookup"><span data-stu-id="dc26d-119">Assess rule impact before deployment</span></span>

<span data-ttu-id="dc26d-120">您可以在 [威脅和弱點管理](https://docs.microsoft.com/windows/security/threat-protection/#tvm)中開啟該規則的安全性建議，以評估攻擊面降低規則可能會如何影響您的網路。</span><span class="sxs-lookup"><span data-stu-id="dc26d-120">You can assess how an attack surface reduction rule might affect your network by opening the security recommendation for that rule in [threat and vulnerability management](https://docs.microsoft.com/windows/security/threat-protection/#tvm).</span></span>

:::image type="content" source="images/asrrecommendation.png" alt-text="攻擊面降低規則的安全性 reco":::

<span data-ttu-id="dc26d-122">在 [建議詳細資料] 窗格中，檢查 [使用者影響] 以判斷您的裝置可接受新原則的百分比，以封鎖模式啟用規則，而不會對生產力造成不良影響。</span><span class="sxs-lookup"><span data-stu-id="dc26d-122">In the recommendation details pane, check for user impact to determine what percentage of your devices can accept a new policy enabling the rule in blocking mode without adversely affecting productivity.</span></span>

## <a name="audit-mode-for-evaluation"></a><span data-ttu-id="dc26d-123">評估的審計模式</span><span class="sxs-lookup"><span data-stu-id="dc26d-123">Audit mode for evaluation</span></span>

<span data-ttu-id="dc26d-124">使用 [審計模式](audit-windows-defender.md) 評估攻擊面降低規則在啟用時會如何影響您的組織。</span><span class="sxs-lookup"><span data-stu-id="dc26d-124">Use [audit mode](audit-windows-defender.md) to evaluate how attack surface reduction rules would affect your organization if they were enabled.</span></span> <span data-ttu-id="dc26d-125">請先在稽核模式中執行所有規則，以便了解它們如何影響您的企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="dc26d-125">Run all rules in audit mode first so you can understand how they affect your line-of-business applications.</span></span> <span data-ttu-id="dc26d-126">許多商務營運應用程式都是以有限的安全性考慮來編寫，而且他們可能會以類似惡意程式碼的方式執行工作。</span><span class="sxs-lookup"><span data-stu-id="dc26d-126">Many line-of-business applications are written with limited security concerns, and they might perform tasks in ways that seem similar to malware.</span></span> <span data-ttu-id="dc26d-127">透過監視審核資料並 [新增](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 必要應用程式的排除專案，您可以在不降低生產力的情況下，部署攻擊面減少規則。</span><span class="sxs-lookup"><span data-stu-id="dc26d-127">By monitoring audit data and [adding exclusions](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) for necessary applications, you can deploy attack surface reduction rules without reducing productivity.</span></span>

## <a name="warn-mode-for-users"></a><span data-ttu-id="dc26d-128">使用者的警告模式</span><span class="sxs-lookup"><span data-stu-id="dc26d-128">Warn mode for users</span></span>

<span data-ttu-id="dc26d-129"> (**NEW**！ ) 在警告模式功能之前，已啟用的攻擊面降規則可以設定為 [稽核模式] 或 [封鎖模式]。</span><span class="sxs-lookup"><span data-stu-id="dc26d-129">(**NEW**!) Prior to warn mode capabilities, attack surface reduction rules that are enabled could be set to either audit mode or block mode.</span></span> <span data-ttu-id="dc26d-130">使用新的警告模式時，每當攻擊面減少規則封鎖內容時，使用者會看到指出內容已封鎖的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="dc26d-130">With the new warn mode, whenever content is blocked by an attack surface reduction rule, users see a dialog box that indicates the content is blocked.</span></span> <span data-ttu-id="dc26d-131">對話方塊也會為使用者提供取消封鎖內容的選項。</span><span class="sxs-lookup"><span data-stu-id="dc26d-131">The dialog box also offers the user an option to unblock the content.</span></span> <span data-ttu-id="dc26d-132">然後，使用者可以重試其動作，並完成操作。</span><span class="sxs-lookup"><span data-stu-id="dc26d-132">The user can then retry their action, and the operation completes.</span></span> <span data-ttu-id="dc26d-133">當使用者取消封鎖內容時，內容會維持在24小時內解除封鎖，然後封鎖簡歷。</span><span class="sxs-lookup"><span data-stu-id="dc26d-133">When a user unblocks content, the content remains unblocked for 24 hours, and then blocking resumes.</span></span>

<span data-ttu-id="dc26d-134">警告模式可協助您的組織實施攻擊面降減規則，而不會防止使用者存取他們執行其工作所需的內容。</span><span class="sxs-lookup"><span data-stu-id="dc26d-134">Warn mode helps your organization have attack surface reduction rules in place without preventing users from accessing the content they need to perform their tasks.</span></span>

### <a name="requirements-for-warn-mode-to-work"></a><span data-ttu-id="dc26d-135">警告模式的運作需求</span><span class="sxs-lookup"><span data-stu-id="dc26d-135">Requirements for warn mode to work</span></span>

<span data-ttu-id="dc26d-136">在執行下列 Windows 版本的裝置上支援警告模式：</span><span class="sxs-lookup"><span data-stu-id="dc26d-136">Warn mode is supported on devices running the following versions of Windows:</span></span>

- <span data-ttu-id="dc26d-137">[Windows 10，版本 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-137">[Windows 10, version 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) or later</span></span>
- <span data-ttu-id="dc26d-138">[Windows Server，版本 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-138">[Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809) or later</span></span>

<span data-ttu-id="dc26d-139">使用 [Active 模式](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)中的即時保護時，必須執行 Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="dc26d-139">Microsoft Defender Antivirus must be running with real-time protection in [Active mode](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).</span></span>

<span data-ttu-id="dc26d-140">此外，請確定已安裝 [Microsoft Defender 防毒軟體和反惡意軟體更新](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) 。</span><span class="sxs-lookup"><span data-stu-id="dc26d-140">In addition, make sure [Microsoft Defender Antivirus and antimalware updates](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) are installed.</span></span>

- <span data-ttu-id="dc26d-141">最低平臺版本需求： `4.18.2008.9`</span><span class="sxs-lookup"><span data-stu-id="dc26d-141">Minimum platform release requirement: `4.18.2008.9`</span></span>
- <span data-ttu-id="dc26d-142">最低引擎發行需求： `1.1.17400.5`</span><span class="sxs-lookup"><span data-stu-id="dc26d-142">Minimum engine release requirement: `1.1.17400.5`</span></span>

<span data-ttu-id="dc26d-143">如需詳細資訊和若要取得更新，請參閱 [Microsoft Defender 反惡意程式碼平臺的更新](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="dc26d-143">For more information and to get your updates, see [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).</span></span>

### <a name="cases-where-warn-mode-is-not-supported"></a><span data-ttu-id="dc26d-144">不支援警告模式的情況</span><span class="sxs-lookup"><span data-stu-id="dc26d-144">Cases where warn mode is not supported</span></span>

<span data-ttu-id="dc26d-145">當您在 Microsoft 端點管理員中進行設定時，三個攻擊面降減規則不支援警告模式。</span><span class="sxs-lookup"><span data-stu-id="dc26d-145">Warn mode is not supported for three attack surface reduction rules when you configure them in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="dc26d-146"> (如果使用群組原則來設定攻擊面降低規則，則會支援警告模式。在 Microsoft 端點管理員中設定這些規則時，請 ) 三個規則不支援警告模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dc26d-146">(If you use Group Policy to configure your attack surface reduction rules, warn mode is supported.) The three rules that do not support warn mode when you configure them in Microsoft Endpoint Manager are as follows:</span></span>

- <span data-ttu-id="dc26d-147">[封鎖 JavaScript 或 VBScript 啟動下載的可執行內容](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`) </span><span class="sxs-lookup"><span data-stu-id="dc26d-147">[Block JavaScript or VBScript from launching downloaded executable content](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)</span></span>
- <span data-ttu-id="dc26d-148">[透過 WMI 事件訂閱封鎖的封鎖](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`) </span><span class="sxs-lookup"><span data-stu-id="dc26d-148">[Block persistence through WMI event subscription](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)</span></span>
- <span data-ttu-id="dc26d-149">[使用針對勒索軟體](#use-advanced-protection-against-ransomware) (GUID 的高級防護 `c1db55ab-c21a-4637-bb3f-a12568109d35`) </span><span class="sxs-lookup"><span data-stu-id="dc26d-149">[Use advanced protection against ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)</span></span>

<span data-ttu-id="dc26d-150">此外，執行舊版 Windows 的裝置不支援警告模式。</span><span class="sxs-lookup"><span data-stu-id="dc26d-150">In addition, warn mode is not supported on devices running older versions of Windows.</span></span> <span data-ttu-id="dc26d-151">在這種情況下，已設定為在警告模式中執行的攻擊面降規則會以封鎖模式執行。</span><span class="sxs-lookup"><span data-stu-id="dc26d-151">In those cases, attack surface reduction rules that are configured to run in warn mode will run in block mode.</span></span>

## <a name="notifications-and-alerts"></a><span data-ttu-id="dc26d-152">通知與提醒</span><span class="sxs-lookup"><span data-stu-id="dc26d-152">Notifications and alerts</span></span>

<span data-ttu-id="dc26d-153">每當觸發攻擊面降低規則時，就會在裝置上顯示通知。</span><span class="sxs-lookup"><span data-stu-id="dc26d-153">Whenever an attack surface reduction rule is triggered, a notification is displayed on the device.</span></span> <span data-ttu-id="dc26d-154">您可以 [自訂](customize-attack-surface-reduction.md#customize-the-notification) 您公司詳細資料和連絡人資訊的通知。</span><span class="sxs-lookup"><span data-stu-id="dc26d-154">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span>

<span data-ttu-id="dc26d-155">此外，當觸發某些攻擊面降低規則時，會產生警示。</span><span class="sxs-lookup"><span data-stu-id="dc26d-155">In addition, when certain attack surface reduction rules are triggered, alerts are generated.</span></span>

<span data-ttu-id="dc26d-156">您可以在 Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 和 microsoft 365 Security center () 中查看所產生的通知和任何警示 [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="dc26d-156">Notifications and any alerts that are generated can be viewed in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and in the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span>

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a><span data-ttu-id="dc26d-157">高級搜尋和攻擊面降低事件</span><span class="sxs-lookup"><span data-stu-id="dc26d-157">Advanced hunting and attack surface reduction events</span></span>

<span data-ttu-id="dc26d-158">您可以使用高級搜尋來查看攻擊面降低事件。</span><span class="sxs-lookup"><span data-stu-id="dc26d-158">You can use advanced hunting to view attack surface reduction events.</span></span> <span data-ttu-id="dc26d-159">為了簡化傳入資料的數量，您可以透過高級搜尋查看每小時只有一個唯一的處理常式。</span><span class="sxs-lookup"><span data-stu-id="dc26d-159">To streamline the volume of incoming data, only unique processes for each hour are viewable with advanced hunting.</span></span> <span data-ttu-id="dc26d-160">攻擊面降低事件的時間是在一小時內第一次看到的事件。</span><span class="sxs-lookup"><span data-stu-id="dc26d-160">The time of an attack surface reduction event is the first time that event is seen within the hour.</span></span>

<span data-ttu-id="dc26d-161">例如，假設在 2:00 PM 小時內10台裝置上發生攻擊面降低事件。</span><span class="sxs-lookup"><span data-stu-id="dc26d-161">For example, suppose that an attack surface reduction event occurs on 10 devices during the 2:00 PM hour.</span></span> <span data-ttu-id="dc26d-162">假設第一個事件發生于2:15，最後是2:45。</span><span class="sxs-lookup"><span data-stu-id="dc26d-162">Suppose that the first event occurred at 2:15, and the last at 2:45.</span></span> <span data-ttu-id="dc26d-163">使用高級搜尋時，您會看到該事件的一個實例 (，即使它實際發生于10個裝置) 上，而且其時間戳記會是 2:15 PM。</span><span class="sxs-lookup"><span data-stu-id="dc26d-163">With advanced hunting, you'll see one instance of that event (even though it actually occurred on 10 devices), and its timestamp will be 2:15 PM.</span></span>

<span data-ttu-id="dc26d-164">如需有關高級搜尋的詳細資訊，請參閱 [使用高級搜尋主動搜尋威脅](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="dc26d-164">For more information about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="attack-surface-reduction-features-across-windows-versions"></a><span data-ttu-id="dc26d-165">跨 Windows 版本的攻擊面減少功能</span><span class="sxs-lookup"><span data-stu-id="dc26d-165">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="dc26d-166">您可以針對執行下列任何版本的 Windows 裝置，設定攻擊面減少規則：</span><span class="sxs-lookup"><span data-stu-id="dc26d-166">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="dc26d-167">Windows 10 專業 [版，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-167">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="dc26d-168">Windows 10 企業 [版，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-168">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="dc26d-169">Windows Server， [版本 1803 (半年通道) ](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 或更新版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-169">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="dc26d-170">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-170">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="dc26d-171">雖然攻擊面降減規則不需要 [Windows e5 授權](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses)，但如果您有 windows e5，您就會取得高級管理功能。</span><span class="sxs-lookup"><span data-stu-id="dc26d-171">Although attack surface reduction rules don't require a [Windows E5 license](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="dc26d-172">這些功能僅適用于 Windows E5，包含可用於 [端點的](microsoft-defender-endpoint.md)監控、分析和工作流程，以及 [Microsoft 365 security center](https://docs.microsoft.com/microsoft-365/security/defender/overview-security-center)中的報告和設定功能。</span><span class="sxs-lookup"><span data-stu-id="dc26d-172">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](microsoft-defender-endpoint.md), as well as reporting and configuration capabilities in the [Microsoft 365 security center](https://docs.microsoft.com/microsoft-365/security/defender/overview-security-center).</span></span> <span data-ttu-id="dc26d-173">Windows Professional 或 Windows E3 授權無法使用這些高級功能;不過，如果您有這些授權，您可以使用 [事件檢視器] 和 [Microsoft Defender 防病毒記錄] 來查看攻擊面減少規則事件。</span><span class="sxs-lookup"><span data-stu-id="dc26d-173">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

## <a name="review-attack-surface-reduction-events-in-the-microsoft-defender-security-center"></a><span data-ttu-id="dc26d-174">在 Microsoft Defender 安全中心檢查攻擊面減少事件</span><span class="sxs-lookup"><span data-stu-id="dc26d-174">Review attack surface reduction events in the Microsoft Defender Security Center</span></span>

<span data-ttu-id="dc26d-175">當警示調查案例中，Defender for Endpoint 提供事件和區塊的詳細報告。</span><span class="sxs-lookup"><span data-stu-id="dc26d-175">Defender for Endpoint provides detailed reporting for events and blocks as part of alert investigation scenarios.</span></span>

<span data-ttu-id="dc26d-176">您可以使用 [ [高級搜尋](advanced-hunting-query-language.md)] 查詢 Defender 的端點資料。</span><span class="sxs-lookup"><span data-stu-id="dc26d-176">You can query Defender for Endpoint data by using [advanced hunting](advanced-hunting-query-language.md).</span></span> <span data-ttu-id="dc26d-177">如果您正在執行 [稽核模式](audit-windows-defender.md)，您可以使用高級搜尋來瞭解攻擊面降低規則如何影響您的環境。</span><span class="sxs-lookup"><span data-stu-id="dc26d-177">If you're running [audit mode](audit-windows-defender.md), you can use advanced hunting to understand how attack surface reduction rules could affect your environment.</span></span>

<span data-ttu-id="dc26d-178">以下是範例查詢：</span><span class="sxs-lookup"><span data-stu-id="dc26d-178">Here is an example query:</span></span>

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="dc26d-179">在 Windows 事件檢視器中查看攻擊面減少事件</span><span class="sxs-lookup"><span data-stu-id="dc26d-179">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="dc26d-180">您可以查看 Windows 事件記錄檔，以查看攻擊面減少規則所產生的事件：</span><span class="sxs-lookup"><span data-stu-id="dc26d-180">You can review the Windows event log to view events generated by attack surface reduction rules:</span></span>

1. <span data-ttu-id="dc26d-181">下載 [評估套件](https://aka.ms/mp7z2w) ，並將檔案 *cfa-events.xml* 解壓至裝置上易於存取的位置。</span><span class="sxs-lookup"><span data-stu-id="dc26d-181">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="dc26d-182">在 [開始] 功能表中輸入文字 [ *事件查看* 器]，以開啟 Windows 事件檢視器。</span><span class="sxs-lookup"><span data-stu-id="dc26d-182">Enter the words, *Event Viewer*, into the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="dc26d-183">在 [ **動作**] 下，選取 [匯 **入自訂視圖 ...**]。</span><span class="sxs-lookup"><span data-stu-id="dc26d-183">Under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="dc26d-184">從解壓縮的位置選取檔案 *cfa-events.xml* 。</span><span class="sxs-lookup"><span data-stu-id="dc26d-184">Select the file *cfa-events.xml* from where it was extracted.</span></span> <span data-ttu-id="dc26d-185">或者， [直接複製 XML](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="dc26d-185">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="dc26d-186">選取 [確定]。</span><span class="sxs-lookup"><span data-stu-id="dc26d-186">Select **OK**.</span></span>

<span data-ttu-id="dc26d-187">您可以建立篩選事件只顯示下列事件的自訂視圖，這些事件都與「受控資料夾存取」有關：</span><span class="sxs-lookup"><span data-stu-id="dc26d-187">You can create a custom view that filters events to only show the following events, all of which are related to controlled folder access:</span></span>

|<span data-ttu-id="dc26d-188">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="dc26d-188">Event ID</span></span>|<span data-ttu-id="dc26d-189">描述</span><span class="sxs-lookup"><span data-stu-id="dc26d-189">Description</span></span>|
|---|---|
|<span data-ttu-id="dc26d-190">5007</span><span class="sxs-lookup"><span data-stu-id="dc26d-190">5007</span></span>|<span data-ttu-id="dc26d-191">設定變更時的事件</span><span class="sxs-lookup"><span data-stu-id="dc26d-191">Event when settings are changed</span></span>|
|<span data-ttu-id="dc26d-192">1121</span><span class="sxs-lookup"><span data-stu-id="dc26d-192">1121</span></span>|<span data-ttu-id="dc26d-193">在組塊模式中激發規則時的事件</span><span class="sxs-lookup"><span data-stu-id="dc26d-193">Event when rule fires in Block-mode</span></span>|
|<span data-ttu-id="dc26d-194">1122</span><span class="sxs-lookup"><span data-stu-id="dc26d-194">1122</span></span>|<span data-ttu-id="dc26d-195">在稽核模式中觸發規則時的事件</span><span class="sxs-lookup"><span data-stu-id="dc26d-195">Event when rule fires in Audit-mode</span></span>|
|

<span data-ttu-id="dc26d-196">在事件記錄中，列出的攻擊面降低事件的「引擎版本」是由 Defender for Endpoint 所產生，而不是由作業系統產生。</span><span class="sxs-lookup"><span data-stu-id="dc26d-196">The "engine version" listed for attack surface reduction events in the event log, is generated by Defender for Endpoint, not by the operating system.</span></span> <span data-ttu-id="dc26d-197">與 Windows 10 整合的端點，所以此功能可在安裝了 Windows 10 的所有裝置上運作。</span><span class="sxs-lookup"><span data-stu-id="dc26d-197">Defender for Endpoint is integrated with Windows 10, so this feature works on all devices with Windows 10 installed.</span></span>

## <a name="attack-surface-reduction-rules"></a><span data-ttu-id="dc26d-198">受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="dc26d-198">Attack surface reduction rules</span></span>

<span data-ttu-id="dc26d-199">下表與子小節分別說明15個攻擊面降減規則。</span><span class="sxs-lookup"><span data-stu-id="dc26d-199">The following table and subsections describe each of the 15 attack surface reduction rules.</span></span> <span data-ttu-id="dc26d-200">攻擊面降低規則會依規則名稱依字母順序列出。</span><span class="sxs-lookup"><span data-stu-id="dc26d-200">The attack surface reduction rules are listed in alphabetical order, by rule name.</span></span>

<span data-ttu-id="dc26d-201">如果您是使用群組原則或 PowerShell 來設定攻擊面降低規則，則需要 Guid。</span><span class="sxs-lookup"><span data-stu-id="dc26d-201">If you are configuring attack surface reduction rules by using Group Policy or PowerShell, you'll need the GUIDs.</span></span> <span data-ttu-id="dc26d-202">另一方面，如果您使用 Microsoft 端點管理員或 Microsoft Intune，您不需要 Guid。</span><span class="sxs-lookup"><span data-stu-id="dc26d-202">On the other hand, if you use Microsoft Endpoint Manager or Microsoft Intune, you do not need the GUIDs.</span></span>

|<span data-ttu-id="dc26d-203">規則名稱</span><span class="sxs-lookup"><span data-stu-id="dc26d-203">Rule name</span></span>|<span data-ttu-id="dc26d-204">GUID</span><span class="sxs-lookup"><span data-stu-id="dc26d-204">GUID</span></span>|<span data-ttu-id="dc26d-205">File & 資料夾排除</span><span class="sxs-lookup"><span data-stu-id="dc26d-205">File & folder exclusions</span></span>|<span data-ttu-id="dc26d-206">支援的最低作業系統</span><span class="sxs-lookup"><span data-stu-id="dc26d-206">Minimum OS supported</span></span>|
|---|:---:|---|---|
|[<span data-ttu-id="dc26d-207">封鎖 Adobe Reader，以建立子流程</span><span class="sxs-lookup"><span data-stu-id="dc26d-207">Block Adobe Reader from creating child processes</span></span>](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|<span data-ttu-id="dc26d-208">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-208">Supported</span></span>|<span data-ttu-id="dc26d-209">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-209">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="dc26d-210">封鎖所有 Office 應用程式以建立子流程</span><span class="sxs-lookup"><span data-stu-id="dc26d-210">Block all Office applications from creating child processes</span></span>](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|<span data-ttu-id="dc26d-211">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-211">Supported</span></span>|<span data-ttu-id="dc26d-212">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-212">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="dc26d-213">從 Windows local security 機關子系統封鎖認證竊取 (lsass.exe) </span><span class="sxs-lookup"><span data-stu-id="dc26d-213">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|<span data-ttu-id="dc26d-214">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-214">Supported</span></span>|<span data-ttu-id="dc26d-215">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-215">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="dc26d-216">從電子郵件客戶程式和 web 郵件封鎖可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="dc26d-216">Block executable content from email client and webmail</span></span>](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|<span data-ttu-id="dc26d-217">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-217">Supported</span></span>|<span data-ttu-id="dc26d-218">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-218">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="dc26d-219">封鎖可執行檔，除非符合流行、age 或受信任的清單準則</span><span class="sxs-lookup"><span data-stu-id="dc26d-219">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|<span data-ttu-id="dc26d-220">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-220">Supported</span></span>|<span data-ttu-id="dc26d-221">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-221">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="dc26d-222">封鎖可能混淆的腳本執行</span><span class="sxs-lookup"><span data-stu-id="dc26d-222">Block execution of potentially obfuscated scripts</span></span>](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|<span data-ttu-id="dc26d-223">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-223">Supported</span></span>|<span data-ttu-id="dc26d-224">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-224">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="dc26d-225">從啟動下載的可執行內容封鎖 JavaScript 或 VBScript</span><span class="sxs-lookup"><span data-stu-id="dc26d-225">Block JavaScript or VBScript from launching downloaded executable content</span></span>](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|<span data-ttu-id="dc26d-226">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-226">Supported</span></span>|<span data-ttu-id="dc26d-227">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-227">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="dc26d-228">封鎖 Office 應用程式建立可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="dc26d-228">Block Office applications from creating executable content</span></span>](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|<span data-ttu-id="dc26d-229">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-229">Supported</span></span>|<span data-ttu-id="dc26d-230">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-230">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="dc26d-231">封鎖 Office 應用程式將程式碼注入其他程式</span><span class="sxs-lookup"><span data-stu-id="dc26d-231">Block Office applications from injecting code into other processes</span></span>](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|<span data-ttu-id="dc26d-232">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-232">Supported</span></span>|<span data-ttu-id="dc26d-233">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-233">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="dc26d-234">封鎖 Office communication application 建立子流程</span><span class="sxs-lookup"><span data-stu-id="dc26d-234">Block Office communication application from creating child processes</span></span>](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|<span data-ttu-id="dc26d-235">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-235">Supported</span></span>|<span data-ttu-id="dc26d-236">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-236">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="dc26d-237">透過 WMI 事件訂閱封鎖持久性</span><span class="sxs-lookup"><span data-stu-id="dc26d-237">Block persistence through WMI event subscription</span></span>](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|<span data-ttu-id="dc26d-238">不支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-238">Not supported</span></span>|<span data-ttu-id="dc26d-239">[Windows 10，版本 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) (組建 18362) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-239">[Windows 10, version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) or greater</span></span>|
|[<span data-ttu-id="dc26d-240">封鎖來自 PSExec 和 WMI 命令的進程建立</span><span class="sxs-lookup"><span data-stu-id="dc26d-240">Block process creations originating from PSExec and WMI commands</span></span>](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|<span data-ttu-id="dc26d-241">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-241">Supported</span></span>|<span data-ttu-id="dc26d-242">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-242">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="dc26d-243">封鎖從 USB 執行的不受信任和未簽署程式</span><span class="sxs-lookup"><span data-stu-id="dc26d-243">Block untrusted and unsigned processes that run from USB</span></span>](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|<span data-ttu-id="dc26d-244">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-244">Supported</span></span>|<span data-ttu-id="dc26d-245">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-245">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="dc26d-246">封鎖 Office 宏的 WIN32 API 呼叫</span><span class="sxs-lookup"><span data-stu-id="dc26d-246">Block Win32 API calls from Office macros</span></span>](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|<span data-ttu-id="dc26d-247">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-247">Supported</span></span>|<span data-ttu-id="dc26d-248">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-248">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="dc26d-249">使用勒索軟體的高級防護</span><span class="sxs-lookup"><span data-stu-id="dc26d-249">Use advanced protection against ransomware</span></span>](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|<span data-ttu-id="dc26d-250">支援</span><span class="sxs-lookup"><span data-stu-id="dc26d-250">Supported</span></span>|<span data-ttu-id="dc26d-251">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc26d-251">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|

### <a name="block-adobe-reader-from-creating-child-processes"></a><span data-ttu-id="dc26d-252">封鎖 Adobe Reader，以建立子流程</span><span class="sxs-lookup"><span data-stu-id="dc26d-252">Block Adobe Reader from creating child processes</span></span>

<span data-ttu-id="dc26d-253">此規則會封鎖來自 Adobe Reader 的攻擊，使其無法建立處理常式。</span><span class="sxs-lookup"><span data-stu-id="dc26d-253">This rule prevents attacks by blocking Adobe Reader from creating processes.</span></span>

<span data-ttu-id="dc26d-254">透過社交工程或利用方式，惡意程式碼可以下載和啟動有效載荷，並中斷 Adobe Reader。</span><span class="sxs-lookup"><span data-stu-id="dc26d-254">Through social engineering or exploits, malware can download and launch payloads, and break out of Adobe Reader.</span></span> <span data-ttu-id="dc26d-255">透過封鎖子流程以供 Adobe Reader 的產生，惡意程式碼嘗試使用它做為向量，便無法散佈。</span><span class="sxs-lookup"><span data-stu-id="dc26d-255">By blocking child processes from being generated by Adobe Reader, malware attempting to use it as a vector are prevented from spreading.</span></span>

<span data-ttu-id="dc26d-256">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-256">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-257">Windows 10，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-257">Windows 10, version 1809</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="dc26d-258">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-258">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-259">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-259">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="dc26d-260">Intune 名稱： `Process creation from Adobe Reader (beta)`</span><span class="sxs-lookup"><span data-stu-id="dc26d-260">Intune name: `Process creation from Adobe Reader (beta)`</span></span>

<span data-ttu-id="dc26d-261">Configuration Manager 名稱：尚未提供</span><span class="sxs-lookup"><span data-stu-id="dc26d-261">Configuration Manager name: Not yet available</span></span>

<span data-ttu-id="dc26d-262">GUID:： `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span><span class="sxs-lookup"><span data-stu-id="dc26d-262">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span></span>

### <a name="block-all-office-applications-from-creating-child-processes"></a><span data-ttu-id="dc26d-263">封鎖所有 Office 應用程式以建立子流程</span><span class="sxs-lookup"><span data-stu-id="dc26d-263">Block all Office applications from creating child processes</span></span>

<span data-ttu-id="dc26d-264">此規則會封鎖 Office 應用程式建立子流程。</span><span class="sxs-lookup"><span data-stu-id="dc26d-264">This rule blocks Office apps from creating child processes.</span></span> <span data-ttu-id="dc26d-265">Office 應用程式包括 Word、Excel、PowerPoint、OneNote 和 Access。</span><span class="sxs-lookup"><span data-stu-id="dc26d-265">Office apps include Word, Excel, PowerPoint, OneNote, and Access.</span></span>

<span data-ttu-id="dc26d-266">建立惡意的子流程是常見的惡意程式碼策略。</span><span class="sxs-lookup"><span data-stu-id="dc26d-266">Creating malicious child processes is a common malware strategy.</span></span> <span data-ttu-id="dc26d-267">濫用 Office 視為向量的惡意程式碼，通常會執行 VBA 宏，並利用程式碼下載並嘗試執行更多負載。</span><span class="sxs-lookup"><span data-stu-id="dc26d-267">Malware that abuse Office as a vector often run VBA macros and exploit code to download and attempt to run more payloads.</span></span> <span data-ttu-id="dc26d-268">不過，某些合法的企業營運應用程式也可能會產生良性目的的子流程，例如產生命令提示字元或使用 PowerShell 來設定登錄設定。</span><span class="sxs-lookup"><span data-stu-id="dc26d-268">However, some legitimate line-of-business applications might also generate child processes for benign purposes, such as spawning a command prompt or using PowerShell to configure registry settings.</span></span>

<span data-ttu-id="dc26d-269">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-269">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-270">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="dc26d-270">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="dc26d-271">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-271">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-272">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-272">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="dc26d-273">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="dc26d-273">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="dc26d-274">Intune 名稱： `Office apps launching child processes`</span><span class="sxs-lookup"><span data-stu-id="dc26d-274">Intune name: `Office apps launching child processes`</span></span>

<span data-ttu-id="dc26d-275">Configuration Manager 名稱： `Block Office application from creating child processes`</span><span class="sxs-lookup"><span data-stu-id="dc26d-275">Configuration Manager name: `Block Office application from creating child processes`</span></span>

<span data-ttu-id="dc26d-276">GUID:： `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span><span class="sxs-lookup"><span data-stu-id="dc26d-276">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span></span>

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a><span data-ttu-id="dc26d-277">從 Windows local security 機關子系統封鎖認證竊取</span><span class="sxs-lookup"><span data-stu-id="dc26d-277">Block credential stealing from the Windows local security authority subsystem</span></span>

<span data-ttu-id="dc26d-278">此規則會透過鎖定本機 Security 機關子系統服務 (LSASS) ，協助防止身分憑證竊取。</span><span class="sxs-lookup"><span data-stu-id="dc26d-278">This rule helps prevent credential stealing, by locking down Local Security Authority Subsystem Service (LSASS).</span></span>

<span data-ttu-id="dc26d-279">LSASS 驗證在 Windows 電腦上登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="dc26d-279">LSASS authenticates users who sign in on a Windows computer.</span></span> <span data-ttu-id="dc26d-280">Windows 10 中的 Microsoft Defender Credential Guard 通常會防止嘗試從 LSASS 提取認證。</span><span class="sxs-lookup"><span data-stu-id="dc26d-280">Microsoft Defender Credential Guard in Windows 10 normally prevents attempts to extract credentials from LSASS.</span></span> <span data-ttu-id="dc26d-281">不過，某些組織無法在其所有電腦上啟用認證防護，因為自訂的智慧卡驅動程式或其他載入至本機安全授權的程式的相容性問題 (LSA) 。</span><span class="sxs-lookup"><span data-stu-id="dc26d-281">However, some organizations can't enable Credential Guard on all of their computers because of compatibility issues with custom smartcard drivers or other programs that load into the Local Security Authority (LSA).</span></span> <span data-ttu-id="dc26d-282">在這些情況下，攻擊者可以使用像是 Mimikatz 的駭客攻擊工具，從 LSASS scrape 純文字密碼和 NTLM 雜湊。</span><span class="sxs-lookup"><span data-stu-id="dc26d-282">In these cases, attackers can use hack tools like Mimikatz to scrape cleartext passwords and NTLM hashes from LSASS.</span></span>

> [!NOTE]
> <span data-ttu-id="dc26d-283">在某些應用程式中，此程式碼會列舉所有執行中的程式，並嘗試以詳盡的許可權來開啟這些進程。</span><span class="sxs-lookup"><span data-stu-id="dc26d-283">In some apps, the code enumerates all running processes and attempts to open them with exhaustive permissions.</span></span> <span data-ttu-id="dc26d-284">此規則會拒絕應用程式的「開啟」動作，並將詳細資料記錄到安全性事件記錄檔。</span><span class="sxs-lookup"><span data-stu-id="dc26d-284">This rule denies the app's process open action and logs the details to the security event log.</span></span> <span data-ttu-id="dc26d-285">此規則會產生大量的噪音。</span><span class="sxs-lookup"><span data-stu-id="dc26d-285">This rule can generate a lot of noise.</span></span> <span data-ttu-id="dc26d-286">如果您有一個應用程式，只列舉 LSASS，但沒有任何實際的功能影響，便不需要將其新增至排除清單。</span><span class="sxs-lookup"><span data-stu-id="dc26d-286">If you have an app that simply enumerates LSASS, but has no real impact in functionality, there is NO need to add it to the exclusion list.</span></span> <span data-ttu-id="dc26d-287">這個事件記錄專案本身不一定表示惡意威脅。</span><span class="sxs-lookup"><span data-stu-id="dc26d-287">By itself, this event log entry doesn't necessarily indicate a malicious threat.</span></span>

<span data-ttu-id="dc26d-288">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-288">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-289">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="dc26d-289">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="dc26d-290">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-290">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-291">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-291">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="dc26d-292">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="dc26d-292">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="dc26d-293">Intune 名稱： `Flag credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="dc26d-293">Intune name: `Flag credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="dc26d-294">Configuration Manager 名稱： `Block credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="dc26d-294">Configuration Manager name: `Block credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="dc26d-295">GUID:： `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span><span class="sxs-lookup"><span data-stu-id="dc26d-295">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span></span>

### <a name="block-executable-content-from-email-client-and-webmail"></a><span data-ttu-id="dc26d-296">從電子郵件客戶程式和 web 郵件封鎖可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="dc26d-296">Block executable content from email client and webmail</span></span>

<span data-ttu-id="dc26d-297">此規則會封鎖下列檔案類型：從 Microsoft Outlook 應用程式內開啟的電子郵件，或 Outlook.com 及其他常用的電子郵件提供者進行啟動：</span><span class="sxs-lookup"><span data-stu-id="dc26d-297">This rule blocks the following file types from launching from email opened within the Microsoft Outlook application, or Outlook.com and other popular webmail providers:</span></span>

- <span data-ttu-id="dc26d-298">可執行檔 (例如 .exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="dc26d-298">Executable files (such as .exe, .dll, or .scr)</span></span>
- <span data-ttu-id="dc26d-299">腳本檔案 (例如 PowerShell .ps、Visual Basic .vbs 或 JavaScript .js 檔案) </span><span class="sxs-lookup"><span data-stu-id="dc26d-299">Script files (such as a PowerShell .ps, Visual Basic .vbs, or JavaScript .js file)</span></span>

<span data-ttu-id="dc26d-300">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-300">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-301">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="dc26d-301">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="dc26d-302">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-302">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-303">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-303">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="dc26d-304">Microsoft 端點管理員 CB 1710</span><span class="sxs-lookup"><span data-stu-id="dc26d-304">Microsoft Endpoint Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="dc26d-305">Intune 名稱： `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="dc26d-305">Intune name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span></span>

<span data-ttu-id="dc26d-306">Microsoft 端點管理員名稱： `Block executable content from email client and webmail`</span><span class="sxs-lookup"><span data-stu-id="dc26d-306">Microsoft Endpoint Manager name: `Block executable content from email client and webmail`</span></span>

<span data-ttu-id="dc26d-307">GUID:： `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span><span class="sxs-lookup"><span data-stu-id="dc26d-307">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span></span>

> [!NOTE]
> <span data-ttu-id="dc26d-308">**從電子郵件客戶程式和 web 郵件封鎖可執行檔內容**，具有下列替代描述（取決於您所使用的應用程式）：</span><span class="sxs-lookup"><span data-stu-id="dc26d-308">The rule **Block executable content from email client and webmail** has the following alternative descriptions, depending on which application you use:</span></span>
>
> - <span data-ttu-id="dc26d-309">Intune (設定檔) ：執行可執行檔內容 (exe、dll、ps、js、vbs 等 ) 從電子郵件 (郵件) web 郵件用戶端 () 沒有例外。</span><span class="sxs-lookup"><span data-stu-id="dc26d-309">Intune (Configuration Profiles): Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions).</span></span>
> - <span data-ttu-id="dc26d-310">端點管理員：封鎖電子郵件和電子郵件用戶端的可執行內容下載。</span><span class="sxs-lookup"><span data-stu-id="dc26d-310">Endpoint Manager: Block executable content download from email and webmail clients.</span></span>
> - <span data-ttu-id="dc26d-311">群組原則：從電子郵件客戶程式和 web 郵件封鎖可執行檔內容。</span><span class="sxs-lookup"><span data-stu-id="dc26d-311">Group Policy: Block executable content from email client and webmail.</span></span>

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a><span data-ttu-id="dc26d-312">封鎖可執行檔，除非符合流行、age 或受信任的清單準則</span><span class="sxs-lookup"><span data-stu-id="dc26d-312">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>

<span data-ttu-id="dc26d-313">此規則會封鎖下列檔案類型的啟動，除非它們符合流行或年齡準則，或是位於信任清單或排除清單中：</span><span class="sxs-lookup"><span data-stu-id="dc26d-313">This rule blocks the following file types from launching unless they meet prevalence or age criteria, or they're in a trusted list or an exclusion list:</span></span>

- <span data-ttu-id="dc26d-314">可執行檔 (例如 .exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="dc26d-314">Executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="dc26d-315">啟動不受信任或未知的可執行檔可能會是危險的，因為如果這些檔案是惡意的，就可能不會進行這種情況。</span><span class="sxs-lookup"><span data-stu-id="dc26d-315">Launching untrusted or unknown executable files can be risky, as it may not be initially clear if the files are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc26d-316">您必須 [啟用雲端提供的保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 才能使用此規則。</span><span class="sxs-lookup"><span data-stu-id="dc26d-316">You must [enable cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>
>
> <span data-ttu-id="dc26d-317">規則會 **封鎖可執行檔，除非符合** 「具有 GUID 的流行」、「年齡」或「受信任」清單準則， `01443614-cd74-433a-b99e-2ecdc07bfc25` 且不是由系統管理員所指定的狀態。</span><span class="sxs-lookup"><span data-stu-id="dc26d-317">The rule **Block executable files from running unless they meet a prevalence, age, or trusted list criterion** with GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` is owned by Microsoft and is not specified by admins.</span></span> <span data-ttu-id="dc26d-318">此規則使用雲端提供的保護，定期更新其信任清單。</span><span class="sxs-lookup"><span data-stu-id="dc26d-318">This rule uses cloud-delivered protection to update its trusted list regularly.</span></span>
>
> <span data-ttu-id="dc26d-319">您可以使用資料夾路徑或完全限定的資源名稱來指定個別檔案或資料夾 () 但是您無法指定適用的規則或排除專案。</span><span class="sxs-lookup"><span data-stu-id="dc26d-319">You can specify individual files or folders (using folder paths or fully qualified resource names) but you can't specify which rules or exclusions apply to.</span></span>

<span data-ttu-id="dc26d-320">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-320">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-321">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="dc26d-321">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="dc26d-322">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-322">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-323">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-323">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="dc26d-324">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="dc26d-324">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="dc26d-325">Intune 名稱： `Executables that don't meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="dc26d-325">Intune name: `Executables that don't meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="dc26d-326">Configuration Manager 名稱： `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="dc26d-326">Configuration Manager name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="dc26d-327">GUID:： `01443614-cd74-433a-b99e-2ecdc07bfc25`</span><span class="sxs-lookup"><span data-stu-id="dc26d-327">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span></span>

### <a name="block-execution-of-potentially-obfuscated-scripts"></a><span data-ttu-id="dc26d-328">封鎖可能混淆的腳本執行</span><span class="sxs-lookup"><span data-stu-id="dc26d-328">Block execution of potentially obfuscated scripts</span></span>

<span data-ttu-id="dc26d-329">此規則會偵測模糊腳本中的可疑屬性。</span><span class="sxs-lookup"><span data-stu-id="dc26d-329">This rule detects suspicious properties within an obfuscated script.</span></span>

<span data-ttu-id="dc26d-330">腳本模糊處理是一種常見的技術，惡意程式碼作者和合法的應用程式都使用它來隱藏知識屬性或減少腳本載入時間。</span><span class="sxs-lookup"><span data-stu-id="dc26d-330">Script obfuscation is a common technique that both malware authors and legitimate applications use to hide intellectual property or decrease script loading times.</span></span> <span data-ttu-id="dc26d-331">惡意程式碼作者也會使用模糊處理，使惡意程式碼難以閱讀，這可防止人員和安全性軟體的接近審查。</span><span class="sxs-lookup"><span data-stu-id="dc26d-331">Malware authors also use obfuscation to make malicious code harder to read, which prevents close scrutiny by humans and security software.</span></span>

<span data-ttu-id="dc26d-332">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-332">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-333">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="dc26d-333">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="dc26d-334">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-334">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-335">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-335">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="dc26d-336">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="dc26d-336">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="dc26d-337">Intune 名稱： `Obfuscated js/vbs/ps/macro code`</span><span class="sxs-lookup"><span data-stu-id="dc26d-337">Intune name: `Obfuscated js/vbs/ps/macro code`</span></span>

<span data-ttu-id="dc26d-338">Configuration Manager 名稱： `Block execution of potentially obfuscated scripts`</span><span class="sxs-lookup"><span data-stu-id="dc26d-338">Configuration Manager name: `Block execution of potentially obfuscated scripts`</span></span>

<span data-ttu-id="dc26d-339">GUID:： `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span><span class="sxs-lookup"><span data-stu-id="dc26d-339">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span></span>

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a><span data-ttu-id="dc26d-340">從啟動下載的可執行內容封鎖 JavaScript 或 VBScript</span><span class="sxs-lookup"><span data-stu-id="dc26d-340">Block JavaScript or VBScript from launching downloaded executable content</span></span>

<span data-ttu-id="dc26d-341">此規則可防止腳本啟動可能已下載的惡意內容。</span><span class="sxs-lookup"><span data-stu-id="dc26d-341">This rule prevents scripts from launching potentially malicious downloaded content.</span></span> <span data-ttu-id="dc26d-342">撰寫在 JavaScript 或 VBScript 中的惡意程式碼通常是可從網際網路取得及啟動其他惡意程式碼的下載宏。</span><span class="sxs-lookup"><span data-stu-id="dc26d-342">Malware written in JavaScript or VBScript often acts as a downloader to fetch and launch other malware from the Internet.</span></span>

<span data-ttu-id="dc26d-343">雖然不是常見的企業營運應用程式，但有時會使用腳本下載及啟動安裝程式。</span><span class="sxs-lookup"><span data-stu-id="dc26d-343">Although not common, line-of-business applications sometimes use scripts to download and launch installers.</span></span>

<span data-ttu-id="dc26d-344">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-344">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-345">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="dc26d-345">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="dc26d-346">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-346">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-347">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-347">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="dc26d-348">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="dc26d-348">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="dc26d-349">Intune 名稱： `js/vbs executing payload downloaded from Internet (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="dc26d-349">Intune name: `js/vbs executing payload downloaded from Internet (no exceptions)`</span></span>

<span data-ttu-id="dc26d-350">Configuration Manager 名稱： `Block JavaScript or VBScript from launching downloaded executable content`</span><span class="sxs-lookup"><span data-stu-id="dc26d-350">Configuration Manager name: `Block JavaScript or VBScript from launching downloaded executable content`</span></span>

<span data-ttu-id="dc26d-351">GUID:： `D3E037E1-3EB8-44C8-A917-57927947596D`</span><span class="sxs-lookup"><span data-stu-id="dc26d-351">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span></span>

### <a name="block-office-applications-from-creating-executable-content"></a><span data-ttu-id="dc26d-352">封鎖 Office 應用程式建立可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="dc26d-352">Block Office applications from creating executable content</span></span>

<span data-ttu-id="dc26d-353">此規則可防止 Office 應用程式（包括 Word、Excel 及 PowerPoint）建立潛在的惡意可執行檔內容，方法是封鎖惡意程式碼，使其無法寫入磁片。</span><span class="sxs-lookup"><span data-stu-id="dc26d-353">This rule prevents Office apps, including Word, Excel, and PowerPoint, from creating potentially malicious executable content, by blocking malicious code from being written to disk.</span></span>

<span data-ttu-id="dc26d-354">濫用 Office 視為向量的惡意程式碼可能會嘗試中斷 Office，並將惡意元件儲存至磁片。</span><span class="sxs-lookup"><span data-stu-id="dc26d-354">Malware that abuses Office as a vector may attempt to break out of Office and save malicious components to disk.</span></span> <span data-ttu-id="dc26d-355">這些惡意元件會在電腦重新開機後，在系統上持續保存下來。</span><span class="sxs-lookup"><span data-stu-id="dc26d-355">These malicious components would survive a computer reboot and persist on the system.</span></span> <span data-ttu-id="dc26d-356">因此，此規則會防禦一般的持久性技術。</span><span class="sxs-lookup"><span data-stu-id="dc26d-356">Therefore, this rule defends against a common persistence technique.</span></span>

<span data-ttu-id="dc26d-357">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-357">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-358">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="dc26d-358">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="dc26d-359">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-359">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-360">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-360">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- <span data-ttu-id="dc26d-361">[System Center Configuration manager](https://docs.microsoft.com/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM 現在是 Microsoft 端點 Configuration Manager) </span><span class="sxs-lookup"><span data-stu-id="dc26d-361">[System Center Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM is now Microsoft Endpoint Configuration Manager)</span></span>

<span data-ttu-id="dc26d-362">Intune 名稱： `Office apps/macros creating executable content`</span><span class="sxs-lookup"><span data-stu-id="dc26d-362">Intune name: `Office apps/macros creating executable content`</span></span>

<span data-ttu-id="dc26d-363">SCCM 名稱： `Block Office applications from creating executable content`</span><span class="sxs-lookup"><span data-stu-id="dc26d-363">SCCM name: `Block Office applications from creating executable content`</span></span>

<span data-ttu-id="dc26d-364">GUID:： `3B576869-A4EC-4529-8536-B80A7769E899`</span><span class="sxs-lookup"><span data-stu-id="dc26d-364">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span></span>

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a><span data-ttu-id="dc26d-365">封鎖 Office 應用程式將程式碼注入其他程式</span><span class="sxs-lookup"><span data-stu-id="dc26d-365">Block Office applications from injecting code into other processes</span></span>

<span data-ttu-id="dc26d-366">此規則會封鎖從 Office 應用程式到其他程式的程式碼插入嘗試。</span><span class="sxs-lookup"><span data-stu-id="dc26d-366">This rule blocks code injection attempts from Office apps into other processes.</span></span>

<span data-ttu-id="dc26d-367">攻擊者可能會嘗試使用 Office 應用程式，透過程式碼注入，將惡意程式碼遷移到其他程式中，讓程式碼可以偽裝成一種乾淨的處理常式。</span><span class="sxs-lookup"><span data-stu-id="dc26d-367">Attackers might attempt to use Office apps to migrate malicious code into other processes through code injection, so the code can masquerade as a clean process.</span></span>

<span data-ttu-id="dc26d-368">使用程式碼注入，並沒有已知的合法商務目的。</span><span class="sxs-lookup"><span data-stu-id="dc26d-368">There are no known legitimate business purposes for using code injection.</span></span>

<span data-ttu-id="dc26d-369">此規則適用于 Word、Excel 及 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="dc26d-369">This rule applies to Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="dc26d-370">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-370">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-371">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="dc26d-371">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="dc26d-372">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-372">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-373">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-373">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="dc26d-374">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="dc26d-374">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="dc26d-375">Intune 名稱： `Office apps injecting code into other processes (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="dc26d-375">Intune name: `Office apps injecting code into other processes (no exceptions)`</span></span>

<span data-ttu-id="dc26d-376">Configuration Manager 名稱： `Block Office applications from injecting code into other processes`</span><span class="sxs-lookup"><span data-stu-id="dc26d-376">Configuration Manager name: `Block Office applications from injecting code into other processes`</span></span>

<span data-ttu-id="dc26d-377">GUID:： `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span><span class="sxs-lookup"><span data-stu-id="dc26d-377">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span></span>

### <a name="block-office-communication-application-from-creating-child-processes"></a><span data-ttu-id="dc26d-378">封鎖 Office communication application 建立子流程</span><span class="sxs-lookup"><span data-stu-id="dc26d-378">Block Office communication application from creating child processes</span></span>

<span data-ttu-id="dc26d-379">此規則可防止 Outlook 建立子流程，但仍然允許合法的 Outlook 功能。</span><span class="sxs-lookup"><span data-stu-id="dc26d-379">This rule prevents Outlook from creating child processes, while still allowing legitimate Outlook functions.</span></span>

<span data-ttu-id="dc26d-380">此規則可防止社交工程攻擊，並防止在 Outlook 中利用 abusing 弱點的程式碼。</span><span class="sxs-lookup"><span data-stu-id="dc26d-380">This rule protects against social engineering attacks and prevents exploiting code from abusing vulnerabilities in Outlook.</span></span> <span data-ttu-id="dc26d-381">它也會針對使用者的認證遭到攻破時，防止攻擊者可使用的 [Outlook 規則和表單攻擊](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) 。</span><span class="sxs-lookup"><span data-stu-id="dc26d-381">It also protects against [Outlook rules and forms exploits](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) that attackers can use when a user's credentials are compromised.</span></span>

> [!NOTE]
> <span data-ttu-id="dc26d-382">此規則只適用于 Outlook 和 Outlook.com。</span><span class="sxs-lookup"><span data-stu-id="dc26d-382">This rule applies to Outlook and Outlook.com only.</span></span>

<span data-ttu-id="dc26d-383">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-383">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-384">Windows 10，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-384">Windows 10, version 1809</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="dc26d-385">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-385">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-386">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-386">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="dc26d-387">Intune 名稱： `Process creation from Office communication products (beta)`</span><span class="sxs-lookup"><span data-stu-id="dc26d-387">Intune name: `Process creation from Office communication products (beta)`</span></span>

<span data-ttu-id="dc26d-388">Configuration Manager 名稱：無法使用</span><span class="sxs-lookup"><span data-stu-id="dc26d-388">Configuration Manager name: Not available</span></span>

<span data-ttu-id="dc26d-389">GUID:： `26190899-1602-49e8-8b27-eb1d0a1ce869`</span><span class="sxs-lookup"><span data-stu-id="dc26d-389">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span></span>

### <a name="block-persistence-through-wmi-event-subscription"></a><span data-ttu-id="dc26d-390">透過 WMI 事件訂閱封鎖持久性</span><span class="sxs-lookup"><span data-stu-id="dc26d-390">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="dc26d-391">此規則可防止惡意程式碼 abusing WMI 在裝置上取得持久性。</span><span class="sxs-lookup"><span data-stu-id="dc26d-391">This rule prevents malware from abusing WMI to attain persistence on a device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc26d-392">檔案與資料夾排除不適用於此攻擊面降規則。</span><span class="sxs-lookup"><span data-stu-id="dc26d-392">File and folder exclusions don't apply to this attack surface reduction rule.</span></span>

<span data-ttu-id="dc26d-393">Fileless 威脅使用各種不同的戰術來保持隱藏狀態，以避免在檔案系統中看到，以及取得定期執行控制。</span><span class="sxs-lookup"><span data-stu-id="dc26d-393">Fileless threats employ various tactics to stay hidden, to avoid being seen in the file system, and to gain periodic execution control.</span></span> <span data-ttu-id="dc26d-394">有些威脅可以濫用 WMI 存放庫和事件模型，以保持隱藏狀態。</span><span class="sxs-lookup"><span data-stu-id="dc26d-394">Some threats can abuse the WMI repository and event model to stay hidden.</span></span>

<span data-ttu-id="dc26d-395">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-395">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-396">Windows 10，版本1903</span><span class="sxs-lookup"><span data-stu-id="dc26d-396">Windows 10, version 1903</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903)
- [<span data-ttu-id="dc26d-397">Windows Server 1903</span><span class="sxs-lookup"><span data-stu-id="dc26d-397">Windows Server 1903</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

<span data-ttu-id="dc26d-398">Intune 名稱：無法使用</span><span class="sxs-lookup"><span data-stu-id="dc26d-398">Intune name: Not available</span></span>

<span data-ttu-id="dc26d-399">Configuration Manager 名稱：無法使用</span><span class="sxs-lookup"><span data-stu-id="dc26d-399">Configuration Manager name: Not available</span></span>

<span data-ttu-id="dc26d-400">GUID:： `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span><span class="sxs-lookup"><span data-stu-id="dc26d-400">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span></span>

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a><span data-ttu-id="dc26d-401">封鎖來自 PSExec 和 WMI 命令的進程建立</span><span class="sxs-lookup"><span data-stu-id="dc26d-401">Block process creations originating from PSExec and WMI commands</span></span>

<span data-ttu-id="dc26d-402">此規則會封鎖透過 [PsExec](https://docs.microsoft.com/sysinternals/downloads/psexec) 和 [WMI](https://docs.microsoft.com/windows/win32/wmisdk/about-wmi) 所建立的處理常式執行。</span><span class="sxs-lookup"><span data-stu-id="dc26d-402">This rule blocks processes created through [PsExec](https://docs.microsoft.com/sysinternals/downloads/psexec) and [WMI](https://docs.microsoft.com/windows/win32/wmisdk/about-wmi) from running.</span></span> <span data-ttu-id="dc26d-403">PsExec 和 WMI 都可以遠端執行程式碼，因此惡意程式碼會 abusing 此功能以進行命令和控制，或將感染傳播到整個組織的網路。</span><span class="sxs-lookup"><span data-stu-id="dc26d-403">Both PsExec and WMI can remotely execute code, so there is a risk of malware abusing this functionality for command and control purposes, or to spread an infection throughout an organization's network.</span></span>

> [!WARNING]
> <span data-ttu-id="dc26d-404">只有在您使用 [Intune](https://docs.microsoft.com/intune) 或另一個 MDM 解決方案管理裝置時，才使用此規則。</span><span class="sxs-lookup"><span data-stu-id="dc26d-404">Only use this rule if you're managing your devices with [Intune](https://docs.microsoft.com/intune) or another MDM solution.</span></span> <span data-ttu-id="dc26d-405">這種規則與透過 [Microsoft 端點 Configuration Manager](https://docs.microsoft.com/configmgr) 的管理不相容，因為此規則會封鎖 Configuration manager 用戶端用來正確運作的 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="dc26d-405">This rule is incompatible with management through [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr) because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span>

<span data-ttu-id="dc26d-406">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-406">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-407">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="dc26d-407">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="dc26d-408">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-408">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-409">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-409">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="dc26d-410">Intune 名稱： `Process creation from PSExec and WMI commands`</span><span class="sxs-lookup"><span data-stu-id="dc26d-410">Intune name: `Process creation from PSExec and WMI commands`</span></span>

<span data-ttu-id="dc26d-411">Configuration Manager 名稱：不適用</span><span class="sxs-lookup"><span data-stu-id="dc26d-411">Configuration Manager name: Not applicable</span></span>

<span data-ttu-id="dc26d-412">GUID:： `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span><span class="sxs-lookup"><span data-stu-id="dc26d-412">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span></span>

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a><span data-ttu-id="dc26d-413">封鎖從 USB 執行的不受信任和未簽署程式</span><span class="sxs-lookup"><span data-stu-id="dc26d-413">Block untrusted and unsigned processes that run from USB</span></span>

<span data-ttu-id="dc26d-414">使用此規則時，系統管理員可以防止未簽署或不受信任的可執行檔，從 USB 抽取式磁碟磁碟機（包括 SD 卡）執行。</span><span class="sxs-lookup"><span data-stu-id="dc26d-414">With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.</span></span> <span data-ttu-id="dc26d-415">封鎖的檔案類型包括可執行檔 (例如 .exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="dc26d-415">Blocked file types include executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="dc26d-416">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-416">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-417">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="dc26d-417">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="dc26d-418">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-418">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-419">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-419">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="dc26d-420">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="dc26d-420">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="dc26d-421">Intune 名稱： `Untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="dc26d-421">Intune name: `Untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="dc26d-422">Configuration Manager 名稱： `Block untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="dc26d-422">Configuration Manager name: `Block untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="dc26d-423">GUID:： `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span><span class="sxs-lookup"><span data-stu-id="dc26d-423">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span></span>

### <a name="block-win32-api-calls-from-office-macros"></a><span data-ttu-id="dc26d-424">封鎖 Office 宏的 WIN32 API 呼叫</span><span class="sxs-lookup"><span data-stu-id="dc26d-424">Block Win32 API calls from Office macros</span></span>

<span data-ttu-id="dc26d-425">此規則可防止 VBA 宏呼叫 WIN32 APIs。</span><span class="sxs-lookup"><span data-stu-id="dc26d-425">This rule prevents VBA macros from calling Win32 APIs.</span></span>

<span data-ttu-id="dc26d-426">Office VBA 會啟用 WIN32 API 呼叫。</span><span class="sxs-lookup"><span data-stu-id="dc26d-426">Office VBA enables Win32 API calls.</span></span> <span data-ttu-id="dc26d-427">惡意程式碼可能會濫用這項功能，例如 [呼叫 WIN32 APIs 以發動惡意外殼代碼](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) ，而不需直接寫入任何內容。</span><span class="sxs-lookup"><span data-stu-id="dc26d-427">Malware can abuse this capability, such as [calling Win32 APIs to launch malicious shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) without writing anything directly to disk.</span></span> <span data-ttu-id="dc26d-428">大多數的組織不依賴在日常運作中呼叫 WIN32 APIs 的功能，即使它們是以其他方式使用宏。</span><span class="sxs-lookup"><span data-stu-id="dc26d-428">Most organizations don't rely on the ability to call Win32 APIs in their day-to-day functioning, even if they use macros in other ways.</span></span>

<span data-ttu-id="dc26d-429">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-429">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-430">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="dc26d-430">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="dc26d-431">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-431">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-432">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-432">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="dc26d-433">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="dc26d-433">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="dc26d-434">Intune 名稱： `Win32 imports from Office macro code`</span><span class="sxs-lookup"><span data-stu-id="dc26d-434">Intune name: `Win32 imports from Office macro code`</span></span>

<span data-ttu-id="dc26d-435">Configuration Manager 名稱： `Block Win32 API calls from Office macros`</span><span class="sxs-lookup"><span data-stu-id="dc26d-435">Configuration Manager name: `Block Win32 API calls from Office macros`</span></span>

<span data-ttu-id="dc26d-436">GUID:： `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span><span class="sxs-lookup"><span data-stu-id="dc26d-436">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span></span>

### <a name="use-advanced-protection-against-ransomware"></a><span data-ttu-id="dc26d-437">使用勒索軟體的高級防護</span><span class="sxs-lookup"><span data-stu-id="dc26d-437">Use advanced protection against ransomware</span></span>

<span data-ttu-id="dc26d-438">此規則可提供額外的保護，以防禦勒索軟體。</span><span class="sxs-lookup"><span data-stu-id="dc26d-438">This rule provides an extra layer of protection against ransomware.</span></span> <span data-ttu-id="dc26d-439">它會同時使用用戶端和雲端試探法來判斷檔案是否與勒索軟體類似。</span><span class="sxs-lookup"><span data-stu-id="dc26d-439">It uses both client and cloud heuristics to determine whether a file resembles ransomware.</span></span> <span data-ttu-id="dc26d-440">此規則不會封鎖具備下列一項或多項特性的檔案：</span><span class="sxs-lookup"><span data-stu-id="dc26d-440">This rule does not block files that have one or more of the following characteristics:</span></span>

- <span data-ttu-id="dc26d-441">檔案已在 Microsoft 雲端中找到 unharmful。</span><span class="sxs-lookup"><span data-stu-id="dc26d-441">The file has already been found to be unharmful in the Microsoft cloud.</span></span>
- <span data-ttu-id="dc26d-442">檔案是有效的簽署檔。</span><span class="sxs-lookup"><span data-stu-id="dc26d-442">The file is a valid signed file.</span></span>
- <span data-ttu-id="dc26d-443">檔案的流行不足，無法視為勒索軟體。</span><span class="sxs-lookup"><span data-stu-id="dc26d-443">The file is prevalent enough to not be considered as ransomware.</span></span>

<span data-ttu-id="dc26d-444">這項規則通常會在警告的另一個方面，以防止勒索軟體。</span><span class="sxs-lookup"><span data-stu-id="dc26d-444">The rule tends to err on the side of caution to prevent ransomware.</span></span>

> [!NOTE]
> <span data-ttu-id="dc26d-445">您必須 [啟用雲端提供的保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 才能使用此規則。</span><span class="sxs-lookup"><span data-stu-id="dc26d-445">You must [enable cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>

<span data-ttu-id="dc26d-446">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="dc26d-446">This rule was introduced in:</span></span>

- [<span data-ttu-id="dc26d-447">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="dc26d-447">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="dc26d-448">Windows Server，版本1809</span><span class="sxs-lookup"><span data-stu-id="dc26d-448">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="dc26d-449">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc26d-449">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="dc26d-450">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="dc26d-450">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="dc26d-451">Intune 名稱： `Advanced ransomware protection`</span><span class="sxs-lookup"><span data-stu-id="dc26d-451">Intune name: `Advanced ransomware protection`</span></span>

<span data-ttu-id="dc26d-452">Configuration Manager 名稱： `Use advanced protection against ransomware`</span><span class="sxs-lookup"><span data-stu-id="dc26d-452">Configuration Manager name: `Use advanced protection against ransomware`</span></span>

<span data-ttu-id="dc26d-453">GUID:： `c1db55ab-c21a-4637-bb3f-a12568109d35`</span><span class="sxs-lookup"><span data-stu-id="dc26d-453">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span></span>

## <a name="see-also"></a><span data-ttu-id="dc26d-454">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dc26d-454">See also</span></span>

- [<span data-ttu-id="dc26d-455">受攻擊面縮小常見問題集</span><span class="sxs-lookup"><span data-stu-id="dc26d-455">Attack surface reduction FAQ</span></span>](attack-surface-reduction-faq.md)
- [<span data-ttu-id="dc26d-456">啟用受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="dc26d-456">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
- [<span data-ttu-id="dc26d-457">評估受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="dc26d-457">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
- [<span data-ttu-id="dc26d-458">Microsoft Defender 防毒軟體與其他防病毒/反惡意程式碼解決方案的相容性</span><span class="sxs-lookup"><span data-stu-id="dc26d-458">Compatibility of Microsoft Defender Antivirus with other antivirus/antimalware solutions</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
