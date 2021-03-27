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
description: 瞭解 Office 365 全域管理員如何將組織的署名套用至加密的電子郵件，& 加密入口網站的內容。
ms.openlocfilehash: 2898e12ad00d11cd9eb2f3be5d817ef113607e79
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394711"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="98f60-103">將貴組織的品牌新增至 Microsoft 365，以進行商務郵件加密加密郵件</span><span class="sxs-lookup"><span data-stu-id="98f60-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="98f60-104">您可以套用公司品牌，以自訂群組織的電子郵件訊息和加密入口網站的外觀。</span><span class="sxs-lookup"><span data-stu-id="98f60-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="98f60-105">您必須先對您的公司或學校帳戶套用全域系統管理員許可權，才可開始使用。</span><span class="sxs-lookup"><span data-stu-id="98f60-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="98f60-106">一旦您具有這些許可權，請使用 Get-OMEConfiguration 和 Set-OMEConfiguration Windows PowerShell Cmdlet 來自訂這些加密電子郵件的這些部分：</span><span class="sxs-lookup"><span data-stu-id="98f60-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="98f60-107">簡介文字</span><span class="sxs-lookup"><span data-stu-id="98f60-107">Introductory text</span></span>

- <span data-ttu-id="98f60-108">免責聲明文字</span><span class="sxs-lookup"><span data-stu-id="98f60-108">Disclaimer text</span></span>

- <span data-ttu-id="98f60-109">組織之隱私權聲明的 URL</span><span class="sxs-lookup"><span data-stu-id="98f60-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="98f60-110">OME 入口網站中的文字</span><span class="sxs-lookup"><span data-stu-id="98f60-110">Text in the OME portal</span></span>

- <span data-ttu-id="98f60-111">出現在電子郵件和 OME 入口網站中的標誌，或是否要使用標誌</span><span class="sxs-lookup"><span data-stu-id="98f60-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="98f60-112">電子郵件訊息和 OME 入口網站中的背景色彩</span><span class="sxs-lookup"><span data-stu-id="98f60-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="98f60-113">您也可以隨時回復為預設的外觀與風格。</span><span class="sxs-lookup"><span data-stu-id="98f60-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="98f60-114">如果您想要更多控制，請使用 Office 365 Advanced Message Encryption，針對來自組織的加密電子郵件建立多個範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="98f60-115">使用這些範本來控制使用者經驗的各個部分。</span><span class="sxs-lookup"><span data-stu-id="98f60-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="98f60-116">例如，指定收件者是否可以使用 Google、Yahoo 和 Microsoft 帳戶登入加密入口網站。</span><span class="sxs-lookup"><span data-stu-id="98f60-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="98f60-117">使用範本來滿足數個使用案例，例如：</span><span class="sxs-lookup"><span data-stu-id="98f60-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="98f60-118">個別部門，例如財務、銷售等等。</span><span class="sxs-lookup"><span data-stu-id="98f60-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="98f60-119">不同的產品</span><span class="sxs-lookup"><span data-stu-id="98f60-119">Different products</span></span>

- <span data-ttu-id="98f60-120">不同的地理區域或國家</span><span class="sxs-lookup"><span data-stu-id="98f60-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="98f60-121">您是否要允許吊銷電子郵件</span><span class="sxs-lookup"><span data-stu-id="98f60-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="98f60-122">您是否想要傳送給外部收件者的電子郵件在指定的天數後到期。</span><span class="sxs-lookup"><span data-stu-id="98f60-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="98f60-123">建立範本後，您可以使用 Exchange 郵件流程規則將其套用至加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="98f60-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="98f60-124">如果您有 Office 365 Advanced Message Encryption，您可以使用這些範本撤銷所有已標記的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="98f60-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="98f60-125">使用 OME 品牌範本</span><span class="sxs-lookup"><span data-stu-id="98f60-125">Work with OME branding templates</span></span>

