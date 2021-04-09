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
ms.date: 03/08/2021
ms.topic: how-to
ms.openlocfilehash: 2ef3fbeec65be512dfe07f1d533df4d8e9b31532
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644497"
---
# <a name="protect-your-network"></a><span data-ttu-id="d6662-104">保護您的網路</span><span class="sxs-lookup"><span data-stu-id="d6662-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d6662-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="d6662-105">**Applies to:**</span></span>
- [<span data-ttu-id="d6662-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="d6662-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d6662-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d6662-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d6662-108">想要體驗 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="d6662-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="d6662-109">註冊免費試用版。</span><span class="sxs-lookup"><span data-stu-id="d6662-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="d6662-110">網路保護可協助從網際網路型事件降低裝置的受攻擊面。</span><span class="sxs-lookup"><span data-stu-id="d6662-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="d6662-111">它可防止員工使用任何應用程式來存取可能在網際網路上主控網路釣魚詐騙、利用方式及其他惡意內容的危險網域。</span><span class="sxs-lookup"><span data-stu-id="d6662-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="d6662-112">網路保護可擴充 [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 的範圍，以封鎖嘗試連線至低信譽來源的所有輸出 HTTP (s) 流量， (根據網域或主機名稱) 。</span><span class="sxs-lookup"><span data-stu-id="d6662-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="d6662-113">Windows 10 版本1709開始支援網路保護。</span><span class="sxs-lookup"><span data-stu-id="d6662-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> 

<span data-ttu-id="d6662-114">如需如何啟用網路保護的詳細資訊，請參閱 [enable network protection](enable-network-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="d6662-114">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="d6662-115">使用群組原則、PowerShell 或 MDM Csp 來啟用和管理網路中的網路保護。</span><span class="sxs-lookup"><span data-stu-id="d6662-115">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="d6662-116">請參閱 Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) ，以查看網路保護的運作方式。</span><span class="sxs-lookup"><span data-stu-id="d6662-116">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="d6662-117">網路保護適用于 [Microsoft Defender For Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)，可讓您在 [警示調查案例](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)中深入報告以利用保護事件和區塊。</span><span class="sxs-lookup"><span data-stu-id="d6662-117">Network protection works best with [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="d6662-118">當網路保護封鎖連線時，會從動作中心顯示通知。</span><span class="sxs-lookup"><span data-stu-id="d6662-118">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="d6662-119">您的安全性運作小組可以自訂您組織的詳細資料和連絡人資訊 [的通知](customize-attack-surface-reduction.md#customize-the-notification) 。</span><span class="sxs-lookup"><span data-stu-id="d6662-119">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="d6662-120">此外，您可以啟用和自訂個別攻擊面減少規則，以符合特定的監控技巧。</span><span class="sxs-lookup"><span data-stu-id="d6662-120">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="d6662-121">您也可以使用 [審計模式](audit-windows-defender.md) ，評估當組織啟用時，網路保護會如何影響您的組織。</span><span class="sxs-lookup"><span data-stu-id="d6662-121">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="d6662-122">需求</span><span class="sxs-lookup"><span data-stu-id="d6662-122">Requirements</span></span>

<span data-ttu-id="d6662-123">網路保護需要 Windows 10 專業版或企業版，以及 Microsoft Defender 防病毒即時保護。</span><span class="sxs-lookup"><span data-stu-id="d6662-123">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="d6662-124">Windows 版本</span><span class="sxs-lookup"><span data-stu-id="d6662-124">Windows version</span></span> | <span data-ttu-id="d6662-125">Microsoft Defender 防病毒</span><span class="sxs-lookup"><span data-stu-id="d6662-125">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="d6662-126">Windows 10 版本1709或更新版本</span><span class="sxs-lookup"><span data-stu-id="d6662-126">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="d6662-127">Windows Server 1803 或更新版本</span><span class="sxs-lookup"><span data-stu-id="d6662-127">Windows Server 1803 or later</span></span> | <span data-ttu-id="d6662-128">必須啟用[Microsoft Defender 防病毒即時保護](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md)和[雲端傳送保護](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d6662-128">[Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="d6662-129">在您啟用服務之後，您可能需要設定網路或防火牆，以允許服務和裝置之間的連線 (也稱為端點) 。</span><span class="sxs-lookup"><span data-stu-id="d6662-129">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- <span data-ttu-id="d6662-130">。 smartscreen.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d6662-130">.smartscreen.microsoft.com</span></span>
- <span data-ttu-id="d6662-131">。 smartscreen-prod.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d6662-131">.smartscreen-prod.microsoft.com</span></span>

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="d6662-132">在 Microsoft Defender for Endpoint Security Center 中查看網路保護事件</span><span class="sxs-lookup"><span data-stu-id="d6662-132">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="d6662-133">Microsoft Defender for Endpoint 提供事件和區塊的詳細報告，成為其 [警示調查案例](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)的一部分。</span><span class="sxs-lookup"><span data-stu-id="d6662-133">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="d6662-134">您可以使用 [ [高級搜尋](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection)] 查詢 Microsoft Defender 的端點資料。</span><span class="sxs-lookup"><span data-stu-id="d6662-134">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="d6662-135">如果您使用的是「 [稽核模式](audit-windows-defender.md)」，您可以使用高級搜尋查看網路保護設定如何影響環境（如果已啟用）。</span><span class="sxs-lookup"><span data-stu-id="d6662-135">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="d6662-136">以下是範例查詢</span><span class="sxs-lookup"><span data-stu-id="d6662-136">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="d6662-137">在 Windows 事件檢視器中查看網路保護事件</span><span class="sxs-lookup"><span data-stu-id="d6662-137">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="d6662-138">您可以查看 Windows 事件記錄檔，以查看網路保護封鎖 (或審核) 對惡意 IP 或網域的存取權時所建立的事件：</span><span class="sxs-lookup"><span data-stu-id="d6662-138">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="d6662-139">[直接複製 XML](event-views.md)。</span><span class="sxs-lookup"><span data-stu-id="d6662-139">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="d6662-140">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d6662-140">Select **OK**.</span></span>

<span data-ttu-id="d6662-141">此程式會建立自訂視圖，篩選為只顯示下列與網路保護相關的事件：</span><span class="sxs-lookup"><span data-stu-id="d6662-141">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="d6662-142">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="d6662-142">Event ID</span></span> | <span data-ttu-id="d6662-143">描述</span><span class="sxs-lookup"><span data-stu-id="d6662-143">Description</span></span> |
|:---|:---|
| <span data-ttu-id="d6662-144">5007</span><span class="sxs-lookup"><span data-stu-id="d6662-144">5007</span></span> | <span data-ttu-id="d6662-145">設定變更時的事件</span><span class="sxs-lookup"><span data-stu-id="d6662-145">Event when settings are changed</span></span> |
| <span data-ttu-id="d6662-146">1125</span><span class="sxs-lookup"><span data-stu-id="d6662-146">1125</span></span> | <span data-ttu-id="d6662-147">在稽核模式中觸發網路保護時的事件</span><span class="sxs-lookup"><span data-stu-id="d6662-147">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="d6662-148">1126</span><span class="sxs-lookup"><span data-stu-id="d6662-148">1126</span></span> | <span data-ttu-id="d6662-149">在封鎖模式中觸發網路保護時的事件</span><span class="sxs-lookup"><span data-stu-id="d6662-149">Event when network protection fires in block mode</span></span> |

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="d6662-150">網路保護疑難排解</span><span class="sxs-lookup"><span data-stu-id="d6662-150">Network protection troubleshooting</span></span>

<span data-ttu-id="d6662-151">由於網路保護的執行環境，Microsoft 可能無法偵測到作業系統 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="d6662-151">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="d6662-152">在某些情況下，網路保護用戶端無法到達雲端服務。</span><span class="sxs-lookup"><span data-stu-id="d6662-152">In some cases, Network Protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="d6662-153">若要解決連線問題，具有 E5 授權的客戶應設定下列其中一個 Defender 登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="d6662-153">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="d6662-154">相關文章</span><span class="sxs-lookup"><span data-stu-id="d6662-154">Related articles</span></span>

- <span data-ttu-id="d6662-155">[評估網路保護](evaluate-network-protection.md) |採取一種快速案例，示範該功能的運作方式，以及通常會建立什麼事件。</span><span class="sxs-lookup"><span data-stu-id="d6662-155">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="d6662-156">[啟用網路保護](enable-network-protection.md) |使用群組原則、PowerShell 或 MDM Csp 來啟用和管理網路中的網路保護。</span><span class="sxs-lookup"><span data-stu-id="d6662-156">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
