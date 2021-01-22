---
title: 部署 Microsoft 365 Defender 支援的服務
description: 瞭解 Microsoft 365 Defender 可整合的 Microsoft 安全性服務、其授權需求及部署程式
keywords: 部署、授權、支援服務、提供、組組 Microsoft Threat Protection、M365、授權資格、Microsoft Defender ATP、MDATP、Office 365 ATP、Azure ATP、Microsoft Cloud App Security、MCAS、Advanced Threat Protection、E5、A5、EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5af58a1c6850619ca08960997a30fe4a81158446
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928959"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="08633-104">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="08633-104">Deploy supported services</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="08633-105">適用於：</span><span class="sxs-lookup"><span data-stu-id="08633-105">**Applies to:**</span></span>
- <span data-ttu-id="08633-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08633-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="08633-107">[Microsoft 365 Defender](microsoft-threat-protection.md) 整合了各種 Microsoft 安全性服務，針對複雜的攻擊提供集中式偵測、防護與調查功能。</span><span class="sxs-lookup"><span data-stu-id="08633-107">[Microsoft 365 Defender](microsoft-threat-protection.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="08633-108">本文說明支援服務、其授權需求、部署一或多個服務的相關優點和限制，以及可如何個別完全部署服務的連結。</span><span class="sxs-lookup"><span data-stu-id="08633-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="08633-109">支援服務</span><span class="sxs-lookup"><span data-stu-id="08633-109">Supported services</span></span>
<span data-ttu-id="08633-110">Microsoft 365 E5、E5 安全性、A5 或 A5 安全性授權或有效的授權組合可提供下列支援服務的存取權，並可讓您在 Microsoft 365 安全性中心使用 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="08633-110">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to the following supported services and entitles you to use Microsoft 365 Defender in Microsoft 365 security center.</span></span> [<span data-ttu-id="08633-111">請參閱授權需求</span><span class="sxs-lookup"><span data-stu-id="08633-111">See licensing requirements</span></span>](prerequisites.md#licensing-requirements)

| <span data-ttu-id="08633-112">支援的服務</span><span class="sxs-lookup"><span data-stu-id="08633-112">Supported service</span></span> | <span data-ttu-id="08633-113">說明</span><span class="sxs-lookup"><span data-stu-id="08633-113">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="08633-114">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="08633-114">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="08633-115">以強大的感應器、雲端分析和威脅情報為內建的端點防護套件</span><span class="sxs-lookup"><span data-stu-id="08633-115">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
|<span data-ttu-id="08633-116">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="08633-116">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="08633-117">在 Office 365 中針對您的應用程式和資料進一的保護，包括電子郵件和其他共同處理工具</span><span class="sxs-lookup"><span data-stu-id="08633-117">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="08633-118">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="08633-118">Microsoft Defender for Identity</span></span> | <span data-ttu-id="08633-119">使用相關 Active Directory 訊號來防範進位威脅、身分被入侵和惡意的 Insider</span><span class="sxs-lookup"><span data-stu-id="08633-119">Defend against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="08633-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="08633-120">Microsoft Cloud App Security</span></span> | <span data-ttu-id="08633-121">識別並對抗 Microsoft 和協力廠商雲端服務中的網路威脅</span><span class="sxs-lookup"><span data-stu-id="08633-121">Identify and combat cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="08633-122">部署的服務和功能</span><span class="sxs-lookup"><span data-stu-id="08633-122">Deployed services and functionality</span></span>
<span data-ttu-id="08633-123">當您部署更多支援服務時，Microsoft 365 Defender 提供更佳的可見度、關聯性與補救功能。</span><span class="sxs-lookup"><span data-stu-id="08633-123">Microsoft 365 Defender provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="08633-124">完整部署的好處</span><span class="sxs-lookup"><span data-stu-id="08633-124">Benefits of full deployment</span></span>
<span data-ttu-id="08633-125">若要取得 Microsoft 365 Defender 的完整權益，建議您部署所有支援服務。</span><span class="sxs-lookup"><span data-stu-id="08633-125">To get the complete benefits of Microsoft 365 Defender, we recommend deploying all supported services.</span></span> <span data-ttu-id="08633-126">以下是完整部署的一些主要優點：</span><span class="sxs-lookup"><span data-stu-id="08633-126">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="08633-127">事件會依據所有可用的感應器和服務特定的分析功能所發出的警示和事件訊號來識別並關聯事件</span><span class="sxs-lookup"><span data-stu-id="08633-127">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="08633-128">AIR 和 AIR (的自動化調查與補救) 適用于各種實體類型，包括裝置、信箱和使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="08633-128">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="08633-129">您可以針對來自裝置、信箱和其他實體的事件和實體資料查詢更全方位的進位搜尋架構</span><span class="sxs-lookup"><span data-stu-id="08633-129">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="08633-130">有限的部署案例</span><span class="sxs-lookup"><span data-stu-id="08633-130">Limited deployment scenarios</span></span>
<span data-ttu-id="08633-131">您部署的每個支援服務都提供極豐富的原始訊號以及相關資訊。</span><span class="sxs-lookup"><span data-stu-id="08633-131">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="08633-132">雖然有限的部署不會讓 Microsoft 365 Defender 功能關閉，但可全面監控端點、應用程式、資料和身分身分的能力會受到影響。</span><span class="sxs-lookup"><span data-stu-id="08633-132">While limited deployment doesn’t cause Microsoft 365 Defender functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="08633-133">同時，任何補救功能都僅適用于可受您部署之服務管理的實體。</span><span class="sxs-lookup"><span data-stu-id="08633-133">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="08633-134">下表列出每個支援的服務如何提供額外的資料、與資料相互關聯以取得其他深入見解的機會，以及更好的補救和回應功能。</span><span class="sxs-lookup"><span data-stu-id="08633-134">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="08633-135">服務</span><span class="sxs-lookup"><span data-stu-id="08633-135">Service</span></span> | <span data-ttu-id="08633-136">資料 (表示&相關資訊) </span><span class="sxs-lookup"><span data-stu-id="08633-136">Data (signals & correlated info)</span></span> | <span data-ttu-id="08633-137">補救&範圍</span><span class="sxs-lookup"><span data-stu-id="08633-137">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="08633-138">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="08633-138">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="08633-139">- 端點狀態和原始事件</span><span class="sxs-lookup"><span data-stu-id="08633-139">- Endpoint states and raw events</span></span><br /><span data-ttu-id="08633-140">- 端點偵測和警示，包括防毒軟體、EDR、攻擊面縮小</span><span class="sxs-lookup"><span data-stu-id="08633-140">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="08633-141">- 端點上所觀察之檔案和其他實體的資訊</span><span class="sxs-lookup"><span data-stu-id="08633-141">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="08633-142">端點</span><span class="sxs-lookup"><span data-stu-id="08633-142">Endpoints</span></span> |
|<span data-ttu-id="08633-143">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="08633-143">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="08633-144">- 郵件和信箱狀態及原始事件</span><span class="sxs-lookup"><span data-stu-id="08633-144">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="08633-145">- 電子郵件、附件和連結偵測</span><span class="sxs-lookup"><span data-stu-id="08633-145">- Email, attachment, and link detections</span></span> | <span data-ttu-id="08633-146">- 信箱</span><span class="sxs-lookup"><span data-stu-id="08633-146">- Mailboxes</span></span><br /><span data-ttu-id="08633-147">- Microsoft 365 帳戶</span><span class="sxs-lookup"><span data-stu-id="08633-147">- Microsoft 365 accounts</span></span> |
| <span data-ttu-id="08633-148">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="08633-148">Microsoft Defender for Identity</span></span> | <span data-ttu-id="08633-149">- Active Directory 訊號，包括驗證事件</span><span class="sxs-lookup"><span data-stu-id="08633-149">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="08633-150">- 身分識別相關檢發偵測</span><span class="sxs-lookup"><span data-stu-id="08633-150">- Identity-related behavioral detections</span></span> | <span data-ttu-id="08633-151">身分識別</span><span class="sxs-lookup"><span data-stu-id="08633-151">Identities</span></span> |
| <span data-ttu-id="08633-152">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="08633-152">Microsoft Cloud App Security</span></span> | <span data-ttu-id="08633-153">- 偵測未檢查的雲端應用程式和服務， (IT) </span><span class="sxs-lookup"><span data-stu-id="08633-153">- Detection of unsanctioned cloud apps and services (shadow IT)</span></span><br /><span data-ttu-id="08633-154">- 將資料曝光到雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="08633-154">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="08633-155">- 與雲端應用程式相關的威脅活動</span><span class="sxs-lookup"><span data-stu-id="08633-155">- Threat activity associated with cloud apps</span></span> | <span data-ttu-id="08633-156">雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="08633-156">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="08633-157">部署服務</span><span class="sxs-lookup"><span data-stu-id="08633-157">Deploy the services</span></span>
<span data-ttu-id="08633-158">部署每個服務通常需要向您的租使用者進行部署，並且需要一些初始群組原則。</span><span class="sxs-lookup"><span data-stu-id="08633-158">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="08633-159">請參閱下表以瞭解每個服務的部署方法。</span><span class="sxs-lookup"><span data-stu-id="08633-159">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="08633-160">服務</span><span class="sxs-lookup"><span data-stu-id="08633-160">Service</span></span> | <span data-ttu-id="08633-161">提供指示</span><span class="sxs-lookup"><span data-stu-id="08633-161">Provisioning instructions</span></span> | <span data-ttu-id="08633-162">初始設定</span><span class="sxs-lookup"><span data-stu-id="08633-162">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="08633-163">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="08633-163">Microsoft Defender for Endpoint</span></span> | [<span data-ttu-id="08633-164">Microsoft Defender 端點部署指南</span><span class="sxs-lookup"><span data-stu-id="08633-164">Microsoft Defender for Endpoint deployment guide</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | <span data-ttu-id="08633-165">*請參閱提供指示*</span><span class="sxs-lookup"><span data-stu-id="08633-165">*See provisioning instructions*</span></span> |
|<span data-ttu-id="08633-166">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="08633-166">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="08633-167">*沒有 ，已與 Office 365 一起提供*</span><span class="sxs-lookup"><span data-stu-id="08633-167">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="08633-168">設定適用於 Office 365 的 Microsoft Defender 原則</span><span class="sxs-lookup"><span data-stu-id="08633-168">Configure Microsoft Defender for Office 365 policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| <span data-ttu-id="08633-169">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="08633-169">Microsoft Defender for Identity</span></span> | [<span data-ttu-id="08633-170">快速入門：建立您的 Microsoft Defender 以用於身分識別實例</span><span class="sxs-lookup"><span data-stu-id="08633-170">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="08633-171">*請參閱提供指示*</span><span class="sxs-lookup"><span data-stu-id="08633-171">*See provisioning instructions*</span></span> |
| <span data-ttu-id="08633-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="08633-172">Microsoft Cloud App Security</span></span> | <span data-ttu-id="08633-173">*無*</span><span class="sxs-lookup"><span data-stu-id="08633-173">*None*</span></span> | [<span data-ttu-id="08633-174">快速入門：開始使用 Microsoft Cloud App 安全性</span><span class="sxs-lookup"><span data-stu-id="08633-174">Quickstart: Get started with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="08633-175">部署支援服務後，請[開啟 Microsoft 365 Defender。](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="08633-175">Once you’ve deployed the supported services, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="08633-176">相關主題</span><span class="sxs-lookup"><span data-stu-id="08633-176">Related topics</span></span>

- [<span data-ttu-id="08633-177">Microsoft 365 Defender 概觀</span><span class="sxs-lookup"><span data-stu-id="08633-177">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="08633-178">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08633-178">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
- [<span data-ttu-id="08633-179">Microsoft Defender 端點概觀</span><span class="sxs-lookup"><span data-stu-id="08633-179">Microsoft Defender for Endpoint overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="08633-180">Office 365 的 Microsoft Defender 概觀</span><span class="sxs-lookup"><span data-stu-id="08633-180">Microsoft Defender for Office 365 overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="08633-181">Microsoft Cloud App Security 概觀</span><span class="sxs-lookup"><span data-stu-id="08633-181">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="08633-182">Microsoft Defender 身分識別概觀</span><span class="sxs-lookup"><span data-stu-id="08633-182">Microsoft Defender for Identity overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
