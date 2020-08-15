---
title: Microsoft 365 合規性支援雙位元組字元集的版本資訊 (預覽版)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 針對雙位元組字元集支援的版本資訊。
ms.openlocfilehash: 13bac873f2ba18bc166451ea73ec0d569fb30f68
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695239"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="9a3d8-103">支援雙位元組字元集的版本資訊 (預覽版)</span><span class="sxs-lookup"><span data-stu-id="9a3d8-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="9a3d8-104">Microsoft 365 資訊保護目前支援預覽版的雙位元組字元集語言：</span><span class="sxs-lookup"><span data-stu-id="9a3d8-104">Microsoft 365 Information Protection now supports in preview double byte character set languages for:</span></span>

- <span data-ttu-id="9a3d8-105">中文 (簡體)</span><span class="sxs-lookup"><span data-stu-id="9a3d8-105">Chinese (simplified)</span></span>
- <span data-ttu-id="9a3d8-106">中文 (繁體)</span><span class="sxs-lookup"><span data-stu-id="9a3d8-106">Chinese (traditional)</span></span>
- <span data-ttu-id="9a3d8-107">韓文</span><span class="sxs-lookup"><span data-stu-id="9a3d8-107">Korean</span></span>
- <span data-ttu-id="9a3d8-108">日文</span><span class="sxs-lookup"><span data-stu-id="9a3d8-108">Japanese</span></span>

<span data-ttu-id="9a3d8-109">此預覽僅限商愛業雲端中，且僅限部署至：</span><span class="sxs-lookup"><span data-stu-id="9a3d8-109">This preview is only in the commercial cloud and the rollout is limited to:</span></span>

- <span data-ttu-id="9a3d8-110">日本</span><span class="sxs-lookup"><span data-stu-id="9a3d8-110">Japan</span></span>
- <span data-ttu-id="9a3d8-111">韓國</span><span class="sxs-lookup"><span data-stu-id="9a3d8-111">Korea</span></span>
- <span data-ttu-id="9a3d8-112">中國</span><span class="sxs-lookup"><span data-stu-id="9a3d8-112">China</span></span>
- <span data-ttu-id="9a3d8-113">香港特別行政區</span><span class="sxs-lookup"><span data-stu-id="9a3d8-113">Hong Kong</span></span>
- <span data-ttu-id="9a3d8-114">澳門特別行政區</span><span class="sxs-lookup"><span data-stu-id="9a3d8-114">Macau</span></span>
- <span data-ttu-id="9a3d8-115">台灣</span><span class="sxs-lookup"><span data-stu-id="9a3d8-115">Taiwan</span></span>

<span data-ttu-id="9a3d8-116">這項支援適用於敏感性資訊類型和關鍵字字典，並將反映在資料外洩防護、通訊合規性、Exchange Online、SharePoint Online、商務用 OneDrive 和 Teams 解決方案中。</span><span class="sxs-lookup"><span data-stu-id="9a3d8-116">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention, communications compliance, Exchange Online, SharePoint Online, OneDrive for Business, and Teams solutions.</span></span>

## <a name="known-issues"></a><span data-ttu-id="9a3d8-117">已知問題</span><span class="sxs-lookup"><span data-stu-id="9a3d8-117">Known issues</span></span>

- <span data-ttu-id="9a3d8-118">當電子郵件附加的文字檔採用不含位元組順序標記 (BOM) 的 UTF-8 格式時，通訊合規性原則不會偵測到該電子郵件。</span><span class="sxs-lookup"><span data-stu-id="9a3d8-118">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="9a3d8-119">如果針對原則條件輸入句子，通訊合規性原則就無法偵測值：「電子郵件包含這些文字」。</span><span class="sxs-lookup"><span data-stu-id="9a3d8-119">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="9a3d8-120">如果在原則中指定的文字是以字組的形式寫入，可以偵測到該文字；不過，如果是以句子中間寫入，將不會偵測到。</span><span class="sxs-lookup"><span data-stu-id="9a3d8-120">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="9a3d8-121">將字典指定為類型資訊的通訊合規性原則，不會偵測 Teams 的個人交談和頻道交談。</span><span class="sxs-lookup"><span data-stu-id="9a3d8-121">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="9a3d8-122">在此階段中，通訊合規性不支援下列條件 (我們計劃在日後修正這些問題)：</span><span class="sxs-lookup"><span data-stu-id="9a3d8-122">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="9a3d8-123">「電子郵件包含任何這些文字」</span><span class="sxs-lookup"><span data-stu-id="9a3d8-123">“Message contains any of these words”</span></span>
  - <span data-ttu-id="9a3d8-124">「電子郵件不包含任何這些文字」</span><span class="sxs-lookup"><span data-stu-id="9a3d8-124">“Message contains none of these words”</span></span>
  - <span data-ttu-id="9a3d8-125">「附件包含任何這些文字」</span><span class="sxs-lookup"><span data-stu-id="9a3d8-125">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="9a3d8-126">「附件包含任何這些文字」</span><span class="sxs-lookup"><span data-stu-id="9a3d8-126">“Attachment contains any of these words”</span></span>

<span data-ttu-id="9a3d8-127">而我們建議您使用關鍵字字典建立自訂敏感性資訊類型 (SIT)，這樣會偵測電子郵件和附件的模式，並使用此自訂 SIT 做為通訊合規性原則條件。</span><span class="sxs-lookup"><span data-stu-id="9a3d8-127">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>
