---
title: 參考原則、作法和指導方針
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: Microsoft 已開發各種原則、程式，並採用數種行業最佳作法，協助保護我們的使用者免受濫用、有害或惡意的電子郵件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f1a71b891829a2c9ea31502342c855db4126a6b5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203600"
---
# <a name="reference-policies-practices-and-guidelines"></a><span data-ttu-id="ffe36-103">參考：原則、實務與指導方針</span><span class="sxs-lookup"><span data-stu-id="ffe36-103">Reference: Policies, practices, and guidelines</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ffe36-104">**適用於**</span><span class="sxs-lookup"><span data-stu-id="ffe36-104">**Applies to**</span></span>
- [<span data-ttu-id="ffe36-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ffe36-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="ffe36-106">適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2</span><span class="sxs-lookup"><span data-stu-id="ffe36-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ffe36-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ffe36-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ffe36-108">Microsoft 致力於協助提供最受信任的使用者在網頁上的體驗。</span><span class="sxs-lookup"><span data-stu-id="ffe36-108">Microsoft is dedicated to helping provide the most trusted user experience on the web.</span></span> <span data-ttu-id="ffe36-109">因此，Microsoft 已開發各種原則、程式，並採用數種行業最佳作法，協助保護我們的使用者免受濫用、有害或惡意的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="ffe36-109">Therefore, Microsoft has developed various policies, procedures, and adopted several industry best practices to help protect our users from abusive, unwanted, or malicious email.</span></span> <span data-ttu-id="ffe36-110">嘗試將電子郵件傳送給使用者的寄件者應確保他們完全瞭解並遵循本文中的指導方針，以協助您進行此工作，並協助避免潛在的傳遞問題。</span><span class="sxs-lookup"><span data-stu-id="ffe36-110">Senders attempting to send email to users should ensure they fully understand and are following the guidance in this article to help in this effort and to help avoid potential delivery issues.</span></span>

<span data-ttu-id="ffe36-111">如果您不遵循這些原則和指導方針，我們的支援小組可能無法協助您。</span><span class="sxs-lookup"><span data-stu-id="ffe36-111">If you are not in compliance with these policies and guidelines, it may not be possible for our support team to assist you.</span></span> <span data-ttu-id="ffe36-112">如果您遵循本文所述的指導方針、作法和原則，而且仍然會根據您傳送的 IP 位址，而遇到傳送問題，請依照下列步驟提交取消列出要求。</span><span class="sxs-lookup"><span data-stu-id="ffe36-112">If you are adhering to the guidelines, practices, and policies presented in this article and are still experiencing delivery issues based on your sending IP address, please follow the steps to submit a delisting request.</span></span> <span data-ttu-id="ffe36-113">如需相關指示，請參閱 [使用取消列出入口網站將您自己從封鎖的寄件者清單中移除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。</span><span class="sxs-lookup"><span data-stu-id="ffe36-113">For instructions, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="general-microsoft-policies"></a><span data-ttu-id="ffe36-114">一般 Microsoft 原則</span><span class="sxs-lookup"><span data-stu-id="ffe36-114">General Microsoft policies</span></span>

<span data-ttu-id="ffe36-115">傳送給 Microsoft 365 使用者的電子郵件，必須遵守所有管理電子郵件傳輸和使用 Microsoft 365 的 Microsoft 原則。</span><span class="sxs-lookup"><span data-stu-id="ffe36-115">Email sent to Microsoft 365 users must comply with all Microsoft policies governing email transmission and use of Microsoft 365.</span></span>

- <span data-ttu-id="ffe36-116">適用于 Microsoft 365 的服務條款;特別是，禁止使用服務來垃圾郵件或散佈惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="ffe36-116">Terms of Services applicable to Microsoft 365; in particular, the prohibition against using the service to spam or distribute malware.</span></span>

- [<span data-ttu-id="ffe36-117">Microsoft 服務合約</span><span class="sxs-lookup"><span data-stu-id="ffe36-117">Microsoft Services Agreement</span></span>](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a><span data-ttu-id="ffe36-118">政府法規</span><span class="sxs-lookup"><span data-stu-id="ffe36-118">Governmental regulations</span></span>

<span data-ttu-id="ffe36-119">傳送給 Microsoft 365 使用者的電子郵件必須遵守所有適用司法轄區中的電子郵件通訊的法律和規定。</span><span class="sxs-lookup"><span data-stu-id="ffe36-119">Email sent to Microsoft 365 users must adhere to all applicable laws and regulations governing email communications in the applicable jurisdiction.</span></span>

- [<span data-ttu-id="ffe36-120">CAN-垃圾郵件法案：商務規範指南</span><span class="sxs-lookup"><span data-stu-id="ffe36-120">CAN-SPAM Act: A Compliance Guide for Business</span></span>](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [<span data-ttu-id="ffe36-121">「移除我的回應和責任：電子郵件行銷人員必須服從「取消訂閱」宣告</span><span class="sxs-lookup"><span data-stu-id="ffe36-121">"Remove Me" Responses and Responsibilities: Email Marketers Must Honor "Unsubscribe" Claims</span></span>](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a><span data-ttu-id="ffe36-122">技術指導方針</span><span class="sxs-lookup"><span data-stu-id="ffe36-122">Technical guidelines</span></span>

<span data-ttu-id="ffe36-123">傳送給 Microsoft 365 的電子郵件應該遵循下列檔中列出的適當建議 (某些連結只會提供英文版) 。</span><span class="sxs-lookup"><span data-stu-id="ffe36-123">Email sent to Microsoft 365 should comply with the applicable recommendations listed in the documents below (some links are only available in English).</span></span>

- [<span data-ttu-id="ffe36-124">RFC 2505： SMTP Mta Anti-Spam 建議</span><span class="sxs-lookup"><span data-stu-id="ffe36-124">RFC 2505: Anti-Spam Recommendations for SMTP MTAs</span></span>](https://www.ietf.org/rfc/rfc2505.txt)

- [<span data-ttu-id="ffe36-125">RFC 2920：命令流水線作業的 SMTP 服務擴充</span><span class="sxs-lookup"><span data-stu-id="ffe36-125">RFC 2920: SMTP Service Extension for Command Pipelining</span></span>](https://www.ietf.org/rfc/rfc2920.txt)

<span data-ttu-id="ffe36-126">此外，連接至 Microsoft 365 的電子郵件伺服器必須符合下列需求：</span><span class="sxs-lookup"><span data-stu-id="ffe36-126">In addition, email servers connecting to Microsoft 365 must adhere to the following requirements:</span></span>

- <span data-ttu-id="ffe36-127">寄件者預計會遵守網際網路電子郵件傳輸的所有技術標準，如網際網路社會的網際網路工程工作力量 (IETF) （包括 RFC 5321、RFC 5322 及其他）所發佈。</span><span class="sxs-lookup"><span data-stu-id="ffe36-127">Sender is expected to comply with all technical standards for the transmission of Internet email, as published by The Internet Society's Internet Engineering Task Force (IETF), including RFC 5321, RFC 5322, and others.</span></span>

- <span data-ttu-id="ffe36-128">在500和599之間的數位 SMTP 錯誤回應碼 (（也稱為永久未傳遞回應或 NDR) ）之後，寄件者不得嘗試將該郵件重新傳輸給該收件者。</span><span class="sxs-lookup"><span data-stu-id="ffe36-128">After given a numeric SMTP error response code between 500 and 599 (also known as a permanent non-delivery response or NDR), the sender must not attempt to retransmit that message to that recipient.</span></span>

- <span data-ttu-id="ffe36-129">在多個未傳遞回應後，寄件者必須停止進一步嘗試將電子郵件傳送給該收件者。</span><span class="sxs-lookup"><span data-stu-id="ffe36-129">After multiple non-delivery responses, the sender must cease further attempts to send email to that recipient.</span></span>

- <span data-ttu-id="ffe36-130">郵件不得透過不安全的電子郵件轉送或 proxy 伺服器來傳送。</span><span class="sxs-lookup"><span data-stu-id="ffe36-130">Messages must not be transmitted through insecure email relay or proxy servers.</span></span>

- <span data-ttu-id="ffe36-131">從個別清單或寄件者所主控的所有清單中，退訂的機制，都必須清楚地加以記錄，且可讓收件者輕易找到及使用。</span><span class="sxs-lookup"><span data-stu-id="ffe36-131">The mechanism for unsubscribing, either from individual lists or all lists hosted by the sender, must be clearly documented and easy for recipients to find and use.</span></span>

- <span data-ttu-id="ffe36-132">可能無法接受來自動態 IP 空間的連線。</span><span class="sxs-lookup"><span data-stu-id="ffe36-132">Connections from dynamic IP space may not be accepted.</span></span>

- <span data-ttu-id="ffe36-133">電子郵件伺服器必須具有有效的反向 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="ffe36-133">Email servers must have valid reverse DNS records.</span></span>

## <a name="reputation-management"></a><span data-ttu-id="ffe36-134">信譽管理</span><span class="sxs-lookup"><span data-stu-id="ffe36-134">Reputation management</span></span>

<span data-ttu-id="ffe36-135">寄件者、ISP 及其他服務提供者應該主動管理輸出 IP 位址的信譽。</span><span class="sxs-lookup"><span data-stu-id="ffe36-135">Senders, ISP's, and other service providers should actively manage the reputation of your outbound IP addresses.</span></span>

## <a name="microsoft-365-limits"></a><span data-ttu-id="ffe36-136">Microsoft 365 限制</span><span class="sxs-lookup"><span data-stu-id="ffe36-136">Microsoft 365 limits</span></span>

<span data-ttu-id="ffe36-137">寄件者必須遵循[Exchange Online Protection 限制](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)中所列的 Microsoft 365 限制。</span><span class="sxs-lookup"><span data-stu-id="ffe36-137">Senders must adhere to Microsoft 365 limits listed in [Exchange Online Protection Limits](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits).</span></span>

## <a name="email-delivery-resources-and-organizations"></a><span data-ttu-id="ffe36-138">電子郵件傳遞資源和組織</span><span class="sxs-lookup"><span data-stu-id="ffe36-138">Email delivery resources and organizations</span></span>

<span data-ttu-id="ffe36-139">Microsoft 主動與業界主體和服務提供者合作，以改善網際網路和電子郵件生態系統。</span><span class="sxs-lookup"><span data-stu-id="ffe36-139">Microsoft actively works with industry bodies and service providers in order to improve the internet and email ecosystem.</span></span> <span data-ttu-id="ffe36-140">這些組織已發佈最佳作法檔，我們支援並建議寄件者遵循。</span><span class="sxs-lookup"><span data-stu-id="ffe36-140">These organizations have published best practice documents that we support and recommend senders adhere to.</span></span> <span data-ttu-id="ffe36-141">這會提升您在世界各地的幾個電子郵件服務提供者之間傳送電子郵件的能力。</span><span class="sxs-lookup"><span data-stu-id="ffe36-141">This improves your ability to deliver email among several email service providers around the world.</span></span>

- [<span data-ttu-id="ffe36-142">郵件惡意程式碼動裝置的反濫用運作群組</span><span class="sxs-lookup"><span data-stu-id="ffe36-142">Messaging Malware Mobile Anti-Abuse Working Group</span></span>](https://www.m3aawg.org/)

- [<span data-ttu-id="ffe36-143">線上信任同盟</span><span class="sxs-lookup"><span data-stu-id="ffe36-143">Online Trust Alliance</span></span>](https://www.internetsociety.org/ota/)

- [<span data-ttu-id="ffe36-144">電子郵件寄件者 & 提供者聯盟</span><span class="sxs-lookup"><span data-stu-id="ffe36-144">Email Sender & Provider Coalition</span></span>](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a><span data-ttu-id="ffe36-145">濫用和垃圾郵件報告</span><span class="sxs-lookup"><span data-stu-id="ffe36-145">Abuse and spam reporting</span></span>

<span data-ttu-id="ffe36-146">若要報告非法、濫用、有害或惡意的電子郵件，請參閱 [將郵件和檔案報告給 Microsoft](report-junk-email-messages-to-microsoft.md)。</span><span class="sxs-lookup"><span data-stu-id="ffe36-146">To report unlawful, abusive, unwanted or malicious email, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span> <span data-ttu-id="ffe36-147">傳送這些類型的通訊會違反 Microsoft 原則，並對已確認的報告採取適當的動作。</span><span class="sxs-lookup"><span data-stu-id="ffe36-147">Sending these types of communications is a violation of Microsoft policy, and appropriate action will be taken on confirmed reports.</span></span>

## <a name="law-enforcement"></a><span data-ttu-id="ffe36-148">執法</span><span class="sxs-lookup"><span data-stu-id="ffe36-148">Law enforcement</span></span>

<span data-ttu-id="ffe36-149">如果您是法律強制執行的成員，且想要為 microsoft Corporation 提供 Office 365 的法律檔，或是您對於提交給 Microsoft 的法律檔有疑問，請致電 (1)  (425) 722-1299。</span><span class="sxs-lookup"><span data-stu-id="ffe36-149">If you are a member of law enforcement and wish to serve Microsoft Corporation with legal documentation regarding Office 365, or if you have questions regarding legal documentation you have submitted to Microsoft, please call (1) (425) 722-1299.</span></span>