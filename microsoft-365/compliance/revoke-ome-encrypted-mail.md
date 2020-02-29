---
title: 撤銷由 Office 365 進階郵件加密所加密的電子郵件
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 02/28/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 是 Office 365 系統管理員，您可以撤銷某些使用 Office 365 進階郵件加密所加密的電子郵件。
ms.openlocfilehash: 0e3ef031e61ed8bc7dd450e7ef61b6b7f41152c6
ms.sourcegitcommit: 004f01fc5d5bdb8aac03d69692d86c38b5e05e14
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/28/2020
ms.locfileid: "42333700"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="48738-103">撤銷由 Office 365 進階郵件加密所加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="48738-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="48738-104">電子郵件被撤銷被提供作為 Office 365 進階郵件加密的一部分。</span><span class="sxs-lookup"><span data-stu-id="48738-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="48738-105">Office 365 進階郵件加密隨附於[Microsoft 365 企業版 E5](https://www.microsoft.com/microsoft-365/enterprise/home)、 Office 365 E5、 Microsoft 365 E5 （非營利組織版人員價格），Office 365 企業版 E5 （非營利組織版人員價格） 和 Office 365 教育版 A5。</span><span class="sxs-lookup"><span data-stu-id="48738-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="48738-106">如果貴組織擁有不包含 Office 365 進階郵件加密的訂閱，您可以購買它與 Microsoft 365 E5 規範 SKU 附加元件的 Microsoft 365 E3，Microsoft 365 E3 （非營利組織版人員價格），或 Office 365 進階為 Microsoft 365 E3，Microsoft 365 E3 的合規性 SKU 附加元件 （非營利組織版人員價格），或 Office 365 Sku。</span><span class="sxs-lookup"><span data-stu-id="48738-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="48738-107">本文屬於較大的一連串的[Office 365 郵件加密](ome.md)的相關文章。</span><span class="sxs-lookup"><span data-stu-id="48738-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="48738-108">如果已加密郵件，使用 Office 365 進階郵件加密，而且您的 Office 365 系統管理員，您可以撤銷在某些情況下的訊息。</span><span class="sxs-lookup"><span data-stu-id="48738-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="48738-109">本文說明哪個撤銷可能會與執行方式] 底下的情況。</span><span class="sxs-lookup"><span data-stu-id="48738-109">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="48738-110">您可以撤銷的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="48738-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="48738-111">如果收件者收到連結為基礎，品牌加密的電子郵件，您可以撤銷加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="48738-111">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="48738-112">如果收件者收到的原生內嵌體驗中支援的 Outlook 用戶端，然後您無法撤銷那些。</span><span class="sxs-lookup"><span data-stu-id="48738-112">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke those.</span></span>

<span data-ttu-id="48738-113">收件者收到的連結為基礎的體驗還是內嵌經驗會視收件者的身分識別類型而定： Office 365 和 Microsoft 帳戶收件者 （例如，outlook.com 使用者） 中支援的 Outlook 用戶端取得內嵌體驗。</span><span class="sxs-lookup"><span data-stu-id="48738-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="48738-114">所有其他收件者類型，例如 Gmail 收件者，取得連結為基礎的體驗。</span><span class="sxs-lookup"><span data-stu-id="48738-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="48738-115">撤銷已加密的電子郵件的收件者體驗</span><span class="sxs-lookup"><span data-stu-id="48738-115">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="48738-116">當使用者透過 Office 365 郵件加密入口網站存取加密的電子郵件收件者之後已撤銷電子郵件，會收到錯誤: 「 寄件者，該訊息已被撤銷 」。</span><span class="sxs-lookup"><span data-stu-id="48738-116">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![螢幕擷取畫面顯示 [撤銷加密的電子郵件。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="48738-118">若要撤銷加密的電子郵件的方式</span><span class="sxs-lookup"><span data-stu-id="48738-118">How to revoke an encrypted email</span></span>

<span data-ttu-id="48738-119">Office 365 系統管理員請遵循下列一般步驟來撤銷合格加密的電子郵件：</span><span class="sxs-lookup"><span data-stu-id="48738-119">Office 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="48738-120">取得電子郵件訊息識別碼。</span><span class="sxs-lookup"><span data-stu-id="48738-120">Get the Message ID of the email.</span></span>
- <span data-ttu-id="48738-121">確認您可以撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="48738-121">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="48738-122">撤銷郵件。</span><span class="sxs-lookup"><span data-stu-id="48738-122">Revoke the mail.</span></span>

<span data-ttu-id="48738-123">撤銷程序中保留每個步驟的深度指示讀取。</span><span class="sxs-lookup"><span data-stu-id="48738-123">Keep reading for in-depth instructions for each step in the revocation process.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="48738-124">步驟 1。</span><span class="sxs-lookup"><span data-stu-id="48738-124">Step 1.</span></span> <span data-ttu-id="48738-125">取得電子郵件訊息識別碼</span><span class="sxs-lookup"><span data-stu-id="48738-125">Obtain the Message ID of the email</span></span>

<span data-ttu-id="48738-126">您可以撤銷加密的郵件之前，請收集郵件訊息識別碼。</span><span class="sxs-lookup"><span data-stu-id="48738-126">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="48738-127">MessageId 通常是的格式：</span><span class="sxs-lookup"><span data-stu-id="48738-127">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="48738-128">有多種方式來尋找您想要撤銷的電子郵件訊息識別碼。</span><span class="sxs-lookup"><span data-stu-id="48738-128">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="48738-129">本小節會說明兩個選項，但您可以使用任何方法，提供識別碼。</span><span class="sxs-lookup"><span data-stu-id="48738-129">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="48738-130">若要找出您想要撤銷安全性使用郵件追蹤的電子郵件訊息識別碼&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="48738-130">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="48738-131">搜尋由寄件者或收件者使用[新的郵件追蹤，在 Office 365 安全性 & 合規性中心中](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="48738-131">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="48738-132">一旦您已經找到電子郵件，請選取帶出 [**郵件追蹤詳細資料**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="48738-132">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="48738-133">依序展開 [**更多的資訊**來找出郵件的識別碼。</span><span class="sxs-lookup"><span data-stu-id="48738-133">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="48738-134">若要找出您想要使用 Office 郵件加密報告安全性撤銷電子郵件訊息識別碼&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="48738-134">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="48738-135">安全性&amp;合規性中心，瀏覽至**郵件加密報告**。</span><span class="sxs-lookup"><span data-stu-id="48738-135">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="48738-136">這份報告的詳細資訊，請參閱[檢視電子郵件安全性報告安全性&amp;合規性中心](../security/office-365-security/view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="48738-136">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="48738-137">選擇 [**檢視詳細資料]** 表格，並找出您想要撤銷的訊息。</span><span class="sxs-lookup"><span data-stu-id="48738-137">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="48738-138">按兩下 [檢視詳細資料] 包含郵件識別碼訊息</span><span class="sxs-lookup"><span data-stu-id="48738-138">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="48738-139">步驟 2。</span><span class="sxs-lookup"><span data-stu-id="48738-139">Step 2.</span></span> <span data-ttu-id="48738-140">確認便可撤銷之電子郵件</span><span class="sxs-lookup"><span data-stu-id="48738-140">Verify that the mail is revocable</span></span>

<span data-ttu-id="48738-141">若要確認您是否可以撤銷一則訊息，請檢查 [撤銷狀態] 欄位是否顯示在 [加密] 報告，**詳細資料**表格中的安全性&amp;合規性中心。</span><span class="sxs-lookup"><span data-stu-id="48738-141">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="48738-142">若要確認是否您可以使用 Windows PowerShell 撤銷將特定電子郵件，完成下列步驟。</span><span class="sxs-lookup"><span data-stu-id="48738-142">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="48738-143">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，請啟動 Windows PowerShell 工作階段，並連線至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="48738-143">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="48738-144">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="48738-144">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="48738-145">執行 Get OMEMessageStatus 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="48738-145">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="48738-146">此命令會傳回郵件以及是否可撤銷之郵件的主旨。</span><span class="sxs-lookup"><span data-stu-id="48738-146">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="48738-147">For example,</span><span class="sxs-lookup"><span data-stu-id="48738-147">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     “Test message” True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="48738-148">步驟 3：</span><span class="sxs-lookup"><span data-stu-id="48738-148">Step 3.</span></span> <span data-ttu-id="48738-149">撤銷郵件</span><span class="sxs-lookup"><span data-stu-id="48738-149">Revoke the mail</span></span>

<span data-ttu-id="48738-150">一旦您知道想要撤銷，請將電子郵件訊息識別碼且已驗證的訊息是可撤銷之，您可以撤銷使用安全的電子郵件&amp;合規性中心或 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="48738-150">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="48738-151">若要撤銷使用安全的郵件&amp;合規性中心</span><span class="sxs-lookup"><span data-stu-id="48738-151">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="48738-152">使用 Office 365 組織中具有全域系統管理員權限的工作或學校帳戶，連線到安全性 & 合規性中心。</span><span class="sxs-lookup"><span data-stu-id="48738-152">Using a work or school account that has global administrator permissions in your Office 365 organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="48738-153">在**加密報告**中為訊息， **Details** ] 資料表中選擇 [**撤銷訊息**。</span><span class="sxs-lookup"><span data-stu-id="48738-153">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="48738-154">若要使用 Windows PowerShell 撤銷電子郵件，請使用組 OMEMessageRevocation 指令程式。</span><span class="sxs-lookup"><span data-stu-id="48738-154">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="48738-155">使用公司或學校帳戶具有 Office 365 組織中，[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)的全域系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="48738-155">Using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="48738-156">執行設定 OMEMessageRevocation 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="48738-156">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="48738-157">若要檢查是否已撤銷電子郵件，請執行 Get OMEMessageStatus 指令程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="48738-157">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="48738-158">如果撤銷成功，cmdlet 就會傳回下列結果：</span><span class="sxs-lookup"><span data-stu-id="48738-158">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="48738-159">Office 365 進階郵件加密的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="48738-159">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="48738-160">Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="48738-160">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- <span data-ttu-id="48738-161">[Office 365 進階的郵件加密]-電子郵件到期](ome-advanced-expiration.md)</span><span class="sxs-lookup"><span data-stu-id="48738-161">[Office 365 Advanced Message Encryption - email expiration](ome-advanced-expiration.md)</span></span>

- [<span data-ttu-id="48738-162">郵件原則及符合性服務說明</span><span class="sxs-lookup"><span data-stu-id="48738-162">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
