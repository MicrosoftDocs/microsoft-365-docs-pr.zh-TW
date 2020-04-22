---
title: 取代郵件加密檢視器應用程式
f1.keywords:
- NOCSH
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
description: 在2018年8月15日，我們將從 Android 和 Apple 店鋪移除 Office 365 郵件加密（OME） Viewer 行動應用程式。 需要有 Office 365 郵件加密檢視器行動應用程式，才能閱讀使用 Apple 和 Android 手機上舊版 OME 加密的電子郵件訊息和附件。 除了移除 OME Viewer 應用程式之外，我們並未對舊版的 OME 進行其他任何變更。
ms.openlocfilehash: 37a10942e49ca0e6249b2b6a0737411a0d6de1c5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636111"
---
# <a name="deprecating-message-encryption-viewer-app"></a><span data-ttu-id="e02e8-105">取代郵件加密檢視器應用程式</span><span class="sxs-lookup"><span data-stu-id="e02e8-105">Deprecating Message Encryption Viewer App</span></span>

<span data-ttu-id="e02e8-106">在2018年8月15日，我們已從 Android 和 Apple 店鋪移除 Office 365 郵件加密（OME） Viewer 行動應用程式。</span><span class="sxs-lookup"><span data-stu-id="e02e8-106">On August 15, 2018, we removed the Office 365 Message Encryption (OME) Viewer mobile app from Android and Apple stores.</span></span> <span data-ttu-id="e02e8-107">需要有 Office 365 郵件加密檢視器行動應用程式，才能閱讀使用 Apple 和 Android 手機上舊版 OME 加密的電子郵件訊息和附件。</span><span class="sxs-lookup"><span data-stu-id="e02e8-107">The Office 365 Message Encryption Viewer mobile app was required to read email messages and attachments that were encrypted with the previous version of OME on Apple and Android phones.</span></span> <span data-ttu-id="e02e8-108">除了移除 OME Viewer 應用程式之外，我們並未對舊版的 OME 進行其他任何變更。</span><span class="sxs-lookup"><span data-stu-id="e02e8-108">Apart from removing the OME Viewer app, we are not making any other changes to the previous version of OME.</span></span>
  
## <a name="changes-from-august-2018"></a><span data-ttu-id="e02e8-109">自八月2018的變更</span><span class="sxs-lookup"><span data-stu-id="e02e8-109">Changes from August 2018</span></span>

