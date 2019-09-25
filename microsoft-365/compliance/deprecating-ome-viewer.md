---
title: 弃用 Office 365 消息加密查看器应用程序
ms.author: krowley
author: kccross
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
description: 2018 年 8 月 15 日，我们将从 Android 和 Apple 商店中删除 Office 365 消息加密 （OME） 查看器移动应用。 Office 365 消息加密查看器移动应用程序需要读取与 Apple 和 Android 手机上以前的 OME 版本加密的电子邮件和附件。 除了删除 OME 查看器应用外，我们不会对早期版本的 OME 进行任何其他更改。
ms.openlocfilehash: 3b5c92d4fa700a1ae8d7b104e33100301cf43506
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076358"
---
# <a name="deprecating-office-365-message-encryption-viewer-app"></a><span data-ttu-id="fa9b2-105">弃用 Office 365 消息加密查看器应用程序</span><span class="sxs-lookup"><span data-stu-id="fa9b2-105">Deprecating Office 365 Message Encryption Viewer App</span></span>

<span data-ttu-id="fa9b2-106">2018 年 8 月 15 日，我们从 Android 和 Apple 商店中删除了 Office 365 消息加密 （OME） 查看器移动应用。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-106">On August 15, 2018, we removed the Office 365 Message Encryption (OME) Viewer mobile app from Android and Apple stores.</span></span> <span data-ttu-id="fa9b2-107">Office 365 消息加密查看器移动应用程序需要读取与 Apple 和 Android 手机上以前的 OME 版本加密的电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-107">The Office 365 Message Encryption Viewer mobile app was required to read email messages and attachments that were encrypted with the previous version of OME on Apple and Android phones.</span></span> <span data-ttu-id="fa9b2-108">除了删除 OME 查看器应用外，我们不会对早期版本的 OME 进行任何其他更改。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-108">Apart from removing the OME Viewer app, we are not making any other changes to the previous version of OME.</span></span>
  
## <a name="changes-from-august-2018"></a><span data-ttu-id="fa9b2-109">2018 年 8 月起更改</span><span class="sxs-lookup"><span data-stu-id="fa9b2-109">Changes from August 2018</span></span>

<span data-ttu-id="fa9b2-110">正如 2017 年 9 月宣布的那样，我们发布了新版本的[Office 365 消息加密，](https://aka.ms/ome2017)以便用户可以在无需移动应用要求的情况下向组织内外的任何人发送加密和受保护的消息。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-110">As announced September 2017, we have released a new version of [Office 365 Message Encryption](https://aka.ms/ome2017) so that users can send encrypted and protected messages to anyone inside or outside the organization without the requirement of the mobile app.</span></span> <span data-ttu-id="fa9b2-111">此后，我们添加了其他功能：</span><span class="sxs-lookup"><span data-stu-id="fa9b2-111">Since then, we've added additional capabilities:</span></span>
  
- [<span data-ttu-id="fa9b2-112">仅加密模板</span><span class="sxs-lookup"><span data-stu-id="fa9b2-112">Encrypt-only template</span></span>](https://aka.ms/encryptonly)

- [<span data-ttu-id="fa9b2-113">控制解密附件</span><span class="sxs-lookup"><span data-stu-id="fa9b2-113">Control to decrypt attachments</span></span>](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
<span data-ttu-id="fa9b2-114">通过此更改，用户将无法从 8 月 1 日起下载 Office 365 消息加密查看器移动应用。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-114">With this change, users will no longer be able to download the Office 365 Message Encryption Viewer mobile app beginning August 1.</span></span> <span data-ttu-id="fa9b2-115">因此，邮件收件人可能无法在某些 Android 和 Apple 移动设备上读取使用早期版本的 OME 加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-115">As a result, mail recipients may not be able to read messages encrypted with the previous version of OME on some Android and Apple mobile devices.</span></span> <span data-ttu-id="fa9b2-116">但是，他们仍然可以在个人计算机上（通过桌面浏览器）读取这些消息。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-116">However, they will still be able to read these messages on personal computers (via desktop browsers).</span></span> <span data-ttu-id="fa9b2-117">已下载应用的用户将继续能够使用它。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-117">Users who have already downloaded the app will continue to be able to use it.</span></span>
  
## <a name="why-this-change-was-made"></a><span data-ttu-id="fa9b2-118">为什么进行此更改</span><span class="sxs-lookup"><span data-stu-id="fa9b2-118">Why this change was made</span></span>

<span data-ttu-id="fa9b2-119">新版本的 OME 不再需要移动应用来读取受保护的电子邮件和附件。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-119">The new version of OME no longer requires a mobile app to read protected email messages and attachments.</span></span> <span data-ttu-id="fa9b2-120">使用新的 OME 功能的 Office 365 客户可以在 Outlook 移动版中查看受保护的邮件，非 Office 365 客户可以在浏览器中查看受保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-120">Office 365 customers using the new OME capabilities can view the protected message in Outlook mobile and non-Office 365 customers can view protected messages in a browser.</span></span>
  
<span data-ttu-id="fa9b2-121">要求用户下载移动应用是客户查看受保护邮件的另一个障碍。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-121">Requiring users to download a mobile app is another hurdle for customers to view protected messages.</span></span> <span data-ttu-id="fa9b2-122">新的 Office 365 消息加密功能提供了更好的移动体验。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-122">The new Office 365 Message Encryption capabilities provide a better mobile experience.</span></span>
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="fa9b2-123">我能否仍然使用 Office 365 邮件加密的早期版本</span><span class="sxs-lookup"><span data-stu-id="fa9b2-123">Can I still use the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="fa9b2-124">Office 365 邮件加密的早期版本此时不会弃用，但是，我们对新版本的 Office 365 消息加密进行了重大增强，从而更易于加密，并有权保护任何人的敏感数据在任何设备上 - 包括 Office 365 用户直接在 Outlook（桌面、移动和 Web）中读取受保护邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-124">The previous version of Office 365 Message Encryption will not be deprecated at this time, however, we have made significant enhancements to the new version of Office 365 Message Encryption, which make it easier to encrypt and rights protect sensitive data to anyone and on any device - including the ability for Office 365 users to read protected messages directly in Outlook (desktop, mobile, and web).</span></span> 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="fa9b2-125">我需要做什么来准备这种变化</span><span class="sxs-lookup"><span data-stu-id="fa9b2-125">What do I need to do to prepare for this change</span></span>

<span data-ttu-id="fa9b2-126">如果您的组织当前向需要 OME 查看器应用的收件人发送加密附件，则应更新文档和培训资源。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-126">If your organization currently sends encrypted attachments to recipients that require the OME Viewer app, you should update your documentation and training resources.</span></span>
  
<span data-ttu-id="fa9b2-127">我们建议更新现有的 Exchange 邮件流规则以使用当前版本的 OME，以便您的组织可以利用新的和改进的功能。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-127">We recommend updating existing Exchange mail flow rules to use the current version of OME so that your organization can take advantage of the new and improved capabilities.</span></span> <span data-ttu-id="fa9b2-128">设置新的 OME 功能后，收件人将不需要 OME 查看器应用来读取移动设备上的加密邮件。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-128">Once you have set up the new OME capabilities, recipients won't need the OME Viewer app to read encrypted messages on mobile devices.</span></span>
  
<span data-ttu-id="fa9b2-129">Microsoft 建议您在您的组织合理时尽快制定计划，以迁移到新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-129">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="fa9b2-130">有关说明，请参阅[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-130">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="fa9b2-131">如果要首先了解有关新功能工作方式的更多信息，请参阅[Office 365 邮件加密](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="fa9b2-131">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span>
  

