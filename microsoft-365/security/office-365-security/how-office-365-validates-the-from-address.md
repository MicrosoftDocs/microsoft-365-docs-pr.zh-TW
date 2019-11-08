---
title: Office 365 如何驗證寄地址以防止網路釣魚
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: 若要協助防止詐騙，Office 365 和 Outlook.com 現在需要 RFC 規範從： 地址。
ms.openlocfilehash: ca3ec0ca6e9a2267c84549f26498b46479f74401
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032348"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="6d0b5-103">Office 365 如何驗證寄地址以防止網路釣魚</span><span class="sxs-lookup"><span data-stu-id="6d0b5-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="6d0b5-104">Office 365 和 Outlook.com 電子郵件帳戶會收到越來越多大量的網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-104">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="6d0b5-105">網路釣客使用的其中一種技術是要傳送郵件，值的 [從： 不符合[RFC 5322](https://tools.ietf.org/html/rfc5322)的地址。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-105">One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="6d0b5-106">[從： 地址也稱為 5322.From 地址。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-106">The From: address is also called the 5322.From address.</span></span> <span data-ttu-id="6d0b5-107">若要協助避免這種類型的網路釣魚，Office 365 和 Outlook.com 需要加入 RFC 不相容服務接收到的郵件從： 解決這篇文章所述。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-107">To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6d0b5-108">本文中的資訊必須要有基本了解一般的電子郵件地址格式。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-108">The information in this article requires you to have a basic understanding of the general format of email addresses.</span></span> <span data-ttu-id="6d0b5-109">如需詳細資訊，請參閱[RFC 5322](https://tools.ietf.org/html/rfc5322) （尤其是各節 3.2.3、 3.4、 和 3.4.1）、 [RFC 5321](https://tools.ietf.org/html/rfc5321)，以及[RFC 3696](https://tools.ietf.org/html/rfc3696)。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-109">For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696).</span></span> <span data-ttu-id="6d0b5-110">這篇文章是有關針對 5322.From 地址原則強制執行。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-110">This article is about policy enforcement for the 5322.From address.</span></span> <span data-ttu-id="6d0b5-111">本文不需 5321.MailFrom 地址。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-111">This article is not about the 5321.MailFrom address.</span></span> 
  
<span data-ttu-id="6d0b5-112">不幸的是，仍有一些舊版的電子郵件伺服器在網際網路上繼續傳送 「 合法 」 的電子郵件有遺失的郵件或從格式錯誤： 地址。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-112">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address.</span></span> <span data-ttu-id="6d0b5-113">如果您定期從組織而言，使用這些舊版的系統接收電子郵件，鼓勵這些組織更新以符合新式的安全性標準其郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-113">If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>
  
<span data-ttu-id="6d0b5-114">Microsoft 將會啟動推出於 2017 年 11 月 9 日本文中所述的原則強制執行。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="6d0b5-115">Office 365 如何強制從有效使用： 地址以防止網路釣魚攻擊</span><span class="sxs-lookup"><span data-stu-id="6d0b5-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="6d0b5-116">Office 365 的方式，它會強制使用的 [寄件者變更： 該函數會收到以更有效率的郵件中的地址會將您防止網路釣魚攻擊。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-116">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks.</span></span> <span data-ttu-id="6d0b5-117">本文內容：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-117">In this article:</span></span>
  
- [<span data-ttu-id="6d0b5-118">所有郵件必須都包含有效的從： 地址</span><span class="sxs-lookup"><span data-stu-id="6d0b5-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- <span data-ttu-id="6d0b5-119">[[從的格式： 地址如果您未包含的顯示名稱](how-office-365-validates-the-from-address.md#FormatNoDisplayName)</span><span class="sxs-lookup"><span data-stu-id="6d0b5-119">[Format of the From: address if you don't include a display name](how-office-365-validates-the-from-address.md#FormatNoDisplayName)</span></span>
    
- <span data-ttu-id="6d0b5-120">[[從的格式： 地址如果加上的顯示名稱](how-office-365-validates-the-from-address.md#FormatDisplayName)</span><span class="sxs-lookup"><span data-stu-id="6d0b5-120">[Format of the From: address if you include a display name](how-office-365-validates-the-from-address.md#FormatDisplayName)</span></span>
    
- [<span data-ttu-id="6d0b5-121">其他的有效及無效的範例： 地址</span><span class="sxs-lookup"><span data-stu-id="6d0b5-121">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)
    
- [<span data-ttu-id="6d0b5-122">隱藏的自動回覆給您的自訂網域，而不中斷 From： 原則</span><span class="sxs-lookup"><span data-stu-id="6d0b5-122">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [<span data-ttu-id="6d0b5-123">Office 365 從覆寫： 地址強制執行原則</span><span class="sxs-lookup"><span data-stu-id="6d0b5-123">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)
    
- [<span data-ttu-id="6d0b5-124">防止，並防止 cybercrimes Office 365 中的其他方法</span><span class="sxs-lookup"><span data-stu-id="6d0b5-124">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)
    
<span data-ttu-id="6d0b5-125">傳送代理另一個使用者不會影響這項變更，如需詳細資訊，請閱讀 Terry Zink 部落格 「[意味著什麼當我們將 「 寄件者 」 的電子郵件？](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)"。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-125">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>
  
### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="6d0b5-126">所有郵件必須都包含有效的從： 地址</span><span class="sxs-lookup"><span data-stu-id="6d0b5-126">All messages must include a valid From: address</span></span>
<span data-ttu-id="6d0b5-127"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="6d0b5-127"></span></span>

<span data-ttu-id="6d0b5-128">某些自動化的郵件未包含 From： 地址時便會被傳送。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-128">Some automated messages don't include a From: address when they are sent.</span></span> <span data-ttu-id="6d0b5-129">在過去，當 Office 365 或 Outlook.com 接收到郵件，但 From 不： 地址，該服務新增從下列預設值： 為了將可傳送作業訊息的地址：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-129">In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>
  
```
From: <>
```

<span data-ttu-id="6d0b5-130">啟動 2017 年 11 月 9 日，Office 365 將會推行變更其資料中心及郵件伺服器會強制執行新的規則可其中沒有 From 郵件： 地址不再可接受的 Office 365 或 Outlook.com。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-130">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com.</span></span> <span data-ttu-id="6d0b5-131">相反地，Office 365 所接收的所有郵件必須已經都包含有效的從： 地址。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-131">Instead, all messages received by Office 365 must already contain a valid From: address.</span></span> <span data-ttu-id="6d0b5-132">否則，郵件會傳送到 Outlook.com 和 Office 365 中的垃圾電子郵件] 或 [刪除的項目資料夾。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-132">Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span> 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="6d0b5-133">語法概觀： 有效的格式為 [從： Office 365 的地址</span><span class="sxs-lookup"><span data-stu-id="6d0b5-133">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="6d0b5-134"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="6d0b5-134"></span></span>

<span data-ttu-id="6d0b5-135">從值的格式： 地址在詳細資料中定義跨多個 Rfc。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-135">The format for the value of the From: address is defined in detail across several RFCs.</span></span> <span data-ttu-id="6d0b5-136">有許多變化定址和功能可能會視為有效或無效。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-136">There are many variations on addressing and what may be considered valid or invalid.</span></span> <span data-ttu-id="6d0b5-137">若要讓它保持簡單的 Microsoft 建議您使用下列格式和定義：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-137">To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>
  
```
From: "displayname " <emailaddress >
```

<span data-ttu-id="6d0b5-138">其中：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-138">Where:</span></span>
  
- <span data-ttu-id="6d0b5-139">（選用） *displayname*是說明擁有者的電子郵件地址的片語。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-139">(Optional)  *displayname*  is a phrase that describes the owner of the email address.</span></span> <span data-ttu-id="6d0b5-140">例如，這可能會更易記的名稱來描述名稱以外，信箱的寄件者。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-140">For example, this might be a more user-friendly name to describe the sender than the name of the mailbox.</span></span> <span data-ttu-id="6d0b5-141">使用的顯示名稱是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-141">Using a display name is optional.</span></span> <span data-ttu-id="6d0b5-142">不過，如果您選擇要使用的顯示名稱，Microsoft 建議您，您一律將其括住引號內所示。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-142">However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span> 
    
- <span data-ttu-id="6d0b5-143">（必要） *emailaddress*組成：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-143">(Required)  *emailaddress*  is made up of:</span></span> 
    
  ```
  local-part @domain
  ```

    <span data-ttu-id="6d0b5-144">其中：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-144">Where:</span></span>
    
  - <span data-ttu-id="6d0b5-145">（必要） *本機組件*是 string，識別會與位址相關聯的信箱。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-145">(Required)  *local-part*  is a string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="6d0b5-146">這是唯一的網域內。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-146">This is unique within the domain.</span></span> <span data-ttu-id="6d0b5-147">通常，信箱擁有者的使用者名稱或 GUID 用於值為本機組件。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-147">Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span> 
    
  - <span data-ttu-id="6d0b5-148">（必要） *網域*是主控信箱的電子郵件地址本機部分所識別郵件伺服器的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-148">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span> 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="6d0b5-149">[從的格式： 地址如果您未包含的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="6d0b5-149">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="6d0b5-150"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="6d0b5-150"></span></span>

<span data-ttu-id="6d0b5-151">從正確格式化 A： 不會納入的顯示名稱的地址包含只有單一電子郵件地址包含或不含角括弧。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-151">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets.</span></span> <span data-ttu-id="6d0b5-152">Microsoft 建議您不要以空格分開角括弧。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-152">Microsoft recommends that you do not separate the angle brackets with spaces.</span></span> <span data-ttu-id="6d0b5-153">此外，不包含任何項目後的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-153">In addition, don't include anything after the email address.</span></span>
  
<span data-ttu-id="6d0b5-154">下列範例是有效的：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-154">The following examples are valid:</span></span>
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="6d0b5-155">下列範例是有效但不是建議這麼做，因為它包含角括弧和電子郵件地址之間的空格：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-155">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>
  
```
From: < sender@contoso.com >
```

<span data-ttu-id="6d0b5-156">下列範例會無效，因為它會包含文字後的電子郵件地址：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-156">The following example is invalid because it contains text after the email address:</span></span>
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="6d0b5-157">[從的格式： 地址如果加上的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="6d0b5-157">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="6d0b5-158"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="6d0b5-158"></span></span>

<span data-ttu-id="6d0b5-159">針對從： 地址包含顯示名稱的值，適用下列規則：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-159">For From: addresses that include a value for the display name, the following rules apply:</span></span>
  
- <span data-ttu-id="6d0b5-160">如果寄件者地址包含顯示名稱，並顯示名稱包含逗點，顯示名稱必須在引號括住。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-160">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks.</span></span> <span data-ttu-id="6d0b5-161">例如：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-161">For example:</span></span>
    
    <span data-ttu-id="6d0b5-162">下列範例是有效的：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-162">The following example is valid:</span></span>
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="6d0b5-163">下列範例不是有效的：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-163">The following example is not valid:</span></span>
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="6d0b5-164">不圍繞引號括住的顯示名稱，如果該顯示名稱中包含逗點是根據 RFC 5322 無效的。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-164">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>
    
    <span data-ttu-id="6d0b5-165">最佳作法是，不論的顯示名稱前後的放入的引號是否是逗號內的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-165">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>
    
- <span data-ttu-id="6d0b5-166">如果寄件者地址中包含的顯示名稱、 電子郵件地址必須內角括弧括住。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-166">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>
    
    <span data-ttu-id="6d0b5-167">最佳作法是，Microsoft 強烈建議您插入的顯示名稱和電子郵件地址之間的空間。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-167">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="6d0b5-168">其他的有效及無效的範例： 地址</span><span class="sxs-lookup"><span data-stu-id="6d0b5-168">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="6d0b5-169"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6d0b5-169"></span></span>

- <span data-ttu-id="6d0b5-170">有效：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-170">Valid:</span></span>
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="6d0b5-171">無效。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-171">Invalid.</span></span> <span data-ttu-id="6d0b5-172">電子郵件地址不是以角括弧括住：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-172">The email address is not enclosed with angle brackets:</span></span>
    
  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="6d0b5-173">有效的但不是建議使用。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-173">Valid, but not recommended.</span></span> <span data-ttu-id="6d0b5-174">顯示名稱不是引號括住。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-174">The display name is not in quotes.</span></span> <span data-ttu-id="6d0b5-175">最佳作法是一律用引號括住顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-175">As a best practice, always put quotation marks around the display name:</span></span>
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="6d0b5-176">無效。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-176">Invalid.</span></span> <span data-ttu-id="6d0b5-177">每個項目括有引號，而不只顯示名稱：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-177">Everything is enclosed within quotation marks, not just the display name:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="6d0b5-178">無效。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-178">Invalid.</span></span> <span data-ttu-id="6d0b5-179">有任何電子郵件地址上角括號：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-179">There are no angle brackets around the email address:</span></span>
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="6d0b5-180">無效。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-180">Invalid.</span></span> <span data-ttu-id="6d0b5-181">沒有之間的顯示名稱和左的角括弧空間：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-181">There is no space between the display name and left angle bracket:</span></span>
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="6d0b5-182">無效。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-182">Invalid.</span></span> <span data-ttu-id="6d0b5-183">沒有顯示名稱前後關閉 quotation mark 和左的角括弧之間的空間。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-183">There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="6d0b5-184">隱藏的自動回覆給您的自訂網域，而不中斷 From： 原則</span><span class="sxs-lookup"><span data-stu-id="6d0b5-184">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="6d0b5-185"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="6d0b5-185"></span></span>

<span data-ttu-id="6d0b5-186">以新從： 原則強制執行 >，您不能再使用從： \< \>抑制自動回覆。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-186">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies.</span></span> <span data-ttu-id="6d0b5-187">相反地，您必須設定為 null 的 MX 記錄的自訂網域。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-187">Instead, you need to set up a null MX record for your custom domain.</span></span>
  
<span data-ttu-id="6d0b5-188">郵件交換程式 (MX) 記錄會以識別接收網域的郵件的郵件伺服器的 DNS 記錄的資源。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-188">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain.</span></span> <span data-ttu-id="6d0b5-189">因為沒有回應的伺服器可以將郵件傳送未發佈的位址，所以，將自然地被抑制自動回覆 （與所有回覆）。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-189">Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>
  
<span data-ttu-id="6d0b5-190">當您設定為 null 的 MX 記錄的自訂網域：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-190">When you set up a null MX record for your custom domain:</span></span>
  
- <span data-ttu-id="6d0b5-191">選擇從網域來傳送郵件，不會接受 （接收） 電子郵件。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-191">Choose a domain from which to send messages that doesn't accept (receive) email.</span></span> <span data-ttu-id="6d0b5-192">例如，如果您主要的網域是 contoso.com，您可能會選擇 noreply.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-192">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>
    
- <span data-ttu-id="6d0b5-193">設定您的網域的 null MX 記錄。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-193">Set up the null MX record for your domain.</span></span> <span data-ttu-id="6d0b5-194">Null 的 MX 記錄所組成單一點，例如：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-194">A null MX record consists of a single dot, for example:</span></span>
    
  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="6d0b5-195">如需發佈 null MX 的詳細資訊，請參閱[RFC 7505](https://tools.ietf.org/html/rfc7505)。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-195">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="6d0b5-196">Office 365 從覆寫： 地址強制執行原則</span><span class="sxs-lookup"><span data-stu-id="6d0b5-196">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="6d0b5-197"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="6d0b5-197"></span></span>

<span data-ttu-id="6d0b5-198">推出新原則完成後，您可以只略過此原則的內送郵件，您收到來自 Office 365 使用下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="6d0b5-198">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span> 
  
- <span data-ttu-id="6d0b5-199">IP 允許清單</span><span class="sxs-lookup"><span data-stu-id="6d0b5-199">IP allow lists</span></span>
    
- <span data-ttu-id="6d0b5-200">Exchange Online 的郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="6d0b5-200">Exchange Online mail flow rules</span></span>
    
<span data-ttu-id="6d0b5-201">Microsoft 強烈建議您針對覆寫強制使用 [從： 原則。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-201">Microsoft strongly recommends against overriding the enforcement of the From: policy.</span></span> <span data-ttu-id="6d0b5-202">覆寫此原則可以增加的曝光度垃圾郵件、 網路釣魚及其他 cybercrimes 貴組織的風險。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-202">Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>
  
<span data-ttu-id="6d0b5-203">您不能覆寫此原則，針對您在 Office 365 中傳送的外寄郵件。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-203">You cannot override this policy for outbound mail you send in Office 365.</span></span> <span data-ttu-id="6d0b5-204">此外，Outlook.com 不允許覆寫任何種類，甚至是透過支援。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-204">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span> 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="6d0b5-205">防止，並防止 cybercrimes Office 365 中的其他方法</span><span class="sxs-lookup"><span data-stu-id="6d0b5-205">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="6d0b5-206"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="6d0b5-206"></span></span>

<span data-ttu-id="6d0b5-207">如需有關如何在您可增強您的組織抵禦網路釣魚像 cybercrimes 的詳細資訊，濫發垃圾郵件、 資料外洩，以及其他威脅，請參閱[Office 365 的安全性最佳做法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)。</span><span class="sxs-lookup"><span data-stu-id="6d0b5-207">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6d0b5-208">相關主題</span><span class="sxs-lookup"><span data-stu-id="6d0b5-208">Related Topics</span></span>

[<span data-ttu-id="6d0b5-209">非法回應郵件與 EOP</span><span class="sxs-lookup"><span data-stu-id="6d0b5-209">Backscatter messages and EOP</span></span>](https://technet.microsoft.com/library/dn499795%28v=exchg.150%29.aspx)
  

