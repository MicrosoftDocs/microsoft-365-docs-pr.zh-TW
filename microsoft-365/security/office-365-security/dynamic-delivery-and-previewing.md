---
title: 使用 Office 365 ATP 安全附件的動態傳遞和預覽
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: 當您設定 ATP 安全附件原則時，您選擇 [動態傳遞] 來避免郵件延遲，並讓人員預覽正在掃描的附件。
ms.openlocfilehash: 221ae4fa5968723fa790cbfb9c26f0e80a827730
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808328"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a><span data-ttu-id="709f1-103">使用 Office 365 ATP 安全附件的動態傳遞和預覽</span><span class="sxs-lookup"><span data-stu-id="709f1-103">Dynamic Delivery and previewing with Office 365 ATP Safe Attachments</span></span>

## <a name="overview"></a><span data-ttu-id="709f1-104">概觀</span><span class="sxs-lookup"><span data-stu-id="709f1-104">Overview</span></span>

<span data-ttu-id="709f1-105">[動態傳遞] 是一個選項，可以針對 [ATP 安全附件](atp-safe-attachments.md)進行選取。</span><span class="sxs-lookup"><span data-stu-id="709f1-105">Dynamic Delivery is an option that can be selected for [ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="709f1-106">請參閱這篇文章，了解 [Office 365 中的 ATP 安全附件](atp-safe-attachments.md)中的動態傳遞和附件預覽功能。</span><span class="sxs-lookup"><span data-stu-id="709f1-106">Read this article to learn about Dynamic Delivery and attachment preview capabilities in [ATP Safe Attachments in Office 365](atp-safe-attachments.md).</span></span>

<span data-ttu-id="709f1-107">當貴組織[已設定 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)時，對於電子郵件附件的處理方式有數個選項。</span><span class="sxs-lookup"><span data-stu-id="709f1-107">When [ATP Safe Attachments policies are set up](set-up-atp-safe-attachments-policies.md) for your organization, there are several options for how email attachments are handled.</span></span> <span data-ttu-id="709f1-108">其中包括 [封鎖]\*\*\*\*、[取代]\*\*\*\* 以及 [動態傳遞]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="709f1-108">These include **Block**, **Replace**, and **Dynamic Delivery**.</span></span> <span data-ttu-id="709f1-109">視設定的 ATP 安全附件原則而定，電子郵件收件者在其附件進行掃描時，可能會遇到電子郵件傳遞的輕微延遲。</span><span class="sxs-lookup"><span data-stu-id="709f1-109">Depending on how ATP Safe Attachments policies are configured, email recipients might experience a minor delay in email delivery while their attachments are scanned.</span></span> <span data-ttu-id="709f1-110">若要避免郵件延遲，請選擇 [動態傳遞]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="709f1-110">To avoid message delays, choose **Dynamic Delivery**.</span></span>

## <a name="how-dynamic-delivery-works"></a><span data-ttu-id="709f1-111">動態傳遞運作方式</span><span class="sxs-lookup"><span data-stu-id="709f1-111">How Dynamic Delivery works</span></span>

<span data-ttu-id="709f1-112">動態傳遞會將電子郵件訊息的本文傳送給收件者，對於每個電子郵件附件使用預留位置，來避免電子郵件延遲。</span><span class="sxs-lookup"><span data-stu-id="709f1-112">Dynamic Delivery eliminates email delays by sending the body of an email message through to the recipient with a placeholder for each email attachment.</span></span> <span data-ttu-id="709f1-113">系統會保留預留位置直到掃描附件的複本，並且由 [ATP 安全附件](atp-safe-attachments.md)判斷是安全的。</span><span class="sxs-lookup"><span data-stu-id="709f1-113">The placeholder remains until a copy of the attachment is scanned and determined to be safe by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>

- <span data-ttu-id="709f1-114">因為每個附件都是乾淨的，可以開啟或下載。</span><span class="sxs-lookup"><span data-stu-id="709f1-114">As each attachment is cleared, it is available to open or download.</span></span>

- <span data-ttu-id="709f1-115">如果附件被認為是惡意的，則會將它傳送給隔離區，而貴組織安全小組 (例如，Office 365 全域系統管理員或安全性系統管理員) 中的某人可以[管理 Office 365 中的隔離郵件](manage-quarantined-messages-and-files.md)。</span><span class="sxs-lookup"><span data-stu-id="709f1-115">If an attachment is determined to be malicious, it is sent to quarantine, where someone on your organization's security team (such as an Office 365 global administrator or security administrator) can [manage quarantined messages in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="709f1-116">大部分 PDF 和 Office 文件都可以在 ATP 掃描正在進行時，在安全模式中預覽。</span><span class="sxs-lookup"><span data-stu-id="709f1-116">Most PDFs and Office documents can be previewed in safe mode while ATP scanning is underway.</span></span> <span data-ttu-id="709f1-117">如果附件與動態傳遞預覽程式不相容，電子郵件收件者會看見附件預留位置，直到 ATP 安全附件掃描完成為止。</span><span class="sxs-lookup"><span data-stu-id="709f1-117">If an attachment is not compatible with the Dynamic Delivery previewer, email recipients see an attachment placeholder until ATP Safe Attachments scanning is complete.</span></span>

> [!TIP]
> <span data-ttu-id="709f1-118">如果您使用的是行動裝置，且一開始 PDF 無法在 [動態傳遞] 預覽程式中轉譯，請嘗試使用您的行動瀏覽器登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="709f1-118">If you're using a mobile device, and PDFs are not rendering in Dynamic Delivery previewer at first, try signing into Office 365 using your mobile browser.</span></span>

<span data-ttu-id="709f1-119">透過動態傳遞，使用者可以在他們的附件進行分析的同時，立即讀取及回覆電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="709f1-119">With Dynamic Delivery, people can read and respond to their email messages right away, while their attachments are being analyzed.</span></span>

<span data-ttu-id="709f1-120">ATP 安全附件掃描會在您的 Office 365 資料所在的同一個區域中進行。</span><span class="sxs-lookup"><span data-stu-id="709f1-120">ATP Safe Attachments scanning takes place in the same region where your Office 365 data resides.</span></span> <span data-ttu-id="709f1-121">如需資料中心地理位置的詳細資訊，請參閱[您的資料位於何處？](https://products.office.com/where-is-your-data-located?geo=All)</span><span class="sxs-lookup"><span data-stu-id="709f1-121">For more information about data center geography, see [Where is your data located?](https://products.office.com/where-is-your-data-located?geo=All)</span></span>

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a><span data-ttu-id="709f1-122">當有人轉寄含有附件的電子郵件時，會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="709f1-122">What happens when someone forwards an email that contains an attachment?</span></span>

<span data-ttu-id="709f1-123">假設組織針對其 [ATP 安全附件原則](set-up-atp-safe-attachments-policies.md)使用動態傳遞，且有人收到包含附件的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="709f1-123">Suppose that an organization is using Dynamic Delivery for their [ATP Safe Attachments policy](set-up-atp-safe-attachments-policies.md), and someone receives an email that contains an attachment.</span></span> <span data-ttu-id="709f1-124">現在假設該人員將電子郵件轉寄給其他人。</span><span class="sxs-lookup"><span data-stu-id="709f1-124">Now suppose that person forwards the email message to someone else.</span></span> <span data-ttu-id="709f1-125">會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="709f1-125">What happens?</span></span> <span data-ttu-id="709f1-126">這取決於附加收件者是否包含在 ATP 安全附件原則中。</span><span class="sxs-lookup"><span data-stu-id="709f1-126">It depends on whether the additional recipients are included in ATP Safe Attachments policies.</span></span>

- <span data-ttu-id="709f1-127">如果收件者涵蓋在使用 [動態傳遞] 選項的 ATP 安全附件原則中，則收件者會看到預留位置，並且可以預覽相容的檔案。</span><span class="sxs-lookup"><span data-stu-id="709f1-127">If a recipient is covered by an ATP Safe Attachments policy using the Dynamic Delivery option, then the recipient sees the placeholder, with the ability to preview compatible files.</span></span>

- <span data-ttu-id="709f1-128">如果收件者未涵蓋在 ATP 安全附件原則中，則電子郵件和附件會通過，而不會有任何 ATP 安全附件掃描或附件預留位置。</span><span class="sxs-lookup"><span data-stu-id="709f1-128">If a recipient is not covered by an ATP Safe Attachments policy, then the email and attachment will go through, without any ATP Safe Attachments scanning or attachment placeholders.</span></span>

## <a name="whats-required-for-dynamic-delivery-to-work"></a><span data-ttu-id="709f1-129">動態傳遞運作需要哪些項目？</span><span class="sxs-lookup"><span data-stu-id="709f1-129">What's required for Dynamic Delivery to work?</span></span>

- <span data-ttu-id="709f1-130">貴組織必須有 [Office 365 進階威脅防護](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="709f1-130">Your organization must have [Office 365 Advanced Threat Protection](office-365-atp.md)</span></span>

- <span data-ttu-id="709f1-131">必須針對使用 [動態傳遞] 選項的 ATP 安全附件定義原則 (請參閱[在 Office 365 中設定 ATP 安全附件原則](set-up-atp-safe-attachments-policies.md))</span><span class="sxs-lookup"><span data-stu-id="709f1-131">Policies must be defined for ATP Safe Attachments using the Dynamic Delivery option (See [Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md))</span></span>

- <span data-ttu-id="709f1-132">貴組織的電子郵件必須在 Office 365 中託管。</span><span class="sxs-lookup"><span data-stu-id="709f1-132">Your organization's email must be hosted in Office 365.</span></span> <span data-ttu-id="709f1-133">雖然 [Office 365 進階威脅防護可以用於任何 SMTP 郵件傳輸代理程式](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (部分機器翻譯) (例如 Exchange Server)，但是適用於 ATP 安全附件的動態傳遞選項需要貴組織的電子郵件是在 Office 365 中託管。</span><span class="sxs-lookup"><span data-stu-id="709f1-133">Although [Office 365 Advanced Threat Protection can be used with any SMTP mail transfer agent](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (such as Exchange Server), the Dynamic Delivery option for ATP Safe Attachments requires that your organization's email be hosted in Office 365.</span></span> <span data-ttu-id="709f1-134">如果您的電子郵件未在 Office 365 中託管，請選擇不同的 [ATP 安全附件原則選項](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options)，例如 [封鎖]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="709f1-134">If your email is not hosted in Office 365, choose a different [ATP Safe Attachments policy option](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options), such as **Block**.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="709f1-135">其他考量因素</span><span class="sxs-lookup"><span data-stu-id="709f1-135">Additional considerations</span></span>

<span data-ttu-id="709f1-136">在某些情況下，動態傳遞不受支援。</span><span class="sxs-lookup"><span data-stu-id="709f1-136">There are certain scenarios in which Dynamic Delivery is not supported.</span></span> <span data-ttu-id="709f1-137">包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="709f1-137">These include the following:</span></span>

- <span data-ttu-id="709f1-138">在公用資料夾中的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="709f1-138">Email messages that are in public folders</span></span>

- <span data-ttu-id="709f1-139">使用自訂規則從使用者的信箱路由傳送出去又傳送回來的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="709f1-139">Email messages that are routed out of and then back into the user's mailbox using custom rules</span></span>

- <span data-ttu-id="709f1-140">移出 (自動或手動) 託管信箱並且移入其他位置 (包括封存資料夾) 的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="709f1-140">Email messages that are moved (automatically or manually) out of the hosted mailbox and into other locations, including archive folders</span></span>

- <span data-ttu-id="709f1-141">已刪除的電子郵件訊息</span><span class="sxs-lookup"><span data-stu-id="709f1-141">Email messages that are deleted</span></span>

- <span data-ttu-id="709f1-142">處於錯誤狀態的使用者信箱搜尋資料夾</span><span class="sxs-lookup"><span data-stu-id="709f1-142">A user's mailbox search folder that is in an error state</span></span>

- <span data-ttu-id="709f1-143">Exchange Online 系統管理員已啟用 Exclaimer 的環境。</span><span class="sxs-lookup"><span data-stu-id="709f1-143">Environments in which an Exchange Online admin has enabled Exclaimer.</span></span> <span data-ttu-id="709f1-144">若要解決此問題，請參閱[使用 ATP 動態傳遞和 Exclaimer 時，不會傳遞含有附件的郵件](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span><span class="sxs-lookup"><span data-stu-id="709f1-144">To resolve this, see [Messages with attachments are not delivered when ATP Dynamic Delivery and Exclaimer are used](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)</span></span>

- <span data-ttu-id="709f1-145">使用 [安全多用途網際網路郵件延伸 (S/MIME)](s-mime-for-message-signing-and-encryption.md)) 加密的郵件</span><span class="sxs-lookup"><span data-stu-id="709f1-145">Messages encrypted with [Secure/Multipurpose Internet Mail Extensions (S/MIME)](s-mime-for-message-signing-and-encryption.md))</span></span>

- <span data-ttu-id="709f1-146">如果動態傳遞不受支援，ATP 安全附件將不會掃描電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="709f1-146">In cases where Dynamic Delivery is not supported, ATP Safe Attachments will not scan email messages.</span></span> <span data-ttu-id="709f1-147">不過，系統會根據您 [ATP 安全連結原則](set-up-atp-safe-links-policies.md)的設定方式，在傳遞具有附件 (含有 URL) 的電子郵件訊息時會進行檢查。</span><span class="sxs-lookup"><span data-stu-id="709f1-147">However, delivering email messages with attachments that contain URLs will be checked, depending on how your [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured.</span></span> <span data-ttu-id="709f1-148">在這些情況下，會檢查電子郵件訊息和 Office 檔案中的 URL。</span><span class="sxs-lookup"><span data-stu-id="709f1-148">In these cases, URLs in email messages and Office files are checked.</span></span>
