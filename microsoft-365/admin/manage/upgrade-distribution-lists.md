---
title: 將通訊群組清單升級至 Outlook 中的 Microsoft 365 群組
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: 瞭解如何將一或多個通訊群組清單升級至 Outlook 中的 Microsoft 365 群組，以及如何使用 PowerShell 同時升級多個通訊群組清單。
ms.openlocfilehash: ef2d6d87d01d0e4874312026909fdeed9c0a8d43
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860604"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="c9908-103">將通訊群組清單升級至 Outlook 中的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="c9908-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="c9908-104">您可以將通訊群組清單升級至 Outlook 中的 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="c9908-104">You can upgrade distribution lists to Microsoft 365 Groups in Outlook.</span></span> <span data-ttu-id="c9908-105">這是一種極好的方法，可讓貴組織的通訊組列出 Microsoft 365 群組的所有功能和功能。</span><span class="sxs-lookup"><span data-stu-id="c9908-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="c9908-106">為什麼您應該將 Outlook 中的通訊群組清單升級成群組</span><span class="sxs-lookup"><span data-stu-id="c9908-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="c9908-107">您可以一次升級一個 DLs，也可以同時升級多個。</span><span class="sxs-lookup"><span data-stu-id="c9908-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="c9908-108">將一個或多個通訊群組清單群組升級至 Outlook 中的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="c9908-108">Upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="c9908-109">您必須是全域系統管理員或 Exchange 系統管理員，才可升級通訊群組清單群組。</span><span class="sxs-lookup"><span data-stu-id="c9908-109">You must be a global admin or Exchange admin to upgrade a distribution list group.</span></span> <span data-ttu-id="c9908-110">若要升級為 Microsoft 365 群組，通訊群組清單群組必須擁有信箱的擁有者。</span><span class="sxs-lookup"><span data-stu-id="c9908-110">To upgrade to Microsoft 365 Groups, the distribution list group must have an owner with a mailbox.</span></span>

### <a name="use-the-new-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="c9908-111">使用新的 EAC 將一個或多個通訊群組清單群組升級至 Outlook 中的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="c9908-111">Use the new EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="c9908-112">移至新的 [Exchange 系統管理中心](https://admin.exchange.microsoft.com)，並 **流覽至 [** 收件者] \> **群組**。</span><span class="sxs-lookup"><span data-stu-id="c9908-112">Go to the new [Exchange admin center](https://admin.exchange.microsoft.com), and navigate to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="c9908-113">從 [群組] 頁面中，選取要從 [**群組**] 頁面升級至 Microsoft 365 群組的通訊群組清單群組 (也稱為 **通訊群組**) 。</span><span class="sxs-lookup"><span data-stu-id="c9908-113">Select the distribution list group (also called a **distribution group**) that you want to upgrade to Microsoft 365 group from the **Groups** page.</span></span>

3. <span data-ttu-id="c9908-114">從工具列選取 [ **升級通訊群組** ]。</span><span class="sxs-lookup"><span data-stu-id="c9908-114">Select the **Upgrade distribution group** from the tool bar.</span></span>

4. <span data-ttu-id="c9908-115">在對話方塊中 **準備好升級？**，按一下 [ **升級**]。</span><span class="sxs-lookup"><span data-stu-id="c9908-115">In the dialog box **Ready to upgrade?**, click **Upgrade**.</span></span> <span data-ttu-id="c9908-116">會立即開始處理常式。</span><span class="sxs-lookup"><span data-stu-id="c9908-116">The process begins immediately.</span></span> <span data-ttu-id="c9908-117">根據您所升級之通訊群組清單群組的大小和數目，此程式可能需要數分鐘或數小時的時間。</span><span class="sxs-lookup"><span data-stu-id="c9908-117">Depending on the size and number of distribution list groups you're upgrading, the process can take minutes or hours.</span></span>

> [!NOTE]
> <span data-ttu-id="c9908-118">頁首的橫幅表示升級，例如 *通訊群組 () 已升級。需要5分鐘才能反映變更。依 Microsoft 365 群組篩選，以查看已升級的 distrubtion 群組 (s)*。</span><span class="sxs-lookup"><span data-stu-id="c9908-118">A banner at the top indicates the upgrade, for example, *Distribution group(s) has been upgraded. It will take 5 minutes to reflect the changes. Filter by Microsoft 365 groups to see the upgraded distrubtion groups(s)*.</span></span>

