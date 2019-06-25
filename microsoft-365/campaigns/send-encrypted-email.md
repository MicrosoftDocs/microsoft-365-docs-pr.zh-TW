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
description: 瞭解如何使用 Outlook 傳送加密的電子郵件。
ms.openlocfilehash: 16e6a6977d7cd8ec4d6bf59adbcd196b14995752
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183251"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="1a92a-103">加密或標記您的機密電子郵件</span><span class="sxs-lookup"><span data-stu-id="1a92a-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="1a92a-104">您的資料和活動資訊非常重要且常常是機密資訊。</span><span class="sxs-lookup"><span data-stu-id="1a92a-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="1a92a-105">使用加密和敏感度標籤來協助保護這個敏感資訊, 讓您和您的電子郵件收件者將資訊視為所需的敏感度。</span><span class="sxs-lookup"><span data-stu-id="1a92a-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>


## <a name="best-practices"></a><span data-ttu-id="1a92a-106">最佳做法</span><span class="sxs-lookup"><span data-stu-id="1a92a-106">Best practices</span></span>

<span data-ttu-id="1a92a-107">在您使用機密或敏感資訊傳送電子郵件之前, 請考慮開啟:</span><span class="sxs-lookup"><span data-stu-id="1a92a-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="1a92a-108">**加密:** 您可以加密您的電子郵件, 以保護電子郵件中資訊的隱私權。</span><span class="sxs-lookup"><span data-stu-id="1a92a-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="1a92a-109">當您加密電子郵件時, 它會從可讀取的純文字轉換成已被打亂的 cypher 文字。</span><span class="sxs-lookup"><span data-stu-id="1a92a-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="1a92a-110">只有具有與用來加密郵件之公開金鑰相符的私密金鑰的收件者, 才可以解密郵件以進行讀取。</span><span class="sxs-lookup"><span data-stu-id="1a92a-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="1a92a-111">但沒有對應私密金鑰的任何收件者, 但是會看到無法解讀的文字。</span><span class="sxs-lookup"><span data-stu-id="1a92a-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="1a92a-112">您的系統管理員可以定義規則, 以自動加密符合特定準則的郵件。</span><span class="sxs-lookup"><span data-stu-id="1a92a-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="1a92a-113">例如, 您的系統管理員可以建立規則, 以加密在組織外部傳送的所有郵件, 或提及特定單字或片語的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="1a92a-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="1a92a-114">系統會自動套用任何加密規則。</span><span class="sxs-lookup"><span data-stu-id="1a92a-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="1a92a-115">**敏感度標籤:** 您的市場活動也可以設定可套用至檔案和電子郵件的敏感度標籤, 以保持其符合您的行銷活動資訊保護原則。</span><span class="sxs-lookup"><span data-stu-id="1a92a-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="1a92a-116">當您設定標籤時, 標籤會與您的電子郵件保持聯繫, 即使傳送時也是如此, 例如, 在郵件中顯示為標頭。</span><span class="sxs-lookup"><span data-stu-id="1a92a-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![包含標籤和加密之注解的電子郵件圖表](media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a><span data-ttu-id="1a92a-118">進行設定</span><span class="sxs-lookup"><span data-stu-id="1a92a-118">Set it up</span></span>

<span data-ttu-id="1a92a-119">如果您想要加密不符合預先定義規則的郵件, 或您的系統管理員尚未設定任何規則, 您可以在傳送郵件之前套用各種不同的加密規則。</span><span class="sxs-lookup"><span data-stu-id="1a92a-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="1a92a-120">若要從 Outlook 2013 或 2016 (或 Outlook 2016 Mac) 傳送加密的郵件, 請選取 [選項] [ **> 許可權**], 然後選取您需要的保護選項。</span><span class="sxs-lookup"><span data-stu-id="1a92a-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="1a92a-121">您也可以在 web 上的 Outlook 中選取 [**保護**] 按鈕, 傳送加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="1a92a-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="1a92a-122">如需詳細資訊, 請參閱[在 Outlook 中傳送、查看和回復加密郵件的電腦](https://support.office.com/en-us/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US)。</span><span class="sxs-lookup"><span data-stu-id="1a92a-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.office.com/en-us/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="1a92a-123">系統管理設定</span><span class="sxs-lookup"><span data-stu-id="1a92a-123">Admin settings</span></span>

<span data-ttu-id="1a92a-124">您可以在[Office 365 中瞭解如何在電子郵件加密中](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption)設定電子郵件加密。</span><span class="sxs-lookup"><span data-stu-id="1a92a-124">You can learn all about setting up email encryption at [Email encryption in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="1a92a-125">自動加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="1a92a-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="1a92a-126">系統管理員可以建立郵件流程規則, 以自動保護從您的市場活動傳送和接收的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1a92a-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="1a92a-127">設定規則以加密任何外寄的電子郵件, 並從您組織內部的加密郵件中移除加密, 或從您的組織傳送的加密郵件回復。</span><span class="sxs-lookup"><span data-stu-id="1a92a-127">Set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> 

<span data-ttu-id="1a92a-128">您可以建立郵件流程規則, 以使用新的 Office 365 郵件加密 (OME) 功能來加密電子郵件。</span><span class="sxs-lookup"><span data-stu-id="1a92a-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="1a92a-129">使用 Exchange 系統管理中心 (EAC), 定義使用新 OME 功能觸發郵件加密的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="1a92a-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="1a92a-130">在網頁瀏覽器中, 使用已被授與全域系統管理員許可權的公司或學校帳戶, 登入 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1a92a-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in to Office 365.</span></span> 
2. <span data-ttu-id="1a92a-131">選擇 [系統管理] 磚。</span><span class="sxs-lookup"><span data-stu-id="1a92a-131">Choose the Admin tile.</span></span> 
3. <span data-ttu-id="1a92a-132">在 Office 365 系統管理中心, 選擇 [系統**管理中心] > Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="1a92a-132">In the Office 365 admin center, choose **Admin centers > Exchange**.</span></span> 

<span data-ttu-id="1a92a-133">如需詳細資訊, 請參閱[定義郵件流程規則以加密 Office 365 中的電子](https://docs.microsoft.com/en-us/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email)郵件。</span><span class="sxs-lookup"><span data-stu-id="1a92a-133">For more information, see [Define mail flow rules to encrypt email messages in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="1a92a-134">署名您的加密郵件</span><span class="sxs-lookup"><span data-stu-id="1a92a-134">Brand your encryption messages</span></span>

<span data-ttu-id="1a92a-135">您也可以套用您的行銷活動品牌, 以自訂電子郵件訊息中的外觀和文字。</span><span class="sxs-lookup"><span data-stu-id="1a92a-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="1a92a-136">如需詳細資訊, 請參閱[將貴組織的品牌新增至加密的郵件](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption)。</span><span class="sxs-lookup"><span data-stu-id="1a92a-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption).</span></span>

