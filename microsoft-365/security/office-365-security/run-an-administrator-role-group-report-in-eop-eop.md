---
title: '執行 EOP 中的系統管理員角色群組報告 '
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: 系統管理員可以了解如何執行系統管理員角色群組報表中 Exchange Online Protection (EOP)。 此報表記錄時為系統管理員成員可以從新增或移除成員系統管理員角色群組，Microsoft Exchange Online Protection (EOP) 會記錄每個項目。
ms.openlocfilehash: 59557f6fab2281cd36569b40afcf3e0225bd9347
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441400"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="0b5ec-104">執行 EOP 中的系統管理員角色群組報告</span><span class="sxs-lookup"><span data-stu-id="0b5ec-104">Run an administrator role group report in EOP</span></span>

 <span data-ttu-id="0b5ec-105">當系統管理員成員可以從新增或移除成員系統管理員角色群組，Exchange Online Protection (EOP) 會記錄每個項目。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-105">When an admin adds members to or removes members from administrator role groups, Exchange Online Protection (EOP) logs each occurrence.</span></span> <span data-ttu-id="0b5ec-106">當您執行系統管理員角色群組報表在 Exchange 系統管理中心 (EAC) 中時，項目顯示為搜尋結果，並包含已變更的角色群組成員資格角色群組會受到影響，與時機，以及進行哪些成員資格更新。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-106">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="0b5ec-107">使用此報告可監視指派給組織使用者的系統管理權限變更。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-107">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0b5ec-108">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="0b5ec-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0b5ec-109">預估完成時間：2 分鐘</span><span class="sxs-lookup"><span data-stu-id="0b5ec-109">Estimated time to complete: 2 minutes</span></span>

- <span data-ttu-id="0b5ec-110">若要開啟 Exchange 系統管理中心，請參閱[Exchange 系統管理中心在 Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-110">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="0b5ec-p103">您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)主題的「報告」一節。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="0b5ec-113">適用於此主題中程序的鍵盤快速鍵相關資訊，請參閱[Exchange 系統管理員的鍵盤快速鍵置在 Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-113">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="0b5ec-114">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="0b5ec-114">Having problems?</span></span> <span data-ttu-id="0b5ec-115">要求在[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)論壇中的協助。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-115">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="0b5ec-116">使用 EAC 執行系統管理員角色群組報告</span><span class="sxs-lookup"><span data-stu-id="0b5ec-116">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="0b5ec-117">執行系統管理員角色群組報表，以尋找特定的時間範圍內您組織中的管理角色群組所做的變更。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-117">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="0b5ec-118">在 EAC 中，瀏覽至 **[相符性管理]** \> **[稽核]**，然後選擇 **[執行系統管理員角色群組報告]**。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-118">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="0b5ec-p105">選擇 **[開始日期]** 和 **[結束日期]**。依預設，報告會搜尋過去兩週以來對系統管理員角色群組所做的變更。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-p105">Choose the **Start date** and **End date**. By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

3. <span data-ttu-id="0b5ec-p106">若要檢視特定角色群組的變更，請按一下 **[選取角色群組]**。在後續的對話方塊中選取一或多個角色群組，然後按一下 **[確定]**。您也可以將欄位留白，以尋找所有變更的角色群組。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-p106">To view the changes for a specific role group, click **Select role groups**. Select the role group (or groups) in the subsequent dialog box, and click **OK**. You can also leave the field blank to find all changed role groups.</span></span>

4. <span data-ttu-id="0b5ec-124">Click **Search**.</span><span class="sxs-lookup"><span data-stu-id="0b5ec-124">Click **Search**.</span></span>

<span data-ttu-id="0b5ec-p107">如果使用您指定的準則找到任何變更，它們會出現在結果窗格中。按一下搜尋結果中的角色群組，即可在詳細資料窗格中查看變更。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-p107">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="0b5ec-127">如何知道這是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="0b5ec-127">How do you know this worked?</span></span>

<span data-ttu-id="0b5ec-p108">如果您已經成功執行系統管理員角色群組報告，已在日期範圍內變更的角色群組會顯示在搜尋結果窗格中。如果沒有任何結果，則表示在指定的日期範圍內，沒有對角色群組進行任何變更。如果您認為應該有結果，請變更日期範圍，然後重新執行報告。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-p108">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="0b5ec-131">監視角色群組成員資格的變更</span><span class="sxs-lookup"><span data-stu-id="0b5ec-131">Monitor changes to role group membership</span></span>

<span data-ttu-id="0b5ec-p109">在角色群組中新增或移除成員時，搜尋結果會顯示在詳細資料窗格中，指出角色群組成員資格已經更新，並列出目前的成員。結果不會明確表示已新增或移除哪一位使用者。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-p109">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="0b5ec-p110">若要判斷是否已新增或移除某位使用者，您必須比較報告中的兩個個別項目。例如，以下是 **HelpDesk** 角色群組的記錄項目：</span><span class="sxs-lookup"><span data-stu-id="0b5ec-p110">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="0b5ec-136">2018/1/27 下午 4:43</span><span class="sxs-lookup"><span data-stu-id="0b5ec-136">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="0b5ec-137">系統管理員</span><span class="sxs-lookup"><span data-stu-id="0b5ec-137">Administrator</span></span> <br> <span data-ttu-id="0b5ec-138">Updated members:Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="0b5ec-138">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="0b5ec-139">2018/2/06 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="0b5ec-139">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="0b5ec-140">系統管理員</span><span class="sxs-lookup"><span data-stu-id="0b5ec-140">Administrator</span></span> <br> <span data-ttu-id="0b5ec-141">Updated members:Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="0b5ec-141">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="0b5ec-142">2018/2/19 下午 2:12</span><span class="sxs-lookup"><span data-stu-id="0b5ec-142">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="0b5ec-143">系統管理員</span><span class="sxs-lookup"><span data-stu-id="0b5ec-143">Administrator</span></span> <br> <span data-ttu-id="0b5ec-144">Updated members:Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="0b5ec-144">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="0b5ec-145">在此範例中，系統管理員使用者帳戶做了以下變更：</span><span class="sxs-lookup"><span data-stu-id="0b5ec-145">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="0b5ec-146">2/06/2018/，它們會新增使用者 tonip。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-146">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="0b5ec-147">2/19/2018/，他們可以移除使用者 pilarp。</span><span class="sxs-lookup"><span data-stu-id="0b5ec-147">On 2/19/2018, they removed the user pilarp.</span></span>
