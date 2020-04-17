---
title: 在 EOP 中設定預設的反網路釣魚原則
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何使用 Exchange Online 信箱，修改 Office 365 組織之預設反網路釣魚原則中可用的反欺騙設定。
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537530"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a><span data-ttu-id="e7757-103">在 EOP 中設定預設的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e7757-103">Configure the default anti-phishing policy in EOP</span></span>

<span data-ttu-id="e7757-104">Office 365 組織若有 Exchange Online 信箱和獨立 Exchange Online Protection （EOP）組織，但沒有 Exchange Online 信箱的組織有預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e7757-104">Office 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes have a default anti-phishing policy.</span></span> <span data-ttu-id="e7757-105">這個原則包含預設會啟用的有限數量的反欺騙功能。</span><span class="sxs-lookup"><span data-stu-id="e7757-105">This policy contains a limited number of anti-spoofing features that are enabled by default.</span></span> <span data-ttu-id="e7757-106">如需詳細資訊，請參閱[反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="e7757-106">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="e7757-107">具有 Exchange Online 信箱的 Office 365 組織可以在 Office 365 安全性 & 合規性中心或 Exchange Online PowerShell 中修改預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e7757-107">Office 365 organizations with Exchange Online mailboxes can modify the default anti-phishing policy in the Office 365 Security & Compliance Center or in Exchange Online PowerShell.</span></span> <span data-ttu-id="e7757-108">沒有 Exchange Online 信箱的獨立 EOP 組織無法修改其預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e7757-108">Standalone EOP organizations without Exchange Online mailboxes can't modify their default anti-phishing policy.</span></span>

