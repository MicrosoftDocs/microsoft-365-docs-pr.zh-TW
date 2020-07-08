---
title: 傳送加密的電子郵件
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: 瞭解如何使用 Outlook 傳送加密的電子郵件。
ms.openlocfilehash: b9d5d32b61c49dcffaab83fb13e46d32f2166552
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080024"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="7efc3-103">加密或標記敏感的電子郵件</span><span class="sxs-lookup"><span data-stu-id="7efc3-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="7efc3-104">您的資料和活動資訊非常重要，通常是保密的。</span><span class="sxs-lookup"><span data-stu-id="7efc3-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="7efc3-105">使用加密和敏感度標籤來協助保護此機密資訊，讓您和您的電子郵件收件者以其所需的靈敏度來處理資訊。</span><span class="sxs-lookup"><span data-stu-id="7efc3-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>


## <a name="best-practices"></a><span data-ttu-id="7efc3-106">最佳做法</span><span class="sxs-lookup"><span data-stu-id="7efc3-106">Best practices</span></span>

<span data-ttu-id="7efc3-107">在您傳送包含機密或機密資訊的電子郵件之前，請考慮開啟：</span><span class="sxs-lookup"><span data-stu-id="7efc3-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="7efc3-108">**加密：** 您可以加密您的電子郵件，以保護電子郵件中資訊的隱私權。</span><span class="sxs-lookup"><span data-stu-id="7efc3-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="7efc3-109">當您加密電子郵件時，它會從可讀取的純文字轉換成亂碼的 cypher 文字。</span><span class="sxs-lookup"><span data-stu-id="7efc3-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="7efc3-110">只有具有與用來加密郵件之公開金鑰相符的私密金鑰的收件者，才能解密郵件以進行讀取。</span><span class="sxs-lookup"><span data-stu-id="7efc3-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="7efc3-111">沒有對應私密金鑰的任何收件者，但是會看到無法破譯的文字。</span><span class="sxs-lookup"><span data-stu-id="7efc3-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="7efc3-112">您的系統管理員可以定義規則，以自動加密符合特定準則的郵件。</span><span class="sxs-lookup"><span data-stu-id="7efc3-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="7efc3-113">例如，您的系統管理員可以建立一種規則，用來加密您的組織外傳送的所有郵件，或所有提及特定文字或片語的郵件。</span><span class="sxs-lookup"><span data-stu-id="7efc3-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="7efc3-114">將會自動套用任何加密規則。</span><span class="sxs-lookup"><span data-stu-id="7efc3-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="7efc3-115">**敏感度標籤：** 您的活動也可以設定敏感度標籤，您可以將敏感度標籤套用至您的檔案和電子郵件，使其符合您的活動的資訊保護原則。</span><span class="sxs-lookup"><span data-stu-id="7efc3-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="7efc3-116">當您設定標籤時，標籤會隨電子郵件一起保留，即使傳送時也是如此; 例如，它會顯示為郵件的標頭。</span><span class="sxs-lookup"><span data-stu-id="7efc3-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![具有標籤和加密之標注的電子郵件圖表](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a><span data-ttu-id="7efc3-118">進行設定</span><span class="sxs-lookup"><span data-stu-id="7efc3-118">Set it up</span></span>

<span data-ttu-id="7efc3-119">如果您想要加密的郵件不符合預先定義的規則，或系統管理員尚未設定任何規則，您可以在傳送郵件之前，套用各種不同的加密規則。</span><span class="sxs-lookup"><span data-stu-id="7efc3-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="7efc3-120">若要從 Outlook 2013 或2016（或 Outlook 2016 Mac）傳送加密的郵件，請選取 [**選項] > 許可權**]，然後選取所需的保護選項。</span><span class="sxs-lookup"><span data-stu-id="7efc3-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="7efc3-121">您也可以在 web 上的 Outlook 中選取 [**保護**] 按鈕來傳送加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="7efc3-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="7efc3-122">如需詳細資訊，請參閱[在 Outlook 中傳送、查看和回復加密郵件的電腦](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)。</span><span class="sxs-lookup"><span data-stu-id="7efc3-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="7efc3-123">系統管理設定</span><span class="sxs-lookup"><span data-stu-id="7efc3-123">Admin settings</span></span>

<span data-ttu-id="7efc3-124">您可以[在 Microsoft 365 中瞭解如何在電子郵件加密中](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)設定電子郵件加密。</span><span class="sxs-lookup"><span data-stu-id="7efc3-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="7efc3-125">自動加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="7efc3-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="7efc3-126">系統管理員可以建立郵件流程規則，以自動保護從您的活動中傳送及接收的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7efc3-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="7efc3-127">設定用來加密任何外寄電子郵件的規則，並從組織內部或從組織傳送的加密郵件中移除加密。</span><span class="sxs-lookup"><span data-stu-id="7efc3-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> 

<span data-ttu-id="7efc3-128">您可以建立郵件流程規則，以使用新的 Office 365 郵件加密（OME）功能來加密電子郵件。</span><span class="sxs-lookup"><span data-stu-id="7efc3-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="7efc3-129">使用 Exchange 系統管理中心（EAC）定義郵件流程規則，以使用新的 OME 功能來觸發郵件加密。</span><span class="sxs-lookup"><span data-stu-id="7efc3-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="7efc3-130">在網頁瀏覽器中，使用已被授與全域管理員許可權的工作或學校帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="7efc3-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span> 
2. <span data-ttu-id="7efc3-131">選擇 [管理] 磚。</span><span class="sxs-lookup"><span data-stu-id="7efc3-131">Choose the Admin tile.</span></span> 
3. <span data-ttu-id="7efc3-132">在系統管理中心中，選擇 [系統**管理中心] > Exchange**。</span><span class="sxs-lookup"><span data-stu-id="7efc3-132">In the admin center, choose **Admin centers > Exchange**.</span></span> 

<span data-ttu-id="7efc3-133">如需詳細資訊，請參閱[定義郵件流程規則以加密電子郵件訊息](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)。</span><span class="sxs-lookup"><span data-stu-id="7efc3-133">For more information, see [Define mail flow rules to encrypt email messages](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="7efc3-134">標記加密郵件</span><span class="sxs-lookup"><span data-stu-id="7efc3-134">Brand your encryption messages</span></span>

<span data-ttu-id="7efc3-135">您也可以套用您的行銷活動品牌，以自訂電子郵件訊息中的外觀和文字。</span><span class="sxs-lookup"><span data-stu-id="7efc3-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="7efc3-136">如需詳細資訊，請參閱[將貴組織的品牌新增至加密的郵件](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)。</span><span class="sxs-lookup"><span data-stu-id="7efc3-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