<span data-ttu-id="98f60-126">您可以在品牌範本中修改數項功能。</span><span class="sxs-lookup"><span data-stu-id="98f60-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="98f60-127">您可以修改預設範本，但不要移除。</span><span class="sxs-lookup"><span data-stu-id="98f60-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="98f60-128">如果您有高級郵件加密，您也可以建立、修改及移除自訂範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="98f60-129">使用 Windows PowerShell 一次可搭配一個署名範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="98f60-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) -修改預設的署名範本或您建立的自訂商標範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="98f60-131">[Set-omeconfiguration](/powershell/module/exchange/new-omeconfiguration) -建立新的署名範本，僅限高級郵件加密。</span><span class="sxs-lookup"><span data-stu-id="98f60-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="98f60-132">[Set-omeconfiguration](/powershell/module/exchange/remove-omeconfiguration) -移除自訂品牌範本，僅限高級郵件加密。</span><span class="sxs-lookup"><span data-stu-id="98f60-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="98f60-133">您無法刪除預設的署名範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="98f60-134">修改 OME 署名範本</span><span class="sxs-lookup"><span data-stu-id="98f60-134">Modify an OME branding template</span></span>

<span data-ttu-id="98f60-135">使用 Windows PowerShell 一次修改一個署名範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="98f60-136">如果您有高級郵件加密，您也可以建立、修改及移除自訂範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="98f60-137">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="98f60-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="98f60-138">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="98f60-138">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="98f60-139">使用 [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) 所述的 Set-OMEConfiguration 指令程式，或使用下圖及表格以取得指導方針。</span><span class="sxs-lookup"><span data-stu-id="98f60-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![可自訂的電子郵件元件](../media/ome-template-breakout.png)

