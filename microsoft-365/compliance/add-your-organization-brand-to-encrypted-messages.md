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
description: 將組織的署名套用至組織的加密電子郵件和加密入口網站的內容。
ms.openlocfilehash: 8d8e0a75a88cfe5dbcd5b1e6ed2c276e2edef904
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351734"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a><span data-ttu-id="b9c87-103">將貴組織的品牌新增至您的加密郵件</span><span class="sxs-lookup"><span data-stu-id="b9c87-103">Add your organization's brand to your encrypted messages</span></span>

<span data-ttu-id="b9c87-104">做為 Exchange Online 或 Exchange Online Protection 管理員，您可以套用公司品牌，以自訂群組織的 Microsoft 365 的商務訊息加密電子郵件和加密入口網站內容的外觀。</span><span class="sxs-lookup"><span data-stu-id="b9c87-104">As an Exchange Online or Exchange Online Protection administrator, you can apply your company branding to customize the look of your organization's Microsoft 365 for business Message Encryption email messages and the contents of the encryption portal.</span></span> <span data-ttu-id="b9c87-105">您可以使用 Get-OMEConfiguration 和 Set-OMEConfiguration Windows PowerShell Cmdlet，針對加密的電子郵件訊息收件者，自訂下列各項流覽體驗：</span><span class="sxs-lookup"><span data-stu-id="b9c87-105">Using the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets, you can customize the following aspects of the viewing experience for recipients of encrypted email messages:</span></span>
  
- <span data-ttu-id="b9c87-106">包含加密訊息的電子郵件簡介文字</span><span class="sxs-lookup"><span data-stu-id="b9c87-106">Introductory text of the email that contains the encrypted message</span></span>

- <span data-ttu-id="b9c87-107">包含加密訊息的電子郵件免責聲明文字</span><span class="sxs-lookup"><span data-stu-id="b9c87-107">Disclaimer text of the email that contains the encrypted message</span></span>

- <span data-ttu-id="b9c87-108">您組織之隱私權聲明的 URL</span><span class="sxs-lookup"><span data-stu-id="b9c87-108">URL of the privacy statement for your organization</span></span>

- <span data-ttu-id="b9c87-109">出現在 OME 入口網站中的文字</span><span class="sxs-lookup"><span data-stu-id="b9c87-109">Text that appears in the OME portal</span></span>

- <span data-ttu-id="b9c87-110">出現在電子郵件和 OME 入口網站中的標誌，或是否要使用標誌</span><span class="sxs-lookup"><span data-stu-id="b9c87-110">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="b9c87-111">電子郵件訊息和 OME 入口網站中的背景色彩</span><span class="sxs-lookup"><span data-stu-id="b9c87-111">Background color in the email message and OME portal</span></span>

<span data-ttu-id="b9c87-112">您也可以隨時回復為預設的外觀與風格。</span><span class="sxs-lookup"><span data-stu-id="b9c87-112">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="b9c87-113">如果您想要控制，您可以使用 Office 365 高級郵件加密，並建立多個範本，以用於來自組織的加密電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b9c87-113">If you'd like more control, you can use Office 365 Advanced Message Encryption and create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="b9c87-114">使用這些範本，您不僅可以控制電子郵件的外觀與風格，還可以控制使用者經驗的各個部分。</span><span class="sxs-lookup"><span data-stu-id="b9c87-114">Using these templates, you can control more than just the look and feel of the email messages, but also control parts of the end-user experience.</span></span> <span data-ttu-id="b9c87-115">例如，您可以指定是否已套用此範本的郵件收件者，以及使用 Google、Yahoo 和 Microsoft 帳戶的收件者，都可以使用這些帳戶登入 Office 365 郵件加密入口網站。</span><span class="sxs-lookup"><span data-stu-id="b9c87-115">For example, you can specify whether recipients of mail that have this template applied and who use Google, Yahoo, and Microsoft Accounts can use these accounts to sign in to the Office 365 Message Encryption portal.</span></span> <span data-ttu-id="b9c87-116">您可以使用範本來滿足數個使用案例，例如：</span><span class="sxs-lookup"><span data-stu-id="b9c87-116">You might use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="b9c87-117">每個部門的範本，例如財務、銷售等等。</span><span class="sxs-lookup"><span data-stu-id="b9c87-117">Templates for each department, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="b9c87-118">不同產品的範本</span><span class="sxs-lookup"><span data-stu-id="b9c87-118">Templates for different products</span></span>

