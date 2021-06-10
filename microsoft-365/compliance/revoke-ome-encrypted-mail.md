---
title: 撤銷由高級郵件加密所加密的電子郵件
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 以系統管理員和郵件寄件者的身分，您可以撤銷使用 Office 365 進階郵件加密所加密的特定電子郵件。
ms.openlocfilehash: 340a9e73dba50e28223ee561db749a089c649df6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051715"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="70983-103">撤銷由高級郵件加密所加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="70983-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="70983-104">電子郵件撤銷是以 Office 365 進階郵件加密的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="70983-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="70983-105">Office 365 進階郵件加密包含[Microsoft 365 企業版 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非盈利性員工定價) 、Office 365 企業版 E5 (非盈利性員工定價) 和 Office 365 教育版 A5。</span><span class="sxs-lookup"><span data-stu-id="70983-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="70983-106">如果您的組織中有未包括 Office 365 進階郵件加密的訂閱，您可以使用 Microsoft 365 E3 的 Microsoft 365 E5 合規性 SKU 附加元件購買它，Microsoft 365 E3 (非盈利性員工定價) 或 Office 365 進階合規性的 SKU 附加元件，Microsoft 365 E3 Microsoft 365 E3 非盈利性員工定價 (，或) Office 365。</span><span class="sxs-lookup"><span data-stu-id="70983-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="70983-107">本文是有關[Office 365 郵件加密](ome.md)的更多系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="70983-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="70983-108">如果郵件已使用 Office 365 進階郵件加密加密，而您是 Microsoft 365 系統管理員或您是郵件的寄件者，您可以在特定情況下撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="70983-109">系統管理員會使用 PowerShell 來撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="70983-110">作為寄件者，您可以撤銷從網頁 Outlook 直接傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="70983-111">本文說明可進行撤銷的情形及其執行方式。</span><span class="sxs-lookup"><span data-stu-id="70983-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="70983-112">您可以撤銷的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="70983-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="70983-113">如果收件者收到連結型、署名加密的電子郵件，系統管理員和郵件寄件者可以撤銷加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="70983-114">如果收件者在支援的 Outlook 用戶端收到本機內嵌經驗，則您無法撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="70983-115">收件者是否收到連結型體驗或內嵌經驗取決於收件者身分識別類型： Office 365 和 Microsoft 帳戶收件者 (例如，outlook.com 使用者) 在支援的 Outlook 用戶端中取得內嵌經驗。</span><span class="sxs-lookup"><span data-stu-id="70983-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="70983-116">所有其他收件者類型，例如 Gmail 和 Yahoo 收件者，會取得連結型經驗。</span><span class="sxs-lookup"><span data-stu-id="70983-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="70983-117">系統管理員和郵件寄件者可以吊銷以直接從網頁 Outlook 所套用之加密來加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="70983-118">例如，使用 [只加密] 選項加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="螢幕擷取畫面顯示 Outlook 網頁上的 [只加密] 選項。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="70983-120">已撤銷的加密電子郵件收件者經驗</span><span class="sxs-lookup"><span data-stu-id="70983-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="70983-121">一旦電子郵件遭到吊銷，當收件者透過 Office 365 郵件加密入口網站來存取加密的電子郵件時，收件者會收到錯誤：「郵件已由寄件者撤銷」。</span><span class="sxs-lookup"><span data-stu-id="70983-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![顯示已撤銷加密之電子郵件的螢幕擷取畫面。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="70983-123">操作方法：撤銷您傳送的加密郵件</span><span class="sxs-lookup"><span data-stu-id="70983-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="70983-124">您可以撤銷您傳送給單一收件者的郵件，該郵件使用社會帳戶，例如 gmail.com 或 yahoo.com。</span><span class="sxs-lookup"><span data-stu-id="70983-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="70983-125">換句話說，您可以撤銷傳送到單一收件者的電子郵件，該收件者會收到連結型經驗。</span><span class="sxs-lookup"><span data-stu-id="70983-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="70983-126">您無法撤銷傳送給收件者的郵件，而該收件者是使用公司或學校帳戶的 Office 365 或 Microsoft 365 或是使用 Microsoft 帳戶的使用者，例如 outlook.com 帳戶。</span><span class="sxs-lookup"><span data-stu-id="70983-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="70983-127">若要撤銷您傳送的加密郵件，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="70983-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="70983-128">在網頁 Outlook 的 [**傳送**] 資料夾中，流覽至您要撤銷的郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="70983-129">如果郵件是可吊銷的，您會在郵件頂端看到 [移除外部存取] 連結。</span><span class="sxs-lookup"><span data-stu-id="70983-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="螢幕擷取畫面顯示您想要在網頁 Outlook 中撤銷的加密郵件。":::

