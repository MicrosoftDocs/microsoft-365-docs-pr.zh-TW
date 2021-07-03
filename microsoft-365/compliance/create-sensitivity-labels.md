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
description: 所有 Microsoft 資訊保護解決方案的需求：建立、設定及發佈敏感度標籤，以便分類及保護貴組織的資料。
ms.openlocfilehash: ac87608a2a7c4913811c090ae3c2befadaf2327e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286618"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="53ef2-103">建立及設定敏感度標籤及其原則</span><span class="sxs-lookup"><span data-stu-id="53ef2-103">Create and configure sensitivity labels and their policies</span></span>

><span data-ttu-id="53ef2-104">*[Microsoft 365 安全性與合規性的授權指引](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*</span><span class="sxs-lookup"><span data-stu-id="53ef2-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="53ef2-105">所有 Microsoft 資訊保護解決方案 (有時候縮寫為 MIP) 是使用[敏感度標籤](sensitivity-labels.md)來實作。</span><span class="sxs-lookup"><span data-stu-id="53ef2-105">All Microsoft Information Protection solutions (sometimes abbreviated to MIP) are implemented by using [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="53ef2-106">若要建立及發佈這些標籤，請前往 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="53ef2-106">To create and publish these labels, go to the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="53ef2-107">您也可以使用更早之前的入口網站 (Office 365 安全性與合規性中心)。</span><span class="sxs-lookup"><span data-stu-id="53ef2-107">You can also use the older portal, Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="53ef2-108">首先，建立並設定您要提供應用程式和其他服務使用的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-108">First, create and configure the sensitivity labels that you want to make available for apps and other services.</span></span> <span data-ttu-id="53ef2-109">例如，您希望使用者從 Office 應用程式看到和套用的標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-109">For example, the labels you want users to see and apply from Office apps.</span></span> 

<span data-ttu-id="53ef2-110">然後，建立一或多個包含您所設定的標籤和原則設定的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="53ef2-110">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="53ef2-111">這是為您所選的使用者和位置發佈標籤和設定的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="53ef2-111">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="53ef2-112">開始之前</span><span class="sxs-lookup"><span data-stu-id="53ef2-112">Before you begin</span></span>

<span data-ttu-id="53ef2-113">組織的全域系統管理員擁有建立及管理敏感度標籤所有層面的完整權限。</span><span class="sxs-lookup"><span data-stu-id="53ef2-113">The global admin for your organization has full permissions to create and manage all aspects of sensitivity labels.</span></span> <span data-ttu-id="53ef2-114">如果您未以全域系統管理員身分登入，請參閱[建立和管理敏感度標籤所需的權限](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="53ef2-114">If you aren't signing in as a global admin, see [Permissions required to create and manage sensitivity labels](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="53ef2-115">建立及設定敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="53ef2-115">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="53ef2-116">在標籤系統管理中心中，導覽至敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="53ef2-116">In your labeling admin center, navigate to sensitivity labels:</span></span>

    - <span data-ttu-id="53ef2-117">Microsoft 365 合規性中心：</span><span class="sxs-lookup"><span data-stu-id="53ef2-117">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="53ef2-118">**解決方案** > **資訊保護**</span><span class="sxs-lookup"><span data-stu-id="53ef2-118">**Solutions** > **Information protection**</span></span>

        <span data-ttu-id="53ef2-119">如果您沒有立即看到這個選項，請先選取 [全部顯示]。</span><span class="sxs-lookup"><span data-stu-id="53ef2-119">If you don't immediately see this option, first select **Show all**.</span></span> 

    - <span data-ttu-id="53ef2-120">安全性與合規性中心：</span><span class="sxs-lookup"><span data-stu-id="53ef2-120">Security & Compliance Center:</span></span>
        - <span data-ttu-id="53ef2-121">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="53ef2-121">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="53ef2-122">在 **[標籤]** 頁面上，選取 **[+ 建立標籤]**，以啟動 [新增敏感度標籤] 精靈。</span><span class="sxs-lookup"><span data-stu-id="53ef2-122">On the **Labels** page, select **+ Create a label** to start the New sensitivity label wizard.</span></span> 

    <span data-ttu-id="53ef2-123">例如，從 Microsoft 365 合規性中心:</span><span class="sxs-lookup"><span data-stu-id="53ef2-123">For example, from the Microsoft 365 compliance center:</span></span>

    ![建立敏感度標籤](../media/create-sensitivity-label-full.png)

    > [!NOTE]
    > <span data-ttu-id="53ef2-125">根據預設，租使用者沒有任何標籤，您必須建立它們。</span><span class="sxs-lookup"><span data-stu-id="53ef2-125">By default, tenants don't have any labels and you must create them.</span></span> <span data-ttu-id="53ef2-126">範例圖片中的標籤會顯示 [從 Azure 資訊保護中遷移的](/azure/information-protection/configure-policy-migrate-labels) 預設標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-126">The labels in the example picture show default labels that were [migrated from Azure Information Protection](/azure/information-protection/configure-policy-migrate-labels).</span></span>

3. <span data-ttu-id="53ef2-127">在 [定義此標籤的範圍 **]** 頁面上，選取的選項會決定您可以進行設定的標籤範圍，以及它們在發佈時顯示的位置：</span><span class="sxs-lookup"><span data-stu-id="53ef2-127">On the **Define the scope for this label** page, the options selected determine the label's scope for the settings that you can configure and where they will be visible when they are published:</span></span>

    ![敏感度標籤的範圍](../media/sensitivity-labels-scopes.png)

    - <span data-ttu-id="53ef2-129">如果已選取 [檔案和電子郵件 **]**，則可以在此精靈中進行設定，以套用至支援敏感度標籤的應用程式，例如 Office Word 和 Outlook。</span><span class="sxs-lookup"><span data-stu-id="53ef2-129">If **Files & emails** is selected, you can configure settings in this wizard that apply to apps that support sensitivity labels, such as Office Word and Outlook.</span></span> <span data-ttu-id="53ef2-130">如果未選取此選項，精靈會顯示這些設定的第一頁，但是您無法設定，而且使用者無法在這些應用程式中選取標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-130">If this option isn't selected, the wizard displays the first page of these settings but you can't configure them and the labels won't be available for users to select in these apps.</span></span>

    - <span data-ttu-id="53ef2-131">如果已選取 [群組和網站 **]**，則可以在此精靈中進行設定，以套用至 Microsoft 365 群組，以及 Teams 和 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="53ef2-131">If **Groups & sites** is selected, you can configure settings in this wizard that apply to Microsoft 365 groups, and sites for Teams and SharePoint.</span></span> <span data-ttu-id="53ef2-132">如果未選取此選項，精靈會顯示這些設定的第一頁，但是您無法設定，而且使用者無法為群組和網站選取標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-132">If this option isn't selected, the wizard displays the first page of these settings but you can't configure them and the labels won't be available for users to select for groups and site.</span></span>

    <span data-ttu-id="53ef2-133">如需 **Azure Purview 資產 (預覽)** 範圍的相關資訊，請參閱 [在 Azure Purview 中自動為您的內容加上標籤](/azure/purview/create-sensitivity-label)。</span><span class="sxs-lookup"><span data-stu-id="53ef2-133">For information about the **Azure Purview assets (preview)** scope, see [Automatically label your content in Azure Purview](/azure/purview/create-sensitivity-label).</span></span>

4. <span data-ttu-id="53ef2-134">按照標籤設定精靈的提示進行。</span><span class="sxs-lookup"><span data-stu-id="53ef2-134">Follow the prompts in the wizard for the label settings.</span></span>

    <span data-ttu-id="53ef2-135">如需有關標籤設定的詳細資訊，請參閱概觀資訊中的[敏感度標籤功能](sensitivity-labels.md#what-sensitivity-labels-can-do) 並為個別設定套用精靈中的幫助。</span><span class="sxs-lookup"><span data-stu-id="53ef2-135">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information and use the help in the wizard for individual settings.</span></span>

5. <span data-ttu-id="53ef2-136">重複這些步驟以建立更多標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-136">Repeat these steps to create more labels.</span></span> <span data-ttu-id="53ef2-137">不過，如果您想要建立子標籤，請先選取父標籤，並選取 **[...]** 以取得 **[其他動作]**，然後選取 **[新增子標籤]**。</span><span class="sxs-lookup"><span data-stu-id="53ef2-137">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

6. <span data-ttu-id="53ef2-138">建立好所有需要的標籤後，請檢查其順序，並視需要將它們上下移動。</span><span class="sxs-lookup"><span data-stu-id="53ef2-138">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="53ef2-139">若要變更標籤的順序，請選取 **...** 以取得 [其他動作]，然後選取 [上移] 或 [下移]。</span><span class="sxs-lookup"><span data-stu-id="53ef2-139">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="53ef2-140">如需詳細資訊，請參閱概覽資訊中的[標籤優先順序 (順序很重要)](sensitivity-labels.md#label-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="53ef2-140">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="53ef2-141">若要編輯現有的標籤，請將其選取，然後選取 **[編輯標籤]** 按鈕:</span><span class="sxs-lookup"><span data-stu-id="53ef2-141">To edit an existing label, select it, and then select the **Edit label** button:</span></span>

![編輯敏感度標籤的 [編輯標籤] 按鈕](../media/edit-sensitivity-label-full.png)

<span data-ttu-id="53ef2-143">此按鈕會啟動 [編輯敏感度標籤 **]** 精靈，它可讓您變更步驟 4 中的所有標籤設定。</span><span class="sxs-lookup"><span data-stu-id="53ef2-143">This button starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 4.</span></span>

<span data-ttu-id="53ef2-144">除非您瞭解對使用者會造成的影響，否則不要刪除標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-144">Don't delete a label unless you understand the impact for users.</span></span> <span data-ttu-id="53ef2-145">如需詳細資訊，請參閱 [移除及刪除標籤](#removing-and-deleting-labels) 一節。</span><span class="sxs-lookup"><span data-stu-id="53ef2-145">For more information, see the [Removing and deleting labels](#removing-and-deleting-labels) section.</span></span> 

> [!NOTE]
> <span data-ttu-id="53ef2-146">如果您編輯已使用標籤原則發佈的標籤，當完成精靈後便不需要額外的步驟。</span><span class="sxs-lookup"><span data-stu-id="53ef2-146">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="53ef2-147">例如，您不需要將其新增到新的標籤原則中，就能讓變更供相同的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="53ef2-147">For example, you don't need to add it to a new label policy for the changes to become available to the same users.</span></span> <span data-ttu-id="53ef2-148">不過，請允許最多 24 小時的時間讓變更複寫到所有應用程式和服務。</span><span class="sxs-lookup"><span data-stu-id="53ef2-148">However, allow up to 24 hours for the changes to replicate to all apps and services.</span></span>

<span data-ttu-id="53ef2-149">在您發佈標籤之前，無法在應用程式中或為服務選取標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-149">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="53ef2-150">若要發佈標籤，必須先[將標籤新增至標籤原則](#publish-sensitivity-labels-by-creating-a-label-policy)。</span><span class="sxs-lookup"><span data-stu-id="53ef2-150">To publish the labels, they must be [added to a label policy](#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53ef2-151">在此 [標籤] 索引標籤上，請勿選取 [發佈標籤] 索引標籤 (也不要在編輯標籤時選取 [發佈標籤] 按鈕)，除非您需要建立新的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="53ef2-151">On this **Labels** tab, do not select the **Publish labels** tab (or the **Publish label** button when you edit a label) unless you need to create a new label policy.</span></span> <span data-ttu-id="53ef2-152">只有當使用者需要不同的標籤或不同的原則設定時，才需要多個標籤原則。</span><span class="sxs-lookup"><span data-stu-id="53ef2-152">You need multiple label policies only if users need different labels or different policy settings.</span></span> <span data-ttu-id="53ef2-153">盡可能建立較少的標籤原則，只建立一個標籤原則的組織也是很常見的。</span><span class="sxs-lookup"><span data-stu-id="53ef2-153">Aim to have as few label policies as possible—it's not uncommon to have just one label policy for the organization.</span></span>

### <a name="additional-label-settings-with-security--compliance-center-powershell"></a><span data-ttu-id="53ef2-154">安全性與合規性中心 PowerShell 的其他標籤設定</span><span class="sxs-lookup"><span data-stu-id="53ef2-154">Additional label settings with Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="53ef2-155">您可以使用[安全性與合規性中心 PowerShell](/powershell/exchange/scc-powershell) 中的 [Set-Label](/powershell/module/exchange/set-label) Cmdlet 取得其他標籤設定。</span><span class="sxs-lookup"><span data-stu-id="53ef2-155">Additional label settings are available with the [Set-Label](/powershell/module/exchange/set-label) cmdlet from [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

<span data-ttu-id="53ef2-156">例如：</span><span class="sxs-lookup"><span data-stu-id="53ef2-156">For example:</span></span>

- <span data-ttu-id="53ef2-157">對跨國部署使用 *LocaleSettings* 參數，以便使用者能夠利用本地語言查看標籤名稱和工具提示。</span><span class="sxs-lookup"><span data-stu-id="53ef2-157">Use the *LocaleSettings* parameter for multinational deployments so that users see the label name and tooltip in their local language.</span></span> <span data-ttu-id="53ef2-158">[下列章節](#example-configuration-to-configure-a-sensitivity-label-for-different-languages)含有為法文、義大利文與德文指定標籤名稱和工具提示文字的範例設定。</span><span class="sxs-lookup"><span data-stu-id="53ef2-158">The [following section](#example-configuration-to-configure-a-sensitivity-label-for-different-languages) has an example configuration that specifies the label name and tooltip text for French, Italian, and German.</span></span>

- <span data-ttu-id="53ef2-159">僅針對 Azure 資訊保護的整合式標籤用戶端，指定包括設定標籤色彩的[進階設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)，並在套用標籤時套用自訂屬性。</span><span class="sxs-lookup"><span data-stu-id="53ef2-159">For the Azure Information Protection unified labeling client only, specify [advanced settings](/azure/information-protection/rms-client/clientv2-admin-guide-customizations) that include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="53ef2-160">如需完整清單，請參閱本用戶端的系統管理指南中的[標籤可用的進階設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)。</span><span class="sxs-lookup"><span data-stu-id="53ef2-160">For the full list, see [Available advanced settings for labels](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels) from this client's admin guide.</span></span>

#### <a name="example-configuration-to-configure-a-sensitivity-label-for-different-languages"></a><span data-ttu-id="53ef2-161">設定不同語言敏感度標籤的設定範例</span><span class="sxs-lookup"><span data-stu-id="53ef2-161">Example configuration to configure a sensitivity label for different languages</span></span>

<span data-ttu-id="53ef2-162">下列範例顯示名為「公開」標籤的 PowerShell 設定，其中包含工具提示的預留位置文字。</span><span class="sxs-lookup"><span data-stu-id="53ef2-162">The following example shows the PowerShell configuration for a label named "Public" with placeholder text for the tooltip.</span></span> <span data-ttu-id="53ef2-163">在此範例中，標籤名稱和工具提示文字設定為法文、義大利文和德文。</span><span class="sxs-lookup"><span data-stu-id="53ef2-163">In this example, the label name and tooltip text are configured for French, Italian, and German.</span></span>

<span data-ttu-id="53ef2-164">由於這項設定，若使用者具有使用這些顯示語言的 Office 應用程式，則會以相同的語言查看其標籤名稱和工具提示。</span><span class="sxs-lookup"><span data-stu-id="53ef2-164">As a result of this configuration, users who have Office apps that use those display languages see their label names and tooltips in the same language.</span></span> <span data-ttu-id="53ef2-165">同樣地，如果您已安裝 Azure 資訊保護的整合標籤用戶端，以在檔案瀏覽器中為檔案加上標籤，則擁有這些語言版本 Windows 的使用者就能在使用滑鼠右鍵進行標記時，以本地語言查看其標籤名稱和工具提示。</span><span class="sxs-lookup"><span data-stu-id="53ef2-165">Similarly, if you have the Azure Information Protection unified labeling client installed to label files from File Explorer, users who have those language versions of Windows see their label names and tooltips in their local language when they use the right-click actions for labeling.</span></span>

<span data-ttu-id="53ef2-166">針對需要支援的語言，請使用 Office [語言識別項](/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (又稱為語言標籤)，然後為標籤名稱和工具提示指定自己的翻譯。</span><span class="sxs-lookup"><span data-stu-id="53ef2-166">For the languages that you need to support, use the Office [language identifiers](/deployoffice/office2016/language-identifiers-and-optionstate-id-values-in-office-2016#language-identifiers) (also known as language tags), and specify your own translation for the label name and tooltip.</span></span>

<span data-ttu-id="53ef2-167">在 PowerShell 中執行命令之前，您必須先[連線至安全性與合規性中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="53ef2-167">Before you run the commands in PowerShell, you must first [connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

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
$TooltipLocaleSettings = [PSCustomObject]@{LocaleKey='Tooltip';
Settings=@(
@{key=$Languages[0];Value=$Tooltips[0];}
@{key=$Languages[1];Value=$Tooltips[1];}
@{key=$Languages[2];Value=$Tooltips[2];})}
Set-Label -Identity $Label -LocaleSettings (ConvertTo-Json $DisplayNameLocaleSettings -Depth 3 -Compress),(ConvertTo-Json $TooltipLocaleSettings -Depth 3 -Compress)
```

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="53ef2-168">建立標籤原則來發佈敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="53ef2-168">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="53ef2-169">在標籤系統管理中心中，導覽至敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="53ef2-169">In your labeling admin center, navigate to sensitivity labels:</span></span>

    - <span data-ttu-id="53ef2-170">Microsoft 365 合規性中心：</span><span class="sxs-lookup"><span data-stu-id="53ef2-170">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="53ef2-171">**解決方案** > **資訊保護**</span><span class="sxs-lookup"><span data-stu-id="53ef2-171">**Solutions** > **Information protection**</span></span>

        <span data-ttu-id="53ef2-172">如果您沒有立即看到這個選項，請先選取 [全部顯示]。</span><span class="sxs-lookup"><span data-stu-id="53ef2-172">If you don't immediately see this option, first select **Show all**.</span></span> 

    - <span data-ttu-id="53ef2-173">安全性與合規性中心：</span><span class="sxs-lookup"><span data-stu-id="53ef2-173">Security & Compliance Center:</span></span>
        - <span data-ttu-id="53ef2-174">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="53ef2-174">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="53ef2-175">選取 **[標籤原則]** 索引標籤，然後 **[發佈標籤]** 以開始 [建立原則] 精靈：</span><span class="sxs-lookup"><span data-stu-id="53ef2-175">Select the **Label policies** tab, and then **Publish labels** to start the Create policy wizard:</span></span>

    <span data-ttu-id="53ef2-176">例如，從 Microsoft 365 合規性中心:</span><span class="sxs-lookup"><span data-stu-id="53ef2-176">For example, from the Microsoft 365 compliance center:</span></span>

    ![發佈標籤](../media/publish-sensitivity-labels-full.png)

    > [!NOTE]
    > <span data-ttu-id="53ef2-178">根據預設，租使用者沒有任何標籤原則，您必須建立它們。</span><span class="sxs-lookup"><span data-stu-id="53ef2-178">By default, tenants don't have any label policies and you must create them.</span></span> 

3. <span data-ttu-id="53ef2-179">在精靈中，請選取 **[選擇要發佈的敏感度標籤]**。</span><span class="sxs-lookup"><span data-stu-id="53ef2-179">In the wizard, select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="53ef2-180">選取您要在應用程式和服務中提供使用的標籤，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="53ef2-180">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="53ef2-181">如果您選取子標籤，請確定您也選取其上層標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-181">If you select a sublabel, make sure you also select its parent label.</span></span>

4. <span data-ttu-id="53ef2-182">檢閱選取的標籤，若要進行任何變更，請選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="53ef2-182">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="53ef2-183">否則請選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="53ef2-183">Otherwise, select **Next**.</span></span>

5. <span data-ttu-id="53ef2-184">遵循提示來設定原則設定。</span><span class="sxs-lookup"><span data-stu-id="53ef2-184">Follow the prompts to configure the policy settings.</span></span>

    <span data-ttu-id="53ef2-185">您看到的原則設定會符您選取的標籤範圍。</span><span class="sxs-lookup"><span data-stu-id="53ef2-185">The policy settings that you see match the scope of the labels that you selected.</span></span> <span data-ttu-id="53ef2-186">例如，如果您選取的標籤只含有 [檔案和電子郵件 **]** 範圍，您就不會看到 [預設將此標籤套用到群組與網站 **]** 和 [要求使用者將標籤套用到群組與網站 **]**。</span><span class="sxs-lookup"><span data-stu-id="53ef2-186">For example, if you selected labels that have just the **Files & emails** scope, you don't see the policy settings **Apply this label by default to groups and sites** and **Require users to apply a label to their groups and sites**.</span></span>

    <span data-ttu-id="53ef2-187">如需有關這些設定的詳細資訊，請參閱概觀資訊中的[標籤原則的功能](sensitivity-labels.md#what-label-policies-can-do)，並使用個別設定的精靈中的說明。</span><span class="sxs-lookup"><span data-stu-id="53ef2-187">For more information about these settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information and use the help in the wizard for individual settings.</span></span>

    <span data-ttu-id="53ef2-188">針對為 **Azure Purview 資產 (預覽)** 設定的標籤：這些標籤沒有任何相關聯的原則設定。</span><span class="sxs-lookup"><span data-stu-id="53ef2-188">For labels configured for **Azure Purview assets (preview)**: These labels don't have any associated policy settings.</span></span>

6. <span data-ttu-id="53ef2-189">如果不同的使用者或範圍需要不同的原則設定，請重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="53ef2-189">Repeat these steps if you need different policy settings for different users or scopes.</span></span> <span data-ttu-id="53ef2-190">例如，您需要一組使用者有額外的標籤，或使用者的子集有不同的預設標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-190">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span> <span data-ttu-id="53ef2-191">或者，如果您已將標籤設定為具有不同範圍。</span><span class="sxs-lookup"><span data-stu-id="53ef2-191">Or, if you have configured labels to have different scopes.</span></span>

7. <span data-ttu-id="53ef2-192">如果您建立可能會導致使用者發生衝突的多個標籤原則，請檢閱原則順序，並視需要將它們上下移動。</span><span class="sxs-lookup"><span data-stu-id="53ef2-192">If you create more than one label policy that might result in a conflict for a user, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="53ef2-193">若要變更標籤原則的順序，請選取 **...** 以取得 **[其他動作]**，然後選取 **[上移]** 或 **[下移]**。</span><span class="sxs-lookup"><span data-stu-id="53ef2-193">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="53ef2-194">如需詳細資訊，請參閱概觀資訊中的 [標籤原則優先順序 (順序很重要)](sensitivity-labels.md#label-policy-priority-order-matters)。</span><span class="sxs-lookup"><span data-stu-id="53ef2-194">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="53ef2-195">完成精靈即會自動發佈標籤原則。</span><span class="sxs-lookup"><span data-stu-id="53ef2-195">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="53ef2-196">若要對已發佈的原則進行變更，只要編輯即可。</span><span class="sxs-lookup"><span data-stu-id="53ef2-196">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="53ef2-197">沒有特定的發佈或重新發佈動作可供您選取。</span><span class="sxs-lookup"><span data-stu-id="53ef2-197">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="53ef2-198">若要編輯現有的標籤原則，請將其選取，然後選取 **[編輯原則]** 按鈕:</span><span class="sxs-lookup"><span data-stu-id="53ef2-198">To edit an existing label policy, select it, and then select the **Edit Policy** button:</span></span> 

![編輯敏感度標籤](../media/edit-sensitivity-label-policy-full.png)

<span data-ttu-id="53ef2-200">這個按鈕會啟動 **[建立原則]** 精靈，這會讓您可以編輯要包含的標籤和標籤設定。</span><span class="sxs-lookup"><span data-stu-id="53ef2-200">This button starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="53ef2-201">完成精靈時，任何變更都會自動複寫到選取的使用者和服務。</span><span class="sxs-lookup"><span data-stu-id="53ef2-201">When you complete the wizard, any changes are automatically replicated to the selected users and services.</span></span>

<span data-ttu-id="53ef2-p125">當您使用在 Windows、macOS、iOS 和 Android 上適用於 Office 應用程式的內建標籤時，使用者可在四小時內查看新標籤，而當您重新整理瀏覽器時，使用者可在一小時內於網頁版 Word、Excel 和 PowerPoint 中查看新標籤。不過，最多允許 24 小時的時間，讓變更複製到所有應用程式和服務。</span><span class="sxs-lookup"><span data-stu-id="53ef2-p125">When you use built-in labeling for Office apps on Windows, macOS, iOS, and Android, users see new labels within four hours, and within one hour for Word, Excel, and PowerPoint on the web when you refresh the browser. However, allow up to 24 hours for changes to replicate to all apps and services.</span></span>

> [!NOTE]
> <span data-ttu-id="53ef2-204">支援敏感度標籤的其他應用程式和服務可能會根據自己的更新排程和觸發程式，進而使更新頻率高於 24 小時。</span><span class="sxs-lookup"><span data-stu-id="53ef2-204">Other apps and services that support sensitivity labels might update more frequently than 24 hours with their own update schedules and triggers for policy updates.</span></span> <span data-ttu-id="53ef2-205">請查看其文件以取得詳細資料。</span><span class="sxs-lookup"><span data-stu-id="53ef2-205">Check their documentation for details.</span></span> <span data-ttu-id="53ef2-206">例如，對於 Azure 資訊保護統一標籤用戶端，請參閱 [Azure 資訊保護用戶端詳細比較](/azure/information-protection/rms-client/use-client#detailed-comparisons-for-the-azure-information-protection-clients)資料表中的 **原則更新** 資料列。</span><span class="sxs-lookup"><span data-stu-id="53ef2-206">For example, for the Azure Information Protection unified labeling client, see the **Policy update** row in the [Detailed comparisons for the Azure Information Protection clients](/azure/information-protection/rms-client/use-client#detailed-comparisons-for-the-azure-information-protection-clients) table.</span></span>

### <a name="additional-label-policy-settings-with-security--compliance-center-powershell"></a><span data-ttu-id="53ef2-207">安全性與合規性中心 PowerShell 的其他標籤原則設定</span><span class="sxs-lookup"><span data-stu-id="53ef2-207">Additional label policy settings with Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="53ef2-208">您可以使用[安全規範中心 PowerShell](/powershell/exchange/scc-powershell) 中的 [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) 指令取得其他標籤原則設定。</span><span class="sxs-lookup"><span data-stu-id="53ef2-208">Additional label policy settings are available with the [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) cmdlet from [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).</span></span>

<span data-ttu-id="53ef2-209">Azure 資訊保護的整合標籤用戶端，支援許多 [[進階設定]](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)，其中包括從其他標籤解決方案移轉，以及在 Outlook 中可警告、證明或封鎖要傳送的電子郵件的快顯訊息。</span><span class="sxs-lookup"><span data-stu-id="53ef2-209">The Azure Information Protection unified labeling client supports many [advanced settings](/azure/information-protection/rms-client/clientv2-admin-guide-customizations) that include migrating from other labeling solutions, and pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="53ef2-210">如需完整清單，請參閱本用戶端的系統管理指南中的[標籤原則可用的進階設定](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)。</span><span class="sxs-lookup"><span data-stu-id="53ef2-210">For the full list, see [Available advanced settings for label policies](/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies) from this client's admin guide.</span></span>

## <a name="use-powershell-for-sensitivity-labels-and-their-policies"></a><span data-ttu-id="53ef2-211">將 PowerShell 用於敏感度標籤及其原則</span><span class="sxs-lookup"><span data-stu-id="53ef2-211">Use PowerShell for sensitivity labels and their policies</span></span>

<span data-ttu-id="53ef2-212">您現在可以使用 [安全規範中心 PowerShell](/powershell/exchange/scc-powershell)，建立並設定您在標記系統管理中心看到的所有設定。</span><span class="sxs-lookup"><span data-stu-id="53ef2-212">You can now use [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell) to create and configure all the settings you see in your labeling admin center.</span></span> <span data-ttu-id="53ef2-213">這表示除了將 PowerShell 用於標籤系統管理中心的設定以外，您現在可以全面編寫敏感度標籤和敏感度標籤原則的建立與維護腳本。</span><span class="sxs-lookup"><span data-stu-id="53ef2-213">This means that in addition to using PowerShell for settings that aren't available in the labeling admin centers, you can now fully script the creation and maintenance of sensitivity labels and sensitivity label policies.</span></span> 

<span data-ttu-id="53ef2-214">如需支援的參數和值，請參閱下列文件：</span><span class="sxs-lookup"><span data-stu-id="53ef2-214">See the following documentation for supported parameters and values:</span></span>

- [<span data-ttu-id="53ef2-215">New-Label</span><span class="sxs-lookup"><span data-stu-id="53ef2-215">New-Label</span></span>](/powershell/module/exchange/new-label)
- [<span data-ttu-id="53ef2-216">New-LabelPolicy</span><span class="sxs-lookup"><span data-stu-id="53ef2-216">New-LabelPolicy</span></span>](/powershell/module/exchange/new-labelpolicy)
- [<span data-ttu-id="53ef2-217">Set-Label</span><span class="sxs-lookup"><span data-stu-id="53ef2-217">Set-Label</span></span>](/powershell/module/exchange/set-label)
- [<span data-ttu-id="53ef2-218">Set-LabelPolicy</span><span class="sxs-lookup"><span data-stu-id="53ef2-218">Set-LabelPolicy</span></span>](/powershell/module/exchange/set-labelpolicy)

<span data-ttu-id="53ef2-219">如果您需要為刪除敏感度標籤或敏感度標籤原則編寫腳本，您也可以使用 [移除標籤](/powershell/module/exchange/remove-label) 和 [移除標籤原則](/powershell/module/exchange/remove-labelpolicy)。</span><span class="sxs-lookup"><span data-stu-id="53ef2-219">You can also use [Remove-Label](/powershell/module/exchange/remove-label) and [Remove-LabelPolicy](/powershell/module/exchange/remove-labelpolicy) if you need to script the deletion of sensitivity labels or sensitivity label policies.</span></span> <span data-ttu-id="53ef2-220">不過，在您刪除敏感度標籤前，請務必先閱讀下列章節。</span><span class="sxs-lookup"><span data-stu-id="53ef2-220">However, before you delete sensitivity labels, make sure you read the following section.</span></span>

## <a name="removing-and-deleting-labels"></a><span data-ttu-id="53ef2-221">移除並刪除標籤</span><span class="sxs-lookup"><span data-stu-id="53ef2-221">Removing and deleting labels</span></span>

<span data-ttu-id="53ef2-222">在生產環境中，您不太可能需要從標籤原則移除敏感度標籤，或刪除敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-222">In a production environment, it's unlikely that you will need to remove sensitivity labels from a label policy, or delete sensitivity labels.</span></span> <span data-ttu-id="53ef2-223">在初始測試階段，您可能需要執行下列其中一項動作。</span><span class="sxs-lookup"><span data-stu-id="53ef2-223">It's more likely that you might need to do one or either of these actions during an initial testing phase.</span></span> <span data-ttu-id="53ef2-224">請務必了解當您執行這些動作時，會發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="53ef2-224">Make sure you understand what happens when you do either of these actions.</span></span>

<span data-ttu-id="53ef2-225">從標籤原則移除標籤比刪除標籤的風險小，您可以在日後需要時，隨時將它新增回標籤原則：</span><span class="sxs-lookup"><span data-stu-id="53ef2-225">Removing a label from a label policy is less risky than deleting it, and you can always add it back to a label policy later if needed:</span></span>

- <span data-ttu-id="53ef2-226">當您從標籤原則中移除標籤以使該標籤不再發佈給最初指定的使用者時，下次重新整理標籤原則時，使用者將不會在 Office 應用程序中看到要選取的標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-226">When you remove a label from a label policy so that the label is no longer published to the originally specified users, the next time the label policy is refreshed, users no longer see that label to select in their Office app.</span></span> <span data-ttu-id="53ef2-227">不過，如果您已將標籤套用至文件或電子郵件，則不會從該內容移除標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-227">However, if the label has been applied to documents or emails, the label isn't removed from that content.</span></span> <span data-ttu-id="53ef2-228">標籤所套用的任何加密都會保留，而基礎保護範本仍然會發佈。</span><span class="sxs-lookup"><span data-stu-id="53ef2-228">Any encryption that was applied by the label remains and the underlying protection template remains published.</span></span> 

- <span data-ttu-id="53ef2-229">針對已移除但之前已套用至內容的標籤，使用 Word、Excel 和 PowerPoint 的內建標籤的使用者仍會在狀態列上看到已套用的標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="53ef2-229">For labels that are removed but have previously been applied to content, users who are using built-in labeling for Word, Excel, and PowerPoint, still see the applied label name on the status bar.</span></span> <span data-ttu-id="53ef2-230">同樣，已刪除且已套用至 SharePoint 網站的標籤仍會在 [敏感度] 欄中顯示標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="53ef2-230">Similarly, labels that are removed that were applied to SharePoint sites still display the label name in the **Sensitivity** column.</span></span>

<span data-ttu-id="53ef2-231">相比之下，當您刪除標籤時：</span><span class="sxs-lookup"><span data-stu-id="53ef2-231">In comparison, when you delete a label:</span></span>

- <span data-ttu-id="53ef2-232">如果標籤已套用加密，則會封存基礎保護範本，以便仍可開啟先前受保護的內容。</span><span class="sxs-lookup"><span data-stu-id="53ef2-232">If the label applied encryption, the underlying protection template is archived so that previously protected content can still be opened.</span></span> <span data-ttu-id="53ef2-233">由於此已封存保護範本，您將無法使用相同名稱建立新標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-233">Because of this archived protection template, you won't be able to create a new label with the same name.</span></span> <span data-ttu-id="53ef2-234">雖然您可以使用 [PowerShell](/powershell/module/aipservice/remove-aipservicetemplate) 來刪除保護範本，但請不要這麼做，除非您確定不需要開啟使用封存範本加密的內容。</span><span class="sxs-lookup"><span data-stu-id="53ef2-234">Although it's possible to delete a protection template by using [PowerShell](/powershell/module/aipservice/remove-aipservicetemplate), don't do this unless you're sure you don't need to open content that was encrypted with the archived template.</span></span>

- <span data-ttu-id="53ef2-235">針對桌面應用程式：中繼資料中的標籤資訊會保留，但由於無法再將標籤識別碼標示為名稱，使用者就不會看到已套用的標籤名稱 (例如，在狀態列上)，因此使用者會假設內容未加上標籤。</span><span class="sxs-lookup"><span data-stu-id="53ef2-235">For desktop apps: The label information in the metadata remains, but because a label ID to name mapping is no longer possible, users don't see the applied label name displayed (for example, on the status bar) so users will assume the content isn't labeled.</span></span> <span data-ttu-id="53ef2-236">如果標籤已套用加密，則會保留加密，而在內容開啟時使用者仍可看到目前封存保護範本的名稱與描述。</span><span class="sxs-lookup"><span data-stu-id="53ef2-236">If the label applied encryption, the encryption remains and when the content is opened, users still see the name and description of the now archived protection template.</span></span>

- <span data-ttu-id="53ef2-237">針對 Office 網頁版：使用者在狀態列或 **[敏感度]** 欄位中不會看到標籤名稱。</span><span class="sxs-lookup"><span data-stu-id="53ef2-237">For Office on the web: Users don't see the label name on the status bar or in the **Sensitivity** column.</span></span> <span data-ttu-id="53ef2-238">只有當標籤未套用加密時，中繼資料中的標籤資訊才會保留。</span><span class="sxs-lookup"><span data-stu-id="53ef2-238">The label information in the metadata remains only if the label didn't apply encryption.</span></span> <span data-ttu-id="53ef2-239">如果標籤已套用加密，而且您已啟用[ SharePoint 和 Onedrive 的[敏感度標籤]](sensitivity-labels-sharepoint-onedrive-files.md)，則會移除中繼資料中的標籤資訊，並將加密移除。</span><span class="sxs-lookup"><span data-stu-id="53ef2-239">If the label applied encryption, and you've enabled [sensitivity labels for SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md), the label information in the metadata is removed and the encryption is removed.</span></span> 

<span data-ttu-id="53ef2-240">當您從標籤原則移除敏感度標籤或刪除敏感度標籤時，這些變更最多可能需要 24 小時的時間，才能複製到所有使用者和服務。</span><span class="sxs-lookup"><span data-stu-id="53ef2-240">When you remove a sensitivity label from a label policy, or delete a sensitivity label, these changes can take up to 24 hours to replicate to all users and services.</span></span>

## <a name="next-steps"></a><span data-ttu-id="53ef2-241">後續步驟</span><span class="sxs-lookup"><span data-stu-id="53ef2-241">Next steps</span></span>

<span data-ttu-id="53ef2-242">若要針對特定案例設定和使用敏感度標籤，請使用下列文章：</span><span class="sxs-lookup"><span data-stu-id="53ef2-242">To configure and use your sensitivity labels for specific scenarios, use the following articles:</span></span>

- [<span data-ttu-id="53ef2-243">使用敏感度標籤中的加密來限制內容的存取</span><span class="sxs-lookup"><span data-stu-id="53ef2-243">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="53ef2-244">自動將敏感度標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="53ef2-244">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="53ef2-245">對團隊、群組和網站使用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="53ef2-245">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="53ef2-246">對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="53ef2-246">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="53ef2-247">若要監視標籤的使用方式，請參閱[開始使用資料分類](data-classification-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="53ef2-247">To monitor how your labels are being used, see [Get started with data classification](data-classification-overview.md).</span></span>
