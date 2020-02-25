---
title: 在 Outlook 中將通訊群組清單升級至 Office 365 群組
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: 了解如何將一或多個通訊群組清單升級至 Office 365 群組，在 Outlook 中，及如何使用 PowerShell 來升級多個通訊群組清單同時。
ms.openlocfilehash: 9e6867a5ccdb97586e3d58784a49312e078ae659
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251584"
---
# <a name="upgrade-distribution-lists-to-office-365-groups-in-outlook"></a><span data-ttu-id="d2795-103">在 Outlook 中將通訊群組清單升級至 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d2795-103">Upgrade distribution lists to Office 365 Groups in Outlook</span></span>

<span data-ttu-id="d2795-104">您可以使用 Outlook 的 Office 365 群組升級通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="d2795-104">You can upgrade distribution lists to Office 365 Groups with Outlook.</span></span> <span data-ttu-id="d2795-105">這是很好的方法讓貴組織的通訊群組清單，所有的功能和 Office 365 群組的功能。</span><span class="sxs-lookup"><span data-stu-id="d2795-105">This is a great way to give your organization's distribution lists all the features and functionality of Office 365 groups.</span></span> [<span data-ttu-id="d2795-106">為什麼您應該將 Outlook 中的通訊群組清單升級成群組</span><span class="sxs-lookup"><span data-stu-id="d2795-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.office.com/article/7fb3d880-593b-4909-aafa-950dd50ce188.aspx)

<span data-ttu-id="d2795-107">您可以在一次，或數個同時升級 Dl 一個。</span><span class="sxs-lookup"><span data-stu-id="d2795-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-office-365-groups-in-outlook"></a><span data-ttu-id="d2795-108">一或多個通訊群組清單升級至在 Outlook 中的 Office 365 群組</span><span class="sxs-lookup"><span data-stu-id="d2795-108">Upgrade one or many distribution lists to Office 365 Groups in Outlook</span></span>

<span data-ttu-id="d2795-109">您必須是 Office 365 全域系統管理員或 Exchange 系統管理員，才能升級通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="d2795-109">You must be an Office 365 global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="d2795-110">若要升級至 Office 365 群組，通訊群組必須具有信箱擁有者。</span><span class="sxs-lookup"><span data-stu-id="d2795-110">To upgrade to Office 365 groups, a distribution group must have an owner with a mailbox.</span></span> 