### <a name="use-the-classic-eac-to-upgrade-one-or-many-distribution-list-groups-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="c9908-119">使用傳統 EAC 將一個或多個通訊群組清單群組升級至 Outlook 中的 Microsoft 365 群組</span><span class="sxs-lookup"><span data-stu-id="c9908-119">Use the Classic EAC to upgrade one or many distribution list groups to Microsoft 365 Groups in Outlook</span></span>

1. <span data-ttu-id="c9908-120">移至傳統的 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="c9908-120">Go to the Classic <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="c9908-121">在傳統 Exchange 系統管理中心中， **移至 [** 收件者 \> **群組**]。</span><span class="sxs-lookup"><span data-stu-id="c9908-121">In the Classic Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="c9908-122">您會看到一則通知，指出您的通訊群組清單 (也稱為 **通訊群組**) 可升級至 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="c9908-122">You'll see a notice indicating you have distribution lists (also called **distribution groups**) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="c9908-123">![選取 [快速入門] 按鈕](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="c9908-123">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="c9908-124">從 [**群組**] 頁面中，選取一或多個通訊群組清單 (也稱為 **通訊群組**) 。</span><span class="sxs-lookup"><span data-stu-id="c9908-124">Select one or more distribution lists (also called a **distribution group**) from the **groups** page.</span></span><br/><span data-ttu-id="c9908-125">![選取通訊群組](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="c9908-125">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="c9908-126">選取 [升級] 圖示。</span><span class="sxs-lookup"><span data-stu-id="c9908-126">Select the upgrade icon.</span></span><br/>![升級至 Microsoft 365 群組圖示](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="c9908-128">在 [資訊] 對話方塊中，選取 **[是]** 以確認升級。</span><span class="sxs-lookup"><span data-stu-id="c9908-128">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="c9908-129">會立即開始處理常式。</span><span class="sxs-lookup"><span data-stu-id="c9908-129">The process begins immediately.</span></span> <span data-ttu-id="c9908-130">視您所升級的 DLs 大小和數目而定，此程式可能需要數分鐘或數小時的時間。</span><span class="sxs-lookup"><span data-stu-id="c9908-130">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="c9908-131">如果無法升級通訊群組清單，就會顯示一個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="c9908-131">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="c9908-132">查看 [哪些通訊群組清單無法升級？](#which-distribution-lists-cant-be-upgraded)。</span><span class="sxs-lookup"><span data-stu-id="c9908-132">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="c9908-133">如果您要升級多個通訊群組清單，請使用下拉式清單來篩選已升級的通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="c9908-133">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="c9908-134">如果清單尚未完成，請稍候片刻，然後選取 [重新整理 **]，以** 查看已成功升級的功能。</span><span class="sxs-lookup"><span data-stu-id="c9908-134">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="c9908-135">在您選取的所有 DLs 完成升級程式時，並無任何通知。</span><span class="sxs-lookup"><span data-stu-id="c9908-135">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span></span> <span data-ttu-id="c9908-136">您可以查看 [ **可用於升級** 或 **升級的 DLs**] 中所列的專案，以找出此專案。</span><span class="sxs-lookup"><span data-stu-id="c9908-136">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="c9908-137">如果您選取了要升級的 DL，但是它仍會顯示在頁面上，以供升級，則無法升級。</span><span class="sxs-lookup"><span data-stu-id="c9908-137">If you selected a DL for upgrade, but it's still appeared on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="c9908-138">若 [升級無法運作，請查看要執行的](#what-to-do-if-the-upgrade-doesnt-work)動作。</span><span class="sxs-lookup"><span data-stu-id="c9908-138">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="c9908-139">如果您正在取得群組摘要電子郵件，您可能會注意到，它有時候會讓您升級您所擁有的任何合格通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="c9908-139">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span></span> <span data-ttu-id="c9908-140">如需有關摘要電子郵件的詳細資訊，請參閱 [在 Outlook 中擁有群組交談](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) 。</span><span class="sxs-lookup"><span data-stu-id="c9908-140">See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="c9908-141">升級無法運作時應執行的動作</span><span class="sxs-lookup"><span data-stu-id="c9908-141">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="c9908-142">無法升級的通訊群組清單保持不變。</span><span class="sxs-lookup"><span data-stu-id="c9908-142">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="c9908-143">若一或多個 **合格** 的通訊群組清單無法升級，請開啟 [支援票證](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="c9908-143">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md).</span></span> <span data-ttu-id="c9908-144">您必須將問題升級至群組工程小組，以找出問題。</span><span class="sxs-lookup"><span data-stu-id="c9908-144">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="c9908-145">通訊群組清單可能由於服務中斷而無法升級，但不太可能。</span><span class="sxs-lookup"><span data-stu-id="c9908-145">It's possible that the distribution list didn't get upgraded because of a service outage, but unlikely.</span></span> <span data-ttu-id="c9908-146">如有需要，請稍候一段時間，然後嘗試再次升級 DL。</span><span class="sxs-lookup"><span data-stu-id="c9908-146">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="c9908-147">如何使用 PowerShell 同時升級多個通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="c9908-147">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="c9908-148">如果您已使用 PowerShell，您可能想要移至此路由，而不是使用 UI。</span><span class="sxs-lookup"><span data-stu-id="c9908-148">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="c9908-149">我們有一組 Cmdlet 可協助您升級通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="c9908-149">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="c9908-150">請參閱下列。</span><span class="sxs-lookup"><span data-stu-id="c9908-150">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="c9908-151">升級單一 DL</span><span class="sxs-lookup"><span data-stu-id="c9908-151">Upgrade a single DL</span></span>

<span data-ttu-id="c9908-152">若要升級單一 DL，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c9908-152">To upgrade a single DL, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

<span data-ttu-id="c9908-153">例如，如果您想要使用 SMTP 位址 dl1@contoso.com 升級 DLs，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c9908-153">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> <span data-ttu-id="c9908-154">您也可以使用 [set-unifiedgroup](/powershell/module/exchange/new-unifiedgroup) PowerShell Cmdlet，將單一通訊群組清單升級至 Microsoft 365 群組。</span><span class="sxs-lookup"><span data-stu-id="c9908-154">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="c9908-155">在批次中升級多個 DLs</span><span class="sxs-lookup"><span data-stu-id="c9908-155">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="c9908-156">您也可以以批次方式傳遞多個 DLs，並將它們升級到一起：</span><span class="sxs-lookup"><span data-stu-id="c9908-156">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="c9908-157">例如，如果您想要使用 SMTP 位址升級5個 DLs `dl1@contoso.com` ， `dl2@contoso.com` 並 `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` 執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c9908-157">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="c9908-158">升級所有合格的 DLs</span><span class="sxs-lookup"><span data-stu-id="c9908-158">Upgrade all eligible DLs</span></span>

<span data-ttu-id="c9908-159">您可以透過兩種方式升級所有合格的 DLs。</span><span class="sxs-lookup"><span data-stu-id="c9908-159">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="c9908-160">Upgrade-DistributionGroup 指令程式不會從管線接收資料，因此，您必須使用「foreach-object」 {} 運算子才能成功執行。</span><span class="sxs-lookup"><span data-stu-id="c9908-160">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="c9908-161">在租使用者中取得合格的 DLs，並使用升級命令進行升級：</span><span class="sxs-lookup"><span data-stu-id="c9908-161">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="c9908-162">取得所有 DLs 的清單，並只升級合格的 DLs：</span><span class="sxs-lookup"><span data-stu-id="c9908-162">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="c9908-163">將通訊群組清單升級至 Outlook 中 Microsoft 365 群組的常見問題</span><span class="sxs-lookup"><span data-stu-id="c9908-163">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="c9908-164">哪些通訊群組清單無法升級？</span><span class="sxs-lookup"><span data-stu-id="c9908-164">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="c9908-165">您只能升級雲端管理、簡單且不會嵌套的通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="c9908-165">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="c9908-166">下表列出 **無法** 升級的通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="c9908-166">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="c9908-167">**屬性**</span><span class="sxs-lookup"><span data-stu-id="c9908-167">**Property**</span></span>|<span data-ttu-id="c9908-168">**資格？**</span><span class="sxs-lookup"><span data-stu-id="c9908-168">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9908-169">內部部署的受管理通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="c9908-169">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="c9908-170">否</span><span class="sxs-lookup"><span data-stu-id="c9908-170">No</span></span>  <br/> |
|<span data-ttu-id="c9908-171">嵌套的通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="c9908-171">Nested distribution lists.</span></span> <span data-ttu-id="c9908-172">通訊群組清單具有子群組或為另一個群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c9908-172">Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="c9908-173">否</span><span class="sxs-lookup"><span data-stu-id="c9908-173">No</span></span>  <br/> |
|<span data-ttu-id="c9908-174">成員 **RecipientTypeDetails** 不是 **UserMailbox**、 **SharedMailbox**、 **TeamMailbox**、 **MailUser** 的通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="c9908-174">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="c9908-175">否</span><span class="sxs-lookup"><span data-stu-id="c9908-175">No</span></span>  <br/> |
|<span data-ttu-id="c9908-176">擁有超過100個擁有者的通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="c9908-176">Distribution list that has more than 100 owners</span></span>  <br/> |<span data-ttu-id="c9908-177">否</span><span class="sxs-lookup"><span data-stu-id="c9908-177">No</span></span>  <br/> |
|<span data-ttu-id="c9908-178">只具有成員但沒有擁有者的通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="c9908-178">Distribution list that only has members but no owner</span></span>  <br/> |<span data-ttu-id="c9908-179">否</span><span class="sxs-lookup"><span data-stu-id="c9908-179">No</span></span>  <br/> |
|<span data-ttu-id="c9908-180">別名包含特殊字元的通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="c9908-180">Distribution list that has alias containing special characters</span></span>  <br/> |<span data-ttu-id="c9908-181">否</span><span class="sxs-lookup"><span data-stu-id="c9908-181">No</span></span>  <br/> |
|<span data-ttu-id="c9908-182">如果通訊群組清單設定為共用信箱的轉寄位址</span><span class="sxs-lookup"><span data-stu-id="c9908-182">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="c9908-183">否</span><span class="sxs-lookup"><span data-stu-id="c9908-183">No</span></span>  <br/> |
|<span data-ttu-id="c9908-184">如果 DL 是另一個 DL 中的 **寄件者限制** 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c9908-184">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="c9908-185">否</span><span class="sxs-lookup"><span data-stu-id="c9908-185">No</span></span>  <br/> |
|<span data-ttu-id="c9908-186">安全性群組</span><span class="sxs-lookup"><span data-stu-id="c9908-186">Security groups</span></span>  <br/> |<span data-ttu-id="c9908-187">否</span><span class="sxs-lookup"><span data-stu-id="c9908-187">No</span></span>  <br/> |
|<span data-ttu-id="c9908-188">動態通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="c9908-188">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="c9908-189">否</span><span class="sxs-lookup"><span data-stu-id="c9908-189">No</span></span>  <br/> |
|<span data-ttu-id="c9908-190">已轉換為 **RoomLists** 的通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="c9908-190">Distribution lists that were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="c9908-191">否</span><span class="sxs-lookup"><span data-stu-id="c9908-191">No</span></span>  <br/> |
|<span data-ttu-id="c9908-192">**關閉** **MemberJoinRestriction** 和/或 **MemberDepartRestriction** 的通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="c9908-192">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="c9908-193">否</span><span class="sxs-lookup"><span data-stu-id="c9908-193">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="c9908-194">檢查哪些 DLs 有資格升級</span><span class="sxs-lookup"><span data-stu-id="c9908-194">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="c9908-195">如果您想要檢查是否有資格使用 DL，您可以執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c9908-195">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="c9908-196">如果您想要檢查哪些 DLs 可用於升級，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c9908-196">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="c9908-197">誰可以執行升級腳本？</span><span class="sxs-lookup"><span data-stu-id="c9908-197">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="c9908-198">具有全域管理員或 Exchange 系統管理員許可權的人員。</span><span class="sxs-lookup"><span data-stu-id="c9908-198">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-an-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="c9908-199">為什麼連絡人卡片仍顯示通訊群組清單？</span><span class="sxs-lookup"><span data-stu-id="c9908-199">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="c9908-200">若要防止已升級的通訊群組清單顯示在我的自動建議清單中，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="c9908-200">What should I do to prevent an upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="c9908-201">若為 Outlook：當有人嘗試在遷移後輸入 Microsoft 365 群組名稱時，在 Outlook 中嘗試傳送電子郵件時，收件者將會解析為通訊群組清單，而不是群組。</span><span class="sxs-lookup"><span data-stu-id="c9908-201">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="c9908-202">收件者的連絡人卡片將會是通訊群組清單連絡人卡片。</span><span class="sxs-lookup"><span data-stu-id="c9908-202">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="c9908-203">這是因為 Outlook 中的收件者緩存或 nick 名稱快取。</span><span class="sxs-lookup"><span data-stu-id="c9908-203">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="c9908-204">電子郵件會順利傳送至群組，但是可能會造成對寄件者的混淆。</span><span class="sxs-lookup"><span data-stu-id="c9908-204">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="c9908-205">您可以執行本文中的步驟， [[Outlook AutoComplete] 清單中的相關資訊](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) 來重設快取，這會修正此問題。</span><span class="sxs-lookup"><span data-stu-id="c9908-205">You can perform the steps in this article, [Information about the Outlook AutoComplete list](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="c9908-206">針對網頁上的 Outlook：在 Outlook 網頁版中，通訊群組清單收件者仍會保留在快取中。</span><span class="sxs-lookup"><span data-stu-id="c9908-206">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="c9908-207">您可以依照「 [從自動完成」清單中移除建議的名稱或電子郵件地址](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) 中的步驟進行，以重新整理快取，以查看群組連絡人卡片。</span><span class="sxs-lookup"><span data-stu-id="c9908-207">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="c9908-208">新增群組成員是否會在其收件匣中取得歡迎使用的電子郵件？</span><span class="sxs-lookup"><span data-stu-id="c9908-208">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="c9908-209">不對。</span><span class="sxs-lookup"><span data-stu-id="c9908-209">No.</span></span> <span data-ttu-id="c9908-210">預設會將 [啟用歡迎郵件] 設定設為 false。</span><span class="sxs-lookup"><span data-stu-id="c9908-210">The setting to enable welcome messages is set to false by default.</span></span> <span data-ttu-id="c9908-211">此設定會影響在遷移完成後，可能會加入的現有和新群組成員。</span><span class="sxs-lookup"><span data-stu-id="c9908-211">This setting affects both existing and new group members who may join after the migration is complete.</span></span> <span data-ttu-id="c9908-212">如果群組擁有者後來允許來賓使用者，來賓使用者將不會在其收件匣中收到歡迎使用的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="c9908-212">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span></span> <span data-ttu-id="c9908-213">來賓成員可以繼續使用群組。</span><span class="sxs-lookup"><span data-stu-id="c9908-213">Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="c9908-214">如果一或部分 DLs 未升級，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="c9908-214">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="c9908-215">在某些情況下，雖然仍有資格，但無法升級。</span><span class="sxs-lookup"><span data-stu-id="c9908-215">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="c9908-216">DL 不會升級，而且會以 DL 形式保留。</span><span class="sxs-lookup"><span data-stu-id="c9908-216">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="c9908-217">在組織中，系統管理員已套用 **群組的電子郵件地址原則** ，並嘗試升級不符合準則的 DLs，而 DL 則無法升級</span><span class="sxs-lookup"><span data-stu-id="c9908-217">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs that doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="c9908-218">**MemberJoinRestriction** 或 **MemberDepartRestriction** 設定為 [**已關閉**] 的 DLs，無法升級</span><span class="sxs-lookup"><span data-stu-id="c9908-218">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="c9908-219">從 EAC 升級時，DL 會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="c9908-219">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="c9908-220">只有在將通話送出至伺服器時，才會進行升級。</span><span class="sxs-lookup"><span data-stu-id="c9908-220">The upgrade will happen only when the call is submitted to the server.</span></span> <span data-ttu-id="c9908-221">升級失敗時，您的 DLs 會完好無損。</span><span class="sxs-lookup"><span data-stu-id="c9908-221">If the upgrade fails, your DLs will be intact.</span></span> <span data-ttu-id="c9908-222">它們的運作方式與使用的方式相同。</span><span class="sxs-lookup"><span data-stu-id="c9908-222">They will work like they used to.</span></span>
