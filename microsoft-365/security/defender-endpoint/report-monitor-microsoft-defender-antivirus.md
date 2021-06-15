---
title: 監視及報告 Microsoft Defender 防毒軟體保護
description: 使用 Configuration Manager 或 security information and event management (SIEM) 工具使用報表，並以 PowerShell 和 WMI 監視 Microsoft Defender AV。
keywords: siem、監控、報告、Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 91891af35def83f21b3db8c7e8fa4b320bef563c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926160"
---
# <a name="report-on-microsoft-defender-antivirus"></a><span data-ttu-id="2c46f-104">在 Microsoft Defender 防毒軟體上報告</span><span class="sxs-lookup"><span data-stu-id="2c46f-104">Report on Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2c46f-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="2c46f-105">**Applies to:**</span></span>

- [<span data-ttu-id="2c46f-106">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2c46f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2c46f-107">Microsoft Defender 防毒軟體會內置於 Windows 10、Windows Server 2019 及 Windows Server 2016。</span><span class="sxs-lookup"><span data-stu-id="2c46f-107">Microsoft Defender Antivirus is built into Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="2c46f-108">Microsoft Defender 防毒軟體是 Microsoft Defender for Endpoint 中的下一代保護。</span><span class="sxs-lookup"><span data-stu-id="2c46f-108">Microsoft Defender Antivirus is of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="2c46f-109">下一代保護可協助保護您的裝置免受電子郵件、應用程式、雲端和網路等軟體威脅（如病毒、惡意程式碼和間諜軟體）的威脅。</span><span class="sxs-lookup"><span data-stu-id="2c46f-109">Next-generation protection helps protect your devices from software threats like viruses, malware, and spyware across email, apps, the cloud, and the web.</span></span>

<span data-ttu-id="2c46f-110">透過 Microsoft Defender 防毒軟體，您有數個選項可以查看保護狀態及警示。</span><span class="sxs-lookup"><span data-stu-id="2c46f-110">With Microsoft Defender Antivirus, you have several options for reviewing protection status and alerts.</span></span> <span data-ttu-id="2c46f-111">您可以使用 Microsoft 端點管理員來[監控 Microsoft Defender 防毒軟體](/configmgr/protect/deploy-use/monitor-endpoint-protection)或[建立電子郵件警示](/configmgr/protect/deploy-use/endpoint-configure-alerts)。</span><span class="sxs-lookup"><span data-stu-id="2c46f-111">You can use Microsoft Endpoint Manager to [monitor Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) or [create email alerts](/configmgr/protect/deploy-use/endpoint-configure-alerts).</span></span> <span data-ttu-id="2c46f-112">或者，您可以使用[Microsoft Intune](/intune/introduction-intune)監視保護。</span><span class="sxs-lookup"><span data-stu-id="2c46f-112">Or, you can monitor protection using [Microsoft Intune](/intune/introduction-intune).</span></span>  

<span data-ttu-id="2c46f-113">Microsoft Operations Management Suite 具有[更新規範增益集](/windows/deployment/update/update-compliance-get-started)，可報告重要的 Microsoft Defender 防毒軟體問題，包括保護更新和即時保護設定。</span><span class="sxs-lookup"><span data-stu-id="2c46f-113">Microsoft Operations Management Suite has an [Update Compliance add-in](/windows/deployment/update/update-compliance-get-started) that reports on key Microsoft Defender Antivirus issues, including protection updates and real-time protection settings.</span></span>

<span data-ttu-id="2c46f-114">如果您有協力廠商的安全性資訊和事件管理 (SIEM) server，您也可以使用[Windows Defender 用戶端事件](/windows/win32/events/windows-events)。</span><span class="sxs-lookup"><span data-stu-id="2c46f-114">If you have a third-party security information and event management (SIEM) server, you can also consume [Windows Defender client events](/windows/win32/events/windows-events).</span></span> 

<span data-ttu-id="2c46f-115">Windows 事件會包含數個安全性事件來源，包括安全性帳戶管理員 (SAM) 事件 ([增強的 Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511)，另請參閱[安全性審核](/windows/device-security/auditing/security-auditing-overview)主題) 和[Windows Defender 事件](troubleshoot-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="2c46f-115">Windows events comprise several security event sources, including Security Account Manager (SAM) events ([enhanced for Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), also see the [Security auditing](/windows/device-security/auditing/security-auditing-overview) topic) and  [Windows Defender events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="2c46f-116">您可以使用[Windows 事件收集器](/windows/win32/wec/windows-event-collector)來集中匯總這些事件。</span><span class="sxs-lookup"><span data-stu-id="2c46f-116">These events can be centrally aggregated using the [Windows event collector](/windows/win32/wec/windows-event-collector).</span></span> <span data-ttu-id="2c46f-117">SIEM 伺服器通常會有 Windows 事件的連接器，可讓您在 SIEM server 中關聯所有的安全性事件。</span><span class="sxs-lookup"><span data-stu-id="2c46f-117">Often, SIEM servers have connectors for Windows events, allowing you to correlate all security events in your SIEM server.</span></span> 

<span data-ttu-id="2c46f-118">您也可以 [使用記錄分析中的惡意程式碼評估解決方案，監控惡意程式碼事件](/azure/log-analytics/log-analytics-malware)。</span><span class="sxs-lookup"><span data-stu-id="2c46f-118">You can also [monitor malware events using the Malware Assessment solution in Log Analytics](/azure/log-analytics/log-analytics-malware).</span></span>

<span data-ttu-id="2c46f-119">若要使用 PowerShell、WMI 或 Microsoft Azure 來監視或決定狀態，請參閱[ (部署、管理及報告選項表格) ](deploy-manage-report-microsoft-defender-antivirus.md#ref2)。</span><span class="sxs-lookup"><span data-stu-id="2c46f-119">For monitoring or determining status with PowerShell, WMI, or Microsoft Azure, see the [(Deployment, management, and reporting options table)](deploy-manage-report-microsoft-defender-antivirus.md#ref2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="2c46f-120">相關文章</span><span class="sxs-lookup"><span data-stu-id="2c46f-120">Related articles</span></span>

- [<span data-ttu-id="2c46f-121">Windows 10 中的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="2c46f-121">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="2c46f-122">Windows Server 2016 和 2019 上的 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="2c46f-122">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="2c46f-123">部署 Microsoft Defender 防毒軟體</span><span class="sxs-lookup"><span data-stu-id="2c46f-123">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)