---
title: 在 Microsoft Defender 中防禦威脅，以供 Office 365、反惡意程式碼、反網路釣魚、反垃圾郵件、保管庫連結、保管庫附件、零小時自動清除 (ZAP) ，MDO 的安全性設定
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 06/22/2021
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 系統管理員可以深入瞭解 Microsoft 365 中的威脅防護，並設定如何將它用於您的組織。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7e37b67dbed75e3283070ba94321fcb03979a5a6
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105389"
---
# <a name="protect-against-threats"></a><span data-ttu-id="01e66-103">防範威脅</span><span class="sxs-lookup"><span data-stu-id="01e66-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="01e66-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="01e66-104">**Applies to**</span></span>
- [<span data-ttu-id="01e66-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="01e66-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="01e66-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="01e66-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="01e66-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01e66-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="01e66-108">以下是將 Office 365 的 Defender 設定中斷為區塊的快速入門手冊。</span><span class="sxs-lookup"><span data-stu-id="01e66-108">Here's a quick-start guide that breaks the configuration of Defender for Office 365 into chunks.</span></span> <span data-ttu-id="01e66-109">如果您是 Office 365 中威脅防護功能的新功能，請不要確定開始的位置，或者，如果您想要瞭解，請使用本指導 *方針做為* 檢查清單和開始點。</span><span class="sxs-lookup"><span data-stu-id="01e66-109">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01e66-110">**每種原則都包含初始建議設定，但有許多選項可供使用，您可以調整設定，以符合特定組織的需求**。</span><span class="sxs-lookup"><span data-stu-id="01e66-110">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="01e66-111">允許大約30分鐘的原則或變更以透過您的資料中心來運作。</span><span class="sxs-lookup"><span data-stu-id="01e66-111">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>
>
> <span data-ttu-id="01e66-112">若要在 Office 365 中略過大多數原則的手動設定，您可以使用標準或嚴格層級的預先設定安全性原則。</span><span class="sxs-lookup"><span data-stu-id="01e66-112">To skip manual configuration of most policies in Defender for Office 365, you can use preset security policies at the Standard or Strict level.</span></span> <span data-ttu-id="01e66-113">如需詳細資訊，請參閱[EOP 和 Microsoft Defender for Office 365 中的預先設定安全性原則](preset-security-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="01e66-113">For more information, see [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="01e66-114">需求</span><span class="sxs-lookup"><span data-stu-id="01e66-114">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="01e66-115">訂閱</span><span class="sxs-lookup"><span data-stu-id="01e66-115">Subscriptions</span></span>

<span data-ttu-id="01e66-116">威脅防護功能包含在 *所有* Microsoft 或 Office 365 訂閱中;不過，有些訂閱具有高級功能。</span><span class="sxs-lookup"><span data-stu-id="01e66-116">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="01e66-117">下表列出本文所含的保護功能及最低訂閱需求。</span><span class="sxs-lookup"><span data-stu-id="01e66-117">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="01e66-118">請注意，除了開啟審計的指示之外，還 *會啟動反* 惡意程式碼、反網路釣魚和反垃圾郵件，並標示為 Office 365 Exchange Online Protection (**EOP**) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="01e66-118">Notice that beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="01e66-119">這在 Office 365 文章的 defender 中看起來會是奇怪的，直到您記得 (**Defender for Office 365**) 包含]，並建立 EOP。</span><span class="sxs-lookup"><span data-stu-id="01e66-119">This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.</span></span>

<br>

****

|<span data-ttu-id="01e66-120">保護類型</span><span class="sxs-lookup"><span data-stu-id="01e66-120">Protection type</span></span>|<span data-ttu-id="01e66-121">訂閱需求</span><span class="sxs-lookup"><span data-stu-id="01e66-121">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="01e66-122">用於報表目的的審計記錄 () </span><span class="sxs-lookup"><span data-stu-id="01e66-122">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="01e66-123">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="01e66-123">Exchange Online</span></span>](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="01e66-124">反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="01e66-124">Anti-malware protection</span></span>|<span data-ttu-id="01e66-125">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**) </span><span class="sxs-lookup"><span data-stu-id="01e66-125">[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="01e66-126">防網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="01e66-126">Anti-phishing protection</span></span>|[<span data-ttu-id="01e66-127">EOP</span><span class="sxs-lookup"><span data-stu-id="01e66-127">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="01e66-128">反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="01e66-128">Anti-spam protection</span></span>|[<span data-ttu-id="01e66-129">EOP</span><span class="sxs-lookup"><span data-stu-id="01e66-129">EOP</span></span>](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="01e66-130">保護電子郵件中的惡意 URLs 和檔案，以及 Office 檔中的檔 (保管庫連結及保管庫附件) </span><span class="sxs-lookup"><span data-stu-id="01e66-130">Protection from malicious URLs and files in email and Office documents (Safe Links and Safe Attachments)</span></span>|[<span data-ttu-id="01e66-131">適用於 Office 365 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="01e66-131">Microsoft Defender for Office 365</span></span>](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="01e66-132">角色及權限</span><span class="sxs-lookup"><span data-stu-id="01e66-132">Roles and permissions</span></span>

<span data-ttu-id="01e66-133">若要設定 Office 365 原則的 Defender，您必須獲指派適當的角色。</span><span class="sxs-lookup"><span data-stu-id="01e66-133">To configure Defender for Office 365 policies, you must be assigned an appropriate role.</span></span> <span data-ttu-id="01e66-134">請參閱下表，以取得可以執行這些動作的角色。</span><span class="sxs-lookup"><span data-stu-id="01e66-134">Take a look at the table below for roles that can do these actions.</span></span>

<br>

****

|<span data-ttu-id="01e66-135">角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="01e66-135">Role or role group</span></span>|<span data-ttu-id="01e66-136">深入瞭解</span><span class="sxs-lookup"><span data-stu-id="01e66-136">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="01e66-137">全域管理員</span><span class="sxs-lookup"><span data-stu-id="01e66-137">global administrator</span></span>|[<span data-ttu-id="01e66-138">關於 Microsoft 365 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="01e66-138">About Microsoft 365 admin roles</span></span>](../../admin/add-users/about-admin-roles.md)|
|<span data-ttu-id="01e66-139">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="01e66-139">Security Administrator</span></span>|[<span data-ttu-id="01e66-140">Azure Active Directory 中的系統管理員角色權限</span><span class="sxs-lookup"><span data-stu-id="01e66-140">Administrator role permissions in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="01e66-141">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="01e66-141">Exchange Online Organization Management</span></span>|[<span data-ttu-id="01e66-142">Exchange Online 中的權限</span><span class="sxs-lookup"><span data-stu-id="01e66-142">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)|
|

<span data-ttu-id="01e66-143">若要深入瞭解，請參閱[Microsoft 365 Defender 入口網站中的許可權](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="01e66-143">To learn more, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="01e66-144">開啟報告和調查的審計記錄</span><span class="sxs-lookup"><span data-stu-id="01e66-144">Turn on audit logging for reporting and investigation</span></span>

- <span data-ttu-id="01e66-145">儘早開始您的審核記錄。</span><span class="sxs-lookup"><span data-stu-id="01e66-145">Start your audit logging early.</span></span> <span data-ttu-id="01e66-146">您必須執行下列其中一個 **步驟的審計** 。</span><span class="sxs-lookup"><span data-stu-id="01e66-146">You'll need auditing to be **ON** for some of the following steps.</span></span> <span data-ttu-id="01e66-147">您可以在包含[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)的訂閱中使用審核記錄。</span><span class="sxs-lookup"><span data-stu-id="01e66-147">Audit logging is available in subscriptions that include [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="01e66-148">為了在威脅防護報告、 [電子郵件安全性報告](view-email-security-reports.md)和 [Explorer](threat-explorer.md)中查看資料，必須 *啟用* 審核記錄。</span><span class="sxs-lookup"><span data-stu-id="01e66-148">In order to view data in threat protection reports, [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="01e66-149">若要深入瞭解，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="01e66-149">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection-in-eop"></a><span data-ttu-id="01e66-150">第1部分-EOP 中的反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="01e66-150">Part 1 - Anti-malware protection in EOP</span></span>

<span data-ttu-id="01e66-151">如需有關反惡意程式碼建議設定的詳細資訊，請參閱 [EOP 防盜-惡意程式碼原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="01e66-151">For more information about the recommended settings for anti-malware, see [EOP anti-malware policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings).</span></span>

1. <span data-ttu-id="01e66-152">在 Microsoft 365 Defender 入口網站中，開啟 [**反惡意** 代碼] 頁面 <https://security.microsoft.com/antimalwarev2> 。</span><span class="sxs-lookup"><span data-stu-id="01e66-152">Open the **Anti-malware** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/antimalwarev2>.</span></span>

2. <span data-ttu-id="01e66-153">在 [ **反惡意** 代碼] 頁面上，透過按一下名稱，選取名為 **default (default)** 的原則。</span><span class="sxs-lookup"><span data-stu-id="01e66-153">On the **Anti-malware** page, select the policy named **Default (Default)** by clicking on the name.</span></span>

3. <span data-ttu-id="01e66-154">在開啟的 [原則詳細資料] 浮出視窗中，按一下 [ **編輯保護設定**]，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-154">In the policy details flyout that opens, click **Edit protection settings**, and then configure the following settings:</span></span>
   - <span data-ttu-id="01e66-155">**保護設定** 區段：</span><span class="sxs-lookup"><span data-stu-id="01e66-155">**Protection settings** section:</span></span>
     - <span data-ttu-id="01e66-156">**啟用常見附件篩選**：選取 [ (開啟) ]。</span><span class="sxs-lookup"><span data-stu-id="01e66-156">**Enable the common attachments filter**: Select (turn on).</span></span> <span data-ttu-id="01e66-157">按一下 [ **自訂檔案類型** ]，以新增更多檔案類型。</span><span class="sxs-lookup"><span data-stu-id="01e66-157">Click **Customize file types** to add more file types.</span></span>
     - <span data-ttu-id="01e66-158">**啟用惡意程式碼的零小時自動清除**：確認已選取此設定。</span><span class="sxs-lookup"><span data-stu-id="01e66-158">**Enable zero-hour auto purge for malware**: Verify this setting is selected.</span></span> <span data-ttu-id="01e66-159">如需有關惡意程式碼之 ZAP 的詳細資訊，請參閱 [零小時自動清除 (zap) 惡意](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware)代碼。</span><span class="sxs-lookup"><span data-stu-id="01e66-159">For more information about ZAP for malware, see [Zero-hour auto purge (ZAP) for malware](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware).</span></span>
   - <span data-ttu-id="01e66-160">**通知** 區段：確認未選取任何通知設定。</span><span class="sxs-lookup"><span data-stu-id="01e66-160">**Notification** section: Verify that none of the notification settings are selected.</span></span>

   <span data-ttu-id="01e66-161">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="01e66-161">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="01e66-162">回到原則詳細資料飛出視窗，按一下 [關閉 **]**。</span><span class="sxs-lookup"><span data-stu-id="01e66-162">Back on the policy details flyout, click **Close**.</span></span>

<span data-ttu-id="01e66-163">如需設定反惡意程式碼原則的詳細指示，請參閱 [在 EOP 中設定反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="01e66-163">For detailed instructions for configuring anti-malware policies, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a><span data-ttu-id="01e66-164">第2部分-EOP 和 Defender for Office 365 中的反網路釣魚防護</span><span class="sxs-lookup"><span data-stu-id="01e66-164">Part 2 - Anti-phishing protection in EOP and Defender for Office 365</span></span>

<span data-ttu-id="01e66-165">您可以在包含[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中取得[反網路釣魚防護](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="01e66-165">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="01e66-166">[Office 365 的 Defender](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中提供高級反網路釣魚防護。</span><span class="sxs-lookup"><span data-stu-id="01e66-166">Advanced anti-phishing protection is available in [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="01e66-167">如需有關反網路釣魚原則建議設定的詳細資訊，請參閱 EOP 的 Microsoft Defender 中的[反網路釣魚原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)和[反網路釣魚原則設定，以取得 Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="01e66-167">For more information about the recommended settings for anti-phishing policies, see [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) and [Anti-phishing policy settings in Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).</span></span>

<span data-ttu-id="01e66-168">下列程式說明如何設定預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="01e66-168">The following procedure describes how to configure the default anti-phishing policy.</span></span> <span data-ttu-id="01e66-169">Office 365 中只會有明確標示的設定。</span><span class="sxs-lookup"><span data-stu-id="01e66-169">Settings that are only available in Defender for Office 365 are clearly marked.</span></span>

1. <span data-ttu-id="01e66-170">在 Microsoft 365 Defender 入口網站中開啟 [**反網路釣魚**] 頁面，網址為 <https://security.microsoft.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="01e66-170">Open the **Anti-phishing** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/antiphishing>.</span></span>

2. <span data-ttu-id="01e66-171">在 [ **反網路釣魚** 網頁] 頁面上，選取名為 **Office365 AntiPhish default 的原則 (預設)** ，方法是按一下名稱。</span><span class="sxs-lookup"><span data-stu-id="01e66-171">On the **Anti-phishing** page, select the policy named **Office365 AntiPhish Default (Default)** by clicking on the name.</span></span>

3. <span data-ttu-id="01e66-172">在出現的 [原則詳細資料] 浮出視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-172">In the policy details flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="01e66-173">**網路釣魚閥值 & 保護** 區段：按一下 [ **編輯防護設定** ]，並在開啟的浮出控制項中設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-173">**Phishing threshold & protection** section: Click **Edit protection settings** and configure the following settings in the flyout that opens:</span></span>
     - <span data-ttu-id="01e66-174">**網路釣魚電子郵件閥值** <sup>\*</sup> ：選取 **2-嚴格** (標準) 或 **3 個** 嚴格 (嚴格) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-174">**Phishing email threshold**<sup>\*</sup>: Select **2 - Aggressive** (Standard) or **3 - More Aggressive** (Strict).</span></span>
     - <span data-ttu-id="01e66-175">**類比** 區段 <sup>\*</sup> ：設定下列值：</span><span class="sxs-lookup"><span data-stu-id="01e66-175">**Impersonation** section<sup>\*</sup>: Configure the following values:</span></span>
       - <span data-ttu-id="01e66-176">選取 [ **允許使用者進行保護**]，然後按一下所出現的 [ **管理 (nn) 寄件者 (])** 連結，然後新增內部和外部寄件者，以防止假冒，例如組織的董事會成員、CEO、CFO 和其他資深領導人。</span><span class="sxs-lookup"><span data-stu-id="01e66-176">Select **Enable users to protect**, click the **Manage (nn) sender(s)** link that appears, and then add internal and external senders to protect from impersonation, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span>
       - <span data-ttu-id="01e66-177">選取 [ **啟用要保護的網域**]，然後設定出現下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-177">Select **Enable domains to protect**, and then configure the following settings that appear:</span></span>
         - <span data-ttu-id="01e66-178">選取 [ **包含我擁有的網域** ]，以保護您公認的網域中的內部寄件者 (可見，請按一下 [ **View my** domain) 類比]。</span><span class="sxs-lookup"><span data-stu-id="01e66-178">Select **Include domains I own** to protect internal senders in your accepted domains (visible by clicking **View my domains**) from impersonation.</span></span>
         - <span data-ttu-id="01e66-179">若要保護其他網域中的寄件者，請選取 [ **包含自訂網域**]，然後按一下所出現的 [ **管理 (nn) 自訂網域 (])** 連結，然後新增其他網域，以防止假冒。</span><span class="sxs-lookup"><span data-stu-id="01e66-179">To protect senders in other domains, select **Include custom domains**, click the **Manage (nn) custom domain(s)** link that appears, and then add other domains to protect from impersonation.</span></span>
     - <span data-ttu-id="01e66-180">**新增信任的寄件者和網域** 區段 <sup>\*</sup> ：按一下 [ **管理 (nn) 信任的寄件者] (s) 和網域 ()** ，設定寄件者和寄件者網域例外狀況，以根據需要設定模擬保護</span><span class="sxs-lookup"><span data-stu-id="01e66-180">**Add trusted senders and domains** section <sup>\*</sup>: Click **Manage (nn) trusted sender(s) and domains(s)** to configure sender and sender domain exceptions to impersonation protection if needed.</span></span>
     - <span data-ttu-id="01e66-181">信箱智慧設定 <sup>\*</sup> ：確認已選取 [ **啟用信箱智慧** ] 和 [ **啟用類比保護的智慧** ]。</span><span class="sxs-lookup"><span data-stu-id="01e66-181">Mailbox intelligence settings <sup>\*</sup>: Verify that **Enable mailbox intelligence** and **Enable intelligence for impersonation protection** are selected.</span></span>
     - <span data-ttu-id="01e66-182">**哄騙** 區段：確認已選取 [ **啟用欺騙智慧** ]。</span><span class="sxs-lookup"><span data-stu-id="01e66-182">**Spoof** section: Verify **Enable spoof intelligence** is selected.</span></span>

     <span data-ttu-id="01e66-183">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="01e66-183">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="01e66-184">**動作** 區段：按一下 [ **編輯動作** ]，並在開啟的飛入視窗中設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-184">**Actions** section: Click **Edit actions** and configure the following settings in the flyout that opens:</span></span>
     - <span data-ttu-id="01e66-185">**郵件動作** 區段：設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-185">**Message actions** section: Configure the following settings:</span></span>
       - <span data-ttu-id="01e66-186">**如果偵測到郵件為模仿的使用者** <sup>\*</sup> ：選取 **[隔離郵件**]。</span><span class="sxs-lookup"><span data-stu-id="01e66-186">**If message is detected as an impersonated user**<sup>\*</sup>: Select **Quarantine the message**.</span></span>
       - <span data-ttu-id="01e66-187">**如果偵測到郵件為類比的網域** <sup>\*</sup> ：請選取 **[隔離郵件**]。</span><span class="sxs-lookup"><span data-stu-id="01e66-187">**If message is detected as an impersonated domain**<sup>\*</sup>: Select **Quarantine the message**.</span></span>
       - <span data-ttu-id="01e66-188">**如果信箱智慧偵測到模仿的使用者** <sup>\*</sup> ：選取 **[將郵件移至收件者的垃圾郵件資料夾**] (標準) 或 **隔離郵件** (Strict) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-188">**If mailbox intelligence detects an impersonated user**<sup>\*</sup>: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).</span></span>
       - <span data-ttu-id="01e66-189">**如果偵測到郵件為欺騙**：請選取 **[將郵件移至收件者的垃圾郵件資料夾** ] (標準) 或 **隔離郵件** (Strict) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-189">**If message is detected as spoof**: Select **Move message to the recipients' Junk Email folders** (Standard) or **Quarantine the message** (Strict).</span></span>
     - <span data-ttu-id="01e66-190">**安全性秘訣 & 指示** 區段：設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-190">**Safety tips & indicators** section: Configure the following settings:</span></span>
       - <span data-ttu-id="01e66-191">**顯示第一個連絡人安全提示**：選取 [ (開啟) ]。</span><span class="sxs-lookup"><span data-stu-id="01e66-191">**Show first contact safety tip**: Select (turn on).</span></span>
       - <span data-ttu-id="01e66-192">**顯示使用者模擬安全提示** <sup>\*</sup> ：選取 (開啟) ]。</span><span class="sxs-lookup"><span data-stu-id="01e66-192">**Show user impersonation safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="01e66-193">**顯示網域模擬安全提示** <sup>\*</sup> ：選取 (開啟) ]。</span><span class="sxs-lookup"><span data-stu-id="01e66-193">**Show domain impersonation safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="01e66-194">**顯示使用者模擬不尋常的字元安全提示** <sup>\*</sup> ：選取 (開啟) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-194">**Show user impersonation unusual characters safety tip**<sup>\*</sup>: Select (turn on).</span></span>
       - <span data-ttu-id="01e66-195">**顯示 (？ ) 以取得未驗證之寄件者的欺騙**：選取 (開啟) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-195">**Show (?) for unauthenticated senders for spoof**: Select (turn on).</span></span>
       - <span data-ttu-id="01e66-196">**顯示「透過」標記**：選取 (開啟) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-196">**Show "via" tag**: Select (turn on).</span></span>

     <span data-ttu-id="01e66-197">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="01e66-197">When you're finished, click **Save**.</span></span>

   <span data-ttu-id="01e66-198"><sup>\*</sup>此設定僅適用于 Office 365 的 Defender。</span><span class="sxs-lookup"><span data-stu-id="01e66-198"><sup>\*</sup> This setting is available only in Defender for Office 365.</span></span>

4. <span data-ttu-id="01e66-199">按一下 [**儲存**]，然後按一下 [**關閉**]</span><span class="sxs-lookup"><span data-stu-id="01e66-199">Click **Save** and then click **Close**</span></span>

<span data-ttu-id="01e66-200">如需設定反網路釣魚原則的詳細指示，請參閱[在 EOP 中設定反網路釣魚原則](configure-anti-phishing-policies-eop.md)及[設定 Microsoft Defender 中的反網路釣魚原則，以供 Office 365](configure-mdo-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="01e66-200">For detailed instructions for configuring anti-phishing policies, see [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) and [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection-in-eop"></a><span data-ttu-id="01e66-201">第3部分-EOP 中的反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="01e66-201">Part 3 - Anti-spam protection in EOP</span></span>

<span data-ttu-id="01e66-202">如需有關反垃圾郵件建議設定的詳細資訊，請參閱 [EOP 反垃圾郵件原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="01e66-202">For more information about the recommended settings for anti-spam, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

1. <span data-ttu-id="01e66-203">在 Microsoft 365 Defender 入口網站中開啟 **反垃圾郵件原則** 頁面，網址為 <https://security.microsoft.com/antispam> 。</span><span class="sxs-lookup"><span data-stu-id="01e66-203">Open the **Anti-spam policies** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="01e66-204">在 [ **反垃圾郵件原則** ] 頁面上，從清單中選取名稱為 [ **反垃圾郵件輸入原則 (預設)** ] 的原則。</span><span class="sxs-lookup"><span data-stu-id="01e66-204">On the **Anti-spam policies** page, select the policy named **Anti-spam inbound policy (Default)** from the list by clicking on the name.</span></span>

3. <span data-ttu-id="01e66-205">在出現的 [原則詳細資料] 浮出視窗中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-205">In the policy details flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="01e66-206">**大量電子郵件閾值 & 垃圾郵件屬性** ] 區段：按一下 [ **編輯垃圾郵件閾值和屬性**]。</span><span class="sxs-lookup"><span data-stu-id="01e66-206">**Bulk email threshold & spam properties** section: Click **Edit spam threshold and properties**.</span></span> <span data-ttu-id="01e66-207">在出現的浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-207">In the flyout that appears, configure the following settings:</span></span>
     - <span data-ttu-id="01e66-208">**大量電子郵件閥** 值：將此值設為 5 (Strict) 或 6 (Standard) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-208">**Bulk email threshold**: Set this value to 5 (Strict) or 6 (Standard).</span></span>
     - <span data-ttu-id="01e66-209">保留其他設定的預設值 (**Off** 或 **None**) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-209">Leave other settings at their default values (**Off** or **None**).</span></span>

     <span data-ttu-id="01e66-210">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="01e66-210">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="01e66-211">**動作** 區段：按一下 [ **編輯動作**]。</span><span class="sxs-lookup"><span data-stu-id="01e66-211">**Actions** section: Click **Edit actions**.</span></span> <span data-ttu-id="01e66-212">在出現的浮出控制項中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-212">In the flyout that appears, configure the following settings:</span></span>
     - <span data-ttu-id="01e66-213">**郵件動作** 區段：</span><span class="sxs-lookup"><span data-stu-id="01e66-213">**Message actions** section:</span></span>
       - <span data-ttu-id="01e66-214">**垃圾郵件**：確認已選取 [ **將郵件移至垃圾郵件資料夾** ] (標準) 或選取 [ **隔離郵件** (Strict) ]。</span><span class="sxs-lookup"><span data-stu-id="01e66-214">**Spam**: Verify **Move message to Junk Email folder** is selected (Standard) or select **Quarantine message** (Strict).</span></span>
       - <span data-ttu-id="01e66-215">**高度信賴的垃圾郵件**：選取 **隔離郵件**。</span><span class="sxs-lookup"><span data-stu-id="01e66-215">**High confidence spam**: Select **Quarantine message**.</span></span>
       - <span data-ttu-id="01e66-216">**網路釣魚**：選取 **隔離郵件**。</span><span class="sxs-lookup"><span data-stu-id="01e66-216">**Phishing**:  Select **Quarantine message**.</span></span>
       - <span data-ttu-id="01e66-217">**高信賴網路釣魚**：確認已選取 **隔離郵件** 。</span><span class="sxs-lookup"><span data-stu-id="01e66-217">**High confidence phishing**: Verify **Quarantine messages** is selected.</span></span>
       - <span data-ttu-id="01e66-218">**大量**：確認已選取 [ **將郵件移至垃圾郵件資料夾** ] (標準) 或選取 [ **隔離郵件** (Strict) ]。</span><span class="sxs-lookup"><span data-stu-id="01e66-218">**Bulk**: Verify **Move message to Junk Email folder** is selected (Standard) or select **Quarantine message** (Strict).</span></span>
     - <span data-ttu-id="01e66-219">**在隔離期間保留這數天的垃圾郵件**：確認 **30** 天的值。</span><span class="sxs-lookup"><span data-stu-id="01e66-219">**Retain spam in quarantine for this many days**: Verify the value **30** days.</span></span>
     - <span data-ttu-id="01e66-220">**啟用垃圾郵件安全提示**：確認已選取此設定 (開啟) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-220">**Enable spam safety tips**: Verify this setting is selected (turned on).</span></span>
     - <span data-ttu-id="01e66-221">**啟用以零小時自動清除 (ZAP)**：確認已選取此設定 (開啟) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-221">**Enable zero-hour auto purge (ZAP)**: Verify this setting is selected (turned on).</span></span>
       - <span data-ttu-id="01e66-222">**啟用網路釣魚郵件**：確認已選取此設定 (開啟) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-222">**Enable for phishing messages**: Verify this setting is selected (turned on).</span></span> <span data-ttu-id="01e66-223">如需詳細資訊，請參閱 [零小時自動清除 (用於網路釣魚的 ZAP) ](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing)。</span><span class="sxs-lookup"><span data-stu-id="01e66-223">For more information, see [Zero-hour auto purge (ZAP) for phishing](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing).</span></span>
       - <span data-ttu-id="01e66-224">**啟用垃圾郵件訊息**：確認已選取此設定 (開啟) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-224">**Enable for spam messages**:  Verify this setting is selected (turned on).</span></span> <span data-ttu-id="01e66-225">如需詳細資訊，請參閱 [零小時自動清除 (用於垃圾郵件的 ZAP) ](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam)。</span><span class="sxs-lookup"><span data-stu-id="01e66-225">For more information, see [Zero-hour auto purge (ZAP) for spam](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam).</span></span>
     - <span data-ttu-id="01e66-226">**通知** 區段：</span><span class="sxs-lookup"><span data-stu-id="01e66-226">**Notifications** section:</span></span>
       - <span data-ttu-id="01e66-227">選取 [ **啟用使用者垃圾郵件通知**]。</span><span class="sxs-lookup"><span data-stu-id="01e66-227">Select **Enable end-user spam notifications**.</span></span>
         - <span data-ttu-id="01e66-228">**每 (天) 傳送一次使用者垃圾郵件通知**：確認 **3** 天的值。</span><span class="sxs-lookup"><span data-stu-id="01e66-228">**Send end-user spam notifications every (days)**: Verify the value **3** days.</span></span>
         - <span data-ttu-id="01e66-229">**語言**：確認值為 [ **預設** 值] 或 [選取語言]。</span><span class="sxs-lookup"><span data-stu-id="01e66-229">**Language**: Verify the value **Default** or select a language.</span></span>

     <span data-ttu-id="01e66-230">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="01e66-230">When you're finished, click **Save**.</span></span>

   - <span data-ttu-id="01e66-231">**允許與封鎖的寄件者和網域** 區段：如 EOP 中的 [ [建立封鎖的寄件者清單](create-block-sender-lists-in-office-365.md) ] 或 [ [在 EOP 中建立安全的寄件者清單](create-safe-sender-lists-in-office-365.md)] 中所述，查看或編輯允許的</span><span class="sxs-lookup"><span data-stu-id="01e66-231">**Allowed and blocked senders and domains** section: Review or edit your allowed senders and allowed domains as described in [Create blocked sender lists in EOP](create-block-sender-lists-in-office-365.md) or [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

     <span data-ttu-id="01e66-232">完成後，按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="01e66-232">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="01e66-233">完成時，請按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="01e66-233">When you're finished, click **Close**.</span></span>

<span data-ttu-id="01e66-234">如需設定反垃圾郵件原則的詳細指示，請參閱 [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="01e66-234">For detailed instructions for configuring anti-spam policies, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a><span data-ttu-id="01e66-235">第4部分-從惡意 URLs 和檔案 (在 Office 365 的 Defender 中保管庫連結及保管庫附件進行防護) </span><span class="sxs-lookup"><span data-stu-id="01e66-235">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Defender for Office 365)</span></span>

<span data-ttu-id="01e66-236">在包含[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)的訂閱中，可使用從惡意 URLs 和檔案進行時間的防護。</span><span class="sxs-lookup"><span data-stu-id="01e66-236">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="01e66-237">它是透過[保管庫附件](safe-attachments.md)和[保管庫連結](safe-links.md)原則進行設定。</span><span class="sxs-lookup"><span data-stu-id="01e66-237">It's set up through [Safe Attachments](safe-attachments.md) and [Safe Links](safe-links.md) policies.</span></span>

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="01e66-238">保管庫Microsoft Defender 中 Office 365 的附件原則</span><span class="sxs-lookup"><span data-stu-id="01e66-238">Safe Attachments policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="01e66-239">如需保管庫附件建議設定的詳細資訊，請參閱。[保管庫附件設定](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="01e66-239">For more information about the recommended settings for Safe Attachments, see .[Safe Attachments settings](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).</span></span>

1. <span data-ttu-id="01e66-240">開啟 Microsoft 365 Defender 入口網站中的 [**保管庫附件**] 頁面，網址為 <https://security.microsoft.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="01e66-240">Open the **Safe Attachments** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/safeattachmentv2>.</span></span>

2. <span data-ttu-id="01e66-241">在 [**保管庫附件**] 頁面上，按一下 [**通用設定**]，然後在出現的快顯視窗上設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-241">On the **Safe Attachments** page, click **Global settings**, and then configure the following settings on the flyout that appears:</span></span>
   - <span data-ttu-id="01e66-242">**針對 SharePoint、OneDrive 及 Microsoft Teams 開啟 Office 365 的 Defender**：開啟此設定， (上的 [開啟] ![ ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-242">**Turn on Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams**: Turn on this setting (![Toggle on](../../media/scc-toggle-on.png)).</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="01e66-243">在 **您開啟 SharePoint、OneDrive 及 Microsoft Teams 的保管庫附件之前，請確認已開啟組織中的審計記錄**。</span><span class="sxs-lookup"><span data-stu-id="01e66-243">**Before you turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams, verify that audit logging is turned in your organization**.</span></span> <span data-ttu-id="01e66-244">此項動作通常是由已在 Exchange Online 中指派「審計記錄」角色的人員所執行。</span><span class="sxs-lookup"><span data-stu-id="01e66-244">This action is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="01e66-245">如需詳細資訊，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)！</span><span class="sxs-lookup"><span data-stu-id="01e66-245">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

   - <span data-ttu-id="01e66-246">**開啟 Office 用戶端的保管庫檔**：開啟此設定 (![ 開啟 ](../../media/scc-toggle-on.png)) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-246">**Turn on Safe Documents for Office clients**: Turn on this setting (![Toggle on](../../media/scc-toggle-on.png)).</span></span> <span data-ttu-id="01e66-247">請注意，這項功能只有 Microsoft 365 E5 或 Microsoft 365 E5 安全性授權才能使用且有意義。</span><span class="sxs-lookup"><span data-stu-id="01e66-247">Note that this feature is available and meaningful only with Microsoft 365 E5 or Microsoft 365 E5 Security licenses.</span></span>
   - <span data-ttu-id="01e66-248">**即使保管庫檔識別為惡意的檔案，也可讓使用者依序按一下 [受保護的檢視**]：確認已關閉此設定 (![) 關閉] ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-248">**Allow people to click through Protected View even if Safe Documents identified the file as malicious**: Verify this setting is turned off (![Toggle off](../../media/scc-toggle-off.png)).</span></span>

   <span data-ttu-id="01e66-249">完成後，請按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="01e66-249">When you're finished, click **Save**</span></span>

3. <span data-ttu-id="01e66-250">回到 [**保管庫附件**] 頁面上，按一下 [ ![ 建立圖示] ](../../media/m365-cc-sc-create-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-250">Back on the **Safe Attachments** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png).</span></span>

4. <span data-ttu-id="01e66-251">在開啟的 [**建立保管庫附件原則**] 嚮導中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-251">In the **Create Safe Attachments policy** wizard that opens, configure the following settings:</span></span>
   - <span data-ttu-id="01e66-252">[**命名您的原則**] 頁面：</span><span class="sxs-lookup"><span data-stu-id="01e66-252">**Name your policy** page:</span></span>
     - <span data-ttu-id="01e66-253">**名稱**：輸入一些獨特且具描述性的描述。</span><span class="sxs-lookup"><span data-stu-id="01e66-253">**Name**: Enter something unique and descriptive.</span></span>
     - <span data-ttu-id="01e66-254">**描述**：輸入選擇性描述。</span><span class="sxs-lookup"><span data-stu-id="01e66-254">**Description**: Enter an optional description.</span></span>
   - <span data-ttu-id="01e66-255">[**使用者和網域**] 頁面：由於這是您的第一個原則，您可能想要最大化覆蓋範圍，請考慮在 [**網域**] 方塊中輸入 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="01e66-255">**Users and domains** page: Because this is your first policy and you likely want to maximize coverage, consider entering your [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in the **Domains** box.</span></span> <span data-ttu-id="01e66-256">否則，您可以使用 [ **使用者** 和 **群組** ] 方塊，以進行更精細的控制。</span><span class="sxs-lookup"><span data-stu-id="01e66-256">Otherwise, you can use the **Users** and **Groups** boxes for more granular control.</span></span> <span data-ttu-id="01e66-257">您可以選取 [ **排除這些使用者、群組和網域** ]，並輸入值，以指定例外狀況。</span><span class="sxs-lookup"><span data-stu-id="01e66-257">You can specify exceptions by selecting **Exclude these users, groups, and domains** and entering values.</span></span>
   - <span data-ttu-id="01e66-258">**設定** 頁面：</span><span class="sxs-lookup"><span data-stu-id="01e66-258">**Settings** page:</span></span>
     - <span data-ttu-id="01e66-259">**保管庫附件未知的惡意程式碼回應**： Select **Block**。</span><span class="sxs-lookup"><span data-stu-id="01e66-259">**Safe Attachments unknown malware response**: Select **Block**.</span></span>
     - <span data-ttu-id="01e66-260">**以偵測到的附件重新導向附件** ： **Enable 重新導向**：開啟此設定 (選取) 並輸入電子郵件地址來接收偵測到的郵件。</span><span class="sxs-lookup"><span data-stu-id="01e66-260">**Redirect attachment with detected attachments** : **Enable redirect**: Turn this setting on (select) and enter an email address to receive detected messages.</span></span>
     - <span data-ttu-id="01e66-261">**如果掃描無法完成 (超時或錯誤，請套用保管庫附件偵測回應)**：確認已選取此設定。</span><span class="sxs-lookup"><span data-stu-id="01e66-261">**Apply the Safe Attachments detection response if scanning can't complete (timeout or errors)**: Verify this setting is selected.</span></span>

5. <span data-ttu-id="01e66-262">完成後，請按一下 [ **提交**]，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="01e66-262">When you're finished, click **Submit**, and then click **Done**.</span></span>

6. <span data-ttu-id="01e66-263"> (建議) 成為全域系統管理員或 SharePoint online 管理員，請執行 **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** Cmdlet，並將 _DisallowInfectedFileDownload_ 參數設定為 `$true` SharePoint 線上 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="01e66-263">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true` in SharePoint Online PowerShell.</span></span>
   - <span data-ttu-id="01e66-264">`$true` 封鎖針對偵測到的檔案 (刪除) 以外的所有動作。</span><span class="sxs-lookup"><span data-stu-id="01e66-264">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="01e66-265">使用者無法開啟、移動、複製或共用偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="01e66-265">People can't open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="01e66-266">`$false` 封鎖除 Delete 和下載中心以外的所有動作。</span><span class="sxs-lookup"><span data-stu-id="01e66-266">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="01e66-267">使用者可以選擇接受風險並下載偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="01e66-267">People can choose to accept the risk and download a detected file.</span></span>

7. <span data-ttu-id="01e66-268">允許最多30分鐘的變更，以散佈至所有的 Microsoft 365 資料中心。</span><span class="sxs-lookup"><span data-stu-id="01e66-268">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

<span data-ttu-id="01e66-269">如需設定保管庫附件的保管庫附件原則及全域設定的詳細指示，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="01e66-269">For detailed instructions for configuring Safe Attachments policies and global settings for Safe Attachments, see the following topics:</span></span>

- [<span data-ttu-id="01e66-270">在 Microsoft Defender 中設定 Office 365 的保管庫附件原則</span><span class="sxs-lookup"><span data-stu-id="01e66-270">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>](set-up-safe-attachments-policies.md)
- [<span data-ttu-id="01e66-271">開啟適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件</span><span class="sxs-lookup"><span data-stu-id="01e66-271">Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="01e66-272">Microsoft 365 E5 中的安全文件</span><span class="sxs-lookup"><span data-stu-id="01e66-272">Safe Documents in Microsoft 365 E5</span></span>](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="01e66-273">保管庫Microsoft Defender 中 Office 365 的連結原則</span><span class="sxs-lookup"><span data-stu-id="01e66-273">Safe Links policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="01e66-274">如需保管庫連結之建議設定的詳細資訊，請參閱[保管庫連結設定](recommended-settings-for-eop-and-office365.md#safe-links-settings)。</span><span class="sxs-lookup"><span data-stu-id="01e66-274">For more information about the recommended settings for Safe Links, see [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).</span></span>

1. <span data-ttu-id="01e66-275">開啟 Microsoft 365 Defender 入口網站中的 [**保管庫連結**] 頁面，網址為 <https://security.microsoft.com/safelinksv2> 。</span><span class="sxs-lookup"><span data-stu-id="01e66-275">Open the **Safe Links** page in the Microsoft 365 Defender portal at <https://security.microsoft.com/safelinksv2>.</span></span>

2. <span data-ttu-id="01e66-276">在 [**保管庫連結**] 頁面上，按一下 [**通用設定**]，然後在出現的快顯視窗上設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-276">On the **Safe Links** page, click **Global settings**, and then configure the following settings on the flyout that appears:</span></span>
   - <span data-ttu-id="01e66-277">**適用于支援的 Office 365 應用程式區段中的內容的設定**：</span><span class="sxs-lookup"><span data-stu-id="01e66-277">**Settings that apply to content in supported Office 365 apps** section:</span></span>
     - <span data-ttu-id="01e66-278">**使用 Office 365 應用程式中的保管庫連結**：確認此設定已開啟 (![) 上的 [切換] ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-278">**Use Safe Links in Office 365 apps**: Verify this setting is turned on (![Toggle on](../../media/scc-toggle-on.png)).</span></span>
     - <span data-ttu-id="01e66-279">**當使用者在 Office 365 應用程式中按一下受保護連結時，請勿追蹤**：關閉此設定 (![) 關閉] ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-279">**Do not track when users click protected links in Office 365 apps**: Turn this setting off (![Toggle off](../../media/scc-toggle-off.png)).</span></span>
     - <span data-ttu-id="01e66-280">**請勿讓使用者在 Office 365 應用程式中按原始 URL**：確認此設定已開啟 ![) 上 (開啟] ](../../media/scc-toggle-on.png) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-280">**Do not let users click through to the original URL in Office 365 apps**: Verify this setting is turned on (![Toggle on](../../media/scc-toggle-on.png)).</span></span>

   <span data-ttu-id="01e66-281">完成後，請按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="01e66-281">When you're finished, click **Save**</span></span>

3. <span data-ttu-id="01e66-282">回到 [**保管庫連結**] 頁面上，按一下 [ ![ 建立圖示] ](../../media/m365-cc-sc-create-icon.png) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-282">Back on the **Safe Links** page, click ![Create icon](../../media/m365-cc-sc-create-icon.png).</span></span>

4. <span data-ttu-id="01e66-283">在開啟的 [**建立保管庫連結原則**] 嚮導中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-283">In the **Create Safe Links policy** wizard that opens, configure the following settings:</span></span>
   - <span data-ttu-id="01e66-284">[**命名您的原則**] 頁面：</span><span class="sxs-lookup"><span data-stu-id="01e66-284">**Name your policy** page:</span></span>
     - <span data-ttu-id="01e66-285">**名稱**：輸入一些獨特且具描述性的描述。</span><span class="sxs-lookup"><span data-stu-id="01e66-285">**Name**: Enter something unique and descriptive.</span></span>
     - <span data-ttu-id="01e66-286">**描述**：輸入選擇性描述。</span><span class="sxs-lookup"><span data-stu-id="01e66-286">**Description**: Enter an optional description.</span></span>
   - <span data-ttu-id="01e66-287">[**使用者和網域**] 頁面：由於這是您的第一個原則，您可能想要最大化覆蓋範圍，請考慮在 [**網域**] 方塊中輸入 [公認的網域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。</span><span class="sxs-lookup"><span data-stu-id="01e66-287">**Users and domains** page: Because this is your first policy and you likely want to maximize coverage, consider entering your [accepted domains](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in the **Domains** box.</span></span> <span data-ttu-id="01e66-288">否則，您可以使用 [ **使用者** 和 **群組** ] 方塊，以進行更精細的控制。</span><span class="sxs-lookup"><span data-stu-id="01e66-288">Otherwise, you can use the **Users** and **Groups** boxes for more granular control.</span></span> <span data-ttu-id="01e66-289">您可以選取 [ **排除這些使用者、群組和網域** ]，並輸入值，以指定例外狀況。</span><span class="sxs-lookup"><span data-stu-id="01e66-289">You can specify exceptions by selecting **Exclude these users, groups, and domains** and entering values.</span></span>
   - <span data-ttu-id="01e66-290">[**保護設定**] 頁面：</span><span class="sxs-lookup"><span data-stu-id="01e66-290">**Protection settings** page:</span></span>
     - <span data-ttu-id="01e66-291">**在郵件中選取未知可能惡意 URLs 的動作** **：開啟此設定。**</span><span class="sxs-lookup"><span data-stu-id="01e66-291">**Select the action for unknown potentially malicious URLs in messages**: Turn this setting **On**.</span></span>
     - <span data-ttu-id="01e66-292">**選取 Microsoft Teams 內未知或可能惡意 URLs 的動作** **：開啟此設定。**</span><span class="sxs-lookup"><span data-stu-id="01e66-292">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Turn this setting **On**.</span></span> <span data-ttu-id="01e66-293">從3月2020起，此設定是在預覽中，且僅適用 Microsoft Teams 技術採用計畫的成員 (點擊) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-293">As of March 2020, this setting is in Preview and is available or functional only for members of the Microsoft Teams Technology Adoption Program (TAP).</span></span>
     - <span data-ttu-id="01e66-294">**對指向檔案的可疑連結和連結套用即時 URL 掃描**：選取此設定 (開啟) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-294">**Apply real-time URL scanning for suspicious links and links that point to files**: Select this setting (turn on).</span></span>
       - <span data-ttu-id="01e66-295">**等候 URL 掃描完成後傳遞郵件**：選取此設定 (開啟) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-295">**Wait for URL scanning to complete before delivering the message**: Select this setting (turn on).</span></span>
     - <span data-ttu-id="01e66-296">套用 **保管庫連結至組織內傳送的電子郵件**：選取此設定 (開啟) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-296">**Apply Safe Links to email messages sent within the organization**: Select this setting (turn on).</span></span>
     - <span data-ttu-id="01e66-297">**請勿追蹤使用者點擊**：請確認未選取此設定 (關閉) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-297">**Do not track user clicks**: Verify this setting is not selected (turned off).</span></span>
     - <span data-ttu-id="01e66-298">**請勿讓使用者依序按一下原始 URL**：確認此設定已開啟選取的)  (。</span><span class="sxs-lookup"><span data-stu-id="01e66-298">**Do not let users click through to the original URL**: Verify this setting is turned on (selected).</span></span>
     - <span data-ttu-id="01e66-299">**在通知和警告頁面上顯示組織商標**：選取此設定 (會在您已遵循 [自訂群組織的 Microsoft 365 主題](../../admin/setup/customize-your-organization-theme.md)，以上傳公司徽標之後，才將其開啟) 。</span><span class="sxs-lookup"><span data-stu-id="01e66-299">**Display the organization branding on notification and warning pages**: Selecting this setting (turning it on) is meaningful only after you've followed the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your company logo.</span></span>
     - <span data-ttu-id="01e66-300">**請勿重新寫入下列 URLs**：我們沒有此設定的特別建議。</span><span class="sxs-lookup"><span data-stu-id="01e66-300">**Do not rewrite the following URLs**: We have no specific recommendation for this setting.</span></span> <span data-ttu-id="01e66-301">如需詳細資訊，請參閱[保管庫連結原則中的「不要重新寫入下列 URLs」清單](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)。</span><span class="sxs-lookup"><span data-stu-id="01e66-301">For more information, see ["Do not rewrite the following URLs" lists in Safe Links policies](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies).</span></span>
   - <span data-ttu-id="01e66-302">**通知** 頁面：</span><span class="sxs-lookup"><span data-stu-id="01e66-302">**Notification** page:</span></span>
     - <span data-ttu-id="01e66-303">**您要如何通知使用者？** 區段：您也可以選取 [ **使用自訂通知文字** ] 來輸入要使用的自訂通知文字。</span><span class="sxs-lookup"><span data-stu-id="01e66-303">**How would you like to notify users?** section: Optionally, you can select **Use custom notification text** to enter customized notification text to use.</span></span> <span data-ttu-id="01e66-304">您也可以選取 [**使用 Microsoft 翻譯工具以進行自動當地語系化**，將自訂通知文字轉譯為使用者語言。</span><span class="sxs-lookup"><span data-stu-id="01e66-304">You can also select **Use Microsoft Translator for automatic localization** to translate the custom notification text into the user's language.</span></span> <span data-ttu-id="01e66-305">否則，請選取 **[使用預設的通知文字** ]。</span><span class="sxs-lookup"><span data-stu-id="01e66-305">Otherwise, leave **Use the default notification text** selected.</span></span>

5. <span data-ttu-id="01e66-306">完成後，請按一下 [ **提交**]，然後按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="01e66-306">When you're finished, click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="01e66-307">如需設定保管庫連結的保管庫連結原則及全域設定的詳細指示，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="01e66-307">For detailed instructions for configuring Safe Links policies and global settings for Safe Links, see the following topics:</span></span>

- [<span data-ttu-id="01e66-308">在 Microsoft Defender 中設定 Office 365 的保管庫連結原則</span><span class="sxs-lookup"><span data-stu-id="01e66-308">Set up Safe Links policies in Microsoft Defender for Office 365</span></span>](set-up-safe-links-policies.md)
- [<span data-ttu-id="01e66-309">針對 Office 365 設定 Microsoft Defender 中保管庫連結的全域設定</span><span class="sxs-lookup"><span data-stu-id="01e66-309">Configure global settings for Safe Links in Microsoft Defender for Office 365</span></span>](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a><span data-ttu-id="01e66-310">現在在 SharePoint Online 或商務用 OneDrive 中設定偵測到檔案的警示</span><span class="sxs-lookup"><span data-stu-id="01e66-310">Now set up alerts for detected files in SharePoint Online or OneDrive for Business</span></span>

<span data-ttu-id="01e66-311">若要在 SharePoint Online 中的檔案或商務用 OneDrive 識別為惡意的檔案時收到通知，您可以依照本節所述來設定警示。</span><span class="sxs-lookup"><span data-stu-id="01e66-311">To receive notification when a file in SharePoint Online or OneDrive for Business has been identified as malicious, you can set up an alert as described in this section.</span></span>

1. <span data-ttu-id="01e66-312">在 Microsoft 365 Defender 入口網站上 <https://security.microsoft.com> ，移至 **電子郵件 &** 共同作業原則 \> **& 規則** \> **警示原則**。</span><span class="sxs-lookup"><span data-stu-id="01e66-312">In the Microsoft 365 Defender portal at <https://security.microsoft.com>, go to **Email & collaboration** \> **Polices & rules** \> **Alert policy**.</span></span>

2. <span data-ttu-id="01e66-313">在 [ **警示原則** ] 頁面上，按一下 [ **新增警示原則**]。</span><span class="sxs-lookup"><span data-stu-id="01e66-313">On the **Alert policy** page, click **New alert policy**.</span></span>

3. <span data-ttu-id="01e66-314">[ **新增警示原則** ] 嚮導隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="01e66-314">The **New alert policy** wizard opens.</span></span> <span data-ttu-id="01e66-315">在 [ **名稱** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-315">On the **Name** page, configure the following settings:</span></span>
   - <span data-ttu-id="01e66-316">**名稱**：輸入唯一且具描述性的名稱。</span><span class="sxs-lookup"><span data-stu-id="01e66-316">**Name**: Enter a unique and descriptive name.</span></span> <span data-ttu-id="01e66-317">例如，您可以輸入「程式庫中的惡意檔案」。</span><span class="sxs-lookup"><span data-stu-id="01e66-317">For example, you could type Malicious Files in Libraries.</span></span>
   - <span data-ttu-id="01e66-318">**描述**：輸入選擇性描述。</span><span class="sxs-lookup"><span data-stu-id="01e66-318">**Description**: Enter an optional description.</span></span>
   - <span data-ttu-id="01e66-319">**嚴重性**：選取 [ **低**]、[ **中** ] 或 [ **高**]。</span><span class="sxs-lookup"><span data-stu-id="01e66-319">**Severity**: Select **Low**, **Medium** or **High**.</span></span>
   - <span data-ttu-id="01e66-320">**類別**：選取 **威脅管理**。</span><span class="sxs-lookup"><span data-stu-id="01e66-320">**Category**: Select **Threat management**.</span></span>

   <span data-ttu-id="01e66-321">完成後，請按 **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="01e66-321">When you're finished, click **Next**</span></span>

4. <span data-ttu-id="01e66-322">在 [ **建立警示設定** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-322">On the **Create alert settings** page, configure the following settings:</span></span>
   - <span data-ttu-id="01e66-323">**您想要提醒什麼？** section： **活動** 偵測 \> **到檔中的惡意** 代碼。</span><span class="sxs-lookup"><span data-stu-id="01e66-323">**What do you want to alert on?** section: **Activity is** \> **Detected malware in file**.</span></span>
   - <span data-ttu-id="01e66-324">**您要如何觸發提醒** ] 區段： **每次活動符合規則** 時請驗證。</span><span class="sxs-lookup"><span data-stu-id="01e66-324">**How do you want the alert to be triggered** section: Verify **Every time an activity matches the rule** is selected.</span></span>

   <span data-ttu-id="01e66-325">完成後，請按 **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="01e66-325">When you're finished, click **Next**</span></span>

5. <span data-ttu-id="01e66-326">在 [ **設定您** 的收件者] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="01e66-326">On the **Set your recipients** page, configure the following settings:</span></span>
   - <span data-ttu-id="01e66-327">**傳送電子郵件通知**：請確認此設定為 selcted。</span><span class="sxs-lookup"><span data-stu-id="01e66-327">**Send email notifications**: Verify this setting is selcted.</span></span>
   - <span data-ttu-id="01e66-328">**電子郵件** 收件者：選取一或多個全域管理員、安全性管理員或安全性讀者，當偵測到惡意檔案時，應該會收到通知。</span><span class="sxs-lookup"><span data-stu-id="01e66-328">**Email recipients**: Select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>
   - <span data-ttu-id="01e66-329">**每日通知限制**：請確認 **未選取限制** 。</span><span class="sxs-lookup"><span data-stu-id="01e66-329">**Daily notification limit**: Verify **No limit** is selected.</span></span>

   <span data-ttu-id="01e66-330">完成後，請按 **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="01e66-330">When you're finished, click **Next**</span></span>

6. <span data-ttu-id="01e66-331">在 [ **複查您的設定** ] 頁面上，複查您的設定，並確認 **[是]，已選取 [立即開啟** ]，然後按一下 **[完成]**</span><span class="sxs-lookup"><span data-stu-id="01e66-331">On the **Review your settings** page, review your settings, verify **Yes, turn it on right away** is selected, and then click **Finish**</span></span>

<span data-ttu-id="01e66-332">若要深入瞭解警示原則，請參閱[Microsoft 365 合規性中心中的警示原則](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="01e66-332">To learn more about alert policies, see [Alert policies in the Microsoft 365 compliance center](../../compliance/alert-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="01e66-333">當您完成設定時，請使用下列連結來開始工作負載調查：</span><span class="sxs-lookup"><span data-stu-id="01e66-333">When you're finished configuring, use these links to start workload investigations:</span></span>
>
>- [<span data-ttu-id="01e66-334">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="01e66-334">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
>- [<span data-ttu-id="01e66-335">使用 Microsoft 365 Defender 入口網站管理 Defender 中的隔離檔案 Office 365</span><span class="sxs-lookup"><span data-stu-id="01e66-335">Use the Microsoft 365 Defender portal to manage quarantined files in Defender for Office 365</span></span>](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [<span data-ttu-id="01e66-336">在 SharePoint 線上、OneDrive 或 Microsoft Teams 中找到惡意檔案時要執行的動作</span><span class="sxs-lookup"><span data-stu-id="01e66-336">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="01e66-337">在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="01e66-337">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="01e66-338">安裝後的工作及後續步驟</span><span class="sxs-lookup"><span data-stu-id="01e66-338">Post-setup tasks and next steps</span></span>

<span data-ttu-id="01e66-339">設定威脅防護功能之後，請務必監視這些功能的運作方式！</span><span class="sxs-lookup"><span data-stu-id="01e66-339">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="01e66-340">複查和修訂您的原則，讓他們能執行您所需的工作。</span><span class="sxs-lookup"><span data-stu-id="01e66-340">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="01e66-341">此外，請留意可增加價值的新功能和服務更新。</span><span class="sxs-lookup"><span data-stu-id="01e66-341">Also, watch for new features and service updates that can add value.</span></span>

<br>

****

|<span data-ttu-id="01e66-342">處理方式</span><span class="sxs-lookup"><span data-stu-id="01e66-342">What to do</span></span>|<span data-ttu-id="01e66-343">可深入了解的資源</span><span class="sxs-lookup"><span data-stu-id="01e66-343">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="01e66-344">查看您的組織如何使用威脅防護功能，以查看報告</span><span class="sxs-lookup"><span data-stu-id="01e66-344">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="01e66-345">電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="01e66-345">Email security reports</span></span>](view-email-security-reports.md) <p> [<span data-ttu-id="01e66-346">Microsoft Defender for Office 365 報告</span><span class="sxs-lookup"><span data-stu-id="01e66-346">Reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md) <p> [<span data-ttu-id="01e66-347">威脅總管</span><span class="sxs-lookup"><span data-stu-id="01e66-347">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="01e66-348">視需要定期複查和修正威脅防護原則</span><span class="sxs-lookup"><span data-stu-id="01e66-348">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="01e66-349">安全分數</span><span class="sxs-lookup"><span data-stu-id="01e66-349">Secure Score</span></span>](../defender/microsoft-secure-score.md) <p> [<span data-ttu-id="01e66-350">Microsoft 365 威脅調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="01e66-350">Microsoft 365 threat investigation and response features</span></span>](./office-365-ti.md)|
|<span data-ttu-id="01e66-351">監視新功能和服務更新</span><span class="sxs-lookup"><span data-stu-id="01e66-351">Watch for new features and service updates</span></span>|[<span data-ttu-id="01e66-352">標準及目標發行選項</span><span class="sxs-lookup"><span data-stu-id="01e66-352">Standard and Targeted release options</span></span>](../../admin/manage/release-options-in-office-365.md) <p> [<span data-ttu-id="01e66-353">訊息中心</span><span class="sxs-lookup"><span data-stu-id="01e66-353">Message Center</span></span>](../../admin/manage/message-center.md) <p> [<span data-ttu-id="01e66-354">Microsoft 365 藍圖</span><span class="sxs-lookup"><span data-stu-id="01e66-354">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [<span data-ttu-id="01e66-355">服務說明</span><span class="sxs-lookup"><span data-stu-id="01e66-355">Service Descriptions</span></span>](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
