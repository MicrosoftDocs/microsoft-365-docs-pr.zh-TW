---
title: 隔離原則
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
description: 系統管理員可以瞭解如何使用隔離原則來控制使用者能夠對其隔離郵件執行的動作。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96dc1e2158787457884ca6a3c6f27bf76e83a369
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055182"
---
# <a name="quarantine-policies"></a><span data-ttu-id="7f50a-103">隔離原則</span><span class="sxs-lookup"><span data-stu-id="7f50a-103">Quarantine policies</span></span>

> [!NOTE]
> <span data-ttu-id="7f50a-104">本文中所述的功能目前在預覽中，無法供所有人使用，而且可能會變更。</span><span class="sxs-lookup"><span data-stu-id="7f50a-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="7f50a-105">Exchange Online Protection (EOP 中的隔離原則 (以前稱為隔離標記) ) 允許系統管理員根據郵件如何抵達隔離的方式，控制使用者能夠對隔離郵件執行的動作。</span><span class="sxs-lookup"><span data-stu-id="7f50a-105">Quarantine policies (formerly known as quarantine tags) in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="7f50a-106">EOP 已傳統允許或防止 [隔離](find-and-release-quarantined-messages-as-a-user.md) 和 [使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)中的郵件的某些層級互動。</span><span class="sxs-lookup"><span data-stu-id="7f50a-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="7f50a-107">例如，使用者可以查看和放開反垃圾郵件篩選隔離為垃圾郵件或大量的郵件，但他們無法查看或發行隔離為高可信度網路釣魚的郵件 (只有系統管理員才能執行該) 。</span><span class="sxs-lookup"><span data-stu-id="7f50a-107">For example, users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing (only admins can do that).</span></span>

