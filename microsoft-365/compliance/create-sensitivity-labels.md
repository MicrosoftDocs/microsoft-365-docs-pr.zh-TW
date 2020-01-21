---
title: 建立及發佈敏感度標籤
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
ms.openlocfilehash: 964fd20d6ada935d2a76ca0bffccc5bf46161c58
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247456"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a><span data-ttu-id="3afba-103">建立及設定敏感度標籤及其原則</span><span class="sxs-lookup"><span data-stu-id="3afba-103">Create and configure sensitivity labels and their policies</span></span>

<span data-ttu-id="3afba-104">若要建立及發佈 [[敏感度標籤]](sensitivity-labels.md)，請前往標籤系統管理中心，例如 [Microsoft 365 合規性中心](https://compliance.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="3afba-104">To create and publish your [sensitivity labels](sensitivity-labels.md), go to your labeling admin center, such as the [Microsoft 365 compliance center](https://compliance.microsoft.com/).</span></span> <span data-ttu-id="3afba-105">您也可以使用 Microsoft 365 安全性中心，或 Office 365 安全性與合規性中心。</span><span class="sxs-lookup"><span data-stu-id="3afba-105">You can also use the Microsoft 365 security center, or the Office 365 Security & Compliance Center.</span></span>

<span data-ttu-id="3afba-106">首先，建立並設定您要在 Office 應用程式和服務中提供使用的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="3afba-106">First, create and configure the sensitivity labels that you want to make available in Office apps and for services.</span></span> <span data-ttu-id="3afba-107">然後，建立一或多個包含您所設定的標籤和原則設定的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="3afba-107">Then, create one or more label policies that contain the labels and policy settings that you configure.</span></span> <span data-ttu-id="3afba-108">這是為您所選的使用者和位置發佈標籤和設定的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="3afba-108">It's the label policy that publishes the labels and settings for your chosen users and locations.</span></span>

## <a name="create-and-configure-sensitivity-labels"></a><span data-ttu-id="3afba-109">建立及設定敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="3afba-109">Create and configure sensitivity labels</span></span>

1. <span data-ttu-id="3afba-110">在標籤系統管理中心中，導覽至敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="3afba-110">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="3afba-111">Microsoft 365 合規性中心：</span><span class="sxs-lookup"><span data-stu-id="3afba-111">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="3afba-112">\*\*\*\* 解決方案 > **資訊保護 (預覽)**</span><span class="sxs-lookup"><span data-stu-id="3afba-112">**Solutions** > **Information protection (preview)**</span></span>
        
        <span data-ttu-id="3afba-113">如果您沒有立即看到這個選項，請先選取 [全部顯示]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3afba-113">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="3afba-114">Microsoft 365 安全性中心：</span><span class="sxs-lookup"><span data-stu-id="3afba-114">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="3afba-115">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="3afba-115">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="3afba-116">Office 365 安全性與合規性中心：</span><span class="sxs-lookup"><span data-stu-id="3afba-116">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="3afba-117">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="3afba-117">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="3afba-118">選取 [標籤]\*\*\*\* 索引標籤上的 [+ 建立標籤]\*\*\*\*，以啟動 [新增敏感度標籤]\*\*\*\* 精靈。</span><span class="sxs-lookup"><span data-stu-id="3afba-118">On the **Labels** tab, select **+ Create a label** to start the **New sensitivity label** wizard.</span></span>

3. <span data-ttu-id="3afba-119">按照標籤設定的提示進行。</span><span class="sxs-lookup"><span data-stu-id="3afba-119">Follow the prompts for the label settings.</span></span>
    
    <span data-ttu-id="3afba-120">如需有關標籤設定的詳細資訊，請參閱概觀資訊中的[敏感度標籤的功能](sensitivity-labels.md#what-sensitivity-labels-can-do)。</span><span class="sxs-lookup"><span data-stu-id="3afba-120">For more information about the label settings, see [What sensitivity labels can do](sensitivity-labels.md#what-sensitivity-labels-can-do) from the overview information.</span></span>

4. <span data-ttu-id="3afba-121">重複這些步驟以建立更多標籤。</span><span class="sxs-lookup"><span data-stu-id="3afba-121">Repeat these steps to create more labels.</span></span> <span data-ttu-id="3afba-122">不過，如果您想要建立子標籤，請先選取父標籤，並選取 **[...]** 以取得 **[其他動作]**，然後選取 **[新增子標籤]**。</span><span class="sxs-lookup"><span data-stu-id="3afba-122">However, if you want to create a sublabel, first select the parent label and select **...** for **More actions**, and then select **Add sub label**.</span></span>

5. <span data-ttu-id="3afba-123">建立好所有需要的標籤後，請檢查其順序，並視需要將它們上下移動。</span><span class="sxs-lookup"><span data-stu-id="3afba-123">When you have created all the labels you need, review their order and if necessary, move them up or down.</span></span> <span data-ttu-id="3afba-124">若要變更標籤的順序，請選取 **...** 以取得 [其他動作]\*\*\*\*，然後選取 [上移]\*\*\*\* 或 [下移]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3afba-124">To change the order of a label, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="3afba-125">如需詳細資訊，請參閱概覽資訊中的[標籤優先順序 (順序很重要)](sensitivity-labels.md#label-priority-order-matters) (英文)。</span><span class="sxs-lookup"><span data-stu-id="3afba-125">For more information, see [Label priority (order matters)](sensitivity-labels.md#label-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="3afba-126">若要編輯現有的標籤，請將其選取，然後選取 [編輯標籤]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3afba-126">To edit an existing label, select it, and then select **Edit label**.</span></span> <span data-ttu-id="3afba-127">這會啟動 [編輯敏感度標籤]\*\*\*\* 精靈，它可讓您變更步驟 3 中的所有標籤設定。</span><span class="sxs-lookup"><span data-stu-id="3afba-127">This starts the **Edit sensitivity label** wizard, which lets you change all the label settings in step 3.</span></span> 

> [!NOTE]
> <span data-ttu-id="3afba-128">如果您編輯已使用標籤原則發佈的標籤，當完成精靈後便不需要額外的步驟。</span><span class="sxs-lookup"><span data-stu-id="3afba-128">If you edit a label that's already published by using a label policy, no extra steps are needed when you finish the wizard.</span></span> <span data-ttu-id="3afba-129">例如，您不需要將它新增到新的標籤原則。</span><span class="sxs-lookup"><span data-stu-id="3afba-129">For example, you don't need to add it to a new label policy.</span></span> <span data-ttu-id="3afba-130">不過，請允許最多 24 小時的時間讓變更複寫到使用者和服務。</span><span class="sxs-lookup"><span data-stu-id="3afba-130">However, allow up to 24 hours for the changes to replicate to users and services.</span></span>

<span data-ttu-id="3afba-131">在您發佈標籤之前，無法在應用程式中或為服務選取標籤。</span><span class="sxs-lookup"><span data-stu-id="3afba-131">Until you publish your labels, they won't be available to select in apps or for services.</span></span> <span data-ttu-id="3afba-132">若要發佈標籤，必須先將標籤新增至標籤原則。</span><span class="sxs-lookup"><span data-stu-id="3afba-132">To publish the labels, they must be added to a label policy.</span></span>

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="3afba-133">Office 365 安全性與合規性中心 PowerShell 的其他標籤設定</span><span class="sxs-lookup"><span data-stu-id="3afba-133">Additional label settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="3afba-134">您可以從 [Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) 使用 [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) Cmdlet 取得其他標籤設定。</span><span class="sxs-lookup"><span data-stu-id="3afba-134">Additional label settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="3afba-135">例如，使用 *LocaleSettings* 參數為您的標籤名稱和工具提示指定不同的語言。</span><span class="sxs-lookup"><span data-stu-id="3afba-135">For example, use the the *LocaleSettings* parameter to specify different languages for your label names and tooltips.</span></span> 

<span data-ttu-id="3afba-136">使用此 Cmdlet，您同時可以為 Azure 資訊保護整合標籤用戶端指定 [[進階設定]](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)。</span><span class="sxs-lookup"><span data-stu-id="3afba-136">Using this cmdlet, you can also specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="3afba-137">這些進階設定包括設定標籤色彩，以及在套用標籤時套用自訂屬性。</span><span class="sxs-lookup"><span data-stu-id="3afba-137">These advanced settings include setting a label color, and applying a custom property when a label is applied.</span></span> <span data-ttu-id="3afba-138">如需完整清單，請參閱[標籤原則可用的進階設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies)。</span><span class="sxs-lookup"><span data-stu-id="3afba-138">For the full list, see [Available advanced settings for label policies](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies).</span></span> 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a><span data-ttu-id="3afba-139">建立標籤原則來發佈敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="3afba-139">Publish sensitivity labels by creating a label policy</span></span>

1. <span data-ttu-id="3afba-140">在標籤系統管理中心中，導覽至敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="3afba-140">In your labeling admin center, navigate to sensitivity labels:</span></span>
    
    - <span data-ttu-id="3afba-141">Microsoft 365 合規性中心：</span><span class="sxs-lookup"><span data-stu-id="3afba-141">Microsoft 365 compliance center:</span></span> 
        - <span data-ttu-id="3afba-142">\*\*\*\* 解決方案 > **資訊保護 (預覽)**</span><span class="sxs-lookup"><span data-stu-id="3afba-142">**Solutions** > **Information protection (preview)**</span></span>
        
        <span data-ttu-id="3afba-143">如果您沒有立即看到這個選項，請先選取 [全部顯示]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3afba-143">If you don't immediately see this option, first select **Show all**.</span></span> 
    
    - <span data-ttu-id="3afba-144">Microsoft 365 安全性中心：</span><span class="sxs-lookup"><span data-stu-id="3afba-144">Microsoft 365 security center:</span></span> 
        - <span data-ttu-id="3afba-145">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="3afba-145">**Classification** > **Sensitivity labels**</span></span>
    
    - <span data-ttu-id="3afba-146">Office 365 安全性與合規性中心：</span><span class="sxs-lookup"><span data-stu-id="3afba-146">Office 365 Security & Compliance Center:</span></span>
        - <span data-ttu-id="3afba-147">**分類** > **敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="3afba-147">**Classification** > **Sensitivity labels**</span></span>

2. <span data-ttu-id="3afba-148">選取 **[標籤原則]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="3afba-148">Select the **Label policies** tab.</span></span>

3. <span data-ttu-id="3afba-149">選取 **[發佈標籤]** 以啟動 **[建立原則精靈]**。</span><span class="sxs-lookup"><span data-stu-id="3afba-149">Select **Publish labels** to start the **Create policy wizard**.</span></span>

4. <span data-ttu-id="3afba-150">選取 **[選擇要發佈的敏感度標籤]**。</span><span class="sxs-lookup"><span data-stu-id="3afba-150">Select **Choose sensitivity labels to publish**.</span></span> <span data-ttu-id="3afba-151">選取您要在應用程式和服務中提供使用的標籤，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="3afba-151">Select the labels that you want to make available in apps and to services, and then select **Add**.</span></span>

5. <span data-ttu-id="3afba-152">檢閱選取的標籤，若要進行任何變更，請選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="3afba-152">Review the selected labels and to make any changes, select **Edit**.</span></span> <span data-ttu-id="3afba-153">否則請選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3afba-153">Otherwise, select **Next**.</span></span>

6. <span data-ttu-id="3afba-154">遵循提示來設定原則設定。</span><span class="sxs-lookup"><span data-stu-id="3afba-154">Follow the prompts to configure the policy settings.</span></span>
    
    <span data-ttu-id="3afba-155">如需有關設定的詳細資訊，請參閱概觀資訊中的[標籤原則的功能](sensitivity-labels.md#what-label-policies-can-do) (英文)。</span><span class="sxs-lookup"><span data-stu-id="3afba-155">For more information about the settings, see [What label policies can do](sensitivity-labels.md#what-label-policies-can-do) from the overview information.</span></span>

7. <span data-ttu-id="3afba-156">如果不同的使用者或位置需要不同的原則設定，請重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="3afba-156">Repeat these steps if you need different policy settings for different users or locations.</span></span> <span data-ttu-id="3afba-157">例如，您需要一組使用者有其他標籤，或使用者的子集有不同的預設標籤。</span><span class="sxs-lookup"><span data-stu-id="3afba-157">For example, you want additional labels for a group of users, or a different default label for a subset of users.</span></span>

8. <span data-ttu-id="3afba-158">如果您建立可能會導致使用者或位置發生衝突的多個標籤原則，請檢閱原則順序，並視需要將它們上下移動。</span><span class="sxs-lookup"><span data-stu-id="3afba-158">If you create more than one label policy that might result in a conflict for a user or location, review the policy order and if necessary, move them up or down.</span></span> <span data-ttu-id="3afba-159">若要變更標籤原則的順序，請選取 **...** 以取得 **[其他動作]**，然後選取 **[上移]** 或 **[下移]**。</span><span class="sxs-lookup"><span data-stu-id="3afba-159">To change the order of a label policy, select **...** for **More actions**, and then select **Move up** or **Move down**.</span></span> <span data-ttu-id="3afba-160">如需詳細資訊，請參閱概觀資訊中的 [標籤原則優先順序 (順序很重要)](sensitivity-labels.md#label-policy-priority-order-matters) (英文)。</span><span class="sxs-lookup"><span data-stu-id="3afba-160">For more information, see [Label policy priority (order matters)](sensitivity-labels.md#label-policy-priority-order-matters) from the overview information.</span></span>

<span data-ttu-id="3afba-161">完成精靈即會自動發佈標籤原則。</span><span class="sxs-lookup"><span data-stu-id="3afba-161">Completing the wizard automatically publishes the label policy.</span></span> <span data-ttu-id="3afba-162">若要對已發佈的原則進行變更，只要編輯即可。</span><span class="sxs-lookup"><span data-stu-id="3afba-162">To make changes to a published policy, simply edit it.</span></span> <span data-ttu-id="3afba-163">沒有特定的發佈或重新發佈動作可供您選取。</span><span class="sxs-lookup"><span data-stu-id="3afba-163">There is no specific publish or republish action for you to select.</span></span>

<span data-ttu-id="3afba-164">若要編輯現有的標籤原則，請將其選取，然後選取 **[編輯原則]**。</span><span class="sxs-lookup"><span data-stu-id="3afba-164">To edit an existing label policy, select it, and then select **Edit Policy**.</span></span> <span data-ttu-id="3afba-165">這會啟動 **[建立原則]** 精靈，讓您編輯要包含的標籤和標籤設定。</span><span class="sxs-lookup"><span data-stu-id="3afba-165">This starts the **Create policy** wizard, which lets you edit which labels are included and the label settings.</span></span> <span data-ttu-id="3afba-166">完成精靈時，任何變更都會自動複寫到選取的使用者和服務。</span><span class="sxs-lookup"><span data-stu-id="3afba-166">When you complete the wizard, any changes are automatically replicated to the selected users and locations.</span></span>

<span data-ttu-id="3afba-167">通常，使用者會在幾小時內在其 Office App 中看到標籤。</span><span class="sxs-lookup"><span data-stu-id="3afba-167">Typically, users see the labels in their Office apps within a couple of hours.</span></span> <span data-ttu-id="3afba-168">不過，請允許最多 24 小時的時間讓您的標籤原則及任何其他所做變更複寫到所有使用者和服務。</span><span class="sxs-lookup"><span data-stu-id="3afba-168">However, allow up to 24 hours for your label policies and any changes to them to replicate to all users and services.</span></span>

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a><span data-ttu-id="3afba-169">Office 365 安全性與何規性中心 PowerShell 的其他標籤原則設定</span><span class="sxs-lookup"><span data-stu-id="3afba-169">Additional label policy settings with Office 365 Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="3afba-170">您可以使用來自 [Office 365 安全性與合規性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) 的 [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) Cmdlet 取得其他標籤原則設定。</span><span class="sxs-lookup"><span data-stu-id="3afba-170">Additional label policy settings are available with the [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) cmdlet from [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).</span></span>

<span data-ttu-id="3afba-171">使用此 Cmdlet，您可以為 Azure 資訊保護整合標籤用戶端指定 [[進階設定]](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)。</span><span class="sxs-lookup"><span data-stu-id="3afba-171">Using this cmdlet, you can specify [advanced settings](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) for the Azure Information Protection unified labeling client.</span></span> <span data-ttu-id="3afba-172">這些進階設定包括為 Outlook 設定不同的預設標籤，以及在 Outlook 中實作可警告、證明或封鎖要傳送的電子郵件的快顯訊息。</span><span class="sxs-lookup"><span data-stu-id="3afba-172">These advanced settings include setting a different default label for Outlook, and implement pop-up messages in Outlook that warn, justify, or block emails being sent.</span></span> <span data-ttu-id="3afba-173">如需完整清單，請參閱[標籤可用的進階設定](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels)。</span><span class="sxs-lookup"><span data-stu-id="3afba-173">For the full list, see [Available advanced settings for labels](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels).</span></span> 

<span data-ttu-id="3afba-174">您也可以使用此 Cmdlet 往返標籤原則來新增和移除標籤。</span><span class="sxs-lookup"><span data-stu-id="3afba-174">You can also use this cmdlet to add and remove labels to and from a label policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="3afba-175">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3afba-175">Next steps</span></span>

<span data-ttu-id="3afba-176">若要針對特定案例設定和使用敏感度標籤，請使用下列文章：</span><span class="sxs-lookup"><span data-stu-id="3afba-176">To configure and use your sensitivity labels for specific scenarios, see the following articles:</span></span>

- [<span data-ttu-id="3afba-177">使用敏感度標籤中的加密來限制內容的存取</span><span class="sxs-lookup"><span data-stu-id="3afba-177">Restrict access to content by using encryption in sensitivity labels</span></span>](encryption-sensitivity-labels.md)

- [<span data-ttu-id="3afba-178">自動將敏感度標籤套用到內容</span><span class="sxs-lookup"><span data-stu-id="3afba-178">Apply a sensitivity label to content automatically</span></span>](apply-sensitivity-label-automatically.md)

- [<span data-ttu-id="3afba-179">對團隊、群組和網站使用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="3afba-179">Use sensitivity labels with teams, groups, and sites</span></span>](sensitivity-labels-teams-groups-sites.md)

- [<span data-ttu-id="3afba-180">對 SharePoint 和 OneDrive 中的 Office 檔案啟用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="3afba-180">Enable sensitivity labels for Office files in SharePoint and OneDrive</span></span>](sensitivity-labels-sharepoint-onedrive-files.md)

<span data-ttu-id="3afba-181">若要監視標籤的使用方式，請參閱[利用標籤分析檢視標籤使用量](label-analytics.md) (英文)。</span><span class="sxs-lookup"><span data-stu-id="3afba-181">To monitor how your labels are being used, see [View label usage with label analytics](label-analytics.md).</span></span>