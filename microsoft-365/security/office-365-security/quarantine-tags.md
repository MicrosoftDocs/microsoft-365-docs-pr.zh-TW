---
title: 隔離標記
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 系統管理員可以瞭解如何使用隔離標記來控制使用者可對其隔離郵件執行的動作。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8024894cdb4a4718422c250eff87fa6da5443a84
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922409"
---
# <a name="quarantine-tags"></a><span data-ttu-id="9ab0b-103">隔離標記</span><span class="sxs-lookup"><span data-stu-id="9ab0b-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="9ab0b-104">本文中所述的功能目前在預覽中，無法供所有人使用，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="9ab0b-105">Exchange Online Protection () EOP 中的隔離標籤，可讓系統管理員根據郵件如何抵達隔離的方式，控制使用者可以對隔離郵件執行的動作。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="9ab0b-106">EOP 已傳統允許或防止 [隔離](find-and-release-quarantined-messages-as-a-user.md) 和 [使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)中的郵件的某些層級互動。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="9ab0b-107">例如，使用者可以查看和放開反垃圾郵件篩選為垃圾郵件或大量進行隔離的郵件，但是不能查看或發行被隔離為高可信度網路釣魚的郵件。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="9ab0b-108">針對 [支援的保護功能](#step-2-assign-a-quarantine-tag-to-supported-features)，隔離標籤會指定在使用者是收件者) 的情況下，使用者可以在使用者的垃圾郵件通知訊息和隔離的郵件中執行的功能 (郵件。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="9ab0b-109">預設的隔離標記會自動指派給使用者強制執行隔離郵件的歷史功能。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="9ab0b-110">或者，您也可以建立並指派自訂隔離標記，以允許或防止使用者對隔離郵件執行特定動作。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="9ab0b-111">個別許可權會組合成下列預設許可權群組：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="9ab0b-112">沒有存取權</span><span class="sxs-lookup"><span data-stu-id="9ab0b-112">No access</span></span>
- <span data-ttu-id="9ab0b-113">限制存取</span><span class="sxs-lookup"><span data-stu-id="9ab0b-113">Limited access</span></span>
- <span data-ttu-id="9ab0b-114">完全存取</span><span class="sxs-lookup"><span data-stu-id="9ab0b-114">Full access</span></span>

