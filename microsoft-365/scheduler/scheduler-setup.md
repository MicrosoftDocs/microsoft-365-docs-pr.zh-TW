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
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362543"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="651cb-103">設定 Microsoft 365 Scheduler</span><span class="sxs-lookup"><span data-stu-id="651cb-103">Setting up Scheduler for Microsoft 365</span></span>


<span data-ttu-id="651cb-104">若要設定 Microsoft 365 的排程器，請遵循下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="651cb-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

| <span data-ttu-id="651cb-105">我需要什麼？</span><span class="sxs-lookup"><span data-stu-id="651cb-105">What do I need?</span></span> | <span data-ttu-id="651cb-106">描述</span><span class="sxs-lookup"><span data-stu-id="651cb-106">Description</span></span> |
|-------------------|-------------|
|<span data-ttu-id="651cb-107">Cortana 信箱</span><span class="sxs-lookup"><span data-stu-id="651cb-107">Cortana mailbox</span></span> |<span data-ttu-id="651cb-108">租使用者系統管理員必須將信箱設定為「Cortana」信箱 (，也就是 cortana@yourdomain.com) 。</span><span class="sxs-lookup"><span data-stu-id="651cb-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="651cb-109">Exchange Online 信箱</span><span class="sxs-lookup"><span data-stu-id="651cb-109">Exchange Online mailbox</span></span> |<span data-ttu-id="651cb-110">使用者必須要有 Exchange Online 郵件和行事曆</span><span class="sxs-lookup"><span data-stu-id="651cb-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="651cb-111">排程程式授權</span><span class="sxs-lookup"><span data-stu-id="651cb-111">Scheduler license</span></span> |<span data-ttu-id="651cb-112">如需授權及定價資訊，請參閱排程[程式 Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing)。</span><span class="sxs-lookup"><span data-stu-id="651cb-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="651cb-113">建立 Cortana 的信箱</span><span class="sxs-lookup"><span data-stu-id="651cb-113">Create a mailbox for Cortana</span></span>

<span data-ttu-id="651cb-114">您租使用者中的 Exchange 信箱充當租使用者傳送和接收 Cortana 中的電子郵件的 Cortana 信箱。</span><span class="sxs-lookup"><span data-stu-id="651cb-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="651cb-115">所有傳送至 Cortana 的電子郵件會根據您的保留原則，保留在租使用者的 Cortana 信箱中。</span><span class="sxs-lookup"><span data-stu-id="651cb-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="651cb-116">使用 Microsoft 365 系統管理中心建立使用者信箱。</span><span class="sxs-lookup"><span data-stu-id="651cb-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="651cb-117">建議使用30天的保留原則。</span><span class="sxs-lookup"><span data-stu-id="651cb-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="651cb-118">使用您信箱的主要 SMTP 位址中 Cortana 的名稱。</span><span class="sxs-lookup"><span data-stu-id="651cb-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="651cb-119">名稱，例如 "Cortana @yourdomain .com"、"CortanaScheduler@contoso.com" 或 "Cortana。Scheduler@yourdomain.com ' 是建議的。</span><span class="sxs-lookup"><span data-stu-id="651cb-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="651cb-120">將信箱指定為計畫程式助理</span><span class="sxs-lookup"><span data-stu-id="651cb-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="651cb-121">建立 Cortana 排程器的唯一信箱之後，您必須指定要 Microsoft 365 正式的信箱。</span><span class="sxs-lookup"><span data-stu-id="651cb-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="651cb-122">指定 Cortana 排程信箱之後，就可以代表您的使用者排程會議。</span><span class="sxs-lookup"><span data-stu-id="651cb-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="651cb-123">若要指定 Cortana 排程信箱，授權的系統管理員必須執行單行 PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="651cb-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="651cb-124">連線以 Microsoft 365 組織的遠端 PowerShell 執行空間。</span><span class="sxs-lookup"><span data-stu-id="651cb-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>

