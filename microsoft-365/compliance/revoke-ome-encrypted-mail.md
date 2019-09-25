---
title: 撤銷由 Office 365 進階郵件加密所加密的電子郵件
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 作为 Office 365 管理员，您可以撤消使用 Office 365 高级邮件加密加密的某些电子邮件。
ms.openlocfilehash: e55129f68c7add589bd973b36f069d7cdbf631cf
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077581"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="dae33-103">撤銷由 Office 365 進階郵件加密所加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="dae33-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="dae33-104">电子邮件吊销作为 Office 365 高级邮件加密的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="dae33-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="dae33-105">在某些订阅中，Office 365 高级邮件加密在 Office 365 邮件加密之上可用。</span><span class="sxs-lookup"><span data-stu-id="dae33-105">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="dae33-106">高级邮件加密包含在[Microsoft 365 企业 E5、Office](https://www.microsoft.com/microsoft-365/enterprise/home)365 企业版 E5 和 Office 365 教育版 A5 中。</span><span class="sxs-lookup"><span data-stu-id="dae33-106">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="dae33-107">如果您的组织具有不包括 Office 365 高级邮件加密的 Office 365 订阅，则可以购买高级邮件加密作为符合高级合规性 SKU 的 E5 合规性的附加组件。</span><span class="sxs-lookup"><span data-stu-id="dae33-107">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="dae33-108">本文是关于[Office 365 消息加密](ome.md)的一系列较大文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="dae33-108">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="dae33-109">如果使用 Office 365 高级邮件加密对邮件进行了加密，并且您是 Office 365 管理员，则可以在某些情况下撤消该邮件。</span><span class="sxs-lookup"><span data-stu-id="dae33-109">If a message was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do revoke the message under certain conditions.</span></span> <span data-ttu-id="dae33-110">本文介绍了可以撤销的情况以及如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="dae33-110">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="dae33-111">可以撤消的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="dae33-111">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="dae33-112">如果收件人收到基于链接的、品牌加密的电子邮件，则可以撤消加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dae33-112">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="dae33-113">如果收件人在支持的 Outlook 客户端中收到本机内联体验，则无法撤消这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dae33-113">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="dae33-114">收件人是否收到基于链接的体验或内联体验取决于收件人标识类型：Office 365 和 Microsoft 帐户收件人（例如，outlook.com用户）在支持的 Outlook 客户端中获得内联体验。</span><span class="sxs-lookup"><span data-stu-id="dae33-114">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="dae33-115">所有其他收件人类型（如 Gmail 收件人）都将获得基于链接的体验。</span><span class="sxs-lookup"><span data-stu-id="dae33-115">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="dae33-116">已吊销加密电子邮件的收件人体验</span><span class="sxs-lookup"><span data-stu-id="dae33-116">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="dae33-117">电子邮件被吊销后，收件人在通过 Office 365 邮件加密门户访问加密电子邮件时收到错误："发件人已吊销邮件"。</span><span class="sxs-lookup"><span data-stu-id="dae33-117">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![显示已吊销加密电子邮件的屏幕截图。](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="dae33-119">如何撤销加密的电子邮件</span><span class="sxs-lookup"><span data-stu-id="dae33-119">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="dae33-120">步驟 1。</span><span class="sxs-lookup"><span data-stu-id="dae33-120">Step 1.</span></span> <span data-ttu-id="dae33-121">获取电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="dae33-121">Obtain the Message ID of the email</span></span>

<span data-ttu-id="dae33-122">在撤销加密邮件之前，您需要收集邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="dae33-122">Before you can revoke an encrypted mail you gather the Message ID of the mail.</span></span> <span data-ttu-id="dae33-123">MessageId 的格式通常为：</span><span class="sxs-lookup"><span data-stu-id="dae33-123">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="dae33-124">有多种方法可以查找要撤消的电子邮件的邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="dae33-124">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="dae33-125">本节介绍几个选项，但您可以使用任何提供 ID 的方法。</span><span class="sxs-lookup"><span data-stu-id="dae33-125">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="dae33-126">在安全&amp;合规性中心中使用邮件跟踪来标识要撤销的电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="dae33-126">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="dae33-127">在[Office 365 安全&合规中心 中，使用"新邮件跟踪"](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)按发件人或收件人搜索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dae33-127">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="dae33-128">找到电子邮件后，选择它可**显示"邮件跟踪详细信息"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="dae33-128">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="dae33-129">**展开"详细信息"** 以查找邮件 ID。</span><span class="sxs-lookup"><span data-stu-id="dae33-129">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="dae33-130">在安全&amp;合规性中心中使用 Office 邮件加密报告来标识要撤消的电子邮件的邮件 ID</span><span class="sxs-lookup"><span data-stu-id="dae33-130">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="dae33-131">在安全&amp;合规性中心中，导航到**邮件加密报告**。</span><span class="sxs-lookup"><span data-stu-id="dae33-131">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="dae33-132">有关此报告的信息，请参阅[在&amp;安全合规性中心中查看电子邮件安全报告。](view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="dae33-132">For information on this report, see [View email security reports in the Security &amp; Compliance Center](view-email-security-reports.md).</span></span>