<span data-ttu-id="e7757-109">如需建立及修改 Office 365 Advanced 威脅防護中可用的更高級 ATP 反網路釣魚原則的詳細資訊，請參閱[在 office 365 中設定 ATP 反網路釣魚原則](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e7757-109">For information about creating and modifying the more advanced ATP anti-phishing policies that are available in Office 365 Advanced Threat Protection, see [Configure ATP anti-phishing policies in Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e7757-110">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="e7757-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e7757-111">您要在 <https://protection.office.com/> 開啟安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="e7757-111">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e7757-112">若要直接移至 [**反網路釣魚**] 頁面<https://protection.office.com/antiphishing>，請使用。</span><span class="sxs-lookup"><span data-stu-id="e7757-112">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="e7757-113">若要連線至 Exchange Online PowerShell，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e7757-113">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e7757-114">您必須已獲指派權限，才能執行這些程序。</span><span class="sxs-lookup"><span data-stu-id="e7757-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="e7757-115">若要新增、修改和刪除反網路釣魚原則，您必須是「**組織管理**」或「**安全性管理員**」角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e7757-115">To add, modify, and delete anti-phishing policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="e7757-116">若要獲得反網路釣魚原則的唯讀存取權，您必須是**Security Reader**角色群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e7757-116">For read-only access to anti-phishing policies, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="e7757-117">如需有關安全性與合規性中心中角色群組的詳細資訊，請參閱 [Office 365 安全性與合規性中心裡的權限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e7757-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="e7757-118">如需針對預設反網路釣魚原則的建議設定，請參閱[EOP 預設的反網路釣魚原則設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="e7757-118">For our recommended settings for the default anti-phishing policy, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

- <span data-ttu-id="e7757-119">允許套用更新的原則最多30分鐘。</span><span class="sxs-lookup"><span data-stu-id="e7757-119">Allow up to 30 minutes for the updated policy to be applied.</span></span>

- <span data-ttu-id="e7757-120">如需在篩選管線中套用反網路釣魚原則的相關資訊，請參閱[Office 365 中的電子郵件保護順序和優先順序](how-policies-and-protections-are-combined.md)。</span><span class="sxs-lookup"><span data-stu-id="e7757-120">For information about where anti-phishing policies are applied in the filtering pipeline, see [Order and precedence of email protection in Office 365](how-policies-and-protections-are-combined.md).</span></span>

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a><span data-ttu-id="e7757-121">使用安全性 & 合規性中心來修改預設的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e7757-121">Use the Security & Compliance Center to modify the default anti-phishing policy</span></span>

<span data-ttu-id="e7757-122">預設的反網路釣魚原則命名為 Office365 AntiPhish 預設值，且不會顯示在原則清單中。</span><span class="sxs-lookup"><span data-stu-id="e7757-122">The default anti-phishing policy is named Office365 AntiPhish Default, and it doesn't appear in the list of policies.</span></span> <span data-ttu-id="e7757-123">若要修改預設的反網路釣魚原則，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e7757-123">To modify the default anti-phishing policy, do the following steps:</span></span>

1. <span data-ttu-id="e7757-124">在安全性 & 規範中心內，移至**威脅管理** \> **原則** \> **反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="e7757-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing**.</span></span>

2. <span data-ttu-id="e7757-125">在 [**反網路釣魚**] 頁面上，按一下 [**預設原則**]。</span><span class="sxs-lookup"><span data-stu-id="e7757-125">On the **Anti-phishing** page, click **Default policy**.</span></span>

3. <span data-ttu-id="e7757-126">隨即會顯示 [**編輯您的原則 Office365 AntiPhish 預設**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e7757-126">The **Edit your policy Office365 AntiPhish Default** page appears.</span></span> <span data-ttu-id="e7757-127">在 [**哄騙**] 區段中，按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e7757-127">In the **Spoof** section, click **Edit**.</span></span>

   <span data-ttu-id="e7757-128">請注意，這些設定與 ATP 反網路釣魚原則中提供的欺騙設定相同。</span><span class="sxs-lookup"><span data-stu-id="e7757-128">Note that these settings are identical to the spoof settings that are available in ATP anti-phishing policies.</span></span>

   - <span data-ttu-id="e7757-129">**哄騙篩選設定**：預設值為 [**開啟**]，建議您將其保持開啟。</span><span class="sxs-lookup"><span data-stu-id="e7757-129">**Spoofing filter settings**: The default value is **On**, and we recommend that you leave it on.</span></span> <span data-ttu-id="e7757-130">若要將它關閉，請將開關滑動至 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e7757-130">To turn it off, slide the toggle to **Off**.</span></span> <span data-ttu-id="e7757-131">如需詳細資訊，請參閱[Configure 哄騙情報 In Office 365](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="e7757-131">For more information, see [Configure spoof intelligence in Office 365](learn-about-spoof-intelligence.md).</span></span>

     > [!NOTE]
     > <span data-ttu-id="e7757-132">如果您的 MX 記錄未指向 Office 365，您不需要停用反欺騙保護;請改為啟用連接器的增強篩選。</span><span class="sxs-lookup"><span data-stu-id="e7757-132">You don't need to disable anti-spoofing protection if your MX record doesn't point to Office 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="e7757-133">如需相關指示，請參閱[在 Exchange Online 中的連接器增強型篩選](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="e7757-133">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

   - <span data-ttu-id="e7757-134">**啟用未經驗證的寄件者功能**：如果郵件失敗電子郵件驗證檢查，則會在寄件者的相片中加入一個問號。</span><span class="sxs-lookup"><span data-stu-id="e7757-134">**Enable Unauthenticated Sender feature**: Adds a question mark to the sender's photo if the message fails email authentication checks.</span></span> <span data-ttu-id="e7757-135">如需詳細資訊，請參閱[反網路釣魚原則中的欺騙設定](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="e7757-135">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span> <span data-ttu-id="e7757-136">預設值為 [開啟]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e7757-136">The default value is **On**.</span></span> <span data-ttu-id="e7757-137">若要將它關閉，請將開關滑動至 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e7757-137">To turn it off, slide the toggle to **Off**.</span></span>

   - <span data-ttu-id="e7757-138">**動作**：指定對哄騙智慧失敗的郵件採取的動作：</span><span class="sxs-lookup"><span data-stu-id="e7757-138">**Actions**: Specify the action to take on messages that fail spoof intelligence:</span></span>

     <span data-ttu-id="e7757-139">**如果電子郵件是由不允許哄騙您網域的人員所傳送**：</span><span class="sxs-lookup"><span data-stu-id="e7757-139">**If email is sent by someone who's not allowed to spoof your domain**:</span></span>

     - <span data-ttu-id="e7757-140">**將郵件移至收件者的 [垃圾郵件] 資料夾**（此為預設值）。</span><span class="sxs-lookup"><span data-stu-id="e7757-140">**Move message to the recipients' Junk Email folders** (This is the default value.)</span></span>
     - <span data-ttu-id="e7757-141">**隔離郵件**</span><span class="sxs-lookup"><span data-stu-id="e7757-141">**Quarantine the message**</span></span>

   - <span data-ttu-id="e7757-142">請**複查您的設定**：設定會顯示在摘要中，而不是按一下每個個別步驟。</span><span class="sxs-lookup"><span data-stu-id="e7757-142">**Review your settings**: Instead of clicking on each individual step, the settings are displayed in a summary.</span></span>

     - <span data-ttu-id="e7757-143">您可以按一下每個區段中的 [**編輯**]，以跳回到相關頁面。</span><span class="sxs-lookup"><span data-stu-id="e7757-143">You can click **Edit** in each section to jump back to the relevant page.</span></span>
     - <span data-ttu-id="e7757-144">您可以在此頁面**上\*\*\*\*直接切換**下列設定：</span><span class="sxs-lookup"><span data-stu-id="e7757-144">You can toggle the following settings **On** or **Off** directly on this page:</span></span>

       - <span data-ttu-id="e7757-145">**啟用 antispoofing 保護**</span><span class="sxs-lookup"><span data-stu-id="e7757-145">**Enable antispoofing protection**</span></span>
       - <span data-ttu-id="e7757-146">**啟用未經驗證的寄件者功能**</span><span class="sxs-lookup"><span data-stu-id="e7757-146">**Enable Unauthenticated Sender feature**</span></span>

   <span data-ttu-id="e7757-147">完成後，按一下 [**儲存**] 任何頁面。</span><span class="sxs-lookup"><span data-stu-id="e7757-147">When you're finished, click **Save** on any page.</span></span>

4. <span data-ttu-id="e7757-148">回到 [**編輯您的原則] Office365 [AntiPhish 預設**] 頁面上，複查您的設定，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e7757-148">Back on the **Edit your policy Office365 AntiPhish Default** page, review your settings and then click **Close**.</span></span>

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a><span data-ttu-id="e7757-149">使用安全性 & 合規性中心來查看預設的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e7757-149">Use the Security & Compliance Center to view the default anti-phishing policy</span></span>

1. <span data-ttu-id="e7757-150">在安全性 & 規範中心，然後移至**威脅管理** \> **原則** \> **ATP 反網路釣魚**。</span><span class="sxs-lookup"><span data-stu-id="e7757-150">In the Security & Compliance Center, and go to **Threat management** \> **Policy** \> **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="e7757-151">按一下 [**預設原則**] 以查看預設的反網路釣魚原則。</span><span class="sxs-lookup"><span data-stu-id="e7757-151">Click **Default policy** to view the default anti-phishing policy.</span></span>

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a><span data-ttu-id="e7757-152">使用 Exchange Online PowerShell 設定預設的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e7757-152">Use Exchange Online PowerShell to configure the default anti-phishing policy</span></span>

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a><span data-ttu-id="e7757-153">使用 PowerShell 來查看預設的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e7757-153">Use PowerShell to view the default anti-phish policy</span></span>

<span data-ttu-id="e7757-154">若要查看預設的反網路釣魚原則，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e7757-154">To view the default anti-phish policy, run the following command:</span></span>

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

<span data-ttu-id="e7757-155">如需詳細的語法及參數資訊，請參閱[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="e7757-155">For detailed syntax and parameter information, see [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).</span></span>

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a><span data-ttu-id="e7757-156">使用 PowerShell 修改預設的反網路釣魚原則</span><span class="sxs-lookup"><span data-stu-id="e7757-156">Use PowerShell to modify the default anti-phish policy</span></span>

<span data-ttu-id="e7757-157">若要修改預設的反網路釣魚原則，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="e7757-157">To modify the default anti-phish policy, use the following syntax:</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

<span data-ttu-id="e7757-158">此範例會變更因驗證失敗，且驗證檢查是否有隔離的欺騙性郵件的動作。</span><span class="sxs-lookup"><span data-stu-id="e7757-158">This example changes the action for spoofed messages that fail authentication checks to quarantine.</span></span>

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

<span data-ttu-id="e7757-159">如需詳細的語法及參數資訊，請參閱[Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)。</span><span class="sxs-lookup"><span data-stu-id="e7757-159">For detailed syntax and parameter information, see [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e7757-160">如何知道這些程序是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="e7757-160">How do you know these procedures worked?</span></span>

<span data-ttu-id="e7757-161">若要確認您是否已成功設定預設的反網路釣魚原則，請執行下列任一步驟：</span><span class="sxs-lookup"><span data-stu-id="e7757-161">To verify that you've successfully configured the default anti-phishing policy, do any of the following steps:</span></span>

- <span data-ttu-id="e7757-162">在 [安全性 & 規範中心] 中，移至**威脅管理** \> **原則** \> **反網路釣魚** \>按一下 [**預設原則**]，然後查看快顯視窗中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e7757-162">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

- <span data-ttu-id="e7757-163">在 Exchange Online PowerShell 中，執行下列命令並確認設定：</span><span class="sxs-lookup"><span data-stu-id="e7757-163">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
