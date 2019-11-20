---
title: 定義郵件流規則以加密 Office 365 中的電子郵件
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
description: 系統管理員可以了解如何建立郵件流程規則 （傳輸規則） 來加密及解密使用 Office 365 郵件加密的郵件。
ms.openlocfilehash: 54fc53d1e39208f42348b6def4afadf71092ff11
ms.sourcegitcommit: b535fe233234fd25146cfe15478e20d954f71e03
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2019
ms.locfileid: "38748551"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a><span data-ttu-id="b6137-103">定義郵件流規則以加密 Office 365 中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="b6137-103">Define mail flow rules to encrypt email messages in Office 365</span></span>

<span data-ttu-id="b6137-104">身為 Office 365 全域管理員，您可以建立郵件流程規則 （也稱為傳輸規則） 來協助保護您傳送和接收的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="b6137-104">As an Office 365 global administrator, you can create mail flow rules (also known as transport rules) to help protect email messages you send and receive.</span></span> <span data-ttu-id="b6137-105">您可以設定規則以加密所有外寄的電子郵件，並移除加密，從加密的郵件來自組織內部或從組織傳送加密郵件的回覆。</span><span class="sxs-lookup"><span data-stu-id="b6137-105">You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> <span data-ttu-id="b6137-106">若要建立這些規則，您可以使用 Exchange 系統管理中心 (EAC) 或 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b6137-106">You can use the Exchange admin center (EAC) or Exchange Online PowerShell to create these rules.</span></span> <span data-ttu-id="b6137-107">除了整體加密的郵件，您也可以選擇啟用或停用使用者的個別郵件加密選項。</span><span class="sxs-lookup"><span data-stu-id="b6137-107">In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end-users.</span></span>

<span data-ttu-id="b6137-108">您無法在組織外加密來自寄件者的內送的郵件。</span><span class="sxs-lookup"><span data-stu-id="b6137-108">You can't encrypt inbound mail from senders outside of your organization.</span></span>

<span data-ttu-id="b6137-109">如果您最近移轉從 AD RMS Azure 資訊保護，您需要檢閱現有的郵件流程規則，以確保它們繼續在新環境中運作。</span><span class="sxs-lookup"><span data-stu-id="b6137-109">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment.</span></span> <span data-ttu-id="b6137-110">此外，如果您想要利用新的 Office 365 郵件加密 (OME) 功能給您透過 Azure 資訊保護，您必須更新您現有的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="b6137-110">Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules.</span></span> <span data-ttu-id="b6137-111">否則，您的使用者將會繼續收到加密的郵件，而不是新的、 無縫 OME 經驗會使用先前的 HTML 附件格式。</span><span class="sxs-lookup"><span data-stu-id="b6137-111">Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience.</span></span> <span data-ttu-id="b6137-112">如果您尚未設定 OME 尚未，請參閱[設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)的資訊。</span><span class="sxs-lookup"><span data-stu-id="b6137-112">If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md) for information.</span></span>