2. <span data-ttu-id="70983-131">按一下 [ **移除外部存取** ] 以撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="70983-132">郵件顯示其狀態為 [已撤銷]。</span><span class="sxs-lookup"><span data-stu-id="70983-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="螢幕擷取畫面顯示網頁 Outlook 中已撤銷的加密郵件。":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="70983-134">如何以系統管理員身分撤銷加密郵件</span><span class="sxs-lookup"><span data-stu-id="70983-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="70983-135">Microsoft 365 管理員請遵循下列一般步驟來撤銷合格的加密電子郵件：</span><span class="sxs-lookup"><span data-stu-id="70983-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="70983-136">取得電子郵件的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="70983-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="70983-137">確認您可以撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="70983-138">撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="70983-139">步驟 1.</span><span class="sxs-lookup"><span data-stu-id="70983-139">Step 1.</span></span> <span data-ttu-id="70983-140">取得電子郵件的郵件識別碼</span><span class="sxs-lookup"><span data-stu-id="70983-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="70983-141">在您可以撤銷加密的郵件之前，請先收集郵件的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="70983-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="70983-142">MessageId 的格式通常如下：</span><span class="sxs-lookup"><span data-stu-id="70983-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="70983-143">有多種方式可尋找您要撤銷之電子郵件的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="70983-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="70983-144">本節說明一些選項，但是您可以使用任何提供識別碼的方法。</span><span class="sxs-lookup"><span data-stu-id="70983-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="70983-145">若要使用安全性與 &amp; 合規性中心的郵件追蹤，識別您想要吊銷之電子郵件的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="70983-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="70983-146">[在安全性 & 規範中心內，以新郵件追蹤](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)方式，搜尋寄件者或收件者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="70983-147">找到電子郵件之後，請選取它以顯示 **郵件追蹤詳細資料** 窗格。</span><span class="sxs-lookup"><span data-stu-id="70983-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="70983-148">展開 **其他資訊** 以找出郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="70983-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="70983-149">若要在安全性與規範中心中使用 Office 郵件加密報告，識別您想要撤銷之電子郵件的郵件識別碼。 &amp;</span><span class="sxs-lookup"><span data-stu-id="70983-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="70983-150">在 [安全性與 &amp; 合規性中心] 中，流覽至 [ **郵件加密] 報告**。</span><span class="sxs-lookup"><span data-stu-id="70983-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="70983-151">如需此報告的詳細資訊，請參閱 [在安全性與 &amp; 規範中心中查看電子郵件安全性報告](../security/defender-365-security/view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="70983-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/defender-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="70983-152">選擇 [ **查看詳細資料** ] 表格，並識別您要撤銷的郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="70983-153">按兩下郵件，以查看包含郵件識別碼的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="70983-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="70983-154">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="70983-154">Step 2.</span></span> <span data-ttu-id="70983-155">確認郵件是可吊銷的</span><span class="sxs-lookup"><span data-stu-id="70983-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="70983-156">若要確認您是否可以吊銷郵件，請在 [安全性與規範中心] 的 [ **詳細資料** ] 表格中，檢查 [吊銷狀態] 欄位是否顯示在加密報告中 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="70983-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="70983-157">若要確認您是否可以使用 Windows PowerShell 撤銷特定的電子郵件，請完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="70983-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="70983-158">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並連接至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="70983-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="70983-159">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="70983-159">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="70983-160">依下列方式執行 Get-OMEMessageStatus Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="70983-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="70983-161">這個命令會傳回郵件的主旨，以及郵件是否可吊銷。</span><span class="sxs-lookup"><span data-stu-id="70983-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="70983-162">例如：</span><span class="sxs-lookup"><span data-stu-id="70983-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="70983-163">步驟 3.</span><span class="sxs-lookup"><span data-stu-id="70983-163">Step 3.</span></span> <span data-ttu-id="70983-164">撤銷郵件</span><span class="sxs-lookup"><span data-stu-id="70983-164">Revoke the mail</span></span>

<span data-ttu-id="70983-165">知道您要吊銷之電子郵件的郵件識別碼，並確認郵件可吊銷後，您就可以使用安全性與 &amp; 合規性中心或 Windows PowerShell 撤銷電子郵件。</span><span class="sxs-lookup"><span data-stu-id="70983-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="70983-166">使用安全性與 &amp; 合規性中心撤銷郵件</span><span class="sxs-lookup"><span data-stu-id="70983-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="70983-167">使用組織中具有全域系統管理員許可權的公司或學校帳戶，連接至安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="70983-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="70983-168">在 **加密報告** 中，于郵件的 [ **詳細資料** ] 表格中，選擇 **[撤銷郵件]**。</span><span class="sxs-lookup"><span data-stu-id="70983-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="70983-169">若要使用 Windows PowerShell 撤銷電子郵件，請使用 Set-OMEMessageRevocation Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="70983-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="70983-170">在您的組織中使用具有全域系統管理員許可權的公司或學校帳戶，[連線 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="70983-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="70983-171">依下列方式執行 Set-OMEMessageRevocation Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="70983-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="70983-172">若要檢查電子郵件是否已撤銷，請執行 Get-OMEMessageStatus Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="70983-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="70983-173">如果撤銷成功，Cmdlet 會傳回下列結果：</span><span class="sxs-lookup"><span data-stu-id="70983-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="70983-174">Office 365 進階郵件加密的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="70983-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="70983-175">Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="70983-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="70983-176">Office 365 進階郵件加密-電子郵件到期</span><span class="sxs-lookup"><span data-stu-id="70983-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="70983-177">郵件原則及合規性服務說明</span><span class="sxs-lookup"><span data-stu-id="70983-177">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)