<span data-ttu-id="7f50a-108">針對 [支援的保護功能](#step-2-assign-a-quarantine-policy-to-supported-features)，隔離原則會指定在使用者是收件者) 的情況下，允許哪些使用者在使用者的垃圾郵件通知訊息和隔離的郵件中執行哪些 (郵件。</span><span class="sxs-lookup"><span data-stu-id="7f50a-108">For [supported protection features](#step-2-assign-a-quarantine-policy-to-supported-features), quarantine policies specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="7f50a-109">會自動指派預設隔離原則，以針對隔離郵件的使用者強制執行歷史功能。</span><span class="sxs-lookup"><span data-stu-id="7f50a-109">Default quarantine policies are automatically assigned to enforce the historical capabilities for users on quarantined messages.</span></span> <span data-ttu-id="7f50a-110">或者，您可以建立並指派自訂隔離原則，以允許或防止使用者對隔離郵件執行特定動作。</span><span class="sxs-lookup"><span data-stu-id="7f50a-110">Or, you can create and assign custom quarantine policies to allow or prevent end users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="7f50a-111">個別許可權會組合成下列預設許可權群組：</span><span class="sxs-lookup"><span data-stu-id="7f50a-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="7f50a-112">沒有存取權</span><span class="sxs-lookup"><span data-stu-id="7f50a-112">No access</span></span>
- <span data-ttu-id="7f50a-113">限制存取</span><span class="sxs-lookup"><span data-stu-id="7f50a-113">Limited access</span></span>
- <span data-ttu-id="7f50a-114">完全存取</span><span class="sxs-lookup"><span data-stu-id="7f50a-114">Full access</span></span>

<span data-ttu-id="7f50a-115">下表說明可用的個別許可權，以及在預置許可權群組中包含或不包含的專案：</span><span class="sxs-lookup"><span data-stu-id="7f50a-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="7f50a-116">權限</span><span class="sxs-lookup"><span data-stu-id="7f50a-116">Permission</span></span>|<span data-ttu-id="7f50a-117">沒有存取權</span><span class="sxs-lookup"><span data-stu-id="7f50a-117">No access</span></span>|<span data-ttu-id="7f50a-118">限制存取</span><span class="sxs-lookup"><span data-stu-id="7f50a-118">Limited access</span></span>|<span data-ttu-id="7f50a-119">完全存取</span><span class="sxs-lookup"><span data-stu-id="7f50a-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="7f50a-120">**允許寄件者** (_PermissionToAllowSender_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![核取記號](../../media/checkmark.png)|
|<span data-ttu-id="7f50a-122">**封鎖寄件者** (_PermissionToBlockSender_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
|<span data-ttu-id="7f50a-125">**Delete** (_PermissionToDelete_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-125">**Delete** (_PermissionToDelete_)</span></span>||![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
|<span data-ttu-id="7f50a-128">**預覽** (_PermissionToPreview_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-128">**Preview** (_PermissionToPreview_)</span></span>||![核取記號](../../media/checkmark.png)|![核取記號](../../media/checkmark.png)|
|<span data-ttu-id="7f50a-131">**允許收件者從隔離區釋放郵件** (_PermissionToRelease_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![核取記號](../../media/checkmark.png)|
|<span data-ttu-id="7f50a-133">**允許收件者要求從隔離區發行郵件** (_PermissionToRequestRelease_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![核取記號](../../media/checkmark.png)||
|

<span data-ttu-id="7f50a-135">如果您不喜歡預設許可權群組中的預設許可權，您可以在建立或修改自訂隔離原則時使用自訂許可權。</span><span class="sxs-lookup"><span data-stu-id="7f50a-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine policies.</span></span> <span data-ttu-id="7f50a-136">如需每個許可權的相關資訊，請參閱本文稍後的 [隔離原則許可權詳細資料](#quarantine-policy-permission-details) 一節。</span><span class="sxs-lookup"><span data-stu-id="7f50a-136">For more information about what each permission does, see the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

<span data-ttu-id="7f50a-137">您可以在 Microsoft 365 Defender 入口網站或 PowerShell (Exchange Online PowerShell 中建立和指派隔離原則，以 Microsoft 365 具有 Exchange Online 信箱的組織。EOP 組織中的獨立 EOP PowerShell，但沒有 Exchange Online 信箱) 。</span><span class="sxs-lookup"><span data-stu-id="7f50a-137">You create and assign quarantine policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7f50a-138">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="7f50a-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7f50a-139">您於 <https://security.microsoft.com> 開啟 Microsoft 365 Defender 入口網站。</span><span class="sxs-lookup"><span data-stu-id="7f50a-139">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="7f50a-140">或是直接移至 [ **隔離原則** ] 頁面，開啟] <https://security.microsoft.com/quarantineTags> 。</span><span class="sxs-lookup"><span data-stu-id="7f50a-140">Or to go directly to the **Quarantine policies** page, open <https://security.microsoft.com/quarantineTags>.</span></span>

- <span data-ttu-id="7f50a-141">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="7f50a-142">若要連接至獨立版 EOP PowerShell，請參閱[連線到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7f50a-143">若要查看、建立、修改或移除隔離原則，您必須是 Microsoft 365 Defender 入口網站中「**組織管理**」或「**安全性管理員**」角色的成員。</span><span class="sxs-lookup"><span data-stu-id="7f50a-143">To view, create, modify, or remove quarantine policies, you need to be a member of the **Organization Management** or **Security Administrator** roles in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="7f50a-144">如需詳細資訊，請參閱 [Microsoft 365 Defender 入口網站中的權限](permissions-microsoft-365-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-144">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="7f50a-145">步驟1：在 Microsoft 365 Defender 入口網站中建立隔離原則</span><span class="sxs-lookup"><span data-stu-id="7f50a-145">Step 1: Create quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="7f50a-146">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 & 協同** \> **威脅原則**] \> 區段 \> **隔離原則**，然後選取 [**隔離原則**]。</span><span class="sxs-lookup"><span data-stu-id="7f50a-146">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="7f50a-147">在 [ **隔離原則** ] 頁面上，按一下 [ ![ 新增自訂原則圖示] [ ](../../media/m365-cc-sc-create-icon.png) **新增自訂原則**]。</span><span class="sxs-lookup"><span data-stu-id="7f50a-147">On the **Quarantine policy** page, click ![Add custom policy icon](../../media/m365-cc-sc-create-icon.png) **Add custom policy**.</span></span>

3. <span data-ttu-id="7f50a-148">[ **新增原則** ] 嚮導隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="7f50a-148">The **New policy** wizard opens.</span></span> <span data-ttu-id="7f50a-149">在 [ **原則名稱** ] 頁面上，于 [ **原則名稱** ] 方塊中輸入簡短但唯一的名稱。</span><span class="sxs-lookup"><span data-stu-id="7f50a-149">On the **Policy name** page, enter a brief but unique name in the **Policy name** box.</span></span> <span data-ttu-id="7f50a-150">您必須在後續步驟中以名稱識別並選取隔離原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-150">You'll need to identify and select the quarantine policy by name in upcoming steps.</span></span> <span data-ttu-id="7f50a-151">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="7f50a-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="7f50a-152">在 [ **收件者郵件存取** ] 頁面上，選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="7f50a-152">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="7f50a-153">**無法存取**</span><span class="sxs-lookup"><span data-stu-id="7f50a-153">**No access**</span></span>
   - <span data-ttu-id="7f50a-154">**限制存取**</span><span class="sxs-lookup"><span data-stu-id="7f50a-154">**Limited access**</span></span>
   - <span data-ttu-id="7f50a-155">**完全存取**</span><span class="sxs-lookup"><span data-stu-id="7f50a-155">**Full access**</span></span>

   <span data-ttu-id="7f50a-156">本文先前會說明這些許可權群組中包含的個別許可權。</span><span class="sxs-lookup"><span data-stu-id="7f50a-156">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="7f50a-157">若要指定自訂許可權，請選取 [ **設定特定 access (Advanced)** ]，然後設定出現下列設定：</span><span class="sxs-lookup"><span data-stu-id="7f50a-157">To specify custom permissions, select **Set specific access (Advanced)** and the configure the following settings that appear:</span></span>

     - <span data-ttu-id="7f50a-158">**選取 [發行動作偏好** 設定]：選取下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="7f50a-158">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="7f50a-159">**無發行動作**：此為預設值。</span><span class="sxs-lookup"><span data-stu-id="7f50a-159">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="7f50a-160">**允許收件者從隔離區釋放郵件**</span><span class="sxs-lookup"><span data-stu-id="7f50a-160">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="7f50a-161">**允許收件者要求從隔離區釋放郵件**</span><span class="sxs-lookup"><span data-stu-id="7f50a-161">**Allow recipients to request a message to be released from quarantine**</span></span>
     - <span data-ttu-id="7f50a-162">**選取其他動作收件者可對隔離郵件採取採取動作**：選取 [部分]、[全部] 或 [無下列任何] 值：</span><span class="sxs-lookup"><span data-stu-id="7f50a-162">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="7f50a-163">**Delete**</span><span class="sxs-lookup"><span data-stu-id="7f50a-163">**Delete**</span></span>
       - <span data-ttu-id="7f50a-164">**預覽**</span><span class="sxs-lookup"><span data-stu-id="7f50a-164">**Preview**</span></span>
       - <span data-ttu-id="7f50a-165">**封鎖寄件者**</span><span class="sxs-lookup"><span data-stu-id="7f50a-165">**Block sender**</span></span>

   <span data-ttu-id="7f50a-166">這些許可權及其對隔離郵件和使用者垃圾郵件通知中的影響將在本文稍後的 [ [隔離原則許可權詳細資料](#quarantine-policy-permission-details) ] 區段中說明。</span><span class="sxs-lookup"><span data-stu-id="7f50a-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

   <span data-ttu-id="7f50a-167">完成後，按 [下一步 **]**。</span><span class="sxs-lookup"><span data-stu-id="7f50a-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7f50a-168">在出現的 [ **複查原則** ] 頁面上，複查您的設定。</span><span class="sxs-lookup"><span data-stu-id="7f50a-168">On the **Review policy** page that appears, review your settings.</span></span> <span data-ttu-id="7f50a-169">您可以在每個區段中選取 [編輯 **]**，以修改該區段內的設定。</span><span class="sxs-lookup"><span data-stu-id="7f50a-169">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="7f50a-170">或者，您可以按一下 [上一步] 或在精靈中選取特定頁面。</span><span class="sxs-lookup"><span data-stu-id="7f50a-170">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="7f50a-171">當您完成時，按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="7f50a-171">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="7f50a-172">在顯示的確認頁面上，按一下 [完成 **]**。</span><span class="sxs-lookup"><span data-stu-id="7f50a-172">On the confirmation page that appears, click **Done**.</span></span>

<span data-ttu-id="7f50a-173">現在，您已準備好將隔離原則指派給隔離功能（如 [步驟 2](#step-2-assign-a-quarantine-policy-to-supported-features) 區段所述）。</span><span class="sxs-lookup"><span data-stu-id="7f50a-173">Now you're ready to assign the quarantine policy to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-policy-to-supported-features) section.</span></span>

### <a name="create-quarantine-policies-in-powershell"></a><span data-ttu-id="7f50a-174">在 PowerShell 中建立隔離原則</span><span class="sxs-lookup"><span data-stu-id="7f50a-174">Create quarantine policies in PowerShell</span></span>

<span data-ttu-id="7f50a-175">如果您不想使用 PowerShell 建立隔離原則，請連線至 Exchange Online PowerShell 或 Exchange Online Protection PowerShell，並使用 **QuarantineTag 指令程式**。</span><span class="sxs-lookup"><span data-stu-id="7f50a-175">If you'd rather use PowerShell to create quarantine policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="7f50a-176">您有兩種不同的方法可供您選擇：</span><span class="sxs-lookup"><span data-stu-id="7f50a-176">You have two different methods to choose from:</span></span>

- <span data-ttu-id="7f50a-177">使用 _EndUserQuarantinePermissionsValue_ 參數。</span><span class="sxs-lookup"><span data-stu-id="7f50a-177">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="7f50a-178">使用 _EndUserQuarantinePermissions_ 參數。</span><span class="sxs-lookup"><span data-stu-id="7f50a-178">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="7f50a-179">這些方法將在下列各節中說明。</span><span class="sxs-lookup"><span data-stu-id="7f50a-179">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="7f50a-180">使用 EndUserQuarantinePermissionsValue 參數</span><span class="sxs-lookup"><span data-stu-id="7f50a-180">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="7f50a-181">若要使用 _EndUserQuarantinePermissionsValue_ 參數建立隔離原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="7f50a-181">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="7f50a-182">_EndUserQuarantinePermissionsValue_ 參數會使用從二進位值轉換而來的十進位值。</span><span class="sxs-lookup"><span data-stu-id="7f50a-182">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="7f50a-183">二進位值對應至可用的使用者隔離許可權特定順序。</span><span class="sxs-lookup"><span data-stu-id="7f50a-183">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="7f50a-184">針對每個許可權，值1等於 True，值0等於 False。</span><span class="sxs-lookup"><span data-stu-id="7f50a-184">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="7f50a-185">下表說明預設許可權群組中每個個別許可權的必要順序和值：</span><span class="sxs-lookup"><span data-stu-id="7f50a-185">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="7f50a-186">權限</span><span class="sxs-lookup"><span data-stu-id="7f50a-186">Permission</span></span>|<span data-ttu-id="7f50a-187">沒有存取權</span><span class="sxs-lookup"><span data-stu-id="7f50a-187">No access</span></span>|<span data-ttu-id="7f50a-188">限制存取</span><span class="sxs-lookup"><span data-stu-id="7f50a-188">Limited access</span></span>|<span data-ttu-id="7f50a-189">完全存取</span><span class="sxs-lookup"><span data-stu-id="7f50a-189">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="7f50a-190">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="7f50a-190">PermissionToAllowSender</span></span>|<span data-ttu-id="7f50a-191">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-191">0</span></span>|<span data-ttu-id="7f50a-192">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-192">0</span></span>|<span data-ttu-id="7f50a-193">1</span><span class="sxs-lookup"><span data-stu-id="7f50a-193">1</span></span>|
|<span data-ttu-id="7f50a-194">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="7f50a-194">PermissionToBlockSender</span></span>|<span data-ttu-id="7f50a-195">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-195">0</span></span>|<span data-ttu-id="7f50a-196">1</span><span class="sxs-lookup"><span data-stu-id="7f50a-196">1</span></span>|<span data-ttu-id="7f50a-197">1</span><span class="sxs-lookup"><span data-stu-id="7f50a-197">1</span></span>|
|<span data-ttu-id="7f50a-198">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="7f50a-198">PermissionToDelete</span></span>|<span data-ttu-id="7f50a-199">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-199">0</span></span>|<span data-ttu-id="7f50a-200">1</span><span class="sxs-lookup"><span data-stu-id="7f50a-200">1</span></span>|<span data-ttu-id="7f50a-201">1</span><span class="sxs-lookup"><span data-stu-id="7f50a-201">1</span></span>|
|<span data-ttu-id="7f50a-202">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f50a-202">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="7f50a-203">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-203">0</span></span>|<span data-ttu-id="7f50a-204">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-204">0</span></span>|<span data-ttu-id="7f50a-205">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-205">0</span></span>|
|<span data-ttu-id="7f50a-206">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="7f50a-206">PermissionToPreview</span></span>|<span data-ttu-id="7f50a-207">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-207">0</span></span>|<span data-ttu-id="7f50a-208">1</span><span class="sxs-lookup"><span data-stu-id="7f50a-208">1</span></span>|<span data-ttu-id="7f50a-209">1</span><span class="sxs-lookup"><span data-stu-id="7f50a-209">1</span></span>|
|<span data-ttu-id="7f50a-210">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f50a-210">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="7f50a-211">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-211">0</span></span>|<span data-ttu-id="7f50a-212">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-212">0</span></span>|<span data-ttu-id="7f50a-213">1</span><span class="sxs-lookup"><span data-stu-id="7f50a-213">1</span></span>|
|<span data-ttu-id="7f50a-214">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f50a-214">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="7f50a-215">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-215">0</span></span>|<span data-ttu-id="7f50a-216">1</span><span class="sxs-lookup"><span data-stu-id="7f50a-216">1</span></span>|<span data-ttu-id="7f50a-217">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-217">0</span></span>|
|<span data-ttu-id="7f50a-218">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f50a-218">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="7f50a-219">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-219">0</span></span>|<span data-ttu-id="7f50a-220">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-220">0</span></span>|<span data-ttu-id="7f50a-221">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-221">0</span></span>|
|<span data-ttu-id="7f50a-222">二進位值</span><span class="sxs-lookup"><span data-stu-id="7f50a-222">Binary value</span></span>|<span data-ttu-id="7f50a-223">00000000</span><span class="sxs-lookup"><span data-stu-id="7f50a-223">00000000</span></span>|<span data-ttu-id="7f50a-224">01101010</span><span class="sxs-lookup"><span data-stu-id="7f50a-224">01101010</span></span>|<span data-ttu-id="7f50a-225">11101100</span><span class="sxs-lookup"><span data-stu-id="7f50a-225">11101100</span></span>|
|<span data-ttu-id="7f50a-226">要使用的十進位數值</span><span class="sxs-lookup"><span data-stu-id="7f50a-226">Decimal value to use</span></span>|<span data-ttu-id="7f50a-227">0</span><span class="sxs-lookup"><span data-stu-id="7f50a-227">0</span></span>|<span data-ttu-id="7f50a-228">106</span><span class="sxs-lookup"><span data-stu-id="7f50a-228">106</span></span>|<span data-ttu-id="7f50a-229">236</span><span class="sxs-lookup"><span data-stu-id="7f50a-229">236</span></span>|
|

<span data-ttu-id="7f50a-230"><sup>\*</sup> 目前這個值永遠為0。</span><span class="sxs-lookup"><span data-stu-id="7f50a-230"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="7f50a-231">若為 PermissionToViewHeader，值0不會隱藏「 **查看郵件頁首** 」按鈕的隔離郵件的詳細資料 (按鈕永遠可供使用) 。</span><span class="sxs-lookup"><span data-stu-id="7f50a-231">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="7f50a-232"><sup>\*\*</sup> 請勿將這兩個值都設為1。</span><span class="sxs-lookup"><span data-stu-id="7f50a-232"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="7f50a-233">將 one 設定為1，另一個設定為0，或設定為0。</span><span class="sxs-lookup"><span data-stu-id="7f50a-233">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="7f50a-234">此範例會建立新的隔離原則名稱 NoAccess，該名稱會指派上表中所述的「沒有存取」許可權。</span><span class="sxs-lookup"><span data-stu-id="7f50a-234">This example creates a new quarantine policy name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="7f50a-235">若為「限制存取」許可權，請使用值106。</span><span class="sxs-lookup"><span data-stu-id="7f50a-235">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="7f50a-236">如需完整存取許可權，請使用值236。</span><span class="sxs-lookup"><span data-stu-id="7f50a-236">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="7f50a-237">若為自訂許可權，請使用上表取得與您想要的許可權相對應的二進位值。</span><span class="sxs-lookup"><span data-stu-id="7f50a-237">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="7f50a-238">將二進位值轉換為十進位值，並使用 _EndUserQuarantinePermissionsValue_ 參數的十進位值。</span><span class="sxs-lookup"><span data-stu-id="7f50a-238">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="7f50a-239">如需詳細的語法及參數資訊，請參閱 [QuarantineTag](/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-239">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="7f50a-240">使用 EndUserQuarantinePermissions 參數</span><span class="sxs-lookup"><span data-stu-id="7f50a-240">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="7f50a-241">若要使用 _EndUserQuarantinePermissionsValue_ 參數建立隔離原則，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="7f50a-241">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="7f50a-242">答：</span><span class="sxs-lookup"><span data-stu-id="7f50a-242">A.</span></span> <span data-ttu-id="7f50a-243">使用 **QuarantinePermissions 指令程式** ，將隔離權限物件儲存在變數中。</span><span class="sxs-lookup"><span data-stu-id="7f50a-243">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="7f50a-244">B。</span><span class="sxs-lookup"><span data-stu-id="7f50a-244">B.</span></span> <span data-ttu-id="7f50a-245">使用此變數做為 **QuarantineTag** 命令中的 _EndUserQuarantinePermissions_ 值。</span><span class="sxs-lookup"><span data-stu-id="7f50a-245">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="7f50a-246">步驟 A：將隔離權限物件儲存在變數中</span><span class="sxs-lookup"><span data-stu-id="7f50a-246">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="7f50a-247">使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="7f50a-247">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="7f50a-248">任何未使用參數的預設值為 `$false` ，所以您只需要使用您要設定值的參數 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="7f50a-248">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="7f50a-249">下列範例顯示如何建立與「預置」許可權群組相對應的權限物件：</span><span class="sxs-lookup"><span data-stu-id="7f50a-249">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="7f50a-250">**無存取權**：</span><span class="sxs-lookup"><span data-stu-id="7f50a-250">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="7f50a-251">**限制存取**：</span><span class="sxs-lookup"><span data-stu-id="7f50a-251">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="7f50a-252">**完全存取**：</span><span class="sxs-lookup"><span data-stu-id="7f50a-252">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="7f50a-253">若要查看您設定的值，請以命令 (執行變數名稱。例如，執行命令 `$NoAccess`) 。</span><span class="sxs-lookup"><span data-stu-id="7f50a-253">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="7f50a-254">若為自訂許可權，請勿將 _PermissionToRelease_ 和 _PermissionToRequestRelease_ 參數都設定為 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="7f50a-254">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="7f50a-255">將其中一個設為 `$true` ，並保留另一個為 `$false` ，或保留兩者 `$false` 。</span><span class="sxs-lookup"><span data-stu-id="7f50a-255">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="7f50a-256">您也可以在建立之後，使用 **QuarantinePermissions** 指令程式來修改現有的權限物件變數。</span><span class="sxs-lookup"><span data-stu-id="7f50a-256">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="7f50a-257">如需詳細的語法及參數資訊，請參閱 [QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-257">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="7f50a-258">步驟 B：使用 New-QuarantineTag 命令中的變數</span><span class="sxs-lookup"><span data-stu-id="7f50a-258">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="7f50a-259">在變數中建立及儲存權限物件之後，請在下列 **QuarantineTag** 命令中使用 _EndUserQuarantinePermission_ 參數值的變數：</span><span class="sxs-lookup"><span data-stu-id="7f50a-259">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="7f50a-260">此範例會使用 `$LimitedAccess` 上一個步驟中所述及建立的權限物件，建立名為 LimitedAccess 的新隔離原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-260">This example creates a new quarantine policy named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="7f50a-261">如需詳細的語法及參數資訊，請參閱 [QuarantineTag](/powershell/module/exchange/new-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-261">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a><span data-ttu-id="7f50a-262">步驟2：將隔離原則指派給支援的功能</span><span class="sxs-lookup"><span data-stu-id="7f50a-262">Step 2: Assign a quarantine policy to supported features</span></span>

<span data-ttu-id="7f50a-263">在 [隔離郵件或檔案 (會自動或作為可設定動作) 的 _支援_ 保護功能中，您可以將隔離原則指派給可用的隔離動作。</span><span class="sxs-lookup"><span data-stu-id="7f50a-263">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine policy to the available quarantine actions.</span></span> <span data-ttu-id="7f50a-264">下表說明隔離郵件和隔離原則可用性的功能：</span><span class="sxs-lookup"><span data-stu-id="7f50a-264">Features that quarantine messages and the availability of quarantine policies are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="7f50a-265">功能</span><span class="sxs-lookup"><span data-stu-id="7f50a-265">Feature</span></span>|<span data-ttu-id="7f50a-266">支援的隔離原則？</span><span class="sxs-lookup"><span data-stu-id="7f50a-266">Quarantine policies supported?</span></span>|<span data-ttu-id="7f50a-267">使用的預設隔離原則</span><span class="sxs-lookup"><span data-stu-id="7f50a-267">Default quarantine policies used</span></span>|
|---|:---:|---|
|<span data-ttu-id="7f50a-268">[反垃圾郵件原則](configure-your-spam-filter-policies.md)：</span><span class="sxs-lookup"><span data-stu-id="7f50a-268">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="7f50a-269">**垃圾郵件** (_SpamAction_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-269">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="7f50a-270">**高信賴垃圾郵件** (_HighConfidenceSpamAction_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-270">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="7f50a-271">**網路釣魚** (_PhishSpamAction_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-271">**Phishing** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="7f50a-272">**高信賴網路釣魚** (_HighConfidencePhishAction_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-272">**High confidence phishing** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="7f50a-273">**大量** (_BulkSpamAction_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-273">**Bulk** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="7f50a-274">是</span><span class="sxs-lookup"><span data-stu-id="7f50a-274">Yes</span></span>|<ul><li><span data-ttu-id="7f50a-275">DefaultSpamTag (完整存取) </span><span class="sxs-lookup"><span data-stu-id="7f50a-275">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="7f50a-276">DefaultHighConfSpamTag (完整存取) </span><span class="sxs-lookup"><span data-stu-id="7f50a-276">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="7f50a-277">DefaultPhishTag (完整存取) </span><span class="sxs-lookup"><span data-stu-id="7f50a-277">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="7f50a-278">DefaultHighConfPhishTag (無法存取) </span><span class="sxs-lookup"><span data-stu-id="7f50a-278">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="7f50a-279">DefaultBulkTag (完整存取) </span><span class="sxs-lookup"><span data-stu-id="7f50a-279">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="7f50a-280">反網路釣魚原則：</span><span class="sxs-lookup"><span data-stu-id="7f50a-280">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="7f50a-281">_AuthenticationFailAction_ 的 [欺騙情報防護](set-up-anti-phishing-policies.md#spoof-settings) () </span><span class="sxs-lookup"><span data-stu-id="7f50a-281">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="7f50a-282">[類比保護](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)：<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7f50a-282">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="7f50a-283">**如果偵測到郵件為類比使用者** (_TargetedUserProtectionAction_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-283">**If message is detected as an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="7f50a-284">**如果偵測到郵件為類比網域** (_TargetedDomainProtectionAction_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-284">**If message is detected as an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="7f50a-285">**如果信箱智慧偵測和模仿使用者** (_MailboxIntelligenceProtectionAction_) </span><span class="sxs-lookup"><span data-stu-id="7f50a-285">**If mailbox intelligence detects and impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="7f50a-286">否</span><span class="sxs-lookup"><span data-stu-id="7f50a-286">No</span></span>|<span data-ttu-id="7f50a-287">不適用</span><span class="sxs-lookup"><span data-stu-id="7f50a-287">n/a</span></span>|
|<span data-ttu-id="7f50a-288">[反惡意程式碼原則](configure-anti-malware-policies.md)：永遠會隔離所有偵測到的郵件。</span><span class="sxs-lookup"><span data-stu-id="7f50a-288">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="7f50a-289">否</span><span class="sxs-lookup"><span data-stu-id="7f50a-289">No</span></span>|<span data-ttu-id="7f50a-290">不適用</span><span class="sxs-lookup"><span data-stu-id="7f50a-290">n/a</span></span>|
|[<span data-ttu-id="7f50a-291">適用於 SharePoint、OneDrive 和 Microsoft Teams 的安全附件</span><span class="sxs-lookup"><span data-stu-id="7f50a-291">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)|<span data-ttu-id="7f50a-292">否</span><span class="sxs-lookup"><span data-stu-id="7f50a-292">No</span></span>|<span data-ttu-id="7f50a-293">不適用</span><span class="sxs-lookup"><span data-stu-id="7f50a-293">n/a</span></span>|
|<span data-ttu-id="7f50a-294">[郵件流程規則](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (也稱為傳輸規則) 具有動作：將 **郵件傳遞至主控隔離** (_隔離_) 。</span><span class="sxs-lookup"><span data-stu-id="7f50a-294">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="7f50a-295">否</span><span class="sxs-lookup"><span data-stu-id="7f50a-295">No</span></span>|<span data-ttu-id="7f50a-296">不適用</span><span class="sxs-lookup"><span data-stu-id="7f50a-296">n/a</span></span>|
|

<span data-ttu-id="7f50a-297"><sup>\*</sup>模擬保護設定僅適用于 Microsoft Defender 的 Office 365 中的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-297"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="7f50a-298">如果您很喜歡預設隔離原則所提供的使用者權限，您不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="7f50a-298">If you're happy with the end-user permissions that are provided by the default quarantine policies, you don't need to do anything.</span></span> <span data-ttu-id="7f50a-299">如果您想要自訂使用者功能 (可用按鈕) 使用者垃圾郵件通知或隔離的郵件詳細資料中，您可以指派自訂隔離原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-299">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine policy.</span></span>

### <a name="assign-quarantine-policies-in-anti-spam-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="7f50a-300">在 Microsoft 365 Defender 入口網站中的反垃圾郵件原則中指派隔離原則</span><span class="sxs-lookup"><span data-stu-id="7f50a-300">Assign quarantine policies in anti-spam policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="7f50a-301">在 [EOP 中設定反垃圾郵件原則](configure-your-spam-filter-policies.md)，說明建立及修改反垃圾郵件原則的完整指示。</span><span class="sxs-lookup"><span data-stu-id="7f50a-301">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="7f50a-302">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 &** 共同作業 \> **原則 & 規則** \> **原則**] 區段 \> **反垃圾郵件**。</span><span class="sxs-lookup"><span data-stu-id="7f50a-302">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Policies** section \> **Anti-spam**.</span></span> <span data-ttu-id="7f50a-303">或者，開啟 <https://security.microsoft.com/antispam> 。</span><span class="sxs-lookup"><span data-stu-id="7f50a-303">Or, open <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="7f50a-304">在 [ **反垃圾郵件原則** ] 頁面上，執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="7f50a-304">On the **Anti-spam policies** page, do one of the following steps:</span></span>
   - <span data-ttu-id="7f50a-305">尋找並選取現有的 **輸入** 反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-305">Find and select an existing **inbound** anti-spam policy.</span></span>
   - <span data-ttu-id="7f50a-306">建立新的 **輸入** 反垃圾郵件原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-306">Create a new **inbound** anti-spam policy.</span></span>

3. <span data-ttu-id="7f50a-307">執行下列其中一個步驟：</span><span class="sxs-lookup"><span data-stu-id="7f50a-307">Do one of the following steps:</span></span>
   - <span data-ttu-id="7f50a-308">**編輯現有的反垃圾郵件原則**：在 [原則詳細資料] 快顯視窗中，移至 [ **動作** ] 區段，然後按一下 [ **編輯動作**]。</span><span class="sxs-lookup"><span data-stu-id="7f50a-308">**Edit existing anti-spam policy**: In the policy details flyout, go to the **Actions** section and then click **Edit actions**.</span></span>
   - <span data-ttu-id="7f50a-309">**建立新的反垃圾郵件原則**：在 [新增原則] 嚮導中，移至 [ **動作** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7f50a-309">**Create new anti-spam policy**: In the new policy wizard, go to the **Actions** page.</span></span>

4. <span data-ttu-id="7f50a-310">在 [ **動作** ] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="7f50a-310">On the **Actions** page.</span></span> <span data-ttu-id="7f50a-311">每個具有 **隔離消息** 動作的判定也會有 [ **選取隔離原則** ] 方塊，以選取對應的隔離原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-311">every verdict that has the **Quarantine message** action will also have the **Select quarantine policy** box for you to select a corresponding quarantine policy.</span></span>

   <span data-ttu-id="7f50a-312">**附注**：當您建立新的原則時，空白的 **選取隔離原則** 值會指出使用該判定的預設隔離原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-312">**Note**: When you create a new policy, a blank **Select quarantine policy** value indicates the default quarantine policy for that verdict is used.</span></span> <span data-ttu-id="7f50a-313">當您後來編輯原則時，空白值會以實際的預設隔離原則名稱取代，如上表所述。</span><span class="sxs-lookup"><span data-stu-id="7f50a-313">When you later edit the policy, the blank values are replaced by the actual default quarantine policy names as described in the previous table.</span></span>

   ![反垃圾郵件原則中的隔離原則選擇](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="7f50a-315">完成後，點擊 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="7f50a-315">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-policies-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="7f50a-316">在 PowerShell 中的反垃圾郵件原則中指派隔離原則</span><span class="sxs-lookup"><span data-stu-id="7f50a-316">Assign quarantine policies in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="7f50a-317">如果您想要使用 PowerShell 來指派反垃圾郵件原則中的隔離原則，請連接到 Exchange Online PowerShell 或 Exchange Online Protection PowerShell，並使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="7f50a-317">If you'd rather use PowerShell to assign quarantine policies in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="7f50a-318">**附註**：</span><span class="sxs-lookup"><span data-stu-id="7f50a-318">**Notes**:</span></span>

- <span data-ttu-id="7f50a-319">_HighConfidencePhishAction_ 參數的預設值是「隔離」，所以您不需要為新反垃圾郵件原則中的高可信度網路釣魚偵測設定隔離動作。</span><span class="sxs-lookup"><span data-stu-id="7f50a-319">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="7f50a-320">針對新的或現有的反垃圾郵件原則中的所有其他垃圾郵件篩選 verdicts，隔離原則只有在 action 值為「隔離」時才有效。</span><span class="sxs-lookup"><span data-stu-id="7f50a-320">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine policy is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="7f50a-321">若要查看現有反垃圾郵件原則中的動作值，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7f50a-321">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="7f50a-322">如需有關 Standard 和 Strict 之預設動作值及建議動作值的詳細資訊，請參閱 [EOP 反垃圾郵件原則設定](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-322">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="7f50a-323">垃圾郵件篩選會判定沒有對應的隔離原則參數，這表示使用該判定的 [預設隔離原則](#step-2-assign-a-quarantine-policy-to-supported-features) 。</span><span class="sxs-lookup"><span data-stu-id="7f50a-323">A spam filtering verdict without a corresponding quarantine policy parameter means the [default quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="7f50a-324">如果您想要變更隔離郵件的預設使用者功能，您只需要將預設隔離原則取代為自訂隔離原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-324">You only need to replace a default quarantine policy with a custom quarantine policy if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="7f50a-325">PowerShell 中的新反垃圾郵件原則需要垃圾郵件篩選原則 (設定) 使用 **New-HostedContentFilterPolicy** 指令程式和新的垃圾郵件篩選規則 (收件者篩選器) 使用 **New-HostedContentFilterRule** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7f50a-325">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="7f50a-326">如需相關指示，請參閱 [使用 PowerShell 建立反垃圾郵件原則](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-326">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="7f50a-327">此範例會使用下列設定來建立名為「Research 部門」的新垃圾郵件篩選原則：</span><span class="sxs-lookup"><span data-stu-id="7f50a-327">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="7f50a-328">所有垃圾郵件篩選 verdicts 的動作都設為隔離。</span><span class="sxs-lookup"><span data-stu-id="7f50a-328">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="7f50a-329">名為「NoAccess 的自訂隔離原則指派「 **沒有存取** 權」許可權會取代預設尚未 **指派任何** 預設隔離原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-329">The custom quarantine policy named NoAccess that assigns **No access** permissions replaces any default quarantine policies that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="7f50a-330">如需詳細的語法及參數資訊，請參閱 [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-330">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="7f50a-331">此範例會修改名為「人力資源」的現有垃圾郵件篩選原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-331">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="7f50a-332">垃圾郵件隔離判定的動作會設定為 [隔離]，而且會指派名為 NoAccess 的自訂隔離原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-332">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine policy named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="7f50a-333">如需詳細的語法及參數資訊，請參閱 [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-333">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="7f50a-334">在 Microsoft 365 Defender 入口網站中設定全域隔離通知設定</span><span class="sxs-lookup"><span data-stu-id="7f50a-334">Configure global quarantine notification settings in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="7f50a-335">隔離原則的全域設定可讓您自訂使用者的垃圾郵件通知，該通知會傳送給被隔離的郵件收件者。</span><span class="sxs-lookup"><span data-stu-id="7f50a-335">The global settings for quarantine policies allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="7f50a-336">如需這些通知的詳細資訊，請參閱 [使用者垃圾郵件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-336">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="7f50a-337">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 & 協同** \> **威脅原則**] \> 區段 \> **隔離原則**，然後選取 [**隔離原則**]。</span><span class="sxs-lookup"><span data-stu-id="7f50a-337">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="7f50a-338">在 [ **隔離原則** ] 頁面上，選取 [ **通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="7f50a-338">On the **Quarantine policy** page, select **Global settings**.</span></span>

3. <span data-ttu-id="7f50a-339">在開啟的 [ **隔離通知設定** ] 浮出控制項中，設定下列部分或所有設定：</span><span class="sxs-lookup"><span data-stu-id="7f50a-339">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="7f50a-340">**顯示名稱**：自訂在使用者垃圾郵件通知中使用的寄件者顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="7f50a-340">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="7f50a-341">針對您新增的每種語言，在 [第二語言] 方塊中選取語言 (不要按一下 X) ，然後在 [ **顯示名稱** ] 方塊中輸入您想要的文字值。</span><span class="sxs-lookup"><span data-stu-id="7f50a-341">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="7f50a-342">下列螢幕擷取畫面顯示使用者垃圾郵件通知中的自訂顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="7f50a-342">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![最終使用者垃圾郵件通知中的自訂寄件者顯示名稱](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="7f50a-344">**免責聲明**：將自訂免責聲明新增至使用者垃圾郵件通知的底部。</span><span class="sxs-lookup"><span data-stu-id="7f50a-344">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="7f50a-345">當地語系化的文字（ **來自您組織的免責聲明** ）永遠包含在第一列，接著您指定的文字。</span><span class="sxs-lookup"><span data-stu-id="7f50a-345">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="7f50a-346">針對您已新增的每種語言，選取 [第二語言] 方塊中的語言 (請勿按一下 X) ，然後在 [ **免責聲明** ] 方塊中輸入您想要的文字值。</span><span class="sxs-lookup"><span data-stu-id="7f50a-346">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="7f50a-347">下列螢幕擷取畫面顯示使用者垃圾郵件通知中的自訂免責聲明：</span><span class="sxs-lookup"><span data-stu-id="7f50a-347">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![最終使用者垃圾郵件通知底部的自訂免責聲明](../../media/quarantine-tags-esn-customization-disclaimer.png)

   - <span data-ttu-id="7f50a-349">**選擇語言**：使用者垃圾郵件通知已根據收件者的語言設定進行當地語系化。</span><span class="sxs-lookup"><span data-stu-id="7f50a-349">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="7f50a-350">您可以針對 **顯示名稱** 和 **免責聲明** 值，以不同語言指定自訂的文字。</span><span class="sxs-lookup"><span data-stu-id="7f50a-350">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="7f50a-351">選取 [第一個語言] 方塊中至少一種語言，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="7f50a-351">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="7f50a-352">您可以在每個語言之後按一下 [ **新增** ]，以選取多種語言。</span><span class="sxs-lookup"><span data-stu-id="7f50a-352">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="7f50a-353">[區段語言] 方塊會顯示您所選取的所有語言：</span><span class="sxs-lookup"><span data-stu-id="7f50a-353">A section language box shows all of the languages that you've selected:</span></span>

     ![隔離原則全域隔離通知設定中的 [第二語言] 方塊中選取的語言](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="7f50a-355">**使用我的公司徽標**：選取此選項以取代在使用者垃圾郵件通知頂端使用的預設 Microsoft 標誌。</span><span class="sxs-lookup"><span data-stu-id="7f50a-355">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="7f50a-356">在執行這項作業之前，您必須遵循[自訂群組織的 Microsoft 365 主題](../../admin/setup/customize-your-organization-theme.md)中的指示，以上傳自訂的徽標。</span><span class="sxs-lookup"><span data-stu-id="7f50a-356">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="7f50a-357">下列螢幕擷取畫面顯示使用者垃圾郵件通知中的自訂標誌：</span><span class="sxs-lookup"><span data-stu-id="7f50a-357">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![最終使用者垃圾郵件通知中的自訂標誌](../../media/quarantine-tags-esn-customization-logo.png)

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="7f50a-359">在 Microsoft 365 Defender 入口網站中查看隔離原則</span><span class="sxs-lookup"><span data-stu-id="7f50a-359">View quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="7f50a-360">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 & 協同** \> **威脅原則**] \> 區段 \> **隔離原則**，然後選取 [**隔離原則**]。</span><span class="sxs-lookup"><span data-stu-id="7f50a-360">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="7f50a-361">[ **隔離原則** ] 頁面會依 **名稱** 和 **上次更新** 日期顯示原則清單。</span><span class="sxs-lookup"><span data-stu-id="7f50a-361">The **Quarantine policy** page shows the list of policies by **Name** and **Last updated** date.</span></span>

3. <span data-ttu-id="7f50a-362">若要查看內建或自訂隔離原則的設定，請按一下名稱以從清單中選取隔離原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-362">To view the settings of built-in or custom quarantine policies, select the quarantine policy from the list by clicking on the name.</span></span>

4. <span data-ttu-id="7f50a-363">若要查看全域設定，請按一下 [**通用設定**]。</span><span class="sxs-lookup"><span data-stu-id="7f50a-363">To view the global settings, click **Global settings**</span></span>

### <a name="view-quarantine-policies-in-powershell"></a><span data-ttu-id="7f50a-364">在 PowerShell 中查看隔離原則</span><span class="sxs-lookup"><span data-stu-id="7f50a-364">View quarantine policies in PowerShell</span></span>

<span data-ttu-id="7f50a-365">如果您不想使用 PowerShell 來查看隔離原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="7f50a-365">If you'd rather use PowerShell to view quarantine policies, do any of the following steps:</span></span>

- <span data-ttu-id="7f50a-366">若要查看所有內建或自訂原則的摘要清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7f50a-366">To view a summary list of all built-in or custom policies, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="7f50a-367">若要查看內建或自訂隔離原則的設定，請 \<QuarantinePolicyName\> 以隔離原則的名稱取代，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7f50a-367">To view the settings of built-in or custom quarantine policies, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<QuarantinePolicyName>"
  ```

- <span data-ttu-id="7f50a-368">若要查看全域設定，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7f50a-368">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="7f50a-369">如需詳細的語法及參數資訊，請參閱 [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-369">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="7f50a-370">在 Microsoft 365 Defender 入口網站中修改隔離原則</span><span class="sxs-lookup"><span data-stu-id="7f50a-370">Modify quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="7f50a-371">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 & 協同** \> **威脅原則**] \> 區段 \> **隔離原則**，然後選取 [**隔離原則**]。</span><span class="sxs-lookup"><span data-stu-id="7f50a-371">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="7f50a-372">在 [ **隔離原則** ] 頁面上，按一下名稱以選取原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-372">On the **Quarantine policies** page, select the policy by clicking on the name.</span></span>

3. <span data-ttu-id="7f50a-373">選取原則之後，按一下所出現的 [ ![ 編輯原則圖示] [ ](../../media/m365-cc-sc-edit-icon.png) **編輯原則** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="7f50a-373">After you select the policy, click the ![Edit policy icon](../../media/m365-cc-sc-edit-icon.png) **Edit policy** icon that appears.</span></span>

4. <span data-ttu-id="7f50a-374">開啟的 **編輯原則** 嚮導與 **新的原則** 嚮導實際上完全相同，如本文稍早的 Microsoft 365 Defender 入口網站一節中的 [建立隔離原則中](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal)所述。</span><span class="sxs-lookup"><span data-stu-id="7f50a-374">The **Edit policy** wizard that opens is virtually identical to the **New policy** wizard as described in the [Create quarantine policies in the Microsoft 365 Defender portal](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) section earlier in this article.</span></span>

   <span data-ttu-id="7f50a-375">主要差異為：您無法重新命名現有的原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-375">The main difference is: you can't rename an existing policy.</span></span>

5. <span data-ttu-id="7f50a-376">完成修改原則之後，請移至 [ **摘要** ] 頁面，然後按一下 [ **提交**]。</span><span class="sxs-lookup"><span data-stu-id="7f50a-376">When you're finished modifying the policy, go to the **Summary** page and click **Submit**.</span></span>

### <a name="modify-quarantine-policies-in-powershell"></a><span data-ttu-id="7f50a-377">在 PowerShell 中修改隔離原則</span><span class="sxs-lookup"><span data-stu-id="7f50a-377">Modify quarantine policies in PowerShell</span></span>

<span data-ttu-id="7f50a-378">如果您不想使用 PowerShell 修改自訂隔離原則，請 \<QuarantinePolicyName\> 以隔離原則的名稱取代，並使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="7f50a-378">If you'd rather use PowerShell to modify a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and use the following syntax:</span></span>

```powershell
Set-QuarantineTag -Identity "<QuarantinePolicyName>" [Settings]
```

<span data-ttu-id="7f50a-379">可用設定與在本文稍早建立隔離原則所述。</span><span class="sxs-lookup"><span data-stu-id="7f50a-379">The available settings are the same as described for creating quarantine policies earlier in this article.</span></span>

<span data-ttu-id="7f50a-380">如需詳細的語法及參數資訊，請參閱 [Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-380">For detailed syntax and parameter information, see [Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag).</span></span>

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="7f50a-381">在 Microsoft 365 Defender 入口網站中移除隔離原則</span><span class="sxs-lookup"><span data-stu-id="7f50a-381">Remove quarantine policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="7f50a-382">**附註**：</span><span class="sxs-lookup"><span data-stu-id="7f50a-382">**Notes**:</span></span>

- <span data-ttu-id="7f50a-383">您無法移除內建的隔離原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-383">You can't remove built-in quarantine policies.</span></span>
- <span data-ttu-id="7f50a-384">移除自訂隔離原則之前，請確認未使用該原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-384">Before you remove a custom quarantine policy, verify that it's not being used.</span></span> <span data-ttu-id="7f50a-385">例如，在 PowerShell: 中執行下列命令</span><span class="sxs-lookup"><span data-stu-id="7f50a-385">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="7f50a-386">若要使用隔離原則，請 [取代指派的隔離原則](#step-2-assign-a-quarantine-policy-to-supported-features) ，再將其移除。</span><span class="sxs-lookup"><span data-stu-id="7f50a-386">If the quarantine policy is being used, [replace the assigned quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="7f50a-387">在 Microsoft 365 Defender 入口網站中，移至 [**電子郵件 & 協同** \> **威脅原則**] \> 區段 \> **隔離原則**，然後選取 [**隔離原則**]。</span><span class="sxs-lookup"><span data-stu-id="7f50a-387">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="7f50a-388">在 [ **隔離原則** ] 頁面上，按一下名稱以選取您要移除的自訂隔離原則。</span><span class="sxs-lookup"><span data-stu-id="7f50a-388">On the **Quarantine policy** page, select the custom quarantine policy that you want to remove by clicking on the name.</span></span>

3. <span data-ttu-id="7f50a-389">選取原則之後，按一下所出現的 [ ![ 刪除原則圖示 ](../../media/m365-cc-sc-delete-icon.png) **刪除原則** ] 圖示。</span><span class="sxs-lookup"><span data-stu-id="7f50a-389">After you select the policy, click the ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy** icon that appears.</span></span>

4. <span data-ttu-id="7f50a-390">在出現的確認對話方塊中，按一下 [ **移除原則** ]。</span><span class="sxs-lookup"><span data-stu-id="7f50a-390">Click **Remove policy** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-policies-in-powershell"></a><span data-ttu-id="7f50a-391">在 PowerShell 中移除隔離原則</span><span class="sxs-lookup"><span data-stu-id="7f50a-391">Remove quarantine policies in PowerShell</span></span>

<span data-ttu-id="7f50a-392">如果您不想使用 PowerShell 移除自訂隔離原則，請 \<QuarantinePolicyName\> 以隔離原則的名稱取代，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7f50a-392">If you'd rather use PowerShell to remove a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<QuarantinePolicyName>"
```

<span data-ttu-id="7f50a-393">如需詳細的語法及參數資訊，請參閱 [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-393">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-policy-permission-details"></a><span data-ttu-id="7f50a-394">隔離原則許可權詳細資料</span><span class="sxs-lookup"><span data-stu-id="7f50a-394">Quarantine policy permission details</span></span>

<span data-ttu-id="7f50a-395">下列各節說明在隔離郵件和使用者垃圾郵件通知的詳細資料中，預置許可權群組和個別許可權的影響。</span><span class="sxs-lookup"><span data-stu-id="7f50a-395">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="7f50a-396">預設許可權群組</span><span class="sxs-lookup"><span data-stu-id="7f50a-396">Preset permissions groups</span></span>

<span data-ttu-id="7f50a-397">在「預置」許可權群組中包含的個別許可權會列在本文開頭的表格中。</span><span class="sxs-lookup"><span data-stu-id="7f50a-397">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="7f50a-398">沒有存取權</span><span class="sxs-lookup"><span data-stu-id="7f50a-398">No access</span></span>

<span data-ttu-id="7f50a-399">如果隔離原則指派「 **無存取** 」許可權 (無許可權) ，使用者仍會取得某些基準功能：</span><span class="sxs-lookup"><span data-stu-id="7f50a-399">If the quarantine policy assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="7f50a-400">**隔離的郵件詳細資料**： [ **View message header** ] 按鈕永遠可供使用。</span><span class="sxs-lookup"><span data-stu-id="7f50a-400">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![隔離原則提供使用者沒有存取許可權時，隔離的郵件詳細資料中可用的按鈕](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="7f50a-402">**使用者垃圾郵件通知**：將使用者帶至隔離區中郵件的 [ **檢查** ] 按鈕永遠可供使用。</span><span class="sxs-lookup"><span data-stu-id="7f50a-402">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![當隔離原則給使用者「沒有存取許可權」時，使用者垃圾郵件通知中的可用按鈕](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="7f50a-404">限制存取</span><span class="sxs-lookup"><span data-stu-id="7f50a-404">Limited access</span></span>

<span data-ttu-id="7f50a-405">如果隔離原則指派「 **限制存取** 」許可權，使用者就能取得下列功能：</span><span class="sxs-lookup"><span data-stu-id="7f50a-405">If the quarantine policy assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="7f50a-406">**隔離的郵件詳細資料**：下列按鈕可用：</span><span class="sxs-lookup"><span data-stu-id="7f50a-406">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="7f50a-407">**要求版本**</span><span class="sxs-lookup"><span data-stu-id="7f50a-407">**Request release**</span></span>
  - <span data-ttu-id="7f50a-408">**查看郵件頭**</span><span class="sxs-lookup"><span data-stu-id="7f50a-408">**View message header**</span></span>
  - <span data-ttu-id="7f50a-409">**預覽郵件**</span><span class="sxs-lookup"><span data-stu-id="7f50a-409">**Preview message**</span></span>
  - <span data-ttu-id="7f50a-410">**封鎖寄件者**</span><span class="sxs-lookup"><span data-stu-id="7f50a-410">**Block sender**</span></span>
  - <span data-ttu-id="7f50a-411">**從隔離區移除**</span><span class="sxs-lookup"><span data-stu-id="7f50a-411">**Remove from quarantine**</span></span>

  ![隔離原則提供使用者限制存取權限時，隔離郵件詳細資料中可用的按鈕](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="7f50a-413">**使用者垃圾郵件通知**：下列按鈕可用：</span><span class="sxs-lookup"><span data-stu-id="7f50a-413">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="7f50a-414">**封鎖寄件者**</span><span class="sxs-lookup"><span data-stu-id="7f50a-414">**Block sender**</span></span>
  - <span data-ttu-id="7f50a-415">**檢閱**</span><span class="sxs-lookup"><span data-stu-id="7f50a-415">**Review**</span></span>

  ![當隔離原則提供使用者限制存取權限時，使用者垃圾郵件通知中可用的按鈕](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="7f50a-417">完全存取</span><span class="sxs-lookup"><span data-stu-id="7f50a-417">Full access</span></span>

<span data-ttu-id="7f50a-418">如果隔離原則指派「 **完整存取** 」許可權 (所有可用許可權) ，使用者會收到下列功能：</span><span class="sxs-lookup"><span data-stu-id="7f50a-418">If the quarantine policy assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="7f50a-419">**隔離的郵件詳細資料**：下列按鈕可用：</span><span class="sxs-lookup"><span data-stu-id="7f50a-419">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="7f50a-420">**Release message**</span><span class="sxs-lookup"><span data-stu-id="7f50a-420">**Release message**</span></span>
  - <span data-ttu-id="7f50a-421">**查看郵件頭**</span><span class="sxs-lookup"><span data-stu-id="7f50a-421">**View message header**</span></span>
  - <span data-ttu-id="7f50a-422">**預覽郵件**</span><span class="sxs-lookup"><span data-stu-id="7f50a-422">**Preview message**</span></span>
  - <span data-ttu-id="7f50a-423">**封鎖寄件者**</span><span class="sxs-lookup"><span data-stu-id="7f50a-423">**Block sender**</span></span>
  - <span data-ttu-id="7f50a-424">**允許寄件者**</span><span class="sxs-lookup"><span data-stu-id="7f50a-424">**Allow sender**</span></span>
  - <span data-ttu-id="7f50a-425">**從隔離區移除**</span><span class="sxs-lookup"><span data-stu-id="7f50a-425">**Remove from quarantine**</span></span>

  ![隔離原則提供使用者「完整存取」許可權時，隔離的郵件詳細資料中可用的按鈕。](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="7f50a-427">**使用者垃圾郵件通知**：下列按鈕可用：</span><span class="sxs-lookup"><span data-stu-id="7f50a-427">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="7f50a-428">**封鎖寄件者**</span><span class="sxs-lookup"><span data-stu-id="7f50a-428">**Block sender**</span></span>
  - <span data-ttu-id="7f50a-429">**發行**</span><span class="sxs-lookup"><span data-stu-id="7f50a-429">**Release**</span></span>
  - <span data-ttu-id="7f50a-430">**檢閱**</span><span class="sxs-lookup"><span data-stu-id="7f50a-430">**Review**</span></span>

  ![當隔離原則提供使用者「完整存取」許可權時，使用者垃圾郵件通知中的可用按鈕](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="7f50a-432">個別許可權</span><span class="sxs-lookup"><span data-stu-id="7f50a-432">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="7f50a-433">請記住，使用者永遠會收到「 [無法存取](#no-access) 」區段中所述的按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f50a-433">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="7f50a-434">這些按鈕不會包含在個別的許可權描述中。</span><span class="sxs-lookup"><span data-stu-id="7f50a-434">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="7f50a-435">允許寄件者許可權</span><span class="sxs-lookup"><span data-stu-id="7f50a-435">Allow sender permission</span></span>

<span data-ttu-id="7f50a-436">[**允許寄件者**] 許可權會 (_PermissionToAllowSender_) 控制對按鈕的存取權，讓使用者可以輕鬆地將隔離的郵件寄件者新增至其保管庫寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="7f50a-436">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="7f50a-437">**隔離的郵件詳細資料**：</span><span class="sxs-lookup"><span data-stu-id="7f50a-437">**Quarantined message details**:</span></span>
  - <span data-ttu-id="7f50a-438">啟用 [**允許寄件者**] 許可權：可以使用 [**允許寄件者**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f50a-438">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="7f50a-439">**允許停用寄件者** 許可權：無法使用 [ **允許寄件者** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f50a-439">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="7f50a-440">**使用者垃圾郵件通知**：沒有作用。</span><span class="sxs-lookup"><span data-stu-id="7f50a-440">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="7f50a-441">如需保管庫寄件者清單的詳細資訊，請參閱[防止受信任的寄件者遭到封鎖](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666)，並[使用 Exchange Online PowerShell 設定信箱上的安全清單集合](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-441">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="7f50a-442">封鎖寄件者許可權</span><span class="sxs-lookup"><span data-stu-id="7f50a-442">Block sender permission</span></span>

<span data-ttu-id="7f50a-443">**Block sender** 許可權 (_PermissionToBlockSender_) 控制對按鈕的存取權，讓使用者可以輕鬆地將隔離的郵件寄件者新增至其封鎖的寄件者清單。</span><span class="sxs-lookup"><span data-stu-id="7f50a-443">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="7f50a-444">**隔離的郵件詳細資料**：</span><span class="sxs-lookup"><span data-stu-id="7f50a-444">**Quarantined message details**:</span></span>
  - <span data-ttu-id="7f50a-445">已啟用 **封鎖寄件者** 許可權：可用的 **封鎖寄件者** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f50a-445">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="7f50a-446">禁止 **封鎖寄件者** 許可權：無法使用 [**封鎖寄件者**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f50a-446">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="7f50a-447">**使用者垃圾郵件通知**：</span><span class="sxs-lookup"><span data-stu-id="7f50a-447">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="7f50a-448">禁止 **封鎖寄件者** 許可權：無法使用 [**封鎖寄件者**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f50a-448">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="7f50a-449">已啟用 **封鎖寄件者** 許可權：可用的 **封鎖寄件者** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f50a-449">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="7f50a-450">如需有關封鎖的寄件者清單的詳細資訊，請參閱[封鎖來自某人的郵件](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667)，並[使用 Exchange Online PowerShell 設定信箱上的安全清單集合](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。</span><span class="sxs-lookup"><span data-stu-id="7f50a-450">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="7f50a-451">刪除權限</span><span class="sxs-lookup"><span data-stu-id="7f50a-451">Delete permission</span></span>

<span data-ttu-id="7f50a-452">「 **刪除** 」許可權 (_PermissionToDelete_) 會控制使用者對其郵件的功能 (郵件的收件者) 從隔離區。</span><span class="sxs-lookup"><span data-stu-id="7f50a-452">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="7f50a-453">**隔離的郵件詳細資料**：</span><span class="sxs-lookup"><span data-stu-id="7f50a-453">**Quarantined message details**:</span></span>
  - <span data-ttu-id="7f50a-454">已啟用 **刪除** 許可權：可以使用 [**從隔離區移除**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f50a-454">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="7f50a-455">已停用 **刪除** 許可權：無法使用 [**從隔離區移除**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f50a-455">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="7f50a-456">**使用者垃圾郵件通知**：沒有作用。</span><span class="sxs-lookup"><span data-stu-id="7f50a-456">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="7f50a-457">預覽許可權</span><span class="sxs-lookup"><span data-stu-id="7f50a-457">Preview permission</span></span>

<span data-ttu-id="7f50a-458">**預覽** 許可權 (_PermissionToPreview_) 控制使用者的功能，以在隔離區中預覽其郵件。</span><span class="sxs-lookup"><span data-stu-id="7f50a-458">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="7f50a-459">**隔離的郵件詳細資料**：</span><span class="sxs-lookup"><span data-stu-id="7f50a-459">**Quarantined message details**:</span></span>
  - <span data-ttu-id="7f50a-460">已啟用 **預覽** 許可權： [**預覽郵件**] 按鈕可供使用。</span><span class="sxs-lookup"><span data-stu-id="7f50a-460">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="7f50a-461">已停用 **預覽** 許可權：無法使用 **預覽郵件** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f50a-461">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="7f50a-462">**使用者垃圾郵件通知**：沒有作用。</span><span class="sxs-lookup"><span data-stu-id="7f50a-462">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="7f50a-463">允許收件者從隔離許可權放開郵件</span><span class="sxs-lookup"><span data-stu-id="7f50a-463">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="7f50a-464">[ **允許收件者從隔離許可權發行郵件** ] (_PermissionToRelease_) 控制使用者在不核准系統管理員的情況下，直接釋放隔離郵件的能力。</span><span class="sxs-lookup"><span data-stu-id="7f50a-464">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="7f50a-465">**隔離的郵件詳細資料**：</span><span class="sxs-lookup"><span data-stu-id="7f50a-465">**Quarantined message details**:</span></span>
  - <span data-ttu-id="7f50a-466">已啟用許可權：「 **發行訊息** 」按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="7f50a-466">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="7f50a-467">已停用許可權：無法使用「 **發行訊息** 」按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f50a-467">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="7f50a-468">**使用者垃圾郵件通知**：</span><span class="sxs-lookup"><span data-stu-id="7f50a-468">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="7f50a-469">已啟用許可權：「 **發行** 」按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="7f50a-469">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="7f50a-470">已停用許可權：無法使用「 **發行** 」按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f50a-470">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="7f50a-471">允許收件者要求從隔離許可權發行郵件</span><span class="sxs-lookup"><span data-stu-id="7f50a-471">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="7f50a-472">[ **允許收件者要求從隔離許可權發行郵件** ] (_PermissionToRequestRelease_) 控制使用者 _要求_ 發行隔離郵件的能力。</span><span class="sxs-lookup"><span data-stu-id="7f50a-472">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="7f50a-473">只有在系統管理員核准要求之後，才會發佈郵件。</span><span class="sxs-lookup"><span data-stu-id="7f50a-473">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="7f50a-474">**隔離的郵件詳細資料**：</span><span class="sxs-lookup"><span data-stu-id="7f50a-474">**Quarantined message details**:</span></span>
  - <span data-ttu-id="7f50a-475">已啟用許可權： [ **要求版本** ] 按鈕可用。</span><span class="sxs-lookup"><span data-stu-id="7f50a-475">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="7f50a-476">已停用許可權： [ **要求版本** ] 按鈕無法使用。</span><span class="sxs-lookup"><span data-stu-id="7f50a-476">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="7f50a-477">**使用者垃圾郵件通知**：無法使用「 **發行** 」按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f50a-477">**End-user spam notifications**: The **Release** button is not available.</span></span>
