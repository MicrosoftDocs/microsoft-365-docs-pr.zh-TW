---
title: 將您的組織品牌新增至加密郵件
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 瞭解 Office 365 全域管理員如何將組織的署名套用至加密的電子郵件 & 加密入口網站的內容。
ms.openlocfilehash: 95320e9f268f19cedd993efe4fa0e68fd75af125
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430729"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="97d9e-103">將貴組織的品牌新增至您的商務用郵件加密加密郵件 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="97d9e-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="97d9e-104">您可以套用公司品牌，以自訂群組織的電子郵件訊息和加密入口網站的外觀。</span><span class="sxs-lookup"><span data-stu-id="97d9e-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="97d9e-105">您必須先對您的公司或學校帳戶套用全域系統管理員許可權，才可開始使用。</span><span class="sxs-lookup"><span data-stu-id="97d9e-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="97d9e-106">一旦您具有這些許可權，請使用 Get-OMEConfiguration 和 Set-OMEConfiguration Windows PowerShell Cmdlet，以自訂加密電子郵件的這些部分：</span><span class="sxs-lookup"><span data-stu-id="97d9e-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="97d9e-107">簡介文字</span><span class="sxs-lookup"><span data-stu-id="97d9e-107">Introductory text</span></span>

- <span data-ttu-id="97d9e-108">免責聲明文字</span><span class="sxs-lookup"><span data-stu-id="97d9e-108">Disclaimer text</span></span>

- <span data-ttu-id="97d9e-109">組織之隱私權聲明的 URL</span><span class="sxs-lookup"><span data-stu-id="97d9e-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="97d9e-110">OME 入口網站中的文字</span><span class="sxs-lookup"><span data-stu-id="97d9e-110">Text in the OME portal</span></span>

- <span data-ttu-id="97d9e-111">出現在電子郵件和 OME 入口網站中的標誌，或是否要使用標誌</span><span class="sxs-lookup"><span data-stu-id="97d9e-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="97d9e-112">電子郵件訊息和 OME 入口網站中的背景色彩</span><span class="sxs-lookup"><span data-stu-id="97d9e-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="97d9e-113">您也可以隨時回復為預設的外觀與風格。</span><span class="sxs-lookup"><span data-stu-id="97d9e-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="97d9e-114">如果您想要更多控制，請使用 Office 365 進階郵件加密來建立多個範本，以供來自組織的加密電子郵件使用。</span><span class="sxs-lookup"><span data-stu-id="97d9e-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="97d9e-115">使用這些範本來控制使用者經驗的各個部分。</span><span class="sxs-lookup"><span data-stu-id="97d9e-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="97d9e-116">例如，指定收件者是否可以使用 Google、Yahoo 和 Microsoft 帳戶登入加密入口網站。</span><span class="sxs-lookup"><span data-stu-id="97d9e-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="97d9e-117">使用範本來滿足數個使用案例，例如：</span><span class="sxs-lookup"><span data-stu-id="97d9e-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="97d9e-118">個別部門，例如財務、銷售等等。</span><span class="sxs-lookup"><span data-stu-id="97d9e-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="97d9e-119">不同的產品</span><span class="sxs-lookup"><span data-stu-id="97d9e-119">Different products</span></span>

- <span data-ttu-id="97d9e-120">不同的地理區域或國家</span><span class="sxs-lookup"><span data-stu-id="97d9e-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="97d9e-121">您是否要允許吊銷電子郵件</span><span class="sxs-lookup"><span data-stu-id="97d9e-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="97d9e-122">您是否想要傳送給外部收件者的電子郵件在指定的天數後到期。</span><span class="sxs-lookup"><span data-stu-id="97d9e-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="97d9e-123">當您建立範本之後，您可以使用 Exchange 郵件流程規則，將其套用至加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="97d9e-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="97d9e-124">如果您有 Office 365 進階郵件加密，您可以使用這些範本撤銷所有已標記的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="97d9e-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="97d9e-125">使用 OME 品牌範本</span><span class="sxs-lookup"><span data-stu-id="97d9e-125">Work with OME branding templates</span></span>

