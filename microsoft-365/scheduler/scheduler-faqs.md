---
title: Microsoft 365 FAQs 的調度程式
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Microsoft 365 FAQs 的調度程式
ms.openlocfilehash: 423660785e51a61cbff9fa2849b9466feddfc1c1
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289664"
---
# <a name="scheduler-for-microsoft-365-faqs"></a><span data-ttu-id="49287-103">Microsoft 365 FAQs 的調度程式</span><span class="sxs-lookup"><span data-stu-id="49287-103">Scheduler for Microsoft 365 FAQs</span></span>

<span data-ttu-id="49287-104">**問題：** 排程器與其他 Cortana 功能的整合方式，例如 Windows、*每日簡報電子郵件* 和 *播放我的電子* 郵件 *的 Cortana*？</span><span class="sxs-lookup"><span data-stu-id="49287-104">**Question:** How does Scheduler integrate with other Cortana features, such as *Cortana for Windows*, *Daily Briefing Email*, and *Play My Emails*?</span></span></br>
<span data-ttu-id="49287-105">排程器是來自其他 Cortana 功能的獨立服務。</span><span class="sxs-lookup"><span data-stu-id="49287-105">Scheduler is an independent service from other Cortana features.</span></span> <span data-ttu-id="49287-106">您可以在租使用者層級停用其他 Cortana 功能，也可以使用 cortana@yourdomain.com 電子郵件地址來啟用排程器。</span><span class="sxs-lookup"><span data-stu-id="49287-106">Other Cortana features can be disabled at the tenant level, and Scheduler can still be enabled by using the cortana@yourdomain.com email address.</span></span> <span data-ttu-id="49287-107">目前，使用者只能透過電子郵件與計畫程式互動。</span><span class="sxs-lookup"><span data-stu-id="49287-107">Currently, users can only interact with Scheduler via email.</span></span>

<span data-ttu-id="49287-108">**問題：** 這只會與 Outlook 搭配運作嗎？</span><span class="sxs-lookup"><span data-stu-id="49287-108">**Question:** Does this work only with Outlook?</span></span> <span data-ttu-id="49287-109">其他電子郵件產品是否支援？</span><span class="sxs-lookup"><span data-stu-id="49287-109">Are other email products supported?</span></span></br>
<span data-ttu-id="49287-110">只要您具有除上述三項需求以外的授權，使用者就可以從任何裝置上的任何電子郵件客戶 cortana@yourdomain.com 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="49287-110">As long as you have a license, other than the three requirements above, users can email cortana@yourdomain.com from any email client on any device.</span></span>

<span data-ttu-id="49287-111">**問題：** 連絡人是否可以位於 Outlook 和 GAL 或其他公司對等的個人連絡人清單中？</span><span class="sxs-lookup"><span data-stu-id="49287-111">**Question:** Can contacts be in a personal contact list on Outlook and GAL or other company equivalent?</span></span></br>
<span data-ttu-id="49287-112">會議出席者可以是公司內部或外部電子郵件地址的任何人。</span><span class="sxs-lookup"><span data-stu-id="49287-112">Meeting attendees can be anyone with an email address inside or outside the company.</span></span> <span data-ttu-id="49287-113">不幸的是，排程現在無法透過在 GAL 中查閱的方式，自動將名稱轉譯為電子郵件地址/別名。</span><span class="sxs-lookup"><span data-stu-id="49287-113">Unfortunately, Scheduler cannot automatically translate names to email addresses / alias by looking it up in the GAL today.</span></span>

<span data-ttu-id="49287-114">**問題：** 我可以使用已安裝版本 (內部部署) 版本 Outlook 的計畫程式嗎？</span><span class="sxs-lookup"><span data-stu-id="49287-114">**Question:** Can I use Scheduler with my installed version (on-premises) version of Outlook?</span></span></br>
<span data-ttu-id="49287-115">排程器需要 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="49287-115">Scheduler requires Exchange Online.</span></span> <span data-ttu-id="49287-116">無法與 Exchange Server (部署) 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="49287-116">Does not work with Exchange Server (On-prem).</span></span> <span data-ttu-id="49287-117">可與任何電子郵件用戶端、Outlook 桌面、OWA、iOS、android、gmail 等等一起運作。</span><span class="sxs-lookup"><span data-stu-id="49287-117">Works with any email client, Outlook Desktop, OWA, iOS, android, gmail, and so on.</span></span>

