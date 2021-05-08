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
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286155"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="824b8-103">設定 Microsoft 365 的調度程式</span><span class="sxs-lookup"><span data-stu-id="824b8-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="824b8-104">若要設定 Microsoft 365 的排程器，請遵循下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="824b8-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="824b8-105">**我需要什麼？**</span><span class="sxs-lookup"><span data-stu-id="824b8-105">**What do I need?**</span></span> |<span data-ttu-id="824b8-106">**描述**</span><span class="sxs-lookup"><span data-stu-id="824b8-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="824b8-107">Cortana 信箱</span><span class="sxs-lookup"><span data-stu-id="824b8-107">Cortana mailbox</span></span> |<span data-ttu-id="824b8-108">租使用者系統管理員必須將信箱設定為「Cortana」信箱 (，也就是 cortana@yourdomain.com) 。</span><span class="sxs-lookup"><span data-stu-id="824b8-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="824b8-109">Exchange Online 信箱</span><span class="sxs-lookup"><span data-stu-id="824b8-109">Exchange Online mailbox</span></span> |<span data-ttu-id="824b8-110">使用者必須要有 Exchange Online 郵件和行事曆</span><span class="sxs-lookup"><span data-stu-id="824b8-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="824b8-111">排程程式授權</span><span class="sxs-lookup"><span data-stu-id="824b8-111">Scheduler license</span></span> |<span data-ttu-id="824b8-112">如需授權及定價資訊，請參閱排程[程式 Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)。</span><span class="sxs-lookup"><span data-stu-id="824b8-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="824b8-113">建立 Cortana 的信箱</span><span class="sxs-lookup"><span data-stu-id="824b8-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="824b8-114">您租使用者中的 Exchange 信箱充當您租使用者的 cortana 信箱，用以傳送和接收 Cortana 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="824b8-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="824b8-115">傳送至 Cortana 的所有電子郵件都會根據您的保留原則保留在租使用者的 Cortana 信箱中。</span><span class="sxs-lookup"><span data-stu-id="824b8-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="824b8-116">使用 Microsoft 365 系統管理中心來建立新的信箱。</span><span class="sxs-lookup"><span data-stu-id="824b8-116">Use the Microsoft 365 admin center to create a new mailbox.</span></span> <span data-ttu-id="824b8-117">建議使用30天的保留原則。</span><span class="sxs-lookup"><span data-stu-id="824b8-117">A 30-day retention policy is recommended.</span></span> <span data-ttu-id="824b8-118">在您信箱的主要 SMTP 位址中使用「Cortana 名稱。</span><span class="sxs-lookup"><span data-stu-id="824b8-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="824b8-119">建議使用名稱，例如 "Cortana@yourdomain.com"、"CortanaScheduler@contoso.com" 或 "Cortana.Scheduler@yourdomain.com"。</span><span class="sxs-lookup"><span data-stu-id="824b8-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>
- <span data-ttu-id="824b8-120">請與 Microsoft (scheduler_m365@microsoft.com) 聯繫，以啟用 Cortana 信箱。</span><span class="sxs-lookup"><span data-stu-id="824b8-120">Contact Microsoft (scheduler_m365@microsoft.com) to enable your Cortana mailbox.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="824b8-121">您必須與 Microsoft 聯繫才能將您的 Cortana 信箱設定為透過電子郵件 scheduler_m365@microsoft.com 使用排程器服務。</span><span class="sxs-lookup"><span data-stu-id="824b8-121">You must contact Microsoft to configure your Cortana mailbox to use the Scheduler service by emailing scheduler_m365@microsoft.com.</span></span> <span data-ttu-id="824b8-122">啟用您的 Cortana 信箱可能需要長達兩周。</span><span class="sxs-lookup"><span data-stu-id="824b8-122">Enabling your Cortana mailbox may take up to two weeks.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="824b8-123">Exchange Online 信箱</span><span class="sxs-lookup"><span data-stu-id="824b8-123">Exchange Online mailbox</span></span>
<span data-ttu-id="824b8-124">排程器是 Microsoft 365 的附加元件。</span><span class="sxs-lookup"><span data-stu-id="824b8-124">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="824b8-125">會議召集人必須有 Exchange Online 的信箱和行事曆，排程才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="824b8-125">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="824b8-126">Exchange 需求</span><span class="sxs-lookup"><span data-stu-id="824b8-126">Exchange requirements</span></span>

<span data-ttu-id="824b8-127">除了授權排程之外，您必須具有下列其中一個授權：</span><span class="sxs-lookup"><span data-stu-id="824b8-127">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="824b8-128">Microsoft 365 E3，A3，E5，A5</span><span class="sxs-lookup"><span data-stu-id="824b8-128">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="824b8-129">Business Basic、商務、商務標準、商務進階版</span><span class="sxs-lookup"><span data-stu-id="824b8-129">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="824b8-130">Office 365E1，A1，E3，A3，E5，A5</span><span class="sxs-lookup"><span data-stu-id="824b8-130">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="824b8-131">商務基本版、商務進階版</span><span class="sxs-lookup"><span data-stu-id="824b8-131">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="824b8-132">Exchange Online方案1或計畫2授權。</span><span class="sxs-lookup"><span data-stu-id="824b8-132">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="824b8-133">在中國由世紀運作之 Office 365 的使用者都無法使用 **Microsoft 365** 的排程器。</span><span class="sxs-lookup"><span data-stu-id="824b8-133">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="824b8-134">使用 Telekom 的德語 cloud，Microsoft 365 使用者也無法使用此功能。</span><span class="sxs-lookup"><span data-stu-id="824b8-134">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="824b8-135">德國使用者的資料位置若不在德國資料中心，則適用此工具。</span><span class="sxs-lookup"><span data-stu-id="824b8-135">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="824b8-136">此功能也不支援政府雲端的使用者，包括 GCC、Consumer、GCC High 或 DoD。</span><span class="sxs-lookup"><span data-stu-id="824b8-136">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
