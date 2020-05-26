---
title: 定義郵件流程規則以加密電子郵件
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: 系統管理員可以瞭解如何建立郵件流程規則（傳輸規則），以使用 Office 365 郵件加密來加密及解密郵件。
ms.openlocfilehash: 869448ff1f5161fc71d332c1b5956015dca50fa2
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351790"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a><span data-ttu-id="2b70d-103">定義郵件流程規則以加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="2b70d-103">Define mail flow rules to encrypt email messages</span></span>

<span data-ttu-id="2b70d-104">以全域管理員的身分，您可以建立郵件流程規則（也稱為傳輸規則），以協助保護您傳送和接收的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="2b70d-104">As a global administrator, you can create mail flow rules (also known as transport rules) to help protect email messages you send and receive.</span></span> <span data-ttu-id="2b70d-105">您可以設定規則來加密任何外寄電子郵件訊息，並移除來自組織內部的加密郵件的加密，或從組織傳送的加密郵件回復。</span><span class="sxs-lookup"><span data-stu-id="2b70d-105">You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> <span data-ttu-id="2b70d-106">您可以使用 Exchange 系統管理中心（EAC）或 Exchange Online PowerShell 來建立這些規則。</span><span class="sxs-lookup"><span data-stu-id="2b70d-106">You can use the Exchange admin center (EAC) or Exchange Online PowerShell to create these rules.</span></span> <span data-ttu-id="2b70d-107">除了整體加密規則，您也可以選擇啟用或停用使用者的個別郵件加密選項。</span><span class="sxs-lookup"><span data-stu-id="2b70d-107">In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end users.</span></span>

<span data-ttu-id="2b70d-108">您無法對來自組織外部寄件者的輸入郵件進行加密。</span><span class="sxs-lookup"><span data-stu-id="2b70d-108">You can't encrypt inbound mail from senders outside of your organization.</span></span>

