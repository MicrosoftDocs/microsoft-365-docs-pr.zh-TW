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
description: 所有 Microsoft 資訊保護解決方案的需求：建立、設定及發佈敏感度標籤，以便分類及保護貴組織的文件和電子郵件。
ms.openlocfilehash: b3f998ec7f52403c4b3676fb08976aacdc1f7d0f
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/13/2020
ms.locfileid: "42635181"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="e541a-103">建立及設定敏感度標籤及其原則</span><span class="sxs-lookup"><span data-stu-id="e541a-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="e541a-104">所有 Microsoft 資訊保護解決方案 (有時候縮寫為 MIP) 是使用[敏感度標籤](sensitivity-labels.md)來實作。</span><span class="sxs-lookup"><span data-stu-id="e541a-104">All Microsoft Information Protection solutions (sometimes abbreviated to MIP) are implemented by using [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="e541a-105">若要建立及發佈這些標籤，請前往標籤系統管理中心，例如 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="e541a-105">To create and publish these labels, go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="e541a-106">您也可以使用 Microsoft 365 安全性中心，或 Office 365 安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="e541a-106">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="e541a-107">首先，建立並設定您要提供應用程式和其他服務使用的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="e541a-107">First, create and configure the sensitivity labels that you want to make available for apps and other services.</span></span> <span data-ttu-id="e541a-108">例如，您希望使用者從 Office 應用程式看到和套用的標籤。</span><span class="sxs-lookup"><span data-stu-id="e541a-108">For example, the labels you want users to see and apply from Office apps.</span></span> 

<span data-ttu-id="e541a-109">然後，建立一或多個包含您所設定的標籤和原則設定的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="e541a-109">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="e541a-110">這是為您所選的使用者和位置發佈標籤和設定的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="e541a-110">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="e541a-111">開始之前</span><span class="sxs-lookup"><span data-stu-id="e541a-111">Before you begin</span></span>

