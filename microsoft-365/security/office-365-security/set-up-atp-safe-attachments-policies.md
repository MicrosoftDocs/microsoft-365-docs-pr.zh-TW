---
title: 在 Microsoft Defender for Office 365 中設定安全附件原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 瞭解如何定義安全附件原則，以利用電子郵件中的惡意檔來保護組織。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d48e373dc95aaa65d0f436f99208d926477aacd6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918711"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a><span data-ttu-id="1267c-103">在 Microsoft Defender for Office 365 中設定安全附件原則</span><span class="sxs-lookup"><span data-stu-id="1267c-103">Set up Safe Attachments policies in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1267c-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="1267c-104">**Applies to**</span></span>
- [<span data-ttu-id="1267c-105">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="1267c-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="1267c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1267c-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> <span data-ttu-id="1267c-107">本文適用於擁有[適用於 Office 365 的 Microsoft Defender](office-365-atp.md) 的商務客戶。</span><span class="sxs-lookup"><span data-stu-id="1267c-107">This article is intended for business customers who have [Microsoft Defender for Office 365](office-365-atp.md).</span></span> <span data-ttu-id="1267c-108">如果您是尋找 Outlook 中附件掃描相關資訊的家用使用者，請參閱 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="1267c-108">If you're a home user looking for information about attachment scanning in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="1267c-109">安全附件是 [Microsoft Defender For Office 365](office-365-atp.md) 中的一項功能，可在 [Exchange ONLINE protection (EOP) ](anti-malware-protection.md)中，但在傳送給收件者之前，使用虛擬環境檢查輸入電子郵件中的附件。</span><span class="sxs-lookup"><span data-stu-id="1267c-109">Safe Attachments is a feature in [Microsoft Defender for Office 365](office-365-atp.md) that uses a virtual environment to check attachments in inbound email messages after they've been scanned by [anti-malware protection in Exchange Online Protection (EOP)](anti-malware-protection.md), but before delivery to recipients.</span></span> <span data-ttu-id="1267c-110">如需詳細資訊，請參閱 [Microsoft Defender For Office 365 中的安全附件](atp-safe-attachments.md)。</span><span class="sxs-lookup"><span data-stu-id="1267c-110">For more information, see [Safe Attachments in Microsoft Defender for Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="1267c-111">沒有內建或預設的安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="1267c-111">There's no built-in or default Safe Attachments policy.</span></span> <span data-ttu-id="1267c-112">若要取得安全附件掃描電子郵件附件，您需要建立一個或多個安全附件原則，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="1267c-112">To get Safe Attachments scanning of email message attachments, you need to create one or more Safe Attachments policies as described in this article.</span></span>

<span data-ttu-id="1267c-113">您可以使用 Exchange Online 中的信箱，在安全性 & 合規性中心或 PowerShell (Exchange Online 365 PowerShell 中設定安全附件原則;獨立 EOP PowerShell 適用于沒有 Exchange Online 信箱的組織，但使用 Defender for Office 365 附加元件訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="1267c-113">You can configure Safe Attachments policies in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for eligible Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes, but with Defender for Office 365 add-on subscriptions).</span></span>

<span data-ttu-id="1267c-114">安全附件原則的基本元素如下：</span><span class="sxs-lookup"><span data-stu-id="1267c-114">The basic elements of a Safe Attachments policy are:</span></span>

- <span data-ttu-id="1267c-115">**安全附件原則**：指定未知惡意程式碼偵測的動作，是否要將具有惡意軟體附件的郵件傳送至指定的電子郵件地址，以及是否要在無法完成安全附件掃描時傳遞郵件。</span><span class="sxs-lookup"><span data-stu-id="1267c-115">**The safe attachment policy**: Specifies the actions for unknown malware detections, whether to send messages with malware attachments to a specified email address, and whether to deliver messages if Safe Attachments scanning can't complete.</span></span>
- <span data-ttu-id="1267c-116">**安全附件規則**：指定原則套用至) 的優先順序和收件者篩選 (。</span><span class="sxs-lookup"><span data-stu-id="1267c-116">**The safe attachment rule**: Specifies the priority and recipient filters (who the policy applies to).</span></span>

<span data-ttu-id="1267c-117">當您在安全性 & 合規性中心管理安全附件原則時，這兩個元素之間的差異並不明顯：</span><span class="sxs-lookup"><span data-stu-id="1267c-117">The difference between these two elements isn't obvious when you manage Safe Attachments polices in the Security & Compliance Center:</span></span>

- <span data-ttu-id="1267c-118">當您建立安全附件原則時，實際上是同時建立安全附件規則和相關聯的安全附件原則，同時為這兩者使用相同的名稱。</span><span class="sxs-lookup"><span data-stu-id="1267c-118">When you create a Safe Attachments policy, you're actually creating a safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>
- <span data-ttu-id="1267c-119">當您修改安全附件原則時，與名稱、優先順序、啟用或停用的設定或收件者篩選器相關的設定會修改安全附件規則。</span><span class="sxs-lookup"><span data-stu-id="1267c-119">When you modify a Safe Attachments policy, settings related to the name, priority, enabled or disabled, and recipient filters modify the safe attachment rule.</span></span> <span data-ttu-id="1267c-120">所有其他設定會修改關聯的安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="1267c-120">All other settings modify the associated safe attachment policy.</span></span>
- <span data-ttu-id="1267c-121">當您移除安全附件原則時，會移除安全附件規則和相關聯的安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="1267c-121">When you remove a Safe Attachments policy, the safe attachment rule and the associated safe attachment policy are removed.</span></span>

<span data-ttu-id="1267c-122">在 Exchange Online PowerShell 或獨立 EOP PowerShell 中，您可以個別管理原則和規則。</span><span class="sxs-lookup"><span data-stu-id="1267c-122">In Exchange Online PowerShell or standalone EOP PowerShell, you manage the policy and the rule separately.</span></span> <span data-ttu-id="1267c-123">如需詳細資訊，請參閱本文稍後的 [使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定安全附件原則](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) 一節。</span><span class="sxs-lookup"><span data-stu-id="1267c-123">For more information, see the [Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) section later in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="1267c-124">在 [安全附件設定] 的 [全域設定] 區域中，設定不會相依于安全附件原則的功能。</span><span class="sxs-lookup"><span data-stu-id="1267c-124">In the global settings area of Safe Attachments settings, you configure features that are not dependent on Safe Attachments policies.</span></span> <span data-ttu-id="1267c-125">如需相關指示，請參閱在[microsoft 365 E5 中](safe-docs.md)[開啟 SharePoint、OneDrive 和 Microsoft 小組和安全檔的安全附件](turn-on-atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="1267c-125">For instructions see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) and [Safe Documents in Microsoft 365 E5](safe-docs.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1267c-126">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="1267c-126">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1267c-127">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="1267c-127">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1267c-128">若要直接移至 [ **安全附件** ] 頁面，請使用 <https://protection.office.com/safeattachmentv2> 。</span><span class="sxs-lookup"><span data-stu-id="1267c-128">To go directly to the **Safe Attachments** page, use <https://protection.office.com/safeattachmentv2>.</span></span>

- <span data-ttu-id="1267c-129">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1267c-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="1267c-130">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="1267c-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1267c-131">您必須已獲指派許可權，才能執行本文中的程式：</span><span class="sxs-lookup"><span data-stu-id="1267c-131">You need to be assigned permissions before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="1267c-132">若要建立、修改和刪除安全附件原則，您必須是 Security & 合規性中心內的「 **組織管理** 」或「 **安全性管理員** 」角色群組成員， **以及** Exchange Online 中的「 **組織管理** 」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1267c-132">To create, modify, and delete Safe Attachments policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups in the Security & Compliance Center **and** a member of the **Organization Management** role group in Exchange Online.</span></span>
  - <span data-ttu-id="1267c-133">針對安全附件原則的唯讀存取，您必須是「安全性 & 規範中心」中 **全域讀取** 者或 **安全性讀取器** 角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1267c-133">For read-only access to Safe Attachments policies, you need to be a member of the **Global Reader** or **Security Reader** role groups in the Security & Compliance Center.</span></span>

  <span data-ttu-id="1267c-134">如需詳細資訊，請參閱 [安全性 & 合規性中心的許可權](permissions-in-the-security-and-compliance-center.md) 和 [Exchange Online 中的許可權](/exchange/permissions-exo/permissions-exo)。</span><span class="sxs-lookup"><span data-stu-id="1267c-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="1267c-135">**附註**：</span><span class="sxs-lookup"><span data-stu-id="1267c-135">**Notes**:</span></span>

  - <span data-ttu-id="1267c-136">在 Microsoft 365 系統管理中心中，將使用者新增至對應的 Azure Active Directory 角色可為使用者提供 [安全性與合規性中心] 所需的權限 _和_ Microsoft 365 中其他功能的權限。</span><span class="sxs-lookup"><span data-stu-id="1267c-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="1267c-137">如需詳細資訊，請參閱[關於系統管理員角色](../../admin/add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="1267c-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="1267c-138">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **僅限檢視組織管理** 角色群組也會提供功能的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="1267c-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="1267c-139">如需安全附件原則的建議設定，請參閱 [安全附件設定](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="1267c-139">For our recommended settings for Safe Attachments policies, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

- <span data-ttu-id="1267c-140">最多允許30分鐘，以套用新的或更新的原則。</span><span class="sxs-lookup"><span data-stu-id="1267c-140">Allow up to 30 minutes for a new or updated policy to be applied.</span></span>

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a><span data-ttu-id="1267c-141">使用安全性 & 規範中心建立安全附件原則</span><span class="sxs-lookup"><span data-stu-id="1267c-141">Use the Security & Compliance Center to create Safe Attachments policies</span></span>

<span data-ttu-id="1267c-142">在安全性 & 合規性中心建立自訂安全附件原則，會同時使用相同的名稱建立安全附件規則和相關聯的安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="1267c-142">Creating a custom Safe Attachments policy in the Security & Compliance Center creates the safe attachment rule and the associated safe attachment policy at the same time using the same name for both.</span></span>

1. <span data-ttu-id="1267c-143">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="1267c-143">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="1267c-144">在 [ **安全附件** ] 頁面上，按一下 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="1267c-144">On the **Safe Attachments** page, click **Create**.</span></span>

3. <span data-ttu-id="1267c-145">[ **新增安全附件原則** ] 嚮導隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="1267c-145">The **New Safe Attachments policy** wizard opens.</span></span> <span data-ttu-id="1267c-146">在 [ **命名您的原則** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="1267c-146">On the **Name your policy** page, configure the following settings:</span></span>

   - <span data-ttu-id="1267c-147">**名稱**：輸入原則的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="1267c-147">**Name**: Enter a unique, descriptive name for the policy.</span></span>

   - <span data-ttu-id="1267c-148">**說明**：輸入原則的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="1267c-148">**Description**: Enter an optional description for the policy.</span></span>

   <span data-ttu-id="1267c-149">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="1267c-149">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="1267c-150">在顯示的 [ **設定** ] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="1267c-150">On the **Settings** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="1267c-151">**安全附件未知的惡意程式碼回應**：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="1267c-151">**Safe Attachments unknown malware response**: Select one of the following values:</span></span>

     - <span data-ttu-id="1267c-152">**Off**：一般而言，我們不建議此值。</span><span class="sxs-lookup"><span data-stu-id="1267c-152">**Off**: Typically, we don't recommend this value.</span></span>
     - <span data-ttu-id="1267c-153">**監視**</span><span class="sxs-lookup"><span data-stu-id="1267c-153">**Monitor**</span></span>
     - <span data-ttu-id="1267c-154">**封鎖**：這是預設值，以及標準及嚴格的預設 [安全性原則](preset-security-policies.md)中的建議值。</span><span class="sxs-lookup"><span data-stu-id="1267c-154">**Block**: This is the default value, and the recommended value in Standard and Strict [preset security policies](preset-security-policies.md).</span></span>
     - <span data-ttu-id="1267c-155">**Replace**</span><span class="sxs-lookup"><span data-stu-id="1267c-155">**Replace**</span></span>
     - <span data-ttu-id="1267c-156">**動態傳遞 (預覽功能)**</span><span class="sxs-lookup"><span data-stu-id="1267c-156">**Dynamic Delivery (Preview Feature)**</span></span>

     <span data-ttu-id="1267c-157">這些值會在 [安全附件原則設定](atp-safe-attachments.md#safe-attachments-policy-settings)中說明。</span><span class="sxs-lookup"><span data-stu-id="1267c-157">These values are explained in [Safe Attachments policy settings](atp-safe-attachments.md#safe-attachments-policy-settings).</span></span>

   - <span data-ttu-id="1267c-158">**將附件傳送至下列電子郵件地址**：針對動作值 **封鎖**、 **監視** 或 **取代**，您可以選取 [ **啟用重新導向** ] 以傳送包含惡意軟體附件的郵件，以進行分析和調查的指定內部或外部電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1267c-158">**Send the attachment to the following email address**: For the action values **Block**, **Monitor**, or **Replace**, you can select **Enable redirect** to send messages that contain malware attachments to the specified internal or external email address for analysis and investigation.</span></span>

     <span data-ttu-id="1267c-159">標準和嚴格原則設定的建議是啟用重新定向。</span><span class="sxs-lookup"><span data-stu-id="1267c-159">The recommendation for Standard and Strict policy settings is to enable redirection.</span></span> <span data-ttu-id="1267c-160">如需詳細資訊，請參閱 [安全附件設定](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。</span><span class="sxs-lookup"><span data-stu-id="1267c-160">For more information, see [Safe Attachments settings](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings).</span></span>

   - <span data-ttu-id="1267c-161">**若惡意程式碼掃描附件超時或發生錯誤，請套用上述選取專案**。安全附件所指定的動作會對郵件採取 **未知惡意程式碼回應** ，即使無法完成安全附件掃描也是一樣。</span><span class="sxs-lookup"><span data-stu-id="1267c-161">**Apply the above selection if malware scanning for attachments times out or error occurs**: The action specified by **Safe Attachments unknown malware response** is taken on messages even when Safe Attachments scanning can't complete.</span></span> <span data-ttu-id="1267c-162">如果您選取此選項，請永遠選取 [ **已啟用重新導向**]。</span><span class="sxs-lookup"><span data-stu-id="1267c-162">If you selected this option, always select **Enabled redirect**.</span></span> <span data-ttu-id="1267c-163">否則，郵件可能會遺失。</span><span class="sxs-lookup"><span data-stu-id="1267c-163">Otherwise, messages might be lost.</span></span>

   <span data-ttu-id="1267c-164">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="1267c-164">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="1267c-165">在出現的 [套用 **至** ] 頁面上，識別套用原則的內部收件者。</span><span class="sxs-lookup"><span data-stu-id="1267c-165">On the **Applied to** page that appears, identify the internal recipients that the policy applies to.</span></span>

   <span data-ttu-id="1267c-166">您只能使用一個條件或一個例外狀況，但可以為條件或例外狀況指定多個值。</span><span class="sxs-lookup"><span data-stu-id="1267c-166">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="1267c-167">相同條件或例外狀況的多個值使用 OR 邏輯 (例如，_\<recipient1\>_ 或 _\<recipient2\>_)。</span><span class="sxs-lookup"><span data-stu-id="1267c-167">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="1267c-168">不同的條件或例外狀況則使用 AND 邏輯 (例如，_\<recipient1\>_ 和 _\<member of group 1\>_)。</span><span class="sxs-lookup"><span data-stu-id="1267c-168">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

   <span data-ttu-id="1267c-169">按一下 [ **新增條件**]。</span><span class="sxs-lookup"><span data-stu-id="1267c-169">Click **Add a condition**.</span></span> <span data-ttu-id="1267c-170">在出現的下拉式清單中，選取 [ **適用于** 下列條件的條件：</span><span class="sxs-lookup"><span data-stu-id="1267c-170">In the dropdown that appears, select a condition under **Applied if**:</span></span>

   - <span data-ttu-id="1267c-171">**收件者是**：指定您組織中的一或多個信箱、郵件使用者或郵件連絡人。</span><span class="sxs-lookup"><span data-stu-id="1267c-171">**The recipient is**: Specifies one or more mailboxes, mail users, or mail contacts in your organization.</span></span>
   - <span data-ttu-id="1267c-172">**收件者以成員的身分存在於**：指定您組織中的一或多個群組。</span><span class="sxs-lookup"><span data-stu-id="1267c-172">**The recipient is a member of**: Specifies one or more groups in your organization.</span></span>
   - <span data-ttu-id="1267c-173">**收件者網域為**：指定組織中一或多個已設定公認網域中的收件者。</span><span class="sxs-lookup"><span data-stu-id="1267c-173">**The recipient domain is**: Specifies recipients in one or more of the configured accepted domains in your organization.</span></span>

   <span data-ttu-id="1267c-174">選取條件後，會出現對應的下拉式清單，其中有 **其中** 一個方塊。</span><span class="sxs-lookup"><span data-stu-id="1267c-174">After you select the condition, a corresponding dropdown appears with an **Any of these** box.</span></span>

   - <span data-ttu-id="1267c-175">在方塊中按一下，並在值清單中向內移動，以選取。</span><span class="sxs-lookup"><span data-stu-id="1267c-175">Click in the box and scroll through the list of values to select.</span></span>
   - <span data-ttu-id="1267c-176">按一下方塊中的 [開始輸入]，以篩選清單並選取值。</span><span class="sxs-lookup"><span data-stu-id="1267c-176">Click in the box and start typing to filter the list and select a value.</span></span>
   - <span data-ttu-id="1267c-177">若要新增其他值，請按一下方塊中的空白區域。</span><span class="sxs-lookup"><span data-stu-id="1267c-177">To add additional values, click in an empty area in the box.</span></span>
   - <span data-ttu-id="1267c-178">若要移除個別專案， 請按一下 ![ ](../../media/scc-remove-icon.png) 值上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="1267c-178">To remove individual entries, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the value.</span></span>
   - <span data-ttu-id="1267c-179">若要移除整個條件，請按一下 ![ ](../../media/scc-remove-icon.png) 條件上的 [移除移除圖示]。</span><span class="sxs-lookup"><span data-stu-id="1267c-179">To remove the whole condition, click **Remove** ![Remove icon](../../media/scc-remove-icon.png) on the condition.</span></span>

   <span data-ttu-id="1267c-180">若要新增其他條件，請按一下 [ **新增條件** ]，然後選取 [套用 **于 if** 中的剩餘值]。</span><span class="sxs-lookup"><span data-stu-id="1267c-180">To add an additional condition, click **Add a condition** and select a remaining value under **Applied if**.</span></span>

   <span data-ttu-id="1267c-181">若要新增例外狀況，請按一下 [ **新增條件** ]，然後選取 [ **除外 if**] 底下的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="1267c-181">To add exceptions, click **Add a condition** and select an exception under **Except if**.</span></span> <span data-ttu-id="1267c-182">設定和行為就像是條件。</span><span class="sxs-lookup"><span data-stu-id="1267c-182">The settings and behavior are exactly like the conditions.</span></span>

   <span data-ttu-id="1267c-183">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="1267c-183">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="1267c-184">在 [ **複查您的設定** ] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="1267c-184">On the **Review your settings** page that appears, review your settings.</span></span> <span data-ttu-id="1267c-185">您可以按一下每個設定的 [ **編輯** ] 進行修改。</span><span class="sxs-lookup"><span data-stu-id="1267c-185">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="1267c-186">完成後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="1267c-186">When you're finished, click **Finish**.</span></span>

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a><span data-ttu-id="1267c-187">使用安全性 & 規範中心來查看安全附件原則</span><span class="sxs-lookup"><span data-stu-id="1267c-187">Use the Security & Compliance Center to view Safe Attachments policies</span></span>

1. <span data-ttu-id="1267c-188">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="1267c-188">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="1267c-189">在 [ **安全附件** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1267c-189">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

   <span data-ttu-id="1267c-190">「即時」顯示原則詳細資料</span><span class="sxs-lookup"><span data-stu-id="1267c-190">The policy details appear in a fly out</span></span>

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a><span data-ttu-id="1267c-191">使用安全性 & 規範中心來修改安全附件原則</span><span class="sxs-lookup"><span data-stu-id="1267c-191">Use the Security & Compliance Center to modify Safe Attachments policies</span></span>

1. <span data-ttu-id="1267c-192">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="1267c-192">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="1267c-193">在 [ **安全附件** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1267c-193">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="1267c-194">在 [原則詳細資料] 顯示的 [飛出] 中，按一下 [ **編輯原則**]。</span><span class="sxs-lookup"><span data-stu-id="1267c-194">In the policy details fly out that appears, click **Edit policy**.</span></span>

<span data-ttu-id="1267c-195">[飛出] 中的可用設定與 [ [使用安全性 & 規範中心] 建立安全附件原則](#use-the-security--compliance-center-to-create-safe-attachments-policies) 一節中所述的相同。</span><span class="sxs-lookup"><span data-stu-id="1267c-195">The available settings in the fly out that appears are identical to those described in the [Use the Security & Compliance Center to create Safe Attachments policies](#use-the-security--compliance-center-to-create-safe-attachments-policies) section.</span></span>

<span data-ttu-id="1267c-196">若要啟用或停用原則或設定原則優先順序順序，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="1267c-196">To enable or disable a policy or set the policy priority order, see the following sections.</span></span>

### <a name="enable-or-disable-safe-attachments-policies"></a><span data-ttu-id="1267c-197">啟用或停用安全附件原則</span><span class="sxs-lookup"><span data-stu-id="1267c-197">Enable or disable Safe Attachments policies</span></span>

1. <span data-ttu-id="1267c-198">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="1267c-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="1267c-199">請注意 [ **狀態** ] 欄中的值：</span><span class="sxs-lookup"><span data-stu-id="1267c-199">Notice the value in the **Status** column:</span></span>

   - <span data-ttu-id="1267c-200">將切換向左移動</span><span class="sxs-lookup"><span data-stu-id="1267c-200">Move the toggle to the left</span></span> ![關閉原則](../../media/scc-toggle-off.png) <span data-ttu-id="1267c-202">停用原則。</span><span class="sxs-lookup"><span data-stu-id="1267c-202">to disable the policy.</span></span>

   - <span data-ttu-id="1267c-203">向右移動切換</span><span class="sxs-lookup"><span data-stu-id="1267c-203">Move the toggle to the right</span></span> ![開啟原則](../../media/scc-toggle-on.png) <span data-ttu-id="1267c-205">以啟用原則。</span><span class="sxs-lookup"><span data-stu-id="1267c-205">to enable the policy.</span></span>

### <a name="set-the-priority-of-safe-attachments-policies"></a><span data-ttu-id="1267c-206">設定安全附件原則的優先順序</span><span class="sxs-lookup"><span data-stu-id="1267c-206">Set the priority of Safe Attachments policies</span></span>

<span data-ttu-id="1267c-207">根據預設，安全附件原則的優先順序會根據它們在 (較舊的原則中所建立的順序而降低優先順序) 。</span><span class="sxs-lookup"><span data-stu-id="1267c-207">By default, Safe Attachments policies are given a priority that's based on the order they were created in (newer polices are lower priority than older policies).</span></span> <span data-ttu-id="1267c-208">較小的優先順序數字表示原則的優先順序較高 (0 最高)，原則是依據優先順序進行處理，較高優先順序的原則會在較低優先順序的原則前面進行處理。</span><span class="sxs-lookup"><span data-stu-id="1267c-208">A lower priority number indicates a higher priority for the policy (0 is the highest), and policies are processed in priority order (higher priority policies are processed before lower priority policies).</span></span> <span data-ttu-id="1267c-209">不論有幾個原則，都不會具有相同的優先順序，且在套用第一個原則之後，原則處理就會停止。</span><span class="sxs-lookup"><span data-stu-id="1267c-209">No two policies can have the same priority, and policy processing stops after the first policy is applied.</span></span>

<span data-ttu-id="1267c-210">如需更多有關優先的排序及如何評估和應用多項原則，請參照 [電子郵件保護的順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="1267c-210">For more information about the order of precedence and how multiple policies are evaluated and applied, see [Order and precedence of email protection](how-policies-and-protections-are-combined.md).</span></span>

<span data-ttu-id="1267c-211">安全附件原則會以處理的順序顯示， (第一個原則的 **Priority** 值為 0) 。</span><span class="sxs-lookup"><span data-stu-id="1267c-211">Safe Attachments policies are displayed in the order they're processed (the first policy has the **Priority** value 0).</span></span>

<span data-ttu-id="1267c-212">**附注**：在 [安全性 & 規範中心] 中，您只能在建立安全附件原則之後變更其優先順序。</span><span class="sxs-lookup"><span data-stu-id="1267c-212">**Note**: In the Security & Compliance Center, you can only change the priority of the Safe Attachments policy after you create it.</span></span> <span data-ttu-id="1267c-213">在 PowerShell 中，您可以在建立安全附件規則時覆寫預設優先順序 (這會影響現有規則) 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="1267c-213">In PowerShell, you can override the default priority when you create the safe attachment rule (which can affect the priority of existing rules).</span></span>

<span data-ttu-id="1267c-214">若要變更原則的優先順序，請在清單中將原則上移或下移 (您無法在安全性與合規性中心直接修改 [優先順序] 數字)。</span><span class="sxs-lookup"><span data-stu-id="1267c-214">To change the priority of a policy, move the policy up or down in the list (you can't directly modify the **Priority** number in the Security & Compliance Center).</span></span>

1. <span data-ttu-id="1267c-215">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="1267c-215">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="1267c-216">在 [ **安全附件** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1267c-216">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="1267c-217">在顯示的 [原則詳細資料] 中，按一下 [可用的優先順序] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1267c-217">In the policy details fly out that appears, click the available priority button.</span></span>

   - <span data-ttu-id="1267c-218">**優先順序** 值為 **0** 的安全附件原則只有「**降低優先順序**」按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="1267c-218">The Safe Attachments policy with the **Priority** value **0** has only the **Decrease priority** button available.</span></span>

   - <span data-ttu-id="1267c-219">具有最低 **優先順序** 值的安全附件原則 (例如， **3**) 只有 [ **增加優先順序** ] 按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="1267c-219">The Safe Attachments policy with the lowest **Priority** value (for example, **3**) has only the **Increase priority** button available.</span></span>

   - <span data-ttu-id="1267c-220">如果您有三個或更多安全附件原則，則最高和最低優先順序值之間的原則都有可用的 [ **增加優先順序** ] 和 [ **降低優先順序** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1267c-220">If you have three or more Safe Attachments policies, policies between the highest and lowest priority values have both the **Increase priority** and **Decrease priority** buttons available.</span></span>

4. <span data-ttu-id="1267c-221">按一下 [ **增加優先順序** ] 或 [ **降低優先順序** ] 以變更 [ **優先順序** ] 值。</span><span class="sxs-lookup"><span data-stu-id="1267c-221">Click **Increase priority** or **Decrease priority** to change the **Priority** value.</span></span>

5. <span data-ttu-id="1267c-222">完成時，請按一下 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="1267c-222">When you're finished, click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a><span data-ttu-id="1267c-223">使用安全性 & 規範中心移除安全附件原則</span><span class="sxs-lookup"><span data-stu-id="1267c-223">Use the Security & Compliance Center to remove Safe Attachments policies</span></span>

1. <span data-ttu-id="1267c-224">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="1267c-224">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span>

2. <span data-ttu-id="1267c-225">在 [ **安全附件** ] 頁面上，從清單中選取一個原則，並按一下該原則 (不要) 選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="1267c-225">On the **Safe Attachments** page, select a policy from the list and click on it (don't select the check box).</span></span>

3. <span data-ttu-id="1267c-226">在顯示的 [原則詳細資料] 中，按一下 [ **刪除原則**]，然後在出現的警告對話方塊中按一下 [ **是]** 。</span><span class="sxs-lookup"><span data-stu-id="1267c-226">In the policy details fly out that appears, click **Delete policy**, and then click **Yes** in the warning dialog that appears.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a><span data-ttu-id="1267c-227">使用 Exchange Online PowerShell 或獨立 EOP PowerShell 設定安全附件原則</span><span class="sxs-lookup"><span data-stu-id="1267c-227">Use Exchange Online PowerShell or standalone EOP PowerShell to configure Safe Attachments policies</span></span>

<span data-ttu-id="1267c-228">如先前所述，安全附件原則是由安全附件原則和安全附件規則所組成。</span><span class="sxs-lookup"><span data-stu-id="1267c-228">As previously described, a Safe Attachments policy consists of a safe attachment policy and a safe attachment rule.</span></span>

<span data-ttu-id="1267c-229">在 PowerShell 中，安全附件原則與安全附件規則之間的差異很明顯。</span><span class="sxs-lookup"><span data-stu-id="1267c-229">In PowerShell, the difference between safe attachment policies and safe attachment rules is apparent.</span></span> <span data-ttu-id="1267c-230">您可以使用 **\* -SafeAttachmentPolicy** Cmdlet 來管理安全附件原則，也可以使用 **\* -SafeAttachmentRule** Cmdlet 來管理安全附件規則。</span><span class="sxs-lookup"><span data-stu-id="1267c-230">You manage safe attachment policies by using the **\*-SafeAttachmentPolicy** cmdlets, and you manage safe attachment rules by using the **\*-SafeAttachmentRule** cmdlets.</span></span>

- <span data-ttu-id="1267c-231">在 PowerShell 中，您先建立安全附件原則，然後建立可識別套用規則之原則的安全附件規則。</span><span class="sxs-lookup"><span data-stu-id="1267c-231">In PowerShell, you create the safe attachment policy first, then you create the safe attachment rule that identifies the policy that the rule applies to.</span></span>
- <span data-ttu-id="1267c-232">在 PowerShell 中，您可以分別修改安全附件原則和安全附件規則中的設定。</span><span class="sxs-lookup"><span data-stu-id="1267c-232">In PowerShell, you modify the settings in the safe attachment policy and the safe attachment rule separately.</span></span>
- <span data-ttu-id="1267c-233">當您從 PowerShell 中移除安全附件原則時，不會自動移除對應的安全附件規則，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="1267c-233">When you remove a safe attachment policy from PowerShell, the corresponding safe attachment rule isn't automatically removed, and vice versa.</span></span>

### <a name="use-powershell-to-create-safe-attachments-policies"></a><span data-ttu-id="1267c-234">使用 PowerShell 建立安全附件原則</span><span class="sxs-lookup"><span data-stu-id="1267c-234">Use PowerShell to create Safe Attachments policies</span></span>

<span data-ttu-id="1267c-235">在 PowerShell 中建立安全附件原則的過程包括兩個步驟：</span><span class="sxs-lookup"><span data-stu-id="1267c-235">Creating a Safe Attachments policy in PowerShell is a two-step process:</span></span>

1. <span data-ttu-id="1267c-236">建立安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="1267c-236">Create the safe attachment policy.</span></span>
2. <span data-ttu-id="1267c-237">建立安全附件規則，以指定套用規則的安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="1267c-237">Create the safe attachment rule that specifies the safe attachment policy that the rule applies to.</span></span>

 <span data-ttu-id="1267c-238">**附註**：</span><span class="sxs-lookup"><span data-stu-id="1267c-238">**Notes**:</span></span>

- <span data-ttu-id="1267c-239">您可以建立新的安全附件規則，並將現有的、未關聯的安全附件原則指派給它。</span><span class="sxs-lookup"><span data-stu-id="1267c-239">You can create a new safe attachment rule and assign an existing, unassociated safe attachment policy to it.</span></span> <span data-ttu-id="1267c-240">安全附件規則無法與一個以上的安全附件原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="1267c-240">A safe attachment rule can't be associated with more than one safe attachment policy.</span></span>

- <span data-ttu-id="1267c-241">您可以在 PowerShell 中的新安全附件原則上設定下列設定，而這些原則在安全性 & 合規性中心內無法使用，直到您建立原則為止：</span><span class="sxs-lookup"><span data-stu-id="1267c-241">You can configure the following settings on new safe attachment policies in PowerShell that aren't available in the Security & Compliance Center until after you create the policy:</span></span>
  - <span data-ttu-id="1267c-242">_在_ `$false` **New-SafeAttachmentRule** Cmdlet) 上，建立新原則做為已停用 (。</span><span class="sxs-lookup"><span data-stu-id="1267c-242">Create the new policy as disabled (_Enabled_ `$false` on the **New-SafeAttachmentRule** cmdlet).</span></span>
  - <span data-ttu-id="1267c-243">在 _\<Number\>_ **New-SafeAttachmentRule** Cmdlet) 上建立 (優先順序) 時，設定原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="1267c-243">Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-SafeAttachmentRule** cmdlet).</span></span>

- <span data-ttu-id="1267c-244">在您將原則指派至安全附件規則之前，您在 PowerShell 中建立的新安全附件原則不會顯示在安全性 & 規範中心。</span><span class="sxs-lookup"><span data-stu-id="1267c-244">A new safe attachment policy that you create in PowerShell isn't visible in the Security & Compliance Center until you assign the policy to a safe attachment rule.</span></span>

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a><span data-ttu-id="1267c-245">步驟1：使用 PowerShell 建立安全附件原則</span><span class="sxs-lookup"><span data-stu-id="1267c-245">Step 1: Use PowerShell to create a safe attachment policy</span></span>

<span data-ttu-id="1267c-246">若要建立安全附件原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1267c-246">To create a safe attachment policy, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

<span data-ttu-id="1267c-247">此範例會建立名為 Contoso 的安全附件原則，並提供下列值：</span><span class="sxs-lookup"><span data-stu-id="1267c-247">This example creates a safe attachment policy named Contoso All with the following values:</span></span>

- <span data-ttu-id="1267c-248">封鎖透過安全檔所找到之惡意程式碼的郵件掃描 (我們不會使用 _Action_ 參數，而且預設值是 `Block`) 。</span><span class="sxs-lookup"><span data-stu-id="1267c-248">Block messages that are found to contain malware by Safe Documents scanning (we aren't using the _Action_ parameter, and the default value is `Block`).</span></span>
- <span data-ttu-id="1267c-249">已啟用重新導向，而且找到包含惡意程式碼的郵件會傳送至 sec-ops@contoso.com 進行分析和調查。</span><span class="sxs-lookup"><span data-stu-id="1267c-249">Redirection is enabled, and messages that are found to contain malware are sent to sec-ops@contoso.com for analysis and investigation.</span></span>
- <span data-ttu-id="1267c-250">如果安全附件掃描無法使用或遇到錯誤，請勿傳遞郵件 (不是使用 _ActionOnError_ 參數，預設值則是 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="1267c-250">If Safe Attachments scanning isn't available or encounters errors, don't deliver the message (we aren't using the _ActionOnError_ parameter, and the default value is `$true`).</span></span>

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

<span data-ttu-id="1267c-251">如需詳細的語法及參數資訊，請參閱 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="1267c-251">For detailed syntax and parameter information, see [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy).</span></span>

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a><span data-ttu-id="1267c-252">步驟2：使用 PowerShell 建立安全附件規則</span><span class="sxs-lookup"><span data-stu-id="1267c-252">Step 2: Use PowerShell to create a safe attachment rule</span></span>

<span data-ttu-id="1267c-253">若要建立安全附件規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1267c-253">To create a safe attachment rule, use this syntax:</span></span>

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

<span data-ttu-id="1267c-254">此範例會建立名為 Contoso 的安全附件規則，且具有下列條件：</span><span class="sxs-lookup"><span data-stu-id="1267c-254">This example creates a safe attachment rule named Contoso All with the following conditions:</span></span>

- <span data-ttu-id="1267c-255">此規則會與名為 Contoso All 的安全附件原則相關聯。</span><span class="sxs-lookup"><span data-stu-id="1267c-255">The rule is associated with the safe attachment policy named Contoso All.</span></span>
- <span data-ttu-id="1267c-256">此規則會套用至 contoso.com 網域中的所有收件者。</span><span class="sxs-lookup"><span data-stu-id="1267c-256">The rule applies to all recipients in the contoso.com domain.</span></span>
- <span data-ttu-id="1267c-257">因為我們沒有使用 _priority_ 參數，所以會使用預設的優先順序。</span><span class="sxs-lookup"><span data-stu-id="1267c-257">Because we aren't using the _Priority_ parameter, the default priority is used.</span></span>
- <span data-ttu-id="1267c-258"> (未使用 _enabled_ 參數時，也會啟用該規則，且預設值為 `$true`) 。</span><span class="sxs-lookup"><span data-stu-id="1267c-258">The rule is enabled (we aren't using the _Enabled_ parameter, and the default value is `$true`).</span></span>

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

<span data-ttu-id="1267c-259">如需詳細的語法及參數資訊，請參閱 [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="1267c-259">For detailed syntax and parameter information, see [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule).</span></span>

### <a name="use-powershell-to-view-safe-attachment-policies"></a><span data-ttu-id="1267c-260">使用 PowerShell 來查看安全附件原則</span><span class="sxs-lookup"><span data-stu-id="1267c-260">Use PowerShell to view safe attachment policies</span></span>

<span data-ttu-id="1267c-261">若要查看現有的安全附件原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1267c-261">To view existing safe attachment policies, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="1267c-262">本範例會傳回所有安全附件原則的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="1267c-262">This example returns a summary list of all safe attachment policies.</span></span>

```PowerShell
Get-SafeAttachmentPolicy
```

<span data-ttu-id="1267c-263">此範例會傳回名為 Contoso 主管的安全附件原則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1267c-263">This example returns detailed information for the safe attachment policy named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="1267c-264">如需詳細的語法及參數資訊，請參閱 [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="1267c-264">For detailed syntax and parameter information, see [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-view-safe-attachment-rules"></a><span data-ttu-id="1267c-265">使用 PowerShell 來查看安全附件規則</span><span class="sxs-lookup"><span data-stu-id="1267c-265">Use PowerShell to view safe attachment rules</span></span>

<span data-ttu-id="1267c-266">若要查看現有的安全附件規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1267c-266">To view existing safe attachment rules, use the following syntax:</span></span>

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

<span data-ttu-id="1267c-267">本範例會傳回所有安全附件規則的摘要清單。</span><span class="sxs-lookup"><span data-stu-id="1267c-267">This example returns a summary list of all safe attachment rules.</span></span>

```PowerShell
Get-SafeAttachmentRule
```

<span data-ttu-id="1267c-268">若要依啟用或停用篩選規則的清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1267c-268">To filter the list by enabled or disabled rules, run the following commands:</span></span>

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

<span data-ttu-id="1267c-269">此範例會傳回名為 Contoso 主管的安全附件規則的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1267c-269">This example returns detailed information for the safe attachment rule named Contoso Executives.</span></span>

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

<span data-ttu-id="1267c-270">如需詳細的語法及參數資訊，請參閱 [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="1267c-270">For detailed syntax and parameter information, see [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-policies"></a><span data-ttu-id="1267c-271">使用 PowerShell 修改安全附件原則</span><span class="sxs-lookup"><span data-stu-id="1267c-271">Use PowerShell to modify safe attachment policies</span></span>

<span data-ttu-id="1267c-272">您無法在 PowerShell 中重新命名安全附件原則 (**Set-SafeAttachmentPolicy** Cmdlet 沒有 _Name_ 參數) 。</span><span class="sxs-lookup"><span data-stu-id="1267c-272">You can't rename a safe attachment policy in PowerShell (the **Set-SafeAttachmentPolicy** cmdlet has no _Name_ parameter).</span></span> <span data-ttu-id="1267c-273">當您在安全性 & 規範中心重新命名安全附件原則時，您只是重新命名安全附件 _規則_。</span><span class="sxs-lookup"><span data-stu-id="1267c-273">When you rename a Safe Attachments policy in the Security & Compliance Center, you're only renaming the safe attachment _rule_.</span></span>

<span data-ttu-id="1267c-274">否則，當您建立安全附件原則時，就會使用相同的設定，如本文稍早 [使用 [步驟1：使用 PowerShell 來建立安全附件原則](#step-1-use-powershell-to-create-a-safe-attachment-policy) ] 區段所述。</span><span class="sxs-lookup"><span data-stu-id="1267c-274">Otherwise, the same settings are available when you create a safe attachment policy as described in the [Step 1: Use PowerShell to create a safe attachment policy](#step-1-use-powershell-to-create-a-safe-attachment-policy) section earlier in this article.</span></span>

<span data-ttu-id="1267c-275">若要修改安全附件原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1267c-275">To modify a safe attachment policy, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

<span data-ttu-id="1267c-276">如需詳細的語法及參數資訊，請參閱 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="1267c-276">For detailed syntax and parameter information, see [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-modify-safe-attachment-rules"></a><span data-ttu-id="1267c-277">使用 PowerShell 修改安全附件規則</span><span class="sxs-lookup"><span data-stu-id="1267c-277">Use PowerShell to modify safe attachment rules</span></span>

<span data-ttu-id="1267c-278">當您在 PowerShell 中修改安全附件規則時，唯一無法使用的設定是 _Enabled_ 參數，可讓您建立已停用的規則。</span><span class="sxs-lookup"><span data-stu-id="1267c-278">The only setting that's not available when you modify a safe attachment rule in PowerShell is the _Enabled_ parameter that allows you to create a disabled rule.</span></span> <span data-ttu-id="1267c-279">若要啟用或停用現有的安全附件規則，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="1267c-279">To enable or disable existing safe attachment rules, see the next section.</span></span>

<span data-ttu-id="1267c-280">否則，當您建立一個規則時，當您在本文稍早 [使用 [步驟2：使用 PowerShell 建立安全附件規則](#step-2-use-powershell-to-create-a-safe-attachment-rule) ] 區段所述時，就可以使用相同的設定。</span><span class="sxs-lookup"><span data-stu-id="1267c-280">Otherwise, the same settings are available when you create a rule as described in the [Step 2: Use PowerShell to create a safe attachment rule](#step-2-use-powershell-to-create-a-safe-attachment-rule) section earlier in this article.</span></span>

<span data-ttu-id="1267c-281">若要修改安全附件規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1267c-281">To modify a safe attachment rule, use this syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

<span data-ttu-id="1267c-282">如需詳細的語法及參數資訊，請參閱 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="1267c-282">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a><span data-ttu-id="1267c-283">使用 PowerShell 來啟用或停用安全附件規則</span><span class="sxs-lookup"><span data-stu-id="1267c-283">Use PowerShell to enable or disable safe attachment rules</span></span>

<span data-ttu-id="1267c-284">啟用或停用 PowerShell 中的安全附件規則可啟用或停用安全附件規則和指派的安全附件原則)  (的整個安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="1267c-284">Enabling or disabling a safe attachment rule in PowerShell enables or disables the whole Safe Attachments policy (the safe attachment rule and the assigned safe attachment policy).</span></span>

<span data-ttu-id="1267c-285">若要啟用或停用 PowerShell 中的安全附件規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1267c-285">To enable or disable a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

<span data-ttu-id="1267c-286">本範例會停用名為「行銷部門」的安全附件規則。</span><span class="sxs-lookup"><span data-stu-id="1267c-286">This example disables the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="1267c-287">此範例會啟用相同規則。</span><span class="sxs-lookup"><span data-stu-id="1267c-287">This example enables same rule.</span></span>

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="1267c-288">如需詳細的語法及參數資訊，請參閱 [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) 和 [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="1267c-288">For detailed syntax and parameter information, see [Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule) and [Disable-SafeAttachmentRule](/powershell/module/exchange/disable-safeattachmentrule).</span></span>

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a><span data-ttu-id="1267c-289">使用 PowerShell 設定安全附件規則的優先順序</span><span class="sxs-lookup"><span data-stu-id="1267c-289">Use PowerShell to set the priority of safe attachment rules</span></span>

<span data-ttu-id="1267c-290">您可以對規則設定的最高優先順序值為 0。</span><span class="sxs-lookup"><span data-stu-id="1267c-290">The highest priority value you can set on a rule is 0.</span></span> <span data-ttu-id="1267c-291">您可以設定的最低值則取決於規則的數目。</span><span class="sxs-lookup"><span data-stu-id="1267c-291">The lowest value you can set depends on the number of rules.</span></span> <span data-ttu-id="1267c-292">例如，如果您有五個規則，則您可以使用 0 到 4 的優先順序值。</span><span class="sxs-lookup"><span data-stu-id="1267c-292">For example, if you have five rules, you can use the priority values 0 through 4.</span></span> <span data-ttu-id="1267c-293">變更現有規則的優先順序會對其他規則造成階層式影響。</span><span class="sxs-lookup"><span data-stu-id="1267c-293">Changing the priority of an existing rule can have a cascading effect on other rules.</span></span> <span data-ttu-id="1267c-294">例如，如果您有五個自訂規則 (優先順序 0 到 4)，而您將規則的優先順序變更為 2，則優先順序為 2 的現有規則會變更為優先順序 3，優先順序 3 的規則會變更為優先順序 4。</span><span class="sxs-lookup"><span data-stu-id="1267c-294">For example, if you have five custom rules (priorities 0 through 4), and you change the priority of a rule to 2, the existing rule with priority 2 is changed to priority 3, and the rule with priority 3 is changed to priority 4.</span></span>

<span data-ttu-id="1267c-295">若要設定 PowerShell 中安全附件規則的優先順序，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1267c-295">To set the priority of a safe attachment rule in PowerShell, use the following syntax:</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

<span data-ttu-id="1267c-296">此範例會將規則 (名稱為 Marketing Department) 的優先順序設定為 2。</span><span class="sxs-lookup"><span data-stu-id="1267c-296">This example sets the priority of the rule named Marketing Department to 2.</span></span> <span data-ttu-id="1267c-297">優先順序小於或等於 2 的所有現有規則會減 1 (它們的優先順序數字會加 1)。</span><span class="sxs-lookup"><span data-stu-id="1267c-297">All existing rules that have a priority less than or equal to 2 are decreased by 1 (their priority numbers are increased by 1).</span></span>

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

<span data-ttu-id="1267c-298">**附注**：若要在建立新規則時設定其優先順序，請改為在 **New-SafeAttachmentRule** Cmdlet 上使用 _priority_ 參數。</span><span class="sxs-lookup"><span data-stu-id="1267c-298">**Note**: To set the priority of a new rule when you create it, use the _Priority_ parameter on the **New-SafeAttachmentRule** cmdlet instead.</span></span>

<span data-ttu-id="1267c-299">如需詳細的語法及參數資訊，請參閱 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="1267c-299">For detailed syntax and parameter information, see [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-policies"></a><span data-ttu-id="1267c-300">使用 PowerShell 移除安全附件原則</span><span class="sxs-lookup"><span data-stu-id="1267c-300">Use PowerShell to remove safe attachment policies</span></span>

<span data-ttu-id="1267c-301">當您使用 PowerShell 來移除安全附件原則時，並不會移除對應的安全附件規則。</span><span class="sxs-lookup"><span data-stu-id="1267c-301">When you use PowerShell to remove a safe attachment policy, the corresponding safe attachment rule isn't removed.</span></span>

<span data-ttu-id="1267c-302">若要移除 PowerShell 中的安全附件原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1267c-302">To remove a safe attachment policy in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

<span data-ttu-id="1267c-303">此範例會移除名為 Marketing 部門的安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="1267c-303">This example removes the safe attachment policy named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

<span data-ttu-id="1267c-304">如需詳細的語法及參數資訊，請參閱 [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy)。</span><span class="sxs-lookup"><span data-stu-id="1267c-304">For detailed syntax and parameter information, see [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy).</span></span>

### <a name="use-powershell-to-remove-safe-attachment-rules"></a><span data-ttu-id="1267c-305">使用 PowerShell 移除安全附件規則</span><span class="sxs-lookup"><span data-stu-id="1267c-305">Use PowerShell to remove safe attachment rules</span></span>

<span data-ttu-id="1267c-306">當您使用 PowerShell 來移除安全附件規則時，並不會移除對應的安全附件原則。</span><span class="sxs-lookup"><span data-stu-id="1267c-306">When you use PowerShell to remove a safe attachment rule, the corresponding safe attachment policy isn't removed.</span></span>

<span data-ttu-id="1267c-307">若要在 PowerShell 中移除安全附件規則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="1267c-307">To remove a safe attachment rule in PowerShell, use this syntax:</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

<span data-ttu-id="1267c-308">本範例會移除名為 Marketing 部門的安全附件規則。</span><span class="sxs-lookup"><span data-stu-id="1267c-308">This example removes the safe attachment rule named Marketing Department.</span></span>

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

<span data-ttu-id="1267c-309">如需詳細的語法及參數資訊，請參閱 [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule)。</span><span class="sxs-lookup"><span data-stu-id="1267c-309">For detailed syntax and parameter information, see [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1267c-310">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="1267c-310">How do you know these procedures worked?</span></span>

<span data-ttu-id="1267c-311">若要確認您是否已成功建立、修改或移除安全附件原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="1267c-311">To verify that you've successfully created, modified, or removed Safe Attachments policies, do any of the following steps:</span></span>

- <span data-ttu-id="1267c-312">在安全性 & 規範中心內，移至 **威脅管理** \> **原則** \> **ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="1267c-312">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP Safe Attachments**.</span></span> <span data-ttu-id="1267c-313">請確認原則的清單、其 **狀態** 值，以及其 **優先順序** 值。</span><span class="sxs-lookup"><span data-stu-id="1267c-313">Verify the list of policies, their **Status** values, and their **Priority** values.</span></span> <span data-ttu-id="1267c-314">若要查看更多詳細資料，請從清單中選取原則，然後在 [飛出] 中查看詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1267c-314">To view more details, select the policy from the list, and view the details in the fly out.</span></span>

- <span data-ttu-id="1267c-315">在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中， \<Name\> 以原則或規則的名稱取代，執行下列命令，然後確認設定：</span><span class="sxs-lookup"><span data-stu-id="1267c-315">In Exchange Online PowerShell or Exchange Online Protection PowerShell, replace \<Name\> with the name of the policy or rule, run the following command, and verify the settings:</span></span>

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

<span data-ttu-id="1267c-316">若要驗證安全附件是否正在掃描郵件，請檢查可用的 Defender for Office 365 報告。</span><span class="sxs-lookup"><span data-stu-id="1267c-316">To verify that Safe Attachments is scanning messages, check the available Defender for Office 365 reports.</span></span> <span data-ttu-id="1267c-317">如需詳細資訊，請參閱 [View For Office 365 的 Defender 報告](view-reports-for-atp.md) 和 [使用 Explorer In Security & 合規性中心](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="1267c-317">For more information, see [View reports for Defender for Office 365](view-reports-for-atp.md) and [Use Explorer in the Security & Compliance Center](threat-explorer.md).</span></span>