<span data-ttu-id="97d9e-126">您可以在品牌範本中修改數項功能。</span><span class="sxs-lookup"><span data-stu-id="97d9e-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="97d9e-127">您可以修改預設範本，但不要移除。</span><span class="sxs-lookup"><span data-stu-id="97d9e-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="97d9e-128">如果您有高級郵件加密，您也可以建立、修改及移除自訂範本。</span><span class="sxs-lookup"><span data-stu-id="97d9e-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="97d9e-129">使用 Windows PowerShell 一次可搭配一個署名範本。</span><span class="sxs-lookup"><span data-stu-id="97d9e-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="97d9e-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) -修改預設的署名範本或您建立的自訂商標範本。</span><span class="sxs-lookup"><span data-stu-id="97d9e-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="97d9e-131">[Set-omeconfiguration](/powershell/module/exchange/new-omeconfiguration) -建立新的署名範本，僅限高級郵件加密。</span><span class="sxs-lookup"><span data-stu-id="97d9e-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="97d9e-132">[Set-omeconfiguration](/powershell/module/exchange/remove-omeconfiguration) -移除自訂品牌範本，僅限高級郵件加密。</span><span class="sxs-lookup"><span data-stu-id="97d9e-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="97d9e-133">您無法刪除預設的署名範本。</span><span class="sxs-lookup"><span data-stu-id="97d9e-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="97d9e-134">修改 OME 署名範本</span><span class="sxs-lookup"><span data-stu-id="97d9e-134">Modify an OME branding template</span></span>

<span data-ttu-id="97d9e-135">使用 Windows PowerShell 一次修改一個署名範本。</span><span class="sxs-lookup"><span data-stu-id="97d9e-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="97d9e-136">如果您有高級郵件加密，您也可以建立、修改及移除自訂範本。</span><span class="sxs-lookup"><span data-stu-id="97d9e-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="97d9e-137">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並連接至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="97d9e-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="97d9e-138">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="97d9e-138">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="97d9e-139">使用 [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) 所述的 Set-OMEConfiguration 指令程式，或使用下圖及表格以取得指導方針。</span><span class="sxs-lookup"><span data-stu-id="97d9e-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![可自訂的電子郵件元件](../media/ome-template-breakout.png)

