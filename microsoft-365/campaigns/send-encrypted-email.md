---
title: 傳送加密的電子郵件
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
description: 了解如何傳送加密的電子郵件使用 Outlook。
ms.openlocfilehash: 7420073ba768f0e5adba33d673d3ccd6369e306c
ms.sourcegitcommit: 2f4a61f02ea90102ded8e5d71c9b78a1f7f6b789
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "35778138"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="14765-103">加密或標籤機密電子郵件</span><span class="sxs-lookup"><span data-stu-id="14765-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="14765-104">您的資料和活動資訊是很重要，通常機密。</span><span class="sxs-lookup"><span data-stu-id="14765-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="14765-105">協助讓您和您的電子郵件收件者的資訊則會需要區分大小寫視為使用加密和敏感度標籤來保護機密資訊。</span><span class="sxs-lookup"><span data-stu-id="14765-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>


## <a name="best-practices"></a><span data-ttu-id="14765-106">最佳做法</span><span class="sxs-lookup"><span data-stu-id="14765-106">Best practices</span></span>

<span data-ttu-id="14765-107">您傳送電子郵件具有敏感或機密資訊之前，請考慮開啟：</span><span class="sxs-lookup"><span data-stu-id="14765-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="14765-108">**加密：** 您可以加密您的電子郵件保護的電子郵件中的資訊私密性。</span><span class="sxs-lookup"><span data-stu-id="14765-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="14765-109">當您將加密的電子郵件訊息時，它會從可讀取的純文字轉換成亂碼的 cypher 文字。</span><span class="sxs-lookup"><span data-stu-id="14765-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="14765-110">只有收件者具有比對的公開金鑰用來加密郵件的私密金鑰可解密讀取的郵件。</span><span class="sxs-lookup"><span data-stu-id="14765-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="14765-111">任何收件者，而不相對應之私密金鑰，不過，會看到無法解讀文字。</span><span class="sxs-lookup"><span data-stu-id="14765-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="14765-112">您的系統管理員可以定義規則以自動加密符合特定準則的郵件。</span><span class="sxs-lookup"><span data-stu-id="14765-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="14765-113">比方說，您的系統管理員可以建立傳送組織外的所有郵件都加密的規則或涵蓋特定單字或片語的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="14765-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="14765-114">任何加密的郵件將會自動套用。</span><span class="sxs-lookup"><span data-stu-id="14765-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="14765-115">**敏感度標籤：** 您可以套用到您的檔案和電子郵件，讓它們與您的行銷活動資訊保護原則相容的敏感度標籤也可以設定您的行銷活動。</span><span class="sxs-lookup"><span data-stu-id="14765-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="14765-116">當您設定標籤時，標籤保存與您的電子郵件，即使它傳送-例如，藉由讓它成為您的郵件標頭。</span><span class="sxs-lookup"><span data-stu-id="14765-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![含有圖說文字的標籤和加密的電子郵件的圖表](media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a><span data-ttu-id="14765-118">進行設定</span><span class="sxs-lookup"><span data-stu-id="14765-118">Set it up</span></span>

<span data-ttu-id="14765-119">如果您想要加密的郵件不符合的預先定義的規則，或您的系統管理員尚未設定任何規則，您可以在傳送郵件之前，先套用各種不同的加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="14765-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="14765-120">傳送加密的郵件，從 Outlook 2013 或 2016 或 Outlook 2016 for Mac 中，選取**選項 > 權限**，然後選取您需要的保護選項。</span><span class="sxs-lookup"><span data-stu-id="14765-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="14765-121">您也可以藉由選取 [**保護**] 按鈕，網頁型 Outlook 中傳送加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="14765-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="14765-122">如需詳細資訊，請參閱[傳送、 檢視和回覆加密郵件的電腦版 Outlook 中](https://support.office.com/en-us/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="14765-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.office.com/en-us/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="14765-123">系統管理員設定</span><span class="sxs-lookup"><span data-stu-id="14765-123">Admin settings</span></span>

<span data-ttu-id="14765-124">您可以了解在[Office 365 中的電子郵件加密](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption)的電子郵件加密設定。</span><span class="sxs-lookup"><span data-stu-id="14765-124">You can learn all about setting up email encryption at [Email encryption in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="14765-125">會自動加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="14765-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="14765-126">系統管理員可以建立郵件流程規則來自動保護的傳送和接收來自您的行銷活動的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="14765-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="14765-127">設定規則以加密所有外寄的電子郵件，並移除加密，從加密的郵件來自組織內部或從組織傳送加密郵件的回覆。</span><span class="sxs-lookup"><span data-stu-id="14765-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> 

<span data-ttu-id="14765-128">建立郵件流程規則來加密與新的 Office 365 郵件加密 (OME) 功能的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="14765-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="14765-129">定義郵件流程規則觸發郵件加密與新的 OME 功能使用 Exchange 系統管理中心 (EAC)。</span><span class="sxs-lookup"><span data-stu-id="14765-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="14765-130">在網頁瀏覽器中，使用已授與全域系統管理員權限的工作或學校帳戶登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="14765-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in to Office 365.</span></span> 
2. <span data-ttu-id="14765-131">選擇 [管理] 磚。</span><span class="sxs-lookup"><span data-stu-id="14765-131">Choose the Admin tile.</span></span> 
3. <span data-ttu-id="14765-132">在系統管理中心中，選擇 [**系統管理中心 > Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="14765-132">In the admin center, choose **Admin centers > Exchange**.</span></span> 

<span data-ttu-id="14765-133">如需詳細資訊，請參閱[定義郵件流規則以加密 Office 365 中的電子郵件](https://docs.microsoft.com/en-us/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email)。</span><span class="sxs-lookup"><span data-stu-id="14765-133">For more information, see [Define mail flow rules to encrypt email messages in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="14765-134">品牌加密郵件</span><span class="sxs-lookup"><span data-stu-id="14765-134">Brand your encryption messages</span></span>

<span data-ttu-id="14765-135">您也可以套用行銷活動品牌自訂外觀和電子郵件訊息中的文字。</span><span class="sxs-lookup"><span data-stu-id="14765-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="14765-136">如需詳細資訊，請參閱[新增至加密郵件的貴組織的品牌](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption)。</span><span class="sxs-lookup"><span data-stu-id="14765-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption).</span></span>

