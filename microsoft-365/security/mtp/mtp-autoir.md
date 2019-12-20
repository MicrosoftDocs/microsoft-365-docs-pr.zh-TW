---
title: Microsoft 威脅防護的自動化調查及回應
description: Microsoft 威脅防護的自動化調查及回應功能的概
keywords: automated, investigation, alert, trigger, action, remediation, 自動化, 調查, 警示, 觸發, 動作, 補救
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: ea3201838e625969a239aee4339e0de605d95c55
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808608"
---
# <a name="automated-investigation-and-response-air-in-microsoft-threat-protection"></a><span data-ttu-id="ad7b3-104">Microsoft 威脅防護的自動化調查及回應 (AIR)</span><span class="sxs-lookup"><span data-stu-id="ad7b3-104">Automated investigation and response (AIR) in Microsoft Threat Protection</span></span>

<span data-ttu-id="ad7b3-105">**適用於：**</span><span class="sxs-lookup"><span data-stu-id="ad7b3-105">**Applies to:**</span></span>
- <span data-ttu-id="ad7b3-106">Microsoft 威脅防護</span><span class="sxs-lookup"><span data-stu-id="ad7b3-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

## <a name="your-virtual-analyst"></a><span data-ttu-id="ad7b3-107">您的虛擬分析員</span><span class="sxs-lookup"><span data-stu-id="ad7b3-107">Your virtual analyst</span></span>

<span data-ttu-id="ad7b3-108">當安全性警示觸發時，您的安全性作業小組將會了解這些警示，並採取步驟保護貴組織。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-108">As security alerts are triggered, it’s up to your security operations team to look into those alerts and take steps to protect your organization.</span></span> <span data-ttu-id="ad7b3-109">優先處理和調查警示可能會非常耗時，特別是在調查進行時新警示持續出現。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-109">Prioritizing and investigating alerts can be very time consuming, especially when new alerts keep coming in while an investigation is going on.</span></span> <span data-ttu-id="ad7b3-110">安全性作業小組可能會對必須監控和防範的龐大威脅感到不知所措。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-110">Security operations teams can feel overwhelmed by the sheer volume of threats they must monitor and protect against.</span></span> 

<span data-ttu-id="ad7b3-111">想像您的第 1 層 / 第 2 層安全性作業小組中有一個虛擬分析員。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-111">Imagine having a virtual analyst in your Tier 1 / Tier 2 security operations team.</span></span> <span data-ttu-id="ad7b3-112">虛擬分析員會模仿安全性作業要採取哪些理想步驟來調查和補救威脅。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-112">The virtual analyst mimics the ideal steps that security operations would take to investigate and remediate threats.</span></span> <span data-ttu-id="ad7b3-113">虛擬助理可以全天候工作、提供無限能力，以及接受大量調查和威脅補救。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-113">The virtual assistant could work 24x7, with unlimited capacity, and take on a significant load of investigations and threat remediation.</span></span> <span data-ttu-id="ad7b3-114">如此一來，虛擬助理可以大幅減少回應時間，讓您的安全性作業小組能夠進行其他重要的策略專案。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-114">Such a virtual assistant could significantly reduce the time to respond, freeing up your security operations team for other important strategic projects.</span></span> <span data-ttu-id="ad7b3-115">如果這聽起來像是科幻小說中的場景，但確實是真的！</span><span class="sxs-lookup"><span data-stu-id="ad7b3-115">If this scenario sounds like science fiction, it’s not!</span></span> <span data-ttu-id="ad7b3-116">這類虛擬分析員是屬於您的 Microsoft 威脅防護套件，其名稱為*自動化調查及回應* (AIR)。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-116">Such a virtual analyst is part of your Microsoft Threat Protection suite, and its name is *automated investigation and response* (AIR).</span></span>

<span data-ttu-id="ad7b3-117">AIR 可讓您的安全性作業小組大幅增加貴組織處理安全性警示和事件的能力。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-117">AIR enables your security operations team to dramatically increase your organization's capacity to deal with security alerts and incidents.</span></span> <span data-ttu-id="ad7b3-118">透過 AIR，您可以降低處理調查和補救活動的成本，並充分利用威脅防護套件。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-118">With AIR, you can reduce the cost of dealing with investigation and remediation activities and get the most out of your threat protection suite.</span></span> <span data-ttu-id="ad7b3-119">AIR 協助您的安全性作業小組：</span><span class="sxs-lookup"><span data-stu-id="ad7b3-119">AIR helps your security operations team by:</span></span>

