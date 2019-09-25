---
title: 開始使用預設的 DLP 原則
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
description: 在创建第一个数据丢失防护 （DLP） 策略之前，DLP 会使用默认策略帮助保护您的敏感信息。 此默认策略及其建议（如下所示）通过在与组织外部的人员共享包含信用卡号的电子邮件或文档时通知您，帮助您确保敏感内容的安全。
ms.openlocfilehash: 32e5fef1cbfb8fe13928100dbfdae0d620e79762
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076987"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="c8070-104">開始使用預設的 DLP 原則</span><span class="sxs-lookup"><span data-stu-id="c8070-104">Get started with the default DLP policy</span></span>

<span data-ttu-id="c8070-105">在创建第一个数据丢失防护 （DLP） 策略之前，DLP 会使用默认策略帮助保护您的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="c8070-105">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="c8070-106">此默认策略及其建议（如下所示）通过在与组织外部的人员共享包含信用卡号的电子邮件或文档时通知您，帮助您确保敏感内容的安全。</span><span class="sxs-lookup"><span data-stu-id="c8070-106">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="c8070-107">您将在安全&amp;合规性中心的**主页**上看到此建议。</span><span class="sxs-lookup"><span data-stu-id="c8070-107">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="c8070-108">您可以使用此小部件快速查看共享敏感信息的时数和共享量，然后只需单击一两下即可优化默认的 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="c8070-108">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="c8070-109">您还可以随时编辑默认的 DLP 策略，因为它是完全可自定义的。</span><span class="sxs-lookup"><span data-stu-id="c8070-109">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="c8070-110">请注意，如果您最初没有看到建议，请尝试单击"**为您推荐"** 部分底部**的"更多"。**</span><span class="sxs-lookup"><span data-stu-id="c8070-110">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![名为"进一步保护共享内容"的小部件](media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="c8070-112">查看报告并优化默认 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="c8070-112">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="c8070-113">当小部件显示用户已与组织外部人员共享敏感信息时，请选择底部**的"优化 DLP 策略"。**</span><span class="sxs-lookup"><span data-stu-id="c8070-113">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="c8070-114">详细报告显示过去 30 天内共享包含信用卡号的内容时数和共享量。</span><span class="sxs-lookup"><span data-stu-id="c8070-114">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="c8070-115">请注意，规则匹配最多可能需要 48 小时才能显示在小部件中。</span><span class="sxs-lookup"><span data-stu-id="c8070-115">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="c8070-116">为了帮助保护敏感信息，默认 DLP 策略：</span><span class="sxs-lookup"><span data-stu-id="c8070-116">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="c8070-117">检测 Exchange、SharePoint 和 OneDrive 中包含至少一个信用卡号的内容何时与组织外部人员共享。</span><span class="sxs-lookup"><span data-stu-id="c8070-117">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="c8070-118">显示策略提示，并在用户尝试与组织外部人员共享此敏感信息时向用户发送电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="c8070-118">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="c8070-119">有关这些选项的详细信息，请参阅[发送电子邮件通知并显示 DLP 策略的策略提示](use-notifications-and-policy-tips.md)。</span><span class="sxs-lookup"><span data-stu-id="c8070-119">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="c8070-120">生成详细的活动报告，以便跟踪与组织外部的人员共享内容的人员以及他们何时共享内容。</span><span class="sxs-lookup"><span data-stu-id="c8070-120">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="c8070-121">您可以使用[DLP 报告](view-the-dlp-reports.md)和[审核日志数据（](search-the-audit-log-in-security-and-compliance.md)**其中活动** = **DLP）** 来查看此信息。</span><span class="sxs-lookup"><span data-stu-id="c8070-121">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="c8070-122">要快速优化默认 DLP 策略，您可以选择：</span><span class="sxs-lookup"><span data-stu-id="c8070-122">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="c8070-123">当用户与组织外部人员共享此敏感信息时，向您发送事件报告电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c8070-123">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="c8070-124">将其他用户添加到电子邮件事件报告。</span><span class="sxs-lookup"><span data-stu-id="c8070-124">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="c8070-125">阻止对包含敏感信息的内容的访问，但允许用户在需要时重写、共享或发送。</span><span class="sxs-lookup"><span data-stu-id="c8070-125">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="c8070-126">有关事件报告或限制访问的详细信息，请参阅[数据丢失防护策略概述](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c8070-126">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="c8070-127">如果以后要更改这些选项，您可以随时编辑默认的 DLP 策略 - 请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="c8070-127">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![名为"进一步保护共享内容"的小部件设置](media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="c8070-129">编辑默认的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="c8070-129">Edit the default DLP policy</span></span>

<span data-ttu-id="c8070-130">此策略名为**默认 Office 365 DLP 策略，** 并显示在安全&amp;合规性中心**的策略**页面上的**数据丢失防护**下。</span><span class="sxs-lookup"><span data-stu-id="c8070-130">This policy is named **Default Office 365 DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="c8070-131">此策略是完全可自定义的，与您从头开始创建自己的任何 DLP 策略相同。</span><span class="sxs-lookup"><span data-stu-id="c8070-131">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="c8070-132">您还可以关闭或删除策略，以便用户不再收到策略提示或电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="c8070-132">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![名为默认 Office 365 DLP 策略的 DLP 策略](media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="c8070-134">当小部件出现时，并且未显示</span><span class="sxs-lookup"><span data-stu-id="c8070-134">When the widget does and does not appear</span></span>

<span data-ttu-id="c8070-135">名为"**进一步保护共享内容"** 的小部件将显示在&amp;安全合规性中心**主页**的"**推荐"** 部分中。</span><span class="sxs-lookup"><span data-stu-id="c8070-135">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="c8070-136">仅当出现此小部件时，</span><span class="sxs-lookup"><span data-stu-id="c8070-136">This widget appears only when:</span></span>
  
- <span data-ttu-id="c8070-137">安全&amp;合规性中心或 Exchange 管理中心没有数据丢失防护策略。</span><span class="sxs-lookup"><span data-stu-id="c8070-137">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="c8070-138">此小部件旨在帮助您开始使用 DLP，因此，如果您已有 DLP 策略，则不会出现此小部件。</span><span class="sxs-lookup"><span data-stu-id="c8070-138">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="c8070-139">在过去 30 天内，至少包含一张信用卡的内容已与组织外部的人员共享。</span><span class="sxs-lookup"><span data-stu-id="c8070-139">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="c8070-140">请注意，规则匹配最多可能需要 48 小时才能对小部件可用，因此在检测到外部共享的敏感信息后，建议最多可能需要两天才能显示。</span><span class="sxs-lookup"><span data-stu-id="c8070-140">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="c8070-141">最后，使用小部件优化默认的 DLP 策略后，小部件将从**主页**中消失。</span><span class="sxs-lookup"><span data-stu-id="c8070-141">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