<span data-ttu-id="2b70d-109">如果您最近從 AD RMS 遷移至 Azure 資訊保護，您必須複查現有的郵件流程規則，以確保它們繼續在您的新環境中運作。</span><span class="sxs-lookup"><span data-stu-id="2b70d-109">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment.</span></span> <span data-ttu-id="2b70d-110">此外，如果您想要利用 Azure 資訊保護可供您使用的新 Office 365 郵件加密（OME）功能，您必須更新現有的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="2b70d-110">Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules.</span></span> <span data-ttu-id="2b70d-111">否則，您的使用者將繼續接收使用舊版 HTML 附件格式的加密郵件，而不是新的無縫 OME 經驗。</span><span class="sxs-lookup"><span data-stu-id="2b70d-111">Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience.</span></span> <span data-ttu-id="2b70d-112">若尚未設定 OME，請參閱[設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2b70d-112">If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md) for information.</span></span>

<span data-ttu-id="2b70d-113">如需組成郵件流程規則的元件，以及郵件流程規則如何運作的詳細資訊，請參閱[郵件流程規則（傳輸規則）中的 Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-113">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span> <span data-ttu-id="2b70d-114">如需郵件流程規則如何使用 Azure 資訊保護的詳細資訊，請參閱設定[Exchange Online mail 流程規則以取得 azure 資訊保護標籤](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-114">For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b70d-115">在混合式 Exchange 環境中，只有在透過 Exchange Online 路由傳送電子郵件時，內部部署使用者才能使用 OME 傳送和接收加密郵件。</span><span class="sxs-lookup"><span data-stu-id="2b70d-115">For hybrid Exchange environments, on-premises users can send and receive encrypted mail using OME only if email is routed through Exchange Online.</span></span> <span data-ttu-id="2b70d-116">若要設定混合式 Exchange 環境中的 OME，您必須先[使用混合式設定向導設定混合](https://docs.microsoft.com/Exchange/exchange-hybrid)式，然後再[將郵件設定為從 Office 365 流向您的電子郵件伺服器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server)，並[將郵件設定為從您的電子郵件伺服器流向 Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-116">To configure OME in a hybrid Exchange environment, you need to first [configure hybrid using the Hybrid Configuration wizard](https://docs.microsoft.com/Exchange/exchange-hybrid) and then [configure mail to flow from Office 365 to your email server](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) and [configure mail to flow from your email server to Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).</span></span> <span data-ttu-id="2b70d-117">將郵件設定為流過 Office 365 後，您就可以使用本指南來設定 OME 的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="2b70d-117">Once you've configured mail to flow through Office 365, then you can configure mail flow rules for OME by using this guidance.</span></span>

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="2b70d-118">建立郵件流程規則，以新的 OME 功能加密電子郵件</span><span class="sxs-lookup"><span data-stu-id="2b70d-118">Create mail flow rules to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="2b70d-119">您可以使用 EAC 來定義郵件流程規則，以使用新的 OME 功能來觸發郵件加密。</span><span class="sxs-lookup"><span data-stu-id="2b70d-119">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="2b70d-120">使用 EAC 建立以新的 OME 功能加密電子郵件的規則</span><span class="sxs-lookup"><span data-stu-id="2b70d-120">Use the EAC to create a rule for encrypting email messages with the new OME capabilities</span></span>

1. <span data-ttu-id="2b70d-121">在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-121">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="2b70d-122">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="2b70d-122">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="2b70d-123">在 Microsoft 365 系統管理中心中，選擇 [系統**管理中心**] [ \> **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-123">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="2b70d-124">在 EAC 中，移至 [**郵件流程** \> **規則**]，然後選取 [**新增**新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-124">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="2b70d-125">如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-125">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="2b70d-126">在 [**名稱**] 中，輸入規則的名稱，例如 [加密 DrToniRamos@hotmail.com 的郵件]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-126">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="2b70d-127">在 [套用**此規則 if**] 中，選取條件，然後視需要輸入值。</span><span class="sxs-lookup"><span data-stu-id="2b70d-127">In **Apply this rule if**, select a condition, and enter a value if necessary.</span></span> <span data-ttu-id="2b70d-128">例如，若要加密要 DrToniRamos@hotmail.com 的郵件：</span><span class="sxs-lookup"><span data-stu-id="2b70d-128">For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="2b70d-129">在 [套用**此規則 if**] 中，選取**收件者為**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-129">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="2b70d-130">從連絡人清單中選取現有名稱，或在 [**檢查名稱**] 方塊中輸入新的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="2b70d-130">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="2b70d-131">若要選取現有名稱，請從清單中進行選取，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-131">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="2b70d-132">若要輸入新名稱，請在 [**檢查名稱**] 方塊中輸入電子郵件地址，然後選取 [**檢查名稱** \> **]**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-132">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="2b70d-133">若要新增更多條件，請選擇 [**更多選項**]，然後選擇 [**新增條件**]，然後從清單中選取。</span><span class="sxs-lookup"><span data-stu-id="2b70d-133">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span>

   <span data-ttu-id="2b70d-134">例如，若要在組織外部的收件者之外套用規則，請選取 [**新增條件**]，然後選取收件者在組織外**外部/內部的收件**者 \> **Outside the organization** \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="2b70d-134">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="2b70d-135">若要使用新的 OME 功能來啟用加密，請從**執行下列**動作，選取 **[修改郵件安全性**]，然後選擇 [套用**Office 365 郵件加密和許可權保護**]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-135">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="2b70d-136">從清單中選取 RMS 範本，然後選擇 [**儲存**]，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-136">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
  <span data-ttu-id="2b70d-137">範本清單包括所有預設範本和選項，以及您已建立供 Office 365 使用的任何自訂範本。</span><span class="sxs-lookup"><span data-stu-id="2b70d-137">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="2b70d-138">如果清單是空的，請確定您已使用[設定新的 office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)中所述的新功能，來設定 Office 365 郵件加密。</span><span class="sxs-lookup"><span data-stu-id="2b70d-138">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="2b70d-139">如需預設範本的相關資訊，請參閱設定[及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-139">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="2b70d-140">如需有關 [**不要轉寄**] 選項的詳細資訊，請參閱[請勿轉寄選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-140">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="2b70d-141">如需只供**加密**之選項的詳細資訊，請參閱[僅限加密選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-141">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

  <span data-ttu-id="2b70d-142">如果您想要指定另一個動作，您可以選擇 [**新增動作**]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-142">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a><span data-ttu-id="2b70d-143">使用 EAC 更新現有的郵件流程規則，以使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="2b70d-143">Use the EAC to update an existing mail flow rule to use the new OME capabilities</span></span>

1. <span data-ttu-id="2b70d-144">在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-144">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="2b70d-145">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="2b70d-145">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="2b70d-146">在 Microsoft 365 系統管理中心中，選擇 [系統**管理中心**] [ \> **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-146">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="2b70d-147">在 EAC 中，移至 [郵件流程]\*\*\*\* \> [規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b70d-147">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

5. <span data-ttu-id="2b70d-148">在郵件流程規則清單中，選取您要修改的規則，以使用新的 OME 功能，然後選擇 [**編輯** ![ 編輯圖示] ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。</span><span class="sxs-lookup"><span data-stu-id="2b70d-148">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

6. <span data-ttu-id="2b70d-149">若要使用新的 OME 功能來啟用加密，請從**執行下列**動作，選擇 [**修改郵件安全性**]，然後選擇 [套用**Office 365 郵件加密和許可權保護**]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-149">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="2b70d-150">從清單中選取 RMS 範本，然後選擇 [**儲存**]，然後選擇 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-150">Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>

   <span data-ttu-id="2b70d-151">範本清單包括所有預設範本和選項，以及您已建立供 Office 365 使用的任何自訂範本。</span><span class="sxs-lookup"><span data-stu-id="2b70d-151">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="2b70d-152">如果清單是空的，請確定您已設定 Office 365 郵件加密的新功能，如[設定以 Azure 資訊保護為基礎的新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。</span><span class="sxs-lookup"><span data-stu-id="2b70d-152">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="2b70d-153">如需預設範本的相關資訊，請參閱設定[及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-153">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="2b70d-154">如需有關 [**不要轉寄**] 選項的詳細資訊，請參閱[請勿轉寄選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-154">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="2b70d-155">如需只供**加密**之選項的詳細資訊，請參閱[僅限加密選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-155">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="2b70d-156">如果您想要指定另一個動作，您可以選擇 [**新增動作**]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-156">You can choose **add action** if you want to specify another action.</span></span>

7. <span data-ttu-id="2b70d-157">從 [**執行下列**動作] 清單中，移除指派給**修改郵件安全性**的任何動作套用 \> **先前版本的 OME**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-157">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>

8. <span data-ttu-id="2b70d-158">選擇 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b70d-158">Choose **Save**.</span></span>

## <a name="create-mail-flow-rules-to-remove-encryption-for-outgoing-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="2b70d-159">建立郵件流程規則，以使用新的 OME 功能移除外寄電子郵件的加密</span><span class="sxs-lookup"><span data-stu-id="2b70d-159">Create mail flow rules to remove encryption for outgoing email messages with the new OME capabilities</span></span>

<span data-ttu-id="2b70d-160">您可以使用 EAC 來定義郵件流程規則，以使用新的 OME 功能來觸發移除郵件加密。</span><span class="sxs-lookup"><span data-stu-id="2b70d-160">You can define mail flow rules for triggering remove message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="2b70d-161">使用 EAC 來建立規則，以使用新的 OME 功能來移除電子郵件中的加密</span><span class="sxs-lookup"><span data-stu-id="2b70d-161">Use the EAC to create a rule to remove encryption from email messages with the new OME capabilities</span></span>

1. <span data-ttu-id="2b70d-162">在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-162">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="2b70d-163">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="2b70d-163">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="2b70d-164">在 Microsoft 365 系統管理中心中，選擇 [系統**管理中心**] [ \> **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-164">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="2b70d-165">在 EAC 中，移至 [**郵件流程** \> **規則**]，然後選取 [**新增**新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-165">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="2b70d-166">如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-166">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="2b70d-167">在 [**名稱**] 中，輸入規則的名稱，例如 [從外寄郵件移除加密]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-167">In **Name**, type a name for the rule, such as Remove encryption from outgoing mail.</span></span>

6. <span data-ttu-id="2b70d-168">在 [套用**此規則**條件] 中，選取應該從郵件中移除加密的條件。</span><span class="sxs-lookup"><span data-stu-id="2b70d-168">In **Apply this rule if**, select the conditions where encryption should be removed from messages.</span></span> <span data-ttu-id="2b70d-169">新增**寄件者位於** \> **組織內**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-169">Add **The sender is located** \> **Inside the organization**.</span></span> <span data-ttu-id="2b70d-170">現在，新增其他條件以設定特定的收件者，例如**收件者位於** \> **組織外**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-170">Now add additional conditions to target specific recipients, such as **The recipient is located** \> **Outside the organization**.</span></span>

7. <span data-ttu-id="2b70d-171">在**執行下列**動作中，選取 **[修改郵件安全性** \> **移除 Office 365 訊息加密和許可權保護**]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-171">In **Do the following**, select **Modify the message security** \> **Remove Office 365 Message Encryption and rights protection**.</span></span>

8. <span data-ttu-id="2b70d-172">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b70d-172">Select **Save**.</span></span>

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="2b70d-173">建立沒有新功能的 Office 365 郵件加密的郵件流程規則</span><span class="sxs-lookup"><span data-stu-id="2b70d-173">Create mail flow rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="2b70d-174">如果您尚未將組織移至新的 OME 功能，請使用這些工作來定義郵件流程規則，以加密組織的郵件。</span><span class="sxs-lookup"><span data-stu-id="2b70d-174">If you haven't yet moved your organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization.</span></span> <span data-ttu-id="2b70d-175">Microsoft 建議您在組織合理的情況時，安排移至新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="2b70d-175">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="2b70d-176">如需相關指示，請參閱[設定以 Azure 資訊保護為基礎的新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-176">For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="2b70d-177">使用 EAC 來建立郵件流程規則，以加密不含新 OME 功能的電子郵件</span><span class="sxs-lookup"><span data-stu-id="2b70d-177">Use the EAC to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="2b70d-178">在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-178">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="2b70d-179">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="2b70d-179">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="2b70d-180">在 Microsoft 365 系統管理中心中，選擇 [系統**管理中心**] [ \> **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-180">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="2b70d-181">在 EAC 中，移至 [**郵件流程** \> **規則**]，然後選取 [**新增**新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-181">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="2b70d-182">如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-182">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="2b70d-183">在 [**名稱**] 中，輸入規則的名稱，例如 [加密 DrToniRamos@hotmail.com 的郵件]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-183">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="2b70d-184">在 [套用**此規則**] 選取條件時，必要時輸入值。</span><span class="sxs-lookup"><span data-stu-id="2b70d-184">In **Apply this rule if** select a condition, and enter a value if necessary.</span></span> <span data-ttu-id="2b70d-185">例如，若要加密要 DrToniRamos@hotmail.com 的郵件：</span><span class="sxs-lookup"><span data-stu-id="2b70d-185">For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="2b70d-186">在 [套用**此規則 if**] 中，選取**收件者為**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-186">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="2b70d-187">從連絡人清單中選取現有名稱，或在 [**檢查名稱**] 方塊中輸入新的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="2b70d-187">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="2b70d-188">若要選取現有名稱，請從清單中進行選取，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-188">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="2b70d-189">若要輸入新名稱，請在 [**檢查名稱**] 方塊中輸入電子郵件地址，然後選取 [**檢查名稱** \> **]**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-189">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="2b70d-190">若要新增更多條件，請選擇 [**更多選項**]，然後選取 [**新增條件**]，然後從清單中選取。</span><span class="sxs-lookup"><span data-stu-id="2b70d-190">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span>

   <span data-ttu-id="2b70d-191">例如，若要在組織外部的收件者之外套用規則，請選取 [**新增條件**]，然後選取收件者在組織外**外部/內部的收件**者 \> **Outside the organization** \> \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="2b70d-191">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="2b70d-192">若要在不使用新 OME 功能的情況下啟用加密，請在**執行下列**動作中，選取 **[修改郵件安全性**] 套用 \> **舊版的 OME**，然後選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-192">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>

  <span data-ttu-id="2b70d-193">如果您收到未啟用 IRM 授權的錯誤，則表示尚未為您的組織設定 OME。</span><span class="sxs-lookup"><span data-stu-id="2b70d-193">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet.</span></span> <span data-ttu-id="2b70d-194">如果您想要立即設定 OME，則必須將它設定為使用新的 OME 功能。</span><span class="sxs-lookup"><span data-stu-id="2b70d-194">If you'd like to set up OME now, you must set it up to use the new OME capabilities.</span></span> <span data-ttu-id="2b70d-195">如需詳細資訊，請參閱[在 Azure 資訊保護上建立新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-195">For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="2b70d-196">Microsoft 不再支援設定新的 OME 部署，沒有新功能。</span><span class="sxs-lookup"><span data-stu-id="2b70d-196">Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>

  <span data-ttu-id="2b70d-197">如果您想要指定另一個動作，您可以選擇 [**新增動作**]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-197">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="2b70d-198">使用 Exchange Online PowerShell 建立郵件流程規則，以加密不含新 OME 功能的電子郵件</span><span class="sxs-lookup"><span data-stu-id="2b70d-198">Use Exchange Online PowerShell to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="2b70d-199">連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2b70d-199">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="2b70d-200">如需詳細資訊，請參閱＜[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)＞。</span><span class="sxs-lookup"><span data-stu-id="2b70d-200">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="2b70d-201">使用**New-TransportRule** Cmdlet 來建立規則，並將_ApplyOME_參數設為 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="2b70d-201">Create a rule by using the **New-TransportRule** cmdlet and set the _ApplyOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="2b70d-202">本範例要求所有傳送至 DrToniRamos@hotmail.com 的電子郵件都必須加密。</span><span class="sxs-lookup"><span data-stu-id="2b70d-202">This example requires that all email messages sent to DrToniRamos@hotmail.com must be encrypted.</span></span>

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   > [!NOTE]
   > 
   > - <span data-ttu-id="2b70d-203">新規則的唯一名稱是「Dr Toni Ramos 的加密規則」。</span><span class="sxs-lookup"><span data-stu-id="2b70d-203">The unique name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>
   > 
   > - <span data-ttu-id="2b70d-204">_SentTo_參數會指定郵件收件者（透過名稱、電子郵件地址、辨識名稱等）。</span><span class="sxs-lookup"><span data-stu-id="2b70d-204">The _SentTo_ parameter specifies the message recipients (identified by name, email address, distinguished name, etc.).</span></span> <span data-ttu-id="2b70d-205">在此範例中，收件者會透過電子郵件地址 "DrToniRamos@hotmail.com" 加以識別。</span><span class="sxs-lookup"><span data-stu-id="2b70d-205">In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span>
   > 
   > - <span data-ttu-id="2b70d-206">_SentToScope_參數會指定郵件收件者的位置。</span><span class="sxs-lookup"><span data-stu-id="2b70d-206">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="2b70d-207">在此範例中，收件者的信箱是在 hotmail 中，而且不是組織的一部分，因此 `NotInOrganization` 會使用此值。</span><span class="sxs-lookup"><span data-stu-id="2b70d-207">In this example, the recipient's mailbox is in hotmail and is not part of the organization, so the value `NotInOrganization` is used.</span></span>
   
   <span data-ttu-id="2b70d-208">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-208">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule).</span></span>

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="2b70d-209">從加密的電子郵件回復中移除加密，但不含新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="2b70d-209">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="2b70d-210">當您的電子郵件使用者傳送加密郵件時，這些郵件的收件者便可使用加密的回復來回應。</span><span class="sxs-lookup"><span data-stu-id="2b70d-210">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies.</span></span> <span data-ttu-id="2b70d-211">您可以建立郵件流程規則，以自動移除回復的加密，使組織中的電子郵件使用者不必登入加密入口網站以進行查看。</span><span class="sxs-lookup"><span data-stu-id="2b70d-211">You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them.</span></span> <span data-ttu-id="2b70d-212">您可以使用 EAC 或 Windows PowerShell Cmdlet 來定義這些規則。</span><span class="sxs-lookup"><span data-stu-id="2b70d-212">You can use the EAC or Windows PowerShell cmdlets to define these rules.</span></span> <span data-ttu-id="2b70d-213">若尚未使用新的 OME 功能，您只能解密從組織內部傳送的郵件，或是對從組織內傳送的郵件回復的郵件進行解密。</span><span class="sxs-lookup"><span data-stu-id="2b70d-213">If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization.</span></span> <span data-ttu-id="2b70d-214">您無法解密來自組織外部的加密郵件。</span><span class="sxs-lookup"><span data-stu-id="2b70d-214">You cannot decrypt encrypted messages originating from outside of your organization.</span></span>

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="2b70d-215">使用 EAC 來建立刪除電子郵件回復加密的規則，而不使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="2b70d-215">Use the EAC to create a rule for removing encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="2b70d-216">在網頁瀏覽器中，使用已獲授與系統管理員許可權的公司或學校帳戶登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-216">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="2b70d-217">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="2b70d-217">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="2b70d-218">在 Microsoft 365 系統管理中心中，選擇 [系統**管理中心**] [ \> **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-218">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="2b70d-219">在 EAC 中，移至 [**郵件流程** \> **規則**]，然後選取 [**新增**新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-219">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="2b70d-220">如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-220">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="2b70d-221">在 [**名稱**] 中，輸入規則的名稱，例如 [移除來自傳入郵件的加密]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-221">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>

6. <span data-ttu-id="2b70d-222">在 [套用**此規則**] 中，選取應該從郵件中移除加密的情況，例如**收件者位於** \> **組織內**。</span><span class="sxs-lookup"><span data-stu-id="2b70d-222">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>

7. <span data-ttu-id="2b70d-223">在**執行下列**動作中，選取 **[修改郵件安全性** \> **移除舊版 OME**]。</span><span class="sxs-lookup"><span data-stu-id="2b70d-223">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>

8. <span data-ttu-id="2b70d-224">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b70d-224">Select **Save**.</span></span>

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="2b70d-225">使用 Exchange Online PowerShell 建立規則，以從加密的電子郵件回復中移除加密，但不使用新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="2b70d-225">Use Exchange Online PowerShell to create a rule to remove encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="2b70d-226">連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2b70d-226">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="2b70d-227">如需詳細資訊，請參閱＜[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)＞。</span><span class="sxs-lookup"><span data-stu-id="2b70d-227">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="2b70d-228">使用**New-TransportRule** Cmdlet 來建立規則，並將_RemoveOME_參數設為 `$true` 。</span><span class="sxs-lookup"><span data-stu-id="2b70d-228">Create a rule by using the **New-TransportRule** cmdlet and set the _RemoveOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="2b70d-229">此範例會移除傳送給組織中收件者的所有郵件的加密。</span><span class="sxs-lookup"><span data-stu-id="2b70d-229">This example removes the encryption from all mail sent to recipients in the organization.</span></span>

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   > [!NOTE]
   > 
   > - <span data-ttu-id="2b70d-230">新規則的唯一名稱是「移除來自傳入郵件的加密」。</span><span class="sxs-lookup"><span data-stu-id="2b70d-230">The unique name of the new rule is "Remove encryption from incoming mail".</span></span>
   > 
   > - <span data-ttu-id="2b70d-231">_SentToScope_參數會指定郵件收件者的位置。</span><span class="sxs-lookup"><span data-stu-id="2b70d-231">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="2b70d-232">在此範例中， `InOrganization` 會使用 value 值，表示：</span><span class="sxs-lookup"><span data-stu-id="2b70d-232">In this example, the value `InOrganization` value is used, which indicates:</span></span>
   > 
   >   - <span data-ttu-id="2b70d-233">收件者是組織中的信箱、郵件使用者、群組或擁有郵件功能的公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="2b70d-233">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization.</span></span>
   > 
   >     <span data-ttu-id="2b70d-234">或</span><span class="sxs-lookup"><span data-stu-id="2b70d-234">or</span></span>
   > 
   >   - <span data-ttu-id="2b70d-235">收件者的電子郵件地址位於已設定為授權網域或組織內部轉送網域的公認網域中，_且_透過已驗證的連線來傳送或接收郵件。</span><span class="sxs-lookup"><span data-stu-id="2b70d-235">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain in your organization, _and_ the message was sent or received over an authenticated connection.</span></span>

<span data-ttu-id="2b70d-236">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule)。</span><span class="sxs-lookup"><span data-stu-id="2b70d-236">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2b70d-237">相關主題</span><span class="sxs-lookup"><span data-stu-id="2b70d-237">Related Topics</span></span>

[<span data-ttu-id="2b70d-238">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="2b70d-238">Encryption in Office 365</span></span>](encryption.md)

[<span data-ttu-id="2b70d-239">設定全新的 Office 365 郵件加密功能</span><span class="sxs-lookup"><span data-stu-id="2b70d-239">Set up new Office 365 Message Encryption capabilities</span></span>](set-up-new-message-encryption-capabilities.md)

[<span data-ttu-id="2b70d-240">將商標新增至加密郵件</span><span class="sxs-lookup"><span data-stu-id="2b70d-240">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)

[<span data-ttu-id="2b70d-241">Exchange Online 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="2b70d-241">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[<span data-ttu-id="2b70d-242">Exchange Online Protection 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="2b70d-242">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