<span data-ttu-id="49287-118">**問題：** 是否 Outlook 必須在背景中開啟？</span><span class="sxs-lookup"><span data-stu-id="49287-118">**Question:** Does Outlook have to be open in the background?</span></span></br>
<span data-ttu-id="49287-119">不需要在背景中開啟 Outlook。</span><span class="sxs-lookup"><span data-stu-id="49287-119">Outlook doesn't need to be open in the background.</span></span> <span data-ttu-id="49287-120">您所需做的只是傳送 Cortana 郵件，並依據它來執行大量的工作。</span><span class="sxs-lookup"><span data-stu-id="49287-120">All you need to do is send Cortana a mail and rely on it to do the bulk of the work.</span></span>

## <a name="frequently-asked-trust-and-privacy-questions"></a><span data-ttu-id="49287-121">常見的信任和隱私權問題</span><span class="sxs-lookup"><span data-stu-id="49287-121">Frequently Asked Trust and Privacy Questions</span></span>

<span data-ttu-id="49287-122">**問題：** 排程程式的運作方式？</span><span class="sxs-lookup"><span data-stu-id="49287-122">**Question:** How does Scheduler work?</span></span></br>
<span data-ttu-id="49287-123">排程器使用排程智慧 (AI) 擴充人工助理。</span><span class="sxs-lookup"><span data-stu-id="49287-123">Scheduler uses Scheduling Intelligence (AI) augmented with human assistants.</span></span> <span data-ttu-id="49287-124">如果 AI 模型產生支援與 Cortana 通訊的自然語言，會議要求會升級至人員進行審閱和完成。</span><span class="sxs-lookup"><span data-stu-id="49287-124">If AI models generate a need for support in the natural language of communication with Cortana, the meeting request escalates to a human for review and completion.</span></span>

<span data-ttu-id="49287-125">**問：** 神秘審閱已上報的要求嗎？</span><span class="sxs-lookup"><span data-stu-id="49287-125">**Question:** Who are the humans that review escalated requests?</span></span> </br>
<span data-ttu-id="49287-126">排程者助理是 Microsoft 供應商的安全性和隱私權保證 (因個人和高度機密資訊而) 認證。</span><span class="sxs-lookup"><span data-stu-id="49287-126">Scheduler assistants are Microsoft Supplier Security and Privacy Assurance (SSPA) certified for personal and highly confidential information.</span></span>

<span data-ttu-id="49287-127">**問題：** SSPA 什麼可以查看？</span><span class="sxs-lookup"><span data-stu-id="49287-127">**Question:** What can SSPA Assistants view?</span></span></br>
<span data-ttu-id="49287-128">排程者和 SSPA 的助理可以查看已寄出至 Cortana 的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="49287-128">Scheduler and the SSPA Assistants can view  the emails that are addressed to Cortana.</span></span> <span data-ttu-id="49287-129">在採用執行緒的電子郵件交換中，只會處理包含 Cortana 電子郵件地址的電子郵件，而不會處理 Cortana 新增之前的執行緒中的先前電子郵件。</span><span class="sxs-lookup"><span data-stu-id="49287-129">In a threaded email exchange, only the emails that include Cortana’s email address will be processed, not the previous emails in the thread before Cortana was added.</span></span>

