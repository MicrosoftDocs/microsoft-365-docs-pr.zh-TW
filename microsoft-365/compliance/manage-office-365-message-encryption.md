---
title: 管理 Office 365 郵件加密
f1.keywords:
- NOCSH
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
description: 當您完成設定 Office 365 郵件加密（OME）後，您可以採用多種方式自訂部署的設定。 例如，您可以設定是否要啟用一次性傳送碼，在 Outlook 網頁版中顯示 [保護] 按鈕，等等。 本文中的工作會說明如何進行這項作業。
ms.openlocfilehash: c235205535b4871deb1963a9113a82429917b75e
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634341"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="269c0-105">管理 Office 365 郵件加密</span><span class="sxs-lookup"><span data-stu-id="269c0-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="269c0-106">當您完成設定 Office 365 郵件加密（OME）後，您可以採用多種方式自訂部署的設定。</span><span class="sxs-lookup"><span data-stu-id="269c0-106">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="269c0-107">例如，您可以設定是否要啟用一次性傳送碼，在 Outlook 網頁版中顯示 [**加密**] 按鈕，等等。</span><span class="sxs-lookup"><span data-stu-id="269c0-107">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="269c0-108">本文中的工作會說明如何進行這項作業。</span><span class="sxs-lookup"><span data-stu-id="269c0-108">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="269c0-109">管理 Google、Yahoo 和 Microsoft 帳戶收件者是否可以使用這些帳戶登入 Office 365 郵件加密入口網站</span><span class="sxs-lookup"><span data-stu-id="269c0-109">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="269c0-110">當您設定新的 Office 365 郵件加密功能時，您組織中的使用者可以傳送郵件給您的 Office 365 組織外的收件者。</span><span class="sxs-lookup"><span data-stu-id="269c0-110">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization.</span></span> <span data-ttu-id="269c0-111">如果收件者使用的*社交識別碼*，例如 Google Account、Yahoo 帳戶或 Microsoft 帳戶，收件者便可使用社交識別碼登入 OME 入口網站。</span><span class="sxs-lookup"><span data-stu-id="269c0-111">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="269c0-112">如有需要，您可以選擇不允許收件者使用社交 IDs 登入 OME 入口網站。</span><span class="sxs-lookup"><span data-stu-id="269c0-112">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="269c0-113">管理收件者是否可以使用社交 IDs 登入 OME 入口網站</span><span class="sxs-lookup"><span data-stu-id="269c0-113">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="269c0-114">[使用遠端 PowerShell 連接至 Exchange Online](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="269c0-114">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="269c0-115">使用 SocialIdSignIn 參數執行 Set-OMEConfiguration Cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="269c0-115">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="269c0-116">例如，若要停用社交 IDs：</span><span class="sxs-lookup"><span data-stu-id="269c0-116">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="269c0-117">啟用社交 IDs：</span><span class="sxs-lookup"><span data-stu-id="269c0-117">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="269c0-118">管理 Office 365 郵件加密入口網站的一次性傳送碼使用</span><span class="sxs-lookup"><span data-stu-id="269c0-118">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="269c0-119">如果由 OME 加密之郵件的收件者不會使用 Outlook，不論收件者使用的帳戶為何，收件者都會收到限制時間的 web view 連結，讓他們可以讀取郵件。</span><span class="sxs-lookup"><span data-stu-id="269c0-119">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="269c0-120">此連結包含一次的傳遞碼。</span><span class="sxs-lookup"><span data-stu-id="269c0-120">This link includes a one-time pass code.</span></span> <span data-ttu-id="269c0-121">以系統管理員的身分，您可以決定收件者是否可以使用一次性傳送碼登入 OME 入口網站。</span><span class="sxs-lookup"><span data-stu-id="269c0-121">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="269c0-122">若要管理 OME 是否會產生一次的傳遞碼</span><span class="sxs-lookup"><span data-stu-id="269c0-122">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="269c0-123">使用 Office 365 組織中具有全域系統管理員許可權的工作或學校帳戶，並啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="269c0-123">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="269c0-124">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="269c0-124">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="269c0-125">使用 OTPEnabled 參數執行 Set-OMEConfiguration Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="269c0-125">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="269c0-126">例如，若要停用一次性處理常式代碼：</span><span class="sxs-lookup"><span data-stu-id="269c0-126">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="269c0-127">啟用一次性處理常式代碼：</span><span class="sxs-lookup"><span data-stu-id="269c0-127">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="269c0-128">管理網頁版 Outlook 中的 [加密] 按鈕的顯示</span><span class="sxs-lookup"><span data-stu-id="269c0-128">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="269c0-129">您可以以系統管理員的身分，管理是否要將此按鈕顯示給使用者。</span><span class="sxs-lookup"><span data-stu-id="269c0-129">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="269c0-130">若要管理 [加密] 按鈕是否顯示于網頁上的 Outlook</span><span class="sxs-lookup"><span data-stu-id="269c0-130">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="269c0-131">使用 Office 365 組織中具有全域系統管理員許可權的工作或學校帳戶，並啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="269c0-131">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="269c0-132">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="269c0-132">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="269c0-133">使用-SimplifiedClientAccessEnabled 參數執行 Set-IRMConfiguration Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="269c0-133">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="269c0-134">例如，若要停用 [**加密**] 按鈕：</span><span class="sxs-lookup"><span data-stu-id="269c0-134">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="269c0-135">啟用 [**加密**] 按鈕：</span><span class="sxs-lookup"><span data-stu-id="269c0-135">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="269c0-136">為 iOS 郵件 app 使用者啟用電子郵件的服務端解密</span><span class="sxs-lookup"><span data-stu-id="269c0-136">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="269c0-137">IOS 的郵件應用程式無法解密使用 Office 365 郵件加密保護的郵件。</span><span class="sxs-lookup"><span data-stu-id="269c0-137">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="269c0-138">做為 Office 365 系統管理員，您可以對傳送至 iOS 郵件應用程式的郵件套用服務端解密。</span><span class="sxs-lookup"><span data-stu-id="269c0-138">As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="269c0-139">當您選擇使用服務端解密時，服務會將郵件的解密複本傳送至 iOS 裝置。</span><span class="sxs-lookup"><span data-stu-id="269c0-139">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="269c0-140">用戶端裝置會儲存郵件的解密複本。</span><span class="sxs-lookup"><span data-stu-id="269c0-140">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="269c0-141">即使 iOS 的郵件應用程式不會對使用者套用用戶端使用許可權，郵件也會保留使用權利的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="269c0-141">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="269c0-142">使用者可以複製或列印郵件，即使他們最初並未具有這麼做的權力。</span><span class="sxs-lookup"><span data-stu-id="269c0-142">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="269c0-143">不過，如果使用者嘗試完成需要 Office 365 郵件伺服器的動作（例如轉寄郵件），如果使用者原來未使用此方法，則伺服器將不會允許執行該動作。</span><span class="sxs-lookup"><span data-stu-id="269c0-143">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="269c0-144">不過，使用者可以從 iOS 郵件應用程式內的不同帳戶轉送郵件，以解決「不要轉寄」使用限制。</span><span class="sxs-lookup"><span data-stu-id="269c0-144">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="269c0-145">不論您是否設定郵件的服務端解密，加密和受版權保護的郵件附件都無法在 iOS 郵件應用程式中查看。</span><span class="sxs-lookup"><span data-stu-id="269c0-145">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="269c0-146">如果您選擇 [不允許將解密的郵件傳送至 iOS 郵件 app 使用者]，使用者會收到訊息，指出他們沒有查看郵件的許可權。</span><span class="sxs-lookup"><span data-stu-id="269c0-146">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="269c0-147">根據預設，不會啟用電子郵件的服務端解密。</span><span class="sxs-lookup"><span data-stu-id="269c0-147">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="269c0-148">如需詳細資訊，以及用戶端經驗的觀點，請參閱[在 iPhone 或 iPad 上查看加密的郵件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)。</span><span class="sxs-lookup"><span data-stu-id="269c0-148">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="269c0-149">若要管理 iOS 郵件應用程式使用者是否可以查看 Office 365 郵件加密所保護的郵件</span><span class="sxs-lookup"><span data-stu-id="269c0-149">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="269c0-150">使用 Office 365 組織中具有全域系統管理員許可權的工作或學校帳戶，並啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="269c0-150">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="269c0-151">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="269c0-151">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="269c0-152">使用 AllowRMSSupportForUnenlightenedApps 參數執行 ActiveSyncOrganizations Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="269c0-152">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="269c0-153">例如，若要設定服務，在將郵件傳送至 unenlightened 應用程式（如 iOS 的郵件應用程式）之前，解密郵件：</span><span class="sxs-lookup"><span data-stu-id="269c0-153">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="269c0-154">或者，若要設定服務不要將解密的郵件傳送至 unenlightened 應用程式：</span><span class="sxs-lookup"><span data-stu-id="269c0-154">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="269c0-155">個別信箱原則（OWA/ActiveSync）覆寫這些設定（例如，IRMEnabled 如果在各自的 OWA 信箱原則中設定為 False，或 ActiveSync 信箱原則，則不會套用這些設定）。</span><span class="sxs-lookup"><span data-stu-id="269c0-155">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="269c0-156">啟用 web 瀏覽器郵件用戶端的電子郵件附件的服務端解密</span><span class="sxs-lookup"><span data-stu-id="269c0-156">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="269c0-157">在一般情況下，當您使用 Office 365 郵件加密時，會自動加密附件。</span><span class="sxs-lookup"><span data-stu-id="269c0-157">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="269c0-158">做為 Office 365 系統管理員，您可以對使用者從網頁瀏覽器下載的電子郵件附件套用服務端解密。</span><span class="sxs-lookup"><span data-stu-id="269c0-158">As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="269c0-159">當您使用服務端解密時，服務會將檔的解密複本傳送至裝置。</span><span class="sxs-lookup"><span data-stu-id="269c0-159">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="269c0-160">郵件仍加密。</span><span class="sxs-lookup"><span data-stu-id="269c0-160">The message is still encrypted.</span></span> <span data-ttu-id="269c0-161">電子郵件附件也會保留使用權利的相關資訊，即使瀏覽器並未對使用者套用用戶端使用許可權。</span><span class="sxs-lookup"><span data-stu-id="269c0-161">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="269c0-162">使用者可以複製或列印電子郵件附件，即使他們最初並未具有這麼做的權力。</span><span class="sxs-lookup"><span data-stu-id="269c0-162">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="269c0-163">不過，如果使用者嘗試完成需要 Office 365 郵件伺服器的動作（例如轉寄附件），如果使用者原來未使用此方法，則伺服器不會允許執行動作。</span><span class="sxs-lookup"><span data-stu-id="269c0-163">However, if the user tries to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="269c0-164">不論是否設定附件的服務端解密，使用者都無法在 iOS 郵件應用程式中查看加密和受版權保護之郵件的任何附件。</span><span class="sxs-lookup"><span data-stu-id="269c0-164">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="269c0-165">如果您選擇不允許解密的電子郵件附件，也就是預設值，使用者會收到訊息，指出他們沒有查看附件的許可權。</span><span class="sxs-lookup"><span data-stu-id="269c0-165">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="269c0-166">如需 Office 365 如何使用僅限「加密」選項對電子郵件和電子郵件附件進行加密的詳細資訊，請參閱[email 的唯讀選項。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="269c0-166">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="269c0-167">管理從網頁瀏覽器下載電子郵件附件是否解密</span><span class="sxs-lookup"><span data-stu-id="269c0-167">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="269c0-168">使用 Office 365 組織中具有全域系統管理員許可權的工作或學校帳戶，並啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="269c0-168">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="269c0-169">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="269c0-169">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="269c0-170">使用 DecryptAttachmentForEncryptOnly 參數執行 Set-IRMConfiguration Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="269c0-170">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="269c0-171">例如，若要設定在使用者從網頁瀏覽器下載時，解密電子郵件附件的服務：</span><span class="sxs-lookup"><span data-stu-id="269c0-171">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="269c0-172">若要設定服務在下載時保留加密的電子郵件附件：</span><span class="sxs-lookup"><span data-stu-id="269c0-172">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="269c0-173">確定所有外部收件者都使用 OME 入口網站來讀取加密的郵件</span><span class="sxs-lookup"><span data-stu-id="269c0-173">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="269c0-174">您可以使用自訂品牌範本，強制收件者收到可在 OME 入口網站中讀取加密電子郵件的包裝郵件，而不是使用 Outlook 或 web 上的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="269c0-174">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="269c0-175">如果您想要更進一步控制收件者如何使用其所收到的郵件，您可能想要這麼做。</span><span class="sxs-lookup"><span data-stu-id="269c0-175">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="269c0-176">例如，如果外部收件者查看網頁入口網站中的電子郵件，您可以設定電子郵件的到期日，也可以撤銷電子郵件。</span><span class="sxs-lookup"><span data-stu-id="269c0-176">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="269c0-177">只有透過 OME 入口網站支援這些功能。</span><span class="sxs-lookup"><span data-stu-id="269c0-177">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="269c0-178">您可以在建立郵件流程規則時，使用 [加密] 選項和 [不要轉寄] 選項。</span><span class="sxs-lookup"><span data-stu-id="269c0-178">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="269c0-179">使用自訂範本強制所有外部收件者都使用 OME 入口網站和加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="269c0-179">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="269c0-180">使用 Office 365 組織中具有全域系統管理員許可權的工作或學校帳戶，並啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="269c0-180">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="269c0-181">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="269c0-181">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="269c0-182">執行 New-TransportRule Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="269c0-182">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="269c0-183">其中：</span><span class="sxs-lookup"><span data-stu-id="269c0-183">where:</span></span>

   - <span data-ttu-id="269c0-184">`mail flow rule name`是您要用於新郵件流程規則的名稱。</span><span class="sxs-lookup"><span data-stu-id="269c0-184">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="269c0-185">`option name`可以`Encrypt`是或`Do Not Forward`。</span><span class="sxs-lookup"><span data-stu-id="269c0-185">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="269c0-186">`template name`是您為自訂商標範本所提供的名稱， `OME Configuration`例如。</span><span class="sxs-lookup"><span data-stu-id="269c0-186">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="269c0-187">若要使用「「OME 設定」範本加密所有外部電子郵件，並套用 [僅限加密] 選項：</span><span class="sxs-lookup"><span data-stu-id="269c0-187">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="269c0-188">若要使用「「OME 設定」範本加密所有外部電子郵件，並套用 [不要轉寄] 選項：</span><span class="sxs-lookup"><span data-stu-id="269c0-188">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="269c0-189">自訂電子郵件和 OME 入口網站的外觀</span><span class="sxs-lookup"><span data-stu-id="269c0-189">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="269c0-190">如需如何為組織自訂 OME 的詳細資訊，請參閱[將組織的品牌新增至加密的郵件](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="269c0-190">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="269c0-191">停用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="269c0-191">Disable the new capabilities for OME</span></span>

<span data-ttu-id="269c0-192">建議您不要這樣做，但是如果您需要，停用 OME 的新功能會非常直接。</span><span class="sxs-lookup"><span data-stu-id="269c0-192">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="269c0-193">首先，您必須移除您已建立的任何郵件流程規則，以使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="269c0-193">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="269c0-194">如需移除郵件流程規則的相關資訊，請參閱[管理郵件流程規則](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="269c0-194">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="269c0-195">然後，在 Exchange Online PowerShell 中完成這些步驟。</span><span class="sxs-lookup"><span data-stu-id="269c0-195">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="269c0-196">停用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="269c0-196">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="269c0-197">在您的 Office 365 組織中使用具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="269c0-197">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="269c0-198">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="269c0-198">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="269c0-199">如果您已在網頁上的 Outlook 中啟用 [**加密**] 按鈕，請使用 SimplifiedClientAccessEnabled 參數執行 Set-IRMConfiguration Cmdlet 以將其停用。</span><span class="sxs-lookup"><span data-stu-id="269c0-199">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="269c0-200">否則，請略過此步驟。</span><span class="sxs-lookup"><span data-stu-id="269c0-200">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="269c0-201">在 AzureRMSLicensingEnabled 參數設為 false 的情況執行 Set-IRMConfiguration Cmdlet，以停用 OME 的新功能：</span><span class="sxs-lookup"><span data-stu-id="269c0-201">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