|<span data-ttu-id="97d9e-141">**若要自訂此加密經驗功能**</span><span class="sxs-lookup"><span data-stu-id="97d9e-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="97d9e-142">**使用這些命令**</span><span class="sxs-lookup"><span data-stu-id="97d9e-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="97d9e-143">背景色彩</span><span class="sxs-lookup"><span data-stu-id="97d9e-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="97d9e-144">**範例：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="97d9e-145">如需背景色彩的詳細資訊，請參閱本文稍後的 [ [背景色彩](#background-color-reference) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="97d9e-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="97d9e-146">標誌</span><span class="sxs-lookup"><span data-stu-id="97d9e-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="97d9e-147">**範例：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="97d9e-148">支援的檔案格式：.png、.jpg、.bmp 或 .tiff</span><span class="sxs-lookup"><span data-stu-id="97d9e-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="97d9e-149">標誌檔案的最佳大小：小於 40 KB</span><span class="sxs-lookup"><span data-stu-id="97d9e-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="97d9e-150">標誌影像的最佳大小：170x70 圖元。</span><span class="sxs-lookup"><span data-stu-id="97d9e-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="97d9e-151">如果您的影像超過這些尺寸，服務會重新調整您的徽標以在入口網站中顯示。</span><span class="sxs-lookup"><span data-stu-id="97d9e-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="97d9e-152">服務不會修改圖形檔案本身。</span><span class="sxs-lookup"><span data-stu-id="97d9e-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="97d9e-153">為了獲得最佳結果，請使用最佳大小。</span><span class="sxs-lookup"><span data-stu-id="97d9e-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="97d9e-154">寄件者名稱和電子郵件地址旁的文字</span><span class="sxs-lookup"><span data-stu-id="97d9e-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="97d9e-155">**範例：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="97d9e-156">出現在「讀取訊息」按鈕上的文字</span><span class="sxs-lookup"><span data-stu-id="97d9e-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="97d9e-157">**範例：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="97d9e-158">出現在 [閱讀郵件] 按鈕下方的文字</span><span class="sxs-lookup"><span data-stu-id="97d9e-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="97d9e-159">**範例：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="97d9e-160">隱私權聲明連結的 URL</span><span class="sxs-lookup"><span data-stu-id="97d9e-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="97d9e-161">**範例：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="97d9e-162">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="97d9e-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="97d9e-163">**範例：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="97d9e-164">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="97d9e-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="97d9e-165">**範例：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="97d9e-166">啟用或停用此自訂範本的一次性程式碼驗證</span><span class="sxs-lookup"><span data-stu-id="97d9e-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="97d9e-167">**範例：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-167">**Examples:**</span></span> <br/><span data-ttu-id="97d9e-168">針對此自訂範本啟用一次 passcodes</span><span class="sxs-lookup"><span data-stu-id="97d9e-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="97d9e-169">針對此自訂範本停用一次 passcodes</span><span class="sxs-lookup"><span data-stu-id="97d9e-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="97d9e-170">啟用或停用此自訂範本的 Microsoft、Google 或 Yahoo 識別碼驗證</span><span class="sxs-lookup"><span data-stu-id="97d9e-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="97d9e-171">**範例：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-171">**Examples:**</span></span> <br/><span data-ttu-id="97d9e-172">啟用此自訂範本的社交 IDs</span><span class="sxs-lookup"><span data-stu-id="97d9e-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="97d9e-173">停用此自訂範本的社交 IDs</span><span class="sxs-lookup"><span data-stu-id="97d9e-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="97d9e-174"> (高級郵件加密建立 OME 署名範本) </span><span class="sxs-lookup"><span data-stu-id="97d9e-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="97d9e-175">如果您有 Office 365 進階郵件加密，您可以使用[set-omeconfiguration](/powershell/module/exchange/new-omeconfiguration) Cmdlet 為組織建立自訂商標範本。</span><span class="sxs-lookup"><span data-stu-id="97d9e-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="97d9e-176">建立範本之後，您可以使用 Set-OMEConfiguration Cmdlet 修改範本，如 [modify a OME 署名範本](#modify-an-ome-branding-template)所述。</span><span class="sxs-lookup"><span data-stu-id="97d9e-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="97d9e-177">您可以建立多個範本。</span><span class="sxs-lookup"><span data-stu-id="97d9e-177">You can create multiple templates.</span></span>