<span data-ttu-id="9ab0b-115">下表說明可用的個別許可權，以及在預置許可權群組中包含或不包含的專案：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="9ab0b-116">權限</span><span class="sxs-lookup"><span data-stu-id="9ab0b-116">Permission</span></span>|<span data-ttu-id="9ab0b-117">沒有存取權</span><span class="sxs-lookup"><span data-stu-id="9ab0b-117">No access</span></span>|<span data-ttu-id="9ab0b-118">限制存取</span><span class="sxs-lookup"><span data-stu-id="9ab0b-118">Limited access</span></span>|<span data-ttu-id="9ab0b-119">完全存取</span><span class="sxs-lookup"><span data-stu-id="9ab0b-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="9ab0b-120">**允許寄件者** (_PermissionToAllowSender_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![核取記號](../../media/checkmark.png)|
|<span data-ttu-id="9ab0b-122">**封鎖寄件者** (_PermissionToBlockSender_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
|<span data-ttu-id="9ab0b-125">**Delete** (_PermissionToDelete_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-125">**Delete** (_PermissionToDelete_)</span></span>||![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
|<span data-ttu-id="9ab0b-128">**預覽** (_PermissionToPreview_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-128">**Preview** (_PermissionToPreview_)</span></span>||![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
|<span data-ttu-id="9ab0b-131">**允許收件者從隔離區釋放郵件** (_PermissionToRelease_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![核取記號](../../media/checkmark.png)|
|<span data-ttu-id="9ab0b-133">**允許收件者要求從隔離區發行郵件** (_PermissionToRequestRelease_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![核取記號](../../media/checkmark.png)||
|

<span data-ttu-id="9ab0b-135">如果您不喜歡預設許可權群組中的預設許可權，您可以在建立或修改自訂隔離標記時使用自訂許可權。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="9ab0b-136">如需每個許可權的相關資訊，請參閱本文稍後的隔離標籤 [許可權詳細資料](#quarantine-tag-permission-details) 一節。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="9ab0b-137">您可以使用 Exchange Online 信箱，在安全性 & 合規性中心或 PowerShell (Exchange Online 365 PowerShell 中建立並指派隔離標記;EOP 組織中的獨立 EOP PowerShell，但沒有 Exchange Online 信箱) 。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9ab0b-138">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="9ab0b-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9ab0b-139">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="9ab0b-140">若要直接移至 [ **隔離標記** ] 頁面，請開啟] <https://protection.office.com/quarantineTags> 。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="9ab0b-141">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="9ab0b-142">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9ab0b-143">若要查看、建立、修改或移除隔離標記，您必須是「[安全性 & 規範中心](permissions-in-the-security-and-compliance-center.md)」中「**組織管理**」或「**安全性管理員**」角色的成員。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="9ab0b-144">步驟1：在安全性 & 規範中心建立隔離標記</span><span class="sxs-lookup"><span data-stu-id="9ab0b-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="9ab0b-145">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** ]，然後選取 [ **隔離標記**]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="9ab0b-146">在 [ **隔離標記** ] 頁面上，選取 [ **新增自訂標記**]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="9ab0b-147">[ **新增標記** ] 嚮導隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="9ab0b-148">在 [ **標記名稱** ] 頁面上，于 [ **標記名稱** ] 欄位中輸入簡短但唯一的名稱。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="9ab0b-149">您必須在後續步驟中以名稱識別並選取標記。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="9ab0b-150">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="9ab0b-151">在 [ **收件者郵件存取** ] 頁面上，選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="9ab0b-152">**無法存取**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-152">**No access**</span></span>
   - <span data-ttu-id="9ab0b-153">**限制存取**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-153">**Limited access**</span></span>
   - <span data-ttu-id="9ab0b-154">**完全存取**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-154">**Full access**</span></span>

   <span data-ttu-id="9ab0b-155">本文先前會說明這些許可權群組中包含的個別許可權。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="9ab0b-156">若要指定自訂許可權，請選取 [ **設定特定 access (Advanced)** ]，然後設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="9ab0b-157">**選取 [發行動作偏好** 設定]：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="9ab0b-158">**無發行動作**：此為預設值。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="9ab0b-159">**允許收件者從隔離區釋放郵件**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="9ab0b-160">**允許收件者要求從隔離區釋放郵件**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="9ab0b-161">**選取其他動作收件者可對隔離郵件採取採取動作**：選取 [部分]、[全部] 或 [無下列任何] 值：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="9ab0b-162">**Delete**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-162">**Delete**</span></span>
       - <span data-ttu-id="9ab0b-163">**預覽**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-163">**Preview**</span></span>
       - <span data-ttu-id="9ab0b-164">**允許寄件者**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-164">**Allow sender**</span></span>
       - <span data-ttu-id="9ab0b-165">**封鎖寄件者**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-165">**Block sender**</span></span>

   <span data-ttu-id="9ab0b-166">這些許可權及其對隔離郵件和使用者垃圾郵件通知中的影響將會在本文稍後的隔離標籤 [許可權詳細資料](#quarantine-tag-permission-details) 一節中說明。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="9ab0b-167">完成後，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="9ab0b-168">在出現的 [ **摘要** ] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="9ab0b-169">您可以按一下每個設定的 [ **編輯** ] 進行修改。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="9ab0b-170">當您完成時，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="9ab0b-171">在出現的確認頁面上，按一下 [ **完成** ]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="9ab0b-172">現在，您已準備好將隔離標籤指派給隔離功能（如 [步驟 2](#step-2-assign-a-quarantine-tag-to-supported-features) 區段所述）。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="9ab0b-173">在 PowerShell 中建立隔離標記</span><span class="sxs-lookup"><span data-stu-id="9ab0b-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="9ab0b-174">如果您想要使用 PowerShell 建立隔離標記，請連線至 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 並使用 **QuarantineTag** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="9ab0b-175">您有兩種不同的方法可供您選擇：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="9ab0b-176">使用 _EndUserQuarantinePermissionsValue_ 參數。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="9ab0b-177">使用 _EndUserQuarantinePermissions_ 參數。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="9ab0b-178">這些方法將在下列各節中說明。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="9ab0b-179">使用 EndUserQuarantinePermissionsValue 參數</span><span class="sxs-lookup"><span data-stu-id="9ab0b-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="9ab0b-180">若要使用 _EndUserQuarantinePermissionsValue_ 參數建立隔離標記，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="9ab0b-181">_EndUserQuarantinePermissionsValue_ 參數會使用從二進位值轉換而來的十進位值。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="9ab0b-182">二進位值對應至可用的使用者隔離許可權特定順序。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="9ab0b-183">針對每個許可權，值1等於 True，值0等於 False。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="9ab0b-184">下表說明預設許可權群組中每個個別許可權的必要順序和值：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="9ab0b-185">權限</span><span class="sxs-lookup"><span data-stu-id="9ab0b-185">Permission</span></span>|<span data-ttu-id="9ab0b-186">沒有存取權</span><span class="sxs-lookup"><span data-stu-id="9ab0b-186">No access</span></span>|<span data-ttu-id="9ab0b-187">限制存取</span><span class="sxs-lookup"><span data-stu-id="9ab0b-187">Limited access</span></span>|<span data-ttu-id="9ab0b-188">完全存取</span><span class="sxs-lookup"><span data-stu-id="9ab0b-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="9ab0b-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="9ab0b-189">PermissionToAllowSender</span></span>|<span data-ttu-id="9ab0b-190">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-190">0</span></span>|<span data-ttu-id="9ab0b-191">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-191">0</span></span>|<span data-ttu-id="9ab0b-192">1</span><span class="sxs-lookup"><span data-stu-id="9ab0b-192">1</span></span>|
|<span data-ttu-id="9ab0b-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="9ab0b-193">PermissionToBlockSender</span></span>|<span data-ttu-id="9ab0b-194">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-194">0</span></span>|<span data-ttu-id="9ab0b-195">1</span><span class="sxs-lookup"><span data-stu-id="9ab0b-195">1</span></span>|<span data-ttu-id="9ab0b-196">1</span><span class="sxs-lookup"><span data-stu-id="9ab0b-196">1</span></span>|
|<span data-ttu-id="9ab0b-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="9ab0b-197">PermissionToDelete</span></span>|<span data-ttu-id="9ab0b-198">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-198">0</span></span>|<span data-ttu-id="9ab0b-199">1</span><span class="sxs-lookup"><span data-stu-id="9ab0b-199">1</span></span>|<span data-ttu-id="9ab0b-200">1</span><span class="sxs-lookup"><span data-stu-id="9ab0b-200">1</span></span>|
|<span data-ttu-id="9ab0b-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ab0b-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="9ab0b-202">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-202">0</span></span>|<span data-ttu-id="9ab0b-203">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-203">0</span></span>|<span data-ttu-id="9ab0b-204">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-204">0</span></span>|
|<span data-ttu-id="9ab0b-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="9ab0b-205">PermissionToPreview</span></span>|<span data-ttu-id="9ab0b-206">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-206">0</span></span>|<span data-ttu-id="9ab0b-207">1</span><span class="sxs-lookup"><span data-stu-id="9ab0b-207">1</span></span>|<span data-ttu-id="9ab0b-208">1</span><span class="sxs-lookup"><span data-stu-id="9ab0b-208">1</span></span>|
|<span data-ttu-id="9ab0b-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ab0b-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="9ab0b-210">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-210">0</span></span>|<span data-ttu-id="9ab0b-211">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-211">0</span></span>|<span data-ttu-id="9ab0b-212">1</span><span class="sxs-lookup"><span data-stu-id="9ab0b-212">1</span></span>|
|<span data-ttu-id="9ab0b-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ab0b-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="9ab0b-214">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-214">0</span></span>|<span data-ttu-id="9ab0b-215">1</span><span class="sxs-lookup"><span data-stu-id="9ab0b-215">1</span></span>|<span data-ttu-id="9ab0b-216">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-216">0</span></span>|
|<span data-ttu-id="9ab0b-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ab0b-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="9ab0b-218">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-218">0</span></span>|<span data-ttu-id="9ab0b-219">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-219">0</span></span>|<span data-ttu-id="9ab0b-220">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-220">0</span></span>|
|<span data-ttu-id="9ab0b-221">二進位值</span><span class="sxs-lookup"><span data-stu-id="9ab0b-221">Binary value</span></span>|<span data-ttu-id="9ab0b-222">00000000</span><span class="sxs-lookup"><span data-stu-id="9ab0b-222">00000000</span></span>|<span data-ttu-id="9ab0b-223">01101010</span><span class="sxs-lookup"><span data-stu-id="9ab0b-223">01101010</span></span>|<span data-ttu-id="9ab0b-224">11101100</span><span class="sxs-lookup"><span data-stu-id="9ab0b-224">11101100</span></span>|
|<span data-ttu-id="9ab0b-225">要使用的十進位數值</span><span class="sxs-lookup"><span data-stu-id="9ab0b-225">Decimal value to use</span></span>|<span data-ttu-id="9ab0b-226">0</span><span class="sxs-lookup"><span data-stu-id="9ab0b-226">0</span></span>|<span data-ttu-id="9ab0b-227">106</span><span class="sxs-lookup"><span data-stu-id="9ab0b-227">106</span></span>|<span data-ttu-id="9ab0b-228">236</span><span class="sxs-lookup"><span data-stu-id="9ab0b-228">236</span></span>|

<span data-ttu-id="9ab0b-229"><sup>\*</sup> 目前這個值永遠為0。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="9ab0b-230">若為 PermissionToViewHeader，值0不會隱藏「 **查看郵件頁首** 」按鈕的隔離郵件的詳細資料 (按鈕永遠可供使用) 。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="9ab0b-231"><sup>\*\*</sup> 請勿將這兩個值都設為1。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="9ab0b-232">將 one 設定為1，另一個設定為0，或設定為0。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="9ab0b-233">這個範例會建立新的隔離標籤名稱 NoAccess，該名稱會指派上表中所述的「沒有存取」許可權。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="9ab0b-234">若為「限制存取」許可權，請使用值106。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="9ab0b-235">如需完整存取許可權，請使用值236。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="9ab0b-236">若為自訂許可權，請使用上表取得與您想要的許可權相對應的二進位值。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="9ab0b-237">將二進位值轉換為十進位值，並使用 _EndUserQuarantinePermissionsValue_ 參數的十進位值。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="9ab0b-238">如需詳細的語法及參數資訊，請參閱 [QuarantineTag](/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-238">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="9ab0b-239">使用 EndUserQuarantinePermissions 參數</span><span class="sxs-lookup"><span data-stu-id="9ab0b-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="9ab0b-240">若要使用 _EndUserQuarantinePermissionsValue_ 參數建立隔離標記，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="9ab0b-241">答：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-241">A.</span></span> <span data-ttu-id="9ab0b-242">使用 **QuarantinePermissions 指令程式** ，將隔離權限物件儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="9ab0b-243">B。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-243">B.</span></span> <span data-ttu-id="9ab0b-244">使用此變數做為 **QuarantineTag** 命令中的 _EndUserQuarantinePermissions_ 值。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="9ab0b-245">步驟 A：將隔離權限物件儲存在變數中</span><span class="sxs-lookup"><span data-stu-id="9ab0b-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="9ab0b-246">使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="9ab0b-247">任何未使用參數的預設值為 `$false` ，所以您只需要使用您要設定值的參數 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="9ab0b-248">下列範例顯示如何建立與「預置」許可權群組相對應的權限物件：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="9ab0b-249">**無存取權**：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="9ab0b-250">**限制存取**：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="9ab0b-251">**完全存取**：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="9ab0b-252">若要查看您設定的值，請以命令 (執行變數名稱。例如，執行命令 `$NoAccess`) 。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="9ab0b-253">若為自訂許可權，請勿將 _PermissionToRelease_ 和 _PermissionToRequestRelease_ 參數都設定為 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="9ab0b-254">將其中一個設為 `$true` ，並保留另一個為 `$false` ，或保留兩者 `$false` 。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="9ab0b-255">您也可以在建立之後，使用 **QuarantinePermissions** 指令程式來修改現有的權限物件變數。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="9ab0b-256">如需詳細的語法及參數資訊，請參閱 [QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="9ab0b-257">步驟 B：使用 New-QuarantineTag 命令中的變數</span><span class="sxs-lookup"><span data-stu-id="9ab0b-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="9ab0b-258">在變數中建立及儲存權限物件之後，請在下列 **QuarantineTag** 命令中使用 _EndUserQuarantinePermission_ 參數值的變數：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="9ab0b-259">此範例會使用 `$LimitedAccess` 上一個步驟中所述及建立的權限物件，建立名為 LimitedAccess 的新隔離標記。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="9ab0b-260">如需詳細的語法及參數資訊，請參閱 [QuarantineTag](/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-260">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="9ab0b-261">步驟2：指派隔離標記至支援的功能</span><span class="sxs-lookup"><span data-stu-id="9ab0b-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="9ab0b-262">在 [隔離郵件或檔案 (會自動或作為可設定動作) 的 _支援_ 保護功能中，您可以指派隔離標籤至可用的隔離動作。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="9ab0b-263">下表說明隔離郵件和隔離標記可用性的功能：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="9ab0b-264">功能</span><span class="sxs-lookup"><span data-stu-id="9ab0b-264">Feature</span></span>|<span data-ttu-id="9ab0b-265">支援隔離標記？</span><span class="sxs-lookup"><span data-stu-id="9ab0b-265">Quarantine tags supported?</span></span>|<span data-ttu-id="9ab0b-266">使用的預設隔離標記</span><span class="sxs-lookup"><span data-stu-id="9ab0b-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="9ab0b-267">[反垃圾郵件原則](configure-your-spam-filter-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="9ab0b-268">**垃圾郵件** (_SpamAction_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="9ab0b-269">**高信賴垃圾郵件** (_HighConfidenceSpamAction_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="9ab0b-270">**網路釣魚電子郵件** (_PhishSpamAction_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="9ab0b-271">**高信賴網路釣魚電子郵件** (_HighConfidencePhishAction_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="9ab0b-272">**大量電子郵件** (_BulkSpamAction_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="9ab0b-273">是</span><span class="sxs-lookup"><span data-stu-id="9ab0b-273">Yes</span></span>|<ul><li><span data-ttu-id="9ab0b-274">DefaultSpamTag (完整存取) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="9ab0b-275">DefaultHighConfSpamTag (完整存取) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="9ab0b-276">DefaultPhishTag (完整存取) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="9ab0b-277">DefaultHighConfPhishTag (無法存取) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="9ab0b-278">DefaultBulkTag (完整存取) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="9ab0b-279">反網路釣魚原則：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="9ab0b-280">_AuthenticationFailAction_ 的 [欺騙情報防護](set-up-anti-phishing-policies.md#spoof-settings) () </span><span class="sxs-lookup"><span data-stu-id="9ab0b-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="9ab0b-281">[類比保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)：<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9ab0b-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="9ab0b-282">**如果由類比的使用者傳送電子郵件** (_TargetedUserProtectionAction_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="9ab0b-283">**如果模擬的網域傳送電子郵件** (_TargetedDomainProtectionAction_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="9ab0b-284">**信箱智慧** \>**如果由類比的使用者傳送電子郵件** (_MailboxIntelligenceProtectionAction_) </span><span class="sxs-lookup"><span data-stu-id="9ab0b-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="9ab0b-285">否</span><span class="sxs-lookup"><span data-stu-id="9ab0b-285">No</span></span>|<span data-ttu-id="9ab0b-286">不適用</span><span class="sxs-lookup"><span data-stu-id="9ab0b-286">n/a</span></span>|
|<span data-ttu-id="9ab0b-287">[反惡意程式碼原則](configure-anti-malware-policies.md)：永遠會隔離所有偵測到的郵件。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="9ab0b-288">否</span><span class="sxs-lookup"><span data-stu-id="9ab0b-288">No</span></span>|<span data-ttu-id="9ab0b-289">不適用</span><span class="sxs-lookup"><span data-stu-id="9ab0b-289">n/a</span></span>|
|[<span data-ttu-id="9ab0b-290">適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件</span><span class="sxs-lookup"><span data-stu-id="9ab0b-290">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="9ab0b-291">否</span><span class="sxs-lookup"><span data-stu-id="9ab0b-291">No</span></span>|<span data-ttu-id="9ab0b-292">不適用</span><span class="sxs-lookup"><span data-stu-id="9ab0b-292">n/a</span></span>|
|<span data-ttu-id="9ab0b-293">[郵件流程規則](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (也稱為傳輸規則) 具有動作：將 **郵件傳遞至主控隔離** (_隔離_) 。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-293">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="9ab0b-294">否</span><span class="sxs-lookup"><span data-stu-id="9ab0b-294">No</span></span>|<span data-ttu-id="9ab0b-295">不適用</span><span class="sxs-lookup"><span data-stu-id="9ab0b-295">n/a</span></span>|
|

<span data-ttu-id="9ab0b-296"><sup>\*</sup> 模擬保護設定只適用于 Microsoft Defender for Office 365 中的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="9ab0b-297">如果您很樂意使用預設隔離標記所提供的使用者權限，您不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="9ab0b-298">如果您想要自訂使用者功能 (可用按鈕) 使用者垃圾郵件通知或隔離的郵件詳細資料中，您可以指定自訂隔離標記。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="9ab0b-299">在安全性 & 合規性中心的反垃圾郵件原則中指派隔離標記</span><span class="sxs-lookup"><span data-stu-id="9ab0b-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="9ab0b-300">在 [EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)，說明建立及修改反垃圾郵件原則的完整指示。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="9ab0b-301">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則**]， \> 然後選取 [ **反垃圾郵件**]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="9ab0b-302">或者，開啟 <https://protection.office.com/antispam> 。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="9ab0b-303">尋找並選取要編輯的現有反垃圾郵件原則，或建立新的反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="9ab0b-304">在 [原則詳細資料] 浮出視窗中，展開 [ **垃圾郵件和大量動作** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="9ab0b-305">如果您已針對可用垃圾郵件篩選判定的動作選取 [ **隔離郵件** ]，則可以使用 [套用 **隔離原則** 標籤] 方塊，為該判定選取隔離標記。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="9ab0b-306">**附注**：當您建立新的原則時，垃圾郵件篩選判定的空白隔離標籤值會指出使用該判定的預設隔離標籤。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="9ab0b-307">當您後來編輯原則時，空白值會以實際的預設隔離標記名稱取代，如上表所述。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![反垃圾郵件原則中的隔離標記選擇](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="9ab0b-309">完成後，按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="9ab0b-310">在 PowerShell 中的反垃圾郵件原則中指派隔離標記</span><span class="sxs-lookup"><span data-stu-id="9ab0b-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="9ab0b-311">如果您想要使用 PowerShell 來指派反垃圾郵件原則中的隔離標記，請連線至 Exchange Online PowerShell 或 Exchange Online Protection PowerShell，並使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="9ab0b-312">**附註**：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-312">**Notes**:</span></span>

- <span data-ttu-id="9ab0b-313">_HighConfidencePhishAction_ 參數的預設值是「隔離」，所以您不需要為新反垃圾郵件原則中的高可信度網路釣魚偵測設定隔離動作。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="9ab0b-314">針對新的或現有的反垃圾郵件原則中的所有其他垃圾郵件篩選 verdicts，隔離標籤只有在 action 值為「隔離」時才有效。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="9ab0b-315">若要查看現有反垃圾郵件原則中的動作值，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="9ab0b-316">如需有關 Standard 和 Strict 之預設動作值及建議動作值的詳細資訊，請參閱 [EOP 反垃圾郵件原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="9ab0b-317">垃圾郵件篩選會判定沒有對應的隔離標籤參數，這表示使用該判定的 [預設隔離標記](#step-2-assign-a-quarantine-tag-to-supported-features) 。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="9ab0b-318">如果您想要變更隔離郵件的預設使用者功能，您只需要將預設的隔離標記取代為自訂隔離標籤。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="9ab0b-319">PowerShell 中的新反垃圾郵件原則需要垃圾郵件篩選原則 (設定) 使用 **New-HostedContentFilterPolicy** 指令程式和新的垃圾郵件篩選規則 (收件者篩選器) 使用 **New-HostedContentFilterRule** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="9ab0b-320">如需相關指示，請參閱 [使用 PowerShell 建立反垃圾郵件原則](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="9ab0b-321">此範例會使用下列設定來建立名為「Research 部門」的新垃圾郵件篩選原則：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="9ab0b-322">所有垃圾郵件篩選 verdicts 的動作都設為隔離。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="9ab0b-323">名為「NoAccess 的自訂隔離標籤會將 **沒有** 指派任何存取權限的預設隔離標記取代為預設 **不指派任何** 預設的隔離標記。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="9ab0b-324">如需詳細的語法及參數資訊，請參閱 [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="9ab0b-325">此範例會修改名為「人力資源」的現有垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="9ab0b-326">垃圾郵件隔離判定的動作會設定為 [隔離]，而且會指派名為 NoAccess 的自訂隔離標記。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="9ab0b-327">如需詳細的語法及參數資訊，請參閱 [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="9ab0b-328">在安全性 & 規範中心設定全域隔離通知設定</span><span class="sxs-lookup"><span data-stu-id="9ab0b-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="9ab0b-329">隔離標籤的通用設定可讓您自訂使用者的垃圾郵件通知，該通知會傳送給被隔離的郵件收件者。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="9ab0b-330">如需這些通知的詳細資訊，請參閱 [使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="9ab0b-331">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** ]，然後選取 [ **隔離標記**]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="9ab0b-332">在 [ **隔離標記** ] 頁面上，選取 [ **通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="9ab0b-333">在開啟的 [ **隔離通知設定** ] 浮出控制項中，設定下列部分或所有設定：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="9ab0b-334">**使用我的公司徽標**：選取此選項以取代在使用者垃圾郵件通知頂端使用的預設 Microsoft 標誌。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="9ab0b-335">在執行這項作業之前，您必須依照 [自訂群組織的 Microsoft 365 主題](../../admin/setup/customize-your-organization-theme.md) 中的指示，上傳自訂的徽標。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="9ab0b-336">下列螢幕擷取畫面顯示使用者垃圾郵件通知中的自訂標誌：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![最終使用者垃圾郵件通知中的自訂標誌](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="9ab0b-338">**選擇語言**：使用者垃圾郵件通知已根據收件者的語言設定進行當地語系化。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="9ab0b-339">您可以針對 **顯示名稱** 和 **免責聲明** 值，以不同語言指定自訂的文字。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="9ab0b-340">選取 [第一個語言] 方塊中至少一種語言，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="9ab0b-341">您可以在每個語言之後按一下 [ **新增** ]，以選取多種語言。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="9ab0b-342">[區段語言] 方塊會顯示您所選取的所有語言：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-342">A section language box shows all of the languages that you've selected:</span></span>

     ![隔離標籤全域隔離通知設定中的 [第二語言] 方塊中選取的語言](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="9ab0b-344">**顯示名稱**：自訂在使用者垃圾郵件通知中使用的寄件者顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="9ab0b-345">針對您新增的每種語言，在 [第二語言] 方塊中選取語言 (不要按一下 X) ，然後在 [ **顯示名稱** ] 方塊中輸入您想要的文字值。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="9ab0b-346">下列螢幕擷取畫面顯示使用者垃圾郵件通知中的自訂顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![最終使用者垃圾郵件通知中的自訂寄件者顯示名稱](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="9ab0b-348">**免責聲明**：將自訂免責聲明新增至使用者垃圾郵件通知的底部。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="9ab0b-349">當地語系化的文字（ **來自您組織的免責聲明** ）永遠包含在第一列，接著您指定的文字。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="9ab0b-350">針對您已新增的每種語言，選取 [第二語言] 方塊中的語言 (請勿按一下 X) ，然後在 [ **免責聲明** ] 方塊中輸入您想要的文字值。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="9ab0b-351">下列螢幕擷取畫面顯示使用者垃圾郵件通知中的自訂免責聲明：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![最終使用者垃圾郵件通知底部的自訂免責聲明](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="9ab0b-353">在安全性 & 規範中心內查看隔離標記</span><span class="sxs-lookup"><span data-stu-id="9ab0b-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="9ab0b-354">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** ]，然後選取 [ **隔離標記**]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="9ab0b-355">若要查看內建或自訂隔離標籤的設定，請從清單中選取 [隔離] 標記 (不要選取] 核取方塊) 。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="9ab0b-356">若要查看全域設定，請選取 [**通用設定**]</span><span class="sxs-lookup"><span data-stu-id="9ab0b-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="9ab0b-357">在 PowerShell 中查看隔離標記</span><span class="sxs-lookup"><span data-stu-id="9ab0b-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="9ab0b-358">如果您想要使用 PowerShell 來查看隔離標記，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="9ab0b-359">若要查看所有內建或自訂標記的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="9ab0b-360">若要查看內建或自訂隔離標記的設定，請 \<TagName\> 以隔離標記的名稱取代，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="9ab0b-361">若要查看全域設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="9ab0b-362">如需詳細的語法及參數資訊，請參閱 [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="9ab0b-363">移除安全性 & 規範中心內的隔離標記</span><span class="sxs-lookup"><span data-stu-id="9ab0b-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="9ab0b-364">**附註**：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-364">**Notes**:</span></span>

- <span data-ttu-id="9ab0b-365">您無法移除內建的隔離標記。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="9ab0b-366">在您移除自訂隔離標記之前，請確認未使用它。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="9ab0b-367">例如，在 PowerShell: 中執行下列命令</span><span class="sxs-lookup"><span data-stu-id="9ab0b-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="9ab0b-368">若要使用隔離標記，請 [取代指派的隔離標記](#step-2-assign-a-quarantine-tag-to-supported-features) ，然後再將其移除。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="9ab0b-369">在 [安全性 & 規範中心] 中，移至 [ **威脅管理** \> **原則** ]，然後選取 [ **隔離標記**]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="9ab0b-370">在 [ **隔離標記** ] 頁面上，選取您要移除的自訂隔離標記，然後按一下 [ **刪除** 標籤]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="9ab0b-371">在出現的確認對話方塊中，按一下 [ **移除** 標籤]。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="9ab0b-372">移除 PowerShell 中的隔離標記</span><span class="sxs-lookup"><span data-stu-id="9ab0b-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="9ab0b-373">如果您想要使用 PowerShell 移除自訂隔離標記，請 \<TagName\> 以隔離標記的名稱取代，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="9ab0b-374">如需詳細的語法及參數資訊，請參閱 [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="9ab0b-375">隔離標記許可權詳細資料</span><span class="sxs-lookup"><span data-stu-id="9ab0b-375">Quarantine tag permission details</span></span>

<span data-ttu-id="9ab0b-376">下列各節說明在隔離郵件和使用者垃圾郵件通知的詳細資料中，預置許可權群組和個別許可權的影響。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="9ab0b-377">預設許可權群組</span><span class="sxs-lookup"><span data-stu-id="9ab0b-377">Preset permissions groups</span></span>

<span data-ttu-id="9ab0b-378">在「預置」許可權群組中包含的個別許可權會列在本文開頭的表格中。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="9ab0b-379">沒有存取權</span><span class="sxs-lookup"><span data-stu-id="9ab0b-379">No access</span></span>

<span data-ttu-id="9ab0b-380">如果隔離標籤指派「 **無存取** 」許可權 (無許可權) ，使用者仍會取得某些基準功能：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="9ab0b-381">**隔離的郵件詳細資料**： [ **View message header** ] 按鈕永遠可供使用。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![隔離的郵件詳細資料中的可用按鈕如果隔離標籤提供給使用者「沒有存取」許可權](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="9ab0b-383">**使用者垃圾郵件通知**：將使用者帶至隔離區中郵件的 [ **檢查** ] 按鈕永遠可供使用。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![使用者沒有存取許可權時，使用者垃圾郵件通知中的可用按鈕](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="9ab0b-385">限制存取</span><span class="sxs-lookup"><span data-stu-id="9ab0b-385">Limited access</span></span>

<span data-ttu-id="9ab0b-386">如果隔離標籤指派「 **限制存取** 」許可權，使用者就可以取得下列功能：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="9ab0b-387">**隔離的郵件詳細資料**：下列按鈕可用：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="9ab0b-388">**要求版本**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-388">**Request release**</span></span>
  - <span data-ttu-id="9ab0b-389">**查看郵件頭**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-389">**View message header**</span></span>
  - <span data-ttu-id="9ab0b-390">**預覽郵件**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-390">**Preview message**</span></span>
  - <span data-ttu-id="9ab0b-391">**封鎖寄件者**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-391">**Block sender**</span></span>
  - <span data-ttu-id="9ab0b-392">**從隔離區移除**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-392">**Remove from quarantine**</span></span>

  ![隔離郵件詳細資料中的可用按鈕（如果隔離標籤提供使用者限制存取權限）](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="9ab0b-394">**使用者垃圾郵件通知**：下列按鈕可用：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="9ab0b-395">**封鎖寄件者**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-395">**Block sender**</span></span>
  - <span data-ttu-id="9ab0b-396">**檢閱**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-396">**Review**</span></span>

  ![使用者的垃圾郵件通知中的可用按鈕（如果隔離標籤提供使用者限制存取權限）](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="9ab0b-398">完全存取</span><span class="sxs-lookup"><span data-stu-id="9ab0b-398">Full access</span></span>

<span data-ttu-id="9ab0b-399">如果隔離標籤會指派「 **完整存取** 」許可權 (所有可用的許可權) ，使用者會收到下列功能：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="9ab0b-400">**隔離的郵件詳細資料**：下列按鈕可用：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="9ab0b-401">**Release message**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-401">**Release message**</span></span>
  - <span data-ttu-id="9ab0b-402">**查看郵件頭**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-402">**View message header**</span></span>
  - <span data-ttu-id="9ab0b-403">**預覽郵件**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-403">**Preview message**</span></span>
  - <span data-ttu-id="9ab0b-404">**封鎖寄件者**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-404">**Block sender**</span></span>
  - <span data-ttu-id="9ab0b-405">**允許寄件者**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-405">**Allow sender**</span></span>
  - <span data-ttu-id="9ab0b-406">**從隔離區移除**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-406">**Remove from quarantine**</span></span>

  ![隔離的郵件詳細資料中的可用按鈕如果隔離標籤提供使用者「完整存取」許可權](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="9ab0b-408">**使用者垃圾郵件通知**：下列按鈕可用：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="9ab0b-409">**封鎖寄件者**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-409">**Block sender**</span></span>
  - <span data-ttu-id="9ab0b-410">**發行**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-410">**Release**</span></span>
  - <span data-ttu-id="9ab0b-411">**檢閱**</span><span class="sxs-lookup"><span data-stu-id="9ab0b-411">**Review**</span></span>

  ![當隔離標籤提供使用者的「完整存取」許可權時，使用者垃圾郵件通知中的可用按鈕](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="9ab0b-413">個別許可權</span><span class="sxs-lookup"><span data-stu-id="9ab0b-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="9ab0b-414">請記住，使用者永遠會收到「 [無法存取](#no-access) 」區段中所述的按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="9ab0b-415">這些按鈕不會包含在個別的許可權描述中。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="9ab0b-416">允許寄件者許可權</span><span class="sxs-lookup"><span data-stu-id="9ab0b-416">Allow sender permission</span></span>

<span data-ttu-id="9ab0b-417">[ **允許寄件者** ] 許可權 (_PermissionToAllowSender_) 控制對按鈕的存取權，讓使用者可以輕鬆地將隔離的郵件寄件者新增至其安全的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="9ab0b-418">**隔離的郵件詳細資料**：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="9ab0b-419">啟用 [**允許寄件者**] 許可權：可以使用 [**允許寄件者**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="9ab0b-420">**允許停用寄件者** 許可權：無法使用 [ **允許寄件者** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="9ab0b-421">**使用者垃圾郵件通知**：沒有作用。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="9ab0b-422">如需安全寄件者清單的詳細資訊，請參閱 [防止受信任的寄件者遭到封鎖](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) ，並 [使用 Exchange Online PowerShell 來設定信箱上的安全清單集合](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="9ab0b-423">封鎖寄件者許可權</span><span class="sxs-lookup"><span data-stu-id="9ab0b-423">Block sender permission</span></span>

<span data-ttu-id="9ab0b-424">**Block sender** 許可權 (_PermissionToBlockSender_) 控制對按鈕的存取權，讓使用者可以輕鬆地將隔離的郵件寄件者新增至其封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="9ab0b-425">**隔離的郵件詳細資料**：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="9ab0b-426">已啟用 **封鎖寄件者** 許可權：可用的 **封鎖寄件者** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="9ab0b-427">禁止 **封鎖寄件者** 許可權：無法使用 [**封鎖寄件者**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="9ab0b-428">**使用者垃圾郵件通知**：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="9ab0b-429">禁止 **封鎖寄件者** 許可權：無法使用 [**封鎖寄件者**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="9ab0b-430">已啟用 **封鎖寄件者** 許可權：可用的 **封鎖寄件者** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="9ab0b-431">如需有關封鎖的寄件者清單的詳細資訊，請參閱 [封鎖來自某人的郵件](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) ，並 [使用 Exchange Online PowerShell 來設定信箱上的安全清單集合](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="9ab0b-432">刪除權限</span><span class="sxs-lookup"><span data-stu-id="9ab0b-432">Delete permission</span></span>

<span data-ttu-id="9ab0b-433">「 **刪除** 」許可權 (_PermissionToDelete_) 會控制使用者對其郵件的功能 (郵件的收件者) 從隔離區。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="9ab0b-434">**隔離的郵件詳細資料**：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="9ab0b-435">已啟用 **刪除** 許可權：可以使用 [**從隔離區移除**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="9ab0b-436">已停用 **刪除** 許可權：無法使用 [**從隔離區移除**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="9ab0b-437">**使用者垃圾郵件通知**：沒有作用。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="9ab0b-438">預覽許可權</span><span class="sxs-lookup"><span data-stu-id="9ab0b-438">Preview permission</span></span>

<span data-ttu-id="9ab0b-439">**預覽** 許可權 (_PermissionToPreview_) 控制使用者的功能，以在隔離區中預覽其郵件。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="9ab0b-440">**隔離的郵件詳細資料**：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="9ab0b-441">已啟用 **預覽** 許可權： [**預覽郵件**] 按鈕可供使用。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="9ab0b-442">已停用 **預覽** 許可權：無法使用 **預覽郵件** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="9ab0b-443">**使用者垃圾郵件通知**：沒有作用。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="9ab0b-444">允許收件者從隔離許可權放開郵件</span><span class="sxs-lookup"><span data-stu-id="9ab0b-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="9ab0b-445">[ **允許收件者從隔離許可權發行郵件** ] (_PermissionToRelease_) 控制使用者在不核准系統管理員的情況下，直接釋放隔離郵件的能力。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="9ab0b-446">**隔離的郵件詳細資料**：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="9ab0b-447">已啟用許可權：「 **發行訊息** 」按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="9ab0b-448">已停用許可權：無法使用「 **發行訊息** 」按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="9ab0b-449">**使用者垃圾郵件通知**：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="9ab0b-450">已啟用許可權：「 **發行** 」按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="9ab0b-451">已停用許可權：無法使用「 **發行** 」按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="9ab0b-452">允許收件者要求從隔離許可權發行郵件</span><span class="sxs-lookup"><span data-stu-id="9ab0b-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="9ab0b-453">[ **允許收件者要求從隔離許可權發行郵件** ] (_PermissionToRequestRelease_) 控制使用者 _要求_ 發行隔離郵件的能力。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="9ab0b-454">只有在系統管理員核准要求之後，才會發佈郵件。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="9ab0b-455">**隔離的郵件詳細資料**：</span><span class="sxs-lookup"><span data-stu-id="9ab0b-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="9ab0b-456">已啟用許可權： [ **要求版本** ] 按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="9ab0b-457">已停用許可權： [ **要求版本** ] 按鈕無法使用。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="9ab0b-458">**使用者垃圾郵件通知**：無法使用「 **發行** 」按鈕。</span><span class="sxs-lookup"><span data-stu-id="9ab0b-458">**End-user spam notifications**: The **Release** button is not available.</span></span>