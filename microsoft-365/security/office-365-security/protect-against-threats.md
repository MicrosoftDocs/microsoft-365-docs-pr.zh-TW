---
title: 防範威脅
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 系統管理員可以深入瞭解 Microsoft 365 中的威脅防護，並設定如何將它用於您的組織。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 646fff4550de2e07342c0fef04952846db65a8eb
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615117"
---
# <a name="protect-against-threats"></a><span data-ttu-id="81c76-103">防範威脅</span><span class="sxs-lookup"><span data-stu-id="81c76-103">Protect against threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="81c76-104">以下是將 Office 365 的 Defender 設定分解成區塊的快速入門手冊。</span><span class="sxs-lookup"><span data-stu-id="81c76-104">Here's a quick-start guide that breaks the configuration of Defender for Office 365 into chunks.</span></span> <span data-ttu-id="81c76-105">如果您是 Office 365 中威脅防護功能的新功能，請不要確定開始的位置，或者，如果您想要 *這麼做*，請使用本指導方針做為檢查清單和開始點。</span><span class="sxs-lookup"><span data-stu-id="81c76-105">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81c76-106">**每種原則都包含初始建議設定，但有許多選項可供使用，您可以調整設定，以符合特定組織的需求**。</span><span class="sxs-lookup"><span data-stu-id="81c76-106">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="81c76-107">允許大約30分鐘的原則或變更以透過您的資料中心來運作。</span><span class="sxs-lookup"><span data-stu-id="81c76-107">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="81c76-108">需求</span><span class="sxs-lookup"><span data-stu-id="81c76-108">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="81c76-109">訂閱</span><span class="sxs-lookup"><span data-stu-id="81c76-109">Subscriptions</span></span>

<span data-ttu-id="81c76-110">威脅防護功能包含在 *所有* Microsoft 或 Office 365 訂閱中;不過，有些訂閱具有高級功能。</span><span class="sxs-lookup"><span data-stu-id="81c76-110">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="81c76-111">下表列出本文所含的保護功能及最低訂閱需求。</span><span class="sxs-lookup"><span data-stu-id="81c76-111">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="81c76-112">請注意，除了開啟審計的指示 *之外，還會啟動反* 惡意程式碼、反網路釣魚和反垃圾郵件，並標示為 Office 365 Exchange Online Protection (**EOP**) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="81c76-112">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="81c76-113">這在 Office 365 文章中看起來會是奇怪的，直到您記得 (**Defender For office 365**) 包含]，並建立在 EOP 上。</span><span class="sxs-lookup"><span data-stu-id="81c76-113">This can seem odd in an Defender for Office 365 article, until you remember (**Defender for Office 365**) contains, and builds on, EOP.</span></span>

****

