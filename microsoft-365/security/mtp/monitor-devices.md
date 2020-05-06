---
title: 裝置監控 & 報告-安全性中心
description: 說明如何讓您的裝置在組織中保持安全、最新和潛在的潛在威脅
keywords: 安全性，惡意程式碼，Microsoft 365，M365，security center，monitor，report，裝置
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 870d2ce1f70028c917cc8b165e8a1c55b746100a
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033995"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="e319c-104">Microsoft 365 security center 中的裝置監控與報告</span><span class="sxs-lookup"><span data-stu-id="e319c-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="e319c-105">在 Microsoft 365 的安全性中心，讓您的裝置具有安全、最新和潛在的潛在威脅。</span><span class="sxs-lookup"><span data-stu-id="e319c-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="e319c-106">View device alerts</span><span class="sxs-lookup"><span data-stu-id="e319c-106">View device alerts</span></span>

<span data-ttu-id="e319c-107">從 Microsoft Defender ATP 取得裝置上的侵犯行為和其他威脅的最新警示（適用于 E5 授權）。</span><span class="sxs-lookup"><span data-stu-id="e319c-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="e319c-108">Microsoft 365 的安全性中心會使用您偏好的工作流程，以較高的層次來監視這些警示。</span><span class="sxs-lookup"><span data-stu-id="e319c-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="e319c-109">監視高影響警示</span><span class="sxs-lookup"><span data-stu-id="e319c-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="e319c-110">每個 Microsoft Defender ATP 警示都有對應的嚴重性（高、中、低或資訊），指出其對您的網路的潛在影響（如果您無法自行進行）。</span><span class="sxs-lookup"><span data-stu-id="e319c-110">Each Microsoft Defender ATP alert has a corresponding severity (high, medium, low, or informational) that indicates its potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="e319c-111">使用**裝置警示嚴重性**卡片，特別針對較嚴重的提醒，而且可能需要立即回應。</span><span class="sxs-lookup"><span data-stu-id="e319c-111">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="e319c-112">您可以從這張卡片中查看 Microsoft Defender 安全中心入口網站的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e319c-112">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![裝置警示嚴重性卡片](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="e319c-114">瞭解警示來源</span><span class="sxs-lookup"><span data-stu-id="e319c-114">Understand sources of alerts</span></span>

<span data-ttu-id="e319c-115">Microsoft Defender ATP 利用各種安全性感應器和智慧來源中的資料來產生警示。</span><span class="sxs-lookup"><span data-stu-id="e319c-115">Microsoft Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="e319c-116">例如，它可以使用來自 Windows Defender 防病毒和協力廠商反惡意軟體的偵測資訊，以及您自己的自訂威脅情報（透過 web 服務 API 提供）。</span><span class="sxs-lookup"><span data-stu-id="e319c-116">For example, it can use detection information from Windows Defender Antivirus and third-party antimalware, as well as your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="e319c-117">**裝置警示偵測**"來源卡] 顯示依來源散佈的報警。</span><span class="sxs-lookup"><span data-stu-id="e319c-117">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="e319c-118">這張卡片可協助您追蹤與特定來源相關的活動，尤其是自訂來源。</span><span class="sxs-lookup"><span data-stu-id="e319c-118">This card can help you track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="e319c-119">您也可以使用此功能，專注于來自未設定為自動封鎖惡意活動或元件的感應器的警示。</span><span class="sxs-lookup"><span data-stu-id="e319c-119">You can also use this to focus on alerts coming from sensors that are not configured to automatically block malicious activity or components.</span></span>

![裝置警示偵測來源卡](../../media/device-alert-detection-sources.png)

<span data-ttu-id="e319c-121">您可以從這張卡片中查看 Microsoft Defender 安全中心入口網站的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e319c-121">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="e319c-122">瞭解觸發警示的威脅類型</span><span class="sxs-lookup"><span data-stu-id="e319c-122">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="e319c-123">Microsoft Defender ATP 會將每個警示排序為代表攻擊鏈中某一階段或威脅元件類型的類別。</span><span class="sxs-lookup"><span data-stu-id="e319c-123">Microsoft Defender ATP sorts each alert into a category representing a certain stage in the attack chain or a type of threat component.</span></span> <span data-ttu-id="e319c-124">例如，偵測到的威脅活動可能會分類為「橫向移動」，以指出嘗試到達網路上的其他裝置。</span><span class="sxs-lookup"><span data-stu-id="e319c-124">For example, a detected threat activity might be categorized as "lateral movement" to indicate that there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="e319c-125">攻擊者取得初始 foothold 後，也可能會發生該活動。</span><span class="sxs-lookup"><span data-stu-id="e319c-125">The activity has also likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="e319c-126">當偵測到威脅元件時，可能會廣泛歸類為惡意程式碼，或更特別是間諜軟體、認證偷竊或其他類型的惡意或不需要的軟體。</span><span class="sxs-lookup"><span data-stu-id="e319c-126">When detected, a threat component might either be classified broadly as malware, or more specifically as ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="e319c-127">**裝置威脅類別**卡片顯示這些類別的警示散佈。</span><span class="sxs-lookup"><span data-stu-id="e319c-127">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="e319c-128">您可以使用此資訊來識別威脅行為（例如認證盜竊企圖）相對於社交工程嘗試的影響是否較高。</span><span class="sxs-lookup"><span data-stu-id="e319c-128">You can use this information to identify threat activity, such as credential theft attempts, that can have higher impact compared to social engineering attempts.</span></span> <span data-ttu-id="e319c-129">您也可以使用此資訊來監視與勒索軟體類似的潛在破壞性威脅。</span><span class="sxs-lookup"><span data-stu-id="e319c-129">You can also use this information to monitor for potentially destructive threats like ransomware.</span></span>

![裝置威脅類別卡片](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="e319c-131">監視主動警示</span><span class="sxs-lookup"><span data-stu-id="e319c-131">Monitor active alerts</span></span>

<span data-ttu-id="e319c-132">**裝置警示狀態**卡片會指出尚未解決而且可能需要注意的警示數目。</span><span class="sxs-lookup"><span data-stu-id="e319c-132">The **Device alert status** card indicates the number of alerts that have not been resolved and might require attention.</span></span> <span data-ttu-id="e319c-133">您可以從這張卡片中查看 Microsoft Defender 安全中心入口網站的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e319c-133">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![裝置警示狀態卡片](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="e319c-135">監視已解析之警示的分類</span><span class="sxs-lookup"><span data-stu-id="e319c-135">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="e319c-136">當您解決 Microsoft Defender ATP 警示時，您的安全性人員可以指定警示是否已驗證為：</span><span class="sxs-lookup"><span data-stu-id="e319c-136">When resolving a Microsoft Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="e319c-137">可識別實際違規活動或威脅元件的真正警示</span><span class="sxs-lookup"><span data-stu-id="e319c-137">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="e319c-138">偵測到正常活動的錯誤警示</span><span class="sxs-lookup"><span data-stu-id="e319c-138">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="e319c-139">**裝置警示分類**卡會顯示您已解決的警示是否已分類為 true 或 false 警示。</span><span class="sxs-lookup"><span data-stu-id="e319c-139">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="e319c-140">您可以從這張卡片中查看 Microsoft Defender 安全中心入口網站的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e319c-140">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="e319c-141">附注：在某些情況下，無法使用特定警示的分類資訊。</span><span class="sxs-lookup"><span data-stu-id="e319c-141">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![裝置警示分類卡](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="e319c-143">監視已解決之警示的決定</span><span class="sxs-lookup"><span data-stu-id="e319c-143">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="e319c-144">除了分類決策過程中的警示是否為 true 或 false 之外，您的安全性人員可提供判斷，指出在驗證提醒時所找到的一般或惡意活動類型。</span><span class="sxs-lookup"><span data-stu-id="e319c-144">In addition to classifying whether an alert is true or false during resolution, your security staff can provide a determination, indicating the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="e319c-145">**裝置警示決定**卡片顯示針對每個警示所提供的決定。</span><span class="sxs-lookup"><span data-stu-id="e319c-145">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="e319c-146">**APT**： advanced persistent 威脅，表示偵測到的活動或威脅元件屬於複雜的破壞性之一，其設計目的是在受影響的網路中取得 foothold</span><span class="sxs-lookup"><span data-stu-id="e319c-146">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="e319c-147">**惡意**代碼：惡意檔或程式碼</span><span class="sxs-lookup"><span data-stu-id="e319c-147">**Malware**: malicious file or code</span></span>
* <span data-ttu-id="e319c-148">**安全性人員**：安全性人員所執行的一般活動</span><span class="sxs-lookup"><span data-stu-id="e319c-148">**Security personnel**: normal activity performed by security staff</span></span>
* <span data-ttu-id="e319c-149">**安全性測試**：設計用來模擬實際威脅的活動或元件，以及預期觸發安全性感應器及產生警示</span><span class="sxs-lookup"><span data-stu-id="e319c-149">**Security testing**: activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="e319c-150">不**需要的軟體**：不會被視為惡意的應用程式和其他軟體，但也違反原則或可接受的使用標準</span><span class="sxs-lookup"><span data-stu-id="e319c-150">**Unwanted software**: apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="e319c-151">**其他**：不屬於所提供類型的任何其他決定</span><span class="sxs-lookup"><span data-stu-id="e319c-151">**Others**: any other determination that does not fall under the provided types</span></span>

<span data-ttu-id="e319c-152">您可以從此卡片中查看 Microsoft Defender Security Center 中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e319c-152">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![裝置警示確定卡](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="e319c-154">瞭解哪些裝置面臨危險</span><span class="sxs-lookup"><span data-stu-id="e319c-154">Understand which devices are at risk</span></span>

<span data-ttu-id="e319c-155">**裝置保護**顯示裝置的風險層級。</span><span class="sxs-lookup"><span data-stu-id="e319c-155">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="e319c-156">風險層級是以裝置的警示類型和嚴重性等因素為基礎。</span><span class="sxs-lookup"><span data-stu-id="e319c-156">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![裝置保護卡](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="e319c-158">監視及報告 Intune 管理裝置的狀態</span><span class="sxs-lookup"><span data-stu-id="e319c-158">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="e319c-159">下列報告包含在 Intune 中註冊裝置的資料。</span><span class="sxs-lookup"><span data-stu-id="e319c-159">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="e319c-160">不包含 unenrolled 裝置中的資料。</span><span class="sxs-lookup"><span data-stu-id="e319c-160">Data from unenrolled devices is not included.</span></span> <span data-ttu-id="e319c-161">只有全域系統管理員可以查看這些卡片。</span><span class="sxs-lookup"><span data-stu-id="e319c-161">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="e319c-162">Intune 註冊的裝置資料包括：</span><span class="sxs-lookup"><span data-stu-id="e319c-162">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="e319c-163">裝置合規性</span><span class="sxs-lookup"><span data-stu-id="e319c-163">Device compliance</span></span>
* <span data-ttu-id="e319c-164">具有主動惡意程式碼的裝置</span><span class="sxs-lookup"><span data-stu-id="e319c-164">Devices with active malware</span></span>
* <span data-ttu-id="e319c-165">裝置上的惡意程式碼類型</span><span class="sxs-lookup"><span data-stu-id="e319c-165">Types of malware on devices</span></span>
* <span data-ttu-id="e319c-166">裝置上的惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="e319c-166">Malware on devices</span></span>
* <span data-ttu-id="e319c-167">具有惡意程式碼偵測的裝置</span><span class="sxs-lookup"><span data-stu-id="e319c-167">Devices with malware detections</span></span>
* <span data-ttu-id="e319c-168">具有惡意程式碼偵測的使用者</span><span class="sxs-lookup"><span data-stu-id="e319c-168">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="e319c-169">監視裝置合規性</span><span class="sxs-lookup"><span data-stu-id="e319c-169">Monitor device compliance</span></span>

<span data-ttu-id="e319c-170">**裝置合規性**顯示在 Intune 中註冊的裝置數目遵循設定原則。</span><span class="sxs-lookup"><span data-stu-id="e319c-170">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![裝置合規性卡](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="e319c-172">探索惡意程式碼偵測裝置</span><span class="sxs-lookup"><span data-stu-id="e319c-172">Discover devices with malware detections</span></span>

<span data-ttu-id="e319c-173">**裝置惡意**代碼偵測提供 Intune 註冊裝置的數目，其中包含尚未完全解決的惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="e319c-173">**Device malware detections** provide the number of Intune enrolled devices with malware that have not been fully resolved.</span></span> <span data-ttu-id="e319c-174">這可能是因為擱置的動作、重新開機、完整掃描、手動使用者動作，或修復動作未順利完成。</span><span class="sxs-lookup"><span data-stu-id="e319c-174">This can be due to pending actions, a restart, a full scan, manual user actions, or if the remediation action did not complete successfully.</span></span>

![裝置惡意軟體偵測卡](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="e319c-176">瞭解偵測到的惡意程式碼類型</span><span class="sxs-lookup"><span data-stu-id="e319c-176">Understand the types of malware detected</span></span>

<span data-ttu-id="e319c-177">**裝置上的惡意程式碼類型**顯示在已登記 Intune 之裝置上偵測到的不同類型惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="e319c-177">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="e319c-178">您可以在 Microsoft 365 的安全性中心調查每一種類型。</span><span class="sxs-lookup"><span data-stu-id="e319c-178">You can investigate each type in the Microsoft 365 security center.</span></span>

![裝置卡片上的惡意程式碼類型](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="e319c-180">瞭解裝置上偵測到的特定惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="e319c-180">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="e319c-181">**裝置上的惡意**代碼會提供裝置上偵測到的特定惡意軟體清單。</span><span class="sxs-lookup"><span data-stu-id="e319c-181">**Malware on devices** provide a list of the specific malware detected on your devices.</span></span>

![裝置卡片上的惡意程式碼](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="e319c-183">瞭解哪些裝置具有最多惡意程式碼</span><span class="sxs-lookup"><span data-stu-id="e319c-183">Understand which devices have the most malware</span></span>

<span data-ttu-id="e319c-184">**含惡意軟體**偵測的裝置會顯示哪些裝置具有最多惡意程式碼偵測。</span><span class="sxs-lookup"><span data-stu-id="e319c-184">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="e319c-185">在 Microsoft 365 的安全性中心，您可以調查惡意程式碼是作用中、使用裝置的使用者，以及其在 Intune 中的管理狀態。</span><span class="sxs-lookup"><span data-stu-id="e319c-185">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![具有惡意軟體偵測卡的裝置](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="e319c-187">瞭解哪些使用者具有最具惡意程式碼的裝置</span><span class="sxs-lookup"><span data-stu-id="e319c-187">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="e319c-188">**使用惡意軟體**偵測的使用者，可顯示具有最多惡意程式碼偵測裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="e319c-188">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="e319c-189">在 Microsoft 365 的 [安全性中心] 中，您可以查看每位使用者指派多少裝置，以及每個裝置和惡意程式碼類型的相關詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e319c-189">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![具有惡意程式碼偵測卡的使用者](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a><span data-ttu-id="e319c-191">監視及管理 ASR 規則的部署和偵測</span><span class="sxs-lookup"><span data-stu-id="e319c-191">Monitor and manage ASR rule deployment and detections</span></span>

<span data-ttu-id="e319c-192">[攻擊面降減（ASR）規則](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)可協助避免使用漏洞搜尋惡意軟體感染裝置時一般使用的動作和應用程式。</span><span class="sxs-lookup"><span data-stu-id="e319c-192">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="e319c-193">這些規則會控制可執行檔的執行時間和方式。</span><span class="sxs-lookup"><span data-stu-id="e319c-193">These rules control when and how executables can run.</span></span> <span data-ttu-id="e319c-194">例如，您可以防止 JavaScript 或 VBScript 啟動已下載的可執行檔、封鎖 Office 巨集中的 WIN32 API 呼叫，或封鎖從 USB 磁碟碟執行的程序。</span><span class="sxs-lookup"><span data-stu-id="e319c-194">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![攻擊面縮減卡](../../media/attack-surface-reduction-rules.png)

<span data-ttu-id="e319c-196">**受攻擊面縮小規則**卡提供在您的裝置之間部署規則的概觀。</span><span class="sxs-lookup"><span data-stu-id="e319c-196">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="e319c-197">卡片上的頂端列顯示在下列部署模式中的裝置總數：</span><span class="sxs-lookup"><span data-stu-id="e319c-197">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="e319c-198">**封鎖模式**：已設定至少一個規則的裝置，以封鎖偵測到的活動</span><span class="sxs-lookup"><span data-stu-id="e319c-198">**Block mode**: devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="e319c-199">**稽核模式**：沒有設定規則的裝置封鎖偵測活動，但至少有一個規則集來審核偵測到的活動</span><span class="sxs-lookup"><span data-stu-id="e319c-199">**Audit mode**: devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="e319c-200">**Off**：關閉所有 ASR 規則的裝置</span><span class="sxs-lookup"><span data-stu-id="e319c-200">**Off**: devices with all ASR rules turned off</span></span>

<span data-ttu-id="e319c-201">這個卡片的下半部會依每個裝置的規則來顯示設定。</span><span class="sxs-lookup"><span data-stu-id="e319c-201">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="e319c-202">每個列都代表已設定為封鎖或稽核偵測，或已完全關閉規則的裝置數量。</span><span class="sxs-lookup"><span data-stu-id="e319c-202">Each bar indicates the number of devices that are set to block or audit detection or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="e319c-203">查看 ASR 偵測</span><span class="sxs-lookup"><span data-stu-id="e319c-203">View ASR detections</span></span>

<span data-ttu-id="e319c-204">若要查看您網路中的 ASR 規則偵測的詳細資訊，請選取 [在**攻擊面減少規則**卡片上**查看**偵測]。</span><span class="sxs-lookup"><span data-stu-id="e319c-204">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="e319c-205">將會**開啟 [詳細報告] 頁面**中的 [偵測到] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e319c-205">The **Detections** tab in the detailed report page will open.</span></span>

![偵測] 索引標籤](../../media/detections-tab.png)

<span data-ttu-id="e319c-207">頁面頂端的圖表會顯示已封鎖或已審核之時間堆疊偵測偵測的偵測結果。</span><span class="sxs-lookup"><span data-stu-id="e319c-207">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="e319c-208">底部的資料表列出最近的偵測。</span><span class="sxs-lookup"><span data-stu-id="e319c-208">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="e319c-209">使用資料表上的下列資訊以了解偵測的性質：</span><span class="sxs-lookup"><span data-stu-id="e319c-209">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="e319c-210">偵測**到**檔案：檔案（通常是腳本或檔），其內容會觸發可疑的攻擊活動</span><span class="sxs-lookup"><span data-stu-id="e319c-210">**Detected file**: the file, typically a script or a document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="e319c-211">**規則**：名稱描述規則所設計的攻擊活動。</span><span class="sxs-lookup"><span data-stu-id="e319c-211">**Rule**: name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="e319c-212">閱讀現有的 ASR 規則</span><span class="sxs-lookup"><span data-stu-id="e319c-212">Read about existing ASR rules</span></span>
* <span data-ttu-id="e319c-213">**來源應用**程式：載入或執行的內容，會觸發可疑的攻擊活動。</span><span class="sxs-lookup"><span data-stu-id="e319c-213">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="e319c-214">這可能是合法的應用程式，例如網頁瀏覽器、Office 應用程式或類似 PowerShell 的系統工具</span><span class="sxs-lookup"><span data-stu-id="e319c-214">This could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="e319c-215">**發行者**：發行來源應用程式的廠商</span><span class="sxs-lookup"><span data-stu-id="e319c-215">**Publisher**: the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="e319c-216">複查裝置 ASR 規則設定</span><span class="sxs-lookup"><span data-stu-id="e319c-216">Review device ASR rule settings</span></span>

<span data-ttu-id="e319c-217">在 [**攻擊面減少規則\*\*\*\*報告] 頁面**中，移至 [設定] 索引標籤，以查看個別裝置的規則設定。</span><span class="sxs-lookup"><span data-stu-id="e319c-217">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="e319c-218">選取裝置以取得每個規則是否為封鎖模式、稽核模式或完全關閉的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e319c-218">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![設定] 索引標籤](../../media/configuration-tab.png)

<span data-ttu-id="e319c-220">Microsoft Intune 提供您之 ASR 規則的管理功能。</span><span class="sxs-lookup"><span data-stu-id="e319c-220">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="e319c-221">如果您想要更新您的設定，請在 [**設定裝置**] 索引標籤中選取 [**啟動**]，以在 Intune 上開啟裝置管理。</span><span class="sxs-lookup"><span data-stu-id="e319c-221">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="e319c-222">排除來自 ASR 規則的檔案</span><span class="sxs-lookup"><span data-stu-id="e319c-222">Exclude files from ASR rules</span></span>

<span data-ttu-id="e319c-223">Microsoft 365 security center 會從偵測中收集[您可能想](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules)要從偵測中排除的檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="e319c-223">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="e319c-224">透過排除檔案，您可以減少誤報的錯誤偵測，並更自信地在封鎖模式中部署攻擊面降低規則。</span><span class="sxs-lookup"><span data-stu-id="e319c-224">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="e319c-225">排除專案是在 Microsoft Intune 上進行管理，但 Microsoft 365 的安全性中心提供分析工具，可協助您瞭解檔案。</span><span class="sxs-lookup"><span data-stu-id="e319c-225">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="e319c-226">若要開始收集排除的檔案，請移至**攻擊面減少規則**報告頁面中的 [**新增排除**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e319c-226">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="e319c-227">工具會依據所有攻擊面降低規則來分析偵測，但[只有某些規則支援排除](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)。</span><span class="sxs-lookup"><span data-stu-id="e319c-227">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![新增排除] 索引標籤](../../media/add-exclusions-tab.png)

<span data-ttu-id="e319c-229">該表會列出攻擊面降低規則所偵測到的所有檔案名。</span><span class="sxs-lookup"><span data-stu-id="e319c-229">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="e319c-230">您可以選取檔案，以查看排除這些檔案的影響：</span><span class="sxs-lookup"><span data-stu-id="e319c-230">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="e319c-231">偵測數目越少</span><span class="sxs-lookup"><span data-stu-id="e319c-231">How many fewer detections</span></span>
* <span data-ttu-id="e319c-232">數量較少的裝置報告偵測</span><span class="sxs-lookup"><span data-stu-id="e319c-232">How many fewer devices report the detections</span></span>

<span data-ttu-id="e319c-233">若要取得選取檔案的完整路徑，以供排除的清單，請選取 [**取得排除路徑**]。</span><span class="sxs-lookup"><span data-stu-id="e319c-233">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="e319c-234">**從 Windows local security 機關子系統（lsass.exe）偷竊之 ASR 規則封鎖認證**的記錄，會將來源應用程式**lsass**（如偵測的檔案）捕獲為一般的系統檔案。</span><span class="sxs-lookup"><span data-stu-id="e319c-234">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**, a normal system file, as the detected file.</span></span> <span data-ttu-id="e319c-235">因此，產生的排除路徑清單會包含此檔案。</span><span class="sxs-lookup"><span data-stu-id="e319c-235">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="e319c-236">若要排除觸發此規則的檔案，而不是**lsass.exe**，請使用來源應用程式的路徑，而非偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="e319c-236">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="e319c-237">若要尋找來源應用程式，請針對此特定規則執行下列[高級搜尋查詢](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)（由規則 ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 識別）：</span><span class="sxs-lookup"><span data-stu-id="e319c-237">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="e319c-238">檢查檔案的排除</span><span class="sxs-lookup"><span data-stu-id="e319c-238">Check files for exclusion</span></span>

<span data-ttu-id="e319c-239">在從 ASR 排除檔案之前，我們建議您檢查檔案，以判斷該檔案是否確實不是惡意檔。</span><span class="sxs-lookup"><span data-stu-id="e319c-239">Before excluding a file from ASR, we recommend that you inspect the file to determine if it is indeed not malicious.</span></span>

<span data-ttu-id="e319c-240">若要查看檔案，請使用 Microsoft Defender Security Center 上的 [檔案[資訊] 頁面](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files)。</span><span class="sxs-lookup"><span data-stu-id="e319c-240">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="e319c-241">此頁面提供傳播資訊以及 VirusTotal 防病毒偵測率。</span><span class="sxs-lookup"><span data-stu-id="e319c-241">The page provides prevalence information as well as the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="e319c-242">您也可以使用頁面提交檔案進行深層分析。</span><span class="sxs-lookup"><span data-stu-id="e319c-242">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="e319c-243">若要在 Microsoft Defender Security Center 中尋找偵測到的檔案，請使用下列高級搜尋查詢搜尋所有 ASR 偵測：</span><span class="sxs-lookup"><span data-stu-id="e319c-243">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="e319c-244">使用結果中的**SHA1**或**InitiatingProcessSHA1** ，以在 Microsoft Defender Security Center 中使用通用搜尋列來搜尋檔案。</span><span class="sxs-lookup"><span data-stu-id="e319c-244">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
