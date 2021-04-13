---
title: 管理 Microsoft Defender 防病毒更新並套用基準
description: 管理 Microsoft Defender 防病毒接收保護和產品更新的方式。
keywords: 更新，安全性基準，保護，排程更新，強制更新，行動更新，wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bf027dd7f5fad032d57d2dd0b686ccd129f568c7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690099"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="aa353-104">管理 Microsoft Defender 防病毒更新並套用基準</span><span class="sxs-lookup"><span data-stu-id="aa353-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="aa353-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="aa353-105">**Applies to:**</span></span>

- [<span data-ttu-id="aa353-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="aa353-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="aa353-107">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="aa353-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="aa353-108">有兩種與保持 Microsoft Defender 防病毒的更新相關的更新類型：</span><span class="sxs-lookup"><span data-stu-id="aa353-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="aa353-109">安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="aa353-109">Security intelligence updates</span></span>
- <span data-ttu-id="aa353-110">產品更新</span><span class="sxs-lookup"><span data-stu-id="aa353-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aa353-111">將 Microsoft Defender 防病毒保持在最新狀態，可確保您的裝置具有最新的技術和功能，以防範新的惡意程式碼和攻擊技術。</span><span class="sxs-lookup"><span data-stu-id="aa353-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>  
> <span data-ttu-id="aa353-112">即使 Microsoft Defender 防病毒是以 [被動模式](./microsoft-defender-antivirus-compatibility.md)執行，也請務必更新防防毒保護。</span><span class="sxs-lookup"><span data-stu-id="aa353-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="aa353-113">若要查看最新的引擎、平臺及簽章日期，請造訪 [Microsoft Defender 防病毒和其他 microsoft 反惡意軟體的安全性智慧更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="aa353-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="aa353-114">安全性智慧更新</span><span class="sxs-lookup"><span data-stu-id="aa353-114">Security intelligence updates</span></span>

<span data-ttu-id="aa353-115">Microsoft Defender 防病毒使用 [雲端傳送的保護](cloud-protection-microsoft-defender-antivirus.md) (也稱為 Microsoft Advanced protection 服務或對應) ，定期下載安全性情報更新，以提供保護。</span><span class="sxs-lookup"><span data-stu-id="aa353-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="aa353-116">更新會在下列 KB 編號之下發行：</span><span class="sxs-lookup"><span data-stu-id="aa353-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="aa353-117">Microsoft Defender 防毒程式： KB2267602</span><span class="sxs-lookup"><span data-stu-id="aa353-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="aa353-118">System Center Endpoint Protection： KB2461484</span><span class="sxs-lookup"><span data-stu-id="aa353-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="aa353-119">雲端傳送保護功能永遠都是開啟的，且需要網際網路連線才能運作。</span><span class="sxs-lookup"><span data-stu-id="aa353-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="aa353-120">安全智慧更新會在排程的節奏上進行， (可透過原則) 設定。</span><span class="sxs-lookup"><span data-stu-id="aa353-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="aa353-121">如需詳細資訊，請參閱 [在 Microsoft Defender 防毒軟體中使用 microsoft 雲端提供的保護](cloud-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="aa353-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="aa353-122">如需最近的安全性智慧更新清單，請參閱 [Microsoft Defender 防毒軟體和其他 microsoft 反惡意軟體的安全性智慧更新](https://www.microsoft.com/en-us/wdsi/defenderupdates)。</span><span class="sxs-lookup"><span data-stu-id="aa353-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="aa353-123">引擎更新包含在安全性智慧更新中，並以每月的節奏發行。</span><span class="sxs-lookup"><span data-stu-id="aa353-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="aa353-124">產品更新</span><span class="sxs-lookup"><span data-stu-id="aa353-124">Product updates</span></span>

<span data-ttu-id="aa353-125">Microsoft Defender 防病毒需要 [每月更新 (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (稱為 *平臺更新*) ，而且將會收到 Windows 10 版本的主要功能更新。</span><span class="sxs-lookup"><span data-stu-id="aa353-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="aa353-126">您可以透過下列其中一種方法來管理更新的發佈：</span><span class="sxs-lookup"><span data-stu-id="aa353-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="aa353-127">Windows Server Update Service (WSUS) </span><span class="sxs-lookup"><span data-stu-id="aa353-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="aa353-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="aa353-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="aa353-129">您用來將 Microsoft 和 Windows 更新部署至網路中端點的常用方法。</span><span class="sxs-lookup"><span data-stu-id="aa353-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="aa353-130">如需詳細資訊，請參閱 [管理 Microsoft Defender 防病毒防護更新的來源](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)。</span><span class="sxs-lookup"><span data-stu-id="aa353-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="aa353-131">每月更新都會以階段發行，導致您的 [視窗伺服器更新服務](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)中顯示多個套件。</span><span class="sxs-lookup"><span data-stu-id="aa353-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="aa353-132">每月平臺及引擎版本</span><span class="sxs-lookup"><span data-stu-id="aa353-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="aa353-133">如需如何更新或安裝平臺更新的資訊，請參閱 [Windows Defender 反惡意程式碼平臺的更新](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform)。</span><span class="sxs-lookup"><span data-stu-id="aa353-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="aa353-134">我們所有的更新均包含</span><span class="sxs-lookup"><span data-stu-id="aa353-134">All our updates contain</span></span> 
- <span data-ttu-id="aa353-135">效能改進;</span><span class="sxs-lookup"><span data-stu-id="aa353-135">performance improvements;</span></span>
- <span data-ttu-id="aa353-136">可維護性改進;和</span><span class="sxs-lookup"><span data-stu-id="aa353-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="aa353-137">整合功能 (Cloud，Microsoft 365 Defender) 。</span><span class="sxs-lookup"><span data-stu-id="aa353-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/><br/>

<details>
<summary> <span data-ttu-id="aa353-138">三月份-2021 (平臺： 4.18.2103.7 |Engine： 1.1.18000.5) </span><span class="sxs-lookup"><span data-stu-id="aa353-138">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="aa353-139">&ensp;安全性智慧更新版本： **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-139">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="aa353-140">&ensp;發行日期： **2021 年4月1日**</span><span class="sxs-lookup"><span data-stu-id="aa353-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="aa353-141">&ensp;Platform： **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="aa353-141">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="aa353-142">&ensp;Engine： **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="aa353-142">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="aa353-143">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="aa353-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa353-144">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-144">What's new</span></span>

- <span data-ttu-id="aa353-145">改進行為監控引擎</span><span class="sxs-lookup"><span data-stu-id="aa353-145">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="aa353-146">擴充網路暴力攻擊緩解</span><span class="sxs-lookup"><span data-stu-id="aa353-146">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="aa353-147">啟用 [防篡改保護](prevent-changes-to-security-settings-with-tamper-protection.md) 時，其他失敗的篡改嘗試事件產生</span><span class="sxs-lookup"><span data-stu-id="aa353-147">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa353-148">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-148">Known Issues</span></span>
<span data-ttu-id="aa353-149">無已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-149">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="aa353-150">二月份-2021 (平臺： 4.18.2102.3 |Engine： 1.1.17900.7) </span><span class="sxs-lookup"><span data-stu-id="aa353-150">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="aa353-151">&ensp;安全性智慧更新版本： **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-151">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="aa353-152">&ensp;發行日期： **2021 年3月9日**</span><span class="sxs-lookup"><span data-stu-id="aa353-152">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="aa353-153">&ensp;Platform： **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="aa353-153">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="aa353-154">&ensp;Engine： **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="aa353-154">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="aa353-155">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="aa353-155">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa353-156">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-156">What's new</span></span>

- <span data-ttu-id="aa353-157">透過[防篡改保護](prevent-changes-to-security-settings-with-tamper-protection.md)改進服務復原</span><span class="sxs-lookup"><span data-stu-id="aa353-157">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="aa353-158">擴充不可篡改的保護範圍</span><span class="sxs-lookup"><span data-stu-id="aa353-158">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa353-159">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-159">Known Issues</span></span>
<span data-ttu-id="aa353-160">無已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="aa353-161">2021年1月 (平臺： 4.18.2101.9 |Engine： 1.1.17800.5) </span><span class="sxs-lookup"><span data-stu-id="aa353-161">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="aa353-162">&ensp;安全性智慧更新版本： **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-162">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="aa353-163">&ensp;發行日期： **2021 年2月2日**</span><span class="sxs-lookup"><span data-stu-id="aa353-163">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="aa353-164">&ensp;Platform： **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="aa353-164">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="aa353-165">&ensp;Engine： **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="aa353-165">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="aa353-166">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="aa353-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa353-167">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-167">What's new</span></span>

- <span data-ttu-id="aa353-168">外殼代碼利用偵測增強功能</span><span class="sxs-lookup"><span data-stu-id="aa353-168">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="aa353-169">增強認證竊取嘗試的知名度</span><span class="sxs-lookup"><span data-stu-id="aa353-169">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="aa353-170">Microsoft Defender 防病毒服務中的 antitampering 功能增強功能</span><span class="sxs-lookup"><span data-stu-id="aa353-170">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="aa353-171">改進支援 ARM x64 模擬</span><span class="sxs-lookup"><span data-stu-id="aa353-171">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="aa353-172">修正：在即時保護執行初始偵測後，EDR 封鎖通知會保留在威脅史中</span><span class="sxs-lookup"><span data-stu-id="aa353-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa353-173">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-173">Known Issues</span></span>
<span data-ttu-id="aa353-174">無已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-174">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="aa353-175">舊版本更新：僅限技術升級支援</span><span class="sxs-lookup"><span data-stu-id="aa353-175">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="aa353-176">發行新的套件版本之後，支援舊版的兩個版本只會縮小為技術支援。</span><span class="sxs-lookup"><span data-stu-id="aa353-176">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="aa353-177">這一節所列出的版本舊，僅提供支援技術升級。</span><span class="sxs-lookup"><span data-stu-id="aa353-177">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="aa353-178">11月-2020 (平臺： 4.18.2011.6 |Engine： 1.1.17700.4) </span><span class="sxs-lookup"><span data-stu-id="aa353-178">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="aa353-179">&ensp;安全性智慧更新版本： **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-179">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="aa353-180">&ensp;發行日期： **2020 年12月**</span><span class="sxs-lookup"><span data-stu-id="aa353-180">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="aa353-181">&ensp;Platform： **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="aa353-181">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="aa353-182">&ensp;Engine： **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="aa353-182">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="aa353-183">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="aa353-183">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa353-184">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-184">What's new</span></span>

- <span data-ttu-id="aa353-185">改進的 [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 狀態支援記錄</span><span class="sxs-lookup"><span data-stu-id="aa353-185">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa353-186">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-186">Known Issues</span></span>
<span data-ttu-id="aa353-187">無已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-187">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="aa353-188">十月-2020 (平臺： 4.18.2010.7 |Engine： 1.1.17600.5) </span><span class="sxs-lookup"><span data-stu-id="aa353-188">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="aa353-189">&ensp;安全性智慧更新版本： **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-189">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="aa353-190">&ensp;發行日期： **2020 年10月29日**</span><span class="sxs-lookup"><span data-stu-id="aa353-190">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="aa353-191">&ensp;Platform： **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="aa353-191">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="aa353-192">&ensp;Engine： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="aa353-192">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="aa353-193">&ensp;支援階段： **安全性和重要更新**</span><span class="sxs-lookup"><span data-stu-id="aa353-193">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa353-194">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-194">What's new</span></span>

- <span data-ttu-id="aa353-195">特殊威脅類別的新描述</span><span class="sxs-lookup"><span data-stu-id="aa353-195">New descriptions for special threat categories</span></span>
- <span data-ttu-id="aa353-196">改進模擬功能</span><span class="sxs-lookup"><span data-stu-id="aa353-196">Improved emulation capabilities</span></span>
- <span data-ttu-id="aa353-197">改進的主機位址允許/封鎖功能</span><span class="sxs-lookup"><span data-stu-id="aa353-197">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="aa353-198">在 Defender CSP 中新增選項，以忽略本機使用者排除的合併</span><span class="sxs-lookup"><span data-stu-id="aa353-198">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa353-199">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-199">Known Issues</span></span>

<span data-ttu-id="aa353-200">無已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="aa353-201">九月份-2020 (平臺： 4.18.2009.7 |Engine： 1.1.17500.4) </span><span class="sxs-lookup"><span data-stu-id="aa353-201">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="aa353-202">&ensp;安全性智慧更新版本： **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-202">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="aa353-203">&ensp;發行日期： **2020 年10月1日**</span><span class="sxs-lookup"><span data-stu-id="aa353-203">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="aa353-204">&ensp;Platform： **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="aa353-204">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="aa353-205">&ensp;Engine： **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="aa353-205">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="aa353-206">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="aa353-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa353-207">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-207">What's new</span></span>

- <span data-ttu-id="aa353-208">需要有系統管理員許可權，才能還原隔離中的檔案</span><span class="sxs-lookup"><span data-stu-id="aa353-208">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="aa353-209">現在支援 XML 格式化的事件</span><span class="sxs-lookup"><span data-stu-id="aa353-209">XML formatted events are now supported</span></span>
- <span data-ttu-id="aa353-210">用於忽略排除合併的 CSP 支援</span><span class="sxs-lookup"><span data-stu-id="aa353-210">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="aa353-211">下列專案的新管理介面：</span><span class="sxs-lookup"><span data-stu-id="aa353-211">New management interfaces for:</span></span>
   - <span data-ttu-id="aa353-212">UDP 檢查</span><span class="sxs-lookup"><span data-stu-id="aa353-212">UDP Inspection</span></span>
   - <span data-ttu-id="aa353-213">伺服器2019上的網路保護</span><span class="sxs-lookup"><span data-stu-id="aa353-213">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="aa353-214">網路保護的 IP 位址排除</span><span class="sxs-lookup"><span data-stu-id="aa353-214">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="aa353-215">改善 TPM 測量的可見度</span><span class="sxs-lookup"><span data-stu-id="aa353-215">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="aa353-216">改進的 Office VBA 模組掃描</span><span class="sxs-lookup"><span data-stu-id="aa353-216">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa353-217">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-217">Known Issues</span></span>

<span data-ttu-id="aa353-218">無已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-218">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="aa353-219">八月-2020 (平臺： 4.18.2008.9 |Engine： 1.1.17400.5) </span><span class="sxs-lookup"><span data-stu-id="aa353-219">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="aa353-220">&ensp;安全性智慧更新版本： **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-220">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="aa353-221">&ensp;發行日期： **2020 年8月27日**</span><span class="sxs-lookup"><span data-stu-id="aa353-221">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="aa353-222">&ensp;Platform： **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="aa353-222">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="aa353-223">&ensp;Engine： **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="aa353-223">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="aa353-224">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="aa353-224">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="aa353-225">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-225">What's new</span></span>

- <span data-ttu-id="aa353-226">新增更多遙測事件</span><span class="sxs-lookup"><span data-stu-id="aa353-226">Add more telemetry events</span></span>
- <span data-ttu-id="aa353-227">改進的掃描事件遙測</span><span class="sxs-lookup"><span data-stu-id="aa353-227">Improved scan event telemetry</span></span>
- <span data-ttu-id="aa353-228">改進的記憶體掃描行為監控</span><span class="sxs-lookup"><span data-stu-id="aa353-228">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="aa353-229">改進的宏資料流程掃描</span><span class="sxs-lookup"><span data-stu-id="aa353-229">Improved macro streams scanning</span></span>
- <span data-ttu-id="aa353-230">新增 `AMRunningMode` 至 Get-MpComputerStatus PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="aa353-230">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="aa353-231">會忽略[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 。</span><span class="sxs-lookup"><span data-stu-id="aa353-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="aa353-232">當 Microsoft Defender 防毒程式偵測到其他防毒程式時，會自動自行關閉。</span><span class="sxs-lookup"><span data-stu-id="aa353-232">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="aa353-233">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-233">Known Issues</span></span>
<span data-ttu-id="aa353-234">無已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-234">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa353-235">2020年7月- (平臺： 4.18.2007.8 |Engine： 1.1.17300.4) </span><span class="sxs-lookup"><span data-stu-id="aa353-235">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="aa353-236">&ensp;安全性智慧更新版本： **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-236">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="aa353-237">&ensp;發行日期： **2020 年7月28日**</span><span class="sxs-lookup"><span data-stu-id="aa353-237">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="aa353-238">&ensp;Platform： **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="aa353-238">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="aa353-239">&ensp;Engine： **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="aa353-239">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="aa353-240">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="aa353-240">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa353-241">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-241">What's new</span></span>

- <span data-ttu-id="aa353-242">改進的遙測的 BITS</span><span class="sxs-lookup"><span data-stu-id="aa353-242">Improved telemetry for BITS</span></span>
- <span data-ttu-id="aa353-243">改進的驗證碼簽名憑證驗證</span><span class="sxs-lookup"><span data-stu-id="aa353-243">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa353-244">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-244">Known Issues</span></span>
<span data-ttu-id="aa353-245">無已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa353-246">六月-2020 (平臺： 4.18.2006.10 |Engine： 1.1.17200.2) </span><span class="sxs-lookup"><span data-stu-id="aa353-246">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="aa353-247">&ensp;安全性智慧更新版本： **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-247">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="aa353-248">&ensp;發行日期： **2020 年6月22日**</span><span class="sxs-lookup"><span data-stu-id="aa353-248">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="aa353-249">&ensp;Platform： **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="aa353-249">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="aa353-250">&ensp;Engine： **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="aa353-250">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="aa353-251">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="aa353-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa353-252">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-252">What's new</span></span>

- <span data-ttu-id="aa353-253">可能指定[支援記錄](./collect-diagnostic-data.md)檔的位置</span><span class="sxs-lookup"><span data-stu-id="aa353-253">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="aa353-254">在被動模式中略過積極 catchup 掃描。</span><span class="sxs-lookup"><span data-stu-id="aa353-254">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="aa353-255">允許 Defender 在流量計費的連線上更新</span><span class="sxs-lookup"><span data-stu-id="aa353-255">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="aa353-256">停用快取時的固定效能調整</span><span class="sxs-lookup"><span data-stu-id="aa353-256">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="aa353-257">固定登錄查詢</span><span class="sxs-lookup"><span data-stu-id="aa353-257">Fixed registry query</span></span> 
- <span data-ttu-id="aa353-258">ADMX 中的固定 scantime 隨機化</span><span class="sxs-lookup"><span data-stu-id="aa353-258">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa353-259">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-259">Known Issues</span></span>
<span data-ttu-id="aa353-260">無已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-260">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa353-261">2020年5月 (平臺： 4.18.2005.4 |Engine： 1.1.17100.2) </span><span class="sxs-lookup"><span data-stu-id="aa353-261">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="aa353-262">&ensp;安全性智慧更新版本： **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-262">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="aa353-263">&ensp;發行日期： **2020 年5月26日**</span><span class="sxs-lookup"><span data-stu-id="aa353-263">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="aa353-264">&ensp;Platform： **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="aa353-264">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="aa353-265">&ensp;Engine： **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="aa353-265">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="aa353-266">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="aa353-266">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa353-267">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-267">What's new</span></span>

- <span data-ttu-id="aa353-268">改進的掃描事件記錄</span><span class="sxs-lookup"><span data-stu-id="aa353-268">Improved logging for scan events</span></span>
- <span data-ttu-id="aa353-269">改進的使用者模式損毀處理。</span><span class="sxs-lookup"><span data-stu-id="aa353-269">Improved user mode crash handling.</span></span>
- <span data-ttu-id="aa353-270">新增防篡改保護的事件追蹤</span><span class="sxs-lookup"><span data-stu-id="aa353-270">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="aa353-271">修正 AMSI 範例提交</span><span class="sxs-lookup"><span data-stu-id="aa353-271">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="aa353-272">固定 AMSI Cloud 封鎖</span><span class="sxs-lookup"><span data-stu-id="aa353-272">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="aa353-273">修正的安全性更新安裝記錄檔</span><span class="sxs-lookup"><span data-stu-id="aa353-273">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa353-274">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-274">Known Issues</span></span>
<span data-ttu-id="aa353-275">無已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-275">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa353-276">四月-2020 (平臺： 4.18.2004.6 |Engine： 1.1.17000.2) </span><span class="sxs-lookup"><span data-stu-id="aa353-276">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="aa353-277">&ensp;安全性智慧更新版本： **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-277">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="aa353-278">&ensp;發行日期： **2020 年4月30日**</span><span class="sxs-lookup"><span data-stu-id="aa353-278">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="aa353-279">&ensp;Platform： **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="aa353-279">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="aa353-280">&ensp;Engine： **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="aa353-280">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="aa353-281">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="aa353-281">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa353-282">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-282">What's new</span></span>
- <span data-ttu-id="aa353-283">WDfilter 改進功能</span><span class="sxs-lookup"><span data-stu-id="aa353-283">WDfilter improvements</span></span>
- <span data-ttu-id="aa353-284">新增更具可操作性的事件資料至攻擊面減少偵測事件</span><span class="sxs-lookup"><span data-stu-id="aa353-284">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="aa353-285">診斷資料和 WMI 中的固定版本資訊</span><span class="sxs-lookup"><span data-stu-id="aa353-285">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="aa353-286">在平臺更新後在 UI 中修復不正確的平臺版本</span><span class="sxs-lookup"><span data-stu-id="aa353-286">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="aa353-287">動態 URL intel for Fileless 威脅防護</span><span class="sxs-lookup"><span data-stu-id="aa353-287">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="aa353-288">UEFI 掃描功能</span><span class="sxs-lookup"><span data-stu-id="aa353-288">UEFI scan capability</span></span>
- <span data-ttu-id="aa353-289">擴充更新記錄</span><span class="sxs-lookup"><span data-stu-id="aa353-289">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="aa353-290">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-290">Known Issues</span></span>
<span data-ttu-id="aa353-291">無已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-291">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa353-292">三月份-2020 (平臺： 4.18.2003.8 |Engine： 1.1.16900.2) </span><span class="sxs-lookup"><span data-stu-id="aa353-292">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="aa353-293">&ensp;安全性智慧更新版本： **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-293">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="aa353-294">&ensp;發行日期： **2020 年3月24日**</span><span class="sxs-lookup"><span data-stu-id="aa353-294">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="aa353-295">&ensp;Platform： **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="aa353-295">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="aa353-296">&ensp;Engine： **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="aa353-296">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="aa353-297">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="aa353-297">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="aa353-298">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-298">What's new</span></span>

- <span data-ttu-id="aa353-299">新增至[MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)的 CPU 節流選項</span><span class="sxs-lookup"><span data-stu-id="aa353-299">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="aa353-300">改善診斷功能</span><span class="sxs-lookup"><span data-stu-id="aa353-300">Improve diagnostic capability</span></span>
- <span data-ttu-id="aa353-301">降低安全性情報超時 (5 分鐘) </span><span class="sxs-lookup"><span data-stu-id="aa353-301">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="aa353-302">擴充 AMSI 引擎內部記錄功能</span><span class="sxs-lookup"><span data-stu-id="aa353-302">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="aa353-303">改進處理常式封鎖的通知</span><span class="sxs-lookup"><span data-stu-id="aa353-303">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="aa353-304">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-304">Known Issues</span></span>
<span data-ttu-id="aa353-305">[**Fixed**]Microsoft Defender 防毒程式正在執行掃描時略過檔案。</span><span class="sxs-lookup"><span data-stu-id="aa353-305">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="aa353-306">二月份-2020 (平臺： |Engine： 1.1.16800.2) </span><span class="sxs-lookup"><span data-stu-id="aa353-306">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="aa353-307">&ensp;安全性智慧更新版本： **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="aa353-307">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="aa353-308">&ensp;發行日期： **2020 年2月25日**</span><span class="sxs-lookup"><span data-stu-id="aa353-308">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="aa353-309">&ensp;平臺/用戶端： **-**</span><span class="sxs-lookup"><span data-stu-id="aa353-309">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="aa353-310">&ensp;Engine： **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="aa353-310">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="aa353-311">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="aa353-311">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="aa353-312">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-312">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="aa353-313">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-313">Known Issues</span></span>
<span data-ttu-id="aa353-314">無已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-314">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa353-315">2020年1月 (平臺： 4.18.2001.10 |Engine： 1.1.16700.2) </span><span class="sxs-lookup"><span data-stu-id="aa353-315">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="aa353-316">安全性智慧更新版本： **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-316">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="aa353-317">發行日期： **2020 年1月30日**</span><span class="sxs-lookup"><span data-stu-id="aa353-317">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="aa353-318">Platform/Client： **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="aa353-318">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="aa353-319">Engine： **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="aa353-319">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="aa353-320">&ensp;支援階段： **僅限技術升級支援 ()**</span><span class="sxs-lookup"><span data-stu-id="aa353-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="aa353-321">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-321">What's new</span></span>

- <span data-ttu-id="aa353-322">WS2016 with Exchange 上的固定 BSOD</span><span class="sxs-lookup"><span data-stu-id="aa353-322">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="aa353-323">當 TMP 重新導向至網路路徑時支援平臺更新</span><span class="sxs-lookup"><span data-stu-id="aa353-323">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="aa353-324">平臺和引擎版本已新增至 [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="aa353-324">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="aa353-325">將緊急特徵碼更新擴充為 [被動模式](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="aa353-325">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="aa353-326">修正4.18.1911.3 懸掛</span><span class="sxs-lookup"><span data-stu-id="aa353-326">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="aa353-327">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-327">Known Issues</span></span>

<span data-ttu-id="aa353-328">[**Fixed**] 採用 [新式待機模式](/windows-hardware/design/device-experiences/modern-standby) 的裝置可能會在 Windows Defender 篩選器驅動程式發生掛起，以導致保護的缺口。</span><span class="sxs-lookup"><span data-stu-id="aa353-328">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="aa353-329">受影響的機器會因尚未更新為最新的反惡意程式碼平臺而向客戶呈現。</span><span class="sxs-lookup"><span data-stu-id="aa353-329">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="aa353-330">此更新如下：</span><span class="sxs-lookup"><span data-stu-id="aa353-330">This update is:</span></span>
> - <span data-ttu-id="aa353-331">由執行低版本平臺的 RS1 裝置所需，以支援 SHA2;</span><span class="sxs-lookup"><span data-stu-id="aa353-331">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="aa353-332">具有懸掛問題的系統重新開機標誌;</span><span class="sxs-lookup"><span data-stu-id="aa353-332">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="aa353-333">會在4月2020內重新發佈，而且不會被更新的更新取代以保留未來的可用性;</span><span class="sxs-lookup"><span data-stu-id="aa353-333">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="aa353-334">因重新開機要求而分類為更新和</span><span class="sxs-lookup"><span data-stu-id="aa353-334">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="aa353-335">只會以 [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update)提供。</span><span class="sxs-lookup"><span data-stu-id="aa353-335">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="aa353-336">11月-2019 (平臺： 4.18.1911.3 |Engine： 1.1.16600.7) </span><span class="sxs-lookup"><span data-stu-id="aa353-336">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="aa353-337">安全性智慧更新版本： **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-337">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="aa353-338">發行日期： **2019 月7日**</span><span class="sxs-lookup"><span data-stu-id="aa353-338">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="aa353-339">Platform： **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="aa353-339">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="aa353-340">Engine： **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="aa353-340">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="aa353-341">支援階段： **不支援**</span><span class="sxs-lookup"><span data-stu-id="aa353-341">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="aa353-342">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa353-342">What's new</span></span>

- <span data-ttu-id="aa353-343">固定 MpCmdRun 追蹤層級</span><span class="sxs-lookup"><span data-stu-id="aa353-343">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="aa353-344">固定 WDFilter 版本資訊</span><span class="sxs-lookup"><span data-stu-id="aa353-344">Fixed WDFilter version info</span></span>
- <span data-ttu-id="aa353-345"> (PUA) 提升通知</span><span class="sxs-lookup"><span data-stu-id="aa353-345">Improve notifications (PUA)</span></span>
- <span data-ttu-id="aa353-346">新增 MRT.LOG 記錄以支援檔案</span><span class="sxs-lookup"><span data-stu-id="aa353-346">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="aa353-347">已知問題</span><span class="sxs-lookup"><span data-stu-id="aa353-347">Known Issues</span></span>
<span data-ttu-id="aa353-348">安裝此更新時，裝置需要「跳過套件4.10.2001.10」才能更新為最新的平臺版本。</span><span class="sxs-lookup"><span data-stu-id="aa353-348">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="aa353-349">Microsoft Defender 防病毒平臺支援</span><span class="sxs-lookup"><span data-stu-id="aa353-349">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="aa353-350">平臺和引擎更新是以每月節奏提供。</span><span class="sxs-lookup"><span data-stu-id="aa353-350">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="aa353-351">若要完全支援，請使用最新的平臺更新來保持最新狀態。</span><span class="sxs-lookup"><span data-stu-id="aa353-351">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="aa353-352">我們的支援結構是動態的，而且會根據最新平臺版本的可用性而演變成兩個階段：</span><span class="sxs-lookup"><span data-stu-id="aa353-352">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="aa353-353">**安全性和重要更新服務階段** -執行最新的平臺版本時，您將有資格收到反惡意程式碼平臺的安全性和重要更新。</span><span class="sxs-lookup"><span data-stu-id="aa353-353">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="aa353-354">**僅限) 階段的技術支援 (** 。發行新的平臺版本之後，支援較舊版本 (n-1) 只會降低技術支援。</span><span class="sxs-lookup"><span data-stu-id="aa353-354">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="aa353-355">不再支援非 N-2 版本的平臺。</span><span class="sxs-lookup"><span data-stu-id="aa353-355">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="aa353-356">\* 系統會繼續提供技術支援，以供從 Windows 10 發行版本本升級 (請參閱 [windows 10 版本隨附的平臺版本](#platform-version-included-with-windows-10-releases)) 至最新版平臺。</span><span class="sxs-lookup"><span data-stu-id="aa353-356">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="aa353-357">在技術支援 (只有) 階段，將會透過 Microsoft 客戶服務 & 支援和 Microsoft 受管理的支援服務， (例如 Premier Support) ，供應商業上合理的支援事件。</span><span class="sxs-lookup"><span data-stu-id="aa353-357">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="aa353-358">如果支援事件需要升級開發以取得進一步的指導方針、需要非安全性更新，或需要安全性更新，則系統會要求客戶升級至最新的平臺版本或中級更新 ( \* ) 。</span><span class="sxs-lookup"><span data-stu-id="aa353-358">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="aa353-359">Windows 10 版本隨附的平臺版本</span><span class="sxs-lookup"><span data-stu-id="aa353-359">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="aa353-360">下表提供 Microsoft Defender 防病毒平臺和引擎版本，隨附于最新的 Windows 10 版本：</span><span class="sxs-lookup"><span data-stu-id="aa353-360">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="aa353-361">Windows 10 版本</span><span class="sxs-lookup"><span data-stu-id="aa353-361">Windows 10 release</span></span>  |<span data-ttu-id="aa353-362">平臺版本</span><span class="sxs-lookup"><span data-stu-id="aa353-362">Platform version</span></span>  |<span data-ttu-id="aa353-363">引擎版本</span><span class="sxs-lookup"><span data-stu-id="aa353-363">Engine version</span></span> |<span data-ttu-id="aa353-364">支援階段</span><span class="sxs-lookup"><span data-stu-id="aa353-364">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="aa353-365">2004 (20H1/20H2) </span><span class="sxs-lookup"><span data-stu-id="aa353-365">2004  (20H1/20H2)</span></span> |<span data-ttu-id="aa353-366">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="aa353-366">4.18.1909.6</span></span> |<span data-ttu-id="aa353-367">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="aa353-367">1.1.17000.2</span></span> | <span data-ttu-id="aa353-368">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="aa353-368">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa353-369">1909 (19H2) </span><span class="sxs-lookup"><span data-stu-id="aa353-369">1909  (19H2)</span></span> |<span data-ttu-id="aa353-370">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="aa353-370">4.18.1902.5</span></span> |<span data-ttu-id="aa353-371">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="aa353-371">1.1.16700.3</span></span> | <span data-ttu-id="aa353-372">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="aa353-372">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa353-373">1903 (19H1) </span><span class="sxs-lookup"><span data-stu-id="aa353-373">1903  (19H1)</span></span> |<span data-ttu-id="aa353-374">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="aa353-374">4.18.1902.5</span></span> |<span data-ttu-id="aa353-375">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="aa353-375">1.1.15600.4</span></span> | <span data-ttu-id="aa353-376">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="aa353-376">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa353-377">1809 (RS5) </span><span class="sxs-lookup"><span data-stu-id="aa353-377">1809  (RS5)</span></span> |<span data-ttu-id="aa353-378">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="aa353-378">4.18.1807.18075</span></span> |<span data-ttu-id="aa353-379">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="aa353-379">1.1.15000.2</span></span> | <span data-ttu-id="aa353-380">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="aa353-380">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa353-381">1803 (RS4) </span><span class="sxs-lookup"><span data-stu-id="aa353-381">1803  (RS4)</span></span> |<span data-ttu-id="aa353-382">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="aa353-382">4.13.17134.1</span></span> |<span data-ttu-id="aa353-383">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="aa353-383">1.1.14600.4</span></span> | <span data-ttu-id="aa353-384">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="aa353-384">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa353-385">1709 (RS3) </span><span class="sxs-lookup"><span data-stu-id="aa353-385">1709  (RS3)</span></span> |<span data-ttu-id="aa353-386">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="aa353-386">4.12.16299.15</span></span> |<span data-ttu-id="aa353-387">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="aa353-387">1.1.14104.0</span></span> | <span data-ttu-id="aa353-388">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="aa353-388">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa353-389">1703 (RS2) </span><span class="sxs-lookup"><span data-stu-id="aa353-389">1703  (RS2)</span></span> |<span data-ttu-id="aa353-390">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="aa353-390">4.11.15603.2</span></span> |<span data-ttu-id="aa353-391">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="aa353-391">1.1.13504.0</span></span> | <span data-ttu-id="aa353-392">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="aa353-392">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="aa353-393">1607 (RS1) </span><span class="sxs-lookup"><span data-stu-id="aa353-393">1607 (RS1)</span></span> |<span data-ttu-id="aa353-394">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="aa353-394">4.10.14393.3683</span></span> |<span data-ttu-id="aa353-395">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="aa353-395">1.1.12805.0</span></span> | <span data-ttu-id="aa353-396">技術升級只支援 () </span><span class="sxs-lookup"><span data-stu-id="aa353-396">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="aa353-397">如需 Windows 10 版本資訊，請參閱 [Windows 生命週期事實資料表](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)。</span><span class="sxs-lookup"><span data-stu-id="aa353-397">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="aa353-398">更新部署映像服務與管理 (DISM) </span><span class="sxs-lookup"><span data-stu-id="aa353-398">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="aa353-399">建議您更新 Windows 10 (Enterprise、Pro 和 Home edition) 、Windows Server 2019 及 Windows Server 2016 OS 安裝影像，並提供最新的防病毒和反惡意軟體更新。</span><span class="sxs-lookup"><span data-stu-id="aa353-399">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="aa353-400">將您的作業系統安裝影像保持在最新狀態，可協助避免保護方面的缺口。</span><span class="sxs-lookup"><span data-stu-id="aa353-400">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="aa353-401">如需詳細資訊，請參閱 [Microsoft Defender update For Windows 作業系統安裝映射](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)。</span><span class="sxs-lookup"><span data-stu-id="aa353-401">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="aa353-402">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="aa353-402">1.1.2104.01</span></span></summary>

<span data-ttu-id="aa353-403">&ensp;套件版本： **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="aa353-403">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="aa353-404">&ensp;平臺版本： **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="aa353-404">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="aa353-405">&ensp;引擎版本： **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="aa353-405">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="aa353-406">&ensp;簽章版本： **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-406">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa353-407">修復</span><span class="sxs-lookup"><span data-stu-id="aa353-407">Fixes</span></span>
- <span data-ttu-id="aa353-408">無</span><span class="sxs-lookup"><span data-stu-id="aa353-408">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa353-409">其他資訊</span><span class="sxs-lookup"><span data-stu-id="aa353-409">Additional information</span></span>
- <span data-ttu-id="aa353-410">無</span><span class="sxs-lookup"><span data-stu-id="aa353-410">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa353-411">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="aa353-411">1.1.2103.01</span></span></summary>

<span data-ttu-id="aa353-412">&ensp;套件版本： **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="aa353-412">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="aa353-413">&ensp;平臺版本： **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="aa353-413">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="aa353-414">&ensp;引擎版本： **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="aa353-414">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="aa353-415">&ensp;簽章版本： **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-415">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa353-416">修復</span><span class="sxs-lookup"><span data-stu-id="aa353-416">Fixes</span></span>
- <span data-ttu-id="aa353-417">無</span><span class="sxs-lookup"><span data-stu-id="aa353-417">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa353-418">其他資訊</span><span class="sxs-lookup"><span data-stu-id="aa353-418">Additional information</span></span>
- <span data-ttu-id="aa353-419">無</span><span class="sxs-lookup"><span data-stu-id="aa353-419">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa353-420">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="aa353-420">1.1.2102.03</span></span></summary>

<span data-ttu-id="aa353-421">&ensp;套件版本： **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="aa353-421">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="aa353-422">&ensp;平臺版本： **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="aa353-422">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="aa353-423">&ensp;引擎版本： **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="aa353-423">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="aa353-424">&ensp;簽章版本： **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-424">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa353-425">修復</span><span class="sxs-lookup"><span data-stu-id="aa353-425">Fixes</span></span>
- <span data-ttu-id="aa353-426">無</span><span class="sxs-lookup"><span data-stu-id="aa353-426">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa353-427">其他資訊</span><span class="sxs-lookup"><span data-stu-id="aa353-427">Additional information</span></span>
- <span data-ttu-id="aa353-428">無</span><span class="sxs-lookup"><span data-stu-id="aa353-428">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa353-429">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="aa353-429">1.1.2101.02</span></span></summary>

<span data-ttu-id="aa353-430">&ensp;套件版本： **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="aa353-430">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="aa353-431">&ensp;平臺版本： **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="aa353-431">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="aa353-432">&ensp;引擎版本： **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="aa353-432">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="aa353-433">&ensp;簽章版本： **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-433">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa353-434">修復</span><span class="sxs-lookup"><span data-stu-id="aa353-434">Fixes</span></span>
- <span data-ttu-id="aa353-435">無</span><span class="sxs-lookup"><span data-stu-id="aa353-435">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa353-436">其他資訊</span><span class="sxs-lookup"><span data-stu-id="aa353-436">Additional information</span></span>
- <span data-ttu-id="aa353-437">無</span><span class="sxs-lookup"><span data-stu-id="aa353-437">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa353-438">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="aa353-438">1.1.2012.01</span></span></summary>

<span data-ttu-id="aa353-439">&ensp;套件版本： **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="aa353-439">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="aa353-440">&ensp;平臺版本： **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="aa353-440">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="aa353-441">&ensp;引擎版本： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="aa353-441">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="aa353-442">&ensp;簽章版本： **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-442">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa353-443">修復</span><span class="sxs-lookup"><span data-stu-id="aa353-443">Fixes</span></span>
- <span data-ttu-id="aa353-444">無</span><span class="sxs-lookup"><span data-stu-id="aa353-444">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa353-445">其他資訊</span><span class="sxs-lookup"><span data-stu-id="aa353-445">Additional information</span></span>
- <span data-ttu-id="aa353-446">無</span><span class="sxs-lookup"><span data-stu-id="aa353-446">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa353-447">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="aa353-447">1.1.2011.02</span></span></summary>

<span data-ttu-id="aa353-448">&ensp;套件版本： **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="aa353-448">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="aa353-449">&ensp;平臺版本： **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="aa353-449">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="aa353-450">&ensp;引擎版本： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="aa353-450">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="aa353-451">&ensp;簽章版本： **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-451">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa353-452">修復</span><span class="sxs-lookup"><span data-stu-id="aa353-452">Fixes</span></span>
- <span data-ttu-id="aa353-453">無</span><span class="sxs-lookup"><span data-stu-id="aa353-453">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa353-454">其他資訊</span><span class="sxs-lookup"><span data-stu-id="aa353-454">Additional information</span></span>
- <span data-ttu-id="aa353-455">重新整理的 Microsoft Defender 防毒軟體簽名</span><span class="sxs-lookup"><span data-stu-id="aa353-455">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa353-456">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="aa353-456">1.1.2011.01</span></span></summary>

<span data-ttu-id="aa353-457">&ensp;套件版本： **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="aa353-457">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="aa353-458">&ensp;平臺版本： **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="aa353-458">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="aa353-459">&ensp;引擎版本： **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="aa353-459">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="aa353-460">&ensp;簽章版本： **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-460">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa353-461">修復</span><span class="sxs-lookup"><span data-stu-id="aa353-461">Fixes</span></span>
- <span data-ttu-id="aa353-462">無</span><span class="sxs-lookup"><span data-stu-id="aa353-462">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa353-463">其他資訊</span><span class="sxs-lookup"><span data-stu-id="aa353-463">Additional information</span></span>
- <span data-ttu-id="aa353-464">無</span><span class="sxs-lookup"><span data-stu-id="aa353-464">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="aa353-465">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="aa353-465">1.1.2009.10</span></span></summary>

<span data-ttu-id="aa353-466">&ensp;套件版本： **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="aa353-466">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="aa353-467">&ensp;平臺版本： **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="aa353-467">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="aa353-468">&ensp;引擎版本： **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="aa353-468">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="aa353-469">&ensp;簽章版本： **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="aa353-469">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="aa353-470">修復</span><span class="sxs-lookup"><span data-stu-id="aa353-470">Fixes</span></span>
- <span data-ttu-id="aa353-471">無</span><span class="sxs-lookup"><span data-stu-id="aa353-471">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="aa353-472">其他資訊</span><span class="sxs-lookup"><span data-stu-id="aa353-472">Additional information</span></span>
- <span data-ttu-id="aa353-473">新增對 Windows 10 RS1 或更新版本作業系統安裝影像的支援。</span><span class="sxs-lookup"><span data-stu-id="aa353-473">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="aa353-474">其他資源</span><span class="sxs-lookup"><span data-stu-id="aa353-474">Additional resources</span></span>

| <span data-ttu-id="aa353-475">文章</span><span class="sxs-lookup"><span data-stu-id="aa353-475">Article</span></span> | <span data-ttu-id="aa353-476">描述</span><span class="sxs-lookup"><span data-stu-id="aa353-476">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="aa353-477">Microsoft Defender update for Windows 作業系統安裝映射</span><span class="sxs-lookup"><span data-stu-id="aa353-477">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="aa353-478">查看您 OS 安裝映射的反惡意軟體更新軟體包 (WIM 和 VHD 檔案) 。</span><span class="sxs-lookup"><span data-stu-id="aa353-478">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="aa353-479">取得 Windows 10 (企業版、專業版和家用版的 Microsoft Defender 防病毒更新) 、Windows Server 2019 及 Windows Server 2016 安裝影像。</span><span class="sxs-lookup"><span data-stu-id="aa353-479">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="aa353-480">管理如何下載及套用保護更新</span><span class="sxs-lookup"><span data-stu-id="aa353-480">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="aa353-481">保護更新可透過許多來源傳遞。</span><span class="sxs-lookup"><span data-stu-id="aa353-481">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="aa353-482">管理應下載及套用防護更新的時間</span><span class="sxs-lookup"><span data-stu-id="aa353-482">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="aa353-483">您可以排程應下載保護更新的時間。</span><span class="sxs-lookup"><span data-stu-id="aa353-483">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="aa353-484">管理已過期端點的更新</span><span class="sxs-lookup"><span data-stu-id="aa353-484">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="aa353-485">如果端點未接更新或排程的掃描，您可以在下次使用者登入時強制更新或掃描。</span><span class="sxs-lookup"><span data-stu-id="aa353-485">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="aa353-486">管理以事件為基礎的強制更新</span><span class="sxs-lookup"><span data-stu-id="aa353-486">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="aa353-487">您可以設定保護更新，以在啟動時或在某些雲端提供的保護事件之後下載。</span><span class="sxs-lookup"><span data-stu-id="aa353-487">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="aa353-488">管理移動裝置和虛擬機器 (Vm 的更新) </span><span class="sxs-lookup"><span data-stu-id="aa353-488">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="aa353-489">您可以指定設定，例如是否應該在電池電源上進行更新，對行動裝置和虛擬機器尤其有用。</span><span class="sxs-lookup"><span data-stu-id="aa353-489">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |