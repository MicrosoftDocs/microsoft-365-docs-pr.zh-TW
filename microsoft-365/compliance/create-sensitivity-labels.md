---
title: 建立及發佈敏感度標籤
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 建立、設定及發佈敏感度標籤的指示，以便分類及保護貴組織的文件和電子郵件。
ms.openlocfilehash: 8018c18e976d0e6f9904923471bb07c8bb3cbc40
ms.sourcegitcommit: 7d07e7ec84390a8f05034d3639fa5db912809585
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42091296"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="9703f-103">建立及設定敏感度標籤及其原則</span><span class="sxs-lookup"><span data-stu-id="9703f-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="9703f-104">若要建立及發佈 [[敏感度標籤]](sensitivity-labels.md)，請前往標籤系統管理中心，例如 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="9703f-104">To create and publish your [sensitivity labels](sensitivity-labels.md), go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="9703f-105">您也可以使用 Microsoft 365 安全性中心，或 Office 365 安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="9703f-105">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="9703f-106">首先，建立並設定您要在 Office 應用程式和服務中提供使用的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="9703f-106">First, create and configure the sensitivity labels that you want to make available in Office apps and for services.</span></span> <span data-ttu-id="9703f-107">然後，建立一或多個包含您所設定的標籤和原則設定的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="9703f-107">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="9703f-108">這是為您所選的使用者和位置發佈標籤和設定的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="9703f-108">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a><span data-ttu-id="9703f-109">建立和管理敏感度標籤所需的權限</span><span class="sxs-lookup"><span data-stu-id="9703f-109">Permissions required to create and manage sensitivity labels</span></span>

<span data-ttu-id="9703f-110">合規性小組成員會建立敏感度標籤，這些成員需要 Microsoft 365 合規性中心、Microsoft 365 安全性中心或 Office 365 安全性與合規性中心的權限。</span><span class="sxs-lookup"><span data-stu-id="9703f-110">Members of your compliance team who will create sensitivity labels need permissions to the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security & Compliance Center.</span></span> 

<span data-ttu-id="9703f-111">根據預設，您的租用戶系統管理員可以存取這些系統管理中心，並且授與法務人員和其他人員存取權限，而不需授與他們租用戶系統管理員的所有權限。如需這個委派的受限系統管理員存取權，請移至其中一個系統管理中心的 [權限]\*\*\*\* 頁面，然後將成員新增至 [合規性資料系統管理員]\*\*\*\*、[合規性系統管理員]\*\*\*\* 或 [安全性系統系統管理員]\*\*\*\* 角色群組。</span><span class="sxs-lookup"><span data-stu-id="9703f-111">By default, your tenant admin has access to these admin centers and can give compliance officers and other people access, without giving them all of the permissions of a tenant admin. For this delegated limited admin access, go to the **Permissions** page of one of these admin centers, and then add members to the **Compliance Data Administrator**, **Compliance Administrator** or **Security Administrator** role group.</span></span>

