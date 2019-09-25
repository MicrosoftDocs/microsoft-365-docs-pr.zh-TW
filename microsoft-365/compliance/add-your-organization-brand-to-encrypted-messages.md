---
title: 将组织品牌添加到加密邮件
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 作为 Office 365 全局管理员，您可以将组织的品牌应用于组织的加密电子邮件和加密门户的内容。
ms.openlocfilehash: dd08ffad4a50cafd90f2306645e93e623b8076cd
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076760"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a><span data-ttu-id="b9990-103">將貴組織的品牌新增至您的加密郵件</span><span class="sxs-lookup"><span data-stu-id="b9990-103">Add your organization's brand to your encrypted messages</span></span>

<span data-ttu-id="b9990-104">作为 Exchange 联机或 Exchange 联机保护管理员，您可以应用公司品牌来自定义组织的 Office 365 邮件加密电子邮件的外观和加密门户的内容。</span><span class="sxs-lookup"><span data-stu-id="b9990-104">As an Exchange Online or Exchange Online Protection administrator, you can apply your company branding to customize the look of your organization's Office 365 Message Encryption email messages and the contents of the encryption portal.</span></span> <span data-ttu-id="b9990-105">使用 Get-OME 配置和设置-OME 配置 Windows PowerShell cmdlet，您可以自定义加密电子邮件收件人的查看体验的以下方面：</span><span class="sxs-lookup"><span data-stu-id="b9990-105">Using the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets, you can customize the following aspects of the viewing experience for recipients of encrypted email messages:</span></span>
  
- <span data-ttu-id="b9990-106">包含加密訊息的電子郵件簡介文字</span><span class="sxs-lookup"><span data-stu-id="b9990-106">Introductory text of the email that contains the encrypted message</span></span>

- <span data-ttu-id="b9990-107">包含加密訊息的電子郵件免責聲明文字</span><span class="sxs-lookup"><span data-stu-id="b9990-107">Disclaimer text of the email that contains the encrypted message</span></span>

- <span data-ttu-id="b9990-108">显示在 OME 门户中的文本</span><span class="sxs-lookup"><span data-stu-id="b9990-108">Text that appears in the OME portal</span></span>

- <span data-ttu-id="b9990-109">电子邮件和 OME 门户中显示的徽标</span><span class="sxs-lookup"><span data-stu-id="b9990-109">Logo that appears in the email message and OME portal</span></span>

- <span data-ttu-id="b9990-110">电子邮件和 OME 门户中的背景颜色</span><span class="sxs-lookup"><span data-stu-id="b9990-110">Background color in the email message and OME portal</span></span>

<span data-ttu-id="b9990-111">您也可以隨時回復為預設的外觀與風格。</span><span class="sxs-lookup"><span data-stu-id="b9990-111">You can also revert back to the default look and feel at any time.</span></span>

 <span data-ttu-id="b9990-112">如果希望获得更多控制，可以使用 Office 365 高级邮件加密，并为来自组织的加密电子邮件创建多个模板。</span><span class="sxs-lookup"><span data-stu-id="b9990-112">If you'd like more control, you can use Office 365 Advanced Message Encryption and create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="b9990-113">使用这些模板，您可以控制的不仅仅是电子邮件的外观，还可以控制最终用户体验的某些部分。</span><span class="sxs-lookup"><span data-stu-id="b9990-113">Using these templates, you can control more than just the look and feel of the email messages, but also control parts of the end-user experience.</span></span> <span data-ttu-id="b9990-114">例如，您可以指定应用了此模板的邮件收件人以及使用这些帐户的用户是否可以使用这些帐户登录到 Office 365 邮件加密门户。</span><span class="sxs-lookup"><span data-stu-id="b9990-114">For example, you can specify whether or not recipients of mail that have this template applied and who use Google, Yahoo, and Microsoft Accounts can use these accounts to sign in to the Office 365 Message Encryption portal.</span></span> <span data-ttu-id="b9990-115">您可以使用模板来实现多个用例，例如：</span><span class="sxs-lookup"><span data-stu-id="b9990-115">You might use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="b9990-116">每个部门的模板，如财务、销售等。</span><span class="sxs-lookup"><span data-stu-id="b9990-116">Templates for each department, such as Finance, Sales, etc.</span></span>

- <span data-ttu-id="b9990-117">不同产品的模板</span><span class="sxs-lookup"><span data-stu-id="b9990-117">Templates for different products</span></span>

- <span data-ttu-id="b9990-118">不同地理区域或国家/地区的模板</span><span class="sxs-lookup"><span data-stu-id="b9990-118">Templates for different geographical regions or countries</span></span>

- <span data-ttu-id="b9990-119">是否希望允许撤销电子邮件</span><span class="sxs-lookup"><span data-stu-id="b9990-119">Whether or not you want to allow emails to be revoked</span></span>

