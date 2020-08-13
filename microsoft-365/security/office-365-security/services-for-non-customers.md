---
title: 將郵件傳送至 Microsoft 365 的非客戶服務
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: 為了協助維護使用者對電子郵件使用的信任，Microsoft 將各種原則和技術放在一起，以協助保護我們的使用者。
ms.openlocfilehash: 74389d3b975a0ffaebdc1619be40fd3ac74d72f4
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652654"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="dd1c1-103">將郵件傳送至 Microsoft 365 的非客戶服務</span><span class="sxs-lookup"><span data-stu-id="dd1c1-103">Services for non-customers sending mail to Microsoft 365</span></span>

<span data-ttu-id="dd1c1-104">電子郵件濫用、垃圾郵件和欺詐電子郵件 (網路釣魚) 會繼續負擔整個電子郵件生態系統。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="dd1c1-105">為了協助維護使用者對電子郵件使用的信任，Microsoft 將各種原則和技術放在適當位置，以協助保護我們的使用者。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="dd1c1-106">不過，Microsoft 知道合法的電子郵件不會受到不良影響。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="dd1c1-107">因此，我們已建立一套服務，以協助寄件者透過主動管理其傳送信譽，以提升電子郵件傳送至 Microsoft 365 使用者的能力。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="dd1c1-108">此概述提供我們為您的組織提供的效益資訊，即使您不是客戶也是如此。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="dd1c1-109">寄件者方案</span><span class="sxs-lookup"><span data-stu-id="dd1c1-109">Sender solutions</span></span>

****

|<span data-ttu-id="dd1c1-110">服務</span><span class="sxs-lookup"><span data-stu-id="dd1c1-110">Service</span></span>|<span data-ttu-id="dd1c1-111">效益</span><span class="sxs-lookup"><span data-stu-id="dd1c1-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="dd1c1-112">這個線上說明內容</span><span class="sxs-lookup"><span data-stu-id="dd1c1-112">This online help content</span></span>|<span data-ttu-id="dd1c1-113">提供：</span><span class="sxs-lookup"><span data-stu-id="dd1c1-113">Provides:</span></span> <br/> <span data-ttu-id="dd1c1-114">與提供與 EOP 使用者通訊相關之任何問題的起點。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-114">A starting point for any questions related to delivering communications to EOP users.</span></span> <br/><br/> <span data-ttu-id="dd1c1-115">包含與我們的原則及需求有關的簡易線上指南。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-115">Includes a simple online guide with our policies and requirements.</span></span> <br/><br/> <span data-ttu-id="dd1c1-116">Microsoft 所採用的垃圾郵件篩選器和驗證技術的概述。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span>|
|[<span data-ttu-id="dd1c1-117">Microsoft 支援</span><span class="sxs-lookup"><span data-stu-id="dd1c1-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="dd1c1-118">提供傳送問題的自我協助和上報支援。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="dd1c1-119">Anti-Spam IP 取消列出入口網站</span><span class="sxs-lookup"><span data-stu-id="dd1c1-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="dd1c1-120">用於提交 IP 取消列出要求的工具。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-120">A tool to submit IP delist request.</span></span> <span data-ttu-id="dd1c1-121">在提交此要求之前，寄件者的責任是確保任何來自于問題的 IP 的後續郵件都不會遭到濫用或惡意。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-121">Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="dd1c1-122">來自 Exchange Online 的垃圾郵件的濫用和垃圾郵件報告</span><span class="sxs-lookup"><span data-stu-id="dd1c1-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="dd1c1-123">讓垃圾郵件和其他有害的郵件無法從 Exchange Online 傳送，並打亂網際網路和您的郵件系統。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="dd1c1-124">Microsoft 支援</span><span class="sxs-lookup"><span data-stu-id="dd1c1-124">Microsoft support</span></span>

<span data-ttu-id="dd1c1-125">Microsoft 提供數種支援選項，讓使用者在傳送郵件給 Microsoft 365 收件者時遇到問題。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="dd1c1-126">我們建議您：</span><span class="sxs-lookup"><span data-stu-id="dd1c1-126">We recommend that you:</span></span>

- <span data-ttu-id="dd1c1-127">遵循您收到的任何未傳遞回報中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="dd1c1-128">查看[對傳送至 Office 365 的郵件進行疑難排解](troubleshooting-mail-sent-to-office-365.md)時，最常遇到的問題。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="dd1c1-129">使用[Microsoft 365 取消列出入口網站](https://sender.office.com)提交要求從封鎖的寄件者清單中移除您的 IP 的要求。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="dd1c1-130">閱讀[Microsoft 社區論壇](https://community.office365.com/f/)。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="dd1c1-131">請聯繫您嘗試使用另一種方法傳送電子郵件的客戶，並要求他們聯繫 Microsoft 支援服務，並代表您開啟支援票證。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="dd1c1-132">在某些情況下，由於法律原因，Microsoft 支援必須直接與擁有被封鎖之 IP 空間的寄件者直接通訊。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="dd1c1-133">不過，非客戶通常無法開啟支援票證。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="dd1c1-134">如需 Microsoft 技術支援 Office 365 的詳細資訊，請參閱[support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support)。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-134">For more information about Microsoft Technical support for Office 365, see [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="dd1c1-135">Anti-Spam IP 取消列出入口網站</span><span class="sxs-lookup"><span data-stu-id="dd1c1-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="dd1c1-136">這是自助服務入口網站，您可以用來將自己從 Microsoft 365 封鎖的寄件者清單中移除。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="dd1c1-137">如果您在嘗試將電子郵件傳送給其電子郵件地址是 Microsoft 365 的收件者時收到錯誤訊息，且您不想要，請使用此入口網站。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="dd1c1-138">如需詳細資訊，請參閱[使用取消列入入口網站以將自己從已封鎖寄件者清單中移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="dd1c1-139">來自 Exchange Online 的垃圾郵件的濫用和垃圾郵件報告</span><span class="sxs-lookup"><span data-stu-id="dd1c1-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="dd1c1-140">Microsoft365 是協力廠商使用，以傳送垃圾郵件，違反我們的使用條款和原則。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="dd1c1-141">如果您收到來自 Office 365 的任何垃圾郵件，您可以將這些郵件報告給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="dd1c1-142">如需相關指示，請參閱[將訊息和檔案報告給 Microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="dd1c1-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>