<span data-ttu-id="9703f-112">除了使用角色以外，您可以建立新的角色群組，並將 [敏感度標籤系統管理員]\*\*\*\* 或 [組織組態]\*\*\*\* 角色新增至此群組。</span><span class="sxs-lookup"><span data-stu-id="9703f-112">Alternatively to using roles, you can create a new role group and add either **Sensitivity Label Administrator** or **Organization Configuration** roles to this group.</span></span> <span data-ttu-id="9703f-113">如需相關指示，請參閱[讓使用者能夠存取 Office 365 安全規範中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。</span><span class="sxs-lookup"><span data-stu-id="9703f-113">For instructions, see [Give users access to the Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).</span></span>

<span data-ttu-id="9703f-114">只有建立及設定敏感度標籤及其標籤原則時，才需要這些權限。</span><span class="sxs-lookup"><span data-stu-id="9703f-114">These permissions are required only to create and configure sensitivity labels and their label policies.</span></span> <span data-ttu-id="9703f-115">您不需要在應用程式或服務中套用這些標籤。</span><span class="sxs-lookup"><span data-stu-id="9703f-115">They are not required to apply the labels in apps or services.</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="9703f-116">建立及設定敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="9703f-116">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="9703f-117">在標籤系統管理中心中，導覽至敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="9703f-117">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="9703f-118">Microsoft 365 合規性中心：</span><span class="sxs-lookup"><span data-stu-id="9703f-118">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="9703f-119">**解決方案** > **資訊保護**</span><span class="sxs-lookup"><span data-stu-id="9703f-119">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="9703f-120">如果您沒有立即看到這個選項，請先選取 [全部顯示]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9703f-120">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="9703f-121">Microsoft 365 安全性中心：</span><span class="sxs-lookup"><span data-stu-id="9703f-121">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="9703f-122">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="9703f-122">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="9703f-123">Office 365 安全性與合規性中心：</span><span class="sxs-lookup"><span data-stu-id="9703f-123">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="9703f-124">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="9703f-124">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="9703f-125">選取 [標籤]\*\*\*\* 索引標籤上的 [+ 建立標籤]\*\*\*\*，以啟動 [新增敏感度標籤]\*\*\*\* 精靈。</span><span class="sxs-lookup"><span data-stu-id="9703f-125">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="9703f-126">按照標籤設定的提示進行。</span><span class="sxs-lookup"><span data-stu-id="9703f-126">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="9703f-127">如需有關標籤設定的詳細資訊，請參閱概觀資訊中的[敏感度標籤的功能](sensitivity-labels.md#what-sensitivity-labels-can-do)。</span><span class="sxs-lookup"><span data-stu-id="9703f-127">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="9703f-128">重複這些步驟以建立更多標籤。</span><span class="sxs-lookup"><span data-stu-id="9703f-128">Repeat these steps to create more labels.</span></span> <span data-ttu-id="9703f-129">不過，如果您想要建立子標籤，請先選取父標籤，並選取 **[...]** 以取得 **[其他動作]**，然後選取 **[新增子標籤]**。</span><span class="sxs-lookup"><span data-stu-id="9703f-129">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="9703f-130">建立好所有需要的標籤後，請檢查其順序，並視需要將它們上下移動。</span><span class="sxs-lookup"><span data-stu-id="9703f-130">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="9703f-131">若要變更標籤的順序，請選取 **...** 以取得 [其他動作]\*\*\*\*，然後選取 [上移]\*\*\*\* 或 [下移]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9703f-131">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="9703f-132">如需詳細資訊，請參閱概覽資訊中的[標籤優先順序 (順序很重要)](sensitivity-labels.md#label-priority-order-matters) (英文)。</span><span class="sxs-lookup"><span data-stu-id="9703f-132">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="9703f-133">若要編輯現有的標籤，請將其選取，然後選取 [編輯標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9703f-133">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="9703f-134">這會啟動 [編輯敏感度標籤]\*\*\*\* 精靈，它可讓您變更步驟 3 中的所有標籤設定。</span><span class="sxs-lookup"><span data-stu-id="9703f-134">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="9703f-135">如果您編輯已使用標籤原則發佈的標籤，當完成精靈後便不需要額外的步驟。</span><span class="sxs-lookup"><span data-stu-id="9703f-135">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="9703f-136">例如，您不需要將其新增到新的標籤原則中，就能讓變更供相同的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="9703f-136">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="9703f-137">不過，請允許最多 24 小時的時間讓變更複寫到使用者和服務。</span><span class="sxs-lookup"><span data-stu-id="9703f-137">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="9703f-138">在您發佈標籤之前，無法在應用程式中或為服務選取標籤。</span><span class="sxs-lookup"><span data-stu-id="9703f-138">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="9703f-139">若要發佈標籤，必須先[將標籤新增至標籤原則](#publish-sensitivity-labels-by-creating-a-label-policy)。</span><span class="sxs-lookup"><span data-stu-id="9703f-139">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9703f-140">在此 [標籤]\*\*\*\* 索引標籤上，請勿選取 [發佈標籤]\*\*\*\* 索引標籤 (也不要在編輯標籤時選取 [發佈標籤]\*\*\*\* 按鈕)，除非您需要建立新的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="9703f-140">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="9703f-141">只有當使用者需要不同的標籤或不同的原則設定時，才需要多個標籤原則。</span><span class="sxs-lookup"><span data-stu-id="9703f-141">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="9703f-142">盡可能建立較少的標籤原則，只建立一個標籤原則的組織也是很常見的。</span><span class="sxs-lookup"><span data-stu-id="9703f-142">Aim to have as few label policies as possible — it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="9703f-143">Office 365 安全性與合規性中心 PowerShell 的其他標籤設定</span><span class="sxs-lookup"><span data-stu-id="9703f-143">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="9703f-144">您可以從 [Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) 使用 [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) Cmdlet 取得其他標籤設定。</span><span class="sxs-lookup"><span data-stu-id="9703f-144">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="9703f-145">對跨國部署使用 *LocaleSettings* 參數，以便使用者能夠利用本地語言查看標籤名稱和工具提示。</span><span class="sxs-lookup"><span data-stu-id="9703f-145">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="9703f-146">如需設定範例，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="9703f-146">See the following section for an example configuration.</span></span> 

<span data-ttu-id="9703f-147">使用此 Cmdlet，您同時可以為 Azure 資訊保護整合標籤用戶端指定 [[進階設定]](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)。</span><span class="sxs-lookup"><span data-stu-id="9703f-147">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="9703f-148">這些進階設定包括設定標籤色彩，以及在套用標籤時套用自訂屬性。</span><span class="sxs-lookup"><span data-stu-id="9703f-148">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="9703f-149">如需完整清單，請參閱[標籤原則可用的進階設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)。</span><span class="sxs-lookup"><span data-stu-id="9703f-149">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="9703f-150">設定不同語言敏感度標籤的設定範例</span><span class="sxs-lookup"><span data-stu-id="9703f-150">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="9703f-151">下列範例顯示名為「公開」標籤的 PowerShell 設定，其中包含工具提示的預留位置文字。</span><span class="sxs-lookup"><span data-stu-id="9703f-151">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="9703f-152">在此範例中，標籤名稱和工具提示文字設定為法文、義大利文和德文。</span><span class="sxs-lookup"><span data-stu-id="9703f-152">In this example, the label name and tooltip text is configured for French, Italian, and German.</span></span>

<span data-ttu-id="9703f-153">由於這項設定，若使用者具有使用這些顯示語言的 Office 應用程式，則會以相同的語言查看其標籤名稱和工具提示。</span><span class="sxs-lookup"><span data-stu-id="9703f-153">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="9703f-154">同樣地，如果您已安裝 Azure 資訊保護的整合標籤用戶端，以在檔案瀏覽器中為檔案加上標籤，則擁有這些語言版本 Windows 的使用者就能在使用滑鼠右鍵進行標記時，以本地語言查看其標籤名稱和工具提示。</span><span class="sxs-lookup"><span data-stu-id="9703f-154">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="9703f-155">針對需要支援的語言，請使用 Office [語言識別項](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (又稱為語言標籤)，然後為標籤名稱和工具提示指定自己的翻譯。</span><span class="sxs-lookup"><span data-stu-id="9703f-155">For the languages that you need to support, use the Office [language identifiers](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="9703f-156">在 PowerShell 中執行命令之前，您必須先[連線至 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="9703f-156">Before you run the commands in PowerShell, you must first [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>


```powershell
$Languages = @("fr-fr","it-it","de-de")
$DisplayNames=@("Publique","Publico","Oeffentlich")
$Tooltips = @("Texte Français","Testo italiano","Deutscher text")
$label = "Public"
$DisplayNameLocaleSettings = [PSCustomObject]@{LocaleKey='DisplayName';
Settings=@(
@{key=$Languages[0];Value=$DisplayNames[0];}
@{key=$Languages[1];Value=$DisplayNames[1];}
@{key=$Languages[2];Value=$DisplayNames[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress)
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="9703f-157">建立標籤原則來發佈敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="9703f-157">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="9703f-158">在標籤系統管理中心中，導覽至敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="9703f-158">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="9703f-159">Microsoft 365 合規性中心：</span><span class="sxs-lookup"><span data-stu-id="9703f-159">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="9703f-160">**解決方案** > **資訊保護**</span><span class="sxs-lookup"><span data-stu-id="9703f-160">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="9703f-161">如果您沒有立即看到這個選項，請先選取 [全部顯示]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9703f-161">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="9703f-162">Microsoft 365 安全性中心：</span><span class="sxs-lookup"><span data-stu-id="9703f-162">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="9703f-163">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="9703f-163">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="9703f-164">Office 365 安全性與合規性中心：</span><span class="sxs-lookup"><span data-stu-id="9703f-164">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="9703f-165">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="9703f-165">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="9703f-166">選取 **[標籤原則]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="9703f-166">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="9703f-167">選取 **[發佈標籤]** 以啟動 **[建立原則精靈]**。</span><span class="sxs-lookup"><span data-stu-id="9703f-167">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="9703f-168">選取 **[選擇要發佈的敏感度標籤]**。</span><span class="sxs-lookup"><span data-stu-id="9703f-168">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="9703f-169">選取您要在應用程式和服務中提供使用的標籤，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="9703f-169">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="9703f-170">檢閱選取的標籤，若要進行任何變更，請選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="9703f-170">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="9703f-171">否則請選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9703f-171">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="9703f-172">遵循提示來設定原則設定。</span><span class="sxs-lookup"><span data-stu-id="9703f-172">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="9703f-173">如需有關設定的詳細資訊，請參閱概觀資訊中的[標籤原則的功能](sensitivity-labels.md#what-label-policies-can-do) (英文)。</span><span class="sxs-lookup"><span data-stu-id="9703f-173">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="9703f-174">如果不同的使用者或位置需要不同的原則設定，請重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="9703f-174">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="9703f-175">例如，您需要一組使用者有其他標籤，或使用者的子集有不同的預設標籤。</span><span class="sxs-lookup"><span data-stu-id="9703f-175">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="9703f-176">如果您建立可能會導致使用者或位置發生衝突的多個標籤原則，請檢閱原則順序，並視需要將它們上下移動。</span><span class="sxs-lookup"><span data-stu-id="9703f-176">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="9703f-177">若要變更標籤原則的順序，請選取 **...** 以取得 **[其他動作]**，然後選取 **[上移]** 或 **[下移]**。</span><span class="sxs-lookup"><span data-stu-id="9703f-177">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="9703f-178">如需詳細資訊，請參閱概觀資訊中的 [標籤原則優先順序 (順序很重要)](sensitivity-labels.md#label-policy-priority-order-matters) (英文)。</span><span class="sxs-lookup"><span data-stu-id="9703f-178">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="9703f-179">完成精靈即會自動發佈標籤原則。</span><span class="sxs-lookup"><span data-stu-id="9703f-179">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="9703f-180">若要對已發佈的原則進行變更，只要編輯即可。</span><span class="sxs-lookup"><span data-stu-id="9703f-180">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="9703f-181">沒有特定的發佈或重新發佈動作可供您選取。</span><span class="sxs-lookup"><span data-stu-id="9703f-181">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="9703f-182">若要編輯現有的標籤原則，請將其選取，然後選取 **[編輯原則]**。</span><span class="sxs-lookup"><span data-stu-id="9703f-182">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="9703f-183">這會啟動 **[建立原則]** 精靈，讓您編輯要包含的標籤和標籤設定。</span><span class="sxs-lookup"><span data-stu-id="9703f-183">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="9703f-184">完成精靈時，任何變更都會自動複寫到選取的使用者和服務。</span><span class="sxs-lookup"><span data-stu-id="9703f-184">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="9703f-185">通常，使用者會在幾小時內在其 Office App 中看到標籤。</span><span class="sxs-lookup"><span data-stu-id="9703f-185">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="9703f-186">不過，請允許最多 24 小時的時間讓您的標籤原則及任何其他所做變更複寫到所有使用者和服務。</span><span class="sxs-lookup"><span data-stu-id="9703f-186">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="9703f-187">Office 365 安全性與何規性中心 PowerShell 的其他標籤原則設定</span><span class="sxs-lookup"><span data-stu-id="9703f-187">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="9703f-188">您可以使用來自 [Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) 的 [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) Cmdlet 取得其他標籤原則設定。</span><span class="sxs-lookup"><span data-stu-id="9703f-188">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="9703f-189">使用此 Cmdlet，您可以為 Azure 資訊保護整合標籤用戶端指定 [[進階設定]](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)。</span><span class="sxs-lookup"><span data-stu-id="9703f-189">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="9703f-190">這些進階設定包括為 Outlook 設定不同的預設標籤，以及在 Outlook 中實作可警告、證明或封鎖要傳送的電子郵件的快顯訊息。</span><span class="sxs-lookup"><span data-stu-id="9703f-190">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="9703f-191">如需完整清單，請參閱[標籤可用的進階設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)。</span><span class="sxs-lookup"><span data-stu-id="9703f-191">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="9703f-192">您也可以使用此 Cmdlet 往返標籤原則來新增和移除標籤。</span><span class="sxs-lookup"><span data-stu-id="9703f-192">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="9703f-193">後續步驟</span><span class="sxs-lookup"><span data-stu-id="9703f-193">Next steps</span></span>

<span data-ttu-id="9703f-194">若要針對特定案例設定和使用敏感度標籤，請使用下列文章：</span><span class="sxs-lookup"><span data-stu-id="9703f-194">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="9703f-195">使用敏感度標籤中的加密來限制內容的存取</span><span class="sxs-lookup"><span data-stu-id="9703f-195">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="9703f-196">自動將敏感度標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="9703f-196">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="9703f-197">對團隊、群組和網站使用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="9703f-197">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="9703f-198">對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="9703f-198">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="9703f-199">若要監視標籤的使用方式，請參閱[利用標籤分析檢視標籤使用量](label-analytics.md) (英文)。</span><span class="sxs-lookup"><span data-stu-id="9703f-199">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>