- <span data-ttu-id="b9990-120">是否希望发送给外部收件人的电子邮件在指定天数后过期。</span><span class="sxs-lookup"><span data-stu-id="b9990-120">Whether or not you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="b9990-121">创建模板后，可以使用 Exchange 邮件流规则将它们应用于加密的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b9990-121">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="b9990-122">如果您有 Office 365 高级邮件加密，则可以撤消使用这些模板标记的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="b9990-122">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>
  
||
|:-----|
|<span data-ttu-id="b9990-123">本文是关于 Office 365 消息加密的较大系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="b9990-123">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="b9990-124">本文面向管理员和 ITPros。</span><span class="sxs-lookup"><span data-stu-id="b9990-124">This article is intended for administrators and ITPros.</span></span> <span data-ttu-id="b9990-125">如果您只想查找有关发送或接收加密邮件的信息，请参阅[Office 365 邮件加密 （OME）](ome.md)中的文章列表，并找到最适合您需求的文章。</span><span class="sxs-lookup"><span data-stu-id="b9990-125">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span>|
||

## <a name="create-branding-templates"></a><span data-ttu-id="b9990-126">创建品牌模板</span><span class="sxs-lookup"><span data-stu-id="b9990-126">Create branding templates</span></span>

<span data-ttu-id="b9990-127">您可以使用"新建 OME 配置 cmdlet"在 Windows PowerShell 中为您的组织创建品牌模板。</span><span class="sxs-lookup"><span data-stu-id="b9990-127">You create branding templates for your organization in Windows PowerShell with the New-OMEConfiguration cmdlet.</span></span> <span data-ttu-id="b9990-128">创建模板后，可以使用 Set-OME 配置 cmdlet 定义模板部分。</span><span class="sxs-lookup"><span data-stu-id="b9990-128">Once you've created the template, you define the pieces of the template by using the Set-OMEConfiguration cmdlet.</span></span> <span data-ttu-id="b9990-129">您可以创建多个模板。</span><span class="sxs-lookup"><span data-stu-id="b9990-129">You can create multiple templates.</span></span>

![可自定义的电子邮件部件](media/ome-template-breakout.png)
  