2. <span data-ttu-id="dae33-133">选择"**查看详细信息"** 表并标识要撤销的邮件。</span><span class="sxs-lookup"><span data-stu-id="dae33-133">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="dae33-134">双击邮件以查看包含消息 ID 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="dae33-134">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="dae33-135">步驟 2。</span><span class="sxs-lookup"><span data-stu-id="dae33-135">Step 2.</span></span> <span data-ttu-id="dae33-136">验证邮件是否可撤销</span><span class="sxs-lookup"><span data-stu-id="dae33-136">Verify that the mail is revocable</span></span>

<span data-ttu-id="dae33-137">要验证是否可以撤消邮件，请在安全&amp;合规性中心的详细信息表中检查"取消状态"字段是否在"加密"报表中\*\*\*\* 可见。</span><span class="sxs-lookup"><span data-stu-id="dae33-137">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="dae33-138">要验证是否可以使用 Windows Powershell 撤消特定电子邮件，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="dae33-138">To verify whether you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="dae33-139">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="dae33-139">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="dae33-140">有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="dae33-140">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="dae33-141">运行 Get-OMEMessage 状态 cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dae33-141">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="dae33-142">这将返回消息的主题以及消息是否可撤销。</span><span class="sxs-lookup"><span data-stu-id="dae33-142">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="dae33-143">For example,</span><span class="sxs-lookup"><span data-stu-id="dae33-143">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="dae33-144">步驟 3。</span><span class="sxs-lookup"><span data-stu-id="dae33-144">Step 3.</span></span> <span data-ttu-id="dae33-145">撤销邮件</span><span class="sxs-lookup"><span data-stu-id="dae33-145">Revoke the mail</span></span>

<span data-ttu-id="dae33-146">知道要撤消的电子邮件的邮件 ID 并验证邮件可撤销后，可以使用安全&amp;合规性中心或 Windows Powershell 撤消该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dae33-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows Powershell.</span></span>

<span data-ttu-id="dae33-147">使用安全&amp;合规性中心撤销邮件</span><span class="sxs-lookup"><span data-stu-id="dae33-147">To revoke the message using the Security &amp; Compliance Center</span></span>

<span data-ttu-id="dae33-148">要撤消安全&amp;合规性中心中的电子邮件，在"加密报告"中，在邮件**的"详细信息"** 表中，**请选择"撤销邮件"。**</span><span class="sxs-lookup"><span data-stu-id="dae33-148">To revoke the email in the Security &amp; Compliance Center, in the Encryption report, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="dae33-149">您可以使用 Windows Powershell 使用 Set-OMEMessageRevocation cmdlet 撤销电子邮件。</span><span class="sxs-lookup"><span data-stu-id="dae33-149">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="dae33-150">[連線至 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="dae33-150">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="dae33-151">运行 Set-OMEMessageresrescdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dae33-151">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="dae33-152">要检查电子邮件是否已吊销，请运行 Get-OMEMessage 状态 cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dae33-152">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="dae33-153">如果吊销成功，cmdlet 将返回以下结果：</span><span class="sxs-lookup"><span data-stu-id="dae33-153">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="dae33-154">有关 Office 365 高级邮件加密的详细信息</span><span class="sxs-lookup"><span data-stu-id="dae33-154">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="dae33-155">Office 365 進階郵件加密</span><span class="sxs-lookup"><span data-stu-id="dae33-155">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="dae33-156">Office 365 高级邮件加密 - 电子邮件过期</span><span class="sxs-lookup"><span data-stu-id="dae33-156">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="dae33-157">消息策略和合规性服务说明</span><span class="sxs-lookup"><span data-stu-id="dae33-157">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