<span data-ttu-id="49287-130">**問題：** 客戶資料是否會保留在排程器的資料 Flow 中？</span><span class="sxs-lookup"><span data-stu-id="49287-130">**Question:** Is customer data retained in the Scheduler's Data Flow?</span></span> </br>
<span data-ttu-id="49287-131">排程器會儲存租使用者界限內的所有客戶內容，並依照 GDPR 指導方針保留資料，Microsoft 365 信任 & 隱私權原則，以及租使用者電子郵件原則。</span><span class="sxs-lookup"><span data-stu-id="49287-131">Scheduler stores all customer content within the tenant boundaries and retains data in accordance with GDPR guidelines, Microsoft 365 Trust & Privacy policies, and tenant email policies.</span></span>

<span data-ttu-id="49287-132">**問題：** 排程者如何處理內部出席者的空閒/忙碌資料？</span><span class="sxs-lookup"><span data-stu-id="49287-132">**Question:** How does Scheduler process the free/busy data of internal attendees?</span></span> </br>
<span data-ttu-id="49287-133">排程器的「自動化」會使用 *findMeetingTimes* 服務來識別出席者和召集人相互使用的時間。</span><span class="sxs-lookup"><span data-stu-id="49287-133">Scheduler's automation uses the *findMeetingTimes* service to identify times that are mutually available for attendees and the organizer.</span></span> <span data-ttu-id="49287-134">此服務會為其他 Outlook 體驗，例如 Outlook 會議表單中 *建議的時間*。</span><span class="sxs-lookup"><span data-stu-id="49287-134">This service powers other Outlook experiences such as *Suggested Times* in the Outlook meeting form.</span></span> <span data-ttu-id="49287-135">空閒/忙碌出席者資訊不會明確地當作空閒/忙碌的封鎖使用。</span><span class="sxs-lookup"><span data-stu-id="49287-135">Free/busy attendee information is not consumed explicitly as free/busy blocks.</span></span>

<span data-ttu-id="49287-136">**問題：** 排程器 GDPR 是否相容？</span><span class="sxs-lookup"><span data-stu-id="49287-136">**Question:** Is Scheduler GDPR Compliant?</span></span> </br>
<span data-ttu-id="49287-137">是。</span><span class="sxs-lookup"><span data-stu-id="49287-137">Yes.</span></span>

<span data-ttu-id="49287-138">**問題：** 神秘可以存取 Cortana 信箱嗎？</span><span class="sxs-lookup"><span data-stu-id="49287-138">**Question:** Who has access to the Cortana mailbox?</span></span> </br>
<span data-ttu-id="49287-139">排程器處理傳送到租使用者 Cortana 信箱的會議要求和相關聯的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="49287-139">Scheduler processes meeting requests and associated emails that are sent to your tenant’s Cortana mailbox.</span></span> <span data-ttu-id="49287-140">Microsoft 不會對 Cortana 信箱進行任何其他存取，除非在租使用者系統管理員要求的情況中透過密碼箱核准。</span><span class="sxs-lookup"><span data-stu-id="49287-140">Microsoft does not have any other access to the Cortana mailbox except through Lockbox approval at the request of the tenant admin.</span></span>

<span data-ttu-id="49287-141">**問題：** 客戶資料是否用於訓練 AI 模型？</span><span class="sxs-lookup"><span data-stu-id="49287-141">**Question:** Is customer data used for training AI models?</span></span></br>
<span data-ttu-id="49287-142">無 Microsoft 365 的計畫者內容可用於資料訓練集。</span><span class="sxs-lookup"><span data-stu-id="49287-142">No customer content from Scheduler for Microsoft 365 can be used for data training sets.</span></span> <span data-ttu-id="49287-143">所有客戶內容均位於客戶租使用者。</span><span class="sxs-lookup"><span data-stu-id="49287-143">All customer content resides in the customer tenant.</span></span>

<span data-ttu-id="49287-144">**問題：** 排程程式是否會處理加密郵件？</span><span class="sxs-lookup"><span data-stu-id="49287-144">**Question:** Will Scheduler process encrypted mail?</span></span></br>
<span data-ttu-id="49287-145">否，計畫程式工作流程會拒絕加密郵件。</span><span class="sxs-lookup"><span data-stu-id="49287-145">No, encrypted mail will be rejected by the Scheduler workflow.</span></span>