1. <span data-ttu-id="b9990-131">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b9990-131">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="b9990-132">有关说明，请参阅[连接到交换在线电源外壳](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="b9990-132">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b9990-133">使用 New-OME 配置 cmdlet 创建新模板。</span><span class="sxs-lookup"><span data-stu-id="b9990-133">Use the New-OMEConfiguration cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   <span data-ttu-id="b9990-134">For example,</span><span class="sxs-lookup"><span data-stu-id="b9990-134">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Branding template 1"
   ```

3. <span data-ttu-id="b9990-135">定义使用 Set-OME 配置 cmdlet 刚刚定义的模板的自定义，如[Set-OME 配置](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述，或使用下表进行指导。</span><span class="sxs-lookup"><span data-stu-id="b9990-135">Define the customizations for the template you just defined by using the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration) or use the following table for guidance.</span></span>

|<span data-ttu-id="b9990-136">**若要自訂此加密經驗功能**</span><span class="sxs-lookup"><span data-stu-id="b9990-136">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="b9990-137">**使用这些命令**</span><span class="sxs-lookup"><span data-stu-id="b9990-137">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9990-138">背景色彩</span><span class="sxs-lookup"><span data-stu-id="b9990-138">Background color</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> <span data-ttu-id="b9990-139">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-139">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|<span data-ttu-id="b9990-140">商標</span><span class="sxs-lookup"><span data-stu-id="b9990-140">Logo</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> <span data-ttu-id="b9990-141">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-141">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="b9990-142">支援的檔案格式：.png、.jpg、.bmp 或 .tiff</span><span class="sxs-lookup"><span data-stu-id="b9990-142">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="b9990-143">標誌檔案的最佳大小：小於 40 KB</span><span class="sxs-lookup"><span data-stu-id="b9990-143">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="b9990-144">標誌影像的最佳大小：170x70 像素</span><span class="sxs-lookup"><span data-stu-id="b9990-144">Optimal size of logo image: 170x70 pixels</span></span>|
|<span data-ttu-id="b9990-145">发件人姓名和电子邮件地址旁边的文本</span><span class="sxs-lookup"><span data-stu-id="b9990-145">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="b9990-146">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-146">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="b9990-147">"阅读消息"按钮上显示的文本</span><span class="sxs-lookup"><span data-stu-id="b9990-147">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="b9990-148">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-148">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="b9990-149">显示在"阅读消息"按钮下方的文本</span><span class="sxs-lookup"><span data-stu-id="b9990-149">Text that appears above below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="b9990-150">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-150">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="b9990-151">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="b9990-151">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="b9990-152">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-152">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="b9990-153">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="b9990-153">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="b9990-154">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-154">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="b9990-155">使用此自定义模板的一次性密码启用或禁用身份验证</span><span class="sxs-lookup"><span data-stu-id="b9990-155">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="b9990-156">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-156">**Examples:**</span></span> <br/><span data-ttu-id="b9990-157">为此自定义模板启用一次性密码</span><span class="sxs-lookup"><span data-stu-id="b9990-157">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="b9990-158">禁用此自定义模板的一次性密码</span><span class="sxs-lookup"><span data-stu-id="b9990-158">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="b9990-159">启用或禁用此自定义模板的 Microsoft、Google 或 Yahoo 标识的身份验证</span><span class="sxs-lookup"><span data-stu-id="b9990-159">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="b9990-160">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-160">**Examples:**</span></span> <br/><span data-ttu-id="b9990-161">为此自定义模板启用社交 ID</span><span class="sxs-lookup"><span data-stu-id="b9990-161">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="b9990-162">禁用此自定义模板的社交 ID</span><span class="sxs-lookup"><span data-stu-id="b9990-162">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a><span data-ttu-id="b9990-163">从 OME 门户中删除品牌自定义和由 OME 加密的电子邮件</span><span class="sxs-lookup"><span data-stu-id="b9990-163">To remove brand customizations from the OME portal and email messages encrypted by OME</span></span>
  
1. <span data-ttu-id="b9990-164">[連線至 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="b9990-164">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b9990-165">使用"**设置-OME**配置"cmdlet，[如"设置-OME 配置"](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述。</span><span class="sxs-lookup"><span data-stu-id="b9990-165">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration).</span></span> <span data-ttu-id="b9990-166">要从免责声明文本、电子邮件文本和门户文本值中删除组织的品牌自定义项，请将值设置为空字符串 。 `""`</span><span class="sxs-lookup"><span data-stu-id="b9990-166">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string,  `""`.</span></span> <span data-ttu-id="b9990-167">对于所有图像值（如徽标），将值设置为`"$null"`。</span><span class="sxs-lookup"><span data-stu-id="b9990-167">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

<span data-ttu-id="b9990-168">**加密自訂選項**</span><span class="sxs-lookup"><span data-stu-id="b9990-168">**Encryption customization options**</span></span>

<span data-ttu-id="b9990-169">**將加密體驗的這項功能回復為預設文字和影像**</span><span class="sxs-lookup"><span data-stu-id="b9990-169">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="b9990-170">**使用这些命令**</span><span class="sxs-lookup"><span data-stu-id="b9990-170">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b9990-171">加密電子郵件隨附的預設文字</span><span class="sxs-lookup"><span data-stu-id="b9990-171">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="b9990-172">預設文字會出現在檢視加密郵件的指示上方。</span><span class="sxs-lookup"><span data-stu-id="b9990-172">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> <span data-ttu-id="b9990-173">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-173">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|<span data-ttu-id="b9990-174">包含加密訊息之電子郵件中的免責聲明</span><span class="sxs-lookup"><span data-stu-id="b9990-174">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> <span data-ttu-id="b9990-175">**範例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-175">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|<span data-ttu-id="b9990-176">出現在加密郵件檢視入口網站上方的文字</span><span class="sxs-lookup"><span data-stu-id="b9990-176">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> <span data-ttu-id="b9990-177">**恢复为默认值的示例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-177">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
|<span data-ttu-id="b9990-178">商標</span><span class="sxs-lookup"><span data-stu-id="b9990-178">Logo</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> <span data-ttu-id="b9990-179">**恢复为默认值的示例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-179">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|<span data-ttu-id="b9990-180">背景色彩</span><span class="sxs-lookup"><span data-stu-id="b9990-180">Background color</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> <span data-ttu-id="b9990-181">**恢复为默认值的示例：**</span><span class="sxs-lookup"><span data-stu-id="b9990-181">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a><span data-ttu-id="b9990-182">创建将自定义品牌应用于加密电子邮件的 Exchange 邮件流规则</span><span class="sxs-lookup"><span data-stu-id="b9990-182">Create an Exchange mail flow rule that applies custom branding to encrypted emails</span></span>

<span data-ttu-id="b9990-183">创建品牌模板后，可以创建 Exchange 邮件流规则，以基于特定条件应用该自定义品牌。</span><span class="sxs-lookup"><span data-stu-id="b9990-183">After you've created a branding template, you can create Exchange mail flow rules to apply that custom branding based on certain conditions.</span></span> <span data-ttu-id="b9990-184">此类规则将在以下情况下应用自定义品牌：</span><span class="sxs-lookup"><span data-stu-id="b9990-184">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="b9990-185">如果电子邮件由来自 Web 上的 Outlook 或 Outlook 客户端（以前称为 Outlook Web 应用）客户端的最终用户手动加密</span><span class="sxs-lookup"><span data-stu-id="b9990-185">If the email was manually encrypted by the end-user from the Outlook or Outlook on the web (formerly known as Outlook Web App) clients</span></span>

- <span data-ttu-id="b9990-186">如果电子邮件由 Exchange 邮件流规则或 Office 365 数据丢失防护策略自动加密</span><span class="sxs-lookup"><span data-stu-id="b9990-186">If the email was automatically encrypted by an Exchange Mail Flow rule or Office 365 Data Loss Prevention policy</span></span>

<span data-ttu-id="b9990-187">有关如何创建应用加密的 Exchange 邮件流规则的信息，请参阅[定义邮件流规则以加密 Office 365 中的电子邮件。](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="b9990-187">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="b9990-188">在 Web 浏览器中，使用已被授予全局管理员权限的工作或学校帐户登录到[Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="b9990-188">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="b9990-189">选择"**管理员"** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="b9990-189">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="b9990-190">在微软365管理中心，选择**管理中心**\>**交换。**</span><span class="sxs-lookup"><span data-stu-id="b9990-190">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="b9990-191">在 EAC 中，**转到"邮件流**\>**规则"** 并**选择"新建"**![图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif)\>**创建新规则。**</span><span class="sxs-lookup"><span data-stu-id="b9990-191">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="b9990-192">有关使用 EAC 的详细信息，请参阅[Exchange 在线交换管理中心。](https://docs.microsoft.com/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="b9990-192">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="b9990-193">**在"名称"** 中键入规则的名称，如销售部门的"品牌"。</span><span class="sxs-lookup"><span data-stu-id="b9990-193">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="b9990-194">**在"应用此规则（如果**选择条件）中，从可用条件列表中**选择"发件人位于组织内**的条件"以及所需的其他条件。</span><span class="sxs-lookup"><span data-stu-id="b9990-194">In **Apply this rule if** select a condition, select the condition **The sender is located inside the organization** as well as other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="b9990-195">例如，您可能希望将特定的品牌模板应用于：</span><span class="sxs-lookup"><span data-stu-id="b9990-195">For example, you might want to apply a particular branding template to:</span></span>

     - <span data-ttu-id="b9990-196">来自财务部门成员发送的所有加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="b9990-196">All encrypted emails sent from members of the finance department</span></span>
     - <span data-ttu-id="b9990-197">使用特定关键字（如"外部"或"合作伙伴"）发送的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="b9990-197">Encrypted emails sent with a certain keyword such as “External” or “Partner”</span></span>
     - <span data-ttu-id="b9990-198">发送到特定域的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="b9990-198">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="b9990-199">从**执行以下内容**中，**选择"修改邮件安全性** > **将自定义品牌应用于 OME 消息"。**</span><span class="sxs-lookup"><span data-stu-id="b9990-199">From **Do the following**, select **Modify the message security** > **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="b9990-200">接下来，从下拉列表中选择一个品牌模板。</span><span class="sxs-lookup"><span data-stu-id="b9990-200">Next, from the drop-down, select a branding template from those that you created.</span></span>

8. <span data-ttu-id="b9990-201">（可选）如果希望邮件流规则在自定义品牌之外应用加密，**请选择"\*\*\*\*修改邮件安全性"，** 然后**选择"应用 Office 365 邮件加密和权限保护"。**</span><span class="sxs-lookup"><span data-stu-id="b9990-201">(Optional) If you want the mail flow rule to also apply encryption in addition to the custom branding, From **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="b9990-202">从列表中选择 RMS 模板，**选择"保存"，** 然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="b9990-202">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
     <span data-ttu-id="b9990-203">模板列表包括所有默认模板和选项，以及您为 Office 365 创建的任何自定义模板。</span><span class="sxs-lookup"><span data-stu-id="b9990-203">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="b9990-204">如果列表为空，请确保已使用"[设置新的 Office 365 邮件加密功能"](set-up-new-message-encryption-capabilities.md)中所述的新功能设置 Office 365 邮件加密。</span><span class="sxs-lookup"><span data-stu-id="b9990-204">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="b9990-205">有关默认模板的信息，请参阅[配置和管理 Azure 信息保护的模板。](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)</span><span class="sxs-lookup"><span data-stu-id="b9990-205">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="b9990-206">有关"**不转发"** 选项的信息，请参阅[电子邮件的"不转发"选项。](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="b9990-206">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="b9990-207">有关**仅加密**选项的信息，请参阅[电子邮件的"仅加密"选项。](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="b9990-207">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

     <span data-ttu-id="b9990-208">如果要指定其他操作，可以选择**添加操作。**</span><span class="sxs-lookup"><span data-stu-id="b9990-208">You can choose **add action** if you want to specify another action.</span></span>