<span data-ttu-id="e541a-112">組織的全域系統管理員擁有建立及管理敏感度標籤所有層面的完整權限。</span><span class="sxs-lookup"><span data-stu-id="e541a-112">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="e541a-113">如果您未以全域系統管理員身分登入，請參閱[建立和管理敏感度標籤所需的權限](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="e541a-113">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="e541a-114">建立及設定敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="e541a-114">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="e541a-115">在標籤系統管理中心中，導覽至敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="e541a-115">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="e541a-116">Microsoft 365 合規性中心：</span><span class="sxs-lookup"><span data-stu-id="e541a-116">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="e541a-117">**解決方案** > **資訊保護**</span><span class="sxs-lookup"><span data-stu-id="e541a-117">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="e541a-118">如果您沒有立即看到這個選項，請先選取 [全部顯示]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e541a-118">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="e541a-119">Microsoft 365 安全性中心：</span><span class="sxs-lookup"><span data-stu-id="e541a-119">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="e541a-120">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="e541a-120">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="e541a-121">Office 365 安全性與合規性中心：</span><span class="sxs-lookup"><span data-stu-id="e541a-121">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="e541a-122">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="e541a-122">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="e541a-123">選取 [標籤]\*\*\*\* 索引標籤上的 [+ 建立標籤]\*\*\*\*，以啟動 [新增敏感度標籤]\*\*\*\* 精靈。</span><span class="sxs-lookup"><span data-stu-id="e541a-123">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="e541a-124">按照標籤設定的提示進行。</span><span class="sxs-lookup"><span data-stu-id="e541a-124">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="e541a-125">如需有關標籤設定的詳細資訊，請參閱概觀資訊中的[敏感度標籤的功能](sensitivity-labels.md#what-sensitivity-labels-can-do)。</span><span class="sxs-lookup"><span data-stu-id="e541a-125">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="e541a-126">重複這些步驟以建立更多標籤。</span><span class="sxs-lookup"><span data-stu-id="e541a-126">Repeat these steps to create more labels.</span></span> <span data-ttu-id="e541a-127">不過，如果您想要建立子標籤，請先選取父標籤，並選取 **[...]** 以取得 **[其他動作]**，然後選取 **[新增子標籤]**。</span><span class="sxs-lookup"><span data-stu-id="e541a-127">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="e541a-128">建立好所有需要的標籤後，請檢查其順序，並視需要將它們上下移動。</span><span class="sxs-lookup"><span data-stu-id="e541a-128">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="e541a-129">若要變更標籤的順序，請選取 **...** 以取得 [其他動作]\*\*\*\*，然後選取 [上移]\*\*\*\* 或 [下移]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e541a-129">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="e541a-130">如需詳細資訊，請參閱概覽資訊中的[標籤優先順序 (順序很重要)](sensitivity-labels.md#label-priority-order-matters) (英文)。</span><span class="sxs-lookup"><span data-stu-id="e541a-130">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="e541a-131">若要編輯現有的標籤，請將其選取，然後選取 [編輯標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e541a-131">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="e541a-132">這會啟動 [編輯敏感度標籤]\*\*\*\* 精靈，它可讓您變更步驟 3 中的所有標籤設定。</span><span class="sxs-lookup"><span data-stu-id="e541a-132">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="e541a-133">如果您編輯已使用標籤原則發佈的標籤，當完成精靈後便不需要額外的步驟。</span><span class="sxs-lookup"><span data-stu-id="e541a-133">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="e541a-134">例如，您不需要將其新增到新的標籤原則中，就能讓變更供相同的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="e541a-134">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="e541a-135">不過，請允許最多 24 小時的時間讓變更複寫到使用者和服務。</span><span class="sxs-lookup"><span data-stu-id="e541a-135">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="e541a-136">在您發佈標籤之前，無法在應用程式中或為服務選取標籤。</span><span class="sxs-lookup"><span data-stu-id="e541a-136">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="e541a-137">若要發佈標籤，必須先[將標籤新增至標籤原則](#publish-sensitivity-labels-by-creating-a-label-policy)。</span><span class="sxs-lookup"><span data-stu-id="e541a-137">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e541a-138">在此 [標籤]\*\*\*\* 索引標籤上，請勿選取 [發佈標籤]\*\*\*\* 索引標籤 (也不要在編輯標籤時選取 [發佈標籤]\*\*\*\* 按鈕)，除非您需要建立新的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="e541a-138">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="e541a-139">只有當使用者需要不同的標籤或不同的原則設定時，才需要多個標籤原則。</span><span class="sxs-lookup"><span data-stu-id="e541a-139">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="e541a-140">盡可能建立較少的標籤原則，只建立一個標籤原則的組織也是很常見的。</span><span class="sxs-lookup"><span data-stu-id="e541a-140">Aim to have as few label policies as possible — it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="e541a-141">Office 365 安全性與合規性中心 PowerShell 的其他標籤設定</span><span class="sxs-lookup"><span data-stu-id="e541a-141">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="e541a-142">您可以從 [Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) 使用 [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) Cmdlet 取得其他標籤設定。</span><span class="sxs-lookup"><span data-stu-id="e541a-142">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="e541a-143">對跨國部署使用 *LocaleSettings* 參數，以便使用者能夠利用本地語言查看標籤名稱和工具提示。</span><span class="sxs-lookup"><span data-stu-id="e541a-143">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="e541a-144">如需設定範例，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="e541a-144">See the following section for an example configuration.</span></span> 

<span data-ttu-id="e541a-145">使用此 Cmdlet，您同時可以為 Azure 資訊保護整合標籤用戶端指定 [[進階設定]](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)。</span><span class="sxs-lookup"><span data-stu-id="e541a-145">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="e541a-146">這些進階設定包括設定標籤色彩，以及在套用標籤時套用自訂屬性。</span><span class="sxs-lookup"><span data-stu-id="e541a-146">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="e541a-147">如需完整清單，請參閱[標籤原則可用的進階設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)。</span><span class="sxs-lookup"><span data-stu-id="e541a-147">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="e541a-148">設定不同語言敏感度標籤的設定範例</span><span class="sxs-lookup"><span data-stu-id="e541a-148">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="e541a-149">下列範例顯示名為「公開」標籤的 PowerShell 設定，其中包含工具提示的預留位置文字。</span><span class="sxs-lookup"><span data-stu-id="e541a-149">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="e541a-150">在此範例中，標籤名稱和工具提示文字設定為法文、義大利文和德文。</span><span class="sxs-lookup"><span data-stu-id="e541a-150">In this example, the label name and tooltip text is configured for French, Italian, and German.</span></span>

<span data-ttu-id="e541a-151">由於這項設定，若使用者具有使用這些顯示語言的 Office 應用程式，則會以相同的語言查看其標籤名稱和工具提示。</span><span class="sxs-lookup"><span data-stu-id="e541a-151">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="e541a-152">同樣地，如果您已安裝 Azure 資訊保護的整合標籤用戶端，以在檔案瀏覽器中為檔案加上標籤，則擁有這些語言版本 Windows 的使用者就能在使用滑鼠右鍵進行標記時，以本地語言查看其標籤名稱和工具提示。</span><span class="sxs-lookup"><span data-stu-id="e541a-152">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="e541a-153">針對需要支援的語言，請使用 Office [語言識別項](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (又稱為語言標籤)，然後為標籤名稱和工具提示指定自己的翻譯。</span><span class="sxs-lookup"><span data-stu-id="e541a-153">For the languages that you need to support, use the Office [language identifiers](https://docs.microsoft.com/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="e541a-154">在 PowerShell 中執行命令之前，您必須先[連線至 Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="e541a-154">Before you run the commands in PowerShell, you must first [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>


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

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="e541a-155">建立標籤原則來發佈敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="e541a-155">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="e541a-156">在標籤系統管理中心中，導覽至敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="e541a-156">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="e541a-157">Microsoft 365 合規性中心：</span><span class="sxs-lookup"><span data-stu-id="e541a-157">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="e541a-158">**解決方案** > **資訊保護**</span><span class="sxs-lookup"><span data-stu-id="e541a-158">**Solutions** > **Information protection**</span></span>
        
        <span data-ttu-id="e541a-159">如果您沒有立即看到這個選項，請先選取 [全部顯示]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e541a-159">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="e541a-160">Microsoft 365 安全性中心：</span><span class="sxs-lookup"><span data-stu-id="e541a-160">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="e541a-161">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="e541a-161">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="e541a-162">Office 365 安全性與合規性中心：</span><span class="sxs-lookup"><span data-stu-id="e541a-162">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="e541a-163">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="e541a-163">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="e541a-164">選取 **[標籤原則]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e541a-164">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="e541a-165">選取 **[發佈標籤]** 以啟動 **[建立原則精靈]**。</span><span class="sxs-lookup"><span data-stu-id="e541a-165">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="e541a-166">選取 **[選擇要發佈的敏感度標籤]**。</span><span class="sxs-lookup"><span data-stu-id="e541a-166">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="e541a-167">選取您要在應用程式和服務中提供使用的標籤，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="e541a-167">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="e541a-168">檢閱選取的標籤，若要進行任何變更，請選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="e541a-168">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="e541a-169">否則請選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e541a-169">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="e541a-170">遵循提示來設定原則設定。</span><span class="sxs-lookup"><span data-stu-id="e541a-170">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="e541a-171">如需有關設定的詳細資訊，請參閱概觀資訊中的[標籤原則的功能](sensitivity-labels.md#what-label-policies-can-do) (英文)。</span><span class="sxs-lookup"><span data-stu-id="e541a-171">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="e541a-172">如果不同的使用者或位置需要不同的原則設定，請重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="e541a-172">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="e541a-173">例如，您需要一組使用者有其他標籤，或使用者的子集有不同的預設標籤。</span><span class="sxs-lookup"><span data-stu-id="e541a-173">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="e541a-174">如果您建立可能會導致使用者或位置發生衝突的多個標籤原則，請檢閱原則順序，並視需要將它們上下移動。</span><span class="sxs-lookup"><span data-stu-id="e541a-174">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="e541a-175">若要變更標籤原則的順序，請選取 **...** 以取得 **[其他動作]**，然後選取 **[上移]** 或 **[下移]**。</span><span class="sxs-lookup"><span data-stu-id="e541a-175">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="e541a-176">如需詳細資訊，請參閱概觀資訊中的 [標籤原則優先順序 (順序很重要)](sensitivity-labels.md#label-policy-priority-order-matters) (英文)。</span><span class="sxs-lookup"><span data-stu-id="e541a-176">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="e541a-177">完成精靈即會自動發佈標籤原則。</span><span class="sxs-lookup"><span data-stu-id="e541a-177">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="e541a-178">若要對已發佈的原則進行變更，只要編輯即可。</span><span class="sxs-lookup"><span data-stu-id="e541a-178">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="e541a-179">沒有特定的發佈或重新發佈動作可供您選取。</span><span class="sxs-lookup"><span data-stu-id="e541a-179">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="e541a-180">若要編輯現有的標籤原則，請將其選取，然後選取 **[編輯原則]**。</span><span class="sxs-lookup"><span data-stu-id="e541a-180">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="e541a-181">這會啟動 **[建立原則]** 精靈，讓您編輯要包含的標籤和標籤設定。</span><span class="sxs-lookup"><span data-stu-id="e541a-181">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="e541a-182">完成精靈時，任何變更都會自動複寫到選取的使用者和服務。</span><span class="sxs-lookup"><span data-stu-id="e541a-182">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="e541a-183">通常，使用者會在幾小時內在其 Office App 中看到標籤。</span><span class="sxs-lookup"><span data-stu-id="e541a-183">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="e541a-184">不過，請允許最多 24 小時的時間讓您的標籤原則及任何其他所做變更複寫到所有使用者和服務。</span><span class="sxs-lookup"><span data-stu-id="e541a-184">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="e541a-185">Office 365 安全性與何規性中心 PowerShell 的其他標籤原則設定</span><span class="sxs-lookup"><span data-stu-id="e541a-185">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="e541a-186">您可以使用來自 [Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) 的 [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) Cmdlet 取得其他標籤原則設定。</span><span class="sxs-lookup"><span data-stu-id="e541a-186">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="e541a-187">使用此 Cmdlet，您可以為 Azure 資訊保護整合標籤用戶端指定 [[進階設定]](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)。</span><span class="sxs-lookup"><span data-stu-id="e541a-187">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="e541a-188">這些進階設定包括為 Outlook 設定不同的預設標籤，以及在 Outlook 中實作可警告、證明或封鎖要傳送的電子郵件的快顯訊息。</span><span class="sxs-lookup"><span data-stu-id="e541a-188">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="e541a-189">如需完整清單，請參閱[標籤可用的進階設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)。</span><span class="sxs-lookup"><span data-stu-id="e541a-189">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="e541a-190">您也可以使用此 Cmdlet 往返標籤原則來新增和移除標籤。</span><span class="sxs-lookup"><span data-stu-id="e541a-190">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>

## <a name="removing-and-deleting-labels"></a><span data-ttu-id="e541a-191">移除並刪除標籤</span><span class="sxs-lookup"><span data-stu-id="e541a-191">Removing and deleting labels</span></span>

<span data-ttu-id="e541a-192">在生產環境中，您不太可能需要從標籤原則移除敏感度標籤，或刪除敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="e541a-192">In a production environment, it's unlikely that you will need to remove sensitivity labels from a label policy, or delete sensitivity labels.</span></span> <span data-ttu-id="e541a-193">在初始測試階段，您可能需要執行下列其中一項動作。</span><span class="sxs-lookup"><span data-stu-id="e541a-193">It's more likely that you might need to do one or either of these actions during an initial testing phase.</span></span> <span data-ttu-id="e541a-194">請務必了解當您執行這些動作時，會發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="e541a-194">Make sure you understand what happens when you do either of these actions.</span></span>

<span data-ttu-id="e541a-195">從標籤原則移除標籤比刪除標籤的風險小，您可以在日後需要時，隨時將它新增回標籤原則：</span><span class="sxs-lookup"><span data-stu-id="e541a-195">Removing a label from a label policy is less risky than deleting it, and you can always add it back to a label policy later if needed:</span></span>

- <span data-ttu-id="e541a-196">當您從標籤原則中移除標籤以使該標籤不再發佈給最初指定的使用者時，下次重新整理標籤原則時，使用者將不會在 Office 應用程序中看到要選取的標籤。</span><span class="sxs-lookup"><span data-stu-id="e541a-196">When you remove a label from a label policy so that the label is no longer published to the originally specified users, the next time the label policy is refreshed, users no longer see that label to select in their Office app.</span></span> <span data-ttu-id="e541a-197">不過，如果您已將標籤套用至文件或電子郵件，則不會從該內容移除標籤。</span><span class="sxs-lookup"><span data-stu-id="e541a-197">However, if the label has been applied to documents or emails, the label isn't removed from that content.</span></span> <span data-ttu-id="e541a-198">標籤所套用的任何加密都會保留，而基礎保護範本仍然會發佈。</span><span class="sxs-lookup"><span data-stu-id="e541a-198">Any encryption that was applied by the label remains and the underlying protection template remains published.</span></span> 

- <span data-ttu-id="e541a-199">針對已移除但之前已套用至內容的標籤，使用 Word、Excel 和 PowerPoint 的內建標籤的使用者仍會在狀態列上看到已套用的標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="e541a-199">For labels that are removed but have previously been applied to content, users who are using built-in labeling for Word, Excel, and PowerPoint, still see the applied label name on the status bar.</span></span> <span data-ttu-id="e541a-200">同樣，已刪除且已套用至 SharePoint 網站的標籤仍會在 [敏感度]\*\*\*\* 欄中顯示標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="e541a-200">Similarly, labels that are removed that were applied to SharePoint sites still display the label name in the **Sensitivity** column.</span></span>

<span data-ttu-id="e541a-201">相比之下，當您刪除標籤時：</span><span class="sxs-lookup"><span data-stu-id="e541a-201">In comparison, when you delete a label:</span></span>

- <span data-ttu-id="e541a-202">如果標籤已套用加密，則會封存基礎保護範本，以便仍可開啟先前受保護的內容。</span><span class="sxs-lookup"><span data-stu-id="e541a-202">If the label applied encryption, the underlying protection template is archived so that previously protected content can still be opened.</span></span> <span data-ttu-id="e541a-203">由於此已封存保護範本，您將無法使用相同名稱建立新標籤。</span><span class="sxs-lookup"><span data-stu-id="e541a-203">Because of this archived protection template, you won't be able to create a new label with the same name.</span></span> <span data-ttu-id="e541a-204">雖然您可以使用 [PowerShell](https://docs.microsoft.com/powershell/module/aipservice/remove-aipservicetemplate) 來刪除保護範本，但請不要這麼做，除非您確定不需要開啟使用封存範本加密的內容。</span><span class="sxs-lookup"><span data-stu-id="e541a-204">Although it's possible to delete a protection template by using [PowerShell](https://docs.microsoft.com/powershell/module/aipservice/remove-aipservicetemplate), don't do this unless you're sure you don't need to open content that was encrypted with the archived template.</span></span>

- <span data-ttu-id="e541a-205">針對桌面應用程式：中繼資料中的標籤資訊會保留，但由於無法再將標籤識別碼標示為名稱，使用者就不會看到已套用的標籤名稱 (例如，在狀態列上)，因此使用者會假設內容未加上標籤。</span><span class="sxs-lookup"><span data-stu-id="e541a-205">For desktop apps: The label information in the metadata remains, but because a label ID to name mapping is no longer possible, users don't see the applied label name displayed (for example, on the status bar) so users will assume the content isn't labeled.</span></span> <span data-ttu-id="e541a-206">如果標籤已套用加密，則會保留加密，而在內容開啟時使用者仍可看到目前封存保護範本的名稱與描述。</span><span class="sxs-lookup"><span data-stu-id="e541a-206">If the label applied encryption, the encryption remains and when the content is opened, uses still see the name and description of the now archived protection template.</span></span>

- <span data-ttu-id="e541a-207">針對 Office 網頁版：使用者在狀態列或 [敏感度]\*\*\*\* 欄中不會看到標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="e541a-207">For Office on the web: Users don't see the label name on status bar or in the **Sensitivity** column.</span></span> <span data-ttu-id="e541a-208">只有當標籤未套用加密時，中繼資料中的標籤資訊才會保留。</span><span class="sxs-lookup"><span data-stu-id="e541a-208">The label information in the metadata remains only if the label didn't apply encryption.</span></span> <span data-ttu-id="e541a-209">如果標籤已套用加密，而且您已啟用 SharePoint 和 Onedrive 的 [敏感度標籤][](sensitivity-labels-sharepoint-onedrive-files.md)，則會移除中繼資料中的標籤資訊，並將加密移除。</span><span class="sxs-lookup"><span data-stu-id="e541a-209">If the label applied encryption, and you've enabled [sensitivity labels for SharePoint and Onedrive](sensitivity-labels-sharepoint-onedrive-files.md), the label information in the metadata is removed and the encryption is removed.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="e541a-210">後續步驟</span><span class="sxs-lookup"><span data-stu-id="e541a-210">Next steps</span></span>

<span data-ttu-id="e541a-211">若要針對特定案例設定和使用敏感度標籤，請使用下列文章：</span><span class="sxs-lookup"><span data-stu-id="e541a-211">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="e541a-212">使用敏感度標籤中的加密來限制內容的存取</span><span class="sxs-lookup"><span data-stu-id="e541a-212">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="e541a-213">自動將敏感度標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="e541a-213">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="e541a-214">對團隊、群組和網站使用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="e541a-214">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="e541a-215">對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="e541a-215">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="e541a-216">若要監視標籤的使用方式，請參閱[利用標籤分析檢視標籤使用量](label-analytics.md) (英文)。</span><span class="sxs-lookup"><span data-stu-id="e541a-216">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>