<span data-ttu-id="e02e8-110">如 9 2017 月宣佈所宣佈，我們已發佈新版本的[Office 365 郵件加密](https://aka.ms/ome2017)，因此使用者可以將加密及受保護的郵件傳送給組織內外的任何人，而不需要行動應用程式。</span><span class="sxs-lookup"><span data-stu-id="e02e8-110">As announced September 2017, we have released a new version of [Office 365 Message Encryption](https://aka.ms/ome2017) so that users can send encrypted and protected messages to anyone inside or outside the organization without the requirement of the mobile app.</span></span> <span data-ttu-id="e02e8-111">自那時起，我們已新增其他功能：</span><span class="sxs-lookup"><span data-stu-id="e02e8-111">Since then, we've added additional capabilities:</span></span>
  
- [<span data-ttu-id="e02e8-112">僅加密範本</span><span class="sxs-lookup"><span data-stu-id="e02e8-112">Encrypt-only template</span></span>](https://aka.ms/encryptonly)

- [<span data-ttu-id="e02e8-113">用於解密附件的控制項</span><span class="sxs-lookup"><span data-stu-id="e02e8-113">Control to decrypt attachments</span></span>](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
<span data-ttu-id="e02e8-114">使用此變更後，使用者將無法再從八月1下載 Office 365 郵件加密檢視器行動應用程式。</span><span class="sxs-lookup"><span data-stu-id="e02e8-114">With this change, users will no longer be able to download the Office 365 Message Encryption Viewer mobile app beginning August 1.</span></span> <span data-ttu-id="e02e8-115">因此，郵件收件者可能無法讀取某些 Android 和 Apple 行動裝置上舊版 OME 所加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="e02e8-115">As a result, mail recipients may not be able to read messages encrypted with the previous version of OME on some Android and Apple mobile devices.</span></span> <span data-ttu-id="e02e8-116">不過，他們仍可以在個人電腦（透過桌面瀏覽器）讀取這些郵件。</span><span class="sxs-lookup"><span data-stu-id="e02e8-116">However, they will still be able to read these messages on personal computers (via desktop browsers).</span></span> <span data-ttu-id="e02e8-117">已下載應用程式的使用者仍可以使用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="e02e8-117">Users who have already downloaded the app will continue to be able to use it.</span></span>
  
## <a name="why-this-change-was-made"></a><span data-ttu-id="e02e8-118">為何進行此變更</span><span class="sxs-lookup"><span data-stu-id="e02e8-118">Why this change was made</span></span>

<span data-ttu-id="e02e8-119">新版本的 OME 不再需要行動應用程式讀取受保護的電子郵件和附件。</span><span class="sxs-lookup"><span data-stu-id="e02e8-119">The new version of OME no longer requires a mobile app to read protected email messages and attachments.</span></span> <span data-ttu-id="e02e8-120">使用新 OME 功能的客戶可以在 Outlook mobile 中查看受保護的郵件，而非客戶可以在瀏覽器中查看受保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="e02e8-120">Customers using the new OME capabilities can view the protected message in Outlook mobile and non-customers can view protected messages in a browser.</span></span>
  
<span data-ttu-id="e02e8-121">要求使用者下載行動應用程式的另一個障礙是讓客戶能夠查看受保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="e02e8-121">Requiring users to download a mobile app is another hurdle for customers to view protected messages.</span></span> <span data-ttu-id="e02e8-122">新的 Office 365 郵件加密功能可提供更佳的移動體驗。</span><span class="sxs-lookup"><span data-stu-id="e02e8-122">The new Office 365 Message Encryption capabilities provide a better mobile experience.</span></span>
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="e02e8-123">我仍然可以使用舊版的 Office 365 郵件加密</span><span class="sxs-lookup"><span data-stu-id="e02e8-123">Can I still use the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="e02e8-124">先前版本的 Office 365 郵件加密現在不會被取代，但我們對新版本的 Office 365 郵件加密進行了很大的增強，這樣就能更輕鬆地將敏感資料加密及許可權保護給任何人，包括讓使用者直接在 Outlook 中讀取受保護郵件的能力（桌面、行動裝置和 web）。</span><span class="sxs-lookup"><span data-stu-id="e02e8-124">The previous version of Office 365 Message Encryption will not be deprecated at this time, however, we have made significant enhancements to the new version of Office 365 Message Encryption, which make it easier to encrypt and rights protect sensitive data to anyone and on any device - including the ability for users to read protected messages directly in Outlook (desktop, mobile, and web).</span></span> 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="e02e8-125">我需要做什麼才能準備這項變更</span><span class="sxs-lookup"><span data-stu-id="e02e8-125">What do I need to do to prepare for this change</span></span>

<span data-ttu-id="e02e8-126">如果您的組織目前將加密的附件傳送給需要 OME 檢視器應用程式的收件者，則應該更新您的檔和訓練資源。</span><span class="sxs-lookup"><span data-stu-id="e02e8-126">If your organization currently sends encrypted attachments to recipients that require the OME Viewer app, you should update your documentation and training resources.</span></span>
  
<span data-ttu-id="e02e8-127">建議您更新現有的 Exchange 郵件流程規則，以使用目前版本的 OME，讓您的組織能夠利用新的和改善的功能。</span><span class="sxs-lookup"><span data-stu-id="e02e8-127">We recommend updating existing Exchange mail flow rules to use the current version of OME so that your organization can take advantage of the new and improved capabilities.</span></span> <span data-ttu-id="e02e8-128">在您設定新的 OME 功能之後，收件者不需要 OME Viewer 應用程式，即可在行動裝置上讀取加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="e02e8-128">Once you have set up the new OME capabilities, recipients won't need the OME Viewer app to read encrypted messages on mobile devices.</span></span>
  
<span data-ttu-id="e02e8-129">Microsoft 建議您在組織合理的情況時，安排移至新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="e02e8-129">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="e02e8-130">如需相關指示，請參閱[Set up New Office 365 Message Encryption 功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="e02e8-130">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="e02e8-131">如果您想要進一步瞭解新功能的運作方式，請參閱[Office 365 Message Encryption](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="e02e8-131">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span>
  