<span data-ttu-id="b6137-113">元件構成郵件流程規則及郵件流程規則的工作的方式的相關資訊，請參閱[Exchange Online 中的郵件流程規則 （傳輸規則）](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="b6137-113">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span> <span data-ttu-id="b6137-114">如需有關使用 Azure 資訊保護郵件流程規則的運作方式的詳細資訊，請參閱[Azure 資訊保護標籤設定 Exchange Online 的郵件流程規則](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。</span><span class="sxs-lookup"><span data-stu-id="b6137-114">For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6137-115">混合式 Exchange 環境中，內部部署使用者可以傳送電子郵件會路由傳送到 Exchange Online 時，才使用 OME 加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="b6137-115">For hybrid Exchange environments, on-premises users can send encrypted mail using OME only if email is routed through Exchange Online.</span></span> <span data-ttu-id="b6137-116">若要設定 OME 混合式 Exchange 環境中，您需要[設定混合式使用混合組態精靈](https://docs.microsoft.com/Exchange/exchange-hybrid)的第一個，然後[將郵件設定為從您的電子郵件伺服器到 Office 365 的流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="b6137-116">To configure OME in a hybrid Exchange environment, you need to first [configure hybrid using the Hybrid Configuration wizard](https://docs.microsoft.com/Exchange/exchange-hybrid) and then [configure mail to flow from your email server to Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).</span></span> <span data-ttu-id="b6137-117">一次您已設定郵件來經過 Office 365，則您也可以使用這份指導的 OME 設定郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="b6137-117">Once you've configured mail to flow through Office 365, then you can configure mail flow rules for OME by using this guidance.</span></span>

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="b6137-118">建立郵件流程規則來加密與新的 OME 功能的電子郵件</span><span class="sxs-lookup"><span data-stu-id="b6137-118">Create mail flow rules to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="b6137-119">您可以定義郵件流程規則的觸發郵件加密與新的 OME 功能使用 EAC。</span><span class="sxs-lookup"><span data-stu-id="b6137-119">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="b6137-120">使用 EAC 來建立加密與新的 OME 功能的電子郵件訊息的規則</span><span class="sxs-lookup"><span data-stu-id="b6137-120">Use the EAC to create a rule for encrypting email messages with the new OME capabilities</span></span>

1. <span data-ttu-id="b6137-121">在網頁瀏覽器中使用已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="b6137-121">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="b6137-122">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="b6137-122">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="b6137-123">在 Microsoft 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="b6137-123">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="b6137-124">在 EAC 中，移至 [**郵件流程** \> **規則**，然後選擇 [**新增** ![[新增] 圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="b6137-124">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="b6137-125">如需使用 EAC 的詳細資訊，請參閱[Exchange 系統管理中心在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="b6137-125">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="b6137-126">在 [**名稱**] 中，輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="b6137-126">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="b6137-127">在 [**套用此規則情況**選擇一個條件，並輸入值，如果需要的話。</span><span class="sxs-lookup"><span data-stu-id="b6137-127">In **Apply this rule if** select a condition, and enter a value if necessary.</span></span> <span data-ttu-id="b6137-128">例如，若要加密郵件移至 [DrToniRamos@hotmail.com:</span><span class="sxs-lookup"><span data-stu-id="b6137-128">For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="b6137-129">在 [**套用此規則情況**，請選取 [**收件者**。</span><span class="sxs-lookup"><span data-stu-id="b6137-129">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="b6137-130">從連絡人清單中選取現有名稱，或在 [**檢查名稱**] 方塊中輸入新的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b6137-130">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="b6137-131">若要選取現有名稱，從清單中選取它，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="b6137-131">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="b6137-132">若要輸入新名稱，在 [**檢查名稱**] 方塊中輸入的電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b6137-132">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="b6137-133">若要新增更多條件，請選擇 [**更多選項]** 然後選擇 [**新增條件**，並從清單中選取。</span><span class="sxs-lookup"><span data-stu-id="b6137-133">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span>

   <span data-ttu-id="b6137-134">例如，只有當收件者是在組織外，請套用規則，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外部的** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b6137-134">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="b6137-135">若要啟用加密使用全新的 OME 功能，從**執行下列動作**，選取 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。</span><span class="sxs-lookup"><span data-stu-id="b6137-135">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="b6137-136">從清單中選取的 RMS 範本，選擇 [**儲存**]，然後選擇 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="b6137-136">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
  <span data-ttu-id="b6137-137">範本的清單包含所有的預設範本及 Office 365 所使用的選項，以及您已建立的任何自訂範本。</span><span class="sxs-lookup"><span data-stu-id="b6137-137">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="b6137-138">如果清單是空的請確定您已設定 Office 365 郵件加密與新功能[設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。</span><span class="sxs-lookup"><span data-stu-id="b6137-138">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="b6137-139">如需預設範本的資訊，請參閱[設定與管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="b6137-139">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="b6137-140">[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="b6137-140">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="b6137-141">[**僅限加密**] 選項的相關資訊，請參閱[僅加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="b6137-141">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

  <span data-ttu-id="b6137-142">如果您想要指定另一個動作，您可以選擇**新增巨集指令**。</span><span class="sxs-lookup"><span data-stu-id="b6137-142">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a><span data-ttu-id="b6137-143">使用 EAC 來更新現有郵件流程規則，以使用全新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="b6137-143">Use the EAC to update an existing mail flow rule to use the new OME capabilities</span></span>

1. <span data-ttu-id="b6137-144">在網頁瀏覽器中使用已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="b6137-144">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="b6137-145">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="b6137-145">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="b6137-146">在 Microsoft 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="b6137-146">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="b6137-147">在 EAC 中，移至 [郵件流程]\*\*\*\* \> [規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b6137-147">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

5. <span data-ttu-id="b6137-148">在 [郵件流程規則] 清單中選取您想要修改以使用全新的 OME 功能]，然後選擇 [**編輯**的規則![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="b6137-148">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

6. <span data-ttu-id="b6137-149">若要啟用加密使用全新的 OME 功能，從**執行下列動作**，選擇 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。</span><span class="sxs-lookup"><span data-stu-id="b6137-149">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="b6137-150">從清單中選取的 RMS 範本，選擇 [**儲存]** ，然後選擇 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="b6137-150">Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>

   <span data-ttu-id="b6137-151">範本的清單包含所有的預設範本及 Office 365 所使用的選項，以及您已建立的任何自訂範本。</span><span class="sxs-lookup"><span data-stu-id="b6137-151">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="b6137-152">如果清單是空的請確定您已設定 Office 365 郵件加密與新功能如所述[設定頂端的 Azure 資訊保護為基礎的新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="b6137-152">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="b6137-153">如需預設範本的資訊，請參閱[設定與管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="b6137-153">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="b6137-154">[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="b6137-154">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="b6137-155">[**僅限加密**] 選項的相關資訊，請參閱[僅加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="b6137-155">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="b6137-156">如果您想要指定另一個動作，您可以選擇**新增巨集指令**。</span><span class="sxs-lookup"><span data-stu-id="b6137-156">You can choose **add action** if you want to specify another action.</span></span>

7. <span data-ttu-id="b6137-157">從**執行下列動作**] 清單中，移除任何已指派給**修改郵件安全性**的動作\>**套用 OME 的舊版本**。</span><span class="sxs-lookup"><span data-stu-id="b6137-157">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>

8. <span data-ttu-id="b6137-158">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b6137-158">Choose **Save**.</span></span>

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="b6137-159">建立郵件流程規則的 Office 365 郵件加密沒有的新功能</span><span class="sxs-lookup"><span data-stu-id="b6137-159">Create mail flow rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="b6137-160">如果您還尚未移您的 Office 365 組織至全新的 OME 功能，可用於這些工作定義郵件流規則以加密您組織的郵件。</span><span class="sxs-lookup"><span data-stu-id="b6137-160">If you haven't yet moved your Office 365 organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization.</span></span> <span data-ttu-id="b6137-161">Microsoft 建議您先將移至全新的 OME 功能，只要是合理的貴組織的計劃。</span><span class="sxs-lookup"><span data-stu-id="b6137-161">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="b6137-162">如需相關指示，請參閱[設定以 Azure 資訊保護基礎所建置的全新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="b6137-162">For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="b6137-163">使用 EAC 來建立郵件流程規則來加密電子郵件，而不需要全新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="b6137-163">Use the EAC to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="b6137-164">在網頁瀏覽器中使用已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="b6137-164">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="b6137-165">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="b6137-165">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="b6137-166">在 Microsoft 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="b6137-166">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="b6137-167">在 EAC 中，移至 [**郵件流程** \> **規則**，然後選擇 [**新增** ![[新增] 圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="b6137-167">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="b6137-168">如需使用 EAC 的詳細資訊，請參閱[Exchange 系統管理中心在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="b6137-168">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="b6137-169">在 [**名稱**] 中，輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="b6137-169">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="b6137-170">在 [**套用此規則情況**選擇一個條件，並輸入值，如果需要的話。</span><span class="sxs-lookup"><span data-stu-id="b6137-170">In **Apply this rule if** select a condition, and enter a value if necessary.</span></span> <span data-ttu-id="b6137-171">例如，若要加密郵件移至 [DrToniRamos@hotmail.com:</span><span class="sxs-lookup"><span data-stu-id="b6137-171">For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="b6137-172">在 [**套用此規則情況**，請選取 [**收件者**。</span><span class="sxs-lookup"><span data-stu-id="b6137-172">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="b6137-173">從連絡人清單中選取現有名稱，或在 [**檢查名稱**] 方塊中輸入新的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="b6137-173">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="b6137-174">若要選取現有名稱，從清單中選取它，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="b6137-174">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="b6137-175">若要輸入新名稱，在 [**檢查名稱**] 方塊中輸入的電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b6137-175">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="b6137-176">若要新增更多條件，選擇 [**更多選項]** 然後選取 [**新增條件，** 並從清單中選取。</span><span class="sxs-lookup"><span data-stu-id="b6137-176">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span>

   <span data-ttu-id="b6137-177">例如，只有當收件者是在組織外，請套用規則，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外部的** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b6137-177">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="b6137-178">若要啟用加密，而不使用全新的 OME 功能中**執行下列動作**,，請選取 [**修改郵件安全性** \> **套用 OME 舊版**]，然後選擇 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="b6137-178">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>

  <span data-ttu-id="b6137-179">如果您收到未啟用 IRM 授權，則您尚未為您的組織尚未設定 OME 的錯誤。</span><span class="sxs-lookup"><span data-stu-id="b6137-179">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet.</span></span> <span data-ttu-id="b6137-180">如果您想要立即設定 OME，您必須使用全新的 OME 功能將其設定。</span><span class="sxs-lookup"><span data-stu-id="b6137-180">If you'd like to set up OME now, you must set it up to use the new OME capabilities.</span></span> <span data-ttu-id="b6137-181">如需資訊，請參閱[設定以 Azure 資訊保護基礎所建置的全新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="b6137-181">For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="b6137-182">Microsoft 不再支援的 OME 沒有的新功能的新部署的設定。</span><span class="sxs-lookup"><span data-stu-id="b6137-182">Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>

  <span data-ttu-id="b6137-183">如果您想要指定另一個動作，您可以選擇**新增巨集指令**。</span><span class="sxs-lookup"><span data-stu-id="b6137-183">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="b6137-184">使用 Exchange Online PowerShell 來建立郵件流程規則來加密電子郵件，而不需要全新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="b6137-184">Use Exchange Online PowerShell to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="b6137-185">連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b6137-185">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="b6137-186">如需詳細資訊，請參閱＜[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)＞。</span><span class="sxs-lookup"><span data-stu-id="b6137-186">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b6137-187">使用**New-transportrule**指令程式建立規則，並將_ApplyOME_參數設定為`$true`。</span><span class="sxs-lookup"><span data-stu-id="b6137-187">Create a rule by using the **New-TransportRule** cmdlet and set the _ApplyOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="b6137-188">這個範例需要所有傳送到 DrToniRamos@hotmail.com 的電子郵件訊息必須經過加密。</span><span class="sxs-lookup"><span data-stu-id="b6137-188">This example requires that all email messages sent to DrToniRamos@hotmail.com must be encrypted.</span></span>

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   <span data-ttu-id="b6137-189">**附註**：</span><span class="sxs-lookup"><span data-stu-id="b6137-189">**Notes**:</span></span>

   - <span data-ttu-id="b6137-190">新規則的唯一名稱是 「 Dr Toni Ramos 加密規則 」。</span><span class="sxs-lookup"><span data-stu-id="b6137-190">The unique name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>

   - <span data-ttu-id="b6137-191">_SentTo_參數會指定 （由名稱、 電子郵件地址、 辨別的名稱等識別）。 郵件收件者。</span><span class="sxs-lookup"><span data-stu-id="b6137-191">The _SentTo_ parameter specifies the message recipients (identified by name, email address, distinguished name, etc.).</span></span> <span data-ttu-id="b6137-192">在這個範例中，收件者的電子郵件地址 」 DrToniRamos@hotmail.com 」 會識別。</span><span class="sxs-lookup"><span data-stu-id="b6137-192">In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span>

   - <span data-ttu-id="b6137-193">_SentToScope_參數會指定郵件的收件者的位置。</span><span class="sxs-lookup"><span data-stu-id="b6137-193">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="b6137-194">在這個範例中，收件者的信箱位於 hotmail 和不屬於 Office 365 組織，因此值`NotInOrganization`使用。</span><span class="sxs-lookup"><span data-stu-id="b6137-194">In this example, the recipient's mailbox is in hotmail and is not part of the Office 365 organization, so the value `NotInOrganization` is used.</span></span>

   <span data-ttu-id="b6137-195">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)。</span><span class="sxs-lookup"><span data-stu-id="b6137-195">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="b6137-196">移除但全新的 OME 功能未加密的電子郵件回覆的加密</span><span class="sxs-lookup"><span data-stu-id="b6137-196">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="b6137-197">當您的電子郵件使用者傳送加密的郵件時，這些郵件的收件者可以回覆與加密回覆。</span><span class="sxs-lookup"><span data-stu-id="b6137-197">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies.</span></span> <span data-ttu-id="b6137-198">您可以建立郵件流程規則來自動移除加密回覆讓組織中的電子郵件使用者不必登入加密入口網站來檢視它們。</span><span class="sxs-lookup"><span data-stu-id="b6137-198">You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them.</span></span> <span data-ttu-id="b6137-199">您可以使用 EAC 或 Windows PowerShell cmdlet 來定義這些規則。</span><span class="sxs-lookup"><span data-stu-id="b6137-199">You can use the EAC or Windows PowerShell cmdlets to define these rules.</span></span> <span data-ttu-id="b6137-200">如果您不尚未使用全新的 OME 功能，您可以只解密郵件的 [寄件者在您的組織或回覆郵件從組織內傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="b6137-200">If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization.</span></span> <span data-ttu-id="b6137-201">您無法解密加密來自組織外的郵件。</span><span class="sxs-lookup"><span data-stu-id="b6137-201">You cannot decrypt encrypted messages originating from outside of your organization.</span></span>

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="b6137-202">使用 EAC 來建立移除全新的 OME 功能不加密的電子郵件回覆中加密的規則</span><span class="sxs-lookup"><span data-stu-id="b6137-202">Use the EAC to create a rule for removing encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="b6137-203">在網頁瀏覽器中使用已授與系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="b6137-203">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="b6137-204">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="b6137-204">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="b6137-205">在 Microsoft 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="b6137-205">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="b6137-206">在 EAC 中，移至 [**郵件流程** \> **規則**，然後選擇 [**新增** ![[新增] 圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="b6137-206">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="b6137-207">如需使用 EAC 的詳細資訊，請參閱[Exchange 系統管理中心在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="b6137-207">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="b6137-208">在 [**名稱**] 中，輸入規則名稱，例如 Remove encryption，從內送郵件。</span><span class="sxs-lookup"><span data-stu-id="b6137-208">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>

6. <span data-ttu-id="b6137-209">在**套用此規則，如果**選取 [從郵件，例如**收件者位於**應該移除加密的條件\>**組織內**。</span><span class="sxs-lookup"><span data-stu-id="b6137-209">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>

7. <span data-ttu-id="b6137-210">在 [**執行下列動作**，選取 [**修改郵件安全性** \> **OME 的先前版本中移除**。</span><span class="sxs-lookup"><span data-stu-id="b6137-210">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>

8. <span data-ttu-id="b6137-211">選取 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b6137-211">Select **Save**.</span></span>

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="b6137-212">使用 Exchange Online PowerShell 來建立規則，以移除全新的 OME 功能不加密的電子郵件回覆的加密</span><span class="sxs-lookup"><span data-stu-id="b6137-212">Use Exchange Online PowerShell to create a rule to remove encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="b6137-213">連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b6137-213">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="b6137-214">如需詳細資訊，請參閱＜[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)＞。</span><span class="sxs-lookup"><span data-stu-id="b6137-214">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b6137-215">使用**New-transportrule**指令程式建立規則，並將_RemoveOME_參數設定為`$true`。</span><span class="sxs-lookup"><span data-stu-id="b6137-215">Create a rule by using the **New-TransportRule** cmdlet and set the _RemoveOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="b6137-216">此範例會移除所有傳送到 Office 365 組織中收件者的郵件中的加密。</span><span class="sxs-lookup"><span data-stu-id="b6137-216">This example removes the encryption from all mail sent to recipients in the Office 365 organization.</span></span>

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   <span data-ttu-id="b6137-217">**附註**：</span><span class="sxs-lookup"><span data-stu-id="b6137-217">**Notes**:</span></span>

   - <span data-ttu-id="b6137-218">新規則的唯一名稱是 「 Remove encryption from incoming mail 」。</span><span class="sxs-lookup"><span data-stu-id="b6137-218">The unique name of the new rule is "Remove encryption from incoming mail".</span></span>

   - <span data-ttu-id="b6137-219">_SentToScope_參數會指定郵件的收件者的位置。</span><span class="sxs-lookup"><span data-stu-id="b6137-219">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="b6137-220">在這個範例中，此值`InOrganization`值用來表示：</span><span class="sxs-lookup"><span data-stu-id="b6137-220">In this example, the value `InOrganization` value is used, which indicates:</span></span>

     - <span data-ttu-id="b6137-221">收件者是信箱、 郵件使用者、 群組或組織中的擁有郵件功能公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="b6137-221">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization.</span></span>

       <span data-ttu-id="b6137-222">或</span><span class="sxs-lookup"><span data-stu-id="b6137-222">or</span></span>

     - <span data-ttu-id="b6137-223">收件者的電子郵件地址位於公認的網域已設定為授權網域] 或 [內部轉送網域中您的組織，_並_將郵件已傳送或接收透過未驗證連線。</span><span class="sxs-lookup"><span data-stu-id="b6137-223">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain in your organization, _and_ the message was sent or received over an authenticated connection.</span></span>

<span data-ttu-id="b6137-224">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)。</span><span class="sxs-lookup"><span data-stu-id="b6137-224">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b6137-225">相關主題</span><span class="sxs-lookup"><span data-stu-id="b6137-225">Related Topics</span></span>

[<span data-ttu-id="b6137-226">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="b6137-226">Encryption in Office 365</span></span>](encryption.md)

[<span data-ttu-id="b6137-227">設定全新的 Office 365 郵件加密功能</span><span class="sxs-lookup"><span data-stu-id="b6137-227">Set up new Office 365 Message Encryption capabilities</span></span>](set-up-new-message-encryption-capabilities.md)

[<span data-ttu-id="b6137-228">將商標新增至加密郵件</span><span class="sxs-lookup"><span data-stu-id="b6137-228">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)

[<span data-ttu-id="b6137-229">Exchange Online 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="b6137-229">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[<span data-ttu-id="b6137-230">Exchange Online Protection 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="b6137-230">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
