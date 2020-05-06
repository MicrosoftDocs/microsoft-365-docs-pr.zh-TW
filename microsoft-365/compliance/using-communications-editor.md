---
title: 使用通訊編輯器
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
description: 當您設定內容格式時，請使用通訊編輯器變更文字和合併欄位變數。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0cb415da9aa09452176bd8aa9be4575cfc827582
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034475"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="d3c45-103">使用通訊編輯器</span><span class="sxs-lookup"><span data-stu-id="d3c45-103">Use the communications editor</span></span>

<span data-ttu-id="d3c45-104">當您定義入口網站內容、法律封存通知和相關的提醒/上報內容時，您可以利用通訊編輯器來格式化並動態自訂內容。</span><span class="sxs-lookup"><span data-stu-id="d3c45-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="d3c45-105">富文字編輯器</span><span class="sxs-lookup"><span data-stu-id="d3c45-105">Rich text editor</span></span> 

<span data-ttu-id="d3c45-106">通訊編輯器可讓使用者使用編輯器選項自訂文字。</span><span class="sxs-lookup"><span data-stu-id="d3c45-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="d3c45-107">例如，使用者可以變更字型類型、建立專案符號清單、反白顯示內容等等。</span><span class="sxs-lookup"><span data-stu-id="d3c45-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="d3c45-108">合併欄位變數</span><span class="sxs-lookup"><span data-stu-id="d3c45-108">Merge field variables</span></span>

<span data-ttu-id="d3c45-109">您可以利用通訊編輯器中的電子郵件合併變數，將自訂的系統管理員屬性嵌入通訊的內文文字。</span><span class="sxs-lookup"><span data-stu-id="d3c45-109">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="d3c45-110">傳送給管理員時，會以對應的欄位填入合併欄位。</span><span class="sxs-lookup"><span data-stu-id="d3c45-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="d3c45-111">例如，當傳送給「保管人 John Smith」時，合併欄位 [保管人 Name] 會以對應的名稱加以轉譯。</span><span class="sxs-lookup"><span data-stu-id="d3c45-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="d3c45-112">您可以透過選取 rtf 文字編輯器控制項頂端的**合併欄位**圖示，使用電子郵件合併欄位。</span><span class="sxs-lookup"><span data-stu-id="d3c45-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="d3c45-113">會根據使用者游標的位置來新增預留位置。</span><span class="sxs-lookup"><span data-stu-id="d3c45-113">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="d3c45-114">合併欄位變數清單</span><span class="sxs-lookup"><span data-stu-id="d3c45-114">List of merge field variables</span></span>

| <span data-ttu-id="d3c45-115">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="d3c45-115">Field name</span></span>                  | <span data-ttu-id="d3c45-116">欄位詳細資料</span><span class="sxs-lookup"><span data-stu-id="d3c45-116">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="d3c45-117">顯示名稱</span><span class="sxs-lookup"><span data-stu-id="d3c45-117">Display Name</span></span>  | <span data-ttu-id="d3c45-118">管理員的名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="d3c45-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="d3c45-119">確認連結</span><span class="sxs-lookup"><span data-stu-id="d3c45-119">Acknowledgement Link</span></span> | <span data-ttu-id="d3c45-120">自訂的連結，可記錄每個保管人的認可。</span><span class="sxs-lookup"><span data-stu-id="d3c45-120">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="d3c45-121">入口網站連結</span><span class="sxs-lookup"><span data-stu-id="d3c45-121">Portal Link</span></span>     | <span data-ttu-id="d3c45-122">管理員的規範入口網站的自訂連結。</span><span class="sxs-lookup"><span data-stu-id="d3c45-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="d3c45-123">簽發官</span><span class="sxs-lookup"><span data-stu-id="d3c45-123">Issuing Officer</span></span>                   | <span data-ttu-id="d3c45-124">指定之簽發專員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="d3c45-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="d3c45-125">簽發日期</span><span class="sxs-lookup"><span data-stu-id="d3c45-125">Issuing Date</span></span>                   | <span data-ttu-id="d3c45-126">發出通知的日期（UTC）。</span><span class="sxs-lookup"><span data-stu-id="d3c45-126">The date that the notice was issued (UTC).</span></span>              |
