---
title: 垃圾郵件信賴等級
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: 當電子郵件通過垃圾郵件篩選會指派的垃圾郵件計分。 該分數是對應至個別的垃圾郵件信賴等級 (SCL) 分級，並在 X 標頭中加上戳記。 服務採取動作時取決於垃圾郵件信賴解譯的 SCL 分級的郵件。 下表顯示由篩選以及對每個分級的輸入郵件採取的預設動作如何解譯不同 SCL 分級。
ms.openlocfilehash: 65b6f51199e6d8f6ce17a05b28c5bad15d9d1760
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42084755"
---
# <a name="spam-confidence-levels"></a><span data-ttu-id="10947-106">垃圾郵件信賴等級</span><span class="sxs-lookup"><span data-stu-id="10947-106">Spam confidence levels</span></span>

<span data-ttu-id="10947-107">當電子郵件通過垃圾郵件篩選會指派的垃圾郵件計分。</span><span class="sxs-lookup"><span data-stu-id="10947-107">When an email message goes through spam filtering it is assigned a spam score.</span></span> <span data-ttu-id="10947-108">該分數是對應至個別的垃圾郵件信賴等級 (SCL) 分級，並在 X 標頭中加上戳記。</span><span class="sxs-lookup"><span data-stu-id="10947-108">That score is mapped to an individual Spam Confidence Level (SCL) rating and stamped in an X-header.</span></span> <span data-ttu-id="10947-109">服務採取動作時取決於垃圾郵件信賴解譯的 SCL 分級的郵件。</span><span class="sxs-lookup"><span data-stu-id="10947-109">The service takes actions upon the messages depending upon the spam confidence interpretation of the SCL rating.</span></span> <span data-ttu-id="10947-110">下表顯示由篩選以及對每個分級的輸入郵件採取的預設動作如何解譯不同 SCL 分級。</span><span class="sxs-lookup"><span data-stu-id="10947-110">The following table shows how the different SCL ratings are interpreted by the filters and the default action that is taken on inbound messages for each rating.</span></span>
  
|<span data-ttu-id="10947-111">**SCL 分級**</span><span class="sxs-lookup"><span data-stu-id="10947-111">**SCL Rating**</span></span>|<span data-ttu-id="10947-112">**垃圾郵件信賴解譯**</span><span class="sxs-lookup"><span data-stu-id="10947-112">**Spam Confidence Interpretation**</span></span>|<span data-ttu-id="10947-113">**預設動作**</span><span class="sxs-lookup"><span data-stu-id="10947-113">**Default Action**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="10947-114">-1</span><span class="sxs-lookup"><span data-stu-id="10947-114">-1</span></span>|<span data-ttu-id="10947-115">非垃圾郵件來自 [安全寄件者，安全的收件者或安全列 （信任的合作夥伴） 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="10947-115">Non-spam coming from a safe sender, safe recipient, or safe listed IP address (trusted partner).</span></span>|<span data-ttu-id="10947-116">將郵件傳遞至收件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="10947-116">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="10947-117">0、1</span><span class="sxs-lookup"><span data-stu-id="10947-117">0, 1</span></span>|<span data-ttu-id="10947-118">非垃圾郵件因為已掃描郵件，並判定為初始狀態。</span><span class="sxs-lookup"><span data-stu-id="10947-118">Non-spam because the message was scanned and determined to be clean.</span></span>|<span data-ttu-id="10947-119">將郵件傳遞至收件者的收件匣。</span><span class="sxs-lookup"><span data-stu-id="10947-119">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="10947-120">5、 6</span><span class="sxs-lookup"><span data-stu-id="10947-120">5, 6</span></span>|<span data-ttu-id="10947-121">垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="10947-121">Spam</span></span>|<span data-ttu-id="10947-122">將郵件傳遞至收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="10947-122">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="10947-123">7、 8、 9</span><span class="sxs-lookup"><span data-stu-id="10947-123">7, 8, 9</span></span>|<span data-ttu-id="10947-124">高信賴度的垃圾郵件</span><span class="sxs-lookup"><span data-stu-id="10947-124">High confidence spam</span></span>|<span data-ttu-id="10947-125">將郵件傳遞至收件者的垃圾郵件] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="10947-125">Deliver the message to the recipients' Junk Email folder.</span></span>|
   
> [!TIP]
> <span data-ttu-id="10947-126">SCL 分級的 2、 3、 4、 7 和 8 不是由服務設定。</span><span class="sxs-lookup"><span data-stu-id="10947-126">SCL ratings of 2, 3, 4, 7, and 8 are not set by the service.</span></span> <span data-ttu-id="10947-127">SCL 分級為 5 或 6 會被視為可疑的垃圾郵件，也就是較不一定要大於 SCL 分級為 9，這會被視為特定垃圾郵件的垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="10947-127">An SCL rating of 5 or 6 is considered suspected spam, which is less certain to be spam than an SCL rating of 9, which is considered certain spam.</span></span> <span data-ttu-id="10947-128">垃圾郵件和高信賴度垃圾郵件的不同動作可以透過您在 Exchange 系統管理中心中的內容篩選原則設定。</span><span class="sxs-lookup"><span data-stu-id="10947-128">Different actions for spam and high confidence spam can be configured via your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="10947-129">如需詳細資訊，請參閱[設定您的垃圾郵件篩選原則](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="10947-129">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="10947-130">您也可以設定為 > 中所述[來設定垃圾郵件信賴等級 (SCL) 郵件中的使用郵件流程規則](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)使用郵件流程規則 （也稱為傳輸規則），符合特定條件的郵件的 SCL 分級。</span><span class="sxs-lookup"><span data-stu-id="10947-130">You can also set the SCL rating for messages that match specific conditions by using mail flow rules (also known as transport rules), as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span> <span data-ttu-id="10947-131">如果您使用郵件流程規則來設定的 scl 值為 7、 8 或 9 郵件會被視為高信賴度垃圾郵件。</span><span class="sxs-lookup"><span data-stu-id="10947-131">If you use a mail flow rule to set SCL of 7, 8, or 9 the message will be treated as high confidence spam.</span></span> 
  
||
|:-----|
|<span data-ttu-id="10947-p104">![LinkedIn Learning 的短圖示](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **初次使用 Office 365？**         探索 LinkedIn Learning 提供的 **Office 365 admins and IT pros** 免費影片課程。</span><span class="sxs-lookup"><span data-stu-id="10947-p104">![The short icon for LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
   

