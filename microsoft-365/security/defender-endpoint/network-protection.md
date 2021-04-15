---
title: 使用網路保護來協助防止連線不良網站
description: 防止使用者存取已知的惡意和可疑網路位址，以保護您的網路
keywords: 網路保護、手段、惡意網站、ip、網域、網域
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 95c87330eec3cb557e5fea96148d626b7e0ee4b3
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768911"
---
# <a name="protect-your-network"></a><span data-ttu-id="f1236-104">保護您的網路</span><span class="sxs-lookup"><span data-stu-id="f1236-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f1236-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="f1236-105">**Applies to:**</span></span>
- [<span data-ttu-id="f1236-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f1236-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f1236-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1236-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f1236-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="f1236-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f1236-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="f1236-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f1236-110">網路保護可協助從網際網路型事件降低裝置的受攻擊面。</span><span class="sxs-lookup"><span data-stu-id="f1236-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="f1236-111">它可防止員工使用任何應用程式來存取可能在網際網路上主控網路釣魚詐騙、利用方式及其他惡意內容的危險網域。</span><span class="sxs-lookup"><span data-stu-id="f1236-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="f1236-112">網路保護可擴充 [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 的範圍，以封鎖嘗試連線至低信譽來源的所有輸出 HTTP (s) 流量， (根據網域或主機名稱) 。</span><span class="sxs-lookup"><span data-stu-id="f1236-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="f1236-113">Windows 10 版本1709開始支援網路保護。</span><span class="sxs-lookup"><span data-stu-id="f1236-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> <span data-ttu-id="f1236-114">在其他作業系統上尚不支援網路保護，但使用以 Chromium 為基礎的新 Microsoft Edge 支援 web 保護。</span><span class="sxs-lookup"><span data-stu-id="f1236-114">Network protection is not yet supported on other operating systems, but web protection is supported using the new Microsoft Edge based on Chromium.</span></span> <span data-ttu-id="f1236-115">若要深入瞭解，請參閱 [Web 保護](web-protection-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f1236-115">To learn more, see [Web protection](web-protection-overview.md).</span></span>

<span data-ttu-id="f1236-116">網路保護將 [Web 保護](web-protection-overview.md) 的保護擴充至作業系統層級。</span><span class="sxs-lookup"><span data-stu-id="f1236-116">Network protection extends the protection in [Web protection](web-protection-overview.md) to the operating system level.</span></span> <span data-ttu-id="f1236-117">它提供與其他支援的瀏覽器和非瀏覽器應用程式 Edge 的 web 保護功能。</span><span class="sxs-lookup"><span data-stu-id="f1236-117">It provides web protection functionality in Edge to other supported browsers and non-browser applications.</span></span> <span data-ttu-id="f1236-118">此外，網路保護也會在與 [端點偵測和回應](overview-endpoint-detection-response.md)搭配使用時，提供與封鎖 (IOCs) 遭到損害的可見度和封鎖。</span><span class="sxs-lookup"><span data-stu-id="f1236-118">In addition, network protection provides visibility and blocking of indicators of compromise (IOCs) when used with [Endpoint detection and response](overview-endpoint-detection-response.md).</span></span> <span data-ttu-id="f1236-119">例如，網路保護可與您的 [自訂指示器](manage-indicators.md)搭配運作。</span><span class="sxs-lookup"><span data-stu-id="f1236-119">For example, network protection works with your [custom indicators](manage-indicators.md).</span></span>

<span data-ttu-id="f1236-120">如需如何啟用網路保護的詳細資訊，請參閱 [enable network protection](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="f1236-120">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="f1236-121">使用群組原則、PowerShell 或 MDM Csp 來啟用和管理網路中的網路保護。</span><span class="sxs-lookup"><span data-stu-id="f1236-121">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="f1236-122">請參閱 Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) ，以查看網路保護的運作方式。</span><span class="sxs-lookup"><span data-stu-id="f1236-122">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="f1236-123">網路保護適用于 [Microsoft Defender For Endpoint](microsoft-defender-endpoint.md)，可讓您在 [警示調查案例](investigate-alerts.md)中深入報告以利用保護事件和區塊。</span><span class="sxs-lookup"><span data-stu-id="f1236-123">Network protection works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="f1236-124">當網路保護封鎖連線時，會從動作中心顯示通知。</span><span class="sxs-lookup"><span data-stu-id="f1236-124">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="f1236-125">您的安全性運作小組可以自訂您組織的詳細資料和連絡人資訊 [的通知](customize-attack-surface-reduction.md#customize-the-notification) 。</span><span class="sxs-lookup"><span data-stu-id="f1236-125">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="f1236-126">此外，您可以啟用和自訂個別攻擊面減少規則，以符合特定的監控技巧。</span><span class="sxs-lookup"><span data-stu-id="f1236-126">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="f1236-127">您也可以使用 [審計模式](audit-windows-defender.md) ，評估當組織啟用時，網路保護會如何影響您的組織。</span><span class="sxs-lookup"><span data-stu-id="f1236-127">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="f1236-128">需求</span><span class="sxs-lookup"><span data-stu-id="f1236-128">Requirements</span></span>

<span data-ttu-id="f1236-129">網路保護需要 Windows 10 專業版或企業版，以及 Microsoft Defender 防病毒即時保護。</span><span class="sxs-lookup"><span data-stu-id="f1236-129">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="f1236-130">Windows 版本</span><span class="sxs-lookup"><span data-stu-id="f1236-130">Windows version</span></span> | <span data-ttu-id="f1236-131">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="f1236-131">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="f1236-132">Windows 10 版本1709或更新版本</span><span class="sxs-lookup"><span data-stu-id="f1236-132">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="f1236-133">Windows Server 1803 或更新版本</span><span class="sxs-lookup"><span data-stu-id="f1236-133">Windows Server 1803 or later</span></span> | <span data-ttu-id="f1236-134">必須啟用[Microsoft Defender 防病毒即時保護](configure-real-time-protection-microsoft-defender-antivirus.md)和[雲端傳送保護](enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f1236-134">[Microsoft Defender Antivirus real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="f1236-135">在您啟用服務之後，您可能需要設定網路或防火牆，以允許服務和裝置之間的連線 (也稱為端點) 。</span><span class="sxs-lookup"><span data-stu-id="f1236-135">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="f1236-136">在 Microsoft Defender for Endpoint Security Center 中查看網路保護事件</span><span class="sxs-lookup"><span data-stu-id="f1236-136">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="f1236-137">Microsoft Defender for Endpoint 提供事件和區塊的詳細報告，成為其 [警示調查案例](investigate-alerts.md)的一部分。</span><span class="sxs-lookup"><span data-stu-id="f1236-137">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="f1236-138">您可以使用 [ [高級搜尋](advanced-hunting-overview.md)] 查詢 Microsoft Defender 的端點資料。</span><span class="sxs-lookup"><span data-stu-id="f1236-138">You can query Microsoft Defender for Endpoint data by using [advanced hunting](advanced-hunting-overview.md).</span></span> <span data-ttu-id="f1236-139">如果您使用的是「 [稽核模式](audit-windows-defender.md)」，您可以使用高級搜尋查看網路保護設定如何影響環境（如果已啟用）。</span><span class="sxs-lookup"><span data-stu-id="f1236-139">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="f1236-140">以下是範例查詢</span><span class="sxs-lookup"><span data-stu-id="f1236-140">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="f1236-141">在 Windows 事件檢視器中查看網路保護事件</span><span class="sxs-lookup"><span data-stu-id="f1236-141">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="f1236-142">您可以查看 Windows 事件記錄檔，以查看網路保護封鎖 (或審核) 對惡意 IP 或網域的存取權時所建立的事件：</span><span class="sxs-lookup"><span data-stu-id="f1236-142">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="f1236-143">[直接複製 XML](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="f1236-143">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="f1236-144">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f1236-144">Select **OK**.</span></span>

<span data-ttu-id="f1236-145">此程式會建立自訂視圖，篩選為只顯示下列與網路保護相關的事件：</span><span class="sxs-lookup"><span data-stu-id="f1236-145">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="f1236-146">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="f1236-146">Event ID</span></span> | <span data-ttu-id="f1236-147">描述</span><span class="sxs-lookup"><span data-stu-id="f1236-147">Description</span></span> |
|:---|:---|
| <span data-ttu-id="f1236-148">5007</span><span class="sxs-lookup"><span data-stu-id="f1236-148">5007</span></span> | <span data-ttu-id="f1236-149">設定變更時的事件</span><span class="sxs-lookup"><span data-stu-id="f1236-149">Event when settings are changed</span></span> |
| <span data-ttu-id="f1236-150">1125</span><span class="sxs-lookup"><span data-stu-id="f1236-150">1125</span></span> | <span data-ttu-id="f1236-151">在稽核模式中觸發網路保護時的事件</span><span class="sxs-lookup"><span data-stu-id="f1236-151">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="f1236-152">1126</span><span class="sxs-lookup"><span data-stu-id="f1236-152">1126</span></span> | <span data-ttu-id="f1236-153">在封鎖模式中觸發網路保護時的事件</span><span class="sxs-lookup"><span data-stu-id="f1236-153">Event when network protection fires in block mode</span></span> |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a><span data-ttu-id="f1236-154">Windows 10 企業版多重會話 Windows 虛擬桌面的考慮</span><span class="sxs-lookup"><span data-stu-id="f1236-154">Considerations for Windows virtual desktop running Windows 10 Enterprise Multi-Session</span></span>

<span data-ttu-id="f1236-155">由於 Windows 10 企業版的多使用者性質，請牢記下列幾點：</span><span class="sxs-lookup"><span data-stu-id="f1236-155">Due to the multi-user nature of Windows 10 Enterprise, keep the following points in mind:</span></span>

1. <span data-ttu-id="f1236-156">網路保護是全裝置的功能，無法以特定的使用者會話為目標。</span><span class="sxs-lookup"><span data-stu-id="f1236-156">Network protection is a device-wide feature and cannot be targeted to specific user sessions.</span></span>

2. <span data-ttu-id="f1236-157">Web 內容篩選原則也是裝置範圍。</span><span class="sxs-lookup"><span data-stu-id="f1236-157">Web content filtering policies are also device wide.</span></span>

3. <span data-ttu-id="f1236-158">如果您需要區分使用者群組，請考慮建立個別的 Windows 虛擬桌面主機集區和指派。</span><span class="sxs-lookup"><span data-stu-id="f1236-158">If you need to differentiate between user groups, consider creating separate Windows Virtual Desktop host pools and assignments.</span></span>

4. <span data-ttu-id="f1236-159">在執行之前，先在審計模式中測試網路保護，以評估其行為。</span><span class="sxs-lookup"><span data-stu-id="f1236-159">Test network protection in audit mode to assess its behavior before rolling out.</span></span> 

5. <span data-ttu-id="f1236-160">如果您有大量的使用者或大量的多使用者會話，請考慮調整部署的大小。</span><span class="sxs-lookup"><span data-stu-id="f1236-160">Consider resizing your deployment if you have a large number of users or a large number of multi-user sessions.</span></span>

### <a name="alternative-option-for-network-protection"></a><span data-ttu-id="f1236-161">網路保護的替代選項</span><span class="sxs-lookup"><span data-stu-id="f1236-161">Alternative option for network protection</span></span>

<span data-ttu-id="f1236-162">針對 Windows 10 企業版的多會話1909和 up，可在 Azure 上的 Windows 虛擬桌面中使用下列方法來啟用網路 Edge 的網路保護：</span><span class="sxs-lookup"><span data-stu-id="f1236-162">For Windows 10 Enterprise Multi-Session 1909 and up, used in Windows Virtual Desktop on Azure, network protection for Microsoft Edge can be enabled using the following method:</span></span>

1. <span data-ttu-id="f1236-163">使用 [ [開啟網路保護](enable-network-protection.md) ]，然後依照指示套用原則。</span><span class="sxs-lookup"><span data-stu-id="f1236-163">Use [Turn on network protection](enable-network-protection.md) and follow the instructions to apply your policy.</span></span>

2. <span data-ttu-id="f1236-164">執行下列 PowerShell 命令： `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span><span class="sxs-lookup"><span data-stu-id="f1236-164">Execute the following PowerShell command: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span></span>

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="f1236-165">網路保護疑難排解</span><span class="sxs-lookup"><span data-stu-id="f1236-165">Network protection troubleshooting</span></span>

<span data-ttu-id="f1236-166">由於網路保護的執行環境，Microsoft 可能無法偵測到作業系統 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="f1236-166">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="f1236-167">在某些情況下，網路保護用戶端無法到達雲端服務。</span><span class="sxs-lookup"><span data-stu-id="f1236-167">In some cases, network protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="f1236-168">若要解決連線問題，具有 E5 授權的客戶應設定下列其中一個 Defender 登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="f1236-168">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="f1236-169">相關文章</span><span class="sxs-lookup"><span data-stu-id="f1236-169">Related articles</span></span>

- <span data-ttu-id="f1236-170">[評估網路保護](evaluate-network-protection.md) |採取一種快速案例，示範該功能的運作方式，以及通常會建立什麼事件。</span><span class="sxs-lookup"><span data-stu-id="f1236-170">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="f1236-171">[啟用網路保護](enable-network-protection.md) |使用群組原則、PowerShell 或 MDM Csp 來啟用和管理網路中的網路保護。</span><span class="sxs-lookup"><span data-stu-id="f1236-171">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