1.  <span data-ttu-id="ad7b3-120">判斷是否要針對威脅採取動作；</span><span class="sxs-lookup"><span data-stu-id="ad7b3-120">Determining whether a threat requires action;</span></span>
2.  <span data-ttu-id="ad7b3-121">執行 (或建議) 任何必要補救動作；</span><span class="sxs-lookup"><span data-stu-id="ad7b3-121">Performing (or recommending) any necessary remediation actions;</span></span>
3.  <span data-ttu-id="ad7b3-122">判斷應該要進行哪些其他調查；以及</span><span class="sxs-lookup"><span data-stu-id="ad7b3-122">Determining what additional investigations should occur; and</span></span>
4.  <span data-ttu-id="ad7b3-123">針對其他警示重複採取必要程序。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-123">Repeating the process as necessary for other alerts.</span></span>

## <a name="the-automated-investigation-process"></a><span data-ttu-id="ad7b3-124">自動化調查程序</span><span class="sxs-lookup"><span data-stu-id="ad7b3-124">The automated investigation process</span></span>

<span data-ttu-id="ad7b3-125">**警示** > **事件** > **自動化調查** > **結果** > **補救動作**</span><span class="sxs-lookup"><span data-stu-id="ad7b3-125">**Alert** > **incident** > **automated investigation** > **verdict** > **remediation action**</span></span>

<span data-ttu-id="ad7b3-126">在高層級，觸發的警示會建立事件，其便會開始自動化調查。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-126">At a high level, a triggered alert creates an incident, which can start an automated investigation.</span></span> <span data-ttu-id="ad7b3-127">該調查會產生一或多個補救動作。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-127">That investigation can result in one or more remediation actions.</span></span> <span data-ttu-id="ad7b3-128">在 Microsoft 威脅防護中，每個自動化調查會與 Azure 進階威脅防護 (Azure ATP)、Microsoft Defender 進階威脅防護 (Microsoft Defender ATP) 和 Office 365 進階威脅防護 (Office 365 ATP) 的訊號有關聯，如下表所示：</span><span class="sxs-lookup"><span data-stu-id="ad7b3-128">In Microsoft Threat Protection, each automated investigation correlates signals across Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP), and Office 365 Advanced Threat Protection (Office 365 ATP), as summarized in the following table:</span></span> 