|<span data-ttu-id="81c76-114">保護類型</span><span class="sxs-lookup"><span data-stu-id="81c76-114">Protection type</span></span>|<span data-ttu-id="81c76-115">訂閱需求</span><span class="sxs-lookup"><span data-stu-id="81c76-115">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="81c76-116">用於報表目的的審計記錄 () </span><span class="sxs-lookup"><span data-stu-id="81c76-116">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="81c76-117">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="81c76-117">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="81c76-118">反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="81c76-118">Anti-malware protection</span></span>|<span data-ttu-id="81c76-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**) </span><span class="sxs-lookup"><span data-stu-id="81c76-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="81c76-120">防網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="81c76-120">Anti-phishing protection</span></span>|[<span data-ttu-id="81c76-121">EOP</span><span class="sxs-lookup"><span data-stu-id="81c76-121">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="81c76-122">反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="81c76-122">Anti-spam protection</span></span>|[<span data-ttu-id="81c76-123">EOP</span><span class="sxs-lookup"><span data-stu-id="81c76-123">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="81c76-124">電子郵件的零小時自動清除 () </span><span class="sxs-lookup"><span data-stu-id="81c76-124">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="81c76-125">EOP</span><span class="sxs-lookup"><span data-stu-id="81c76-125">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="81c76-126">保護電子郵件和 Office 檔中的惡意 URLs 和檔案 (安全連結和安全附件) </span><span class="sxs-lookup"><span data-stu-id="81c76-126">Protection from malicious URLs and files in email and Office documents (safe links and safe attachments)</span></span>|[<span data-ttu-id="81c76-127">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="81c76-127">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|<span data-ttu-id="81c76-128">開啟 SharePoint、OneDrive 和 Microsoft 小組工作負載的 ATP</span><span class="sxs-lookup"><span data-stu-id="81c76-128">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>|[<span data-ttu-id="81c76-129">適用于 Office 的 Defender 365 </span><span class="sxs-lookup"><span data-stu-id="81c76-129">Defender for Office 365 </span></span>](atp-for-spo-odb-and-teams.md)|
|<span data-ttu-id="81c76-130">高級反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="81c76-130">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="81c76-131">適用於 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="81c76-131">Defender for Office 365</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="81c76-132">角色及權限</span><span class="sxs-lookup"><span data-stu-id="81c76-132">Roles and permissions</span></span>

<span data-ttu-id="81c76-133">若要設定 Office 365 的 Defender 原則，您必須在 [安全性 & 合規性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)中獲指派適當的角色。</span><span class="sxs-lookup"><span data-stu-id="81c76-133">To configure Defender for Office 365 policies, you must be assigned an appropriate role in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="81c76-134">請參閱下表，以取得可以執行這些動作的角色。</span><span class="sxs-lookup"><span data-stu-id="81c76-134">Take a look at the table below for roles that can do these actions.</span></span>

****

|<span data-ttu-id="81c76-135">角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="81c76-135">Role or role group</span></span>|<span data-ttu-id="81c76-136">深入瞭解</span><span class="sxs-lookup"><span data-stu-id="81c76-136">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="81c76-137">全域管理員</span><span class="sxs-lookup"><span data-stu-id="81c76-137">global administrator</span></span>|[<span data-ttu-id="81c76-138">關於 Microsoft 365 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="81c76-138">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="81c76-139">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="81c76-139">Security Administrator</span></span>|[<span data-ttu-id="81c76-140">Azure Active Directory 中的系統管理員角色權限</span><span class="sxs-lookup"><span data-stu-id="81c76-140">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="81c76-141">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="81c76-141">Exchange Online Organization Management</span></span>|[<span data-ttu-id="81c76-142">Exchange Online 中的權限</span><span class="sxs-lookup"><span data-stu-id="81c76-142">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> <span data-ttu-id="81c76-143">和</span><span class="sxs-lookup"><span data-stu-id="81c76-143">and</span></span> <p> [<span data-ttu-id="81c76-144">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="81c76-144">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="81c76-145">若要深入瞭解，請參閱 [安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="81c76-145">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="81c76-146">開始之前，請開啟報告和調查的審計記錄</span><span class="sxs-lookup"><span data-stu-id="81c76-146">Before you begin, turn on Audit logging for reporting and investigation</span></span>

<span data-ttu-id="81c76-147">儘早開始您的審核記錄。</span><span class="sxs-lookup"><span data-stu-id="81c76-147">Start your audit logging early.</span></span> <span data-ttu-id="81c76-148">您 **必須執行** 下列步驟的審計。</span><span class="sxs-lookup"><span data-stu-id="81c76-148">You'll need auditing to be **ON** for certain of the steps that follow.</span></span> <span data-ttu-id="81c76-149">在包含 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)的訂閱中可使用審核記錄。</span><span class="sxs-lookup"><span data-stu-id="81c76-149">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="81c76-150">為了在威脅防護報告中查看資料，例如 [安全性儀表板](security-dashboard.md)、 [電子郵件安全性報告](view-email-security-reports.md)和 [Explorer](threat-explorer.md)，必須 *啟用* 審核記錄。</span><span class="sxs-lookup"><span data-stu-id="81c76-150">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="81c76-151">若要深入瞭解，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="81c76-151">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="81c76-152">第1部分-反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="81c76-152">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="81c76-153">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中提供[反惡意程式碼保護](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="81c76-153">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="81c76-154">在 [ [安全性 & 規範中心](https://protection.office.com)] 中，選擇 [ **威脅管理** \> **原則** \> **反惡意** 代碼]。</span><span class="sxs-lookup"><span data-stu-id="81c76-154">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-malware**.</span></span>

2. <span data-ttu-id="81c76-155">按兩下 **預設** 原則，然後選擇 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-155">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="81c76-156">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="81c76-156">Specify the following settings:</span></span>

    - <span data-ttu-id="81c76-157">在 [ **惡意程式碼偵測回應** ] 區段中，保留預設設定 [ **否**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-157">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="81c76-158">在 [ **一般附件類型篩選** ] 區段中，選擇 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-158">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="81c76-159">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="81c76-159">Click **Save**.</span></span>

<span data-ttu-id="81c76-160">若要深入瞭解反惡意程式碼原則選項，請參閱 [設定反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="81c76-160">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection"></a><span data-ttu-id="81c76-161">第2部分-反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="81c76-161">Part 2 - Anti-phishing protection</span></span>

<span data-ttu-id="81c76-162">您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中取得[反網路釣魚防護](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="81c76-162">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="81c76-163">適用于 [Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)的高級反網路釣魚防護。</span><span class="sxs-lookup"><span data-stu-id="81c76-163">Advanced anti-phishing protection is available in [Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="81c76-164">下列程式說明如何在 Microsoft Defender for Office 365 中設定反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="81c76-164">The following procedure describes how to configure an anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="81c76-165">步驟與在 EOP 中設定反網路釣魚原則類似。</span><span class="sxs-lookup"><span data-stu-id="81c76-165">The steps are similar for configuring an anti-phishing policy in EOP.</span></span>

1. <span data-ttu-id="81c76-166">在 [ [安全性 & 規範中心](https://protection.office.com)] 中，選擇 [ **威脅管理** \> **原則** \> **ATP 反網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-166">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="81c76-167">按一下 [ **預設原則**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-167">Click **Default policy**.</span></span>

3. <span data-ttu-id="81c76-168">在 [ **類比** ] 區段中，按一下 [ **編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="81c76-168">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="81c76-169">在 [**新增要保護的使用者**] 索引卷 *標上，開啟保護。*</span><span class="sxs-lookup"><span data-stu-id="81c76-169">On the **Add users to protect** tab, turn *On* protection.</span></span> <span data-ttu-id="81c76-170">然後新增使用者，例如貴組織的董事會成員、CEO、CFO 和其他資深領導人。</span><span class="sxs-lookup"><span data-stu-id="81c76-170">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="81c76-171"> (您可以輸入個別的電子郵件地址，或按一下以顯示清單。 ) </span><span class="sxs-lookup"><span data-stu-id="81c76-171">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="81c76-172">在 [ **新增要保護的網域** ] 索引標籤上，開啟 [ **自動包含我擁有的網域**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-172">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="81c76-173">如果您有自訂網域，請立即新增。</span><span class="sxs-lookup"><span data-stu-id="81c76-173">If you have custom domains, add them now.</span></span>

   - <span data-ttu-id="81c76-174">在 [**動作**] 索引標籤上，選取 [隔離 **使用者** 和模擬的 **網域**] 選項的 **[郵件**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-174">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="81c76-175">此外，開啟類比安全提示。</span><span class="sxs-lookup"><span data-stu-id="81c76-175">Also, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="81c76-176">在 [ **信箱智慧** ] 索引標籤上，確認已開啟信箱智慧，並開啟信箱智慧類比保護。</span><span class="sxs-lookup"><span data-stu-id="81c76-176">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on and turn on mailbox intelligence-based impersonation protection.</span></span> <span data-ttu-id="81c76-177">在 [ **如果模擬使用者傳送電子郵件** ] 清單中，選擇 [ **隔離郵件**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-177">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="81c76-178">在 [ **新增信任的寄件者和網域** ] 索引標籤上，指定您要新增的任何信任寄件者或網域。</span><span class="sxs-lookup"><span data-stu-id="81c76-178">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="81c76-179">檢查您的設定之後，請 **儲存** 在 [**檢查您的設定**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="81c76-179">**Save** on the **Review your settings** tab after you've reviewed your settings.</span></span>

4. <span data-ttu-id="81c76-180">在 [ **哄騙** ] 區段中，按一下 [ **編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="81c76-180">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="81c76-181">在 [ **哄騙篩選設定** ] 索引標籤上，確定已開啟反欺詐保護。</span><span class="sxs-lookup"><span data-stu-id="81c76-181">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="81c76-182">在 [ **動作** ] 索引標籤上，選擇 [ **隔離郵件**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-182">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="81c76-183">在您檢查您的變更之後，請 **儲存** 在 [**檢查您的設定**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="81c76-183">**Save** on the **Review your settings** tab after you have reviewed your changes.</span></span> <span data-ttu-id="81c76-184"> (如果您未進行任何變更，請 **取消**。 ) </span><span class="sxs-lookup"><span data-stu-id="81c76-184">(If you didn't make any changes, **Cancel**.)</span></span>

5. <span data-ttu-id="81c76-185">關閉 [預設原則設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="81c76-185">Close the default policy settings page.</span></span>

<span data-ttu-id="81c76-186">若要深入瞭解您的反網路釣魚原則選項，請參閱 [在 Microsoft Defender For Office 365 中設定反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="81c76-186">To learn more about your anti-phishing policy options, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection"></a><span data-ttu-id="81c76-187">第3部分-反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="81c76-187">Part 3 - Anti-spam protection</span></span>

<span data-ttu-id="81c76-188">您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中取得[反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="81c76-188">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="81c76-189">在 [ [安全性 & 規範中心](https://protection.office.com)] 中，選擇 [ **威脅管理** \> **原則**] \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="81c76-189">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="81c76-190">在 [ **自訂** ] 索引標籤上，開啟 [自訂設定]。</span><span class="sxs-lookup"><span data-stu-id="81c76-190">On the **Custom** tab, turn on Custom settings.</span></span>

3. <span data-ttu-id="81c76-191">展開 [ **預設垃圾郵件篩選原則**]，按一下 [ **編輯原則**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="81c76-191">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="81c76-192">在 [ **垃圾郵件及大量動作** ] 區段中，將臨界值設為5或6。</span><span class="sxs-lookup"><span data-stu-id="81c76-192">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="81c76-193">在 [ **允許清單** ] 區段中，複查 (和/或編輯) 允許的寄件者和網域。</span><span class="sxs-lookup"><span data-stu-id="81c76-193">In the **Allow lists** section, review (and/or edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="81c76-194">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="81c76-194">Click **Save**.</span></span>

<span data-ttu-id="81c76-195">若要深入瞭解您的反垃圾郵件原則選項，請參閱 [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="81c76-195">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a><span data-ttu-id="81c76-196">第4部分-針對 Office 365 的 Defender 中的安全連結和安全附件，防範來自惡意 URLs 和檔案 (安全連結和安全附件) </span><span class="sxs-lookup"><span data-stu-id="81c76-196">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments in Defender for Office 365)</span></span>

<span data-ttu-id="81c76-197">在包含 [Microsoft Defender For Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)的訂閱中，可使用從惡意 URLs 和檔案進行時間的防護。</span><span class="sxs-lookup"><span data-stu-id="81c76-197">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="81c76-198">它是透過 [安全附件](atp-safe-attachments.md) 和 [安全連結](atp-safe-links.md) 原則來設定。</span><span class="sxs-lookup"><span data-stu-id="81c76-198">It's set up through [Safe Attachments](atp-safe-attachments.md) and [Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="81c76-199">Microsoft Defender for Office 365 中的安全附件原則</span><span class="sxs-lookup"><span data-stu-id="81c76-199">Safe Attachments policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="81c76-200">若要設定 [安全附件](atp-safe-attachments.md)，請至少建立一個安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="81c76-200">To set up [Safe Attachments](atp-safe-attachments.md), create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="81c76-201">在 [ [安全性 & 規範中心](https://protection.office.com)] 中，選擇 [ **威脅管理** \> **原則** \> **ATP 安全附件**]，然後按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-201">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Create**.</span></span>

2. <span data-ttu-id="81c76-202">在出現的 [ **新增安全附件原則** ] 嚮導中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="81c76-202">In the **New Safe Attachments policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="81c76-203">在 [ **名稱** ] 方塊中，輸入 `Block malware` ，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="81c76-203">In the **Name** box, type `Block malware`, and then click **Next**.</span></span>

   - <span data-ttu-id="81c76-204">在 [ **設定** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="81c76-204">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="81c76-205">在 [ **安全附件未知惡意程式碼回應** ] 區段中，選擇 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-205">In the **Safe attachments unknown malware response** section, choose **Block**.</span></span>
     - <span data-ttu-id="81c76-206">在 [重新 **導向附件** ] 區段中，選取 [ **啟用重新導向**] 選項。</span><span class="sxs-lookup"><span data-stu-id="81c76-206">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="81c76-207">指定組織的安全性系統管理員或操作員的電子郵件地址，誰會檢查偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="81c76-207">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

     <span data-ttu-id="81c76-208">按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="81c76-208">Click **Next**.</span></span>

3. <span data-ttu-id="81c76-209">在 [套用 **至**] 頁面上，按一下 [**新增條件**]，然後選擇 [套用者 **：收件者網域是**]，按一下 [**新增**]，選取您的網域，按一下 [**新增**]，按一下 [**完成**]，然後按 **[下一步**</span><span class="sxs-lookup"><span data-stu-id="81c76-209">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

4. <span data-ttu-id="81c76-210">請複查您的設定，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="81c76-210">Review your settings and then click **Finish**.</span></span>

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="81c76-211">Microsoft Defender for Office 365 中的安全連結原則</span><span class="sxs-lookup"><span data-stu-id="81c76-211">Safe Links policies in Microsoft Defender for Office 365</span></span>

<span data-ttu-id="81c76-212">若要設定 [安全連結](atp-safe-links.md)，請複查及編輯安全連結的全域設定，並至少建立一個安全連結原則。</span><span class="sxs-lookup"><span data-stu-id="81c76-212">To set up [Safe Links](atp-safe-links.md), review and edit your global settings for Safe Links, and create at least one Safe Links policy.</span></span>

1. <span data-ttu-id="81c76-213">在 [ [安全性 & 規範中心](https://protection.office.com)] 中，選擇 [ **威脅管理** \> **原則** \> **ATP 安全連結**]，然後按一下 [ **通用設定**]，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="81c76-213">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Links**, and click **Global settings**, and then configure the following settings:</span></span>

   - <span data-ttu-id="81c76-214">驗證 **使用下列安全連結： Office 365 應用程式** 已開啟： ![ 開啟開啟] ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。</span><span class="sxs-lookup"><span data-stu-id="81c76-214">Verify **Use Safe Links in: Office 365 applications** is turned on: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>
   - <span data-ttu-id="81c76-215">**當使用者按一下安全連結時，請勿追蹤**：關閉此設定以追蹤使用者點擊： ![ 關閉 ](../../media/scc-toggle-off.png) 。</span><span class="sxs-lookup"><span data-stu-id="81c76-215">**Do not track when users click Safe Links**: Turn this setting off to track user clicks: ![Toggle off](../../media/scc-toggle-off.png).</span></span>
   - <span data-ttu-id="81c76-216">**不要讓使用者點擊 [安全連結至原始 URL**]：確認已開啟此設定： ![ 開啟開啟 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 。</span><span class="sxs-lookup"><span data-stu-id="81c76-216">**Do not let users click through safe links to original URL**: Verify this setting is turned on: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).</span></span>

   <span data-ttu-id="81c76-217">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="81c76-217">When you're finished, click **Save**.</span></span>

2. <span data-ttu-id="81c76-218">回到 [主要安全連結] 頁面上，按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-218">Back on the main Safe Links page, click **Create**.</span></span>

3. <span data-ttu-id="81c76-219">在出現的 [ **建立安全連結原則** ] 嚮導中，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="81c76-219">In the **Create Safe Links policy** wizard that appears, configure the following settings:</span></span>

   - <span data-ttu-id="81c76-220">在 [ **名稱** ] 方塊中，輸入名稱，例如 `Safe Links` ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="81c76-220">In the **Name** box, type a name, such as `Safe Links`, and then click **Next**.</span></span>

   - <span data-ttu-id="81c76-221">在 [ **設定** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="81c76-221">On the **Settings** page, configure the following settings:</span></span>
     - <span data-ttu-id="81c76-222">**在郵件中選取未知可能惡意 URLs 的動作**：選擇 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-222">**Select the action for unknown potentially malicious URLs in messages**: Choose **On**.</span></span>
     - <span data-ttu-id="81c76-223">**選取 Microsoft 小組中未知或可能惡意 URLs 的動作**：選擇 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-223">**Select the action for unknown or potentially malicious URLs within Microsoft Teams**: Choose **On**.</span></span>
     - <span data-ttu-id="81c76-224">**對組織內傳送的電子郵件套用安全連結**</span><span class="sxs-lookup"><span data-stu-id="81c76-224">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="81c76-225">**等待 URL 掃描完成再傳遞郵件**</span><span class="sxs-lookup"><span data-stu-id="81c76-225">**Wait for URL scanning to complete before delivering the message**</span></span>
     - <span data-ttu-id="81c76-226">**對組織內傳送的電子郵件套用安全連結**</span><span class="sxs-lookup"><span data-stu-id="81c76-226">**Apply safe links to email messages sent within the organization**</span></span>
     - <span data-ttu-id="81c76-227">**不允許使用者點選原始 URL**</span><span class="sxs-lookup"><span data-stu-id="81c76-227">**Do not allow users to click through to original URL**</span></span>

     <span data-ttu-id="81c76-228">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="81c76-228">Click **Next**</span></span>

4. <span data-ttu-id="81c76-229">在 [套用 **至**] 頁面上，按一下 [**新增條件**]，然後選擇 [套用者 **：收件者網域是**]，按一下 [**新增**]，選取您的網域，按一下 [**新增**]，按一下 [**完成**]，然後按 **[下一步**</span><span class="sxs-lookup"><span data-stu-id="81c76-229">On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.</span></span>

5. <span data-ttu-id="81c76-230">請複查您的設定，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="81c76-230">Review your settings and then click **Finish**.</span></span>

<span data-ttu-id="81c76-231">若要深入了解，請參閱[設定安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="81c76-231">To learn more, see [Set up Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a><span data-ttu-id="81c76-232">第5部分-確認 SharePoint、OneDrive 和 Microsoft 團隊的 ATP 已開啟</span><span class="sxs-lookup"><span data-stu-id="81c76-232">Part 5 - Verify ATP for SharePoint, OneDrive, and Microsoft Teams is turned on</span></span>

<span data-ttu-id="81c76-233">SharePoint、OneDrive 和小組等工作負載都是為了共同作業而建立的。</span><span class="sxs-lookup"><span data-stu-id="81c76-233">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="81c76-234">使用適用于 Office 的 Defender 365 可協助封鎖和偵測在小組網站和文件庫中識別為惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="81c76-234">Using Defender for Office 365 helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="81c76-235">您可以在 [這裡](atp-for-spo-odb-and-teams.md)進一步閱讀該功能的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="81c76-235">You can read more about how that works [here](atp-for-spo-odb-and-teams.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81c76-236">**開始此程式之前，請確定已為您的 Microsoft 365 環境開啟了審核記錄**。</span><span class="sxs-lookup"><span data-stu-id="81c76-236">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="81c76-237">這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。</span><span class="sxs-lookup"><span data-stu-id="81c76-237">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="81c76-238">如需詳細資訊，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)！</span><span class="sxs-lookup"><span data-stu-id="81c76-238">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="81c76-239">在 [ [安全性 & 規範中心](https://protection.office.com)] 中，選擇 [ **威脅管理** \> **原則** \> **ATP 安全附件**]，然後按一下 [ **通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-239">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.</span></span>

2. <span data-ttu-id="81c76-240">驗證 **SharePoint、OneDrive 和 Microsoft 團隊** 切換功能的開啟 ATP 是否為右對齊： ![ 切換開啟]，然後按一下 [ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-240">Verify the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** toggle is to the right: ![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png), and then click **Save**.</span></span>

3. <span data-ttu-id="81c76-241">檢閱 (並視需要編輯) 組織的 [[安全附件原則]](set-up-atp-safe-attachments-policies.md) 和 [[安全連結原則]](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="81c76-241">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

4. <span data-ttu-id="81c76-242"> (建議) 成為全域系統管理員或 SharePoint Online 管理員，請執行 **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** Cmdlet，並將 _DisallowInfectedFileDownload_ 參數設定為 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="81c76-242">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to `$true`.</span></span>

   - <span data-ttu-id="81c76-243">`$true` 封鎖針對偵測到的檔案 (刪除) 以外的所有動作。</span><span class="sxs-lookup"><span data-stu-id="81c76-243">`$true` blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="81c76-244">使用者將無法開啟、移動、複製或共用偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="81c76-244">People cannot open, move, copy, or share detected files.</span></span>
   - <span data-ttu-id="81c76-245">`$false` 封鎖除 Delete 和下載中心以外的所有動作。</span><span class="sxs-lookup"><span data-stu-id="81c76-245">`$false` blocks all actions except Delete and Download.</span></span> <span data-ttu-id="81c76-246">使用者可以選擇接受風險並下載偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="81c76-246">People can choose to accept the risk and download a detected file.</span></span>

   > [!TIP]
   > <span data-ttu-id="81c76-247">若要深入瞭解搭配 Microsoft 365 使用 PowerShell，請參閱使用 [PowerShell 管理 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="81c76-247">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).</span></span>

5. <span data-ttu-id="81c76-248">允許最多30分鐘的變更，以散佈至所有 Microsoft 365 資料中心。</span><span class="sxs-lookup"><span data-stu-id="81c76-248">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>

### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="81c76-249">現在，設定偵測到檔案的警示</span><span class="sxs-lookup"><span data-stu-id="81c76-249">Now set up alerts for detected files</span></span>

<span data-ttu-id="81c76-250">若要在 SharePoint Online、商務用 OneDrive 或 Microsoft Teams 中的檔案被識別為惡意檔案時收到通知，您可以設定警示。</span><span class="sxs-lookup"><span data-stu-id="81c76-250">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="81c76-251">在 [ [安全性 & 規範中心](https://protection.office.com)] 中，選擇 [ **警示**] [ \> **管理提醒**]。</span><span class="sxs-lookup"><span data-stu-id="81c76-251">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="81c76-252">選擇 **[新警示原則]**。</span><span class="sxs-lookup"><span data-stu-id="81c76-252">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="81c76-253">指定警示的名稱。</span><span class="sxs-lookup"><span data-stu-id="81c76-253">Specify a name for the alert.</span></span> <span data-ttu-id="81c76-254">例如，您可以輸入「程式庫中的惡意檔案」。</span><span class="sxs-lookup"><span data-stu-id="81c76-254">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="81c76-255">輸入警示描述。</span><span class="sxs-lookup"><span data-stu-id="81c76-255">Type a description for the alert.</span></span> <span data-ttu-id="81c76-256">例如，當您在 SharePoint Online、OneDrive 或 Microsoft Teams 中偵測到惡意檔案時，您可以輸入「通知系統管理員」。</span><span class="sxs-lookup"><span data-stu-id="81c76-256">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="81c76-257">在 [ **傳送此警示** 的時機 ...] 區段中，設定：</span><span class="sxs-lookup"><span data-stu-id="81c76-257">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="81c76-258">a.</span><span class="sxs-lookup"><span data-stu-id="81c76-258">a.</span></span> <span data-ttu-id="81c76-259">在 **[活動]** 清單中，選擇 **[已偵測到檔案中的惡意程式碼]**。</span><span class="sxs-lookup"><span data-stu-id="81c76-259">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="81c76-260">b.</span><span class="sxs-lookup"><span data-stu-id="81c76-260">b.</span></span> <span data-ttu-id="81c76-261">將 **[使用者]** 欄位保留空白。</span><span class="sxs-lookup"><span data-stu-id="81c76-261">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="81c76-262">在 **[傳送此通知到...]** 區段中，選取一或多位全域系統管理員、安全性系統管理員，或在偵測到惡意檔案時應收到通知的安全性讀者。</span><span class="sxs-lookup"><span data-stu-id="81c76-262">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="81c76-263">**儲存**。</span><span class="sxs-lookup"><span data-stu-id="81c76-263">**Save**.</span></span>

<span data-ttu-id="81c76-264">若要深入瞭解提醒，請參閱 [在安全性 & 規範中心建立活動警示](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="81c76-264">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="81c76-265">當您完成設定時，請使用下列連結來開始工作負載調查：</span><span class="sxs-lookup"><span data-stu-id="81c76-265">When you're finished configuring, use these links to start workload investigations:</span></span>
>
>- [<span data-ttu-id="81c76-266">威脅防護狀態報告</span><span class="sxs-lookup"><span data-stu-id="81c76-266">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
>- [<span data-ttu-id="81c76-267">使用安全性 & 規範中心管理隔離的檔案</span><span class="sxs-lookup"><span data-stu-id="81c76-267">Use the Security & Compliance Center to manage quarantined files</span></span>](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [<span data-ttu-id="81c76-268">在 SharePoint 線上、OneDrive 或 Microsoft 小組中找到惡意檔案時，要執行的動作</span><span class="sxs-lookup"><span data-stu-id="81c76-268">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="81c76-269">在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="81c76-269">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="81c76-270">第6部分-要設定的其他設定</span><span class="sxs-lookup"><span data-stu-id="81c76-270">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="81c76-271">在設定惡意程式碼、惡意 URLs 和檔案、網路釣魚和垃圾郵件的防護時，建議您設定零小時自動清除。</span><span class="sxs-lookup"><span data-stu-id="81c76-271">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="81c76-272">EOP 中的電子郵件的自動清除零小時</span><span class="sxs-lookup"><span data-stu-id="81c76-272">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="81c76-273">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中可使用[零小時自動清除](zero-hour-auto-purge.md) (ZAP) 。</span><span class="sxs-lookup"><span data-stu-id="81c76-273">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="81c76-274">此保護功能預設為開啟狀態;不過，保護生效的情況必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="81c76-274">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="81c76-275">垃圾 [訊息原則](anti-spam-protection.md)中的垃圾郵件動作會設定為 **將郵件移至 [垃圾郵件] 資料夾**。</span><span class="sxs-lookup"><span data-stu-id="81c76-275">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="81c76-276">使用者保留其預設的 [垃圾郵件設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)，但未關閉垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="81c76-276">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="81c76-277">若要深入瞭解，請參閱 [零時自動清除-防護垃圾郵件和惡意](zero-hour-auto-purge.md)代碼。</span><span class="sxs-lookup"><span data-stu-id="81c76-277">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="81c76-278">安裝後的工作及後續步驟</span><span class="sxs-lookup"><span data-stu-id="81c76-278">Post-setup tasks and next steps</span></span>

<span data-ttu-id="81c76-279">設定威脅防護功能之後，請務必監視這些功能的運作方式！</span><span class="sxs-lookup"><span data-stu-id="81c76-279">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="81c76-280">複查和修訂您的原則，讓他們能執行您所需的工作。</span><span class="sxs-lookup"><span data-stu-id="81c76-280">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="81c76-281">此外，請留意可增加價值的新功能和服務更新。</span><span class="sxs-lookup"><span data-stu-id="81c76-281">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="81c76-282">處理方式</span><span class="sxs-lookup"><span data-stu-id="81c76-282">What to do</span></span>|<span data-ttu-id="81c76-283">可深入了解的資源</span><span class="sxs-lookup"><span data-stu-id="81c76-283">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="81c76-284">查看您的組織如何使用威脅防護功能，以查看報告</span><span class="sxs-lookup"><span data-stu-id="81c76-284">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="81c76-285">安全性儀表板</span><span class="sxs-lookup"><span data-stu-id="81c76-285">Security dashboard</span></span>](security-dashboard.md) <p> [<span data-ttu-id="81c76-286">電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="81c76-286">Email security reports</span></span>](view-email-security-reports.md) <p> [<span data-ttu-id="81c76-287">Microsoft Defender for Office 365 的報告</span><span class="sxs-lookup"><span data-stu-id="81c76-287">Reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md) <p> [<span data-ttu-id="81c76-288">威脅總管</span><span class="sxs-lookup"><span data-stu-id="81c76-288">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="81c76-289">視需要定期複查和修正威脅防護原則</span><span class="sxs-lookup"><span data-stu-id="81c76-289">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="81c76-290">安全分數</span><span class="sxs-lookup"><span data-stu-id="81c76-290">Secure Score</span></span>](../mtp/microsoft-secure-score.md) <p> [<span data-ttu-id="81c76-291">智慧報告和洞察力</span><span class="sxs-lookup"><span data-stu-id="81c76-291">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md) <p> [<span data-ttu-id="81c76-292">Microsoft 365 威脅調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="81c76-292">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="81c76-293">監視新功能和服務更新</span><span class="sxs-lookup"><span data-stu-id="81c76-293">Watch for new features and service updates</span></span>|[<span data-ttu-id="81c76-294">標準及目標發行選項</span><span class="sxs-lookup"><span data-stu-id="81c76-294">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365) <p> [<span data-ttu-id="81c76-295">訊息中心</span><span class="sxs-lookup"><span data-stu-id="81c76-295">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center) <p> [<span data-ttu-id="81c76-296">Microsoft 365 藍圖</span><span class="sxs-lookup"><span data-stu-id="81c76-296">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [<span data-ttu-id="81c76-297">服務說明</span><span class="sxs-lookup"><span data-stu-id="81c76-297">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="81c76-298">瞭解適用于 EOP 和 Defender for Office 365 的建議標準和嚴格安全性設定的詳細資料</span><span class="sxs-lookup"><span data-stu-id="81c76-298">Learn the details about recommended Standard and Strict security configurations for EOP and Defender for Office 365</span></span>|[<span data-ttu-id="81c76-299">EOP 和 Microsoft Defender for Office 365 安全性的建議設定</span><span class="sxs-lookup"><span data-stu-id="81c76-299">Recommended settings for EOP and Microsoft Defender for Office 365 security</span></span>](recommended-settings-for-eop-and-office365-atp.md)|