- <span data-ttu-id="b9c87-119">不同地理區域或國家/地區的範本</span><span class="sxs-lookup"><span data-stu-id="b9c87-119">Templates for different geographical regions or countries</span></span>

- <span data-ttu-id="b9c87-120">您是否要允許吊銷電子郵件</span><span class="sxs-lookup"><span data-stu-id="b9c87-120">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="b9c87-121">您是否想要傳送給外部收件者的電子郵件在指定的天數後到期。</span><span class="sxs-lookup"><span data-stu-id="b9c87-121">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="b9c87-122">建立範本後，您可以使用 Exchange 郵件流程規則將其套用至加密的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b9c87-122">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="b9c87-123">如果您有 Office 365 Advanced Message Encryption，您可以使用這些範本撤銷所有已標記的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="b9c87-123">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="b9c87-124">使用 OME 品牌範本</span><span class="sxs-lookup"><span data-stu-id="b9c87-124">Work with OME branding templates</span></span>

<span data-ttu-id="b9c87-125">您可以在品牌範本中修改數項功能。</span><span class="sxs-lookup"><span data-stu-id="b9c87-125">You can modify several features within a branding template.</span></span> <span data-ttu-id="b9c87-126">您可以修改預設範本，但不要移除。</span><span class="sxs-lookup"><span data-stu-id="b9c87-126">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="b9c87-127">如果您有高級郵件加密，您也可以建立、修改及移除自訂範本。</span><span class="sxs-lookup"><span data-stu-id="b9c87-127">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="b9c87-128">使用 Windows PowerShell 一次可搭配一個署名範本。</span><span class="sxs-lookup"><span data-stu-id="b9c87-128">Use Windows PowerShell to work with one branding template at a time.</span></span> <span data-ttu-id="b9c87-129">您需要在組織中具備全域系統管理員許可權的工作或學校帳戶，才可使用這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b9c87-129">You'll need a work or school account that has global administrator permissions in your organization to use these cmdlets.</span></span>

