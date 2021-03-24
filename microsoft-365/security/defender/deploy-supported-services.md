---
title: 部署 Microsoft 365 Defender 支援的服務
description: 深入瞭解可由 Microsoft 365 Defender、其授權需求和部署程式整合的 Microsoft 安全服務
keywords: 部署，授權，支援的服務，布建，設定 Microsoft 威脅防護，M365，授權資格，Microsoft Defender ATP，MDATP，Office 365 ATP，Azure ATP，Microsoft Cloud App Security，MCAS，advanced 威脅防護，E5，A5，EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
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
ms.openlocfilehash: d0b7b600e0880bacda3588598387e5b1e8c82958
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054578"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="8f378-104">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="8f378-104">Deploy supported services</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8f378-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="8f378-105">**Applies to:**</span></span>
- <span data-ttu-id="8f378-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f378-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8f378-107">[Microsoft 365 Defender](microsoft-365-defender.md) 整合各種 Microsoft 安全服務，以提供集中式偵測、防護和調查功能，以防禦複雜的攻擊。</span><span class="sxs-lookup"><span data-stu-id="8f378-107">[Microsoft 365 Defender](microsoft-365-defender.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="8f378-108">本文說明支援的服務、其授權需求、與部署一或多項服務相關的優點與限制，以及您可以個別完全部署這些服務的方式連結。</span><span class="sxs-lookup"><span data-stu-id="8f378-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="8f378-109">支援的服務</span><span class="sxs-lookup"><span data-stu-id="8f378-109">Supported services</span></span>
<span data-ttu-id="8f378-110">Microsoft 365 E5，E5 Security，A5，or A5 安全性授權或有效的授權組合，可提供下列支援服務的存取權，以及您在 Microsoft 365 Security center 中使用 Microsoft 365 Defender 的權力。</span><span class="sxs-lookup"><span data-stu-id="8f378-110">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to the following supported services and entitles you to use Microsoft 365 Defender in Microsoft 365 security center.</span></span> [<span data-ttu-id="8f378-111">請參閱授權需求</span><span class="sxs-lookup"><span data-stu-id="8f378-111">See licensing requirements</span></span>](prerequisites.md#licensing-requirements)

| <span data-ttu-id="8f378-112">支援的服務</span><span class="sxs-lookup"><span data-stu-id="8f378-112">Supported service</span></span> | <span data-ttu-id="8f378-113">描述</span><span class="sxs-lookup"><span data-stu-id="8f378-113">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="8f378-114">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8f378-114">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="8f378-115">以強大行為感應器、雲端分析和威脅智慧為基礎的 Endpoint protection 套件</span><span class="sxs-lookup"><span data-stu-id="8f378-115">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
|<span data-ttu-id="8f378-116">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8f378-116">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="8f378-117">Office 365 中的應用程式和資料的高級保護，包括電子郵件和其他共同作業工具</span><span class="sxs-lookup"><span data-stu-id="8f378-117">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="8f378-118">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8f378-118">Microsoft Defender for Identity</span></span> | <span data-ttu-id="8f378-119">使用關聯的 Active Directory 信號，防禦高級威脅、遭到破壞的身分識別，以及惡意內幕用。</span><span class="sxs-lookup"><span data-stu-id="8f378-119">Defend against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="8f378-120">Microsoft 雲端應用程式安全性</span><span class="sxs-lookup"><span data-stu-id="8f378-120">Microsoft Cloud App Security</span></span> | <span data-ttu-id="8f378-121">在您的 Microsoft 和協力廠商雲端服務之間識別及打擊 cyberthreats</span><span class="sxs-lookup"><span data-stu-id="8f378-121">Identify and combat cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="8f378-122">部署的服務和功能</span><span class="sxs-lookup"><span data-stu-id="8f378-122">Deployed services and functionality</span></span>
<span data-ttu-id="8f378-123">當您部署更支援的服務時，Microsoft 365 Defender 可提供更好的可見度、關聯性和修正能力。</span><span class="sxs-lookup"><span data-stu-id="8f378-123">Microsoft 365 Defender provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="8f378-124">完整部署的優點</span><span class="sxs-lookup"><span data-stu-id="8f378-124">Benefits of full deployment</span></span>
<span data-ttu-id="8f378-125">為了取得 Microsoft 365 Defender 的完整優點，我們建議您部署所有支援的服務。</span><span class="sxs-lookup"><span data-stu-id="8f378-125">To get the complete benefits of Microsoft 365 Defender, we recommend deploying all supported services.</span></span> <span data-ttu-id="8f378-126">以下是完整部署的一些重要優點：</span><span class="sxs-lookup"><span data-stu-id="8f378-126">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="8f378-127">事件會根據所有可用的感應器及服務特有的分析功能，以警示和事件信號進行識別和關聯。</span><span class="sxs-lookup"><span data-stu-id="8f378-127">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="8f378-128">自動化調查和修正 (空氣) 行動裝置適用于各種實體類型，包括裝置、信箱和使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="8f378-128">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="8f378-129">可查詢更完整的高級搜尋架構，以取得來自裝置、信箱及其他實體的事件和實體資料</span><span class="sxs-lookup"><span data-stu-id="8f378-129">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="8f378-130">有限的部署案例</span><span class="sxs-lookup"><span data-stu-id="8f378-130">Limited deployment scenarios</span></span>
<span data-ttu-id="8f378-131">您部署的每個支援服務都會提供一組極其豐富的原始信號，以及相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="8f378-131">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="8f378-132">雖然有限的部署不會造成 Microsoft 365 Defender 功能關閉，但在端點、應用程式、資料及身分識別等範圍內，可提供完整的可見度的功能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="8f378-132">While limited deployment doesn’t cause Microsoft 365 Defender functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="8f378-133">同時，任何修正功能都只適用于您已部署之服務可管理的實體。</span><span class="sxs-lookup"><span data-stu-id="8f378-133">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="8f378-134">下表列出每個支援的服務如何提供額外的資料、關聯資料，以及更好的修復與回應功能，以取得額外的洞察力。</span><span class="sxs-lookup"><span data-stu-id="8f378-134">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="8f378-135">服務</span><span class="sxs-lookup"><span data-stu-id="8f378-135">Service</span></span> | <span data-ttu-id="8f378-136">資料 (信號 & 相關的資訊) </span><span class="sxs-lookup"><span data-stu-id="8f378-136">Data (signals & correlated info)</span></span> | <span data-ttu-id="8f378-137">修正 & 回應範圍</span><span class="sxs-lookup"><span data-stu-id="8f378-137">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="8f378-138">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8f378-138">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="8f378-139">-端點狀態和原始事件</span><span class="sxs-lookup"><span data-stu-id="8f378-139">- Endpoint states and raw events</span></span><br /><span data-ttu-id="8f378-140">-端點偵測和警示，包含防毒程式、EDR、攻擊面降低</span><span class="sxs-lookup"><span data-stu-id="8f378-140">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="8f378-141">-在端點上觀察到的檔案及其他實體的資訊</span><span class="sxs-lookup"><span data-stu-id="8f378-141">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="8f378-142">端點</span><span class="sxs-lookup"><span data-stu-id="8f378-142">Endpoints</span></span> |
|<span data-ttu-id="8f378-143">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8f378-143">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="8f378-144">-郵件和信箱狀態和原始事件</span><span class="sxs-lookup"><span data-stu-id="8f378-144">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="8f378-145">-電子郵件、附件及連結偵測</span><span class="sxs-lookup"><span data-stu-id="8f378-145">- Email, attachment, and link detections</span></span> | <span data-ttu-id="8f378-146">-信箱</span><span class="sxs-lookup"><span data-stu-id="8f378-146">- Mailboxes</span></span><br /><span data-ttu-id="8f378-147">-Microsoft 365 帳戶</span><span class="sxs-lookup"><span data-stu-id="8f378-147">- Microsoft 365 accounts</span></span> |
| <span data-ttu-id="8f378-148">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8f378-148">Microsoft Defender for Identity</span></span> | <span data-ttu-id="8f378-149">-Active Directory 信號，包括驗證事件</span><span class="sxs-lookup"><span data-stu-id="8f378-149">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="8f378-150">-身分識別相關的行為偵測</span><span class="sxs-lookup"><span data-stu-id="8f378-150">- Identity-related behavioral detections</span></span> | <span data-ttu-id="8f378-151">身分識別</span><span class="sxs-lookup"><span data-stu-id="8f378-151">Identities</span></span> |
| <span data-ttu-id="8f378-152">Microsoft 雲端應用程式安全性</span><span class="sxs-lookup"><span data-stu-id="8f378-152">Microsoft Cloud App Security</span></span> | <span data-ttu-id="8f378-153">-偵測 unsanctioned cloud app and services (shadow) </span><span class="sxs-lookup"><span data-stu-id="8f378-153">- Detection of unsanctioned cloud apps and services (shadow IT)</span></span><br /><span data-ttu-id="8f378-154">-向雲端應用程式公開資料</span><span class="sxs-lookup"><span data-stu-id="8f378-154">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="8f378-155">-Cloud app 相關聯的威脅活動</span><span class="sxs-lookup"><span data-stu-id="8f378-155">- Threat activity associated with cloud apps</span></span> | <span data-ttu-id="8f378-156">雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="8f378-156">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="8f378-157">部署服務</span><span class="sxs-lookup"><span data-stu-id="8f378-157">Deploy the services</span></span>
<span data-ttu-id="8f378-158">部署每個服務時，通常需要為您的租使用者和某些初始設定提供布建。</span><span class="sxs-lookup"><span data-stu-id="8f378-158">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="8f378-159">請參閱下表以瞭解各項服務的部署方式。</span><span class="sxs-lookup"><span data-stu-id="8f378-159">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="8f378-160">服務</span><span class="sxs-lookup"><span data-stu-id="8f378-160">Service</span></span> | <span data-ttu-id="8f378-161">布建指示</span><span class="sxs-lookup"><span data-stu-id="8f378-161">Provisioning instructions</span></span> | <span data-ttu-id="8f378-162">初始設定</span><span class="sxs-lookup"><span data-stu-id="8f378-162">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="8f378-163">適用於端點的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8f378-163">Microsoft Defender for Endpoint</span></span> | [<span data-ttu-id="8f378-164">Microsoft Defender for Endpoint 部署指南</span><span class="sxs-lookup"><span data-stu-id="8f378-164">Microsoft Defender for Endpoint deployment guide</span></span>](../defender-endpoint/deployment-phases.md) | <span data-ttu-id="8f378-165">*請參閱布建指示*</span><span class="sxs-lookup"><span data-stu-id="8f378-165">*See provisioning instructions*</span></span> |
|<span data-ttu-id="8f378-166">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8f378-166">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="8f378-167">*無，使用 Office 365 布建*</span><span class="sxs-lookup"><span data-stu-id="8f378-167">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="8f378-168">設定適用於 Office 365 的 Microsoft Defender 原則</span><span class="sxs-lookup"><span data-stu-id="8f378-168">Configure Microsoft Defender for Office 365 policies</span></span>](/microsoft-365/security/defender-365-security/defender-for-office-365#configure-atp-policies) |
| <span data-ttu-id="8f378-169">適用於身分識別的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8f378-169">Microsoft Defender for Identity</span></span> | [<span data-ttu-id="8f378-170">快速入門：建立您的 Microsoft Defender for Identity 實例</span><span class="sxs-lookup"><span data-stu-id="8f378-170">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="8f378-171">*請參閱布建指示*</span><span class="sxs-lookup"><span data-stu-id="8f378-171">*See provisioning instructions*</span></span> |
| <span data-ttu-id="8f378-172">Microsoft 雲端應用程式安全性</span><span class="sxs-lookup"><span data-stu-id="8f378-172">Microsoft Cloud App Security</span></span> | <span data-ttu-id="8f378-173">*無*</span><span class="sxs-lookup"><span data-stu-id="8f378-173">*None*</span></span> | [<span data-ttu-id="8f378-174">快速入門： Microsoft Cloud App Security 快速入門</span><span class="sxs-lookup"><span data-stu-id="8f378-174">Quickstart: Get started with Microsoft Cloud App Security</span></span>](/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="8f378-175">部署支援的服務之後，請 [開啟 Microsoft 365 Defender](m365d-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="8f378-175">Once you’ve deployed the supported services, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8f378-176">相關主題</span><span class="sxs-lookup"><span data-stu-id="8f378-176">Related topics</span></span>

- [<span data-ttu-id="8f378-177">Microsoft 365 Defender 概述</span><span class="sxs-lookup"><span data-stu-id="8f378-177">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="8f378-178">開啟 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8f378-178">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
- [<span data-ttu-id="8f378-179">Microsoft Defender for Endpoint 簡介</span><span class="sxs-lookup"><span data-stu-id="8f378-179">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-advanced-threat-protection.md)
- [<span data-ttu-id="8f378-180">Microsoft Defender for Office 365 簡介</span><span class="sxs-lookup"><span data-stu-id="8f378-180">Microsoft Defender for Office 365 overview</span></span>](../defender-365-security/defender-for-office-365.md)
- [<span data-ttu-id="8f378-181">Microsoft Cloud App Security 概觀</span><span class="sxs-lookup"><span data-stu-id="8f378-181">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="8f378-182">Microsoft Defender 身分識別概述</span><span class="sxs-lookup"><span data-stu-id="8f378-182">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
