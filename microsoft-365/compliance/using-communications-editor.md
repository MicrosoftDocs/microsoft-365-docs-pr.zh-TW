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
description: ''
ms.openlocfilehash: 2f445e4449fb20f0d13d857bb83d3dc85d7b7387
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069200"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="af279-102">使用通訊編輯器</span><span class="sxs-lookup"><span data-stu-id="af279-102">Use the communications editor</span></span>

<span data-ttu-id="af279-103">當您定義入口網站內容的內容，法律保留通知和相關的提醒/呈報之後，您可以利用通訊編輯器]，以格式化，並以動態方式來自訂您的內容。</span><span class="sxs-lookup"><span data-stu-id="af279-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="af279-104">Rtf 編輯器</span><span class="sxs-lookup"><span data-stu-id="af279-104">Rich text editor</span></span> 

<span data-ttu-id="af279-105">通訊編輯器可讓使用者自訂使用 [編輯器] 選項的文字。</span><span class="sxs-lookup"><span data-stu-id="af279-105">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="af279-106">例如，使用者可以變更字型類型，建立項目符號清單、 醒目提示內容等等。</span><span class="sxs-lookup"><span data-stu-id="af279-106">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="af279-107">合併欄位變數</span><span class="sxs-lookup"><span data-stu-id="af279-107">Merge field variables</span></span>

<span data-ttu-id="af279-108">您可以利用電子郵件合併變數將嵌入的通訊內文文字的自訂的 custodian 屬性從通訊編輯器。</span><span class="sxs-lookup"><span data-stu-id="af279-108">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="af279-109">傳送至 custodian 時，合併列印欄位也會填入對應的欄位。</span><span class="sxs-lookup"><span data-stu-id="af279-109">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="af279-110">例如，傳送至 custodian John Smith 時，[Custodian 名稱] 的合併列印欄位會轉譯與對應的名稱。</span><span class="sxs-lookup"><span data-stu-id="af279-110">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="af279-111">您可以藉由選取編排 rtf 編輯器控制項的**合併列印欄位**圖示使用電子郵件合併列印功能變數。</span><span class="sxs-lookup"><span data-stu-id="af279-111">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="af279-112">版面配置區將新增型關閉使用者的資料指標的位置。</span><span class="sxs-lookup"><span data-stu-id="af279-112">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="af279-113">合併列印欄位變數的清單</span><span class="sxs-lookup"><span data-stu-id="af279-113">List of merge field variables</span></span>

| <span data-ttu-id="af279-114">欄位名稱</span><span class="sxs-lookup"><span data-stu-id="af279-114">Field name</span></span>                  | <span data-ttu-id="af279-115">欄位的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="af279-115">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="af279-116">顯示名稱</span><span class="sxs-lookup"><span data-stu-id="af279-116">Display Name</span></span>  | <span data-ttu-id="af279-117">Custodian 的名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="af279-117">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="af279-118">認可連結</span><span class="sxs-lookup"><span data-stu-id="af279-118">Acknowledgement Link</span></span> | <span data-ttu-id="af279-119">記錄每個 custodian 認可自訂的連結。</span><span class="sxs-lookup"><span data-stu-id="af279-119">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="af279-120">入口網站的連結</span><span class="sxs-lookup"><span data-stu-id="af279-120">Portal Link</span></span>     | <span data-ttu-id="af279-121">Custodian 規範入口網站自訂的連結。</span><span class="sxs-lookup"><span data-stu-id="af279-121">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="af279-122">發出長</span><span class="sxs-lookup"><span data-stu-id="af279-122">Issuing Officer</span></span>                   | <span data-ttu-id="af279-123">指定的單位法務人員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="af279-123">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="af279-124">發行日期</span><span class="sxs-lookup"><span data-stu-id="af279-124">Issuing Date</span></span>                   | <span data-ttu-id="af279-125">請注意所發出的 (時間 UTC) 日期。</span><span class="sxs-lookup"><span data-stu-id="af279-125">The date that the notice was issued (UTC).</span></span>              |