<span data-ttu-id="97d9e-178">若要建立新的自訂品牌範本：</span><span class="sxs-lookup"><span data-stu-id="97d9e-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="97d9e-179">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並連接至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="97d9e-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="97d9e-180">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="97d9e-180">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="97d9e-181">使用 [set-omeconfiguration](/powershell/module/exchange/new-omeconfiguration) Cmdlet 來建立新的範本。</span><span class="sxs-lookup"><span data-stu-id="97d9e-181">Use the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="97d9e-182">例如：</span><span class="sxs-lookup"><span data-stu-id="97d9e-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="97d9e-183">將預設署名範本傳回其原始值</span><span class="sxs-lookup"><span data-stu-id="97d9e-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="97d9e-184">若要從預設範本移除所有修改（包括品牌自訂專案）等等，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="97d9e-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="97d9e-185">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並連接至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="97d9e-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="97d9e-186">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="97d9e-186">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="97d9e-187">使用 [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration)中所述的 **Set-OMEConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="97d9e-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="97d9e-188">若要從 DisclaimerText、EmailText 及 PortalText 值中移除組織的署名自訂，請將值設為空字串 `""` 。</span><span class="sxs-lookup"><span data-stu-id="97d9e-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="97d9e-189">針對所有影像值，例如 [標誌]，將值設為  `"$null"` 。</span><span class="sxs-lookup"><span data-stu-id="97d9e-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="97d9e-190">下表說明加密自訂選項的預設值。</span><span class="sxs-lookup"><span data-stu-id="97d9e-190">The following table describes the encryption customization option defaults.</span></span>

   |<span data-ttu-id="97d9e-191">將加密體驗的這項功能回復為預設文字和影像</span><span class="sxs-lookup"><span data-stu-id="97d9e-191">To revert this feature of the encryption experience back to the default text and image</span></span>|<span data-ttu-id="97d9e-192">使用這些命令</span><span class="sxs-lookup"><span data-stu-id="97d9e-192">Use these commands</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="97d9e-193">附帶加密電子郵件的預設文字。</span><span class="sxs-lookup"><span data-stu-id="97d9e-193">Default text that comes with encrypted email messages.</span></span>  <span data-ttu-id="97d9e-194">預設文字會出現在檢視加密郵件的指示上方。</span><span class="sxs-lookup"><span data-stu-id="97d9e-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="97d9e-195">**範例：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="97d9e-196">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="97d9e-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="97d9e-197">**範例：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="97d9e-198">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="97d9e-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="97d9e-199">**範例回復為預設值：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="97d9e-200">標誌</span><span class="sxs-lookup"><span data-stu-id="97d9e-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="97d9e-201">**範例回復為預設值：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="97d9e-202">背景色彩</span><span class="sxs-lookup"><span data-stu-id="97d9e-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="97d9e-203">**範例回復為預設值：**</span><span class="sxs-lookup"><span data-stu-id="97d9e-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="97d9e-204"> (高級郵件加密移除自訂商標範本) </span><span class="sxs-lookup"><span data-stu-id="97d9e-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="97d9e-205">您只可以移除或刪除您所做的品牌範本。</span><span class="sxs-lookup"><span data-stu-id="97d9e-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="97d9e-206">您無法移除預設的署名範本。</span><span class="sxs-lookup"><span data-stu-id="97d9e-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="97d9e-207">若要移除自訂商標範本：</span><span class="sxs-lookup"><span data-stu-id="97d9e-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="97d9e-208">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並連接至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="97d9e-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="97d9e-209">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="97d9e-209">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="97d9e-210">使用 **Remove-set-omeconfiguration 指令程式** ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="97d9e-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="97d9e-211">例如：</span><span class="sxs-lookup"><span data-stu-id="97d9e-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="97d9e-212">如需詳細資訊，請參閱 [Remove-set-omeconfiguration](/powershell/module/exchange/remove-omeconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="97d9e-212">For more information, see [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="97d9e-213">建立 Exchange 郵件流程規則，將自訂品牌套用至加密的電子郵件</span><span class="sxs-lookup"><span data-stu-id="97d9e-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97d9e-214">掃描及修改郵件的協力廠商應用程式，可防止 OME 署名正確套用。</span><span class="sxs-lookup"><span data-stu-id="97d9e-214">Third-party applications that scan and modify mail can prevent OME branding from being applied correctly.</span></span>

