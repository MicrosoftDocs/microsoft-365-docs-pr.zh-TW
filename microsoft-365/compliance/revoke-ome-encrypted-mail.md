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
description: 以系統管理員和郵件寄件者的身分，您可以撤銷使用 Office 365 高級郵件加密所加密的特定電子郵件。
ms.openlocfilehash: 79ab3ef801d4d19317cbf1416d858de74d9f1393
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868936"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="83d0b-103">撤銷由高級郵件加密所加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="83d0b-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="83d0b-104">電子郵件吊銷是以 Office 365 Advanced Message Encryption 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="83d0b-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="83d0b-105">Office 365 Advanced Message Encryption 包含在 [Microsoft 365 企業版 e5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非盈利性員工定價) 、Office 365 企業版 E5 (非盈利性員工定價) 和 Office 365 教育版 A5。</span><span class="sxs-lookup"><span data-stu-id="83d0b-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="83d0b-106">如果您的組織中有未包含 Office 365 Advanced Message Encryption 的訂閱，您可以使用 microsoft 365 E5 相容性 SKU 附加元件（適用于 Microsoft 365 E3）購買它; microsoft 365 E3 (非盈利性員工定價) ，或 Office 365 的高級合規性 SKU 附加元件（適用于 Microsoft 365 E3），Microsoft 365 E3 (非盈利性員工定價) 或 Office 365 SKUs。</span><span class="sxs-lookup"><span data-stu-id="83d0b-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="83d0b-107">本文是有關 [Office 365 郵件加密](ome.md)的更多系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="83d0b-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="83d0b-108">如果郵件是使用 Office 365 高級郵件加密進行加密，而且您是 Microsoft 365 系統管理員或您是郵件的寄件者，您可以在特定條件下撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="83d0b-109">系統管理員會使用 PowerShell 來撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="83d0b-110">作為寄件者，您可以撤銷從網頁 Outlook 直接傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="83d0b-111">本文說明可進行撤銷的情形及其執行方式。</span><span class="sxs-lookup"><span data-stu-id="83d0b-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="83d0b-112">您可以撤銷的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="83d0b-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="83d0b-113">如果收件者收到連結型、署名加密的電子郵件，系統管理員和郵件寄件者可以撤銷加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="83d0b-114">如果收件者在支援的 Outlook 用戶端收到原生內嵌經驗，則您無法撤銷該郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="83d0b-115">收件者是否收到連結型體驗或內嵌經驗取決於收件者身分識別類型： Office 365 和 Microsoft 帳戶收件者 (例如，outlook.com 使用者) 在支援的 Outlook 用戶端中取得內嵌經驗。</span><span class="sxs-lookup"><span data-stu-id="83d0b-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="83d0b-116">所有其他收件者類型，例如 Gmail 和 Yahoo 收件者，會取得連結型經驗。</span><span class="sxs-lookup"><span data-stu-id="83d0b-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="83d0b-117">系統管理員和郵件寄件者可以吊銷以直接從網頁上 Outlook 套用的加密來加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="83d0b-118">例如，使用 [只加密] 選項加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="螢幕擷取畫面顯示 Outlook 網頁版中的 [僅加密] 選項。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="83d0b-120">已撤銷的加密電子郵件收件者經驗</span><span class="sxs-lookup"><span data-stu-id="83d0b-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="83d0b-121">一旦電子郵件遭到吊銷，當收件者透過 Office 365 郵件加密入口網站存取加密的電子郵件時，收件者會收到錯誤訊息：「郵件已由寄件者撤銷」。</span><span class="sxs-lookup"><span data-stu-id="83d0b-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![顯示已撤銷加密之電子郵件的螢幕擷取畫面。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="83d0b-123">操作方法：撤銷您傳送的加密郵件</span><span class="sxs-lookup"><span data-stu-id="83d0b-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="83d0b-124">若要撤銷您傳送的加密郵件，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="83d0b-124">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="83d0b-125">在網頁的 Outlook 中，流覽至 **您要** 撤銷的郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-125">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="83d0b-126">如果郵件是可吊銷的，您會在郵件頂端看到 [移除外部存取] 連結。</span><span class="sxs-lookup"><span data-stu-id="83d0b-126">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="螢幕擷取畫面顯示您想要在 Outlook 網頁版中撤銷的加密郵件。":::

2. <span data-ttu-id="83d0b-128">按一下 [ **移除外部存取** ] 以撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-128">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="83d0b-129">郵件顯示其狀態為 [已撤銷]。</span><span class="sxs-lookup"><span data-stu-id="83d0b-129">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="螢幕擷取畫面顯示 Outlook 網頁版中已撤銷的加密郵件。":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="83d0b-131">如何以系統管理員身分撤銷加密郵件</span><span class="sxs-lookup"><span data-stu-id="83d0b-131">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="83d0b-132">Microsoft 365 系統管理員請遵循下列一般步驟來撤銷合格的加密電子郵件：</span><span class="sxs-lookup"><span data-stu-id="83d0b-132">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="83d0b-133">取得電子郵件的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="83d0b-133">Get the Message ID of the email.</span></span>
- <span data-ttu-id="83d0b-134">確認您可以撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-134">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="83d0b-135">撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-135">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="83d0b-136">步驟 1：</span><span class="sxs-lookup"><span data-stu-id="83d0b-136">Step 1.</span></span> <span data-ttu-id="83d0b-137">取得電子郵件的郵件識別碼</span><span class="sxs-lookup"><span data-stu-id="83d0b-137">Obtain the Message ID of the email</span></span>

