---
title: 管理 Office 365 郵件加密
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 设置完 Office 365 消息加密 （OME） 后，可以通过多种方式自定义部署配置。 例如，您可以配置是否启用一次性密码、在 Web 上的 Outlook 中显示"保护"按钮等。 本文中的任务描述了如何。
ms.openlocfilehash: 5e087211ec72c9cc37896a9a48cc01ce3c1a8d07
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077183"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="9b646-105">管理 Office 365 郵件加密</span><span class="sxs-lookup"><span data-stu-id="9b646-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="9b646-106">设置完 Office 365 消息加密 （OME） 后，可以通过多种方式自定义部署配置。</span><span class="sxs-lookup"><span data-stu-id="9b646-106">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="9b646-107">例如，您可以配置是否启用一次性密码、在 Web 上的 Outlook 中显示**加密**按钮等。</span><span class="sxs-lookup"><span data-stu-id="9b646-107">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="9b646-108">本文中的任务描述了如何。</span><span class="sxs-lookup"><span data-stu-id="9b646-108">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="9b646-109">管理 Google、Yahoo 和 Microsoft 帐户收件人是否可以使用这些帐户登录到 Office 365 邮件加密门户</span><span class="sxs-lookup"><span data-stu-id="9b646-109">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="9b646-110">设置新的 Office 365 邮件加密功能时，组织中的用户可以向 Office 365 组织外部的收件人发送邮件。</span><span class="sxs-lookup"><span data-stu-id="9b646-110">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization.</span></span> <span data-ttu-id="9b646-111">如果收件人使用社交*ID（* 如 Google 帐户、雅虎帐户或 Microsoft 帐户），则收件人可以使用社交 ID 登录 OME 门户。</span><span class="sxs-lookup"><span data-stu-id="9b646-111">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="9b646-112">如果需要，您可以选择不允许收件人使用社交标识登录到 OME 门户。</span><span class="sxs-lookup"><span data-stu-id="9b646-112">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="9b646-113">管理收件人是否可以使用社交标识登录到 OME 门户</span><span class="sxs-lookup"><span data-stu-id="9b646-113">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="9b646-114">[使用远程电源外壳连接到在线交换。](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9b646-114">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="9b646-115">使用社交 IdSignIn 参数运行 Set-OME 配置 cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9b646-115">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="9b646-116">例如，要禁用社交 ID：</span><span class="sxs-lookup"><span data-stu-id="9b646-116">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="9b646-117">要启用社交 ID：</span><span class="sxs-lookup"><span data-stu-id="9b646-117">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="9b646-118">管理 Office 365 邮件加密门户的一次性密码的使用</span><span class="sxs-lookup"><span data-stu-id="9b646-118">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="9b646-119">如果 OME 加密的邮件的收件人不使用 Outlook，而不考虑收件人使用的帐户，则收件人将收到一个限时 Web 视图链接，允许他们阅读邮件。</span><span class="sxs-lookup"><span data-stu-id="9b646-119">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="9b646-120">此链接包括一次性密码。</span><span class="sxs-lookup"><span data-stu-id="9b646-120">This link includes a one-time pass code.</span></span> <span data-ttu-id="9b646-121">作为管理员，您可以决定收件人是否可以使用一次性密码登录到 OME 门户。</span><span class="sxs-lookup"><span data-stu-id="9b646-121">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="9b646-122">管理 OME 是否生成一次性密码</span><span class="sxs-lookup"><span data-stu-id="9b646-122">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="9b646-123">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，然后启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9b646-123">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9b646-124">有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="9b646-124">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9b646-125">使用 OTP 启用参数运行 Set-OME 配置 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9b646-125">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="9b646-126">例如，要禁用一次性密码：</span><span class="sxs-lookup"><span data-stu-id="9b646-126">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="9b646-127">要启用一次性密码：</span><span class="sxs-lookup"><span data-stu-id="9b646-127">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="9b646-128">管理 Web Outlook 中"加密"按钮的显示</span><span class="sxs-lookup"><span data-stu-id="9b646-128">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="9b646-129">作为管理员，您可以管理是否向最终用户显示此按钮。</span><span class="sxs-lookup"><span data-stu-id="9b646-129">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="9b646-130">管理"加密"按钮是否显示在 Web 上的 Outlook 中</span><span class="sxs-lookup"><span data-stu-id="9b646-130">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="9b646-131">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，然后启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9b646-131">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9b646-132">有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="9b646-132">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9b646-133">使用 -简化客户端访问启用参数运行 Set-IRM 配置 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9b646-133">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="9b646-134">例如，要**禁用"加密"** 按钮：</span><span class="sxs-lookup"><span data-stu-id="9b646-134">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="9b646-135">要**启用"加密"** 按钮：</span><span class="sxs-lookup"><span data-stu-id="9b646-135">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="9b646-136">为 iOS 邮件应用用户启用服务端电子邮件解密</span><span class="sxs-lookup"><span data-stu-id="9b646-136">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="9b646-137">iOS 邮件应用无法解密受 Office 365 邮件加密保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="9b646-137">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="9b646-138">作为 Office 365 管理员，您可以对传递到 iOS 邮件应用的邮件应用服务端解密。</span><span class="sxs-lookup"><span data-stu-id="9b646-138">As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="9b646-139">当您选择使用服务端解密时，服务会向 iOS 设备发送消息的解密副本。</span><span class="sxs-lookup"><span data-stu-id="9b646-139">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="9b646-140">客户端设备存储消息的解密副本。</span><span class="sxs-lookup"><span data-stu-id="9b646-140">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="9b646-141">即使 iOS 邮件应用不将客户端使用权限应用于用户，该邮件也会保留有关使用权限的信息。</span><span class="sxs-lookup"><span data-stu-id="9b646-141">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="9b646-142">用户可以复制或打印邮件，即使他们最初没有这样做的权限。</span><span class="sxs-lookup"><span data-stu-id="9b646-142">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="9b646-143">但是，如果用户尝试完成需要 Office 365 邮件服务器的操作（如转发邮件），则如果用户最初没有执行此操作的权限，则服务器将不允许执行该操作。</span><span class="sxs-lookup"><span data-stu-id="9b646-143">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="9b646-144">但是，最终用户可以通过从 iOS 邮件应用中的不同帐户转发邮件来绕过"不转发"使用限制。</span><span class="sxs-lookup"><span data-stu-id="9b646-144">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="9b646-145">无论您是否设置了邮件的服务端解密，在 iOS 邮件应用中都无法查看加密邮件和受权限保护邮件的附件。</span><span class="sxs-lookup"><span data-stu-id="9b646-145">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="9b646-146">如果选择不允许将解密邮件发送给 iOS 邮件应用用户，则用户会收到一条消息，指出他们无权查看邮件。</span><span class="sxs-lookup"><span data-stu-id="9b646-146">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="9b646-147">默认情况下，未启用电子邮件的服务端解密。</span><span class="sxs-lookup"><span data-stu-id="9b646-147">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="9b646-148">有关详细信息，以及有关客户体验的视图，请参阅[查看 iPhone 或 iPad 上的加密邮件。](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)</span><span class="sxs-lookup"><span data-stu-id="9b646-148">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="9b646-149">管理 iOS 邮件应用用户是否可以查看受 Office 365 邮件加密保护的邮件</span><span class="sxs-lookup"><span data-stu-id="9b646-149">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="9b646-150">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，然后启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9b646-150">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9b646-151">有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="9b646-151">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9b646-152">使用"允许RMS 支持未启迪应用"参数运行"设置活动同步组织 cmdlet"：</span><span class="sxs-lookup"><span data-stu-id="9b646-152">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="9b646-153">例如，要将服务配置为在邮件发送到未开明的应用（如 iOS 邮件应用）之前解密邮件：</span><span class="sxs-lookup"><span data-stu-id="9b646-153">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="9b646-154">或者，要将服务配置为不向未启用的应用发送解密消息：</span><span class="sxs-lookup"><span data-stu-id="9b646-154">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="9b646-155">单个邮箱策略 （OWA/ActiveSync） 将覆盖这些设置（即，如果 -IRMEnabled 在相应的 OWA 邮箱策略或 ActiveSync 邮箱策略中设置为 False，则这些配置将不适用）。</span><span class="sxs-lookup"><span data-stu-id="9b646-155">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="9b646-156">为 Web 浏览器邮件客户端启用服务端解密电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="9b646-156">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="9b646-157">通常，当您使用 Office 365 邮件加密时，附件会自动加密。</span><span class="sxs-lookup"><span data-stu-id="9b646-157">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="9b646-158">作为 Office 365 管理员，您可以对用户从 Web 浏览器下载的电子邮件附件应用服务端解密。</span><span class="sxs-lookup"><span data-stu-id="9b646-158">As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="9b646-159">使用服务端解密时，服务会向设备发送文件的解密副本。</span><span class="sxs-lookup"><span data-stu-id="9b646-159">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="9b646-160">邮件仍加密。</span><span class="sxs-lookup"><span data-stu-id="9b646-160">The message is still encrypted.</span></span> <span data-ttu-id="9b646-161">即使浏览器不将客户端使用权限应用于用户，电子邮件附件也会保留有关使用权限的信息。</span><span class="sxs-lookup"><span data-stu-id="9b646-161">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="9b646-162">用户可以复制或打印电子邮件附件，即使他们最初没有这样做的权限。</span><span class="sxs-lookup"><span data-stu-id="9b646-162">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="9b646-163">但是，如果用户尝试完成需要 Office 365 邮件服务器的操作（如转发附件），则如果用户最初没有执行此操作的权限，则服务器将不允许执行该操作。</span><span class="sxs-lookup"><span data-stu-id="9b646-163">However, if the user tries to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="9b646-164">无论您是否设置了服务端附件解密，用户都无法在 iOS 邮件应用中查看加密邮件和受权限保护邮件的任何附件。</span><span class="sxs-lookup"><span data-stu-id="9b646-164">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="9b646-165">如果选择不允许解密的电子邮件附件（默认设置），则用户会收到一条消息，指出他们无权查看附件。</span><span class="sxs-lookup"><span data-stu-id="9b646-165">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="9b646-166">有关 Office 365 如何使用"仅加密"选项实现电子邮件和电子邮件附件加密的详细信息，请参阅[电子邮件的"仅加密"选项。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="9b646-166">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="9b646-167">管理是否从 Web 浏览器下载时解密电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="9b646-167">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="9b646-168">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，然后启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9b646-168">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9b646-169">有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="9b646-169">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9b646-170">使用"解密附件从门户"参数运行 Set-IRM 配置 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9b646-170">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="9b646-171">例如，要将服务配置为在用户从 Web 浏览器下载电子邮件附件时解密这些附件：</span><span class="sxs-lookup"><span data-stu-id="9b646-171">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="9b646-172">要将服务配置为在下载时保留加密的电子邮件附件：</span><span class="sxs-lookup"><span data-stu-id="9b646-172">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a><span data-ttu-id="9b646-173">确保所有外部收件人使用 OME 门户读取加密邮件 – 仅限 Office 365 高级邮件加密</span><span class="sxs-lookup"><span data-stu-id="9b646-173">Ensure all external recipients use the OME Portal to read encrypted mail — Office 365 Advanced Message Encryption only</span></span>

<span data-ttu-id="9b646-174">如果您有 Office 365 高级邮件加密，则可以使用自定义品牌模板强制收件人接收包装邮件，指示他们在 OME 门户中读取加密电子邮件，而不是在 Web 上使用 Outlook 或 Outlook。</span><span class="sxs-lookup"><span data-stu-id="9b646-174">If you have Office 365 Advanced Message Encryption, you can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="9b646-175">如果您使用该控件希望更好地控制收件人使用他们收到的邮件的方式，则可能需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9b646-175">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="9b646-176">例如，如果外部收件人在 Web 门户中查看电子邮件，则可以为电子邮件设置到期日期，也可以撤消该电子邮件。</span><span class="sxs-lookup"><span data-stu-id="9b646-176">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="9b646-177">这些功能仅通过 OME 门户支持。</span><span class="sxs-lookup"><span data-stu-id="9b646-177">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="9b646-178">创建邮件流规则时，可以使用"加密"选项和"不转发"选项。</span><span class="sxs-lookup"><span data-stu-id="9b646-178">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a><span data-ttu-id="9b646-179">创建自定义模板以强制所有外部收件人使用 OME 门户，并确保加密电子邮件可撤销并在 7 天后过期</span><span class="sxs-lookup"><span data-stu-id="9b646-179">Create a custom template to force all external recipients to use the OME Portal and for encrypted email to be revocable and expire in 7 days</span></span>

1. <span data-ttu-id="9b646-180">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，然后启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9b646-180">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9b646-181">有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="9b646-181">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9b646-182">运行新 OME 配置 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9b646-182">Run the New-OMEConfiguration cmdlet:</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   <span data-ttu-id="9b646-183">要`template name`用于 Office 365 邮件加密自定义品牌模板的名称。</span><span class="sxs-lookup"><span data-stu-id="9b646-183">where `template name` is the name you want to use for the Office 365 Message Encryption custom branding template.</span></span> <span data-ttu-id="9b646-184">For example,</span><span class="sxs-lookup"><span data-stu-id="9b646-184">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. <span data-ttu-id="9b646-185">运行新传输规则 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9b646-185">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="9b646-186">其中：</span><span class="sxs-lookup"><span data-stu-id="9b646-186">where:</span></span>

   - <span data-ttu-id="9b646-187">`mail flow rule name`是要用于新邮件流规则的名称。</span><span class="sxs-lookup"><span data-stu-id="9b646-187">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="9b646-188">`option name`或`Encrypt`。 `Do Not Forward`</span><span class="sxs-lookup"><span data-stu-id="9b646-188">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="9b646-189">`template name`是您为自定义品牌模板提供的名称，例如`One week expiration`。</span><span class="sxs-lookup"><span data-stu-id="9b646-189">`template name` is the name you gave the custom branding template, for example `One week expiration`.</span></span>

   <span data-ttu-id="9b646-190">要使用"一周过期"模板加密所有外部电子邮件，并应用"仅加密"选项：</span><span class="sxs-lookup"><span data-stu-id="9b646-190">To encrypt all external email with the "One week expiration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   <span data-ttu-id="9b646-191">要使用"一周过期"模板加密所有外部电子邮件，并应用"不转发"选项：</span><span class="sxs-lookup"><span data-stu-id="9b646-191">To encrypt all external email with the "One week expiration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="9b646-192">自定义电子邮件和 OME 门户的外观</span><span class="sxs-lookup"><span data-stu-id="9b646-192">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="9b646-193">有关如何为组织自定义 OME 的详细信息，请参阅[将组织的品牌添加到加密邮件](add-your-organization-brand-to-encrypted-messages.md)中。</span><span class="sxs-lookup"><span data-stu-id="9b646-193">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="9b646-194">禁用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="9b646-194">Disable the new capabilities for OME</span></span>

<span data-ttu-id="9b646-195">我们希望它不会实现它，但如果需要，禁用 OME 的新功能非常简单。</span><span class="sxs-lookup"><span data-stu-id="9b646-195">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="9b646-196">首先，您需要删除已创建的任何使用新的 OME 功能的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="9b646-196">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="9b646-197">有关删除邮件流规则的信息，请参阅[管理邮件流规则](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9b646-197">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="9b646-198">然后，在 Exchange 在线电源外壳中完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="9b646-198">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="9b646-199">禁用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="9b646-199">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="9b646-200">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="9b646-200">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="9b646-201">有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="9b646-201">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="9b646-202">如果在 Web 上的 Outlook 中启用**了"加密"** 按钮，请禁用该按钮，使用"简化客户端访问启用"参数运行 Set-IRM 配置 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9b646-202">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="9b646-203">否则，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="9b646-203">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="9b646-204">禁用 OME 的新功能，使用设置为 false 的 AzureRMS 许可启用参数运行 Set-IRM 配置 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9b646-204">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