<span data-ttu-id="97d9e-215">修改預設範本或建立新的品牌範本之後，您可以建立 Exchange 郵件流程規則，以根據特定條件套用您的自訂品牌。</span><span class="sxs-lookup"><span data-stu-id="97d9e-215">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="97d9e-216">這類規則會在下列情況中套用自訂品牌：</span><span class="sxs-lookup"><span data-stu-id="97d9e-216">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="97d9e-217">如果使用者使用 Outlook 或 Outlook 網頁版手動加密電子郵件，則以前會 Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="97d9e-217">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="97d9e-218">如果電子郵件已由 Exchange 郵件流程規則或資料遺失防護原則自動加密</span><span class="sxs-lookup"><span data-stu-id="97d9e-218">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="97d9e-219">如需如何建立套用加密之 Exchange 郵件流程規則的詳細資訊，請參閱[定義郵件流程規則，以在 Office 365 中加密電子郵件](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="97d9e-219">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="97d9e-220">在網頁瀏覽器中，使用已被授與全域管理員許可權的公司或學校帳戶，登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="97d9e-220">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="97d9e-221">選擇 [ **管理** ] 磚。</span><span class="sxs-lookup"><span data-stu-id="97d9e-221">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="97d9e-222">在 Microsoft 365 系統管理中心中，選擇 [系統 **管理中心**] \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="97d9e-222">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="97d9e-223">在 EAC 中，移至 [ **郵件流程** \> **規則** ]，然後選取 [ **新增** 新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="97d9e-223">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="97d9e-224">如需使用 EAC 的詳細資訊，請參閱[Exchange Online 中 Exchange 系統管理中心](/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="97d9e-224">For more information about using the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="97d9e-225">在 [ **名稱**] 中，輸入規則的名稱，例如「銷售部門的商標」。</span><span class="sxs-lookup"><span data-stu-id="97d9e-225">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="97d9e-226">在 [套用 **此規則** 條件] 中，選取 **寄件者位於組織內部的** 條件，以及您在可用條件清單中所需的其他條件。</span><span class="sxs-lookup"><span data-stu-id="97d9e-226">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="97d9e-227">例如，您可能想要將特定的署名範本套用到：</span><span class="sxs-lookup"><span data-stu-id="97d9e-227">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="97d9e-228">從財務部門的成員傳送的所有加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="97d9e-228">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="97d9e-229">以特定關鍵字（如 "External" 或 "Partner"）傳送的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="97d9e-229">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="97d9e-230">傳送至特定網域的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="97d9e-230">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="97d9e-231">從 **執行下列** 動作，選取 **[修改郵件安全性** 套用 \> **自訂品牌] 以 OME 郵件**。</span><span class="sxs-lookup"><span data-stu-id="97d9e-231">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="97d9e-232">接下來，從下拉式清單中選取商標範本。</span><span class="sxs-lookup"><span data-stu-id="97d9e-232">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="97d9e-233"> (選用) 您可以設定郵件流程規則套用加密和自訂商標。</span><span class="sxs-lookup"><span data-stu-id="97d9e-233">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="97d9e-234">從 **執行下列** 動作，選取 **[修改郵件安全性**]，然後選擇 [套用 **Office 365 郵件加密和許可權保護**]。</span><span class="sxs-lookup"><span data-stu-id="97d9e-234">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="97d9e-235">從清單中選取 RMS 範本，然後選擇 [ **儲存**]，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="97d9e-235">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="97d9e-236">範本清單包含預設範本和選項，以及您建立的任何自訂範本。</span><span class="sxs-lookup"><span data-stu-id="97d9e-236">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="97d9e-237">如果清單是空的，請確定您已使用新功能設定 Office 365 郵件加密。</span><span class="sxs-lookup"><span data-stu-id="97d9e-237">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="97d9e-238">如需相關指示，請參閱[Set up new Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="97d9e-238">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="97d9e-239">如需預設範本的相關資訊，請參閱設定 [及管理 Azure 資訊保護的範本](/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="97d9e-239">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="97d9e-240">如需有關 [ **不要轉寄** ] 選項的詳細資訊，請參閱 [請勿轉寄選項的電子郵件](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="97d9e-240">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="97d9e-241">如需只供 **加密** 之選項的詳細資訊，請參閱 [僅限加密選項的電子郵件](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="97d9e-241">For information about the **encrypt only** option, see [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="97d9e-242">如果您想要指定另一個動作，請選擇 [ **新增動作** ]。</span><span class="sxs-lookup"><span data-stu-id="97d9e-242">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="97d9e-243">背景色彩參考</span><span class="sxs-lookup"><span data-stu-id="97d9e-243">Background color reference</span></span>

<span data-ttu-id="97d9e-244">您可以用於背景色彩的色彩名稱是有限的。</span><span class="sxs-lookup"><span data-stu-id="97d9e-244">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="97d9e-245">您可以使用十六進位代碼值 (#RRGGBB) ，而不是使用色彩名稱。</span><span class="sxs-lookup"><span data-stu-id="97d9e-245">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="97d9e-246">您可以使用對應于色彩名稱的十六進位代碼值，也可以使用自訂的十六進位代碼值。</span><span class="sxs-lookup"><span data-stu-id="97d9e-246">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="97d9e-247">請務必以引號括住十六進位代碼值 (例如， `"#f0f8ff"`) 。</span><span class="sxs-lookup"><span data-stu-id="97d9e-247">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="97d9e-248">下表說明可用的背景色彩名稱及其對應的十六進位代碼值。</span><span class="sxs-lookup"><span data-stu-id="97d9e-248">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="97d9e-249">**色彩名稱**</span><span class="sxs-lookup"><span data-stu-id="97d9e-249">**Color name**</span></span>|<span data-ttu-id="97d9e-250">**色彩代碼**</span><span class="sxs-lookup"><span data-stu-id="97d9e-250">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="97d9e-251">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="97d9e-251">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="97d9e-252">#faebd7</span><span class="sxs-lookup"><span data-stu-id="97d9e-252">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="97d9e-253">#00ffff</span><span class="sxs-lookup"><span data-stu-id="97d9e-253">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="97d9e-254">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="97d9e-254">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="97d9e-255">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="97d9e-255">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="97d9e-256">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="97d9e-256">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="97d9e-257">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="97d9e-257">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="97d9e-258">#000000</span><span class="sxs-lookup"><span data-stu-id="97d9e-258">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="97d9e-259">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="97d9e-259">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="97d9e-260">#0000ff</span><span class="sxs-lookup"><span data-stu-id="97d9e-260">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="97d9e-261">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="97d9e-261">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="97d9e-262">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="97d9e-262">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="97d9e-263">#deb887</span><span class="sxs-lookup"><span data-stu-id="97d9e-263">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="97d9e-264">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="97d9e-264">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="97d9e-265">#7fff00</span><span class="sxs-lookup"><span data-stu-id="97d9e-265">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="97d9e-266">#d2691e</span><span class="sxs-lookup"><span data-stu-id="97d9e-266">#d2691e</span></span>|
|`coral`|<span data-ttu-id="97d9e-267">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="97d9e-267">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="97d9e-268">#6495ed</span><span class="sxs-lookup"><span data-stu-id="97d9e-268">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="97d9e-269">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="97d9e-269">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="97d9e-270">#dc143c</span><span class="sxs-lookup"><span data-stu-id="97d9e-270">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="97d9e-271">#00ffff</span><span class="sxs-lookup"><span data-stu-id="97d9e-271">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="97d9e-272">#00008b</span><span class="sxs-lookup"><span data-stu-id="97d9e-272">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="97d9e-273">#008b8b</span><span class="sxs-lookup"><span data-stu-id="97d9e-273">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="97d9e-274">#b8860b</span><span class="sxs-lookup"><span data-stu-id="97d9e-274">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="97d9e-275">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="97d9e-275">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="97d9e-276">#006400</span><span class="sxs-lookup"><span data-stu-id="97d9e-276">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="97d9e-277">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="97d9e-277">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="97d9e-278">#8b008b</span><span class="sxs-lookup"><span data-stu-id="97d9e-278">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="97d9e-279">#556b2f</span><span class="sxs-lookup"><span data-stu-id="97d9e-279">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="97d9e-280">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="97d9e-280">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="97d9e-281">#9932cc</span><span class="sxs-lookup"><span data-stu-id="97d9e-281">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="97d9e-282">#8b0000</span><span class="sxs-lookup"><span data-stu-id="97d9e-282">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="97d9e-283">#e9967a</span><span class="sxs-lookup"><span data-stu-id="97d9e-283">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="97d9e-284">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="97d9e-284">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="97d9e-285">#483d8b</span><span class="sxs-lookup"><span data-stu-id="97d9e-285">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="97d9e-286">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="97d9e-286">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="97d9e-287">#00ced1</span><span class="sxs-lookup"><span data-stu-id="97d9e-287">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="97d9e-288">#9400d3</span><span class="sxs-lookup"><span data-stu-id="97d9e-288">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="97d9e-289">#ff1493</span><span class="sxs-lookup"><span data-stu-id="97d9e-289">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="97d9e-290">#00bfff</span><span class="sxs-lookup"><span data-stu-id="97d9e-290">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="97d9e-291">#696969</span><span class="sxs-lookup"><span data-stu-id="97d9e-291">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="97d9e-292">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="97d9e-292">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="97d9e-293">#b22222</span><span class="sxs-lookup"><span data-stu-id="97d9e-293">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="97d9e-294">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="97d9e-294">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="97d9e-295">#228b22</span><span class="sxs-lookup"><span data-stu-id="97d9e-295">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="97d9e-296">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="97d9e-296">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="97d9e-297">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="97d9e-297">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="97d9e-298">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="97d9e-298">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="97d9e-299">#ffd700</span><span class="sxs-lookup"><span data-stu-id="97d9e-299">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="97d9e-300">#daa520</span><span class="sxs-lookup"><span data-stu-id="97d9e-300">#daa520</span></span>|
|`gray`|<span data-ttu-id="97d9e-301">#808080</span><span class="sxs-lookup"><span data-stu-id="97d9e-301">#808080</span></span>|
|`green`|<span data-ttu-id="97d9e-302">#008000</span><span class="sxs-lookup"><span data-stu-id="97d9e-302">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="97d9e-303">#adff2f</span><span class="sxs-lookup"><span data-stu-id="97d9e-303">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="97d9e-304">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="97d9e-304">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="97d9e-305">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="97d9e-305">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="97d9e-306">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="97d9e-306">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="97d9e-307">#4b0082</span><span class="sxs-lookup"><span data-stu-id="97d9e-307">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="97d9e-308">#fffff0</span><span class="sxs-lookup"><span data-stu-id="97d9e-308">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="97d9e-309">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="97d9e-309">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="97d9e-310">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="97d9e-310">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="97d9e-311">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="97d9e-311">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="97d9e-312">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="97d9e-312">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="97d9e-313">#fffacd</span><span class="sxs-lookup"><span data-stu-id="97d9e-313">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="97d9e-314">#add8e6</span><span class="sxs-lookup"><span data-stu-id="97d9e-314">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="97d9e-315">#f08080</span><span class="sxs-lookup"><span data-stu-id="97d9e-315">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="97d9e-316">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="97d9e-316">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="97d9e-317">#fafad2</span><span class="sxs-lookup"><span data-stu-id="97d9e-317">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="97d9e-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="97d9e-318">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="97d9e-319">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="97d9e-319">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="97d9e-320">#90ee90</span><span class="sxs-lookup"><span data-stu-id="97d9e-320">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="97d9e-321">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="97d9e-321">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="97d9e-322">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="97d9e-322">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="97d9e-323">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="97d9e-323">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="97d9e-324">#87cefa</span><span class="sxs-lookup"><span data-stu-id="97d9e-324">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="97d9e-325">#778899</span><span class="sxs-lookup"><span data-stu-id="97d9e-325">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="97d9e-326">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="97d9e-326">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="97d9e-327">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="97d9e-327">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="97d9e-328">#00ff00</span><span class="sxs-lookup"><span data-stu-id="97d9e-328">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="97d9e-329">#32cd32</span><span class="sxs-lookup"><span data-stu-id="97d9e-329">#32cd32</span></span>|
|`linen`|<span data-ttu-id="97d9e-330">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="97d9e-330">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="97d9e-331">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="97d9e-331">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="97d9e-332">#800000</span><span class="sxs-lookup"><span data-stu-id="97d9e-332">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="97d9e-333">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="97d9e-333">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="97d9e-334">#0000cd</span><span class="sxs-lookup"><span data-stu-id="97d9e-334">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="97d9e-335">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="97d9e-335">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="97d9e-336">#9370db</span><span class="sxs-lookup"><span data-stu-id="97d9e-336">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="97d9e-337">#3cb371</span><span class="sxs-lookup"><span data-stu-id="97d9e-337">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="97d9e-338">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="97d9e-338">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="97d9e-339">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="97d9e-339">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="97d9e-340">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="97d9e-340">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="97d9e-341">#c71585</span><span class="sxs-lookup"><span data-stu-id="97d9e-341">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="97d9e-342">#191970</span><span class="sxs-lookup"><span data-stu-id="97d9e-342">#191970</span></span>|
|`mintcream`|<span data-ttu-id="97d9e-343">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="97d9e-343">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="97d9e-344">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="97d9e-344">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="97d9e-345">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="97d9e-345">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="97d9e-346">#ffdead</span><span class="sxs-lookup"><span data-stu-id="97d9e-346">#ffdead</span></span>|
|`navy`|<span data-ttu-id="97d9e-347">#000080</span><span class="sxs-lookup"><span data-stu-id="97d9e-347">#000080</span></span>|
|`oldlace`|<span data-ttu-id="97d9e-348">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="97d9e-348">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="97d9e-349">#808000</span><span class="sxs-lookup"><span data-stu-id="97d9e-349">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="97d9e-350">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="97d9e-350">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="97d9e-351">#ffa500</span><span class="sxs-lookup"><span data-stu-id="97d9e-351">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="97d9e-352">#ff4500</span><span class="sxs-lookup"><span data-stu-id="97d9e-352">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="97d9e-353">#da70d6</span><span class="sxs-lookup"><span data-stu-id="97d9e-353">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="97d9e-354">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="97d9e-354">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="97d9e-355">#98fb98</span><span class="sxs-lookup"><span data-stu-id="97d9e-355">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="97d9e-356">#afeeee</span><span class="sxs-lookup"><span data-stu-id="97d9e-356">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="97d9e-357">#db7093</span><span class="sxs-lookup"><span data-stu-id="97d9e-357">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="97d9e-358">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="97d9e-358">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="97d9e-359">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="97d9e-359">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="97d9e-360">#cd853f</span><span class="sxs-lookup"><span data-stu-id="97d9e-360">#cd853f</span></span>|
|`pink`|<span data-ttu-id="97d9e-361">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="97d9e-361">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="97d9e-362">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="97d9e-362">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="97d9e-363">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="97d9e-363">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="97d9e-364">#800080</span><span class="sxs-lookup"><span data-stu-id="97d9e-364">#800080</span></span>|
|`red`|<span data-ttu-id="97d9e-365">#ff0000</span><span class="sxs-lookup"><span data-stu-id="97d9e-365">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="97d9e-366">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="97d9e-366">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="97d9e-367">#4169e1</span><span class="sxs-lookup"><span data-stu-id="97d9e-367">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="97d9e-368">#8b4513</span><span class="sxs-lookup"><span data-stu-id="97d9e-368">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="97d9e-369">#fa8072</span><span class="sxs-lookup"><span data-stu-id="97d9e-369">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="97d9e-370">#f4a460</span><span class="sxs-lookup"><span data-stu-id="97d9e-370">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="97d9e-371">#00ff00</span><span class="sxs-lookup"><span data-stu-id="97d9e-371">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="97d9e-372">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="97d9e-372">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="97d9e-373">#a0522d</span><span class="sxs-lookup"><span data-stu-id="97d9e-373">#a0522d</span></span>|
|`silver`|<span data-ttu-id="97d9e-374">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="97d9e-374">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="97d9e-375">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="97d9e-375">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="97d9e-376">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="97d9e-376">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="97d9e-377">#708090</span><span class="sxs-lookup"><span data-stu-id="97d9e-377">#708090</span></span>|
|`snow`|<span data-ttu-id="97d9e-378">#fffafa</span><span class="sxs-lookup"><span data-stu-id="97d9e-378">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="97d9e-379">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="97d9e-379">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="97d9e-380">#4682b4</span><span class="sxs-lookup"><span data-stu-id="97d9e-380">#4682b4</span></span>|
|`tan`|<span data-ttu-id="97d9e-381">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="97d9e-381">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="97d9e-382">#008080</span><span class="sxs-lookup"><span data-stu-id="97d9e-382">#008080</span></span>|
|`thistle`|<span data-ttu-id="97d9e-383">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="97d9e-383">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="97d9e-384">#ff6347</span><span class="sxs-lookup"><span data-stu-id="97d9e-384">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="97d9e-385">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="97d9e-385">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="97d9e-386">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="97d9e-386">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="97d9e-387">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="97d9e-387">#f5deb3</span></span>|
|`white`|<span data-ttu-id="97d9e-388">#ffffff</span><span class="sxs-lookup"><span data-stu-id="97d9e-388">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="97d9e-389">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="97d9e-389">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="97d9e-390">#ffff00</span><span class="sxs-lookup"><span data-stu-id="97d9e-390">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="97d9e-391">#9acd32</span><span class="sxs-lookup"><span data-stu-id="97d9e-391">#9acd32</span></span>|
