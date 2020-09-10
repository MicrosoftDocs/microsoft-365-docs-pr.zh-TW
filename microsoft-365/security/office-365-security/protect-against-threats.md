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
description: 系統管理員可以深入瞭解 Microsoft 365 中的威脅防護，並設定如何將它用於您的組織。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b96ba1735f94e80450fa4f604fc45dc60b80d12
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417119"
---
# <a name="protect-against-threats"></a><span data-ttu-id="257b0-103">防範威脅</span><span class="sxs-lookup"><span data-stu-id="257b0-103">Protect against threats</span></span>

<span data-ttu-id="257b0-104">以下是將高級威脅防護設定中斷為區塊的快速入門手冊。</span><span class="sxs-lookup"><span data-stu-id="257b0-104">Here's a quick-start guide that breaks the configuration of Advanced Threat Protection into chunks.</span></span> <span data-ttu-id="257b0-105">如果您是 Office 365 中威脅防護功能的新功能，請不要確定開始的位置，或者，如果您想要 *這麼做*，請使用本指導方針做為檢查清單和開始點。</span><span class="sxs-lookup"><span data-stu-id="257b0-105">If you're new to threat protection features in Office 365, not sure where to begin, or if you learn best by *doing*, use this guidance as a checklist and a starting point.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="257b0-106">**每種原則都包含初始建議設定，但有許多選項可供使用，您可以調整設定，以符合特定組織的需求**。</span><span class="sxs-lookup"><span data-stu-id="257b0-106">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="257b0-107">允許大約30分鐘的原則或變更以透過您的資料中心來運作。</span><span class="sxs-lookup"><span data-stu-id="257b0-107">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="257b0-108">需求</span><span class="sxs-lookup"><span data-stu-id="257b0-108">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="257b0-109">訂閱</span><span class="sxs-lookup"><span data-stu-id="257b0-109">Subscriptions</span></span>

<span data-ttu-id="257b0-110">威脅防護功能包含在 *所有* Microsoft 或 Office 365 訂閱中;不過，有些訂閱具有高級功能。</span><span class="sxs-lookup"><span data-stu-id="257b0-110">Threat protection features are included in *all* Microsoft or Office 365 subscriptions; however, some subscriptions have advanced features.</span></span> <span data-ttu-id="257b0-111">下表列出本文所含的保護功能及最低訂閱需求。</span><span class="sxs-lookup"><span data-stu-id="257b0-111">The table below lists the protection features included in this article together with the minimum subscription requirements.</span></span>