2. <span data-ttu-id="651cb-125">執行下列 PowerShell 腳本，以指定排程器的信箱：</span><span class="sxs-lookup"><span data-stu-id="651cb-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    <span data-ttu-id="651cb-126">在 Cortana 排程者信箱上執行這個「設定」命令之後，會在信箱上設定新的「PersistedCapability」，以附注此信箱是 "SchedulerAssistant"。</span><span class="sxs-lookup"><span data-stu-id="651cb-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="651cb-127">請遵循下列步驟，將您的組織連接至 PowerShell （如果先前尚未執行此動作）：[連線 Microsoft 365 PowerShell](../enterprise/connect-to-microsoft-365-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="651cb-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="651cb-128">若要找出貴組織中的哪個信箱目前已設定為 Cortana 的排程器助理，請執行 get 函數：</span><span class="sxs-lookup"><span data-stu-id="651cb-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> <span data-ttu-id="651cb-129">最多可能需要兩個小時的時間，讓計畫程式信箱完成完整布建，以設定 SchedulerAssistant 功能。</span><span class="sxs-lookup"><span data-stu-id="651cb-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="651cb-130">Exchange Online 信箱</span><span class="sxs-lookup"><span data-stu-id="651cb-130">Exchange Online mailbox</span></span>
<span data-ttu-id="651cb-131">排程器授權是 Microsoft 365 的附加元件，可讓會議召集人將其會議排程工作委派給其計畫者助理。</span><span class="sxs-lookup"><span data-stu-id="651cb-131">A Scheduler license is an add-on to Microsoft 365, that enables the meeting organizer to delegate their meeting scheduling tasks to their Scheduler assistant.</span></span> <span data-ttu-id="651cb-132">若要讓排程程式正常運作，通常是透過 Microsoft 365 授權，會議召集人需要下列元件：</span><span class="sxs-lookup"><span data-stu-id="651cb-132">For the Scheduler to work, typically through Microsoft 365 license, meeting organizers require the following components:</span></span>

- <span data-ttu-id="651cb-133">指定為排程器助理信箱的信箱</span><span class="sxs-lookup"><span data-stu-id="651cb-133">A mailbox designated as Scheduler assistant mailbox</span></span>
- <span data-ttu-id="651cb-134">排程程式授權</span><span class="sxs-lookup"><span data-stu-id="651cb-134">Scheduler license</span></span>
- <span data-ttu-id="651cb-135">Exchange Online 信箱和行事曆</span><span class="sxs-lookup"><span data-stu-id="651cb-135">Exchange Online mailbox and calendar</span></span>

<span data-ttu-id="651cb-136">會議出席者不需要排程器或 Microsoft 365 授權。</span><span class="sxs-lookup"><span data-stu-id="651cb-136">The meeting attendees do not require Scheduler or Microsoft 365 license.</span></span>

## <a name="scheduler-end-user-license-requirements"></a><span data-ttu-id="651cb-137">排程端使用者授權需求</span><span class="sxs-lookup"><span data-stu-id="651cb-137">Scheduler end-user license requirements</span></span>

<span data-ttu-id="651cb-138">排程程式授權需要下列其中一個授權：</span><span class="sxs-lookup"><span data-stu-id="651cb-138">A Scheduler license requires one of the following licenses:</span></span>

- <span data-ttu-id="651cb-139">Microsoft 365 E3，A3，E5，A5</span><span class="sxs-lookup"><span data-stu-id="651cb-139">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="651cb-140">Business Basic、商務、商務標準、商務進階版</span><span class="sxs-lookup"><span data-stu-id="651cb-140">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="651cb-141">Office 365 E1，A1，E3，A3，E5，A5</span><span class="sxs-lookup"><span data-stu-id="651cb-141">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="651cb-142">商務基本版、商務進階版</span><span class="sxs-lookup"><span data-stu-id="651cb-142">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="651cb-143">Exchange Online方案1或計畫2授權。</span><span class="sxs-lookup"><span data-stu-id="651cb-143">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]

> <span data-ttu-id="651cb-144">Microsoft 365 的排程器可在全球多租使用者環境中取得，僅限英文。</span><span class="sxs-lookup"><span data-stu-id="651cb-144">Scheduler for Microsoft 365 is available in worldwide multi-tenant environments in English only.</span></span> <span data-ttu-id="651cb-145">使用者無法使用 **Microsoft 365 的計畫程式**：</span><span class="sxs-lookup"><span data-stu-id="651cb-145">**Scheduler for Microsoft 365** isn't available to users of:</span></span>

- <span data-ttu-id="651cb-146">中國的世紀運作 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="651cb-146">Microsoft 365 operated by 21Vianet in China</span></span>
- <span data-ttu-id="651cb-147">Microsoft 365 搭配德文 cloud，使用資料受信者德文 Telekom</span><span class="sxs-lookup"><span data-stu-id="651cb-147">Microsoft 365 with German cloud that uses the data trustee German Telekom</span></span>
- <span data-ttu-id="651cb-148">政府雲端包括 GCC、消費者、GCC 高或 DoD</span><span class="sxs-lookup"><span data-stu-id="651cb-148">Government cloud including GCC, Consumer, GCC High, or DoD</span></span>

<span data-ttu-id="651cb-149">當德國的資料位置不在德文 datacenter 中時，排程器不支援德國使用者。</span><span class="sxs-lookup"><span data-stu-id="651cb-149">Scheduler does support users in Germany whose data location is not in the German datacenter.</span></span>
