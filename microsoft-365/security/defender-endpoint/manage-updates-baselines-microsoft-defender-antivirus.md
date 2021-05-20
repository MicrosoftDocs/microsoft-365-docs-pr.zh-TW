---
title: 管理 Microsoft Defender 防毒軟體更新及套用基準
description: 管理 Microsoft Defender 防毒軟體如何接收保護和產品更新。
keywords: 更新，安全性基準，保護，排程更新，強制更新，行動更新，wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 05/13/2021
ms.openlocfilehash: 17a76b39b51293de82cf9b3e5f0e323ec3d28844
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538036"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="07ad9-104">管理 Microsoft Defender 防毒軟體更新及套用基準</span><span class="sxs-lookup"><span data-stu-id="07ad9-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="07ad9-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="07ad9-105">**Applies to:**</span></span>

- [<span data-ttu-id="07ad9-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="07ad9-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="07ad9-107">Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="07ad9-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="07ad9-108">有兩種與 Microsoft Defender 防毒軟體保持最新狀態相關的更新：</span><span class="sxs-lookup"><span data-stu-id="07ad9-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="07ad9-109">安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="07ad9-109">Security intelligence updates</span></span>
- <span data-ttu-id="07ad9-110">產品更新</span><span class="sxs-lookup"><span data-stu-id="07ad9-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07ad9-111">將 Microsoft Defender 防毒軟體保持在最新狀態，是確保您的裝置具備防範新惡意程式碼和攻擊技巧所需的最新技術和功能。</span><span class="sxs-lookup"><span data-stu-id="07ad9-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="07ad9-112">即使在[被動模式下](./microsoft-defender-antivirus-compatibility.md)執行 Microsoft Defender 防毒軟體，也請務必更新防防毒保護。</span><span class="sxs-lookup"><span data-stu-id="07ad9-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="07ad9-113">若要查看最新的引擎、平臺及簽章日期，請流覽[Microsoft Defender 防毒軟體和其他 Microsoft 反惡意軟體的安全性情報更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="07ad9-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="07ad9-114">安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="07ad9-114">Security intelligence updates</span></span>

<span data-ttu-id="07ad9-115">Microsoft Defender 防毒軟體使用[雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md) (也稱為 Microsoft Advanced protection 服務或對應) ，定期下載安全性情報更新，以提供保護。</span><span class="sxs-lookup"><span data-stu-id="07ad9-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="07ad9-116">更新會在下列 KB 編號之下發行：</span><span class="sxs-lookup"><span data-stu-id="07ad9-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="07ad9-117">Microsoft Defender 防毒軟體： KB2267602</span><span class="sxs-lookup"><span data-stu-id="07ad9-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="07ad9-118">System Center Endpoint Protection： KB2461484</span><span class="sxs-lookup"><span data-stu-id="07ad9-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="07ad9-119">雲端傳送保護功能永遠都是開啟的，且需要網際網路連線才能運作。</span><span class="sxs-lookup"><span data-stu-id="07ad9-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="07ad9-120">安全智慧更新會在排程的節奏上進行， (可透過原則) 設定。</span><span class="sxs-lookup"><span data-stu-id="07ad9-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="07ad9-121">如需詳細資訊，請參閱[在 Microsoft Defender 防毒軟體中使用 Microsoft 雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="07ad9-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="07ad9-122">如需最近的安全性情報更新清單，請參閱[Microsoft Defender 防毒軟體和其他 Microsoft 反惡意軟體的安全性情報更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="07ad9-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="07ad9-123">引擎更新包含在安全性智慧更新中，並以每月的節奏發行。</span><span class="sxs-lookup"><span data-stu-id="07ad9-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="07ad9-124">產品更新</span><span class="sxs-lookup"><span data-stu-id="07ad9-124">Product updates</span></span>

<span data-ttu-id="07ad9-125">Microsoft Defender 防毒軟體需要 [每月更新 (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (稱為 *平臺更新*) ，而且會在 Windows 10 版本的情況下收到重要的功能更新。</span><span class="sxs-lookup"><span data-stu-id="07ad9-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="07ad9-126">您可以透過下列其中一種方法來管理更新的發佈：</span><span class="sxs-lookup"><span data-stu-id="07ad9-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="07ad9-127">Windows伺服器更新服務 (WSUS) </span><span class="sxs-lookup"><span data-stu-id="07ad9-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="07ad9-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="07ad9-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="07ad9-129">您用來部署 Microsoft 和 Windows 網路中端點更新的常用方法。</span><span class="sxs-lookup"><span data-stu-id="07ad9-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="07ad9-130">如需詳細資訊，請參閱[管理來源以取得 Microsoft Defender 防毒軟體保護更新](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="07ad9-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="07ad9-131">每月更新都會以階段發行，導致您的 [視窗伺服器更新服務](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)中顯示多個套件。</span><span class="sxs-lookup"><span data-stu-id="07ad9-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="07ad9-132">每月平臺及引擎版本</span><span class="sxs-lookup"><span data-stu-id="07ad9-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="07ad9-133">如需如何更新或安裝平臺更新的資訊，請參閱[Windows Defender 的反惡意程式碼平臺更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="07ad9-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="07ad9-134">我們所有的更新均包含</span><span class="sxs-lookup"><span data-stu-id="07ad9-134">All our updates contain</span></span> 
- <span data-ttu-id="07ad9-135">效能改進;</span><span class="sxs-lookup"><span data-stu-id="07ad9-135">performance improvements;</span></span>
- <span data-ttu-id="07ad9-136">可維護性改進;和</span><span class="sxs-lookup"><span data-stu-id="07ad9-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="07ad9-137"> (Cloud Microsoft 365 Defender) 的整合增強功能。</span><span class="sxs-lookup"><span data-stu-id="07ad9-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="07ad9-138">四月-2021 (平臺： 4.18.2104.14 |Engine： 1.1.18100.5) </span><span class="sxs-lookup"><span data-stu-id="07ad9-138">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="07ad9-139">&ensp;安全性智慧更新版本： **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="07ad9-140">&ensp;發行日期： **2021 年4月1日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="07ad9-141">&ensp;Platform： **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="07ad9-141">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="07ad9-142">&ensp;Engine： **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="07ad9-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="07ad9-143">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="07ad9-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ad9-144">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-144">What's new</span></span>
- <span data-ttu-id="07ad9-145">其他行為監控邏輯</span><span class="sxs-lookup"><span data-stu-id="07ad9-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="07ad9-146">改進的核心模式 keylogger 偵測</span><span class="sxs-lookup"><span data-stu-id="07ad9-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ad9-147">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-147">Known Issues</span></span>
<span data-ttu-id="07ad9-148">無已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ad9-149">三月份-2021 (平臺： 4.18.2103.7 |Engine： 1.1.18000.5) </span><span class="sxs-lookup"><span data-stu-id="07ad9-149">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="07ad9-150">&ensp;安全性智慧更新版本： **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="07ad9-151">&ensp;發行日期： **2021 年4月1日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="07ad9-152">&ensp;Platform： **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="07ad9-152">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="07ad9-153">&ensp;Engine： **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="07ad9-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="07ad9-154">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="07ad9-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ad9-155">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-155">What's new</span></span>

- <span data-ttu-id="07ad9-156">改進行為監控引擎</span><span class="sxs-lookup"><span data-stu-id="07ad9-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="07ad9-157">擴充網路暴力攻擊緩解</span><span class="sxs-lookup"><span data-stu-id="07ad9-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="07ad9-158">啟用 [防篡改保護](prevent-changes-to-security-settings-with-tamper-protection.md) 時，其他失敗的篡改嘗試事件產生</span><span class="sxs-lookup"><span data-stu-id="07ad9-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ad9-159">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-159">Known Issues</span></span>
<span data-ttu-id="07ad9-160">無已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="07ad9-161">二月份-2021 (平臺： 4.18.2102.3 |Engine： 1.1.17900.7) </span><span class="sxs-lookup"><span data-stu-id="07ad9-161">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="07ad9-162">&ensp;安全性智慧更新版本： **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="07ad9-163">&ensp;發行日期： **2021 年3月9日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="07ad9-164">&ensp;Platform： **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="07ad9-164">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="07ad9-165">&ensp;Engine： **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="07ad9-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="07ad9-166">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="07ad9-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ad9-167">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-167">What's new</span></span>

- <span data-ttu-id="07ad9-168">透過[防篡改保護](prevent-changes-to-security-settings-with-tamper-protection.md)改進服務復原</span><span class="sxs-lookup"><span data-stu-id="07ad9-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="07ad9-169">擴充不可篡改的保護範圍</span><span class="sxs-lookup"><span data-stu-id="07ad9-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ad9-170">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-170">Known Issues</span></span>
<span data-ttu-id="07ad9-171">無已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="07ad9-172">舊版本更新：僅限技術升級支援</span><span class="sxs-lookup"><span data-stu-id="07ad9-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="07ad9-173">發行新的套件版本之後，支援舊版的兩個版本只會縮小為技術支援。</span><span class="sxs-lookup"><span data-stu-id="07ad9-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="07ad9-174">這一節所列出的版本舊，僅提供支援技術升級。</span><span class="sxs-lookup"><span data-stu-id="07ad9-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="07ad9-175">2021年1月 (平臺： 4.18.2101.9 |Engine： 1.1.17800.5) </span><span class="sxs-lookup"><span data-stu-id="07ad9-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="07ad9-176">&ensp;安全性智慧更新版本： **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="07ad9-177">&ensp;發行日期： **2021 年2月2日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="07ad9-178">&ensp;Platform： **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="07ad9-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="07ad9-179">&ensp;Engine： **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="07ad9-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="07ad9-180">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="07ad9-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ad9-181">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-181">What's new</span></span>

- <span data-ttu-id="07ad9-182">外殼代碼利用偵測增強功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="07ad9-183">增強認證竊取嘗試的知名度</span><span class="sxs-lookup"><span data-stu-id="07ad9-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="07ad9-184">Microsoft Defender 防毒軟體服務中的 antitampering 功能的增強功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="07ad9-185">改進支援 ARM x64 模擬</span><span class="sxs-lookup"><span data-stu-id="07ad9-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="07ad9-186">修正：在即時保護執行初始偵測後，威脅史中仍會保留 EDR 封鎖通知</span><span class="sxs-lookup"><span data-stu-id="07ad9-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ad9-187">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-187">Known Issues</span></span>
<span data-ttu-id="07ad9-188">無已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="07ad9-189">11月-2020 (平臺： 4.18.2011.6 |Engine： 1.1.17700.4) </span><span class="sxs-lookup"><span data-stu-id="07ad9-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="07ad9-190">&ensp;安全性智慧更新版本： **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="07ad9-191">&ensp;發行日期： **2020 年12月**</span><span class="sxs-lookup"><span data-stu-id="07ad9-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="07ad9-192">&ensp;Platform： **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="07ad9-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="07ad9-193">&ensp;Engine： **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="07ad9-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="07ad9-194">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="07ad9-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ad9-195">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-195">What's new</span></span>

- <span data-ttu-id="07ad9-196">改進的 [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 狀態支援記錄</span><span class="sxs-lookup"><span data-stu-id="07ad9-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ad9-197">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-197">Known Issues</span></span>
<span data-ttu-id="07ad9-198">無已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="07ad9-199">十月-2020 (平臺： 4.18.2010.7 |Engine： 1.1.17600.5) </span><span class="sxs-lookup"><span data-stu-id="07ad9-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="07ad9-200">&ensp;安全性智慧更新版本： **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="07ad9-201">&ensp;發行日期： **2020 年10月29日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="07ad9-202">&ensp;Platform： **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="07ad9-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="07ad9-203">&ensp;Engine： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="07ad9-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="07ad9-204">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="07ad9-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ad9-205">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-205">What's new</span></span>

- <span data-ttu-id="07ad9-206">特殊威脅類別的新描述</span><span class="sxs-lookup"><span data-stu-id="07ad9-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="07ad9-207">改進模擬功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="07ad9-208">改進的主機位址允許/封鎖功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="07ad9-209">在 Defender CSP 中新增選項，以忽略本機使用者排除的合併</span><span class="sxs-lookup"><span data-stu-id="07ad9-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ad9-210">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-210">Known Issues</span></span>

<span data-ttu-id="07ad9-211">無已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="07ad9-212">九月份-2020 (平臺： 4.18.2009.7 |Engine： 1.1.17500.4) </span><span class="sxs-lookup"><span data-stu-id="07ad9-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="07ad9-213">&ensp;安全性智慧更新版本： **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="07ad9-214">&ensp;發行日期： **2020 年10月1日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="07ad9-215">&ensp;Platform： **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="07ad9-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="07ad9-216">&ensp;Engine： **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="07ad9-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="07ad9-217">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="07ad9-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ad9-218">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-218">What's new</span></span>

- <span data-ttu-id="07ad9-219">需要有系統管理員許可權，才能還原隔離中的檔案</span><span class="sxs-lookup"><span data-stu-id="07ad9-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="07ad9-220">現在支援 XML 格式化的事件</span><span class="sxs-lookup"><span data-stu-id="07ad9-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="07ad9-221">用於忽略排除合併的 CSP 支援</span><span class="sxs-lookup"><span data-stu-id="07ad9-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="07ad9-222">下列專案的新管理介面：</span><span class="sxs-lookup"><span data-stu-id="07ad9-222">New management interfaces for:</span></span>
   - <span data-ttu-id="07ad9-223">UDP 檢查</span><span class="sxs-lookup"><span data-stu-id="07ad9-223">UDP Inspection</span></span>
   - <span data-ttu-id="07ad9-224">伺服器2019上的網路保護</span><span class="sxs-lookup"><span data-stu-id="07ad9-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="07ad9-225">網路保護的 IP 位址排除</span><span class="sxs-lookup"><span data-stu-id="07ad9-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="07ad9-226">改善 TPM 測量的可見度</span><span class="sxs-lookup"><span data-stu-id="07ad9-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="07ad9-227">改進的 Office VBA 模組掃描</span><span class="sxs-lookup"><span data-stu-id="07ad9-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ad9-228">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-228">Known Issues</span></span>

<span data-ttu-id="07ad9-229">無已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="07ad9-230">八月-2020 (平臺： 4.18.2008.9 |Engine： 1.1.17400.5) </span><span class="sxs-lookup"><span data-stu-id="07ad9-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="07ad9-231">&ensp;安全性智慧更新版本： **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="07ad9-232">&ensp;發行日期： **2020 年8月27日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="07ad9-233">&ensp;Platform： **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="07ad9-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="07ad9-234">&ensp;Engine： **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="07ad9-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="07ad9-235">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="07ad9-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="07ad9-236">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-236">What's new</span></span>

- <span data-ttu-id="07ad9-237">新增更多遙測事件</span><span class="sxs-lookup"><span data-stu-id="07ad9-237">Add more telemetry events</span></span>
- <span data-ttu-id="07ad9-238">改進的掃描事件遙測</span><span class="sxs-lookup"><span data-stu-id="07ad9-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="07ad9-239">改進的記憶體掃描行為監控</span><span class="sxs-lookup"><span data-stu-id="07ad9-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="07ad9-240">改進的宏資料流程掃描</span><span class="sxs-lookup"><span data-stu-id="07ad9-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="07ad9-241">新增 `AMRunningMode` 至 Get-MpComputerStatus PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="07ad9-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="07ad9-242">會忽略[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 。</span><span class="sxs-lookup"><span data-stu-id="07ad9-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="07ad9-243">Microsoft Defender 防毒軟體會在偵測其他防毒程式時自動開啟自身。</span><span class="sxs-lookup"><span data-stu-id="07ad9-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="07ad9-244">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-244">Known Issues</span></span>
<span data-ttu-id="07ad9-245">無已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ad9-246">2020年7月- (平臺： 4.18.2007.8 |Engine： 1.1.17300.4) </span><span class="sxs-lookup"><span data-stu-id="07ad9-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="07ad9-247">&ensp;安全性智慧更新版本： **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="07ad9-248">&ensp;發行日期： **2020 年7月28日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="07ad9-249">&ensp;Platform： **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="07ad9-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="07ad9-250">&ensp;Engine： **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="07ad9-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="07ad9-251">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="07ad9-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ad9-252">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-252">What's new</span></span>

- <span data-ttu-id="07ad9-253">改進的遙測的 BITS</span><span class="sxs-lookup"><span data-stu-id="07ad9-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="07ad9-254">改進的驗證碼簽名憑證驗證</span><span class="sxs-lookup"><span data-stu-id="07ad9-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ad9-255">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-255">Known Issues</span></span>
<span data-ttu-id="07ad9-256">無已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ad9-257">六月-2020 (平臺： 4.18.2006.10 |Engine： 1.1.17200.2) </span><span class="sxs-lookup"><span data-stu-id="07ad9-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="07ad9-258">&ensp;安全性智慧更新版本： **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="07ad9-259">&ensp;發行日期： **2020 年6月22日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="07ad9-260">&ensp;Platform： **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="07ad9-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="07ad9-261">&ensp;Engine： **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="07ad9-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="07ad9-262">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="07ad9-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ad9-263">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-263">What's new</span></span>

- <span data-ttu-id="07ad9-264">可能指定[支援記錄](./collect-diagnostic-data.md)檔的位置</span><span class="sxs-lookup"><span data-stu-id="07ad9-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="07ad9-265">在被動模式中略過積極 catchup 掃描。</span><span class="sxs-lookup"><span data-stu-id="07ad9-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="07ad9-266">允許 Defender 在流量計費的連線上更新</span><span class="sxs-lookup"><span data-stu-id="07ad9-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="07ad9-267">停用快取時的固定效能調整</span><span class="sxs-lookup"><span data-stu-id="07ad9-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="07ad9-268">固定登錄查詢</span><span class="sxs-lookup"><span data-stu-id="07ad9-268">Fixed registry query</span></span> 
- <span data-ttu-id="07ad9-269">ADMX 中的固定 scantime 隨機化</span><span class="sxs-lookup"><span data-stu-id="07ad9-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ad9-270">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-270">Known Issues</span></span>
<span data-ttu-id="07ad9-271">無已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ad9-272">2020年5月 (平臺： 4.18.2005.4 |Engine： 1.1.17100.2) </span><span class="sxs-lookup"><span data-stu-id="07ad9-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="07ad9-273">&ensp;安全性智慧更新版本： **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="07ad9-274">&ensp;發行日期： **2020 年5月26日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="07ad9-275">&ensp;Platform： **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="07ad9-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="07ad9-276">&ensp;Engine： **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="07ad9-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="07ad9-277">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="07ad9-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ad9-278">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-278">What's new</span></span>

- <span data-ttu-id="07ad9-279">改進的掃描事件記錄</span><span class="sxs-lookup"><span data-stu-id="07ad9-279">Improved logging for scan events</span></span>
- <span data-ttu-id="07ad9-280">改進的使用者模式損毀處理。</span><span class="sxs-lookup"><span data-stu-id="07ad9-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="07ad9-281">新增防篡改保護的事件追蹤</span><span class="sxs-lookup"><span data-stu-id="07ad9-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="07ad9-282">修正 AMSI 範例提交</span><span class="sxs-lookup"><span data-stu-id="07ad9-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="07ad9-283">固定 AMSI Cloud 封鎖</span><span class="sxs-lookup"><span data-stu-id="07ad9-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="07ad9-284">修正的安全性更新安裝記錄檔</span><span class="sxs-lookup"><span data-stu-id="07ad9-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ad9-285">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-285">Known Issues</span></span>
<span data-ttu-id="07ad9-286">無已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ad9-287">四月-2020 (平臺： 4.18.2004.6 |Engine： 1.1.17000.2) </span><span class="sxs-lookup"><span data-stu-id="07ad9-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="07ad9-288">&ensp;安全性智慧更新版本： **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="07ad9-289">&ensp;發行日期： **2020 年4月30日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="07ad9-290">&ensp;Platform： **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="07ad9-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="07ad9-291">&ensp;Engine： **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="07ad9-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="07ad9-292">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="07ad9-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ad9-293">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-293">What's new</span></span>
- <span data-ttu-id="07ad9-294">WDfilter 改進功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-294">WDfilter improvements</span></span>
- <span data-ttu-id="07ad9-295">新增更具可操作性的事件資料至攻擊面減少偵測事件</span><span class="sxs-lookup"><span data-stu-id="07ad9-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="07ad9-296">診斷資料和 WMI 中的固定版本資訊</span><span class="sxs-lookup"><span data-stu-id="07ad9-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="07ad9-297">在平臺更新後在 UI 中修復不正確的平臺版本</span><span class="sxs-lookup"><span data-stu-id="07ad9-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="07ad9-298">動態 URL intel for Fileless 威脅防護</span><span class="sxs-lookup"><span data-stu-id="07ad9-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="07ad9-299">UEFI 掃描功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-299">UEFI scan capability</span></span>
- <span data-ttu-id="07ad9-300">擴充更新記錄</span><span class="sxs-lookup"><span data-stu-id="07ad9-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="07ad9-301">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-301">Known Issues</span></span>
<span data-ttu-id="07ad9-302">無已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ad9-303">三月份-2020 (平臺： 4.18.2003.8 |Engine： 1.1.16900.2) </span><span class="sxs-lookup"><span data-stu-id="07ad9-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="07ad9-304">&ensp;安全性智慧更新版本： **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="07ad9-305">&ensp;發行日期： **2020 年3月24日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="07ad9-306">&ensp;Platform： **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="07ad9-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="07ad9-307">&ensp;Engine： **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="07ad9-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="07ad9-308">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="07ad9-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="07ad9-309">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-309">What's new</span></span>

- <span data-ttu-id="07ad9-310">新增至[MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)的 CPU 節流選項</span><span class="sxs-lookup"><span data-stu-id="07ad9-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="07ad9-311">改善診斷功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="07ad9-312">降低安全性情報超時 (5 分鐘) </span><span class="sxs-lookup"><span data-stu-id="07ad9-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="07ad9-313">擴充 AMSI 引擎內部記錄功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="07ad9-314">改進處理常式封鎖的通知</span><span class="sxs-lookup"><span data-stu-id="07ad9-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="07ad9-315">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-315">Known Issues</span></span>
<span data-ttu-id="07ad9-316">[**Fixed**]Microsoft Defender 防毒軟體會在執行掃描時略過檔案。</span><span class="sxs-lookup"><span data-stu-id="07ad9-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="07ad9-317">二月份-2020 (平臺： |Engine： 1.1.16800.2) </span><span class="sxs-lookup"><span data-stu-id="07ad9-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="07ad9-318">&ensp;安全性智慧更新版本： **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="07ad9-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="07ad9-319">&ensp;發行日期： **2020 年2月25日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="07ad9-320">&ensp;平臺/用戶端： **-**</span><span class="sxs-lookup"><span data-stu-id="07ad9-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="07ad9-321">&ensp;Engine： **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="07ad9-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="07ad9-322">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="07ad9-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="07ad9-323">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="07ad9-324">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-324">Known Issues</span></span>
<span data-ttu-id="07ad9-325">無已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ad9-326">2020年1月 (平臺： 4.18.2001.10 |Engine： 1.1.16700.2) </span><span class="sxs-lookup"><span data-stu-id="07ad9-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="07ad9-327">安全性智慧更新版本： **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="07ad9-328">發行日期： **2020 年1月30日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="07ad9-329">Platform/Client： **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="07ad9-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="07ad9-330">Engine： **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="07ad9-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="07ad9-331">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="07ad9-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="07ad9-332">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-332">What's new</span></span>

- <span data-ttu-id="07ad9-333">具有 Exchange 的 WS2016 上的固定 BSOD</span><span class="sxs-lookup"><span data-stu-id="07ad9-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="07ad9-334">當 TMP 重新導向至網路路徑時支援平臺更新</span><span class="sxs-lookup"><span data-stu-id="07ad9-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="07ad9-335">平臺和引擎版本已新增至 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="07ad9-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="07ad9-336">將緊急特徵碼更新擴充為 [被動模式](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="07ad9-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="07ad9-337">修正4.18.1911.3 懸掛</span><span class="sxs-lookup"><span data-stu-id="07ad9-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="07ad9-338">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-338">Known Issues</span></span>

<span data-ttu-id="07ad9-339">[**Fixed**] 採用 [新式待機模式](/windows-hardware/design/device-experiences/modern-standby)的裝置可能會在 Windows Defender 篩選器驅動程式遇到中斷，從而導致保護的缺口。</span><span class="sxs-lookup"><span data-stu-id="07ad9-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="07ad9-340">受影響的機器會因尚未更新為最新的反惡意程式碼平臺而向客戶呈現。</span><span class="sxs-lookup"><span data-stu-id="07ad9-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="07ad9-341">此更新如下：</span><span class="sxs-lookup"><span data-stu-id="07ad9-341">This update is:</span></span>
> - <span data-ttu-id="07ad9-342">由執行低版本平臺的 RS1 裝置所需，以支援 SHA2;</span><span class="sxs-lookup"><span data-stu-id="07ad9-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="07ad9-343">具有懸掛問題的系統重新開機標誌;</span><span class="sxs-lookup"><span data-stu-id="07ad9-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="07ad9-344">會在4月2020內重新發佈，而且不會被更新的更新取代以保留未來的可用性;</span><span class="sxs-lookup"><span data-stu-id="07ad9-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="07ad9-345">因重新開機要求而分類為更新和</span><span class="sxs-lookup"><span data-stu-id="07ad9-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="07ad9-346">只會以[Windows 更新](https://support.microsoft.com/help/4027667/windows-10-update)提供。</span><span class="sxs-lookup"><span data-stu-id="07ad9-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="07ad9-347">11月-2019 (平臺： 4.18.1911.3 |Engine： 1.1.16600.7) </span><span class="sxs-lookup"><span data-stu-id="07ad9-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="07ad9-348">安全性智慧更新版本： **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="07ad9-349">發行日期： **2019 月7日**</span><span class="sxs-lookup"><span data-stu-id="07ad9-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="07ad9-350">Platform： **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="07ad9-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="07ad9-351">Engine： **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="07ad9-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="07ad9-352">支援階段： **不支援**</span><span class="sxs-lookup"><span data-stu-id="07ad9-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="07ad9-353">新增功能</span><span class="sxs-lookup"><span data-stu-id="07ad9-353">What's new</span></span>

- <span data-ttu-id="07ad9-354">固定 MpCmdRun 追蹤層級</span><span class="sxs-lookup"><span data-stu-id="07ad9-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="07ad9-355">固定 WDFilter 版本資訊</span><span class="sxs-lookup"><span data-stu-id="07ad9-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="07ad9-356"> (PUA) 提升通知</span><span class="sxs-lookup"><span data-stu-id="07ad9-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="07ad9-357">新增 MRT.LOG 記錄以支援檔案</span><span class="sxs-lookup"><span data-stu-id="07ad9-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="07ad9-358">已知問題</span><span class="sxs-lookup"><span data-stu-id="07ad9-358">Known Issues</span></span>
<span data-ttu-id="07ad9-359">安裝此更新時，裝置需要「跳過套件4.10.2001.10」才能更新為最新的平臺版本。</span><span class="sxs-lookup"><span data-stu-id="07ad9-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="07ad9-360">Microsoft Defender 防毒軟體平臺支援</span><span class="sxs-lookup"><span data-stu-id="07ad9-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="07ad9-361">平臺和引擎更新是以每月節奏提供。</span><span class="sxs-lookup"><span data-stu-id="07ad9-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="07ad9-362">若要完全支援，請使用最新的平臺更新來保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="07ad9-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="07ad9-363">我們的支援結構是動態的，而且會根據最新平臺版本的可用性而演變成兩個階段：</span><span class="sxs-lookup"><span data-stu-id="07ad9-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="07ad9-364">**安全性和重要更新服務階段** -執行最新的平臺版本時，您將有資格收到反惡意程式碼平臺的安全性和重要更新。</span><span class="sxs-lookup"><span data-stu-id="07ad9-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="07ad9-365">**僅限) 階段的技術支援 (** 。發行新的平臺版本之後，支援較舊版本 (n-1) 只會降低技術支援。</span><span class="sxs-lookup"><span data-stu-id="07ad9-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="07ad9-366">不再支援非 N-2 版本的平臺。</span><span class="sxs-lookup"><span data-stu-id="07ad9-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="07ad9-367">\*將繼續提供技術支援，以供從 Windows 10 發行版本本升級 (請參閱[Windows 10 版本隨附的平臺版本](#platform-version-included-with-windows-10-releases)) 至最新的平臺版本。</span><span class="sxs-lookup"><span data-stu-id="07ad9-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="07ad9-368">在技術支援 (只有) 階段，將會透過 Microsoft 客戶服務 & 支援和 Microsoft 受管理的支援服務， (例如 Premier Support) ，供應商業上合理的支援事件。</span><span class="sxs-lookup"><span data-stu-id="07ad9-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="07ad9-369">如果支援事件需要升級開發以取得進一步的指導方針、需要非安全性更新，或需要安全性更新，則系統會要求客戶升級至最新的平臺版本或中級更新 ( \* ) 。</span><span class="sxs-lookup"><span data-stu-id="07ad9-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="07ad9-370">Windows 10 版本隨附的平臺版本</span><span class="sxs-lookup"><span data-stu-id="07ad9-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="07ad9-371">下表提供隨附于最新 Windows 10 版本的 Microsoft Defender 防毒軟體平臺和引擎版本：</span><span class="sxs-lookup"><span data-stu-id="07ad9-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="07ad9-372">Windows 10 版本</span><span class="sxs-lookup"><span data-stu-id="07ad9-372">Windows 10 release</span></span>  |<span data-ttu-id="07ad9-373">平臺版本</span><span class="sxs-lookup"><span data-stu-id="07ad9-373">Platform version</span></span>  |<span data-ttu-id="07ad9-374">引擎版本</span><span class="sxs-lookup"><span data-stu-id="07ad9-374">Engine version</span></span> |<span data-ttu-id="07ad9-375">支援階段</span><span class="sxs-lookup"><span data-stu-id="07ad9-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="07ad9-376">2004 (20H1/20H2) </span><span class="sxs-lookup"><span data-stu-id="07ad9-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="07ad9-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="07ad9-377">4.18.1909.6</span></span> |<span data-ttu-id="07ad9-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="07ad9-378">1.1.17000.2</span></span> | <span data-ttu-id="07ad9-379">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="07ad9-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ad9-380">1909 (19H2) </span><span class="sxs-lookup"><span data-stu-id="07ad9-380">1909  (19H2)</span></span> |<span data-ttu-id="07ad9-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="07ad9-381">4.18.1902.5</span></span> |<span data-ttu-id="07ad9-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="07ad9-382">1.1.16700.3</span></span> | <span data-ttu-id="07ad9-383">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="07ad9-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ad9-384">1903 (19H1) </span><span class="sxs-lookup"><span data-stu-id="07ad9-384">1903  (19H1)</span></span> |<span data-ttu-id="07ad9-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="07ad9-385">4.18.1902.5</span></span> |<span data-ttu-id="07ad9-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="07ad9-386">1.1.15600.4</span></span> | <span data-ttu-id="07ad9-387">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="07ad9-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ad9-388">1809 (RS5) </span><span class="sxs-lookup"><span data-stu-id="07ad9-388">1809  (RS5)</span></span> |<span data-ttu-id="07ad9-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="07ad9-389">4.18.1807.18075</span></span> |<span data-ttu-id="07ad9-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="07ad9-390">1.1.15000.2</span></span> | <span data-ttu-id="07ad9-391">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="07ad9-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ad9-392">1803 (RS4) </span><span class="sxs-lookup"><span data-stu-id="07ad9-392">1803  (RS4)</span></span> |<span data-ttu-id="07ad9-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="07ad9-393">4.13.17134.1</span></span> |<span data-ttu-id="07ad9-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="07ad9-394">1.1.14600.4</span></span> | <span data-ttu-id="07ad9-395">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="07ad9-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ad9-396">1709 (RS3) </span><span class="sxs-lookup"><span data-stu-id="07ad9-396">1709  (RS3)</span></span> |<span data-ttu-id="07ad9-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="07ad9-397">4.12.16299.15</span></span> |<span data-ttu-id="07ad9-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="07ad9-398">1.1.14104.0</span></span> | <span data-ttu-id="07ad9-399">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="07ad9-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ad9-400">1703 (RS2) </span><span class="sxs-lookup"><span data-stu-id="07ad9-400">1703  (RS2)</span></span> |<span data-ttu-id="07ad9-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="07ad9-401">4.11.15603.2</span></span> |<span data-ttu-id="07ad9-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="07ad9-402">1.1.13504.0</span></span> | <span data-ttu-id="07ad9-403">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="07ad9-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="07ad9-404">1607 (RS1) </span><span class="sxs-lookup"><span data-stu-id="07ad9-404">1607 (RS1)</span></span> |<span data-ttu-id="07ad9-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="07ad9-405">4.10.14393.3683</span></span> |<span data-ttu-id="07ad9-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="07ad9-406">1.1.12805.0</span></span> | <span data-ttu-id="07ad9-407">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="07ad9-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="07ad9-408">如需 Windows 10 版本資訊，請參閱[Windows 生命週期事實資料表](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="07ad9-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="07ad9-409">更新部署映像服務與管理 (DISM) </span><span class="sxs-lookup"><span data-stu-id="07ad9-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="07ad9-410">建議您更新 Windows 10 (Enterprise、Pro 及 Home edition) 、Windows Server 2019，以及 Windows Server 2016 OS 安裝影像與最新的防病毒和反惡意軟體更新。</span><span class="sxs-lookup"><span data-stu-id="07ad9-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="07ad9-411">將您的作業系統安裝影像保持在最新狀態，可協助避免保護方面的缺口。</span><span class="sxs-lookup"><span data-stu-id="07ad9-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="07ad9-412">如需詳細資訊，請參閱[Microsoft Defender update for Windows 作業系統安裝影像](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="07ad9-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="07ad9-413">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="07ad9-413">1.1.2105.01</span></span></summary>

<span data-ttu-id="07ad9-414">&ensp;套件版本： **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="07ad9-414">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="07ad9-415">&ensp;平臺版本： **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="07ad9-415">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="07ad9-416">&ensp;引擎版本： **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="07ad9-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="07ad9-417">&ensp;簽章版本： **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-417">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ad9-418">修復</span><span class="sxs-lookup"><span data-stu-id="07ad9-418">Fixes</span></span>
- <span data-ttu-id="07ad9-419">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ad9-420">其他資訊</span><span class="sxs-lookup"><span data-stu-id="07ad9-420">Additional information</span></span>
- <span data-ttu-id="07ad9-421">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ad9-422">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="07ad9-422">1.1.2104.01</span></span></summary>

<span data-ttu-id="07ad9-423">&ensp;套件版本： **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="07ad9-423">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="07ad9-424">&ensp;平臺版本： **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="07ad9-424">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="07ad9-425">&ensp;引擎版本： **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="07ad9-425">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="07ad9-426">&ensp;簽章版本： **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-426">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ad9-427">修復</span><span class="sxs-lookup"><span data-stu-id="07ad9-427">Fixes</span></span>
- <span data-ttu-id="07ad9-428">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ad9-429">其他資訊</span><span class="sxs-lookup"><span data-stu-id="07ad9-429">Additional information</span></span>
- <span data-ttu-id="07ad9-430">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ad9-431">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="07ad9-431">1.1.2103.01</span></span></summary>

<span data-ttu-id="07ad9-432">&ensp;套件版本： **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="07ad9-432">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="07ad9-433">&ensp;平臺版本： **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="07ad9-433">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="07ad9-434">&ensp;引擎版本： **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="07ad9-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="07ad9-435">&ensp;簽章版本： **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-435">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ad9-436">修復</span><span class="sxs-lookup"><span data-stu-id="07ad9-436">Fixes</span></span>
- <span data-ttu-id="07ad9-437">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ad9-438">其他資訊</span><span class="sxs-lookup"><span data-stu-id="07ad9-438">Additional information</span></span>
- <span data-ttu-id="07ad9-439">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ad9-440">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="07ad9-440">1.1.2102.03</span></span></summary>

<span data-ttu-id="07ad9-441">&ensp;套件版本： **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="07ad9-441">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="07ad9-442">&ensp;平臺版本： **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="07ad9-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="07ad9-443">&ensp;引擎版本： **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="07ad9-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="07ad9-444">&ensp;簽章版本： **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-444">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ad9-445">修復</span><span class="sxs-lookup"><span data-stu-id="07ad9-445">Fixes</span></span>
- <span data-ttu-id="07ad9-446">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ad9-447">其他資訊</span><span class="sxs-lookup"><span data-stu-id="07ad9-447">Additional information</span></span>
- <span data-ttu-id="07ad9-448">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ad9-449">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="07ad9-449">1.1.2101.02</span></span></summary>

<span data-ttu-id="07ad9-450">&ensp;套件版本： **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="07ad9-450">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="07ad9-451">&ensp;平臺版本： **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="07ad9-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="07ad9-452">&ensp;引擎版本： **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="07ad9-452">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="07ad9-453">&ensp;簽章版本： **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-453">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ad9-454">修復</span><span class="sxs-lookup"><span data-stu-id="07ad9-454">Fixes</span></span>
- <span data-ttu-id="07ad9-455">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ad9-456">其他資訊</span><span class="sxs-lookup"><span data-stu-id="07ad9-456">Additional information</span></span>
- <span data-ttu-id="07ad9-457">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ad9-458">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="07ad9-458">1.1.2012.01</span></span></summary>

<span data-ttu-id="07ad9-459">&ensp;套件版本： **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="07ad9-459">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="07ad9-460">&ensp;平臺版本： **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="07ad9-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="07ad9-461">&ensp;引擎版本： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="07ad9-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="07ad9-462">&ensp;簽章版本： **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-462">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ad9-463">修復</span><span class="sxs-lookup"><span data-stu-id="07ad9-463">Fixes</span></span>
- <span data-ttu-id="07ad9-464">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ad9-465">其他資訊</span><span class="sxs-lookup"><span data-stu-id="07ad9-465">Additional information</span></span>
- <span data-ttu-id="07ad9-466">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ad9-467">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="07ad9-467">1.1.2011.02</span></span></summary>

<span data-ttu-id="07ad9-468">&ensp;套件版本： **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="07ad9-468">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="07ad9-469">&ensp;平臺版本： **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="07ad9-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="07ad9-470">&ensp;引擎版本： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="07ad9-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="07ad9-471">&ensp;簽章版本： **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-471">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ad9-472">修復</span><span class="sxs-lookup"><span data-stu-id="07ad9-472">Fixes</span></span>
- <span data-ttu-id="07ad9-473">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ad9-474">其他資訊</span><span class="sxs-lookup"><span data-stu-id="07ad9-474">Additional information</span></span>
- <span data-ttu-id="07ad9-475">更新 Microsoft Defender 防毒軟體簽章</span><span class="sxs-lookup"><span data-stu-id="07ad9-475">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ad9-476">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="07ad9-476">1.1.2011.01</span></span></summary>

<span data-ttu-id="07ad9-477">&ensp;套件版本： **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="07ad9-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="07ad9-478">&ensp;平臺版本： **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="07ad9-478">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="07ad9-479">&ensp;引擎版本： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="07ad9-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="07ad9-480">&ensp;簽章版本： **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-480">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ad9-481">修復</span><span class="sxs-lookup"><span data-stu-id="07ad9-481">Fixes</span></span>
- <span data-ttu-id="07ad9-482">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ad9-483">其他資訊</span><span class="sxs-lookup"><span data-stu-id="07ad9-483">Additional information</span></span>
- <span data-ttu-id="07ad9-484">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-484">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="07ad9-485">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="07ad9-485">1.1.2009.10</span></span></summary>

<span data-ttu-id="07ad9-486">&ensp;套件版本： **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="07ad9-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="07ad9-487">&ensp;平臺版本： **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="07ad9-487">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="07ad9-488">&ensp;引擎版本： **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="07ad9-488">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="07ad9-489">&ensp;簽章版本： **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="07ad9-489">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="07ad9-490">修復</span><span class="sxs-lookup"><span data-stu-id="07ad9-490">Fixes</span></span>
- <span data-ttu-id="07ad9-491">無</span><span class="sxs-lookup"><span data-stu-id="07ad9-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="07ad9-492">其他資訊</span><span class="sxs-lookup"><span data-stu-id="07ad9-492">Additional information</span></span>
- <span data-ttu-id="07ad9-493">新增對 Windows 10 RS1 或更新版本作業系統安裝影像的支援。</span><span class="sxs-lookup"><span data-stu-id="07ad9-493">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="07ad9-494">其他資源</span><span class="sxs-lookup"><span data-stu-id="07ad9-494">Additional resources</span></span>

| <span data-ttu-id="07ad9-495">文章</span><span class="sxs-lookup"><span data-stu-id="07ad9-495">Article</span></span> | <span data-ttu-id="07ad9-496">描述</span><span class="sxs-lookup"><span data-stu-id="07ad9-496">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="07ad9-497">適用于 Windows 作業系統安裝映射的 Microsoft Defender 更新</span><span class="sxs-lookup"><span data-stu-id="07ad9-497">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="07ad9-498">查看您 OS 安裝映射的反惡意軟體更新軟體包 (WIM 和 VHD 檔案) 。</span><span class="sxs-lookup"><span data-stu-id="07ad9-498">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="07ad9-499">取得 Windows 10 (Enterprise、Pro 和家用版的 Microsoft Defender 防毒軟體更新) 、Windows Server 2019 及 Windows Server 2016 安裝影像。</span><span class="sxs-lookup"><span data-stu-id="07ad9-499">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="07ad9-500">管理如何下載及套用保護更新</span><span class="sxs-lookup"><span data-stu-id="07ad9-500">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="07ad9-501">保護更新可透過許多來源傳遞。</span><span class="sxs-lookup"><span data-stu-id="07ad9-501">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="07ad9-502">管理應下載及套用防護更新的時間</span><span class="sxs-lookup"><span data-stu-id="07ad9-502">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="07ad9-503">您可以排程應下載保護更新的時間。</span><span class="sxs-lookup"><span data-stu-id="07ad9-503">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="07ad9-504">管理已過期端點的更新</span><span class="sxs-lookup"><span data-stu-id="07ad9-504">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="07ad9-505">如果端點未接更新或排程的掃描，您可以在下次使用者登入時強制更新或掃描。</span><span class="sxs-lookup"><span data-stu-id="07ad9-505">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="07ad9-506">管理事件型強制更新</span><span class="sxs-lookup"><span data-stu-id="07ad9-506">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="07ad9-507">您可以設定保護更新，以在啟動時或在某些雲端提供的保護事件之後下載。</span><span class="sxs-lookup"><span data-stu-id="07ad9-507">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="07ad9-508">管理行動裝置和虛擬機器 (VM) 的更新</span><span class="sxs-lookup"><span data-stu-id="07ad9-508">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="07ad9-509">您可以指定設定，例如是否應該在電池電源上進行更新，對行動裝置和虛擬機器尤其有用。</span><span class="sxs-lookup"><span data-stu-id="07ad9-509">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