> [!TIP]
> <span data-ttu-id="257b0-112">請注意，除了開啟審計的指示 *之外，還會啟動反* 惡意程式碼、反網路釣魚和反垃圾郵件，並標示為 Office 365 Exchange Online Protection (**EOP**) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="257b0-112">Notice that, beyond the directions to turn on auditing, *steps* start anti-malware, anti-phishing, and anti-spam, which are marked as part of Office 365 Exchange Online Protection (**EOP**).</span></span> <span data-ttu-id="257b0-113">這在「高級威脅防護」文章中看起來會是奇怪的，直到您記得) 包含的高級威脅防護 (**ATP** 包含，並在 EOP 中建立。</span><span class="sxs-lookup"><span data-stu-id="257b0-113">This can seem odd in an Advanced Threat Protection article, until you remember Advanced Threat Protection (**ATP**) contains, and builds on, EOP.</span></span>

****

|<span data-ttu-id="257b0-114">保護類型</span><span class="sxs-lookup"><span data-stu-id="257b0-114">Protection type</span></span>|<span data-ttu-id="257b0-115">訂閱需求</span><span class="sxs-lookup"><span data-stu-id="257b0-115">Subscription requirement</span></span>|
|---|---|
|<span data-ttu-id="257b0-116">用於報表目的的審計記錄 () </span><span class="sxs-lookup"><span data-stu-id="257b0-116">Audit logging (for reporting purposes)</span></span>|[<span data-ttu-id="257b0-117">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="257b0-117">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|<span data-ttu-id="257b0-118">反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="257b0-118">Anti-malware protection</span></span>|<span data-ttu-id="257b0-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**) </span><span class="sxs-lookup"><span data-stu-id="257b0-119">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)</span></span>|
|<span data-ttu-id="257b0-120">防網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="257b0-120">Anti-phishing protection</span></span>|[<span data-ttu-id="257b0-121">EOP</span><span class="sxs-lookup"><span data-stu-id="257b0-121">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="257b0-122">反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="257b0-122">Anti-spam protection</span></span>|[<span data-ttu-id="257b0-123">EOP</span><span class="sxs-lookup"><span data-stu-id="257b0-123">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="257b0-124">電子郵件的零小時自動清除 () </span><span class="sxs-lookup"><span data-stu-id="257b0-124">Zero-hour auto purge (for email)</span></span>|[<span data-ttu-id="257b0-125">EOP</span><span class="sxs-lookup"><span data-stu-id="257b0-125">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|<span data-ttu-id="257b0-126">保護電子郵件和 Office 檔中的惡意 URLs 和檔案 (安全連結和安全附件) </span><span class="sxs-lookup"><span data-stu-id="257b0-126">Protection from malicious URLs and files in email and Office documents (safe links and safe attachments)</span></span>|<span data-ttu-id="257b0-127">[Office 365 高級威脅防護](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**) </span><span class="sxs-lookup"><span data-stu-id="257b0-127">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**)</span></span>|
|<span data-ttu-id="257b0-128">開啟 SharePoint、OneDrive 和 Microsoft 小組工作負載的 ATP</span><span class="sxs-lookup"><span data-stu-id="257b0-128">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>| [<span data-ttu-id="257b0-129">Atp</span><span class="sxs-lookup"><span data-stu-id="257b0-129">ATP</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide)|
|<span data-ttu-id="257b0-130">高級反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="257b0-130">Advanced anti-phishing protection</span></span>|[<span data-ttu-id="257b0-131">Atp</span><span class="sxs-lookup"><span data-stu-id="257b0-131">ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a><span data-ttu-id="257b0-132">角色及權限</span><span class="sxs-lookup"><span data-stu-id="257b0-132">Roles and permissions</span></span>

<span data-ttu-id="257b0-133">若要設定 ATP 原則，您必須在 [安全性 & 規範中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)中獲指派適當的角色。</span><span class="sxs-lookup"><span data-stu-id="257b0-133">To configure ATP policies, you must be assigned an appropriate role in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="257b0-134">請參閱下表，以取得可以執行這些動作的角色。</span><span class="sxs-lookup"><span data-stu-id="257b0-134">Take a look at the table below for roles that can do these actions.</span></span>

****

|<span data-ttu-id="257b0-135">角色或角色群組</span><span class="sxs-lookup"><span data-stu-id="257b0-135">Role or role group</span></span>|<span data-ttu-id="257b0-136">深入瞭解</span><span class="sxs-lookup"><span data-stu-id="257b0-136">Where to learn more</span></span>|
|---|---|
|<span data-ttu-id="257b0-137">全域管理員</span><span class="sxs-lookup"><span data-stu-id="257b0-137">global administrator</span></span>|[<span data-ttu-id="257b0-138">關於 Microsoft 365 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="257b0-138">About Microsoft 365 admin roles</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="257b0-139">安全性系統管理員</span><span class="sxs-lookup"><span data-stu-id="257b0-139">Security Administrator</span></span>|[<span data-ttu-id="257b0-140">Azure Active Directory 中的系統管理員角色權限</span><span class="sxs-lookup"><span data-stu-id="257b0-140">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="257b0-141">Exchange Online 組織管理</span><span class="sxs-lookup"><span data-stu-id="257b0-141">Exchange Online Organization Management</span></span>|[<span data-ttu-id="257b0-142">Exchange Online 中的權限</span><span class="sxs-lookup"><span data-stu-id="257b0-142">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="257b0-143">和</span><span class="sxs-lookup"><span data-stu-id="257b0-143">and</span></span><br> [<span data-ttu-id="257b0-144">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="257b0-144">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

<span data-ttu-id="257b0-145">若要深入瞭解，請參閱 [安全性與 &amp; 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="257b0-145">To learn more, see [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="257b0-146">開始之前，請開啟報告和調查的審計記錄</span><span class="sxs-lookup"><span data-stu-id="257b0-146">Before you begin, turn on Audit logging for reporting and investigation</span></span>

<span data-ttu-id="257b0-147">儘早開始您的審核記錄。</span><span class="sxs-lookup"><span data-stu-id="257b0-147">Start your audit logging early.</span></span> <span data-ttu-id="257b0-148">您 **必須執行** 下列步驟的審計。</span><span class="sxs-lookup"><span data-stu-id="257b0-148">You'll need auditing to be **ON** for certain of the steps that follow.</span></span> <span data-ttu-id="257b0-149">在包含 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)的訂閱中可使用審核記錄。</span><span class="sxs-lookup"><span data-stu-id="257b0-149">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).</span></span> <span data-ttu-id="257b0-150">為了在威脅防護報告中查看資料，例如 [安全性儀表板](security-dashboard.md)、 [電子郵件安全性報告](view-email-security-reports.md)和 [Explorer](threat-explorer.md)，必須 *啟用*審核記錄。</span><span class="sxs-lookup"><span data-stu-id="257b0-150">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](threat-explorer.md), audit logging must be *On*.</span></span> <span data-ttu-id="257b0-151">若要深入瞭解，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="257b0-151">To learn more, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="257b0-152">第1部分-反惡意程式碼保護</span><span class="sxs-lookup"><span data-stu-id="257b0-152">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="257b0-153">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中提供[反惡意程式碼保護](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="257b0-153">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="257b0-154">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理**  >  **原則**  >  **反惡意**代碼]。</span><span class="sxs-lookup"><span data-stu-id="257b0-154">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="257b0-155">按兩下 **預設** 原則，然後選擇 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-155">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="257b0-156">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="257b0-156">Specify the following settings:</span></span>

    - <span data-ttu-id="257b0-157">在 [ **惡意程式碼偵測回應** ] 區段中，保留預設設定 [ **否**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-157">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="257b0-158">在 [ **一般附件類型篩選** ] 區段中，選擇 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-158">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="257b0-159">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="257b0-159">Click **Save**.</span></span>

<span data-ttu-id="257b0-160">若要深入瞭解反惡意程式碼原則選項，請參閱 [設定反惡意程式碼原則](configure-anti-malware-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="257b0-160">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---anti-phishing-protection"></a><span data-ttu-id="257b0-161">第2部分-反網路釣魚保護</span><span class="sxs-lookup"><span data-stu-id="257b0-161">Part 2 - Anti-phishing protection</span></span>

<span data-ttu-id="257b0-162">[防網路釣魚]</span><span class="sxs-lookup"><span data-stu-id="257b0-162">[Anti-phishing]</span></span>

<span data-ttu-id="257b0-163">您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中取得[反網路釣魚防護](anti-phishing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="257b0-163">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="257b0-164">您可以使用 [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中的高級反網路釣魚防護。</span><span class="sxs-lookup"><span data-stu-id="257b0-164">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

<span data-ttu-id="257b0-165">下列程式說明如何設定 ATP 反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="257b0-165">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="257b0-166">設定不含 ATP) 的反網路釣魚原則 (，步驟類似。</span><span class="sxs-lookup"><span data-stu-id="257b0-166">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="257b0-167">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理**  >  **原則**  >  **ATP 反網路釣魚**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-167">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="257b0-168">按一下 [ **預設原則**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-168">Click **Default policy**.</span></span>

3. <span data-ttu-id="257b0-169">在 [ **類比** ] 區段中，按一下 [ **編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="257b0-169">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="257b0-170">在 [**新增要保護的使用者**] 索引卷*標上，開啟保護。*</span><span class="sxs-lookup"><span data-stu-id="257b0-170">On the **Add users to protect** tab, turn *On* protection.</span></span> <span data-ttu-id="257b0-171">然後新增使用者，例如貴組織的董事會成員、CEO、CFO 和其他資深領導人。</span><span class="sxs-lookup"><span data-stu-id="257b0-171">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="257b0-172"> (您可以輸入個別的電子郵件地址，或按一下以顯示清單。 ) </span><span class="sxs-lookup"><span data-stu-id="257b0-172">(You can type an individual email address, or click to display a list.)</span></span>

   - <span data-ttu-id="257b0-173">在 [ **新增要保護的網域** ] 索引標籤上，開啟 [ **自動包含我擁有的網域**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-173">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="257b0-174">如果您有自訂網域，請立即新增。</span><span class="sxs-lookup"><span data-stu-id="257b0-174">If you have custom domains, add them now.</span></span>

   - <span data-ttu-id="257b0-175">在 [**動作**] 索引標籤上，選取 [隔離**使用者**和模擬的**網域**] 選項的 **[郵件**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-175">On the **Actions** tab, select **Quarantine the message** for both the **impersonated user** and **impersonated domain** options.</span></span> <span data-ttu-id="257b0-176">此外，開啟類比安全提示。</span><span class="sxs-lookup"><span data-stu-id="257b0-176">Also, turn on impersonation safety tips.</span></span>

   - <span data-ttu-id="257b0-177">在 [ **信箱智慧** ] 索引標籤上，確認已開啟信箱智慧，並開啟信箱智慧類比保護。</span><span class="sxs-lookup"><span data-stu-id="257b0-177">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on and turn on mailbox intelligence-based impersonation protection.</span></span> <span data-ttu-id="257b0-178">在 [ **如果模擬使用者傳送電子郵件** ] 清單中，選擇 [ **隔離郵件**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-178">In the **If email is sent by an impersonated user** list, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="257b0-179">在 [ **新增信任的寄件者和網域** ] 索引標籤上，指定您要新增的任何信任寄件者或網域。</span><span class="sxs-lookup"><span data-stu-id="257b0-179">On the **Add trusted senders and domains** tab, specify any trusted senders or domains that you want to add.</span></span>

   - <span data-ttu-id="257b0-180">檢查您的設定之後，請**儲存**在 [**檢查您的設定**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="257b0-180">**Save** on the **Review your settings** tab after you've reviewed your settings.</span></span>

4. <span data-ttu-id="257b0-181">在 [ **哄騙** ] 區段中，按一下 [ **編輯**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="257b0-181">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

   - <span data-ttu-id="257b0-182">在 [ **哄騙篩選設定** ] 索引標籤上，確定已開啟反欺詐保護。</span><span class="sxs-lookup"><span data-stu-id="257b0-182">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

   - <span data-ttu-id="257b0-183">在 [ **動作** ] 索引標籤上，選擇 [ **隔離郵件**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-183">On the **Actions** tab, choose **Quarantine the message**.</span></span>

   - <span data-ttu-id="257b0-184">在您檢查您的變更之後，請**儲存**在 [**檢查您的設定**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="257b0-184">**Save** on the **Review your settings** tab after you have reviewed your changes.</span></span> <span data-ttu-id="257b0-185"> (如果您未進行任何變更，請 **取消**。 ) </span><span class="sxs-lookup"><span data-stu-id="257b0-185">(If you didn't make any changes, **Cancel**.)</span></span>

5. <span data-ttu-id="257b0-186">關閉 [預設原則設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="257b0-186">Close the default policy settings page.</span></span>

<span data-ttu-id="257b0-187">若要深入瞭解您的反網路釣魚原則選項，請參閱 [設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="257b0-187">To learn more about your anti-phishing policy options, see [Configure ATP anti-phishing policies](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="part-3---anti-spam-protection"></a><span data-ttu-id="257b0-188">第3部分-反垃圾郵件保護</span><span class="sxs-lookup"><span data-stu-id="257b0-188">Part 3 - Anti-spam protection</span></span>

<span data-ttu-id="257b0-189">您可以在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中取得[反垃圾郵件保護](anti-spam-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="257b0-189">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="257b0-190">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理**  >  **原則**]  >  **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="257b0-190">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="257b0-191">在 [ **自訂** ] 索引標籤上，開啟 [自訂設定]。</span><span class="sxs-lookup"><span data-stu-id="257b0-191">On the **Custom** tab, turn on Custom settings.</span></span>

3. <span data-ttu-id="257b0-192">展開 [ **預設垃圾郵件篩選原則**]，按一下 [ **編輯原則**]，然後指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="257b0-192">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

   - <span data-ttu-id="257b0-193">在 [ **垃圾郵件及大量動作** ] 區段中，將臨界值設為5或6。</span><span class="sxs-lookup"><span data-stu-id="257b0-193">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

   - <span data-ttu-id="257b0-194">在 [ **允許清單** ] 區段中，複查 (和/或編輯) 允許的寄件者和網域。</span><span class="sxs-lookup"><span data-stu-id="257b0-194">In the **Allow lists** section, review (and/or edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="257b0-195">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="257b0-195">Click **Save**.</span></span>

<span data-ttu-id="257b0-196">若要深入瞭解您的反垃圾郵件原則選項，請參閱 [在 EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="257b0-196">To learn more about your anti-spam policy options, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments"></a><span data-ttu-id="257b0-197">第4部分-防範惡意 URLs 和檔案 (安全連結和安全附件) </span><span class="sxs-lookup"><span data-stu-id="257b0-197">Part 4 - Protection from malicious URLs and files (Safe Links and Safe Attachments)</span></span>

<span data-ttu-id="257b0-198">在包含 [Office 365 atp](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (atp) 的訂閱中，可使用從惡意 URLs 和檔案進行的點擊時間防護。</span><span class="sxs-lookup"><span data-stu-id="257b0-198">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP).</span></span> <span data-ttu-id="257b0-199">它是透過 [Atp 安全附件](atp-safe-attachments.md) 和 [atp 安全連結](atp-safe-links.md) 原則進行設定。</span><span class="sxs-lookup"><span data-stu-id="257b0-199">It's set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="257b0-200">ATP 安全附件原則</span><span class="sxs-lookup"><span data-stu-id="257b0-200">ATP Safe Attachments policies</span></span>

<span data-ttu-id="257b0-201">若要設定 [Atp 安全附件](atp-safe-attachments.md)，您必須至少定義一個 Atp 安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="257b0-201">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span>

1. <span data-ttu-id="257b0-202">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理**  >  **原則**  >  **ATP 安全附件**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-202">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="257b0-203">選取 [為 **SharePoint、OneDrive 和 Microsoft 團隊開啟 ATP**] 選項。</span><span class="sxs-lookup"><span data-stu-id="257b0-203">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="257b0-204">在 [ **保護電子郵件附件** ] 區段中，按一下加號 (**+**) 。</span><span class="sxs-lookup"><span data-stu-id="257b0-204">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="257b0-205">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="257b0-205">Specify the following settings:</span></span>

   - <span data-ttu-id="257b0-206">在 [ **名稱** ] 方塊中，輸入 `Block malware` 。</span><span class="sxs-lookup"><span data-stu-id="257b0-206">In the **Name** box, type `Block malware`.</span></span>

   - <span data-ttu-id="257b0-207">在 [回應] 區段中，選擇 [ **封鎖**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-207">In the response section, choose **Block**.</span></span>

   - <span data-ttu-id="257b0-208">在 [重新 **導向附件** ] 區段中，選取 [ **啟用重新導向**] 選項。</span><span class="sxs-lookup"><span data-stu-id="257b0-208">In the **Redirect attachment** section, select the option **Enable redirect**.</span></span> <span data-ttu-id="257b0-209">指定組織的安全性系統管理員或操作員的電子郵件地址，誰會檢查偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="257b0-209">Specify the email address for your organization's security administrator or operator, who will review detected files.</span></span>

   - <span data-ttu-id="257b0-210">在 [套用 **于** ] 區段中，選擇 **[收件者網域是**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-210">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="257b0-211">然後，選取您的網域，選擇 [ **新增**]，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="257b0-211">Then, select your domain, choose **Add**, and then **OK**.</span></span>

5. <span data-ttu-id="257b0-212">**儲存**。</span><span class="sxs-lookup"><span data-stu-id="257b0-212">**Save**.</span></span>

6. <span data-ttu-id="257b0-213"> (**建議的其他步驟**) 為全域系統管理員或 SharePoint Online 管理員，請針對您的 Microsoft 365 環境，以**DisallowInfectedFileDownload**參數設定為*true* ，以執行**[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="257b0-213">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Microsoft 365 environment.</span></span> <span data-ttu-id="257b0-214"> (此方式可防止使用者開啟、移動、複製或共用偵測為惡意的檔案。 ) </span><span class="sxs-lookup"><span data-stu-id="257b0-214">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>

<span data-ttu-id="257b0-215">若要深入瞭解，請參閱 [設定 office 365 Atp 安全附件原則](set-up-atp-safe-attachments-policies.md) ，並 [為 SharePoint、OneDrive 和 Microsoft 團隊開啟 office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="257b0-215">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="257b0-216">ATP 安全連結原則</span><span class="sxs-lookup"><span data-stu-id="257b0-216">ATP Safe Links policies</span></span>

<span data-ttu-id="257b0-217">若要設定 [ATP 安全連結](atp-safe-links.md)，請複查和編輯您的預設原則，並新增特定使用者的原則。</span><span class="sxs-lookup"><span data-stu-id="257b0-217">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="257b0-218">在 [[安全性 & 規範中心](https://protection.office.com)] 中，選擇 [**威脅管理**  >  **原則**  >  **ATP 安全連結**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-218">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="257b0-219">連按兩下 **預設** 原則。</span><span class="sxs-lookup"><span data-stu-id="257b0-219">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="257b0-220">在 [ **使用安全連結** ] 區段中，選取 [ **Microsoft 365 應用程式適用于企業，Office iOS 和 Android**]，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-220">In the **Use safe links in** section, select the option **Microsoft 365 Apps for enterprise, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="257b0-221">在 [套用 **至特定** 收件者的原則] 區段中，按一下加號 (**+**) 。</span><span class="sxs-lookup"><span data-stu-id="257b0-221">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="257b0-222">指定下列設定：</span><span class="sxs-lookup"><span data-stu-id="257b0-222">Specify the following settings:</span></span>

   - <span data-ttu-id="257b0-223">在 [ **名稱** ] 方塊中，輸入名稱，例如 `Safe Links` 。</span><span class="sxs-lookup"><span data-stu-id="257b0-223">In the **Name** box, type a name, such as `Safe Links`.</span></span>

   - <span data-ttu-id="257b0-224">在 [選取動作]\*\*\*\* 區段中，選擇 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="257b0-224">In the **Select the action** section, choose **On**.</span></span>

   - <span data-ttu-id="257b0-225">選取下列選項：</span><span class="sxs-lookup"><span data-stu-id="257b0-225">Select these options:</span></span>

     - <span data-ttu-id="257b0-226">**使用安全附件掃描可下載的內容**</span><span class="sxs-lookup"><span data-stu-id="257b0-226">**Use safe attachments to scan downloadable content**</span></span>

     - <span data-ttu-id="257b0-227">**對組織內傳送的電子郵件套用安全連結**</span><span class="sxs-lookup"><span data-stu-id="257b0-227">**Apply safe links to email messages sent within the organization**</span></span>

     - <span data-ttu-id="257b0-228">**不要讓使用者點擊至原始 URL 的安全連結**</span><span class="sxs-lookup"><span data-stu-id="257b0-228">**Do not let users click through safe links to original URL**</span></span>

   - <span data-ttu-id="257b0-229">在 [套用 **于** ] 區段中，選擇 **[收件者網域是**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-229">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="257b0-230">然後，選取您的網域，選擇 [ **新增**]，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="257b0-230">Then, select your domain, choose **Add**, and then **OK**.</span></span>

6. <span data-ttu-id="257b0-231">**儲存**。</span><span class="sxs-lookup"><span data-stu-id="257b0-231">**Save**.</span></span>

<span data-ttu-id="257b0-232">若要深入了解，請參閱[設定 Office 365 ATP 安全連結原則](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="257b0-232">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

## <a name="part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads"></a><span data-ttu-id="257b0-233">第5部分-開啟 SharePoint、OneDrive 和 Microsoft 小組工作負載的 ATP</span><span class="sxs-lookup"><span data-stu-id="257b0-233">Part 5 - Turn on ATP for SharePoint, OneDrive, and Microsoft Teams workloads</span></span>

<span data-ttu-id="257b0-234">SharePoint、OneDrive 和小組等工作負載都是為了共同作業而建立的。</span><span class="sxs-lookup"><span data-stu-id="257b0-234">Workloads like SharePoint, OneDrive, and Teams are built for collaboration.</span></span> <span data-ttu-id="257b0-235">使用 ATP 可協助封鎖和偵測小組網站和文件庫中識別為惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="257b0-235">Using ATP helps with blocking and detection of files that are identified as malicious in team sites and document libraries.</span></span> <span data-ttu-id="257b0-236">您可以在 [這裡](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide)進一步閱讀該功能的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="257b0-236">You can read more about how that works [here](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="257b0-237">**開始此程式之前，請確定已為您的 Microsoft 365 環境開啟了審核記錄**。</span><span class="sxs-lookup"><span data-stu-id="257b0-237">**Before you begin this procedure, make sure that audit logging is already turned on for your Microsoft 365 environment**.</span></span> <span data-ttu-id="257b0-238">這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。</span><span class="sxs-lookup"><span data-stu-id="257b0-238">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="257b0-239">如需詳細資訊，請參閱 [開啟或關閉審核記錄搜尋](../../compliance/turn-audit-log-search-on-or-off.md)！</span><span class="sxs-lookup"><span data-stu-id="257b0-239">For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)!</span></span>

1. <span data-ttu-id="257b0-240">移至 <https://protection.office.com> 然後以您的公司或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="257b0-240">Go to <https://protection.office.com>, and sign in with your work or school account.</span></span>

2. <span data-ttu-id="257b0-241">在 [安全性 & 規範中心] 的左功能窗格中，選擇 [ **威脅管理**] 底下的 [ **原則** \> **安全附件**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-241">In the Security & Compliance Center, in the left navigation pane, under **Threat management**, choose **Policy** \> **Safe Attachments**.</span></span>

   ![在 [安全性 & 規範中心] 中，選擇 [威脅管理 \> 原則]](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. <span data-ttu-id="257b0-243">選取 **[開啟適用於 SharePoint、OneDrive 與 Microsoft Teams 的 ATP]**。</span><span class="sxs-lookup"><span data-stu-id="257b0-243">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

   ![開啟適用於 SharePoint Online、商務用 OneDrive 與 Microsoft Teams 的進階威脅防護](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. <span data-ttu-id="257b0-245">**儲存**。</span><span class="sxs-lookup"><span data-stu-id="257b0-245">**Save**.</span></span>

5. <span data-ttu-id="257b0-246">檢閱 (並視需要編輯) 組織的 [[安全附件原則]](set-up-atp-safe-attachments-policies.md) 和 [[安全連結原則]](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="257b0-246">Review (and, as appropriate, edit) your organization's [Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

6. <span data-ttu-id="257b0-247"> (建議) 成為全域系統管理員或 SharePoint Online 管理員，請執行 **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** Cmdlet，並將 _DisallowInfectedFileDownload_ 參數設定為 *true*。</span><span class="sxs-lookup"><span data-stu-id="257b0-247">(Recommended) As a global administrator or a SharePoint Online administrator, run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet with the _DisallowInfectedFileDownload_ parameter set to *true*.</span></span>

   - <span data-ttu-id="257b0-248">將參數設定為 *true* 可封鎖偵測到的檔案的所有動作 (刪除除外)。</span><span class="sxs-lookup"><span data-stu-id="257b0-248">Setting the parameter to *true* blocks all actions (except Delete) for detected files.</span></span> <span data-ttu-id="257b0-249">使用者將無法開啟、移動、複製或共用偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="257b0-249">People cannot open, move, copy, or share detected files.</span></span>

   - <span data-ttu-id="257b0-250">將參數設定為 *false* 可封鎖所有動作 (刪除和下載除外)。</span><span class="sxs-lookup"><span data-stu-id="257b0-250">Setting the parameter to *false* blocks all actions except Delete and Download.</span></span> <span data-ttu-id="257b0-251">使用者可以選擇接受風險並下載偵測到的檔案。</span><span class="sxs-lookup"><span data-stu-id="257b0-251">People can choose to accept the risk and download a detected file.</span></span>
   > [!TIP] <span data-ttu-id="257b0-252">若要深入瞭解搭配 Microsoft 365 使用 PowerShell，請參閱使用 [PowerShell 管理 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="257b0-252">To learn more about using PowerShell with Microsoft 365, see [Manage Microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).</span></span>

7. <span data-ttu-id="257b0-253">允許最多30分鐘的變更，以散佈至所有 Microsoft 365 資料中心。</span><span class="sxs-lookup"><span data-stu-id="257b0-253">Allow up to 30 minutes for your changes to spread to all Microsoft 365 datacenters.</span></span>


#### <a name="now-set-up-alerts-for-detected-files"></a><span data-ttu-id="257b0-254">現在，設定偵測到檔案的警示</span><span class="sxs-lookup"><span data-stu-id="257b0-254">Now set up alerts for detected files</span></span>

<span data-ttu-id="257b0-255">若要在 SharePoint Online、商務用 OneDrive 或 Microsoft Teams 中的檔案被識別為惡意檔案時收到通知，您可以設定警示。</span><span class="sxs-lookup"><span data-stu-id="257b0-255">To receive notification when a file in SharePoint Online, OneDrive for Business, or Microsoft Teams has been identified as malicious, you can set up an alert.</span></span>

1. <span data-ttu-id="257b0-256">在 [ [安全性 & 規範中心](https://protection.office.com)] 中，選擇 [ **警示**] [ \> **管理提醒**]。</span><span class="sxs-lookup"><span data-stu-id="257b0-256">In the [Security & Compliance Center](https://protection.office.com), choose **Alerts** \> **Manage alerts**.</span></span>

2. <span data-ttu-id="257b0-257">選擇 **[新警示原則]**。</span><span class="sxs-lookup"><span data-stu-id="257b0-257">Choose **New alert policy**.</span></span>

3. <span data-ttu-id="257b0-258">指定警示的名稱。</span><span class="sxs-lookup"><span data-stu-id="257b0-258">Specify a name for the alert.</span></span> <span data-ttu-id="257b0-259">例如，您可以輸入「程式庫中的惡意檔案」。</span><span class="sxs-lookup"><span data-stu-id="257b0-259">For example, you could type Malicious Files in Libraries.</span></span>

4. <span data-ttu-id="257b0-260">輸入警示描述。</span><span class="sxs-lookup"><span data-stu-id="257b0-260">Type a description for the alert.</span></span> <span data-ttu-id="257b0-261">例如，當您在 SharePoint Online、OneDrive 或 Microsoft Teams 中偵測到惡意檔案時，您可以輸入「通知系統管理員」。</span><span class="sxs-lookup"><span data-stu-id="257b0-261">For example, you could type Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams.</span></span>

5. <span data-ttu-id="257b0-262">在 [ **傳送此警示** 的時機 ...] 區段中，設定：</span><span class="sxs-lookup"><span data-stu-id="257b0-262">In the **Send this alert when...** section, set:</span></span>

   <span data-ttu-id="257b0-263">a.</span><span class="sxs-lookup"><span data-stu-id="257b0-263">a.</span></span> <span data-ttu-id="257b0-264">在 **[活動]** 清單中，選擇 **[已偵測到檔案中的惡意程式碼]**。</span><span class="sxs-lookup"><span data-stu-id="257b0-264">In the **Activities** list, choose **Detected malware in file**.</span></span>

   <span data-ttu-id="257b0-265">b.</span><span class="sxs-lookup"><span data-stu-id="257b0-265">b.</span></span> <span data-ttu-id="257b0-266">將 **[使用者]** 欄位保留空白。</span><span class="sxs-lookup"><span data-stu-id="257b0-266">Leave the **Users** field empty.</span></span>

6. <span data-ttu-id="257b0-267">在 **[傳送此通知到...]** 區段中，選取一或多位全域系統管理員、安全性系統管理員，或在偵測到惡意檔案時應收到通知的安全性讀者。</span><span class="sxs-lookup"><span data-stu-id="257b0-267">In the **Send this alert to...** section, select one or more global administrators, security administrators, or security readers who should receive notification when a malicious file is detected.</span></span>

7. <span data-ttu-id="257b0-268">**儲存**。</span><span class="sxs-lookup"><span data-stu-id="257b0-268">**Save**.</span></span>

<span data-ttu-id="257b0-269">若要深入瞭解提醒，請參閱 [在安全性 & 規範中心建立活動警示](../../compliance/create-activity-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="257b0-269">To learn more about alerts, see [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).</span></span>

> [!NOTE]
> <span data-ttu-id="257b0-270">當您完成設定時，請使用下列連結來開始工作負載調查：</span><span class="sxs-lookup"><span data-stu-id="257b0-270">When you're finished configuring, use these links to start workload investigations:</span></span>
>- [<span data-ttu-id="257b0-271">檢視在 SharePoint、OneDrive 或 Microsoft Teams 中偵測到的惡意檔案資訊</span><span class="sxs-lookup"><span data-stu-id="257b0-271">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
>- [<span data-ttu-id="257b0-272">在 SharePoint 線上、OneDrive 或 Microsoft 小組中找到惡意檔案時，要執行的動作</span><span class="sxs-lookup"><span data-stu-id="257b0-272">What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams</span></span>](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [<span data-ttu-id="257b0-273">在 Microsoft 365 中以系統管理員身分管理被隔離的郵件和檔案</span><span class="sxs-lookup"><span data-stu-id="257b0-273">Manage quarantined messages and files as an administrator in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md) 

## <a name="part-6---additional-settings-to-configure"></a><span data-ttu-id="257b0-274">第6部分-要設定的其他設定</span><span class="sxs-lookup"><span data-stu-id="257b0-274">Part 6 - Additional settings to configure</span></span>

<span data-ttu-id="257b0-275">在設定惡意程式碼、惡意 URLs 和檔案、網路釣魚和垃圾郵件的防護時，建議您設定零小時自動清除。</span><span class="sxs-lookup"><span data-stu-id="257b0-275">Along with configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend you configure zero-hour auto purge.</span></span>

### <a name="zero-hour-auto-purge-for-email-in-eop"></a><span data-ttu-id="257b0-276">EOP 中的電子郵件的自動清除零小時</span><span class="sxs-lookup"><span data-stu-id="257b0-276">Zero-hour auto purge for email in EOP</span></span>

<span data-ttu-id="257b0-277">在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的訂閱中可使用[零小時自動清除](zero-hour-auto-purge.md) (ZAP) 。</span><span class="sxs-lookup"><span data-stu-id="257b0-277">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).</span></span> <span data-ttu-id="257b0-278">此保護功能預設為開啟狀態;不過，保護生效的情況必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="257b0-278">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="257b0-279">垃圾[訊息原則](anti-spam-protection.md)中的垃圾郵件動作會設定為**將郵件移至 [垃圾郵件] 資料夾**。</span><span class="sxs-lookup"><span data-stu-id="257b0-279">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="257b0-280">使用者保留其預設的 [垃圾郵件設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)，但未關閉垃圾郵件保護。</span><span class="sxs-lookup"><span data-stu-id="257b0-280">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and haven't turned off junk email protection.</span></span>

<span data-ttu-id="257b0-281">若要深入瞭解，請參閱 [零時自動清除-防護垃圾郵件和惡意](zero-hour-auto-purge.md)代碼。</span><span class="sxs-lookup"><span data-stu-id="257b0-281">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

## <a name="post-setup-tasks-and-next-steps"></a><span data-ttu-id="257b0-282">安裝後的工作及後續步驟</span><span class="sxs-lookup"><span data-stu-id="257b0-282">Post-setup tasks and next steps</span></span>

<span data-ttu-id="257b0-283">設定威脅防護功能之後，請務必監視這些功能的運作方式！</span><span class="sxs-lookup"><span data-stu-id="257b0-283">After configuring the threat protection features, make sure to monitor how those features are working!</span></span> <span data-ttu-id="257b0-284">複查和修訂您的原則，讓他們能執行您所需的工作。</span><span class="sxs-lookup"><span data-stu-id="257b0-284">Review and revise your policies so that they do what you need them to.</span></span> <span data-ttu-id="257b0-285">此外，請留意可增加價值的新功能和服務更新。</span><span class="sxs-lookup"><span data-stu-id="257b0-285">Also, watch for new features and service updates that can add value.</span></span>

****

|<span data-ttu-id="257b0-286">處理方式</span><span class="sxs-lookup"><span data-stu-id="257b0-286">What to do</span></span>|<span data-ttu-id="257b0-287">可深入了解的資源</span><span class="sxs-lookup"><span data-stu-id="257b0-287">Resources to learn more</span></span>|
|---|---|
|<span data-ttu-id="257b0-288">查看您的組織如何使用威脅防護功能，以查看報告</span><span class="sxs-lookup"><span data-stu-id="257b0-288">See how threat protection features are working for your organization by viewing reports</span></span>|[<span data-ttu-id="257b0-289">安全性儀表板</span><span class="sxs-lookup"><span data-stu-id="257b0-289">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="257b0-290">電子郵件安全性報告</span><span class="sxs-lookup"><span data-stu-id="257b0-290">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="257b0-291">Office 365 ATP 報告</span><span class="sxs-lookup"><span data-stu-id="257b0-291">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="257b0-292">威脅總管</span><span class="sxs-lookup"><span data-stu-id="257b0-292">Threat Explorer</span></span>](threat-explorer.md)|
|<span data-ttu-id="257b0-293">視需要定期複查和修正威脅防護原則</span><span class="sxs-lookup"><span data-stu-id="257b0-293">Periodically review and revise your threat protection policies as needed</span></span>|[<span data-ttu-id="257b0-294">安全分數</span><span class="sxs-lookup"><span data-stu-id="257b0-294">Secure Score</span></span>](../mtp/microsoft-secure-score.md)<br/>[<span data-ttu-id="257b0-295">智慧報告和洞察力</span><span class="sxs-lookup"><span data-stu-id="257b0-295">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="257b0-296">Microsoft 365 威脅調查和回應功能</span><span class="sxs-lookup"><span data-stu-id="257b0-296">Microsoft 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)|
|<span data-ttu-id="257b0-297">監視新功能和服務更新</span><span class="sxs-lookup"><span data-stu-id="257b0-297">Watch for new features and service updates</span></span>|[<span data-ttu-id="257b0-298">標準及目標發行選項</span><span class="sxs-lookup"><span data-stu-id="257b0-298">Standard and Targeted release options</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[<span data-ttu-id="257b0-299">訊息中心</span><span class="sxs-lookup"><span data-stu-id="257b0-299">Message Center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[<span data-ttu-id="257b0-300">Microsoft 365 藍圖</span><span class="sxs-lookup"><span data-stu-id="257b0-300">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="257b0-301">服務說明</span><span class="sxs-lookup"><span data-stu-id="257b0-301">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|<span data-ttu-id="257b0-302">深入瞭解 EOP 和 ATP 的建議標準和嚴格安全設定的詳細資料</span><span class="sxs-lookup"><span data-stu-id="257b0-302">Learn the details about recommended Standard and Strict security configurations for EOP and ATP</span></span> | [<span data-ttu-id="257b0-303">EOP 和 Office 365 ATP 安全性的建議設定</span><span class="sxs-lookup"><span data-stu-id="257b0-303">Recommended settings for EOP and Office 365 ATP security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) |