- <span data-ttu-id="b9c87-130">[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) -修改預設的署名範本或您建立的自訂商標範本。</span><span class="sxs-lookup"><span data-stu-id="b9c87-130">[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="b9c87-131">[Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) -建立新的署名範本，僅限高級郵件加密。</span><span class="sxs-lookup"><span data-stu-id="b9c87-131">[New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="b9c87-132">[Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) -移除自訂品牌範本，僅限高級郵件加密。</span><span class="sxs-lookup"><span data-stu-id="b9c87-132">[Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="b9c87-133">您無法刪除預設的署名範本。</span><span class="sxs-lookup"><span data-stu-id="b9c87-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="b9c87-134">修改 OME 署名範本</span><span class="sxs-lookup"><span data-stu-id="b9c87-134">Modify an OME branding template</span></span>

<span data-ttu-id="b9c87-135">使用 Windows PowerShell 一次修改一個署名範本。</span><span class="sxs-lookup"><span data-stu-id="b9c87-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="b9c87-136">如果您有高級郵件加密，您也可以建立、修改及移除自訂範本。</span><span class="sxs-lookup"><span data-stu-id="b9c87-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="b9c87-137">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b9c87-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="b9c87-138">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="b9c87-138">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b9c87-139">使用[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration)中所述的 Set-OMEConfiguration 指令程式修改範本，或使用下列圖形和表格以取得指導方針。</span><span class="sxs-lookup"><span data-stu-id="b9c87-139">Modify the template by using the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![可自訂的電子郵件元件](../media/ome-template-breakout.png)

|<span data-ttu-id="b9c87-141">**若要自訂此加密經驗功能**</span><span class="sxs-lookup"><span data-stu-id="b9c87-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="b9c87-142">**使用這些命令**</span><span class="sxs-lookup"><span data-stu-id="b9c87-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9c87-143">背景色彩</span><span class="sxs-lookup"><span data-stu-id="b9c87-143">Background color</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> <span data-ttu-id="b9c87-144">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|<span data-ttu-id="b9c87-145">標誌</span><span class="sxs-lookup"><span data-stu-id="b9c87-145">Logo</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> <span data-ttu-id="b9c87-146">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-146">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="b9c87-147">支援的檔案格式：.png、.jpg、.bmp 或 .tiff</span><span class="sxs-lookup"><span data-stu-id="b9c87-147">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="b9c87-148">標誌檔案的最佳大小：小於 40 KB</span><span class="sxs-lookup"><span data-stu-id="b9c87-148">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="b9c87-149">標誌影像的最佳大小：170x70 圖元。</span><span class="sxs-lookup"><span data-stu-id="b9c87-149">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="b9c87-150">如果您的影像超過這些尺寸，服務會重新調整您的徽標以在入口網站中顯示。</span><span class="sxs-lookup"><span data-stu-id="b9c87-150">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="b9c87-151">服務不會修改圖形檔案本身。</span><span class="sxs-lookup"><span data-stu-id="b9c87-151">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="b9c87-152">為了獲得最佳結果，請使用最佳大小。</span><span class="sxs-lookup"><span data-stu-id="b9c87-152">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="b9c87-153">寄件者名稱和電子郵件地址旁的文字</span><span class="sxs-lookup"><span data-stu-id="b9c87-153">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="b9c87-154">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-154">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="b9c87-155">出現在「讀取訊息」按鈕上的文字</span><span class="sxs-lookup"><span data-stu-id="b9c87-155">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="b9c87-156">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-156">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="b9c87-157">出現在 [閱讀郵件] 按鈕下方的文字</span><span class="sxs-lookup"><span data-stu-id="b9c87-157">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="b9c87-158">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-158">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="b9c87-159">隱私權聲明連結的 URL</span><span class="sxs-lookup"><span data-stu-id="b9c87-159">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="b9c87-160">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-160">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="b9c87-161">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="b9c87-161">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="b9c87-162">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-162">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="b9c87-163">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="b9c87-163">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="b9c87-164">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-164">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="b9c87-165">啟用或停用此自訂範本的一次性程式碼驗證</span><span class="sxs-lookup"><span data-stu-id="b9c87-165">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="b9c87-166">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-166">**Examples:**</span></span> <br/><span data-ttu-id="b9c87-167">針對此自訂範本啟用一次 passcodes</span><span class="sxs-lookup"><span data-stu-id="b9c87-167">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="b9c87-168">針對此自訂範本停用一次 passcodes</span><span class="sxs-lookup"><span data-stu-id="b9c87-168">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="b9c87-169">啟用或停用此自訂範本的 Microsoft、Google 或 Yahoo 識別碼驗證</span><span class="sxs-lookup"><span data-stu-id="b9c87-169">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="b9c87-170">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-170">**Examples:**</span></span> <br/><span data-ttu-id="b9c87-171">啟用此自訂範本的社交 IDs</span><span class="sxs-lookup"><span data-stu-id="b9c87-171">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="b9c87-172">停用此自訂範本的社交 IDs</span><span class="sxs-lookup"><span data-stu-id="b9c87-172">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="b9c87-173">建立 OME 署名範本（高級郵件加密）</span><span class="sxs-lookup"><span data-stu-id="b9c87-173">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="b9c87-174">如果您有 Office 365 Advanced Message Encryption，您可以使用[set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) Cmdlet 為您的組織建立自訂商標範本。</span><span class="sxs-lookup"><span data-stu-id="b9c87-174">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="b9c87-175">建立範本之後，您可以使用 Set-OMEConfiguration Cmdlet 修改範本，如[modify a OME 署名範本](#modify-an-ome-branding-template)所述。</span><span class="sxs-lookup"><span data-stu-id="b9c87-175">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="b9c87-176">您可以建立多個範本。</span><span class="sxs-lookup"><span data-stu-id="b9c87-176">You can create multiple templates.</span></span>

<span data-ttu-id="b9c87-177">若要建立新的自訂品牌範本：</span><span class="sxs-lookup"><span data-stu-id="b9c87-177">To create a new custom branding template:</span></span>

1. <span data-ttu-id="b9c87-178">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b9c87-178">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="b9c87-179">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="b9c87-179">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b9c87-180">使用[set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) Cmdlet 來建立新的範本。</span><span class="sxs-lookup"><span data-stu-id="b9c87-180">Use the [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   <span data-ttu-id="b9c87-181">For example,</span><span class="sxs-lookup"><span data-stu-id="b9c87-181">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="b9c87-182">將預設署名範本傳回其原始值</span><span class="sxs-lookup"><span data-stu-id="b9c87-182">Return the default branding template to its original values</span></span>

<span data-ttu-id="b9c87-183">若要從預設範本移除所有修改（包括品牌自訂專案）等等，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b9c87-183">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="b9c87-184">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b9c87-184">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="b9c87-185">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="b9c87-185">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b9c87-186">使用[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration)中所述的**Set-OMEConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b9c87-186">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="b9c87-187">若要從 DisclaimerText、EmailText 及 PortalText 值中移除組織的署名自訂，請將值設為空字串 `""` 。</span><span class="sxs-lookup"><span data-stu-id="b9c87-187">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="b9c87-188">針對所有影像值，例如 [標誌]，將值設為 `"$null"` 。</span><span class="sxs-lookup"><span data-stu-id="b9c87-188">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="b9c87-189">下表說明加密自訂選項的預設值。</span><span class="sxs-lookup"><span data-stu-id="b9c87-189">The following table describes the encryption customization option defaults.</span></span>

   <span data-ttu-id="b9c87-190">**將加密體驗的這項功能回復為預設文字和影像**</span><span class="sxs-lookup"><span data-stu-id="b9c87-190">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="b9c87-191">**使用這些命令**</span><span class="sxs-lookup"><span data-stu-id="b9c87-191">**Use these commands**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b9c87-192">加密電子郵件隨附的預設文字</span><span class="sxs-lookup"><span data-stu-id="b9c87-192">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="b9c87-193">預設文字會出現在檢視加密郵件的指示上方。</span><span class="sxs-lookup"><span data-stu-id="b9c87-193">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> <span data-ttu-id="b9c87-194">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-194">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="b9c87-195">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="b9c87-195">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> <span data-ttu-id="b9c87-196">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-196">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="b9c87-197">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="b9c87-197">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> <span data-ttu-id="b9c87-198">**範例回復為預設值：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-198">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="b9c87-199">標誌</span><span class="sxs-lookup"><span data-stu-id="b9c87-199">Logo</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> <span data-ttu-id="b9c87-200">**範例回復為預設值：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-200">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="b9c87-201">背景色彩</span><span class="sxs-lookup"><span data-stu-id="b9c87-201">Background color</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> <span data-ttu-id="b9c87-202">**範例回復為預設值：**</span><span class="sxs-lookup"><span data-stu-id="b9c87-202">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="b9c87-203">移除自訂商標範本（高級郵件加密）</span><span class="sxs-lookup"><span data-stu-id="b9c87-203">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="b9c87-204">您只可以移除或刪除您所做的品牌範本。</span><span class="sxs-lookup"><span data-stu-id="b9c87-204">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="b9c87-205">您無法移除預設的署名範本。</span><span class="sxs-lookup"><span data-stu-id="b9c87-205">You can't remove the default branding template.</span></span>

<span data-ttu-id="b9c87-206">若要移除自訂商標範本：</span><span class="sxs-lookup"><span data-stu-id="b9c87-206">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="b9c87-207">使用組織中具有全域系統管理員許可權的公司或學校帳戶，啟動 Windows PowerShell 會話，並聯機至 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b9c87-207">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="b9c87-208">如需詳細指示，請參閱[連線到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="b9c87-208">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b9c87-209">使用**Remove-set-omeconfiguration 指令程式**，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b9c87-209">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "<OMEConfigurationIdParameter>
   ```

   <span data-ttu-id="b9c87-210">For example,</span><span class="sxs-lookup"><span data-stu-id="b9c87-210">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="b9c87-211">如需詳細資訊，請參閱[Remove-set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration)。</span><span class="sxs-lookup"><span data-stu-id="b9c87-211">For more information, see [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="b9c87-212">建立將自訂品牌套用至加密電子郵件的 Exchange 郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="b9c87-212">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

<span data-ttu-id="b9c87-213">修改預設範本或建立新的品牌範本之後，您可以建立 Exchange 郵件流程規則，以根據特定條件套用您的自訂品牌。</span><span class="sxs-lookup"><span data-stu-id="b9c87-213">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="b9c87-214">這類規則會在下列情況中套用自訂品牌：</span><span class="sxs-lookup"><span data-stu-id="b9c87-214">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="b9c87-215">如果最終使用者從 Outlook 或網頁版 outlook （先前稱為 Outlook Web App）用戶端手動加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="b9c87-215">If the email was manually encrypted by the end user from the Outlook or Outlook on the web (formerly known as Outlook Web App) clients</span></span>

- <span data-ttu-id="b9c87-216">如果電子郵件已由 Exchange 郵件流程規則或資料遺失防護原則自動加密</span><span class="sxs-lookup"><span data-stu-id="b9c87-216">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="b9c87-217">如需如何建立可套用加密之 Exchange 郵件流程規則的詳細資訊，請參閱[定義郵件流程規則，以在 Office 365 中加密電子郵件訊息](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="b9c87-217">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="b9c87-218">在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="b9c87-218">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="b9c87-219">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="b9c87-219">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="b9c87-220">在 Microsoft 365 系統管理中心中，選擇 [系統**管理中心**] [ \> **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="b9c87-220">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="b9c87-221">在 EAC 中，移至 [**郵件流程** \> **規則**]，然後選取 [**新增**新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="b9c87-221">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="b9c87-222">如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="b9c87-222">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="b9c87-223">在 [**名稱**] 中，輸入規則的名稱，例如「銷售部門的商標」。</span><span class="sxs-lookup"><span data-stu-id="b9c87-223">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="b9c87-224">在 [套用**此規則**條件] 中，選取**寄件者位於組織內部**的條件，以及您在可用條件清單中所需的其他條件。</span><span class="sxs-lookup"><span data-stu-id="b9c87-224">In **Apply this rule if**, select the condition **The sender is located inside the organization** as well as other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="b9c87-225">例如，您可能想要將特定的署名範本套用到：</span><span class="sxs-lookup"><span data-stu-id="b9c87-225">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="b9c87-226">從財務部門的成員傳送的所有加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="b9c87-226">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="b9c87-227">以特定關鍵字（如 "External" 或 "Partner"）傳送的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="b9c87-227">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="b9c87-228">傳送至特定網域的加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="b9c87-228">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="b9c87-229">從**執行下列**動作，選取 **[修改郵件安全性**套用  >  **自訂品牌] 以 OME 郵件**。</span><span class="sxs-lookup"><span data-stu-id="b9c87-229">From **Do the following**, select **Modify the message security** > **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="b9c87-230">接下來，從下拉式清單中，選取您建立或修改的品牌範本。</span><span class="sxs-lookup"><span data-stu-id="b9c87-230">Next, from the drop-down, select a branding template from those you created or modified.</span></span>

8. <span data-ttu-id="b9c87-231">選如果您除了自訂商標之外，您也想要將郵件流程規則套用加密，請選取 **[\*\*\*\*修改郵件安全性**]，然後選擇 [套用**Office 365 郵件加密和許可權保護**]。</span><span class="sxs-lookup"><span data-stu-id="b9c87-231">(Optional) If you want the mail flow rule to apply encryption in addition to the custom branding, from **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="b9c87-232">從清單中選取 RMS 範本，然後選擇 [**儲存**]，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b9c87-232">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="b9c87-233">範本清單包括所有預設範本和選項，以及您已建立供 Office 365 使用的任何自訂範本。</span><span class="sxs-lookup"><span data-stu-id="b9c87-233">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="b9c87-234">如果清單是空的，請確定您已使用[設定新的 office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)中所述的新功能，來設定 Office 365 郵件加密。</span><span class="sxs-lookup"><span data-stu-id="b9c87-234">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="b9c87-235">如需預設範本的相關資訊，請參閱設定[及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="b9c87-235">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="b9c87-236">如需有關 [**不要轉寄**] 選項的詳細資訊，請參閱[請勿轉寄選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="b9c87-236">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="b9c87-237">如需只供**加密**之選項的詳細資訊，請參閱[僅限加密選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="b9c87-237">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="b9c87-238">如果您想要指定另一個動作，請選擇 [**新增動作**]。</span><span class="sxs-lookup"><span data-stu-id="b9c87-238">Choose **add action** if you want to specify another action.</span></span>