1. <span data-ttu-id="d2795-111">移至 <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 系統管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="d2795-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="d2795-112">在 Exchange 系統管理中心中，前往 [**收件者** \> **群組**。</span><span class="sxs-lookup"><span data-stu-id="d2795-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="d2795-113">您會看到指出您有 （也稱為**通訊群組**） 合格升級至 Office 365 群組的通訊群組清單的通知。</span><span class="sxs-lookup"><span data-stu-id="d2795-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Office 365 groups.</span></span><br/> <span data-ttu-id="d2795-114">![選取要開始使用] 按鈕](../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="d2795-114">![Select the Get started button](../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="d2795-115">選取一或多個通訊群組清單 （也稱為**通訊群組**） 從 [**群組**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="d2795-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="d2795-116">![選取一個通訊群組](../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="d2795-116">![Select a distribution group](../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="d2795-117">選取 [升級] 圖示。</span><span class="sxs-lookup"><span data-stu-id="d2795-117">Select the upgrade icon.</span></span><br/>![升級至 Office 365 群組圖示](../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="d2795-119">在 [資訊] 對話方塊中，選取 **[是]** 以確認升級。</span><span class="sxs-lookup"><span data-stu-id="d2795-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="d2795-120">會立即開始處理程序。</span><span class="sxs-lookup"><span data-stu-id="d2795-120">The process begins immediately.</span></span> <span data-ttu-id="d2795-121">根據大小和數目您正在升級的通訊群組清單中，則過程會需要分鐘或數小時。</span><span class="sxs-lookup"><span data-stu-id="d2795-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="d2795-122">如果通訊群組清單無法升級，對話方塊會隨即出現說這樣。</span><span class="sxs-lookup"><span data-stu-id="d2795-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="d2795-123">請參閱[無法升級通訊群組清單？](#which-distribution-lists-cannot-be-upgraded)。</span><span class="sxs-lookup"><span data-stu-id="d2795-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cannot-be-upgraded).</span></span>

6. <span data-ttu-id="d2795-124">如果您要升級多個通訊群組清單，請使用哪些通訊群組清單均已升級的篩選下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="d2795-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="d2795-125">如果清單不完整，等待長一段時間，然後選取 [以查看哪些已成功升級的 [**重新整理**。</span><span class="sxs-lookup"><span data-stu-id="d2795-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="d2795-126">沒有任何通知，告知您升級程序完成時的所有通訊群組清單您所選取。</span><span class="sxs-lookup"><span data-stu-id="d2795-126">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span></span> <span data-ttu-id="d2795-127">您可以查出這來查看項目會列在**適用於升級**或**升級 Dl**下方。</span><span class="sxs-lookup"><span data-stu-id="d2795-127">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="d2795-128">如果您選取了 DL 升級，但它有仍會顯示在頁面上為適用於升級，然後它無法升級。</span><span class="sxs-lookup"><span data-stu-id="d2795-128">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="d2795-129">請參閱[What to 時，升級作業不會運作](#what-to-do-if-the-upgrade-doesnt-work)。</span><span class="sxs-lookup"><span data-stu-id="d2795-129">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="d2795-130">如果您要取得群組摘要電子郵件，您可能會發現在有時會提供可讓您升級任何合格的通訊群組的底部會列出您的擁有者。</span><span class="sxs-lookup"><span data-stu-id="d2795-130">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span></span> <span data-ttu-id="d2795-131">如需 digest 電子郵件的詳細資訊，請參閱[已在 Outlook 中的群組交談](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d2795-131">See [Have a group conversation in Outlook](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx) for more information about digest emails.</span></span>


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="d2795-132">如果升級無法解決問題，該怎麼辦</span><span class="sxs-lookup"><span data-stu-id="d2795-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="d2795-133">若要升級失敗的通訊群組清單維持不變。</span><span class="sxs-lookup"><span data-stu-id="d2795-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="d2795-134">如果一或多個**合格**的通訊群組清單無法升級，開啟[支援票證](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="d2795-134">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md).</span></span> <span data-ttu-id="d2795-135">此問題： 將需要擴大至群組工程小組他們找出問題。</span><span class="sxs-lookup"><span data-stu-id="d2795-135">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="d2795-136">它是可行的通訊群組清單並未取得升級因服務中斷，但 pretty 互不。</span><span class="sxs-lookup"><span data-stu-id="d2795-136">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely.</span></span> <span data-ttu-id="d2795-137">如果您想，等候一段時間，然後再試一次升級 DL。</span><span class="sxs-lookup"><span data-stu-id="d2795-137">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="d2795-138">如何使用 PowerShell 來升級多個通訊群組清單在同一時間</span><span class="sxs-lookup"><span data-stu-id="d2795-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="d2795-139">如果您曾經在使用 PowerShell，您可能想要前往此路由，而不是使用 UI。</span><span class="sxs-lookup"><span data-stu-id="d2795-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="d2795-140">我們有一組 cmdlet，可協助您升級通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="d2795-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="d2795-141">請參閱以下。</span><span class="sxs-lookup"><span data-stu-id="d2795-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="d2795-142">升級單一 DL</span><span class="sxs-lookup"><span data-stu-id="d2795-142">Upgrade a single DL</span></span>

<span data-ttu-id="d2795-143">若要升級單一 DL 執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d2795-143">To upgrade a single DL run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

<span data-ttu-id="d2795-144">例如，如果您想要升級的 SMTP 地址 dl1@contoso.com Dl，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d2795-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> <span data-ttu-id="d2795-145">您也可以使用[新增 UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet 與 Office 365 群組升級單一通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="d2795-145">You can also upgrade a single distribution list to an Office 365 group using the [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="d2795-146">升級批次中的多個通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="d2795-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="d2795-147">您也可以傳遞為批次的多個通訊群組清單，並在一起升級：</span><span class="sxs-lookup"><span data-stu-id="d2795-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="d2795-148">例如，如果您想要升級使用 SMTP 位址的五個 Dl`dl1@contoso.com`和`dl2@contoso.com`， `dl3@contoso.com`、`dl4@contoso.com`和`dl5@contoso.com`，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d2795-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="d2795-149">升級所有合格的通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="d2795-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="d2795-150">有兩種方式在其中您可以升級所有合格的 Dl。</span><span class="sxs-lookup"><span data-stu-id="d2795-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="d2795-151">升級 DistributionGroup 指令程式不會接收資料管線，因此它所需使用 「 foreach 物件{}"運算子能夠順利執行。</span><span class="sxs-lookup"><span data-stu-id="d2795-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="d2795-152">取得租用戶中的合格的通訊群組清單並進行升級使用升級的命令：</span><span class="sxs-lookup"><span data-stu-id="d2795-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="d2795-153">取得所有通訊群組清單的清單，並升級僅符合資格的通訊群組清單：</span><span class="sxs-lookup"><span data-stu-id="d2795-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-office-365-groups-in-outlook"></a><span data-ttu-id="d2795-154">將通訊群組清單升級至在 Outlook 中的 Office 365 群組相關的常見問題集</span><span class="sxs-lookup"><span data-stu-id="d2795-154">FAQ about upgrading distribution lists to Office 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cannot-be-upgraded"></a><span data-ttu-id="d2795-155">無法升級通訊群組清單？</span><span class="sxs-lookup"><span data-stu-id="d2795-155">Which distribution lists cannot be upgraded?</span></span>

<span data-ttu-id="d2795-156">您只可以升級雲端管理、 簡單、 非巢狀通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="d2795-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="d2795-157">下表列出可升級**CANNOT**的通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="d2795-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="d2795-158">**屬性**</span><span class="sxs-lookup"><span data-stu-id="d2795-158">**Property**</span></span>|<span data-ttu-id="d2795-159">**合格嗎？**</span><span class="sxs-lookup"><span data-stu-id="d2795-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d2795-160">內部部署受管理的通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="d2795-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="d2795-161">否</span><span class="sxs-lookup"><span data-stu-id="d2795-161">No</span></span>  <br/> |
|<span data-ttu-id="d2795-162">巢狀通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="d2795-162">Nested distribution lists.</span></span> <span data-ttu-id="d2795-163">通訊群組清單具有子群組或另一個群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d2795-163">Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="d2795-164">否</span><span class="sxs-lookup"><span data-stu-id="d2795-164">No</span></span>  <br/> |
|<span data-ttu-id="d2795-165">通訊群組清單成員以外的**UserMailbox**、 **SharedMailbox**、 **TeamMailbox**、 **MailUser** **RecipientTypeDetails**</span><span class="sxs-lookup"><span data-stu-id="d2795-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="d2795-166">否</span><span class="sxs-lookup"><span data-stu-id="d2795-166">No</span></span>  <br/> |
|<span data-ttu-id="d2795-167">有 100 個以上的擁有者的通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="d2795-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="d2795-168">否</span><span class="sxs-lookup"><span data-stu-id="d2795-168">No</span></span>  <br/> |
|<span data-ttu-id="d2795-169">通訊群組清單，只有成員，但沒有擁有者</span><span class="sxs-lookup"><span data-stu-id="d2795-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="d2795-170">否</span><span class="sxs-lookup"><span data-stu-id="d2795-170">No</span></span>  <br/> |
|<span data-ttu-id="d2795-171">通訊群組清單具有別名包含特殊字元</span><span class="sxs-lookup"><span data-stu-id="d2795-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="d2795-172">否</span><span class="sxs-lookup"><span data-stu-id="d2795-172">No</span></span>  <br/> |
|<span data-ttu-id="d2795-173">如果通訊群組清單設定為共用信箱轉寄地址</span><span class="sxs-lookup"><span data-stu-id="d2795-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="d2795-174">否</span><span class="sxs-lookup"><span data-stu-id="d2795-174">No</span></span>  <br/> |
|<span data-ttu-id="d2795-175">如果 DL 是另一個 DL 中的**寄件者限制**的一部分。</span><span class="sxs-lookup"><span data-stu-id="d2795-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="d2795-176">否</span><span class="sxs-lookup"><span data-stu-id="d2795-176">No</span></span>  <br/> |
|<span data-ttu-id="d2795-177">安全性群組</span><span class="sxs-lookup"><span data-stu-id="d2795-177">Security groups</span></span>  <br/> |<span data-ttu-id="d2795-178">否</span><span class="sxs-lookup"><span data-stu-id="d2795-178">No</span></span>  <br/> |
|<span data-ttu-id="d2795-179">動態通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="d2795-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="d2795-180">否</span><span class="sxs-lookup"><span data-stu-id="d2795-180">No</span></span>  <br/> |
|<span data-ttu-id="d2795-181">已轉換成**RoomLists**通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="d2795-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="d2795-182">否</span><span class="sxs-lookup"><span data-stu-id="d2795-182">No</span></span>  <br/> |
|<span data-ttu-id="d2795-183">**MemberJoinRestriction**及/或**MemberDepartRestriction**是**已關閉**的通訊群組清單</span><span class="sxs-lookup"><span data-stu-id="d2795-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="d2795-184">否</span><span class="sxs-lookup"><span data-stu-id="d2795-184">No</span></span>  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="d2795-185">如何檢查通訊群組清單是適合升級？</span><span class="sxs-lookup"><span data-stu-id="d2795-185">How do I check which DLs are eligible for upgrade?</span></span>

<span data-ttu-id="d2795-186">如果您想要檢查是否 DL 是否合格，您可以執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d2795-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="d2795-187">如果您想要檢查通訊群組清單是適合進行升級，請直接執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d2795-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="d2795-188">誰可以執行升級的指令碼？</span><span class="sxs-lookup"><span data-stu-id="d2795-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="d2795-189">含 Office 365 全域系統管理員或 Exchange 系統管理員權限的人員。</span><span class="sxs-lookup"><span data-stu-id="d2795-189">People with Office 365 global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="d2795-190">連絡人卡片仍然顯示通訊群組清單的為何？</span><span class="sxs-lookup"><span data-stu-id="d2795-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="d2795-191">我該怎麼辦可防止已升級的通訊群組清單中我自動顯示建議] 清單？</span><span class="sxs-lookup"><span data-stu-id="d2795-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="d2795-192">Outlook： 當有人嘗試在 Outlook 中傳送一封電子郵件移轉後輸入 Office 365 群組名稱時，收件者會解析為通訊群組清單，而不是群組。</span><span class="sxs-lookup"><span data-stu-id="d2795-192">For Outlook: When someone tries to send an email in Outlook by typing the Office 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="d2795-193">收件者的連絡人卡片會是通訊群組清單連絡人卡片。</span><span class="sxs-lookup"><span data-stu-id="d2795-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="d2795-194">這是因為收件者的快取或 nick 名稱快取在 Outlook 中。</span><span class="sxs-lookup"><span data-stu-id="d2795-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="d2795-195">電子郵件會傳送至群組時，成功，但寄件者可能會造成混淆。</span><span class="sxs-lookup"><span data-stu-id="d2795-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="d2795-196">您可以執行本主題中， [Outlook 自動完成清單的相關資訊](https://go.microsoft.com/fwlink/?LinkID=798736)來重設會修正此問題的快取中的步驟。</span><span class="sxs-lookup"><span data-stu-id="d2795-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](https://go.microsoft.com/fwlink/?LinkID=798736) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="d2795-197">在 web 上的 outlook： 時網頁型 Outlook，通訊群組清單的收件者仍會保留在快取。</span><span class="sxs-lookup"><span data-stu-id="d2795-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="d2795-198">您可以遵循[建議的名稱或電子郵件地址從自動完成清單中移除](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx)重新整理快取，查看 [連絡人卡片] 群組中的步驟。</span><span class="sxs-lookup"><span data-stu-id="d2795-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="d2795-199">新的群組成員可以取得的歡迎使用電子郵件收件匣？</span><span class="sxs-lookup"><span data-stu-id="d2795-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="d2795-200">否。</span><span class="sxs-lookup"><span data-stu-id="d2795-200">No.</span></span> <span data-ttu-id="d2795-201">根據預設啟用的歡迎訊息] 設定設為 false。</span><span class="sxs-lookup"><span data-stu-id="d2795-201">The setting to enable welcome messages is set to false by default.</span></span> <span data-ttu-id="d2795-202">此設定會影響移轉完成後可能會加入的現有和新群組成員。</span><span class="sxs-lookup"><span data-stu-id="d2795-202">This setting affects both existing and new group members who may join after the migration is complete.</span></span> <span data-ttu-id="d2795-203">如果群組擁有者稍後允許來賓使用者，來賓使用者不會在其收件匣中收到的歡迎使用電子郵件。</span><span class="sxs-lookup"><span data-stu-id="d2795-203">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span></span> <span data-ttu-id="d2795-204">來賓成員可以繼續使用該群組。</span><span class="sxs-lookup"><span data-stu-id="d2795-204">Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="d2795-205">如果一或 Dl 部分不會升級？</span><span class="sxs-lookup"><span data-stu-id="d2795-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="d2795-206">雖然 DL 符合資格，但無法升級，有某些情況下，在其中。</span><span class="sxs-lookup"><span data-stu-id="d2795-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="d2795-207">DL 不會取得升級，但仍會保留為 DL。</span><span class="sxs-lookup"><span data-stu-id="d2795-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="d2795-208">系統管理員已套用**群組電子郵件地址原則**的組織中的群組，以及它們嘗試升級不會滿足準則的 Dl DL 無法升級</span><span class="sxs-lookup"><span data-stu-id="d2795-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="d2795-209">Dl **MemberJoinRestriction**或**MemberDepartRestriction**設為**已關閉**，無法升級</span><span class="sxs-lookup"><span data-stu-id="d2795-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="d2795-210">會發生什麼情況 DL 從 EAC 升級失敗時？</span><span class="sxs-lookup"><span data-stu-id="d2795-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="d2795-211">只有當通話送至伺服器時，會發生升級。</span><span class="sxs-lookup"><span data-stu-id="d2795-211">The upgrade will happen only when the call is submitted to the server.</span></span> <span data-ttu-id="d2795-212">如果升級失敗時，將 Dl 會保持不變。</span><span class="sxs-lookup"><span data-stu-id="d2795-212">If the upgrade fails, your DLs will be intact.</span></span> <span data-ttu-id="d2795-213">它們 like 他們用來運作。</span><span class="sxs-lookup"><span data-stu-id="d2795-213">They will work like they used to.</span></span>


