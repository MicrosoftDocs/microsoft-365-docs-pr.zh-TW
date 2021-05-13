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
ms.openlocfilehash: 3ca8f5234f90624c8570cbfb10e75bd0ee9380ae
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345833"
---
# <a name="use-attack-surface-reduction-rules-to-prevent-malware-infection"></a><span data-ttu-id="e71b8-104">使用攻擊面減少規則，以防止惡意程式碼感染</span><span class="sxs-lookup"><span data-stu-id="e71b8-104">Use attack surface reduction rules to prevent malware infection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e71b8-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="e71b8-105">**Applies to:**</span></span>

- [<span data-ttu-id="e71b8-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e71b8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- [<span data-ttu-id="e71b8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e71b8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="why-attack-surface-reduction-rules-are-important"></a><span data-ttu-id="e71b8-108">攻擊面減少規則為何很重要</span><span class="sxs-lookup"><span data-stu-id="e71b8-108">Why attack surface reduction rules are important</span></span>

<span data-ttu-id="e71b8-109">組織的攻擊麵包括攻擊者可能會損害組織之裝置或網路的所有地方。</span><span class="sxs-lookup"><span data-stu-id="e71b8-109">Your organization's attack surface includes all the places where an attacker could compromise your organization's devices or networks.</span></span> <span data-ttu-id="e71b8-110">減少攻擊面是指保護您組織的裝置和網路，這可讓攻擊者以較少的方式執行攻擊。</span><span class="sxs-lookup"><span data-stu-id="e71b8-110">Reducing your attack surface means protecting your organization's devices and network, which leaves attackers with fewer ways to perform attacks.</span></span> <span data-ttu-id="e71b8-111">在 Microsoft Defender for Endpoint 中設定攻擊面降低規則可協助！</span><span class="sxs-lookup"><span data-stu-id="e71b8-111">Configuring attack surface reduction rules in Microsoft Defender for Endpoint can help!</span></span>

<span data-ttu-id="e71b8-112">攻擊面減少規則會以特定的軟體行為為目標，例如：</span><span class="sxs-lookup"><span data-stu-id="e71b8-112">Attack surface reduction rules target certain software behaviors, such as:</span></span>

- <span data-ttu-id="e71b8-113">啟動可執行檔及腳本，以嘗試下載或執行檔;</span><span class="sxs-lookup"><span data-stu-id="e71b8-113">Launching executable files and scripts that attempt to download or run files;</span></span>
- <span data-ttu-id="e71b8-114">執行已模糊處理或其他可疑的腳本;和</span><span class="sxs-lookup"><span data-stu-id="e71b8-114">Running obfuscated or otherwise suspicious scripts; and</span></span>
- <span data-ttu-id="e71b8-115">執行在正常的日常工作中，應用程式通常不會啟動的行為。</span><span class="sxs-lookup"><span data-stu-id="e71b8-115">Performing behaviors that apps don't usually initiate during normal day-to-day work.</span></span>

<span data-ttu-id="e71b8-116">這類軟體行為有時會出現在合法的應用程式中;不過，這些行為通常會被視為危險，因為它們通常是透過惡意程式碼被攻擊者濫用。</span><span class="sxs-lookup"><span data-stu-id="e71b8-116">Such software behaviors are sometimes seen in legitimate applications; however, these behaviors are often considered risky because they are commonly abused by attackers through malware.</span></span> <span data-ttu-id="e71b8-117">攻擊面減少規則可限制危險的行為，並協助保護您的組織安全。</span><span class="sxs-lookup"><span data-stu-id="e71b8-117">Attack surface reduction rules can constrain risky behaviors and help keep your organization safe.</span></span>

<span data-ttu-id="e71b8-118">如需設定攻擊面減少規則的相關資訊，請參閱 [啟用攻擊面降減規則](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="e71b8-118">For more information about configuring attack surface reduction rules, see [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

## <a name="assess-rule-impact-before-deployment"></a><span data-ttu-id="e71b8-119">在部署之前評估規則影響</span><span class="sxs-lookup"><span data-stu-id="e71b8-119">Assess rule impact before deployment</span></span>

<span data-ttu-id="e71b8-120">您可以在[威脅與弱點管理](https://docs.microsoft.com/windows/security/threat-protection/#tvm)中開啟該規則的安全性建議，以評估攻擊面降低規則可能會如何影響您的網路。</span><span class="sxs-lookup"><span data-stu-id="e71b8-120">You can assess how an attack surface reduction rule might affect your network by opening the security recommendation for that rule in [threat and vulnerability management](https://docs.microsoft.com/windows/security/threat-protection/#tvm).</span></span>

:::image type="content" source="images/asrrecommendation.png" alt-text="攻擊面降低規則的安全性 reco":::

<span data-ttu-id="e71b8-122">在 [建議詳細資料] 窗格中，檢查 [使用者影響] 以判斷您的裝置可接受新原則的百分比，以封鎖模式啟用規則，而不會對生產力造成不良影響。</span><span class="sxs-lookup"><span data-stu-id="e71b8-122">In the recommendation details pane, check for user impact to determine what percentage of your devices can accept a new policy enabling the rule in blocking mode without adversely affecting productivity.</span></span>

## <a name="audit-mode-for-evaluation"></a><span data-ttu-id="e71b8-123">評估的審計模式</span><span class="sxs-lookup"><span data-stu-id="e71b8-123">Audit mode for evaluation</span></span>

<span data-ttu-id="e71b8-124">使用 [審計模式](audit-windows-defender.md) 評估攻擊面降低規則在啟用時會如何影響您的組織。</span><span class="sxs-lookup"><span data-stu-id="e71b8-124">Use [audit mode](audit-windows-defender.md) to evaluate how attack surface reduction rules would affect your organization if they were enabled.</span></span> <span data-ttu-id="e71b8-125">請先在稽核模式中執行所有規則，以便了解它們如何影響您的企業營運應用程式。</span><span class="sxs-lookup"><span data-stu-id="e71b8-125">Run all rules in audit mode first so you can understand how they affect your line-of-business applications.</span></span> <span data-ttu-id="e71b8-126">許多商務營運應用程式都是以有限的安全性考慮來編寫，而且他們可能會以類似惡意程式碼的方式執行工作。</span><span class="sxs-lookup"><span data-stu-id="e71b8-126">Many line-of-business applications are written with limited security concerns, and they might perform tasks in ways that seem similar to malware.</span></span> <span data-ttu-id="e71b8-127">透過監視審核資料並 [新增](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) 必要應用程式的排除專案，您可以在不降低生產力的情況下，部署攻擊面減少規則。</span><span class="sxs-lookup"><span data-stu-id="e71b8-127">By monitoring audit data and [adding exclusions](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) for necessary applications, you can deploy attack surface reduction rules without reducing productivity.</span></span>

## <a name="warn-mode-for-users"></a><span data-ttu-id="e71b8-128">使用者的警告模式</span><span class="sxs-lookup"><span data-stu-id="e71b8-128">Warn mode for users</span></span>

<span data-ttu-id="e71b8-129"> (**NEW**！ ) 在警告模式功能之前，已啟用的攻擊面降規則可以設定為 [稽核模式] 或 [封鎖模式]。</span><span class="sxs-lookup"><span data-stu-id="e71b8-129">(**NEW**!) Prior to warn mode capabilities, attack surface reduction rules that are enabled could be set to either audit mode or block mode.</span></span> <span data-ttu-id="e71b8-130">使用新的警告模式時，每當攻擊面減少規則封鎖內容時，使用者會看到指出內容已封鎖的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e71b8-130">With the new warn mode, whenever content is blocked by an attack surface reduction rule, users see a dialog box that indicates the content is blocked.</span></span> <span data-ttu-id="e71b8-131">對話方塊也會為使用者提供取消封鎖內容的選項。</span><span class="sxs-lookup"><span data-stu-id="e71b8-131">The dialog box also offers the user an option to unblock the content.</span></span> <span data-ttu-id="e71b8-132">然後，使用者可以重試其動作，並完成操作。</span><span class="sxs-lookup"><span data-stu-id="e71b8-132">The user can then retry their action, and the operation completes.</span></span> <span data-ttu-id="e71b8-133">當使用者取消封鎖內容時，內容會維持在24小時內解除封鎖，然後封鎖簡歷。</span><span class="sxs-lookup"><span data-stu-id="e71b8-133">When a user unblocks content, the content remains unblocked for 24 hours, and then blocking resumes.</span></span>

<span data-ttu-id="e71b8-134">警告模式可協助您的組織實施攻擊面降減規則，而不會防止使用者存取他們執行其工作所需的內容。</span><span class="sxs-lookup"><span data-stu-id="e71b8-134">Warn mode helps your organization have attack surface reduction rules in place without preventing users from accessing the content they need to perform their tasks.</span></span>

### <a name="requirements-for-warn-mode-to-work"></a><span data-ttu-id="e71b8-135">警告模式的運作需求</span><span class="sxs-lookup"><span data-stu-id="e71b8-135">Requirements for warn mode to work</span></span>

<span data-ttu-id="e71b8-136">在執行下列 Windows 版本的裝置上支援警告模式：</span><span class="sxs-lookup"><span data-stu-id="e71b8-136">Warn mode is supported on devices running the following versions of Windows:</span></span>

- <span data-ttu-id="e71b8-137">[Windows 10，版本 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)或更新版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-137">[Windows 10, version 1809](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) or later</span></span>
- <span data-ttu-id="e71b8-138">[Windows Server，版本 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)或更新版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-138">[Windows Server, version 1809](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809) or later</span></span>

<span data-ttu-id="e71b8-139">使用[Active 模式](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)中的即時保護時，必須執行 Microsoft Defender 防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="e71b8-139">Microsoft Defender Antivirus must be running with real-time protection in [Active mode](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state).</span></span>

<span data-ttu-id="e71b8-140">此外，請確定已安裝[Microsoft Defender 防毒軟體和反惡意軟體更新](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)。</span><span class="sxs-lookup"><span data-stu-id="e71b8-140">In addition, make sure [Microsoft Defender Antivirus and antimalware updates](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions) are installed.</span></span>

- <span data-ttu-id="e71b8-141">最低平臺版本需求： `4.18.2008.9`</span><span class="sxs-lookup"><span data-stu-id="e71b8-141">Minimum platform release requirement: `4.18.2008.9`</span></span>
- <span data-ttu-id="e71b8-142">最低引擎發行需求： `1.1.17400.5`</span><span class="sxs-lookup"><span data-stu-id="e71b8-142">Minimum engine release requirement: `1.1.17400.5`</span></span>

<span data-ttu-id="e71b8-143">如需詳細資訊和若要取得更新，請參閱 [Microsoft Defender 反惡意程式碼平臺的更新](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="e71b8-143">For more information and to get your updates, see [Update for Microsoft Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform).</span></span>

### <a name="cases-where-warn-mode-is-not-supported"></a><span data-ttu-id="e71b8-144">不支援警告模式的情況</span><span class="sxs-lookup"><span data-stu-id="e71b8-144">Cases where warn mode is not supported</span></span>

<span data-ttu-id="e71b8-145">當您在 Microsoft 端點管理員中設定三種攻擊面降減規則時，不支援警告模式。</span><span class="sxs-lookup"><span data-stu-id="e71b8-145">Warn mode is not supported for three attack surface reduction rules when you configure them in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="e71b8-146"> (如果使用群組原則來設定攻擊面降低規則，則會支援警告模式。 ) 在 Microsoft 端點管理員中進行設定時，不支援警告模式的三個規則如下：</span><span class="sxs-lookup"><span data-stu-id="e71b8-146">(If you use Group Policy to configure your attack surface reduction rules, warn mode is supported.) The three rules that do not support warn mode when you configure them in Microsoft Endpoint Manager are as follows:</span></span>

- <span data-ttu-id="e71b8-147">[封鎖 JavaScript 或 VBScript 啟動下載的可執行內容](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`) </span><span class="sxs-lookup"><span data-stu-id="e71b8-147">[Block JavaScript or VBScript from launching downloaded executable content](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) (GUID `d3e037e1-3eb8-44c8-a917-57927947596d`)</span></span>
- <span data-ttu-id="e71b8-148">[透過 WMI 事件訂閱封鎖的封鎖](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`) </span><span class="sxs-lookup"><span data-stu-id="e71b8-148">[Block persistence through WMI event subscription](#block-persistence-through-wmi-event-subscription) (GUID `e6db77e5-3df2-4cf1-b95a-636979351e5b`)</span></span>
- <span data-ttu-id="e71b8-149">[使用針對勒索軟體](#use-advanced-protection-against-ransomware) (GUID 的高級防護 `c1db55ab-c21a-4637-bb3f-a12568109d35`) </span><span class="sxs-lookup"><span data-stu-id="e71b8-149">[Use advanced protection against ransomware](#use-advanced-protection-against-ransomware) (GUID `c1db55ab-c21a-4637-bb3f-a12568109d35`)</span></span>

<span data-ttu-id="e71b8-150">此外，執行舊版本 Windows 的裝置不支援警告模式。</span><span class="sxs-lookup"><span data-stu-id="e71b8-150">In addition, warn mode is not supported on devices running older versions of Windows.</span></span> <span data-ttu-id="e71b8-151">在這種情況下，已設定為在警告模式中執行的攻擊面降規則會以封鎖模式執行。</span><span class="sxs-lookup"><span data-stu-id="e71b8-151">In those cases, attack surface reduction rules that are configured to run in warn mode will run in block mode.</span></span>

## <a name="notifications-and-alerts"></a><span data-ttu-id="e71b8-152">通知與提醒</span><span class="sxs-lookup"><span data-stu-id="e71b8-152">Notifications and alerts</span></span>

<span data-ttu-id="e71b8-153">每當觸發攻擊面降低規則時，就會在裝置上顯示通知。</span><span class="sxs-lookup"><span data-stu-id="e71b8-153">Whenever an attack surface reduction rule is triggered, a notification is displayed on the device.</span></span> <span data-ttu-id="e71b8-154">您可以 [自訂](customize-attack-surface-reduction.md#customize-the-notification) 您公司詳細資料和連絡人資訊的通知。</span><span class="sxs-lookup"><span data-stu-id="e71b8-154">You can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your company details and contact information.</span></span>

<span data-ttu-id="e71b8-155">此外，當觸發某些攻擊面降低規則時，會產生警示。</span><span class="sxs-lookup"><span data-stu-id="e71b8-155">In addition, when certain attack surface reduction rules are triggered, alerts are generated.</span></span>

<span data-ttu-id="e71b8-156">您可以在 Microsoft Defender 資訊安全中心 ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 中或 Microsoft 365 的安全性中心 () 中查看所產生的通知和任何警示 [https://security.microsoft.com](https://security.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="e71b8-156">Notifications and any alerts that are generated can be viewed in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and in the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span>

## <a name="advanced-hunting-and-attack-surface-reduction-events"></a><span data-ttu-id="e71b8-157">高級搜尋和攻擊面降低事件</span><span class="sxs-lookup"><span data-stu-id="e71b8-157">Advanced hunting and attack surface reduction events</span></span>

<span data-ttu-id="e71b8-158">您可以使用高級搜尋來查看攻擊面降低事件。</span><span class="sxs-lookup"><span data-stu-id="e71b8-158">You can use advanced hunting to view attack surface reduction events.</span></span> <span data-ttu-id="e71b8-159">為了簡化傳入資料的數量，您可以透過高級搜尋查看每小時只有一個唯一的處理常式。</span><span class="sxs-lookup"><span data-stu-id="e71b8-159">To streamline the volume of incoming data, only unique processes for each hour are viewable with advanced hunting.</span></span> <span data-ttu-id="e71b8-160">攻擊面降低事件的時間是在一小時內第一次看到的事件。</span><span class="sxs-lookup"><span data-stu-id="e71b8-160">The time of an attack surface reduction event is the first time that event is seen within the hour.</span></span>

<span data-ttu-id="e71b8-161">例如，假設在 2:00 PM 小時內10台裝置上發生攻擊面降低事件。</span><span class="sxs-lookup"><span data-stu-id="e71b8-161">For example, suppose that an attack surface reduction event occurs on 10 devices during the 2:00 PM hour.</span></span> <span data-ttu-id="e71b8-162">假設第一個事件發生于2:15，最後是2:45。</span><span class="sxs-lookup"><span data-stu-id="e71b8-162">Suppose that the first event occurred at 2:15, and the last at 2:45.</span></span> <span data-ttu-id="e71b8-163">使用高級搜尋時，您會看到該事件的一個實例 (，即使它實際發生于10個裝置) 上，而且其時間戳記會是 2:15 PM。</span><span class="sxs-lookup"><span data-stu-id="e71b8-163">With advanced hunting, you'll see one instance of that event (even though it actually occurred on 10 devices), and its timestamp will be 2:15 PM.</span></span>

<span data-ttu-id="e71b8-164">如需有關高級搜尋的詳細資訊，請參閱 [使用高級搜尋主動搜尋威脅](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e71b8-164">For more information about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="attack-surface-reduction-features-across-windows-versions"></a><span data-ttu-id="e71b8-165">跨 Windows 版本的攻擊面減少功能</span><span class="sxs-lookup"><span data-stu-id="e71b8-165">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="e71b8-166">您可以針對執行下列任何版本與 Windows 的裝置，設定攻擊面減少規則：</span><span class="sxs-lookup"><span data-stu-id="e71b8-166">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="e71b8-167">Windows 10 專業版，[版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-167">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="e71b8-168">Windows 10 企業版，[版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-168">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="e71b8-169">Windows伺服器，[版本 1803 (半年通道) ](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)或更新版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-169">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="e71b8-170">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-170">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="e71b8-171">雖然攻擊面降減規則不需要[Windows E5 授權](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses)，但如果您有 Windows E5，就會取得高級管理功能。</span><span class="sxs-lookup"><span data-stu-id="e71b8-171">Although attack surface reduction rules don't require a [Windows E5 license](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="e71b8-172">這些功能只能在 Windows E5 中包含用於[端點的](microsoft-defender-endpoint.md)監控、分析和工作流程，以及[Microsoft 365 安全性中心](https://docs.microsoft.com/microsoft-365/security/defender/overview-security-center)的報表和設定功能。</span><span class="sxs-lookup"><span data-stu-id="e71b8-172">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](microsoft-defender-endpoint.md), as well as reporting and configuration capabilities in the [Microsoft 365 security center](https://docs.microsoft.com/microsoft-365/security/defender/overview-security-center).</span></span> <span data-ttu-id="e71b8-173">Windows Professional 或 Windows E3 授權無法使用這些高級功能;不過，如果您有這些授權，您可以使用「事件檢視器」和 Microsoft Defender 防毒軟體記錄檔，以查看攻擊面減少規則事件。</span><span class="sxs-lookup"><span data-stu-id="e71b8-173">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

## <a name="review-attack-surface-reduction-events-in-the-microsoft-defender-security-center"></a><span data-ttu-id="e71b8-174">複查 Microsoft Defender 資訊安全中心中的攻擊面降低事件</span><span class="sxs-lookup"><span data-stu-id="e71b8-174">Review attack surface reduction events in the Microsoft Defender Security Center</span></span>

<span data-ttu-id="e71b8-175">當警示調查案例中，Defender for Endpoint 提供事件和區塊的詳細報告。</span><span class="sxs-lookup"><span data-stu-id="e71b8-175">Defender for Endpoint provides detailed reporting for events and blocks as part of alert investigation scenarios.</span></span>

<span data-ttu-id="e71b8-176">您可以使用 [ [高級搜尋](advanced-hunting-query-language.md)] 查詢 Defender 的端點資料。</span><span class="sxs-lookup"><span data-stu-id="e71b8-176">You can query Defender for Endpoint data by using [advanced hunting](advanced-hunting-query-language.md).</span></span> <span data-ttu-id="e71b8-177">如果您正在執行 [稽核模式](audit-windows-defender.md)，您可以使用高級搜尋來瞭解攻擊面降低規則如何影響您的環境。</span><span class="sxs-lookup"><span data-stu-id="e71b8-177">If you're running [audit mode](audit-windows-defender.md), you can use advanced hunting to understand how attack surface reduction rules could affect your environment.</span></span>

<span data-ttu-id="e71b8-178">以下是範例查詢：</span><span class="sxs-lookup"><span data-stu-id="e71b8-178">Here is an example query:</span></span>

```kusto
DeviceEvents
| where ActionType startswith 'Asr'
```

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a><span data-ttu-id="e71b8-179">在 Windows 事件檢視器中查看攻擊面降低事件</span><span class="sxs-lookup"><span data-stu-id="e71b8-179">Review attack surface reduction events in Windows Event Viewer</span></span>

<span data-ttu-id="e71b8-180">您可以查看 Windows 事件記錄檔，以查看攻擊面減少規則所產生的事件：</span><span class="sxs-lookup"><span data-stu-id="e71b8-180">You can review the Windows event log to view events generated by attack surface reduction rules:</span></span>

1. <span data-ttu-id="e71b8-181">下載 [評估套件](https://aka.ms/mp7z2w) ，並將檔案 *cfa-events.xml* 解壓至裝置上易於存取的位置。</span><span class="sxs-lookup"><span data-stu-id="e71b8-181">Download the [Evaluation Package](https://aka.ms/mp7z2w) and extract the file *cfa-events.xml* to an easily accessible location on the device.</span></span>
2. <span data-ttu-id="e71b8-182">在 [開始] 功能表中輸入文字 [*事件檢視器*]，以開啟 Windows 事件檢視器。</span><span class="sxs-lookup"><span data-stu-id="e71b8-182">Enter the words, *Event Viewer*, into the Start menu to open the Windows Event Viewer.</span></span>
3. <span data-ttu-id="e71b8-183">在 [ **動作**] 下，選取 [匯 **入自訂視圖 ...**]。</span><span class="sxs-lookup"><span data-stu-id="e71b8-183">Under **Actions**, select **Import custom view...**.</span></span>
4. <span data-ttu-id="e71b8-184">從解壓縮的位置選取檔案 *cfa-events.xml* 。</span><span class="sxs-lookup"><span data-stu-id="e71b8-184">Select the file *cfa-events.xml* from where it was extracted.</span></span> <span data-ttu-id="e71b8-185">或者， [直接複製 XML](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="e71b8-185">Alternatively, [copy the XML directly](event-views.md).</span></span>
5. <span data-ttu-id="e71b8-186">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e71b8-186">Select **OK**.</span></span>

<span data-ttu-id="e71b8-187">您可以建立篩選事件只顯示下列事件的自訂視圖，這些事件都與「受控資料夾存取」有關：</span><span class="sxs-lookup"><span data-stu-id="e71b8-187">You can create a custom view that filters events to only show the following events, all of which are related to controlled folder access:</span></span>

|<span data-ttu-id="e71b8-188">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="e71b8-188">Event ID</span></span>|<span data-ttu-id="e71b8-189">描述</span><span class="sxs-lookup"><span data-stu-id="e71b8-189">Description</span></span>|
|---|---|
|<span data-ttu-id="e71b8-190">5007</span><span class="sxs-lookup"><span data-stu-id="e71b8-190">5007</span></span>|<span data-ttu-id="e71b8-191">設定變更時的事件</span><span class="sxs-lookup"><span data-stu-id="e71b8-191">Event when settings are changed</span></span>|
|<span data-ttu-id="e71b8-192">1121</span><span class="sxs-lookup"><span data-stu-id="e71b8-192">1121</span></span>|<span data-ttu-id="e71b8-193">在組塊模式中激發規則時的事件</span><span class="sxs-lookup"><span data-stu-id="e71b8-193">Event when rule fires in Block-mode</span></span>|
|<span data-ttu-id="e71b8-194">1122</span><span class="sxs-lookup"><span data-stu-id="e71b8-194">1122</span></span>|<span data-ttu-id="e71b8-195">在稽核模式中觸發規則時的事件</span><span class="sxs-lookup"><span data-stu-id="e71b8-195">Event when rule fires in Audit-mode</span></span>|
|

<span data-ttu-id="e71b8-196">在事件記錄中，列出的攻擊面降低事件的「引擎版本」是由 Defender for Endpoint 所產生，而不是由作業系統產生。</span><span class="sxs-lookup"><span data-stu-id="e71b8-196">The "engine version" listed for attack surface reduction events in the event log, is generated by Defender for Endpoint, not by the operating system.</span></span> <span data-ttu-id="e71b8-197">與 Windows 10 的 Defender 已整合，所以此功能可在已安裝 Windows 10 的所有裝置上運作。</span><span class="sxs-lookup"><span data-stu-id="e71b8-197">Defender for Endpoint is integrated with Windows 10, so this feature works on all devices with Windows 10 installed.</span></span>

## <a name="attack-surface-reduction-rules"></a><span data-ttu-id="e71b8-198">受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="e71b8-198">Attack surface reduction rules</span></span>

<span data-ttu-id="e71b8-199">下表與子小節分別說明15個攻擊面降減規則。</span><span class="sxs-lookup"><span data-stu-id="e71b8-199">The following table and subsections describe each of the 15 attack surface reduction rules.</span></span> <span data-ttu-id="e71b8-200">攻擊面降低規則會依規則名稱依字母順序列出。</span><span class="sxs-lookup"><span data-stu-id="e71b8-200">The attack surface reduction rules are listed in alphabetical order, by rule name.</span></span>

<span data-ttu-id="e71b8-201">如果您是使用群組原則或 PowerShell 來設定攻擊面降低規則，則需要 Guid。</span><span class="sxs-lookup"><span data-stu-id="e71b8-201">If you are configuring attack surface reduction rules by using Group Policy or PowerShell, you'll need the GUIDs.</span></span> <span data-ttu-id="e71b8-202">另一方面，如果您使用 Microsoft 端點管理員或 Microsoft Intune，便不需要 guid。</span><span class="sxs-lookup"><span data-stu-id="e71b8-202">On the other hand, if you use Microsoft Endpoint Manager or Microsoft Intune, you do not need the GUIDs.</span></span>

|<span data-ttu-id="e71b8-203">規則名稱</span><span class="sxs-lookup"><span data-stu-id="e71b8-203">Rule name</span></span>|<span data-ttu-id="e71b8-204">GUID</span><span class="sxs-lookup"><span data-stu-id="e71b8-204">GUID</span></span>|<span data-ttu-id="e71b8-205">File & 資料夾排除</span><span class="sxs-lookup"><span data-stu-id="e71b8-205">File & folder exclusions</span></span>|<span data-ttu-id="e71b8-206">支援的最低作業系統</span><span class="sxs-lookup"><span data-stu-id="e71b8-206">Minimum OS supported</span></span>|
|---|:---:|---|---|
|[<span data-ttu-id="e71b8-207">封鎖濫用的漏洞簽章驅動程式</span><span class="sxs-lookup"><span data-stu-id="e71b8-207">Block abuse of exploited vulnerable signed drivers</span></span>](#block-abuse-of-exploited-vulnerable-signed-drivers)|`56a863a9-875e-4185-98a7-b882c64b5ce5`|<span data-ttu-id="e71b8-208">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-208">Supported</span></span>|[<span data-ttu-id="e71b8-209">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="e71b8-209">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)|
|[<span data-ttu-id="e71b8-210">封鎖 Adobe Reader，以建立子流程</span><span class="sxs-lookup"><span data-stu-id="e71b8-210">Block Adobe Reader from creating child processes</span></span>](#block-adobe-reader-from-creating-child-processes)|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|<span data-ttu-id="e71b8-211">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-211">Supported</span></span>|<span data-ttu-id="e71b8-212">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-212">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="e71b8-213">封鎖所有 Office 的應用程式建立子流程</span><span class="sxs-lookup"><span data-stu-id="e71b8-213">Block all Office applications from creating child processes</span></span>](#block-all-office-applications-from-creating-child-processes)|`D4F940AB-401B-4EFC-AADC-AD5F3C50688A`|<span data-ttu-id="e71b8-214">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-214">Supported</span></span>|<span data-ttu-id="e71b8-215">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-215">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="e71b8-216">封鎖 Windows 本機安全性群組子系統 (lsass.exe 中的認證竊取) </span><span class="sxs-lookup"><span data-stu-id="e71b8-216">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>](#block-credential-stealing-from-the-windows-local-security-authority-subsystem)|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|<span data-ttu-id="e71b8-217">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-217">Supported</span></span>|<span data-ttu-id="e71b8-218">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-218">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="e71b8-219">從電子郵件客戶程式和 web 郵件封鎖可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="e71b8-219">Block executable content from email client and webmail</span></span>](#block-executable-content-from-email-client-and-webmail)|`BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`|<span data-ttu-id="e71b8-220">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-220">Supported</span></span>|<span data-ttu-id="e71b8-221">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-221">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="e71b8-222">封鎖可執行檔，除非符合流行、age 或受信任的清單準則</span><span class="sxs-lookup"><span data-stu-id="e71b8-222">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)|`01443614-cd74-433a-b99e-2ecdc07bfc25`|<span data-ttu-id="e71b8-223">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-223">Supported</span></span>|<span data-ttu-id="e71b8-224">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-224">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="e71b8-225">封鎖可能混淆的腳本執行</span><span class="sxs-lookup"><span data-stu-id="e71b8-225">Block execution of potentially obfuscated scripts</span></span>](#block-execution-of-potentially-obfuscated-scripts)|`5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`|<span data-ttu-id="e71b8-226">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-226">Supported</span></span>|<span data-ttu-id="e71b8-227">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-227">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="e71b8-228">從啟動下載的可執行內容封鎖 JavaScript 或 VBScript</span><span class="sxs-lookup"><span data-stu-id="e71b8-228">Block JavaScript or VBScript from launching downloaded executable content</span></span>](#block-javascript-or-vbscript-from-launching-downloaded-executable-content)|`D3E037E1-3EB8-44C8-A917-57927947596D`|<span data-ttu-id="e71b8-229">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-229">Supported</span></span>|<span data-ttu-id="e71b8-230">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-230">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="e71b8-231">封鎖 Office 應用程式建立可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="e71b8-231">Block Office applications from creating executable content</span></span>](#block-office-applications-from-creating-executable-content)|`3B576869-A4EC-4529-8536-B80A7769E899`|<span data-ttu-id="e71b8-232">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-232">Supported</span></span>|<span data-ttu-id="e71b8-233">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-233">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="e71b8-234">封鎖 Office 的應用程式將程式碼注入其他進程</span><span class="sxs-lookup"><span data-stu-id="e71b8-234">Block Office applications from injecting code into other processes</span></span>](#block-office-applications-from-injecting-code-into-other-processes)|`75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`|<span data-ttu-id="e71b8-235">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-235">Supported</span></span>|<span data-ttu-id="e71b8-236">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-236">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="e71b8-237">封鎖 Office 通訊應用程式建立子流程</span><span class="sxs-lookup"><span data-stu-id="e71b8-237">Block Office communication application from creating child processes</span></span>](#block-office-communication-application-from-creating-child-processes)|`26190899-1602-49e8-8b27-eb1d0a1ce869`|<span data-ttu-id="e71b8-238">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-238">Supported</span></span>|<span data-ttu-id="e71b8-239">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-239">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="e71b8-240">透過 WMI 事件訂閱封鎖持久性</span><span class="sxs-lookup"><span data-stu-id="e71b8-240">Block persistence through WMI event subscription</span></span>](#block-persistence-through-wmi-event-subscription)|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|<span data-ttu-id="e71b8-241">不支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-241">Not supported</span></span>|<span data-ttu-id="e71b8-242">[Windows 10，版本 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) (組建 18362) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-242">[Windows 10, version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) (build 18362) or greater</span></span>|
|[<span data-ttu-id="e71b8-243">封鎖來自 PSExec 和 WMI 命令的進程建立</span><span class="sxs-lookup"><span data-stu-id="e71b8-243">Block process creations originating from PSExec and WMI commands</span></span>](#block-process-creations-originating-from-psexec-and-wmi-commands)|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|<span data-ttu-id="e71b8-244">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-244">Supported</span></span>|<span data-ttu-id="e71b8-245">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-245">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="e71b8-246">封鎖從 USB 執行的不受信任和未簽署程式</span><span class="sxs-lookup"><span data-stu-id="e71b8-246">Block untrusted and unsigned processes that run from USB</span></span>](#block-untrusted-and-unsigned-processes-that-run-from-usb)|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|<span data-ttu-id="e71b8-247">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-247">Supported</span></span>|<span data-ttu-id="e71b8-248">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-248">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="e71b8-249">從 Office 宏封鎖 WIN32 API 通話</span><span class="sxs-lookup"><span data-stu-id="e71b8-249">Block Win32 API calls from Office macros</span></span>](#block-win32-api-calls-from-office-macros)|`92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`|<span data-ttu-id="e71b8-250">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-250">Supported</span></span>|<span data-ttu-id="e71b8-251">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-251">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|[<span data-ttu-id="e71b8-252">使用勒索軟體的高級防護</span><span class="sxs-lookup"><span data-stu-id="e71b8-252">Use advanced protection against ransomware</span></span>](#use-advanced-protection-against-ransomware)|`c1db55ab-c21a-4637-bb3f-a12568109d35`|<span data-ttu-id="e71b8-253">支援</span><span class="sxs-lookup"><span data-stu-id="e71b8-253">Supported</span></span>|<span data-ttu-id="e71b8-254">[Windows 10，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3，組建 16299) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-254">[Windows 10, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) (RS3, build 16299) or greater</span></span>|
|

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a><span data-ttu-id="e71b8-255">封鎖濫用的漏洞簽章驅動程式</span><span class="sxs-lookup"><span data-stu-id="e71b8-255">Block abuse of exploited vulnerable signed drivers</span></span>

<span data-ttu-id="e71b8-256">此規則可防止應用程式在磁片上寫入具有漏洞且已簽署的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="e71b8-256">This rule prevents an application from writing a vulnerable, signed driver to disk.</span></span> <span data-ttu-id="e71b8-257">實際上， \- _具有足夠許可權_ \- 才能存取內核的本機應用程式可以利用有漏洞的已簽署驅動程式。</span><span class="sxs-lookup"><span data-stu-id="e71b8-257">In-the-wild, vulnerable signed drivers can be exploited by local applications \- _that have sufficient privileges_ \- to gain access to the kernel.</span></span> <span data-ttu-id="e71b8-258">有漏洞的簽章驅動程式可讓攻擊者停用或規避安全性解決方案，最後導致系統受損。</span><span class="sxs-lookup"><span data-stu-id="e71b8-258">Vulnerable signed drivers enable attackers to disable or circumvent security solutions, eventually leading to system compromise.</span></span>

<span data-ttu-id="e71b8-259">此規則不會封鎖已存在於已在系統上載入的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="e71b8-259">This rule does not block a driver already existing on the system from being loaded.</span></span>

<span data-ttu-id="e71b8-260">所有支援 ASR 的版本都支援此規則;如下：</span><span class="sxs-lookup"><span data-stu-id="e71b8-260">This rule is supported in all versions in which ASR is supported; which is:</span></span>

- <span data-ttu-id="e71b8-261">[Windows 10 專業版，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-261">[Windows 10 Pro, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="e71b8-262">[Windows 10 企業版，版本 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)或更新版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-262">[Windows 10 Enterprise, version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="e71b8-263">[Windows Server，版本 1803 (半年通道) ](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)或更新版本</span><span class="sxs-lookup"><span data-stu-id="e71b8-263">[Windows Server, version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="e71b8-264">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-264">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="e71b8-265">Intune 名稱： `Block abuse of exploited vulnerable signed drivers`</span><span class="sxs-lookup"><span data-stu-id="e71b8-265">Intune Name: `Block abuse of exploited vulnerable signed drivers`</span></span>

<span data-ttu-id="e71b8-266">GUID:：  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span><span class="sxs-lookup"><span data-stu-id="e71b8-266">GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`</span></span>

<span data-ttu-id="e71b8-267">請參閱[Microsoft 端點管理員自訂](enable-attack-surface-reduction.md#microsoft-endpoint-manager-custom-procedure)程式的 MEM 自訂規則程式資訊。</span><span class="sxs-lookup"><span data-stu-id="e71b8-267">See [Microsoft Endpoint Manager custom procedure](enable-attack-surface-reduction.md#microsoft-endpoint-manager-custom-procedure) for MEM custom rules procedure information.</span></span>

<span data-ttu-id="e71b8-268">您可以在命令列中執行下列命令，以啟用 ASR 規則：</span><span class="sxs-lookup"><span data-stu-id="e71b8-268">You can run this command in the command line to enable the ASR rule:</span></span>

```powershell
"& {&'Add-MpPreference' -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled"}
```

<span data-ttu-id="e71b8-269">您可以使用此網站 [提交分析的驅動程式](https://www.microsoft.com/en-us/wdsi/driversubmission)。</span><span class="sxs-lookup"><span data-stu-id="e71b8-269">You can use this Web site to [Submit a driver for analysis](https://www.microsoft.com/en-us/wdsi/driversubmission).</span></span>

### <a name="block-adobe-reader-from-creating-child-processes"></a><span data-ttu-id="e71b8-270">封鎖 Adobe Reader，以建立子流程</span><span class="sxs-lookup"><span data-stu-id="e71b8-270">Block Adobe Reader from creating child processes</span></span>

<span data-ttu-id="e71b8-271">此規則會封鎖來自 Adobe Reader 的攻擊，使其無法建立處理常式。</span><span class="sxs-lookup"><span data-stu-id="e71b8-271">This rule prevents attacks by blocking Adobe Reader from creating processes.</span></span>

<span data-ttu-id="e71b8-272">透過社交工程或利用方式，惡意程式碼可以下載和啟動有效載荷，並中斷 Adobe Reader。</span><span class="sxs-lookup"><span data-stu-id="e71b8-272">Through social engineering or exploits, malware can download and launch payloads, and break out of Adobe Reader.</span></span> <span data-ttu-id="e71b8-273">透過封鎖子流程以供 Adobe Reader 的產生，惡意程式碼嘗試使用它做為向量，便無法散佈。</span><span class="sxs-lookup"><span data-stu-id="e71b8-273">By blocking child processes from being generated by Adobe Reader, malware attempting to use it as a vector are prevented from spreading.</span></span>

<span data-ttu-id="e71b8-274">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-274">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-275">Windows 10，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-275">Windows 10, version 1809</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="e71b8-276">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-276">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-277">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-277">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="e71b8-278">Intune 名稱： `Process creation from Adobe Reader (beta)`</span><span class="sxs-lookup"><span data-stu-id="e71b8-278">Intune name: `Process creation from Adobe Reader (beta)`</span></span>

<span data-ttu-id="e71b8-279">Configuration Manager 名稱：尚未提供</span><span class="sxs-lookup"><span data-stu-id="e71b8-279">Configuration Manager name: Not yet available</span></span>

<span data-ttu-id="e71b8-280">GUID:： `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span><span class="sxs-lookup"><span data-stu-id="e71b8-280">GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`</span></span>

### <a name="block-all-office-applications-from-creating-child-processes"></a><span data-ttu-id="e71b8-281">封鎖所有 Office 的應用程式建立子流程</span><span class="sxs-lookup"><span data-stu-id="e71b8-281">Block all Office applications from creating child processes</span></span>

<span data-ttu-id="e71b8-282">此規則會封鎖 Office 的應用程式建立子流程。</span><span class="sxs-lookup"><span data-stu-id="e71b8-282">This rule blocks Office apps from creating child processes.</span></span> <span data-ttu-id="e71b8-283">Office 應用程式包括 Word、Excel、PowerPoint、OneNote 和 Access。</span><span class="sxs-lookup"><span data-stu-id="e71b8-283">Office apps include Word, Excel, PowerPoint, OneNote, and Access.</span></span>

<span data-ttu-id="e71b8-284">建立惡意的子流程是常見的惡意程式碼策略。</span><span class="sxs-lookup"><span data-stu-id="e71b8-284">Creating malicious child processes is a common malware strategy.</span></span> <span data-ttu-id="e71b8-285">濫用 Office 為向量的惡意程式碼通常會執行 VBA 宏，並利用程式碼下載並嘗試執行更多負載。</span><span class="sxs-lookup"><span data-stu-id="e71b8-285">Malware that abuse Office as a vector often run VBA macros and exploit code to download and attempt to run more payloads.</span></span> <span data-ttu-id="e71b8-286">不過，某些合法的企業營運應用程式也可能會產生良性目的的子流程，例如產生命令提示字元或使用 PowerShell 來設定登錄設定。</span><span class="sxs-lookup"><span data-stu-id="e71b8-286">However, some legitimate line-of-business applications might also generate child processes for benign purposes, such as spawning a command prompt or using PowerShell to configure registry settings.</span></span>

<span data-ttu-id="e71b8-287">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-287">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-288">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="e71b8-288">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="e71b8-289">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-289">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-290">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-290">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="e71b8-291">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="e71b8-291">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="e71b8-292">Intune 名稱： `Office apps launching child processes`</span><span class="sxs-lookup"><span data-stu-id="e71b8-292">Intune name: `Office apps launching child processes`</span></span>

<span data-ttu-id="e71b8-293">Configuration Manager 名稱： `Block Office application from creating child processes`</span><span class="sxs-lookup"><span data-stu-id="e71b8-293">Configuration Manager name: `Block Office application from creating child processes`</span></span>

<span data-ttu-id="e71b8-294">GUID:： `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span><span class="sxs-lookup"><span data-stu-id="e71b8-294">GUID: `D4F940AB-401B-4EFC-AADC-AD5F3C50688A`</span></span>

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a><span data-ttu-id="e71b8-295">封鎖從 Windows 本機安全授權子系統偷竊的認證</span><span class="sxs-lookup"><span data-stu-id="e71b8-295">Block credential stealing from the Windows local security authority subsystem</span></span>

<span data-ttu-id="e71b8-296">此規則會透過鎖定本機 Security 機關子系統服務 (LSASS) ，協助防止身分憑證竊取。</span><span class="sxs-lookup"><span data-stu-id="e71b8-296">This rule helps prevent credential stealing, by locking down Local Security Authority Subsystem Service (LSASS).</span></span>

<span data-ttu-id="e71b8-297">LSASS 驗證在 Windows 電腦上登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="e71b8-297">LSASS authenticates users who sign in on a Windows computer.</span></span> <span data-ttu-id="e71b8-298">Microsoft Defender Credential Guard in Windows 10 一般會防止嘗試從 LSASS 提取認證。</span><span class="sxs-lookup"><span data-stu-id="e71b8-298">Microsoft Defender Credential Guard in Windows 10 normally prevents attempts to extract credentials from LSASS.</span></span> <span data-ttu-id="e71b8-299">不過，某些組織無法在其所有電腦上啟用認證防護，因為自訂的智慧卡驅動程式或其他載入至本機安全授權的程式的相容性問題 (LSA) 。</span><span class="sxs-lookup"><span data-stu-id="e71b8-299">However, some organizations can't enable Credential Guard on all of their computers because of compatibility issues with custom smartcard drivers or other programs that load into the Local Security Authority (LSA).</span></span> <span data-ttu-id="e71b8-300">在這些情況下，攻擊者可以使用像是 Mimikatz 的駭客攻擊工具，從 LSASS scrape 純文字密碼和 NTLM 雜湊。</span><span class="sxs-lookup"><span data-stu-id="e71b8-300">In these cases, attackers can use hack tools like Mimikatz to scrape cleartext passwords and NTLM hashes from LSASS.</span></span>

> [!NOTE]
> <span data-ttu-id="e71b8-301">在某些應用程式中，此程式碼會列舉所有執行中的程式，並嘗試以詳盡的許可權來開啟這些進程。</span><span class="sxs-lookup"><span data-stu-id="e71b8-301">In some apps, the code enumerates all running processes and attempts to open them with exhaustive permissions.</span></span> <span data-ttu-id="e71b8-302">此規則會拒絕應用程式的「開啟」動作，並將詳細資料記錄到安全性事件記錄檔。</span><span class="sxs-lookup"><span data-stu-id="e71b8-302">This rule denies the app's process open action and logs the details to the security event log.</span></span> <span data-ttu-id="e71b8-303">此規則會產生大量的噪音。</span><span class="sxs-lookup"><span data-stu-id="e71b8-303">This rule can generate a lot of noise.</span></span> <span data-ttu-id="e71b8-304">如果您有一個應用程式，只列舉 LSASS，但沒有任何實際的功能影響，便不需要將其新增至排除清單。</span><span class="sxs-lookup"><span data-stu-id="e71b8-304">If you have an app that simply enumerates LSASS, but has no real impact in functionality, there is NO need to add it to the exclusion list.</span></span> <span data-ttu-id="e71b8-305">這個事件記錄專案本身不一定表示惡意威脅。</span><span class="sxs-lookup"><span data-stu-id="e71b8-305">By itself, this event log entry doesn't necessarily indicate a malicious threat.</span></span>

<span data-ttu-id="e71b8-306">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-306">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-307">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="e71b8-307">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="e71b8-308">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-308">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-309">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-309">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="e71b8-310">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="e71b8-310">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="e71b8-311">Intune 名稱： `Flag credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="e71b8-311">Intune name: `Flag credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="e71b8-312">Configuration Manager 名稱： `Block credential stealing from the Windows local security authority subsystem`</span><span class="sxs-lookup"><span data-stu-id="e71b8-312">Configuration Manager name: `Block credential stealing from the Windows local security authority subsystem`</span></span>

<span data-ttu-id="e71b8-313">GUID:： `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span><span class="sxs-lookup"><span data-stu-id="e71b8-313">GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`</span></span>

### <a name="block-executable-content-from-email-client-and-webmail"></a><span data-ttu-id="e71b8-314">從電子郵件客戶程式和 web 郵件封鎖可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="e71b8-314">Block executable content from email client and webmail</span></span>

<span data-ttu-id="e71b8-315">此規則會封鎖下列檔案類型，以從 Microsoft Outlook 應用程式內開啟的電子郵件，或 Outlook .com 和其他流行的 web 郵件提供者來啟動：</span><span class="sxs-lookup"><span data-stu-id="e71b8-315">This rule blocks the following file types from launching from email opened within the Microsoft Outlook application, or Outlook.com and other popular webmail providers:</span></span>

- <span data-ttu-id="e71b8-316">可執行檔 (例如 .exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="e71b8-316">Executable files (such as .exe, .dll, or .scr)</span></span>
- <span data-ttu-id="e71b8-317">腳本檔案 (例如 PowerShell .ps、Visual Basic .vbs 或 JavaScript .js 檔) </span><span class="sxs-lookup"><span data-stu-id="e71b8-317">Script files (such as a PowerShell .ps, Visual Basic .vbs, or JavaScript .js file)</span></span>

<span data-ttu-id="e71b8-318">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-318">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-319">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="e71b8-319">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="e71b8-320">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-320">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-321">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-321">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="e71b8-322">Microsoft 端點管理員CB 1710</span><span class="sxs-lookup"><span data-stu-id="e71b8-322">Microsoft Endpoint Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="e71b8-323">Intune 名稱： `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="e71b8-323">Intune name: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`</span></span>

<span data-ttu-id="e71b8-324">Microsoft 端點管理員名稱：`Block executable content from email client and webmail`</span><span class="sxs-lookup"><span data-stu-id="e71b8-324">Microsoft Endpoint Manager name: `Block executable content from email client and webmail`</span></span>

<span data-ttu-id="e71b8-325">GUID:： `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span><span class="sxs-lookup"><span data-stu-id="e71b8-325">GUID: `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550`</span></span>

> [!NOTE]
> <span data-ttu-id="e71b8-326">**從電子郵件客戶程式和 web 郵件封鎖可執行檔內容**，具有下列替代描述（取決於您所使用的應用程式）：</span><span class="sxs-lookup"><span data-stu-id="e71b8-326">The rule **Block executable content from email client and webmail** has the following alternative descriptions, depending on which application you use:</span></span>
>
> - <span data-ttu-id="e71b8-327">Intune (設定檔) ：執行可執行檔內容 (exe、dll、ps、js、vbs 等 ) 從電子郵件 (郵件) web 郵件用戶端 () 沒有例外。</span><span class="sxs-lookup"><span data-stu-id="e71b8-327">Intune (Configuration Profiles): Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions).</span></span>
> - <span data-ttu-id="e71b8-328">端點管理員：封鎖電子郵件和郵件傳送用戶端的可執行內容下載。</span><span class="sxs-lookup"><span data-stu-id="e71b8-328">Endpoint Manager: Block executable content download from email and webmail clients.</span></span>
> - <span data-ttu-id="e71b8-329">群組原則：從電子郵件客戶程式和 web 郵件封鎖可執行檔內容。</span><span class="sxs-lookup"><span data-stu-id="e71b8-329">Group Policy: Block executable content from email client and webmail.</span></span>

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a><span data-ttu-id="e71b8-330">封鎖可執行檔，除非符合流行、age 或受信任的清單準則</span><span class="sxs-lookup"><span data-stu-id="e71b8-330">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>

<span data-ttu-id="e71b8-331">此規則會封鎖下列檔案類型的啟動，除非它們符合流行或年齡準則，或是位於信任清單或排除清單中：</span><span class="sxs-lookup"><span data-stu-id="e71b8-331">This rule blocks the following file types from launching unless they meet prevalence or age criteria, or they're in a trusted list or an exclusion list:</span></span>

- <span data-ttu-id="e71b8-332">可執行檔 (例如 .exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="e71b8-332">Executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="e71b8-333">啟動不受信任或未知的可執行檔可能會是危險的，因為如果這些檔案是惡意的，就可能不會進行這種情況。</span><span class="sxs-lookup"><span data-stu-id="e71b8-333">Launching untrusted or unknown executable files can be risky, as it may not be initially clear if the files are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e71b8-334">您必須 [啟用雲端提供的保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 才能使用此規則。</span><span class="sxs-lookup"><span data-stu-id="e71b8-334">You must [enable cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>
>
> <span data-ttu-id="e71b8-335">規則會 **封鎖可執行檔，除非符合** 「具有 GUID 的流行」、「年齡」或「受信任」清單準則， `01443614-cd74-433a-b99e-2ecdc07bfc25` 且不是由系統管理員所指定的狀態。</span><span class="sxs-lookup"><span data-stu-id="e71b8-335">The rule **Block executable files from running unless they meet a prevalence, age, or trusted list criterion** with GUID `01443614-cd74-433a-b99e-2ecdc07bfc25` is owned by Microsoft and is not specified by admins.</span></span> <span data-ttu-id="e71b8-336">此規則使用雲端提供的保護，定期更新其信任清單。</span><span class="sxs-lookup"><span data-stu-id="e71b8-336">This rule uses cloud-delivered protection to update its trusted list regularly.</span></span>
>
> <span data-ttu-id="e71b8-337">您可以使用資料夾路徑或完全限定的資源名稱來指定個別檔案或資料夾 () 但是您無法指定適用的規則或排除專案。</span><span class="sxs-lookup"><span data-stu-id="e71b8-337">You can specify individual files or folders (using folder paths or fully qualified resource names) but you can't specify which rules or exclusions apply to.</span></span>

<span data-ttu-id="e71b8-338">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-338">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-339">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="e71b8-339">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="e71b8-340">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-340">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-341">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-341">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="e71b8-342">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="e71b8-342">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="e71b8-343">Intune 名稱： `Executables that don't meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="e71b8-343">Intune name: `Executables that don't meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="e71b8-344">Configuration Manager 名稱： `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span><span class="sxs-lookup"><span data-stu-id="e71b8-344">Configuration Manager name: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`</span></span>

<span data-ttu-id="e71b8-345">GUID:： `01443614-cd74-433a-b99e-2ecdc07bfc25`</span><span class="sxs-lookup"><span data-stu-id="e71b8-345">GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`</span></span>

### <a name="block-execution-of-potentially-obfuscated-scripts"></a><span data-ttu-id="e71b8-346">封鎖可能混淆的腳本執行</span><span class="sxs-lookup"><span data-stu-id="e71b8-346">Block execution of potentially obfuscated scripts</span></span>

<span data-ttu-id="e71b8-347">此規則會偵測模糊腳本中的可疑屬性。</span><span class="sxs-lookup"><span data-stu-id="e71b8-347">This rule detects suspicious properties within an obfuscated script.</span></span>

<span data-ttu-id="e71b8-348">腳本模糊處理是一種常見的技術，惡意程式碼作者和合法的應用程式都使用它來隱藏知識屬性或減少腳本載入時間。</span><span class="sxs-lookup"><span data-stu-id="e71b8-348">Script obfuscation is a common technique that both malware authors and legitimate applications use to hide intellectual property or decrease script loading times.</span></span> <span data-ttu-id="e71b8-349">惡意程式碼作者也會使用模糊處理，使惡意程式碼難以閱讀，這可防止人員和安全性軟體的接近審查。</span><span class="sxs-lookup"><span data-stu-id="e71b8-349">Malware authors also use obfuscation to make malicious code harder to read, which prevents close scrutiny by humans and security software.</span></span>

<span data-ttu-id="e71b8-350">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-350">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-351">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="e71b8-351">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="e71b8-352">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-352">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-353">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-353">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="e71b8-354">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="e71b8-354">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="e71b8-355">Intune 名稱： `Obfuscated js/vbs/ps/macro code`</span><span class="sxs-lookup"><span data-stu-id="e71b8-355">Intune name: `Obfuscated js/vbs/ps/macro code`</span></span>

<span data-ttu-id="e71b8-356">Configuration Manager 名稱： `Block execution of potentially obfuscated scripts`</span><span class="sxs-lookup"><span data-stu-id="e71b8-356">Configuration Manager name: `Block execution of potentially obfuscated scripts`</span></span>

<span data-ttu-id="e71b8-357">GUID:： `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span><span class="sxs-lookup"><span data-stu-id="e71b8-357">GUID: `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC`</span></span>

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a><span data-ttu-id="e71b8-358">從啟動下載的可執行內容封鎖 JavaScript 或 VBScript</span><span class="sxs-lookup"><span data-stu-id="e71b8-358">Block JavaScript or VBScript from launching downloaded executable content</span></span>

<span data-ttu-id="e71b8-359">此規則可防止腳本啟動可能已下載的惡意內容。</span><span class="sxs-lookup"><span data-stu-id="e71b8-359">This rule prevents scripts from launching potentially malicious downloaded content.</span></span> <span data-ttu-id="e71b8-360">撰寫在 JavaScript 或 VBScript 中的惡意程式碼通常是可從網際網路取得及啟動其他惡意程式碼的下載宏。</span><span class="sxs-lookup"><span data-stu-id="e71b8-360">Malware written in JavaScript or VBScript often acts as a downloader to fetch and launch other malware from the Internet.</span></span>

<span data-ttu-id="e71b8-361">雖然不是常見的企業營運應用程式，但有時會使用腳本下載及啟動安裝程式。</span><span class="sxs-lookup"><span data-stu-id="e71b8-361">Although not common, line-of-business applications sometimes use scripts to download and launch installers.</span></span>

<span data-ttu-id="e71b8-362">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-362">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-363">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="e71b8-363">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="e71b8-364">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-364">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-365">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-365">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="e71b8-366">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="e71b8-366">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="e71b8-367">Intune 名稱： `js/vbs executing payload downloaded from Internet (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="e71b8-367">Intune name: `js/vbs executing payload downloaded from Internet (no exceptions)`</span></span>

<span data-ttu-id="e71b8-368">Configuration Manager 名稱： `Block JavaScript or VBScript from launching downloaded executable content`</span><span class="sxs-lookup"><span data-stu-id="e71b8-368">Configuration Manager name: `Block JavaScript or VBScript from launching downloaded executable content`</span></span>

<span data-ttu-id="e71b8-369">GUID:： `D3E037E1-3EB8-44C8-A917-57927947596D`</span><span class="sxs-lookup"><span data-stu-id="e71b8-369">GUID: `D3E037E1-3EB8-44C8-A917-57927947596D`</span></span>

### <a name="block-office-applications-from-creating-executable-content"></a><span data-ttu-id="e71b8-370">封鎖 Office 應用程式建立可執行檔內容</span><span class="sxs-lookup"><span data-stu-id="e71b8-370">Block Office applications from creating executable content</span></span>

<span data-ttu-id="e71b8-371">此規則可防止 Office 的應用程式（包括 Word、Excel 及 PowerPoint）從建立潛在的惡意可執行檔內容，封鎖惡意程式碼寫入磁片。</span><span class="sxs-lookup"><span data-stu-id="e71b8-371">This rule prevents Office apps, including Word, Excel, and PowerPoint, from creating potentially malicious executable content, by blocking malicious code from being written to disk.</span></span>

<span data-ttu-id="e71b8-372">以向量進行濫用 Office 的惡意程式碼可能會嘗試中斷 Office，並將惡意元件儲存至磁片。</span><span class="sxs-lookup"><span data-stu-id="e71b8-372">Malware that abuses Office as a vector may attempt to break out of Office and save malicious components to disk.</span></span> <span data-ttu-id="e71b8-373">這些惡意元件會在電腦重新開機後，在系統上持續保存下來。</span><span class="sxs-lookup"><span data-stu-id="e71b8-373">These malicious components would survive a computer reboot and persist on the system.</span></span> <span data-ttu-id="e71b8-374">因此，此規則會防禦一般的持久性技術。</span><span class="sxs-lookup"><span data-stu-id="e71b8-374">Therefore, this rule defends against a common persistence technique.</span></span>

<span data-ttu-id="e71b8-375">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-375">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-376">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="e71b8-376">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="e71b8-377">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-377">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-378">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-378">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- <span data-ttu-id="e71b8-379">[System Center Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/manage/updates) (sccm) CB 1710 (SCCM 現在已 Microsoft Endpoint Configuration Manager) </span><span class="sxs-lookup"><span data-stu-id="e71b8-379">[System Center Configuration Manager](https://docs.microsoft.com/configmgr/core/servers/manage/updates) (SCCM) CB 1710 (SCCM is now Microsoft Endpoint Configuration Manager)</span></span>

<span data-ttu-id="e71b8-380">Intune 名稱： `Office apps/macros creating executable content`</span><span class="sxs-lookup"><span data-stu-id="e71b8-380">Intune name: `Office apps/macros creating executable content`</span></span>

<span data-ttu-id="e71b8-381">SCCM 名稱： `Block Office applications from creating executable content`</span><span class="sxs-lookup"><span data-stu-id="e71b8-381">SCCM name: `Block Office applications from creating executable content`</span></span>

<span data-ttu-id="e71b8-382">GUID:： `3B576869-A4EC-4529-8536-B80A7769E899`</span><span class="sxs-lookup"><span data-stu-id="e71b8-382">GUID: `3B576869-A4EC-4529-8536-B80A7769E899`</span></span>

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a><span data-ttu-id="e71b8-383">封鎖 Office 的應用程式將程式碼注入其他進程</span><span class="sxs-lookup"><span data-stu-id="e71b8-383">Block Office applications from injecting code into other processes</span></span>

<span data-ttu-id="e71b8-384">此規則封鎖程式碼注入嘗試 Office 的應用程式到其他的處理常式。</span><span class="sxs-lookup"><span data-stu-id="e71b8-384">This rule blocks code injection attempts from Office apps into other processes.</span></span>

<span data-ttu-id="e71b8-385">攻擊者可能會嘗試使用 Office 的應用程式，透過程式碼注入將惡意程式碼遷移到其他程式中，讓程式碼可以偽裝成一種乾淨的處理常式。</span><span class="sxs-lookup"><span data-stu-id="e71b8-385">Attackers might attempt to use Office apps to migrate malicious code into other processes through code injection, so the code can masquerade as a clean process.</span></span>

<span data-ttu-id="e71b8-386">使用程式碼注入，並沒有已知的合法商務目的。</span><span class="sxs-lookup"><span data-stu-id="e71b8-386">There are no known legitimate business purposes for using code injection.</span></span>

<span data-ttu-id="e71b8-387">此規則會套用至 Word、Excel 及 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="e71b8-387">This rule applies to Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="e71b8-388">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-388">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-389">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="e71b8-389">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="e71b8-390">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-390">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-391">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-391">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="e71b8-392">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="e71b8-392">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="e71b8-393">Intune 名稱： `Office apps injecting code into other processes (no exceptions)`</span><span class="sxs-lookup"><span data-stu-id="e71b8-393">Intune name: `Office apps injecting code into other processes (no exceptions)`</span></span>

<span data-ttu-id="e71b8-394">Configuration Manager 名稱： `Block Office applications from injecting code into other processes`</span><span class="sxs-lookup"><span data-stu-id="e71b8-394">Configuration Manager name: `Block Office applications from injecting code into other processes`</span></span>

<span data-ttu-id="e71b8-395">GUID:： `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span><span class="sxs-lookup"><span data-stu-id="e71b8-395">GUID: `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84`</span></span>

### <a name="block-office-communication-application-from-creating-child-processes"></a><span data-ttu-id="e71b8-396">封鎖 Office 通訊應用程式建立子流程</span><span class="sxs-lookup"><span data-stu-id="e71b8-396">Block Office communication application from creating child processes</span></span>

<span data-ttu-id="e71b8-397">此規則可防止 Outlook 建立子流程，但仍然允許合法 Outlook 函式。</span><span class="sxs-lookup"><span data-stu-id="e71b8-397">This rule prevents Outlook from creating child processes, while still allowing legitimate Outlook functions.</span></span>

<span data-ttu-id="e71b8-398">此規則可防止「社交工程」攻擊，並防止在 Outlook 中利用 abusing 弱點的程式碼。</span><span class="sxs-lookup"><span data-stu-id="e71b8-398">This rule protects against social engineering attacks and prevents exploiting code from abusing vulnerabilities in Outlook.</span></span> <span data-ttu-id="e71b8-399">它也會防止攻擊者在使用者的認證遭到破壞時可使用的[Outlook 規則和表單攻擊](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/)。</span><span class="sxs-lookup"><span data-stu-id="e71b8-399">It also protects against [Outlook rules and forms exploits](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) that attackers can use when a user's credentials are compromised.</span></span>

> [!NOTE]
> <span data-ttu-id="e71b8-400">此規則只適用于 Outlook 和 Outlook .com。</span><span class="sxs-lookup"><span data-stu-id="e71b8-400">This rule applies to Outlook and Outlook.com only.</span></span>

<span data-ttu-id="e71b8-401">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-401">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-402">Windows 10，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-402">Windows 10, version 1809</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809)
- [<span data-ttu-id="e71b8-403">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-403">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-404">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-404">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="e71b8-405">Intune 名稱： `Process creation from Office communication products (beta)`</span><span class="sxs-lookup"><span data-stu-id="e71b8-405">Intune name: `Process creation from Office communication products (beta)`</span></span>

<span data-ttu-id="e71b8-406">Configuration Manager 名稱：無法使用</span><span class="sxs-lookup"><span data-stu-id="e71b8-406">Configuration Manager name: Not available</span></span>

<span data-ttu-id="e71b8-407">GUID:： `26190899-1602-49e8-8b27-eb1d0a1ce869`</span><span class="sxs-lookup"><span data-stu-id="e71b8-407">GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`</span></span>

### <a name="block-persistence-through-wmi-event-subscription"></a><span data-ttu-id="e71b8-408">透過 WMI 事件訂閱封鎖持久性</span><span class="sxs-lookup"><span data-stu-id="e71b8-408">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="e71b8-409">此規則可防止惡意程式碼 abusing WMI 在裝置上取得持久性。</span><span class="sxs-lookup"><span data-stu-id="e71b8-409">This rule prevents malware from abusing WMI to attain persistence on a device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e71b8-410">檔案與資料夾排除不適用於此攻擊面降規則。</span><span class="sxs-lookup"><span data-stu-id="e71b8-410">File and folder exclusions don't apply to this attack surface reduction rule.</span></span>

<span data-ttu-id="e71b8-411">Fileless 威脅使用各種不同的戰術來保持隱藏狀態，以避免在檔案系統中看到，以及取得定期執行控制。</span><span class="sxs-lookup"><span data-stu-id="e71b8-411">Fileless threats employ various tactics to stay hidden, to avoid being seen in the file system, and to gain periodic execution control.</span></span> <span data-ttu-id="e71b8-412">有些威脅可以濫用 WMI 存放庫和事件模型，以保持隱藏狀態。</span><span class="sxs-lookup"><span data-stu-id="e71b8-412">Some threats can abuse the WMI repository and event model to stay hidden.</span></span>

<span data-ttu-id="e71b8-413">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-413">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-414">Windows 10，版本1903</span><span class="sxs-lookup"><span data-stu-id="e71b8-414">Windows 10, version 1903</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903)
- [<span data-ttu-id="e71b8-415">Windows伺服器1903</span><span class="sxs-lookup"><span data-stu-id="e71b8-415">Windows Server 1903</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-in-windows-server-1903-1909)

<span data-ttu-id="e71b8-416">Intune 名稱：無法使用</span><span class="sxs-lookup"><span data-stu-id="e71b8-416">Intune name: Not available</span></span>

<span data-ttu-id="e71b8-417">Configuration Manager 名稱：無法使用</span><span class="sxs-lookup"><span data-stu-id="e71b8-417">Configuration Manager name: Not available</span></span>

<span data-ttu-id="e71b8-418">GUID:： `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span><span class="sxs-lookup"><span data-stu-id="e71b8-418">GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`</span></span>

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a><span data-ttu-id="e71b8-419">封鎖來自 PSExec 和 WMI 命令的進程建立</span><span class="sxs-lookup"><span data-stu-id="e71b8-419">Block process creations originating from PSExec and WMI commands</span></span>

<span data-ttu-id="e71b8-420">此規則會封鎖透過 [PsExec](https://docs.microsoft.com/sysinternals/downloads/psexec) 和 [WMI](https://docs.microsoft.com/windows/win32/wmisdk/about-wmi) 所建立的處理常式執行。</span><span class="sxs-lookup"><span data-stu-id="e71b8-420">This rule blocks processes created through [PsExec](https://docs.microsoft.com/sysinternals/downloads/psexec) and [WMI](https://docs.microsoft.com/windows/win32/wmisdk/about-wmi) from running.</span></span> <span data-ttu-id="e71b8-421">PsExec 和 WMI 都可以遠端執行程式碼，因此惡意程式碼會 abusing 此功能以進行命令和控制，或將感染傳播到整個組織的網路。</span><span class="sxs-lookup"><span data-stu-id="e71b8-421">Both PsExec and WMI can remotely execute code, so there is a risk of malware abusing this functionality for command and control purposes, or to spread an infection throughout an organization's network.</span></span>

> [!WARNING]
> <span data-ttu-id="e71b8-422">只有在您使用 [Intune](https://docs.microsoft.com/intune) 或另一個 MDM 解決方案管理裝置時，才使用此規則。</span><span class="sxs-lookup"><span data-stu-id="e71b8-422">Only use this rule if you're managing your devices with [Intune](https://docs.microsoft.com/intune) or another MDM solution.</span></span> <span data-ttu-id="e71b8-423">因為此規則會封鎖 Configuration Manager 用戶端用來正確運作的 WMI 命令，所以此規則與管理的[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr)不相容。</span><span class="sxs-lookup"><span data-stu-id="e71b8-423">This rule is incompatible with management through [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr) because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span>

<span data-ttu-id="e71b8-424">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-424">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-425">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="e71b8-425">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="e71b8-426">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-426">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-427">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-427">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="e71b8-428">Intune 名稱： `Process creation from PSExec and WMI commands`</span><span class="sxs-lookup"><span data-stu-id="e71b8-428">Intune name: `Process creation from PSExec and WMI commands`</span></span>

<span data-ttu-id="e71b8-429">Configuration Manager 名稱：不適用</span><span class="sxs-lookup"><span data-stu-id="e71b8-429">Configuration Manager name: Not applicable</span></span>

<span data-ttu-id="e71b8-430">GUID:： `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span><span class="sxs-lookup"><span data-stu-id="e71b8-430">GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`</span></span>

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a><span data-ttu-id="e71b8-431">封鎖從 USB 執行的不受信任和未簽署程式</span><span class="sxs-lookup"><span data-stu-id="e71b8-431">Block untrusted and unsigned processes that run from USB</span></span>

<span data-ttu-id="e71b8-432">使用此規則時，系統管理員可以防止未簽署或不受信任的可執行檔，從 USB 抽取式磁碟磁碟機（包括 SD 卡）執行。</span><span class="sxs-lookup"><span data-stu-id="e71b8-432">With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.</span></span> <span data-ttu-id="e71b8-433">封鎖的檔案類型包括可執行檔 (例如 .exe、.dll 或 .scr) </span><span class="sxs-lookup"><span data-stu-id="e71b8-433">Blocked file types include executable files (such as .exe, .dll, or .scr)</span></span>

<span data-ttu-id="e71b8-434">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-434">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-435">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="e71b8-435">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="e71b8-436">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-436">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-437">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-437">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="e71b8-438">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="e71b8-438">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="e71b8-439">Intune 名稱： `Untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="e71b8-439">Intune name: `Untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="e71b8-440">Configuration Manager 名稱： `Block untrusted and unsigned processes that run from USB`</span><span class="sxs-lookup"><span data-stu-id="e71b8-440">Configuration Manager name: `Block untrusted and unsigned processes that run from USB`</span></span>

<span data-ttu-id="e71b8-441">GUID:： `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span><span class="sxs-lookup"><span data-stu-id="e71b8-441">GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`</span></span>

### <a name="block-win32-api-calls-from-office-macros"></a><span data-ttu-id="e71b8-442">從 Office 宏封鎖 WIN32 API 通話</span><span class="sxs-lookup"><span data-stu-id="e71b8-442">Block Win32 API calls from Office macros</span></span>

<span data-ttu-id="e71b8-443">此規則可防止 VBA 宏呼叫 WIN32 APIs。</span><span class="sxs-lookup"><span data-stu-id="e71b8-443">This rule prevents VBA macros from calling Win32 APIs.</span></span>

<span data-ttu-id="e71b8-444">OfficeVBA 啟用 WIN32 API 呼叫。</span><span class="sxs-lookup"><span data-stu-id="e71b8-444">Office VBA enables Win32 API calls.</span></span> <span data-ttu-id="e71b8-445">惡意程式碼可能會濫用這項功能，例如 [呼叫 WIN32 APIs 以發動惡意外殼代碼](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) ，而不需直接寫入任何內容。</span><span class="sxs-lookup"><span data-stu-id="e71b8-445">Malware can abuse this capability, such as [calling Win32 APIs to launch malicious shellcode](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) without writing anything directly to disk.</span></span> <span data-ttu-id="e71b8-446">大多數的組織不依賴在日常運作中呼叫 WIN32 APIs 的功能，即使它們是以其他方式使用宏。</span><span class="sxs-lookup"><span data-stu-id="e71b8-446">Most organizations don't rely on the ability to call Win32 APIs in their day-to-day functioning, even if they use macros in other ways.</span></span>

<span data-ttu-id="e71b8-447">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-447">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-448">Windows 10，版本1709</span><span class="sxs-lookup"><span data-stu-id="e71b8-448">Windows 10, version 1709</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709)
- [<span data-ttu-id="e71b8-449">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-449">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-450">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-450">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="e71b8-451">Configuration Manager CB 1710</span><span class="sxs-lookup"><span data-stu-id="e71b8-451">Configuration Manager CB 1710</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="e71b8-452">Intune 名稱： `Win32 imports from Office macro code`</span><span class="sxs-lookup"><span data-stu-id="e71b8-452">Intune name: `Win32 imports from Office macro code`</span></span>

<span data-ttu-id="e71b8-453">Configuration Manager 名稱： `Block Win32 API calls from Office macros`</span><span class="sxs-lookup"><span data-stu-id="e71b8-453">Configuration Manager name: `Block Win32 API calls from Office macros`</span></span>

<span data-ttu-id="e71b8-454">GUID:： `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span><span class="sxs-lookup"><span data-stu-id="e71b8-454">GUID: `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B`</span></span>

### <a name="use-advanced-protection-against-ransomware"></a><span data-ttu-id="e71b8-455">使用勒索軟體的高級防護</span><span class="sxs-lookup"><span data-stu-id="e71b8-455">Use advanced protection against ransomware</span></span>

<span data-ttu-id="e71b8-456">此規則可提供額外的保護，以防禦勒索軟體。</span><span class="sxs-lookup"><span data-stu-id="e71b8-456">This rule provides an extra layer of protection against ransomware.</span></span> <span data-ttu-id="e71b8-457">它會同時使用用戶端和雲端試探法來判斷檔案是否與勒索軟體類似。</span><span class="sxs-lookup"><span data-stu-id="e71b8-457">It uses both client and cloud heuristics to determine whether a file resembles ransomware.</span></span> <span data-ttu-id="e71b8-458">此規則不會封鎖具備下列一項或多項特性的檔案：</span><span class="sxs-lookup"><span data-stu-id="e71b8-458">This rule does not block files that have one or more of the following characteristics:</span></span>

- <span data-ttu-id="e71b8-459">檔案已在 Microsoft 雲端中找到 unharmful。</span><span class="sxs-lookup"><span data-stu-id="e71b8-459">The file has already been found to be unharmful in the Microsoft cloud.</span></span>
- <span data-ttu-id="e71b8-460">檔案是有效的簽署檔。</span><span class="sxs-lookup"><span data-stu-id="e71b8-460">The file is a valid signed file.</span></span>
- <span data-ttu-id="e71b8-461">檔案的流行不足，無法視為勒索軟體。</span><span class="sxs-lookup"><span data-stu-id="e71b8-461">The file is prevalent enough to not be considered as ransomware.</span></span>

<span data-ttu-id="e71b8-462">這項規則通常會在警告的另一個方面，以防止勒索軟體。</span><span class="sxs-lookup"><span data-stu-id="e71b8-462">The rule tends to err on the side of caution to prevent ransomware.</span></span>

> [!NOTE]
> <span data-ttu-id="e71b8-463">您必須 [啟用雲端提供的保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 才能使用此規則。</span><span class="sxs-lookup"><span data-stu-id="e71b8-463">You must [enable cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to use this rule.</span></span>

<span data-ttu-id="e71b8-464">此規則的引入時間：</span><span class="sxs-lookup"><span data-stu-id="e71b8-464">This rule was introduced in:</span></span>

- [<span data-ttu-id="e71b8-465">Windows 10，版本1803</span><span class="sxs-lookup"><span data-stu-id="e71b8-465">Windows 10, version 1803</span></span>](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803)
- [<span data-ttu-id="e71b8-466">Windows伺服器，版本1809</span><span class="sxs-lookup"><span data-stu-id="e71b8-466">Windows Server, version 1809</span></span>](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1809)
- [<span data-ttu-id="e71b8-467">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e71b8-467">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)
- [<span data-ttu-id="e71b8-468">Configuration Manager CB 1802</span><span class="sxs-lookup"><span data-stu-id="e71b8-468">Configuration Manager CB 1802</span></span>](https://docs.microsoft.com/configmgr/core/servers/manage/updates)

<span data-ttu-id="e71b8-469">Intune 名稱： `Advanced ransomware protection`</span><span class="sxs-lookup"><span data-stu-id="e71b8-469">Intune name: `Advanced ransomware protection`</span></span>

<span data-ttu-id="e71b8-470">Configuration Manager 名稱： `Use advanced protection against ransomware`</span><span class="sxs-lookup"><span data-stu-id="e71b8-470">Configuration Manager name: `Use advanced protection against ransomware`</span></span>

<span data-ttu-id="e71b8-471">GUID:： `c1db55ab-c21a-4637-bb3f-a12568109d35`</span><span class="sxs-lookup"><span data-stu-id="e71b8-471">GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`</span></span>

## <a name="see-also"></a><span data-ttu-id="e71b8-472">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e71b8-472">See also</span></span>

- [<span data-ttu-id="e71b8-473">受攻擊面縮小常見問題集</span><span class="sxs-lookup"><span data-stu-id="e71b8-473">Attack surface reduction FAQ</span></span>](attack-surface-reduction-faq.md)
- [<span data-ttu-id="e71b8-474">啟用受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="e71b8-474">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)
- [<span data-ttu-id="e71b8-475">評估受攻擊面縮小規則</span><span class="sxs-lookup"><span data-stu-id="e71b8-475">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
- [<span data-ttu-id="e71b8-476">與其他防病毒/反惡意程式碼解決方案的 Microsoft Defender 防毒軟體相容性</span><span class="sxs-lookup"><span data-stu-id="e71b8-476">Compatibility of Microsoft Defender Antivirus with other antivirus/antimalware solutions</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