|<span data-ttu-id="98f60-141">**若要自訂此加密經驗功能**</span><span class="sxs-lookup"><span data-stu-id="98f60-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="98f60-142">**使用這些命令**</span><span class="sxs-lookup"><span data-stu-id="98f60-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="98f60-143">背景色彩</span><span class="sxs-lookup"><span data-stu-id="98f60-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="98f60-144">**範例：**</span><span class="sxs-lookup"><span data-stu-id="98f60-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="98f60-145">如需背景色彩的詳細資訊，請參閱本文稍後的 [ [背景色彩](#background-color-reference) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="98f60-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="98f60-146">標誌</span><span class="sxs-lookup"><span data-stu-id="98f60-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="98f60-147">**範例：**</span><span class="sxs-lookup"><span data-stu-id="98f60-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="98f60-148">支援的檔案格式：.png、.jpg、.bmp 或 .tiff</span><span class="sxs-lookup"><span data-stu-id="98f60-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="98f60-149">標誌檔案的最佳大小：小於 40 KB</span><span class="sxs-lookup"><span data-stu-id="98f60-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="98f60-150">標誌影像的最佳大小：170x70 圖元。</span><span class="sxs-lookup"><span data-stu-id="98f60-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="98f60-151">如果您的影像超過這些尺寸，服務會重新調整您的徽標以在入口網站中顯示。</span><span class="sxs-lookup"><span data-stu-id="98f60-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="98f60-152">服務不會修改圖形檔案本身。</span><span class="sxs-lookup"><span data-stu-id="98f60-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="98f60-153">為了獲得最佳結果，請使用最佳大小。</span><span class="sxs-lookup"><span data-stu-id="98f60-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="98f60-154">寄件者名稱和電子郵件地址旁的文字</span><span class="sxs-lookup"><span data-stu-id="98f60-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="98f60-155">**範例：**</span><span class="sxs-lookup"><span data-stu-id="98f60-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="98f60-156">出現在「讀取訊息」按鈕上的文字</span><span class="sxs-lookup"><span data-stu-id="98f60-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="98f60-157">**範例：**</span><span class="sxs-lookup"><span data-stu-id="98f60-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="98f60-158">出現在 [閱讀郵件] 按鈕下方的文字</span><span class="sxs-lookup"><span data-stu-id="98f60-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="98f60-159">**範例：**</span><span class="sxs-lookup"><span data-stu-id="98f60-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="98f60-160">隱私權聲明連結的 URL</span><span class="sxs-lookup"><span data-stu-id="98f60-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="98f60-161">**範例：**</span><span class="sxs-lookup"><span data-stu-id="98f60-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="98f60-162">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="98f60-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="98f60-163">**範例：**</span><span class="sxs-lookup"><span data-stu-id="98f60-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="98f60-164">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="98f60-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="98f60-165">**範例：**</span><span class="sxs-lookup"><span data-stu-id="98f60-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="98f60-166">啟用或停用此自訂範本的一次性程式碼驗證</span><span class="sxs-lookup"><span data-stu-id="98f60-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="98f60-167">**範例：**</span><span class="sxs-lookup"><span data-stu-id="98f60-167">**Examples:**</span></span> <br/><span data-ttu-id="98f60-168">針對此自訂範本啟用一次 passcodes</span><span class="sxs-lookup"><span data-stu-id="98f60-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="98f60-169">針對此自訂範本停用一次 passcodes</span><span class="sxs-lookup"><span data-stu-id="98f60-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="98f60-170">啟用或停用此自訂範本的 Microsoft、Google 或 Yahoo 識別碼驗證</span><span class="sxs-lookup"><span data-stu-id="98f60-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="98f60-171">**範例：**</span><span class="sxs-lookup"><span data-stu-id="98f60-171">**Examples:**</span></span> <br/><span data-ttu-id="98f60-172">啟用此自訂範本的社交 IDs</span><span class="sxs-lookup"><span data-stu-id="98f60-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="98f60-173">停用此自訂範本的社交 IDs</span><span class="sxs-lookup"><span data-stu-id="98f60-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="98f60-174"> (高級郵件加密建立 OME 署名範本) </span><span class="sxs-lookup"><span data-stu-id="98f60-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="98f60-175">如果您有 Office 365 Advanced Message Encryption，您可以使用 [set-omeconfiguration](/powershell/module/exchange/new-omeconfiguration) Cmdlet 為您的組織建立自訂商標範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="98f60-176">建立範本之後，您可以使用 Set-OMEConfiguration Cmdlet 修改範本，如 [modify a OME 署名範本](#modify-an-ome-branding-template)所述。</span><span class="sxs-lookup"><span data-stu-id="98f60-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="98f60-177">您可以建立多個範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-177">You can create multiple templates.</span></span>

<span data-ttu-id="98f60-178">若要建立新的自訂品牌範本：</span><span class="sxs-lookup"><span data-stu-id="98f60-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="98f60-179">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="98f60-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="98f60-180">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="98f60-180">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="98f60-181">使用 [set-omeconfiguration](/powershell/module/exchange/new-omeconfiguration) Cmdlet 來建立新的範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-181">Use the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="98f60-182">例如：</span><span class="sxs-lookup"><span data-stu-id="98f60-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="98f60-183">將預設署名範本傳回其原始值</span><span class="sxs-lookup"><span data-stu-id="98f60-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="98f60-184">若要從預設範本移除所有修改（包括品牌自訂專案）等等，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="98f60-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="98f60-185">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="98f60-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="98f60-186">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="98f60-186">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="98f60-187">使用 [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration)中所述的 **Set-OMEConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="98f60-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="98f60-188">若要從 DisclaimerText、EmailText 及 PortalText 值中移除組織的署名自訂，請將值設為空字串 `""` 。</span><span class="sxs-lookup"><span data-stu-id="98f60-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="98f60-189">針對所有影像值，例如 [標誌]，將值設為  `"$null"` 。</span><span class="sxs-lookup"><span data-stu-id="98f60-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="98f60-190">下表說明加密自訂選項的預設值。</span><span class="sxs-lookup"><span data-stu-id="98f60-190">The following table describes the encryption customization option defaults.</span></span>

   |<span data-ttu-id="98f60-191">將加密體驗的這項功能回復為預設文字和影像</span><span class="sxs-lookup"><span data-stu-id="98f60-191">To revert this feature of the encryption experience back to the default text and image</span></span>|<span data-ttu-id="98f60-192">使用這些命令</span><span class="sxs-lookup"><span data-stu-id="98f60-192">Use these commands</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="98f60-193">附帶加密電子郵件的預設文字。</span><span class="sxs-lookup"><span data-stu-id="98f60-193">Default text that comes with encrypted email messages.</span></span>  <span data-ttu-id="98f60-194">預設文字會出現在檢視加密郵件的指示上方。</span><span class="sxs-lookup"><span data-stu-id="98f60-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="98f60-195">**範例：**</span><span class="sxs-lookup"><span data-stu-id="98f60-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="98f60-196">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="98f60-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="98f60-197">**範例：**</span><span class="sxs-lookup"><span data-stu-id="98f60-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="98f60-198">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="98f60-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="98f60-199">**範例回復為預設值：**</span><span class="sxs-lookup"><span data-stu-id="98f60-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="98f60-200">標誌</span><span class="sxs-lookup"><span data-stu-id="98f60-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="98f60-201">**範例回復為預設值：**</span><span class="sxs-lookup"><span data-stu-id="98f60-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="98f60-202">背景色彩</span><span class="sxs-lookup"><span data-stu-id="98f60-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="98f60-203">**範例回復為預設值：**</span><span class="sxs-lookup"><span data-stu-id="98f60-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="98f60-204"> (高級郵件加密移除自訂商標範本) </span><span class="sxs-lookup"><span data-stu-id="98f60-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="98f60-205">您只可以移除或刪除您所做的品牌範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="98f60-206">您無法移除預設的署名範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="98f60-207">若要移除自訂商標範本：</span><span class="sxs-lookup"><span data-stu-id="98f60-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="98f60-208">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="98f60-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="98f60-209">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="98f60-209">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="98f60-210">使用 **Remove-set-omeconfiguration 指令程式** ，如下所示：</span><span class="sxs-lookup"><span data-stu-id="98f60-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="98f60-211">例如：</span><span class="sxs-lookup"><span data-stu-id="98f60-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="98f60-212">如需詳細資訊，請參閱 [Remove-set-omeconfiguration](/powershell/module/exchange/remove-omeconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="98f60-212">For more information, see [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="98f60-213">建立將自訂品牌套用至加密電子郵件的 Exchange 郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="98f60-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

<span data-ttu-id="98f60-214">修改預設範本或建立新的品牌範本之後，您可以建立 Exchange 郵件流程規則，以根據特定條件套用您的自訂品牌。</span><span class="sxs-lookup"><span data-stu-id="98f60-214">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="98f60-215">這類規則會在下列情況中套用自訂品牌：</span><span class="sxs-lookup"><span data-stu-id="98f60-215">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="98f60-216">如果使用者使用 Outlook 或網頁上的 outlook 來手動加密電子郵件，則為 Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="98f60-216">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="98f60-217">如果電子郵件已由 Exchange 郵件流程規則或資料遺失防護原則自動加密</span><span class="sxs-lookup"><span data-stu-id="98f60-217">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="98f60-218">如需如何建立可套用加密之 Exchange 郵件流程規則的詳細資訊，請參閱 [定義郵件流程規則，以在 Office 365 中加密電子郵件訊息](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="98f60-218">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="98f60-219">在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登 [入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="98f60-219">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="98f60-220">選擇 [ **管理** ] 磚。</span><span class="sxs-lookup"><span data-stu-id="98f60-220">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="98f60-221">在 Microsoft 365 系統管理中心中，選擇 [系統 **管理中心**] [ \> **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="98f60-221">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="98f60-222">在 EAC 中，移至 [ **郵件流程** \> **規則** ]，然後選取 [ **新增** 新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="98f60-222">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="98f60-223">如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="98f60-223">For more information about using the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="98f60-224">在 [ **名稱**] 中，輸入規則的名稱，例如「銷售部門的商標」。</span><span class="sxs-lookup"><span data-stu-id="98f60-224">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="98f60-225">在 [套用 **此規則** 條件] 中，選取 **寄件者位於組織內部的** 條件，以及您在可用條件清單中所需的其他條件。</span><span class="sxs-lookup"><span data-stu-id="98f60-225">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="98f60-226">例如，您可能想要將特定的署名範本套用到：</span><span class="sxs-lookup"><span data-stu-id="98f60-226">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="98f60-227">從財務部門的成員傳送的所有加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="98f60-227">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="98f60-228">以特定關鍵字（如 "External" 或 "Partner"）傳送的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="98f60-228">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="98f60-229">傳送至特定網域的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="98f60-229">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="98f60-230">從 **執行下列** 動作，選取 **[修改郵件安全性** 套用 \> **自訂品牌] 以 OME 郵件**。</span><span class="sxs-lookup"><span data-stu-id="98f60-230">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="98f60-231">接下來，從下拉式清單中選取商標範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-231">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="98f60-232"> (選用) 您可以設定郵件流程規則套用加密和自訂商標。</span><span class="sxs-lookup"><span data-stu-id="98f60-232">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="98f60-233">從 **執行下列** 動作，選取 **[修改郵件安全性**]，然後選擇 [套用 **Office 365 郵件加密和許可權保護**]。</span><span class="sxs-lookup"><span data-stu-id="98f60-233">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="98f60-234">從清單中選取 RMS 範本，然後選擇 [ **儲存**]，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="98f60-234">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="98f60-235">範本清單包含預設範本和選項，以及您建立的任何自訂範本。</span><span class="sxs-lookup"><span data-stu-id="98f60-235">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="98f60-236">如果清單是空的，請確定您已使用新功能設定 Office 365 郵件加密。</span><span class="sxs-lookup"><span data-stu-id="98f60-236">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="98f60-237">如需相關指示，請參閱 [Set up New Office 365 Message Encryption 功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="98f60-237">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="98f60-238">如需預設範本的相關資訊，請參閱設定 [及管理 Azure 資訊保護的範本](/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="98f60-238">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="98f60-239">如需有關 [ **不要轉寄** ] 選項的詳細資訊，請參閱 [請勿轉寄選項的電子郵件](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="98f60-239">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="98f60-240">如需只供 **加密** 之選項的詳細資訊，請參閱 [僅限加密選項的電子郵件](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="98f60-240">For information about the **encrypt only** option, see [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="98f60-241">如果您想要指定另一個動作，請選擇 [ **新增動作** ]。</span><span class="sxs-lookup"><span data-stu-id="98f60-241">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="98f60-242">背景色彩參考</span><span class="sxs-lookup"><span data-stu-id="98f60-242">Background color reference</span></span>

<span data-ttu-id="98f60-243">您可以用於背景色彩的色彩名稱是有限的。</span><span class="sxs-lookup"><span data-stu-id="98f60-243">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="98f60-244">您可以使用十六進位代碼值 (#RRGGBB) ，而不是使用色彩名稱。</span><span class="sxs-lookup"><span data-stu-id="98f60-244">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="98f60-245">您可以使用對應于色彩名稱的十六進位代碼值，也可以使用自訂的十六進位代碼值。</span><span class="sxs-lookup"><span data-stu-id="98f60-245">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="98f60-246">請務必以引號括住十六進位代碼值 (例如， `"#f0f8ff"`) 。</span><span class="sxs-lookup"><span data-stu-id="98f60-246">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="98f60-247">下表說明可用的背景色彩名稱及其對應的十六進位代碼值。</span><span class="sxs-lookup"><span data-stu-id="98f60-247">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="98f60-248">**色彩名稱**</span><span class="sxs-lookup"><span data-stu-id="98f60-248">**Color name**</span></span>|<span data-ttu-id="98f60-249">**色彩代碼**</span><span class="sxs-lookup"><span data-stu-id="98f60-249">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="98f60-250">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="98f60-250">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="98f60-251">#faebd7</span><span class="sxs-lookup"><span data-stu-id="98f60-251">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="98f60-252">#00ffff</span><span class="sxs-lookup"><span data-stu-id="98f60-252">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="98f60-253">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="98f60-253">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="98f60-254">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="98f60-254">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="98f60-255">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="98f60-255">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="98f60-256">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="98f60-256">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="98f60-257">#000000</span><span class="sxs-lookup"><span data-stu-id="98f60-257">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="98f60-258">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="98f60-258">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="98f60-259">#0000ff</span><span class="sxs-lookup"><span data-stu-id="98f60-259">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="98f60-260">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="98f60-260">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="98f60-261">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="98f60-261">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="98f60-262">#deb887</span><span class="sxs-lookup"><span data-stu-id="98f60-262">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="98f60-263">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="98f60-263">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="98f60-264">#7fff00</span><span class="sxs-lookup"><span data-stu-id="98f60-264">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="98f60-265">#d2691e</span><span class="sxs-lookup"><span data-stu-id="98f60-265">#d2691e</span></span>|
|`coral`|<span data-ttu-id="98f60-266">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="98f60-266">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="98f60-267">#6495ed</span><span class="sxs-lookup"><span data-stu-id="98f60-267">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="98f60-268">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="98f60-268">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="98f60-269">#dc143c</span><span class="sxs-lookup"><span data-stu-id="98f60-269">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="98f60-270">#00ffff</span><span class="sxs-lookup"><span data-stu-id="98f60-270">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="98f60-271">#00008b</span><span class="sxs-lookup"><span data-stu-id="98f60-271">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="98f60-272">#008b8b</span><span class="sxs-lookup"><span data-stu-id="98f60-272">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="98f60-273">#b8860b</span><span class="sxs-lookup"><span data-stu-id="98f60-273">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="98f60-274">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="98f60-274">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="98f60-275">#006400</span><span class="sxs-lookup"><span data-stu-id="98f60-275">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="98f60-276">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="98f60-276">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="98f60-277">#8b008b</span><span class="sxs-lookup"><span data-stu-id="98f60-277">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="98f60-278">#556b2f</span><span class="sxs-lookup"><span data-stu-id="98f60-278">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="98f60-279">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="98f60-279">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="98f60-280">#9932cc</span><span class="sxs-lookup"><span data-stu-id="98f60-280">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="98f60-281">#8b0000</span><span class="sxs-lookup"><span data-stu-id="98f60-281">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="98f60-282">#e9967a</span><span class="sxs-lookup"><span data-stu-id="98f60-282">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="98f60-283">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="98f60-283">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="98f60-284">#483d8b</span><span class="sxs-lookup"><span data-stu-id="98f60-284">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="98f60-285">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="98f60-285">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="98f60-286">#00ced1</span><span class="sxs-lookup"><span data-stu-id="98f60-286">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="98f60-287">#9400d3</span><span class="sxs-lookup"><span data-stu-id="98f60-287">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="98f60-288">#ff1493</span><span class="sxs-lookup"><span data-stu-id="98f60-288">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="98f60-289">#00bfff</span><span class="sxs-lookup"><span data-stu-id="98f60-289">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="98f60-290">#696969</span><span class="sxs-lookup"><span data-stu-id="98f60-290">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="98f60-291">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="98f60-291">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="98f60-292">#b22222</span><span class="sxs-lookup"><span data-stu-id="98f60-292">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="98f60-293">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="98f60-293">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="98f60-294">#228b22</span><span class="sxs-lookup"><span data-stu-id="98f60-294">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="98f60-295">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="98f60-295">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="98f60-296">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="98f60-296">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="98f60-297">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="98f60-297">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="98f60-298">#ffd700</span><span class="sxs-lookup"><span data-stu-id="98f60-298">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="98f60-299">#daa520</span><span class="sxs-lookup"><span data-stu-id="98f60-299">#daa520</span></span>|
|`gray`|<span data-ttu-id="98f60-300">#808080</span><span class="sxs-lookup"><span data-stu-id="98f60-300">#808080</span></span>|
|`green`|<span data-ttu-id="98f60-301">#008000</span><span class="sxs-lookup"><span data-stu-id="98f60-301">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="98f60-302">#adff2f</span><span class="sxs-lookup"><span data-stu-id="98f60-302">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="98f60-303">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="98f60-303">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="98f60-304">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="98f60-304">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="98f60-305">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="98f60-305">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="98f60-306">#4b0082</span><span class="sxs-lookup"><span data-stu-id="98f60-306">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="98f60-307">#fffff0</span><span class="sxs-lookup"><span data-stu-id="98f60-307">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="98f60-308">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="98f60-308">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="98f60-309">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="98f60-309">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="98f60-310">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="98f60-310">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="98f60-311">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="98f60-311">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="98f60-312">#fffacd</span><span class="sxs-lookup"><span data-stu-id="98f60-312">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="98f60-313">#add8e6</span><span class="sxs-lookup"><span data-stu-id="98f60-313">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="98f60-314">#f08080</span><span class="sxs-lookup"><span data-stu-id="98f60-314">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="98f60-315">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="98f60-315">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="98f60-316">#fafad2</span><span class="sxs-lookup"><span data-stu-id="98f60-316">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="98f60-317">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="98f60-317">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="98f60-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="98f60-318">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="98f60-319">#90ee90</span><span class="sxs-lookup"><span data-stu-id="98f60-319">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="98f60-320">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="98f60-320">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="98f60-321">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="98f60-321">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="98f60-322">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="98f60-322">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="98f60-323">#87cefa</span><span class="sxs-lookup"><span data-stu-id="98f60-323">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="98f60-324">#778899</span><span class="sxs-lookup"><span data-stu-id="98f60-324">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="98f60-325">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="98f60-325">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="98f60-326">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="98f60-326">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="98f60-327">#00ff00</span><span class="sxs-lookup"><span data-stu-id="98f60-327">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="98f60-328">#32cd32</span><span class="sxs-lookup"><span data-stu-id="98f60-328">#32cd32</span></span>|
|`linen`|<span data-ttu-id="98f60-329">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="98f60-329">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="98f60-330">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="98f60-330">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="98f60-331">#800000</span><span class="sxs-lookup"><span data-stu-id="98f60-331">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="98f60-332">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="98f60-332">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="98f60-333">#0000cd</span><span class="sxs-lookup"><span data-stu-id="98f60-333">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="98f60-334">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="98f60-334">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="98f60-335">#9370db</span><span class="sxs-lookup"><span data-stu-id="98f60-335">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="98f60-336">#3cb371</span><span class="sxs-lookup"><span data-stu-id="98f60-336">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="98f60-337">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="98f60-337">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="98f60-338">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="98f60-338">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="98f60-339">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="98f60-339">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="98f60-340">#c71585</span><span class="sxs-lookup"><span data-stu-id="98f60-340">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="98f60-341">#191970</span><span class="sxs-lookup"><span data-stu-id="98f60-341">#191970</span></span>|
|`mintcream`|<span data-ttu-id="98f60-342">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="98f60-342">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="98f60-343">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="98f60-343">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="98f60-344">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="98f60-344">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="98f60-345">#ffdead</span><span class="sxs-lookup"><span data-stu-id="98f60-345">#ffdead</span></span>|
|`navy`|<span data-ttu-id="98f60-346">#000080</span><span class="sxs-lookup"><span data-stu-id="98f60-346">#000080</span></span>|
|`oldlace`|<span data-ttu-id="98f60-347">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="98f60-347">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="98f60-348">#808000</span><span class="sxs-lookup"><span data-stu-id="98f60-348">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="98f60-349">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="98f60-349">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="98f60-350">#ffa500</span><span class="sxs-lookup"><span data-stu-id="98f60-350">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="98f60-351">#ff4500</span><span class="sxs-lookup"><span data-stu-id="98f60-351">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="98f60-352">#da70d6</span><span class="sxs-lookup"><span data-stu-id="98f60-352">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="98f60-353">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="98f60-353">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="98f60-354">#98fb98</span><span class="sxs-lookup"><span data-stu-id="98f60-354">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="98f60-355">#afeeee</span><span class="sxs-lookup"><span data-stu-id="98f60-355">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="98f60-356">#db7093</span><span class="sxs-lookup"><span data-stu-id="98f60-356">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="98f60-357">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="98f60-357">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="98f60-358">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="98f60-358">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="98f60-359">#cd853f</span><span class="sxs-lookup"><span data-stu-id="98f60-359">#cd853f</span></span>|
|`pink`|<span data-ttu-id="98f60-360">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="98f60-360">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="98f60-361">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="98f60-361">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="98f60-362">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="98f60-362">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="98f60-363">#800080</span><span class="sxs-lookup"><span data-stu-id="98f60-363">#800080</span></span>|
|`red`|<span data-ttu-id="98f60-364">#ff0000</span><span class="sxs-lookup"><span data-stu-id="98f60-364">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="98f60-365">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="98f60-365">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="98f60-366">#4169e1</span><span class="sxs-lookup"><span data-stu-id="98f60-366">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="98f60-367">#8b4513</span><span class="sxs-lookup"><span data-stu-id="98f60-367">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="98f60-368">#fa8072</span><span class="sxs-lookup"><span data-stu-id="98f60-368">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="98f60-369">#f4a460</span><span class="sxs-lookup"><span data-stu-id="98f60-369">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="98f60-370">#00ff00</span><span class="sxs-lookup"><span data-stu-id="98f60-370">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="98f60-371">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="98f60-371">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="98f60-372">#a0522d</span><span class="sxs-lookup"><span data-stu-id="98f60-372">#a0522d</span></span>|
|`silver`|<span data-ttu-id="98f60-373">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="98f60-373">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="98f60-374">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="98f60-374">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="98f60-375">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="98f60-375">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="98f60-376">#708090</span><span class="sxs-lookup"><span data-stu-id="98f60-376">#708090</span></span>|
|`snow`|<span data-ttu-id="98f60-377">#fffafa</span><span class="sxs-lookup"><span data-stu-id="98f60-377">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="98f60-378">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="98f60-378">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="98f60-379">#4682b4</span><span class="sxs-lookup"><span data-stu-id="98f60-379">#4682b4</span></span>|
|`tan`|<span data-ttu-id="98f60-380">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="98f60-380">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="98f60-381">#008080</span><span class="sxs-lookup"><span data-stu-id="98f60-381">#008080</span></span>|
|`thistle`|<span data-ttu-id="98f60-382">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="98f60-382">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="98f60-383">#ff6347</span><span class="sxs-lookup"><span data-stu-id="98f60-383">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="98f60-384">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="98f60-384">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="98f60-385">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="98f60-385">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="98f60-386">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="98f60-386">#f5deb3</span></span>|
|`white`|<span data-ttu-id="98f60-387">#ffffff</span><span class="sxs-lookup"><span data-stu-id="98f60-387">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="98f60-388">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="98f60-388">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="98f60-389">#ffff00</span><span class="sxs-lookup"><span data-stu-id="98f60-389">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="98f60-390">#9acd32</span><span class="sxs-lookup"><span data-stu-id="98f60-390">#9acd32</span></span>|