|<span data-ttu-id="ad7b3-129">實體</span><span class="sxs-lookup"><span data-stu-id="ad7b3-129">Entities</span></span> |<span data-ttu-id="ad7b3-130">威脅防護服務</span><span class="sxs-lookup"><span data-stu-id="ad7b3-130">Threat protection services</span></span>  |
|---------|---------|
|<span data-ttu-id="ad7b3-131">裝置 (也稱為端點)</span><span class="sxs-lookup"><span data-stu-id="ad7b3-131">Devices (also referred to as endpoints)</span></span>     |[<span data-ttu-id="ad7b3-132">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="ad7b3-132">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[<span data-ttu-id="ad7b3-133">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="ad7b3-133">Azure ATP</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|<span data-ttu-id="ad7b3-134">電子郵件內容 (信箱中的檔案和郵件)</span><span class="sxs-lookup"><span data-stu-id="ad7b3-134">Email content (files and messages in mailboxes)</span></span>     |[<span data-ttu-id="ad7b3-135">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="ad7b3-135">Office 365 ATP</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |


<span data-ttu-id="ad7b3-136">每個調查會針對每個調查證據產生結果 (*惡意*、*可疑*或*乾淨*)。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-136">Each investigation generates verdicts (*Malicious*, *Suspicious*, or *Clean*) for each piece of evidence investigated.</span></span> <span data-ttu-id="ad7b3-137">根據威脅類型和產生的結果，補救動作會自動進行，或由貴組織的安全性作業小組核准進行。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-137">Depending on the type of threat and resulting verdict, remediation actions occur automatically or upon approval by your organization’s security operations team.</span></span> <span data-ttu-id="ad7b3-138">待處理和已完成的操作會列在[重要訊息中心](mtp-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-138">Pending and completed actions are listed in the [Action center](mtp-action-center.md).</span></span>

<span data-ttu-id="ad7b3-139">當調查進行時，出現的任何其他相關警示會新增到調查中，直到調查完成。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-139">While an investigation is running, any other related alerts that arise are added to the investigation until it completes.</span></span> <span data-ttu-id="ad7b3-140">如果在其他地方看到受感染的實體，則自動化調查將擴大其範圍，以包括該實體，並且將執行一般安全性劇本。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-140">If an incriminated entity is seen elsewhere, the automated investigation will expand its scope to include that entity, and a general security playbook will run.</span></span> 

> [!NOTE]
> <span data-ttu-id="ad7b3-141">並非每個警式都會觸發自動化調查，也不是每個調查都會產生自動化補救措施；這一切都取決於貴組織如何設定 AIR。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-141">Not every alert triggers an automated investigation, and not every investigation results in automated remediation actions; this all depends on how AIR is configured for your organization.</span></span> 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a><span data-ttu-id="ad7b3-142">Microsoft 威脅防護的 AIR 需求</span><span class="sxs-lookup"><span data-stu-id="ad7b3-142">Requirements for AIR in Microsoft Threat Protection</span></span>

| | |
|--|--|
|<span data-ttu-id="ad7b3-143">訂閱需求</span><span class="sxs-lookup"><span data-stu-id="ad7b3-143">Subscription requirements</span></span> |<span data-ttu-id="ad7b3-144">- Microsoft 365 E5 或 Microsoft 365 E3 以及身分識別與威脅防護產品</span><span class="sxs-lookup"><span data-stu-id="ad7b3-144">- Microsoft 365 E5 or Microsoft 365 E3 together with Identity & Threat Protection</span></span><br/><span data-ttu-id="ad7b3-145">- 請參閱[Microsoft 365 方案](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview#plans)</span><span class="sxs-lookup"><span data-stu-id="ad7b3-145">- See [Microsoft 365 plans](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview#plans)</span></span>|
|<span data-ttu-id="ad7b3-146">網路需求</span><span class="sxs-lookup"><span data-stu-id="ad7b3-146">Network requirements</span></span> |<span data-ttu-id="ad7b3-147">- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)已啟用</span><span class="sxs-lookup"><span data-stu-id="ad7b3-147">- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) enabled</span></span><br/><span data-ttu-id="ad7b3-148">- [Microsoft 雲端 App 安全性](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) 已設定</span><span class="sxs-lookup"><span data-stu-id="ad7b3-148">- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) configured</span></span><br/><span data-ttu-id="ad7b3-149">- [與 Azure ATP 整合的 MCAS](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span><span class="sxs-lookup"><span data-stu-id="ad7b3-149">- [MCAS integrated with Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration)</span></span> |
|<span data-ttu-id="ad7b3-150">Windows 電腦需求</span><span class="sxs-lookup"><span data-stu-id="ad7b3-150">Windows machine requirements</span></span> |<span data-ttu-id="ad7b3-151">- Windows 10，安裝版本 1709 或更新版本 (請參閱 [Windows 10 版本資訊](https://docs.microsoft.com/windows/release-information/))</span><span class="sxs-lookup"><span data-stu-id="ad7b3-151">- Windows 10, version 1709 or later installed (See [Windows 10 release information](https://docs.microsoft.com/windows/release-information/))</span></span><br/><span data-ttu-id="ad7b3-152">- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) 已設定</span><span class="sxs-lookup"><span data-stu-id="ad7b3-152">- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) configured</span></span> <br/><span data-ttu-id="ad7b3-153">- [Windows Defender 防毒軟體](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)已設定</span><span class="sxs-lookup"><span data-stu-id="ad7b3-153">- [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) configured</span></span> |
|<span data-ttu-id="ad7b3-154">權限</span><span class="sxs-lookup"><span data-stu-id="ad7b3-154">Permissions</span></span> |<span data-ttu-id="ad7b3-155">- 若要*設定* AIR，您必須在 Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) 或 Microsoft 365 系統管理中心 ([https://admin.microsoft.com](https://admin.microsoft.com)) 中被指派**全域系統管理員**或**安全性系統管理員**角色。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-155">- To *configure* AIR, you must have the **Global Administrator** or **Security Administrator** role assigned in either Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) or in the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)).</span></span><br/><br/><span data-ttu-id="ad7b3-156">- 若要*使用* AIR 功能，請參閱[重要訊息中心的必要權限](mtp-action-center.md#required-permissions-for-action-center-tasks)。</span><span class="sxs-lookup"><span data-stu-id="ad7b3-156">- To *use* AIR capabilities, see [Required permissions for Action center tasks](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span> |

## <a name="next-steps"></a><span data-ttu-id="ad7b3-157">後續步驟</span><span class="sxs-lookup"><span data-stu-id="ad7b3-157">Next steps</span></span>

- [<span data-ttu-id="ad7b3-158">與自動化調查及回應相關的核准或拒絕動作</span><span class="sxs-lookup"><span data-stu-id="ad7b3-158">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="ad7b3-159">深入了解重要訊息中心</span><span class="sxs-lookup"><span data-stu-id="ad7b3-159">Learn more about the Action center</span></span>](mtp-action-center.md)
