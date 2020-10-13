---
title: 部署 Microsoft 威脅防護所支援的服務
description: 深入瞭解可透過 Microsoft 威脅防護、其授權需求和部署程式整合的 Microsoft 安全性服務
keywords: 部署，授權，支援的服務，布建，設定 Microsoft 威脅防護，M365，授權資格，Microsoft Defender ATP，MDATP，Office 365 ATP，Azure ATP，Microsoft Cloud App Security，MCAS，advanced 威脅防護，E5，A5，EMS
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 4e4036e1a1ee0ccf807dc5299b9842911f140478
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430808"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="5af19-104">部署支援服務</span><span class="sxs-lookup"><span data-stu-id="5af19-104">Deploy supported services</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5af19-105">適用於：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5af19-105">**Applies to:**</span></span>
- <span data-ttu-id="5af19-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="5af19-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="5af19-107">[Microsoft 威脅防護](microsoft-threat-protection.md) 會整合各種 Microsoft 安全性服務，以提供集中式偵測、防護和調查功能，以防禦複雜的攻擊。</span><span class="sxs-lookup"><span data-stu-id="5af19-107">[Microsoft Threat Protection](microsoft-threat-protection.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="5af19-108">本文說明支援的服務、其授權需求、與部署一或多項服務相關的優點與限制，以及您可以個別完全部署這些服務的方式連結。</span><span class="sxs-lookup"><span data-stu-id="5af19-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="5af19-109">支援的服務</span><span class="sxs-lookup"><span data-stu-id="5af19-109">Supported services</span></span>
<span data-ttu-id="5af19-110">Microsoft 365 E5，E5 Security，A5，or A5 安全性授權或有效的授權組合，可提供下列支援服務的存取權，以及您在 Microsoft 365 安全性中心中使用 Microsoft 威脅防護所享有的許可權。</span><span class="sxs-lookup"><span data-stu-id="5af19-110">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to the following supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span> [<span data-ttu-id="5af19-111">請參閱授權需求</span><span class="sxs-lookup"><span data-stu-id="5af19-111">See licensing requirements</span></span>](prerequisites.md#licensing-requirements)

| <span data-ttu-id="5af19-112">支援的服務</span><span class="sxs-lookup"><span data-stu-id="5af19-112">Supported service</span></span> | <span data-ttu-id="5af19-113">描述</span><span class="sxs-lookup"><span data-stu-id="5af19-113">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="5af19-114">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5af19-114">Microsoft Defender ATP</span></span> | <span data-ttu-id="5af19-115">以強大行為感應器、雲端分析和威脅智慧為基礎的 Endpoint protection 套件</span><span class="sxs-lookup"><span data-stu-id="5af19-115">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
| <span data-ttu-id="5af19-116">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="5af19-116">Office 365 ATP</span></span> | <span data-ttu-id="5af19-117">Office 365 中的應用程式和資料的高級保護，包括電子郵件和其他共同作業工具</span><span class="sxs-lookup"><span data-stu-id="5af19-117">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="5af19-118">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="5af19-118">Azure ATP</span></span> | <span data-ttu-id="5af19-119">使用關聯的 Active Directory 信號，防禦高級威脅、遭到破壞的身分識別，以及惡意內幕用。</span><span class="sxs-lookup"><span data-stu-id="5af19-119">Defend against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="5af19-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5af19-120">Microsoft Cloud App Security</span></span> | <span data-ttu-id="5af19-121">在您的 Microsoft 和協力廠商雲端服務之間識別及打擊 cyberthreats</span><span class="sxs-lookup"><span data-stu-id="5af19-121">Identify and combat cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="5af19-122">部署的服務和功能</span><span class="sxs-lookup"><span data-stu-id="5af19-122">Deployed services and functionality</span></span>
<span data-ttu-id="5af19-123">當您部署更支援的服務時，Microsoft 威脅防護可提供更佳的可見度、關聯性和修正功能。</span><span class="sxs-lookup"><span data-stu-id="5af19-123">Microsoft Threat Protection provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="5af19-124">完整部署的優點</span><span class="sxs-lookup"><span data-stu-id="5af19-124">Benefits of full deployment</span></span>
<span data-ttu-id="5af19-125">若要取得 Microsoft 威脅防護的完整優點，建議您部署所有支援的服務。</span><span class="sxs-lookup"><span data-stu-id="5af19-125">To get the complete benefits of Microsoft Threat Protection, we recommend deploying all supported services.</span></span> <span data-ttu-id="5af19-126">以下是完整部署的一些重要優點：</span><span class="sxs-lookup"><span data-stu-id="5af19-126">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="5af19-127">事件會根據所有可用的感應器及服務特有的分析功能，以警示和事件信號進行識別和關聯。</span><span class="sxs-lookup"><span data-stu-id="5af19-127">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="5af19-128">自動化調查和修正 (空氣) 行動裝置適用于各種實體類型，包括裝置、信箱和使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="5af19-128">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="5af19-129">可查詢更完整的高級搜尋架構，以取得來自裝置、信箱及其他實體的事件和實體資料</span><span class="sxs-lookup"><span data-stu-id="5af19-129">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="5af19-130">有限的部署案例</span><span class="sxs-lookup"><span data-stu-id="5af19-130">Limited deployment scenarios</span></span>
<span data-ttu-id="5af19-131">您部署的每個支援服務都會提供一組極其豐富的原始信號，以及相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="5af19-131">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="5af19-132">雖然有限的部署不會造成 Microsoft 威脅防護功能關閉，但在端點、應用程式、資料及身分識別等範圍內，其提供完整可視性的能力也會受到影響。</span><span class="sxs-lookup"><span data-stu-id="5af19-132">While limited deployment doesn’t cause Microsoft Threat Protection functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="5af19-133">同時，任何修正功能都只適用于您已部署之服務可管理的實體。</span><span class="sxs-lookup"><span data-stu-id="5af19-133">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="5af19-134">下表列出每個支援的服務如何提供額外的資料、關聯資料，以及更好的修復與回應功能，以取得額外的洞察力。</span><span class="sxs-lookup"><span data-stu-id="5af19-134">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="5af19-135">服務</span><span class="sxs-lookup"><span data-stu-id="5af19-135">Service</span></span> | <span data-ttu-id="5af19-136">資料 (信號 & 相關的資訊) </span><span class="sxs-lookup"><span data-stu-id="5af19-136">Data (signals & correlated info)</span></span> | <span data-ttu-id="5af19-137">修正 & 回應範圍</span><span class="sxs-lookup"><span data-stu-id="5af19-137">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="5af19-138">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5af19-138">Microsoft Defender ATP</span></span> | <span data-ttu-id="5af19-139">-端點狀態和原始事件</span><span class="sxs-lookup"><span data-stu-id="5af19-139">- Endpoint states and raw events</span></span><br /><span data-ttu-id="5af19-140">-端點偵測和警示，包含防毒程式、EDR、攻擊面降低</span><span class="sxs-lookup"><span data-stu-id="5af19-140">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="5af19-141">-在端點上觀察到的檔案及其他實體的資訊</span><span class="sxs-lookup"><span data-stu-id="5af19-141">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="5af19-142">端點</span><span class="sxs-lookup"><span data-stu-id="5af19-142">Endpoints</span></span> |
| <span data-ttu-id="5af19-143">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="5af19-143">Office 365 ATP</span></span> | <span data-ttu-id="5af19-144">-郵件和信箱狀態和原始事件</span><span class="sxs-lookup"><span data-stu-id="5af19-144">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="5af19-145">-電子郵件、附件及連結偵測</span><span class="sxs-lookup"><span data-stu-id="5af19-145">- Email, attachment, and link detections</span></span> | <span data-ttu-id="5af19-146">-信箱</span><span class="sxs-lookup"><span data-stu-id="5af19-146">- Mailboxes</span></span><br /><span data-ttu-id="5af19-147">-Microsoft 365 帳戶</span><span class="sxs-lookup"><span data-stu-id="5af19-147">- Microsoft 365 accounts</span></span> |
| <span data-ttu-id="5af19-148">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="5af19-148">Azure ATP</span></span> | <span data-ttu-id="5af19-149">-Active Directory 信號，包括驗證事件</span><span class="sxs-lookup"><span data-stu-id="5af19-149">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="5af19-150">-身分識別相關的行為偵測</span><span class="sxs-lookup"><span data-stu-id="5af19-150">- Identity-related behavioral detections</span></span> | <span data-ttu-id="5af19-151">身分識別</span><span class="sxs-lookup"><span data-stu-id="5af19-151">Identities</span></span> |
| <span data-ttu-id="5af19-152">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5af19-152">Microsoft Cloud App Security</span></span> | <span data-ttu-id="5af19-153">-偵測 unsanctioned cloud app and services (shadow) </span><span class="sxs-lookup"><span data-stu-id="5af19-153">- Detection of unsanctioned cloud apps and services (shadow IT)</span></span><br /><span data-ttu-id="5af19-154">-向雲端應用程式公開資料</span><span class="sxs-lookup"><span data-stu-id="5af19-154">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="5af19-155">-Cloud app 相關聯的威脅活動</span><span class="sxs-lookup"><span data-stu-id="5af19-155">- Threat activity associated with cloud apps</span></span> | <span data-ttu-id="5af19-156">雲端應用程式</span><span class="sxs-lookup"><span data-stu-id="5af19-156">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="5af19-157">部署服務</span><span class="sxs-lookup"><span data-stu-id="5af19-157">Deploy the services</span></span>
<span data-ttu-id="5af19-158">部署每個服務時，通常需要為您的租使用者和某些初始設定提供布建。</span><span class="sxs-lookup"><span data-stu-id="5af19-158">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="5af19-159">請參閱下表以瞭解各項服務的部署方式。</span><span class="sxs-lookup"><span data-stu-id="5af19-159">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="5af19-160">服務</span><span class="sxs-lookup"><span data-stu-id="5af19-160">Service</span></span> | <span data-ttu-id="5af19-161">布建指示</span><span class="sxs-lookup"><span data-stu-id="5af19-161">Provisioning instructions</span></span> | <span data-ttu-id="5af19-162">初始設定</span><span class="sxs-lookup"><span data-stu-id="5af19-162">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="5af19-163">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5af19-163">Microsoft Defender ATP</span></span> | [<span data-ttu-id="5af19-164">Microsoft Defender ATP 部署指南</span><span class="sxs-lookup"><span data-stu-id="5af19-164">Microsoft Defender ATP deployment guide</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | <span data-ttu-id="5af19-165">*請參閱布建指示*</span><span class="sxs-lookup"><span data-stu-id="5af19-165">*See provisioning instructions*</span></span> |
| <span data-ttu-id="5af19-166">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="5af19-166">Office 365 ATP</span></span> | <span data-ttu-id="5af19-167">*無，使用 Office 365 布建*</span><span class="sxs-lookup"><span data-stu-id="5af19-167">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="5af19-168">設定 ATP 原則</span><span class="sxs-lookup"><span data-stu-id="5af19-168">Configure ATP policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| <span data-ttu-id="5af19-169">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="5af19-169">Azure ATP</span></span> | [<span data-ttu-id="5af19-170">快速入門：建立您的 Azure ATP 實例</span><span class="sxs-lookup"><span data-stu-id="5af19-170">Quickstart: Create your Azure ATP instance</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="5af19-171">*請參閱布建指示*</span><span class="sxs-lookup"><span data-stu-id="5af19-171">*See provisioning instructions*</span></span> |
| <span data-ttu-id="5af19-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5af19-172">Microsoft Cloud App Security</span></span> | <span data-ttu-id="5af19-173">*無*</span><span class="sxs-lookup"><span data-stu-id="5af19-173">*None*</span></span> | [<span data-ttu-id="5af19-174">快速入門： Microsoft Cloud App Security 快速入門</span><span class="sxs-lookup"><span data-stu-id="5af19-174">Quickstart: Get started with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="5af19-175">部署支援的服務後， [開啟 Microsoft 威脅防護](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="5af19-175">Once you’ve deployed the supported services, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5af19-176">相關主題</span><span class="sxs-lookup"><span data-stu-id="5af19-176">Related topics</span></span>

- [<span data-ttu-id="5af19-177">Microsoft 威脅防護概觀</span><span class="sxs-lookup"><span data-stu-id="5af19-177">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="5af19-178">開啟 Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="5af19-178">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="5af19-179">Microsoft Defender ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="5af19-179">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="5af19-180">Office 365 ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="5af19-180">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="5af19-181">Microsoft Cloud App Security 概觀</span><span class="sxs-lookup"><span data-stu-id="5af19-181">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="5af19-182">Azure ATP 概觀</span><span class="sxs-lookup"><span data-stu-id="5af19-182">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
