---
title: 設定 Microsoft 365 的調度程式。
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: 設定 Microsoft 365 的調度程式。
ms.openlocfilehash: ba1e178545001473bf73eea3eb02b5ab1c7bf084
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861476"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="af5c9-103">設定 Microsoft 365 的調度程式</span><span class="sxs-lookup"><span data-stu-id="af5c9-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="af5c9-104">若要設定 Microsoft 365 的排程器，請遵循下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="af5c9-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="af5c9-105">**我需要什麼？**</span><span class="sxs-lookup"><span data-stu-id="af5c9-105">**What do I need?**</span></span> |<span data-ttu-id="af5c9-106">**描述**</span><span class="sxs-lookup"><span data-stu-id="af5c9-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="af5c9-107">Cortana 信箱</span><span class="sxs-lookup"><span data-stu-id="af5c9-107">Cortana mailbox</span></span> |<span data-ttu-id="af5c9-108">租使用者系統管理員必須將信箱設定為「Cortana」信箱 (，也就是 cortana@yourdomain.com) 。</span><span class="sxs-lookup"><span data-stu-id="af5c9-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="af5c9-109">Exchange Online 信箱</span><span class="sxs-lookup"><span data-stu-id="af5c9-109">Exchange Online mailbox</span></span> |<span data-ttu-id="af5c9-110">使用者必須要有 Exchange Online 郵件和行事曆</span><span class="sxs-lookup"><span data-stu-id="af5c9-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="af5c9-111">排程程式授權</span><span class="sxs-lookup"><span data-stu-id="af5c9-111">Scheduler license</span></span> |<span data-ttu-id="af5c9-112">如需授權及定價資訊，請參閱排程[程式 Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)。</span><span class="sxs-lookup"><span data-stu-id="af5c9-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="af5c9-113">建立 Cortana 的信箱</span><span class="sxs-lookup"><span data-stu-id="af5c9-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="af5c9-114">您租使用者中的 Exchange 信箱充當您租使用者的 cortana 信箱，用以傳送和接收 Cortana 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="af5c9-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="af5c9-115">傳送至 Cortana 的所有電子郵件都會根據您的保留原則保留在租使用者的 Cortana 信箱中。</span><span class="sxs-lookup"><span data-stu-id="af5c9-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="af5c9-116">使用 Microsoft 365 系統管理中心建立使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="af5c9-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="af5c9-117">建議使用30天的保留原則。</span><span class="sxs-lookup"><span data-stu-id="af5c9-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="af5c9-118">在您信箱的主要 SMTP 位址中使用「Cortana 名稱。</span><span class="sxs-lookup"><span data-stu-id="af5c9-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="af5c9-119">建議使用名稱，例如 "Cortana@yourdomain.com"、"CortanaScheduler@contoso.com" 或 "Cortana.Scheduler@yourdomain.com"。</span><span class="sxs-lookup"><span data-stu-id="af5c9-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="af5c9-120">將信箱指定為計畫程式助理</span><span class="sxs-lookup"><span data-stu-id="af5c9-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="af5c9-121">建立 Cortana 排程器的唯一信箱之後，您必須指定要 Microsoft 365 正式的信箱。</span><span class="sxs-lookup"><span data-stu-id="af5c9-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="af5c9-122">指定 Cortana 排程器信箱之後，就可以代表您的使用者排程會議。</span><span class="sxs-lookup"><span data-stu-id="af5c9-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="af5c9-123">若要指定 Cortana 排程器信箱，授權的系統管理員必須執行單行 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="af5c9-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="af5c9-124">連線以 Microsoft 365 組織的遠端 PowerShell 執行空間。</span><span class="sxs-lookup"><span data-stu-id="af5c9-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>
2. <span data-ttu-id="af5c9-125">執行下列 PowerShell 腳本，以指定排程器的信箱：</span><span class="sxs-lookup"><span data-stu-id="af5c9-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

<span data-ttu-id="af5c9-126">在 Cortana 排程信箱上執行這個「設定」命令之後，會在信箱上設定新的「PersistedCapability」，以附注此信箱是 "SchedulerAssistant"。</span><span class="sxs-lookup"><span data-stu-id="af5c9-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="af5c9-127">請遵循下列步驟，將您的組織連接至 PowerShell （如果先前尚未執行此動作[）：連線 Microsoft 365 PowerShell-Microsoft 365 企業版 |Microsoft](../enterprise/connect-to-microsoft-365-powershell.md)檔</span><span class="sxs-lookup"><span data-stu-id="af5c9-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell - Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span></span>

<span data-ttu-id="af5c9-128">若要找出貴組織中目前設定為 Cortana 排程器助理的信箱，請執行 get 函數：</span><span class="sxs-lookup"><span data-stu-id="af5c9-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>
 
```powershell

Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}

```

> [!IMPORTANT]
> <span data-ttu-id="af5c9-129">最多可能需要兩個小時的時間，讓計畫程式信箱完成完整布建，以設定 SchedulerAssistant 功能。</span><span class="sxs-lookup"><span data-stu-id="af5c9-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="af5c9-130">Exchange Online 信箱</span><span class="sxs-lookup"><span data-stu-id="af5c9-130">Exchange Online mailbox</span></span>
<span data-ttu-id="af5c9-131">排程器是 Microsoft 365 的附加元件。</span><span class="sxs-lookup"><span data-stu-id="af5c9-131">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="af5c9-132">會議召集人必須有 Exchange Online 的信箱和行事曆，排程才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="af5c9-132">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="af5c9-133">Exchange 需求</span><span class="sxs-lookup"><span data-stu-id="af5c9-133">Exchange requirements</span></span>

<span data-ttu-id="af5c9-134">除了授權排程之外，您必須具有下列其中一個授權：</span><span class="sxs-lookup"><span data-stu-id="af5c9-134">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="af5c9-135">Microsoft 365 E3，A3，E5，A5</span><span class="sxs-lookup"><span data-stu-id="af5c9-135">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="af5c9-136">Business Basic、商務、商務標準、商務進階版</span><span class="sxs-lookup"><span data-stu-id="af5c9-136">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="af5c9-137">Office 365E1，A1，E3，A3，E5，A5</span><span class="sxs-lookup"><span data-stu-id="af5c9-137">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="af5c9-138">商務基本版、商務進階版</span><span class="sxs-lookup"><span data-stu-id="af5c9-138">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="af5c9-139">Exchange Online方案1或計畫2授權。</span><span class="sxs-lookup"><span data-stu-id="af5c9-139">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="af5c9-140">在中國由世紀運作之 Office 365 的使用者都無法使用 **Microsoft 365** 的排程器。</span><span class="sxs-lookup"><span data-stu-id="af5c9-140">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="af5c9-141">使用 Telekom 的德語 cloud，Microsoft 365 使用者也無法使用此功能。</span><span class="sxs-lookup"><span data-stu-id="af5c9-141">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="af5c9-142">德國使用者的資料位置若不在德國資料中心，則適用此工具。</span><span class="sxs-lookup"><span data-stu-id="af5c9-142">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="af5c9-143">此功能也不支援政府雲端的使用者，包括 GCC、Consumer、GCC High 或 DoD。</span><span class="sxs-lookup"><span data-stu-id="af5c9-143">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
