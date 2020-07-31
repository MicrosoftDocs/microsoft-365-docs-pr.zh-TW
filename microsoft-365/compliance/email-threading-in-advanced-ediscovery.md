---
title: 電子郵件執行緒-eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 當您執行高級 eDiscovery 分析時，電子郵件執行緒會分析電子郵件交談，並將每封郵件分隔成不同的類別。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e6072650a07f634b8dc19a013907eb36469c443b
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527671"
---
# <a name="email-threading"></a><span data-ttu-id="36d19-103">電子郵件執行緒</span><span class="sxs-lookup"><span data-stu-id="36d19-103">Email threading</span></span>

<span data-ttu-id="36d19-104">請考慮已有一段時間的電子郵件交談。</span><span class="sxs-lookup"><span data-stu-id="36d19-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="36d19-105">在大多數情況下，線索上的最後一封電子郵件會包含上述所有電子郵件的內容;檢查最後一個電子郵件將會提供執行緒中發生之談話的完整內容。</span><span class="sxs-lookup"><span data-stu-id="36d19-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="36d19-106">電子郵件執行緒識別這類電子郵件，讓檢閱者可以在不遺失任何內容的情況下，審閱收集的檔數。</span><span class="sxs-lookup"><span data-stu-id="36d19-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="36d19-107">電子郵件執行緒的功能為何？</span><span class="sxs-lookup"><span data-stu-id="36d19-107">What does email threading do?</span></span>

<span data-ttu-id="36d19-108">電子郵件串接會分析每封電子郵件，並將它 deconstructs 至個別郵件;每封電子郵件都是個別郵件的鏈。</span><span class="sxs-lookup"><span data-stu-id="36d19-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="36d19-109">然後，它會分析審閱集中的所有電子郵件，以判斷電子郵件是否有獨特的內容，或此鏈是否完全包含在不同的電子郵件中。</span><span class="sxs-lookup"><span data-stu-id="36d19-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="36d19-110">在結束電子郵件中分為四個類別：</span><span class="sxs-lookup"><span data-stu-id="36d19-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="36d19-111">**包含**：電子郵件中的最後一封郵件有唯一的內容，而且電子郵件中包含其他電子郵件中包含的所有附件，該內容完全包含在此電子郵件中。</span><span class="sxs-lookup"><span data-stu-id="36d19-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="36d19-112">**包括減號**：電子郵件中的最後一封郵件有唯一的內容，但是電子郵件不包含其他電子郵件中所包含的一些附件，此電子郵件中的內容已完全包含在此電子郵件中。</span><span class="sxs-lookup"><span data-stu-id="36d19-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="36d19-113">**包含副本**：含非獨佔/包含的負數電子郵件的確切副本</span><span class="sxs-lookup"><span data-stu-id="36d19-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="36d19-114">**None**：此電子郵件的內容全部包含在至少一個標記為包含/包含減號的電子郵件中。</span><span class="sxs-lookup"><span data-stu-id="36d19-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="36d19-115">它與 Outlook 中的交談有何不同？</span><span class="sxs-lookup"><span data-stu-id="36d19-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="36d19-116">這聽起來類似于 Outlook 中的交談群組。</span><span class="sxs-lookup"><span data-stu-id="36d19-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="36d19-117">不過，有一些重要的區別。</span><span class="sxs-lookup"><span data-stu-id="36d19-117">However, there are some important distinctions.</span></span> <span data-ttu-id="36d19-118">請考慮可分為兩個交談的電子郵件交談;例如，某人回應的電子郵件並不是最新的交談，所以交談中的最後兩封電子郵件都有唯一的內容。</span><span class="sxs-lookup"><span data-stu-id="36d19-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="36d19-119">Outlook 仍然會將電子郵件組合成單一交談;只閱讀最後一個電子郵件會丟失第二對最後一個電子郵件的內容，也就是包含唯一的內容。</span><span class="sxs-lookup"><span data-stu-id="36d19-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="36d19-120">因為電子郵件執行緒會將每封電子郵件剖析為個別元件，並加以比較，所以電子郵件執行緒會將最後兩封電子郵件都標示為包含在內，以確保您閱讀所有標記為包含的電子郵件時，不會漏掉任何內容。</span><span class="sxs-lookup"><span data-stu-id="36d19-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