<span data-ttu-id="83d0b-138">在您可以撤銷加密的郵件之前，請先收集郵件的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="83d0b-138">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="83d0b-139">MessageId 的格式通常如下：</span><span class="sxs-lookup"><span data-stu-id="83d0b-139">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="83d0b-140">有多種方式可尋找您要撤銷之電子郵件的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="83d0b-140">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="83d0b-141">本節說明一些選項，但是您可以使用任何提供識別碼的方法。</span><span class="sxs-lookup"><span data-stu-id="83d0b-141">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="83d0b-142">若要使用安全性與 &amp; 合規性中心的郵件追蹤，識別您想要吊銷之電子郵件的郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="83d0b-142">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="83d0b-143">[在安全性 & 規範中心內，以新郵件追蹤](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)方式，搜尋寄件者或收件者的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-143">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="83d0b-144">找到電子郵件之後，請選取它以顯示 **郵件追蹤詳細資料** 窗格。</span><span class="sxs-lookup"><span data-stu-id="83d0b-144">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="83d0b-145">展開 **其他資訊** 以找出郵件識別碼。</span><span class="sxs-lookup"><span data-stu-id="83d0b-145">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="83d0b-146">若要在安全性與 &amp; 合規性中心使用 Office 郵件加密報告識別您想要吊銷之電子郵件的郵件識別碼</span><span class="sxs-lookup"><span data-stu-id="83d0b-146">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="83d0b-147">在 [安全性與 &amp; 合規性中心] 中，流覽至 [ **郵件加密] 報告**。</span><span class="sxs-lookup"><span data-stu-id="83d0b-147">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="83d0b-148">如需此報告的詳細資訊，請參閱 [在安全性與 &amp; 規範中心中查看電子郵件安全性報告](../security/office-365-security/view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="83d0b-148">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="83d0b-149">選擇 [ **查看詳細資料** ] 表格，並識別您要撤銷的郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-149">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="83d0b-150">按兩下郵件，以查看包含郵件識別碼的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="83d0b-150">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="83d0b-151">步驟 2：</span><span class="sxs-lookup"><span data-stu-id="83d0b-151">Step 2.</span></span> <span data-ttu-id="83d0b-152">確認郵件是可吊銷的</span><span class="sxs-lookup"><span data-stu-id="83d0b-152">Verify that the mail is revocable</span></span>

<span data-ttu-id="83d0b-153">若要確認您是否可以吊銷郵件，請在 [安全性與規範中心] 的 [ **詳細資料** ] 表格中，檢查 [吊銷狀態] 欄位是否顯示在加密報告中 &amp; 。</span><span class="sxs-lookup"><span data-stu-id="83d0b-153">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="83d0b-154">若要確認您是否可以使用 Windows PowerShell 撤銷特定的電子郵件訊息，請完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="83d0b-154">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="83d0b-155">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="83d0b-155">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="83d0b-156">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="83d0b-156">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="83d0b-157">執行 OMEMessageStatus 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="83d0b-157">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="83d0b-158">這個命令會傳回郵件的主旨，以及郵件是否可吊銷。</span><span class="sxs-lookup"><span data-stu-id="83d0b-158">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="83d0b-159">例如：</span><span class="sxs-lookup"><span data-stu-id="83d0b-159">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="83d0b-160">步驟 3：</span><span class="sxs-lookup"><span data-stu-id="83d0b-160">Step 3.</span></span> <span data-ttu-id="83d0b-161">撤銷郵件</span><span class="sxs-lookup"><span data-stu-id="83d0b-161">Revoke the mail</span></span>

<span data-ttu-id="83d0b-162">知道您要吊銷之電子郵件的郵件識別碼，並確認該郵件可吊銷後，您就可以使用安全性與 &amp; 合規性中心或 Windows PowerShell 撤銷電子郵件。</span><span class="sxs-lookup"><span data-stu-id="83d0b-162">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="83d0b-163">使用安全性與 &amp; 合規性中心撤銷郵件</span><span class="sxs-lookup"><span data-stu-id="83d0b-163">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="83d0b-164">使用組織中具有全域系統管理員許可權的公司或學校帳戶，連接至安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="83d0b-164">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="83d0b-165">在 **加密報告**中，于郵件的 [ **詳細資料** ] 表格中，選擇 **[撤銷郵件]**。</span><span class="sxs-lookup"><span data-stu-id="83d0b-165">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="83d0b-166">若要使用 Windows PowerShell 撤銷電子郵件，請使用 OMEMessageRevocation Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="83d0b-166">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="83d0b-167">使用組織中具有全域系統管理員許可權的工作或學校帳戶，連線 [至 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="83d0b-167">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="83d0b-168">執行 OMEMessageRevocation 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="83d0b-168">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="83d0b-169">若要檢查電子郵件是否已撤銷，請執行 OMEMessageStatus 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="83d0b-169">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="83d0b-170">如果撤銷成功，Cmdlet 會傳回下列結果：</span><span class="sxs-lookup"><span data-stu-id="83d0b-170">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="83d0b-171">有關 Office 365 Advanced Message Encryption 的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="83d0b-171">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="83d0b-172">Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="83d0b-172">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="83d0b-173">Office 365 Advanced Message Encryption-電子郵件到期</span><span class="sxs-lookup"><span data-stu-id="83d0b-173">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="83d0b-174">郵件原則及合規性服務說明</span><span class="sxs-lookup"><span data-stu-id="83d0b-174">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
