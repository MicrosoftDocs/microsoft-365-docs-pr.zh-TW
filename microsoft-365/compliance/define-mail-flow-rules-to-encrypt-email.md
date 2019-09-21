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
ms.openlocfilehash: 75b8e3c977a2708eb1edb8e2b94f555aa54045ca
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37076369"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a><span data-ttu-id="3778e-103">定義郵件流規則以加密 Office 365 中的電子郵件</span><span class="sxs-lookup"><span data-stu-id="3778e-103">Define mail flow rules to encrypt email messages in Office 365</span></span>

<span data-ttu-id="3778e-104">身為 Office 365 全域管理員，您可以建立郵件流程規則 （也稱為傳輸規則） 來協助保護您傳送和接收的電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="3778e-104">As an Office 365 global administrator, you can create mail flow rules (also known as transport rules) to help protect email messages you send and receive.</span></span> <span data-ttu-id="3778e-105">您可以設定規則以加密所有外寄的電子郵件，並移除加密，從加密的郵件來自組織內部或從組織傳送加密郵件的回覆。</span><span class="sxs-lookup"><span data-stu-id="3778e-105">You can set up rules to encrypt any outgoing email messages and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> <span data-ttu-id="3778e-106">若要建立這些規則，您可以使用 Exchange 系統管理中心 (EAC) 或 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3778e-106">You can use the Exchange admin center (EAC) or Exchange Online PowerShell to create these rules.</span></span> <span data-ttu-id="3778e-107">除了整體加密的郵件，您也可以選擇啟用或停用使用者的個別郵件加密選項。</span><span class="sxs-lookup"><span data-stu-id="3778e-107">In addition to overall encryption rules, you can also choose to enable or disable individual message encryption options for end-users.</span></span>

||
|:-----|
|<span data-ttu-id="3778e-108">本文屬於較大的一連串的 Office 365 郵件加密的相關文章。</span><span class="sxs-lookup"><span data-stu-id="3778e-108">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="3778e-109">本文適用於系統管理員和 ITPros。</span><span class="sxs-lookup"><span data-stu-id="3778e-109">This article is intended for administrators and ITPros.</span></span> <span data-ttu-id="3778e-110">如果您只是正在尋找的資訊傳送或接收的加密的訊息，請參閱在[Office 365 郵件加密 (OME)](ome.md)中的文章的清單，並找出最適合您需求的文章。</span><span class="sxs-lookup"><span data-stu-id="3778e-110">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

<span data-ttu-id="3778e-111">如果您最近移轉從 AD RMS Azure 資訊保護，您需要檢閱現有的郵件流程規則，以確保它們繼續在新環境中運作。</span><span class="sxs-lookup"><span data-stu-id="3778e-111">If you recently migrated from AD RMS to Azure Information Protection, you'll need to review your existing mail flow rules to ensure that they continue to work in your new environment.</span></span> <span data-ttu-id="3778e-112">此外，如果您想要利用新的 Office 365 郵件加密 (OME) 功能給您透過 Azure 資訊保護，您必須更新您現有的郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="3778e-112">Additionally, if you want to take advantage of the new Office 365 Message Encryption (OME) capabilities available to you through Azure Information Protection, you need to update your existing mail flow rules.</span></span> <span data-ttu-id="3778e-113">否則，您的使用者將會繼續收到加密的郵件，而不是新的、 無縫 OME 經驗會使用先前的 HTML 附件格式。</span><span class="sxs-lookup"><span data-stu-id="3778e-113">Otherwise, your users will continue to receive encrypted mail that uses the previous HTML attachment format instead of the new, seamless OME experience.</span></span> <span data-ttu-id="3778e-114">如果您尚未設定 OME 尚未，請參閱[設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)的資訊。</span><span class="sxs-lookup"><span data-stu-id="3778e-114">If you haven't set up OME yet, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md) for information.</span></span>

<span data-ttu-id="3778e-115">元件構成郵件流程規則及郵件流程規則的工作的方式的相關資訊，請參閱[Exchange Online 中的郵件流程規則 （傳輸規則）](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。</span><span class="sxs-lookup"><span data-stu-id="3778e-115">For information about the components that make up mail flow rules and how mail flow rules work, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span> <span data-ttu-id="3778e-116">如需有關使用 Azure 資訊保護郵件流程規則的運作方式的詳細資訊，請參閱[Azure 資訊保護標籤設定 Exchange Online 的郵件流程規則](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。</span><span class="sxs-lookup"><span data-stu-id="3778e-116">For additional information about how mail flow rules work with Azure Information Protection, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3778e-117">混合式 Exchange 環境中，內部部署使用者可以傳送電子郵件會路由傳送到 Exchange Online 時，才使用 OME 加密的郵件。</span><span class="sxs-lookup"><span data-stu-id="3778e-117">For hybrid Exchange environments, on-premises users can send encrypted mail using OME only if email is routed through Exchange Online.</span></span> <span data-ttu-id="3778e-118">若要設定 OME 混合式 Exchange 環境中，您需要[設定混合式使用混合組態精靈](https://docs.microsoft.com/Exchange/exchange-hybrid)的第一個，然後[將郵件設定為從您的電子郵件伺服器到 Office 365 的流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。</span><span class="sxs-lookup"><span data-stu-id="3778e-118">To configure OME in a hybrid Exchange environment, you need to first [configure hybrid using the Hybrid Configuration wizard](https://docs.microsoft.com/Exchange/exchange-hybrid) and then [configure mail to flow from your email server to Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).</span></span> <span data-ttu-id="3778e-119">一次您已設定郵件來經過 Office 365，則您也可以使用這份指導的 OME 設定郵件流程規則。</span><span class="sxs-lookup"><span data-stu-id="3778e-119">Once you've configured mail to flow through Office 365, then you can configure mail flow rules for OME by using this guidance.</span></span>

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="3778e-120">建立郵件流程規則來加密與新的 OME 功能的電子郵件</span><span class="sxs-lookup"><span data-stu-id="3778e-120">Create mail flow rules to encrypt email messages with the new OME capabilities</span></span>

<span data-ttu-id="3778e-121">您可以定義郵件流程規則的觸發郵件加密與新的 OME 功能使用 EAC。</span><span class="sxs-lookup"><span data-stu-id="3778e-121">You can define mail flow rules for triggering message encryption with the new OME capabilities by using the EAC.</span></span>

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a><span data-ttu-id="3778e-122">使用 EAC 來建立加密與新的 OME 功能的電子郵件訊息的規則</span><span class="sxs-lookup"><span data-stu-id="3778e-122">Use the EAC to create a rule for encrypting email messages with the new OME capabilities</span></span>

1. <span data-ttu-id="3778e-123">在網頁瀏覽器中使用已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="3778e-123">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="3778e-124">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="3778e-124">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="3778e-125">在 Microsoft 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="3778e-125">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="3778e-126">在 EAC 中，移至 [**郵件流程** \> **規則**，然後選擇 [**新增** ![[新增] 圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="3778e-126">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="3778e-127">如需使用 EAC 的詳細資訊，請參閱[Exchange 系統管理中心在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="3778e-127">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="3778e-128">在 [**名稱**] 中，輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="3778e-128">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="3778e-129">在 [**套用此規則情況**選擇一個條件，並輸入值，如果需要的話。</span><span class="sxs-lookup"><span data-stu-id="3778e-129">In **Apply this rule if** select a condition, and enter a value if necessary.</span></span> <span data-ttu-id="3778e-130">例如，若要加密郵件移至 [DrToniRamos@hotmail.com:</span><span class="sxs-lookup"><span data-stu-id="3778e-130">For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="3778e-131">在 [**套用此規則情況**，請選取 [**收件者**。</span><span class="sxs-lookup"><span data-stu-id="3778e-131">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="3778e-132">從連絡人清單中選取現有名稱，或在 [**檢查名稱**] 方塊中輸入新的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3778e-132">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="3778e-133">若要選取現有名稱，從清單中選取它，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="3778e-133">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="3778e-134">若要輸入新名稱，在 [**檢查名稱**] 方塊中輸入的電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3778e-134">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="3778e-135">若要新增更多條件，請選擇 [**更多選項]** 然後選擇 [**新增條件**，並從清單中選取。</span><span class="sxs-lookup"><span data-stu-id="3778e-135">To add more conditions, choose **More options** and then choose **add condition** and select from the list.</span></span>

   <span data-ttu-id="3778e-136">例如，只有當收件者是在組織外，請套用規則，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外部的** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3778e-136">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="3778e-137">若要啟用加密使用全新的 OME 功能，從**執行下列動作**，選取 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。</span><span class="sxs-lookup"><span data-stu-id="3778e-137">To enable encryption using the new OME capabilities, from **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="3778e-138">從清單中選取的 RMS 範本，選擇 [**儲存**]，然後選擇 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="3778e-138">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
  <span data-ttu-id="3778e-139">範本的清單包含所有的預設範本及 Office 365 所使用的選項，以及您已建立的任何自訂範本。</span><span class="sxs-lookup"><span data-stu-id="3778e-139">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="3778e-140">如果清單是空的請確定您已設定 Office 365 郵件加密與新功能[設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。</span><span class="sxs-lookup"><span data-stu-id="3778e-140">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="3778e-141">如需預設範本的資訊，請參閱[設定與管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="3778e-141">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="3778e-142">[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="3778e-142">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="3778e-143">[**僅限加密**] 選項的相關資訊，請參閱[僅加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="3778e-143">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

  <span data-ttu-id="3778e-144">如果您想要指定另一個動作，您可以選擇**新增巨集指令**。</span><span class="sxs-lookup"><span data-stu-id="3778e-144">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a><span data-ttu-id="3778e-145">使用 EAC 來更新現有郵件流程規則，以使用全新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="3778e-145">Use the EAC to update an existing mail flow rule to use the new OME capabilities</span></span>

1. <span data-ttu-id="3778e-146">在網頁瀏覽器中使用已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="3778e-146">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="3778e-147">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="3778e-147">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="3778e-148">在 Microsoft 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="3778e-148">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="3778e-149">In the EAC, go to **Mail flow** \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="3778e-149">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

5. <span data-ttu-id="3778e-150">在 [郵件流程規則] 清單中選取您想要修改以使用全新的 OME 功能]，然後選擇 [**編輯**的規則![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。</span><span class="sxs-lookup"><span data-stu-id="3778e-150">In the list of mail flow rules, select the rule you want to modify to use the new OME capabilities and then choose **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>

6. <span data-ttu-id="3778e-151">若要啟用加密使用全新的 OME 功能，從**執行下列動作**，選擇 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。</span><span class="sxs-lookup"><span data-stu-id="3778e-151">To enable encryption using the new OME capabilities, from **Do the following**, choose **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="3778e-152">從清單中選取的 RMS 範本，選擇 [**儲存]** ，然後選擇 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="3778e-152">Select an RMS template from the list, choose **Save** and then choose **OK**.</span></span>

   <span data-ttu-id="3778e-153">範本的清單包含所有的預設範本及 Office 365 所使用的選項，以及您已建立的任何自訂範本。</span><span class="sxs-lookup"><span data-stu-id="3778e-153">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="3778e-154">如果清單是空的請確定您已設定 Office 365 郵件加密與新功能如所述[設定頂端的 Azure 資訊保護為基礎的新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="3778e-154">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="3778e-155">如需預設範本的資訊，請參閱[設定與管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="3778e-155">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="3778e-156">[**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="3778e-156">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="3778e-157">[**僅限加密**] 選項的相關資訊，請參閱[僅加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="3778e-157">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="3778e-158">如果您想要指定另一個動作，您可以選擇**新增巨集指令**。</span><span class="sxs-lookup"><span data-stu-id="3778e-158">You can choose **add action** if you want to specify another action.</span></span>

7. <span data-ttu-id="3778e-159">從**執行下列動作**] 清單中，移除任何已指派給**修改郵件安全性**的動作\>**套用 OME 的舊版本**。</span><span class="sxs-lookup"><span data-stu-id="3778e-159">From the **Do the following** list, remove any actions that are assigned to **Modify the message security** \> **Apply the previous version of OME**.</span></span>

8. <span data-ttu-id="3778e-160">選擇 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="3778e-160">Choose **Save**.</span></span>

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a><span data-ttu-id="3778e-161">建立郵件流程規則的 Office 365 郵件加密沒有的新功能</span><span class="sxs-lookup"><span data-stu-id="3778e-161">Create mail flow rules for Office 365 Message Encryption without the new capabilities</span></span>

<span data-ttu-id="3778e-162">如果您還尚未移您的 Office 365 組織至全新的 OME 功能，可用於這些工作定義郵件流規則以加密您組織的郵件。</span><span class="sxs-lookup"><span data-stu-id="3778e-162">If you haven't yet moved your Office 365 organization to the new OME capabilities, use these tasks to define mail flow rules to encrypt messages for your organization.</span></span> <span data-ttu-id="3778e-163">Microsoft 建議您先將移至全新的 OME 功能，只要是合理的貴組織的計劃。</span><span class="sxs-lookup"><span data-stu-id="3778e-163">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="3778e-164">如需相關指示，請參閱[設定以 Azure 資訊保護基礎所建置的全新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="3778e-164">For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span>

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="3778e-165">使用 EAC 來建立郵件流程規則來加密電子郵件，而不需要全新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="3778e-165">Use the EAC to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="3778e-166">在網頁瀏覽器中使用已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="3778e-166">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="3778e-167">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="3778e-167">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="3778e-168">在 Microsoft 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="3778e-168">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="3778e-169">在 EAC 中，移至 [**郵件流程** \> **規則**，然後選擇 [**新增** ![[新增] 圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="3778e-169">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="3778e-170">如需使用 EAC 的詳細資訊，請參閱[Exchange 系統管理中心在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="3778e-170">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="3778e-171">在 [**名稱**] 中，輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。</span><span class="sxs-lookup"><span data-stu-id="3778e-171">In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.</span></span>

6. <span data-ttu-id="3778e-172">在 [**套用此規則情況**選擇一個條件，並輸入值，如果需要的話。</span><span class="sxs-lookup"><span data-stu-id="3778e-172">In **Apply this rule if** select a condition, and enter a value if necessary.</span></span> <span data-ttu-id="3778e-173">例如，若要加密郵件移至 [DrToniRamos@hotmail.com:</span><span class="sxs-lookup"><span data-stu-id="3778e-173">For example, to encrypt messages going to DrToniRamos@hotmail.com:</span></span>

   1. <span data-ttu-id="3778e-174">在 [**套用此規則情況**，請選取 [**收件者**。</span><span class="sxs-lookup"><span data-stu-id="3778e-174">In **Apply this rule if**, select **the recipient is**.</span></span>

   2. <span data-ttu-id="3778e-175">從連絡人清單中選取現有名稱，或在 [**檢查名稱**] 方塊中輸入新的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="3778e-175">Select an existing name from the contact list or type a new email address in the **check names** box.</span></span>

      - <span data-ttu-id="3778e-176">若要選取現有名稱，從清單中選取它，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="3778e-176">To select an existing name, select it from the list and then click **OK**.</span></span>

      - <span data-ttu-id="3778e-177">若要輸入新名稱，在 [**檢查名稱**] 方塊中輸入的電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3778e-177">To enter a new name, type an email address in the **check names** box and then select **check names** \> **OK**.</span></span>

7. <span data-ttu-id="3778e-178">若要新增更多條件，選擇 [**更多選項]** 然後選取 [**新增條件，** 並從清單中選取。</span><span class="sxs-lookup"><span data-stu-id="3778e-178">To add more conditions, choose **More options** and then select **add condition** and select from the list.</span></span>

   <span data-ttu-id="3778e-179">例如，只有當收件者是在組織外，請套用規則，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外部的** \> **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3778e-179">For example, to apply the rule only if the recipient is outside your organization, select **add condition** and then select **The recipient is external/internal** \> **Outside the organization** \> **OK**.</span></span>

8. <span data-ttu-id="3778e-180">若要啟用加密，而不使用全新的 OME 功能中**執行下列動作**,，請選取 [**修改郵件安全性** \> **套用 OME 舊版**]，然後選擇 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="3778e-180">To enable encryption without using the new OME capabilities, in **Do the following**, select **Modify the message security** \> **Apply the previous version of OME**, and then choose **Save**.</span></span>

  <span data-ttu-id="3778e-181">如果您收到未啟用 IRM 授權，則您尚未為您的組織尚未設定 OME 的錯誤。</span><span class="sxs-lookup"><span data-stu-id="3778e-181">If you receive an error that IRM licensing isn't enabled, then you haven't set up OME for your organization yet.</span></span> <span data-ttu-id="3778e-182">如果您想要立即設定 OME，您必須使用全新的 OME 功能將其設定。</span><span class="sxs-lookup"><span data-stu-id="3778e-182">If you'd like to set up OME now, you must set it up to use the new OME capabilities.</span></span> <span data-ttu-id="3778e-183">如需資訊，請參閱[設定以 Azure 資訊保護基礎所建置的全新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="3778e-183">For information, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="3778e-184">Microsoft 不再支援的 OME 沒有的新功能的新部署的設定。</span><span class="sxs-lookup"><span data-stu-id="3778e-184">Microsoft no longer supports setting up new deployments of OME without the new capabilities.</span></span>

  <span data-ttu-id="3778e-185">如果您想要指定另一個動作，您可以選擇**新增巨集指令**。</span><span class="sxs-lookup"><span data-stu-id="3778e-185">You can choose **add action** if you want to specify another action.</span></span>

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a><span data-ttu-id="3778e-186">使用 Exchange Online PowerShell 來建立郵件流程規則來加密電子郵件，而不需要全新的 OME 功能</span><span class="sxs-lookup"><span data-stu-id="3778e-186">Use Exchange Online PowerShell to create a mail flow rule for encrypting email messages without the new OME capabilities</span></span>

1. <span data-ttu-id="3778e-187">連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3778e-187">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="3778e-188">如需詳細資訊，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3778e-188">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3778e-189">使用**New-transportrule**指令程式建立規則，並將_ApplyOME_參數設定為`$true`。</span><span class="sxs-lookup"><span data-stu-id="3778e-189">Create a rule by using the **New-TransportRule** cmdlet and set the _ApplyOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="3778e-190">這個範例需要所有傳送到 DrToniRamos@hotmail.com 的電子郵件訊息必須經過加密。</span><span class="sxs-lookup"><span data-stu-id="3778e-190">This example requires that all email messages sent to DrToniRamos@hotmail.com must be encrypted.</span></span>

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   <span data-ttu-id="3778e-191">**附註**：</span><span class="sxs-lookup"><span data-stu-id="3778e-191">**Notes**:</span></span>

   - <span data-ttu-id="3778e-192">新規則的唯一名稱是 「 Dr Toni Ramos 加密規則 」。</span><span class="sxs-lookup"><span data-stu-id="3778e-192">The unique name of the new rule is "Encrypt rule for Dr Toni Ramos".</span></span>

   - <span data-ttu-id="3778e-193">_SentTo_參數會指定 （由名稱、 電子郵件地址、 辨別的名稱等識別）。 郵件收件者。</span><span class="sxs-lookup"><span data-stu-id="3778e-193">The _SentTo_ parameter specifies the message recipients (identified by name, email address, distinguished name, etc.).</span></span> <span data-ttu-id="3778e-194">在這個範例中，收件者的電子郵件地址 」 DrToniRamos@hotmail.com 」 會識別。</span><span class="sxs-lookup"><span data-stu-id="3778e-194">In this example, the recipient is identified by the email address "DrToniRamos@hotmail.com".</span></span>

   - <span data-ttu-id="3778e-195">_SentToScope_參數會指定郵件的收件者的位置。</span><span class="sxs-lookup"><span data-stu-id="3778e-195">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="3778e-196">在這個範例中，收件者的信箱位於 hotmail 和不屬於 Office 365 組織，因此值`NotInOrganization`使用。</span><span class="sxs-lookup"><span data-stu-id="3778e-196">In this example, the recipient's mailbox is in hotmail and is not part of the Office 365 organization, so the value `NotInOrganization` is used.</span></span>

   <span data-ttu-id="3778e-197">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="3778e-197">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="3778e-198">移除但全新的 OME 功能未加密的電子郵件回覆的加密</span><span class="sxs-lookup"><span data-stu-id="3778e-198">Remove encryption from email replies encrypted without the new OME capabilities</span></span>

<span data-ttu-id="3778e-199">當您的電子郵件使用者傳送加密的郵件時，這些郵件的收件者可以回覆與加密回覆。</span><span class="sxs-lookup"><span data-stu-id="3778e-199">When your email users send encrypted messages, recipients of those messages can respond with encrypted replies.</span></span> <span data-ttu-id="3778e-200">您可以建立郵件流程規則來自動移除加密回覆讓組織中的電子郵件使用者不必登入加密入口網站來檢視它們。</span><span class="sxs-lookup"><span data-stu-id="3778e-200">You can create mail flow rules to automatically remove encryption from replies so email users in your organization don't have to sign in to the encryption portal to view them.</span></span> <span data-ttu-id="3778e-201">您可以使用 EAC 或 Windows PowerShell cmdlet 來定義這些規則。</span><span class="sxs-lookup"><span data-stu-id="3778e-201">You can use the EAC or Windows PowerShell cmdlets to define these rules.</span></span> <span data-ttu-id="3778e-202">如果您不尚未使用全新的 OME 功能，您可以只解密郵件的 [寄件者在您的組織或回覆郵件從組織內傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="3778e-202">If you are not yet using the new OME capabilities, you can only decrypt messages that are either sent from within your organization or messages that are replies to messages sent from within your organization.</span></span> <span data-ttu-id="3778e-203">您無法解密加密來自組織外的郵件。</span><span class="sxs-lookup"><span data-stu-id="3778e-203">You cannot decrypt encrypted messages originating from outside of your organization.</span></span>

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="3778e-204">使用 EAC 來建立移除全新的 OME 功能不加密的電子郵件回覆中加密的規則</span><span class="sxs-lookup"><span data-stu-id="3778e-204">Use the EAC to create a rule for removing encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="3778e-205">在網頁瀏覽器中使用已授與系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="3778e-205">In a web browser, using a work or school account that has been granted admin permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="3778e-206">選擇 [**管理**] 磚。</span><span class="sxs-lookup"><span data-stu-id="3778e-206">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="3778e-207">在 Microsoft 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。</span><span class="sxs-lookup"><span data-stu-id="3778e-207">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="3778e-208">在 EAC 中，移至 [**郵件流程** \> **規則**，然後選擇 [**新增** ![[新增] 圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。</span><span class="sxs-lookup"><span data-stu-id="3778e-208">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="3778e-209">如需使用 EAC 的詳細資訊，請參閱[Exchange 系統管理中心在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="3778e-209">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="3778e-210">在 [**名稱**] 中，輸入規則名稱，例如 Remove encryption，從內送郵件。</span><span class="sxs-lookup"><span data-stu-id="3778e-210">In **Name**, type a name for the rule, such as Remove encryption from incoming mail.</span></span>

6. <span data-ttu-id="3778e-211">在**套用此規則，如果**選取 [從郵件，例如**收件者位於**應該移除加密的條件\>**組織內**。</span><span class="sxs-lookup"><span data-stu-id="3778e-211">In **Apply this rule if** select the conditions where encryption should be removed from messages, such as **The recipient is located** \> **Inside the organization**.</span></span>

7. <span data-ttu-id="3778e-212">在 [**執行下列動作**，選取 [**修改郵件安全性** \> **OME 的先前版本中移除**。</span><span class="sxs-lookup"><span data-stu-id="3778e-212">In **Do the following**, select **Modify the message security** \> **Remove the previous version of OME**.</span></span>

8. <span data-ttu-id="3778e-213">選取**儲存**。</span><span class="sxs-lookup"><span data-stu-id="3778e-213">Select **Save**.</span></span>

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a><span data-ttu-id="3778e-214">使用 Exchange Online PowerShell 來建立規則，以移除全新的 OME 功能不加密的電子郵件回覆的加密</span><span class="sxs-lookup"><span data-stu-id="3778e-214">Use Exchange Online PowerShell to create a rule to remove encryption from email replies encrypted without the new OME capabilities</span></span>

1. <span data-ttu-id="3778e-215">連線至 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3778e-215">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="3778e-216">如需詳細資訊，請參閱[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="3778e-216">For more information, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="3778e-217">使用**New-transportrule**指令程式建立規則，並將_RemoveOME_參數設定為`$true`。</span><span class="sxs-lookup"><span data-stu-id="3778e-217">Create a rule by using the **New-TransportRule** cmdlet and set the _RemoveOME_ parameter to `$true`.</span></span>

   <span data-ttu-id="3778e-218">此範例會移除所有傳送到 Office 365 組織中收件者的郵件中的加密。</span><span class="sxs-lookup"><span data-stu-id="3778e-218">This example removes the encryption from all mail sent to recipients in the Office 365 organization.</span></span>

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   <span data-ttu-id="3778e-219">**附註**：</span><span class="sxs-lookup"><span data-stu-id="3778e-219">**Notes**:</span></span>

   - <span data-ttu-id="3778e-220">新規則的唯一名稱是 「 Remove encryption from incoming mail 」。</span><span class="sxs-lookup"><span data-stu-id="3778e-220">The unique name of the new rule is "Remove encryption from incoming mail".</span></span>

   - <span data-ttu-id="3778e-221">_SentToScope_參數會指定郵件的收件者的位置。</span><span class="sxs-lookup"><span data-stu-id="3778e-221">The _SentToScope_ parameter specifies the location of the message recipients.</span></span> <span data-ttu-id="3778e-222">在這個範例中，此值`InOrganization`值用來表示：</span><span class="sxs-lookup"><span data-stu-id="3778e-222">In this example, the value `InOrganization` value is used, which indicates:</span></span>

     - <span data-ttu-id="3778e-223">收件者是信箱、 郵件使用者、 群組或組織中的擁有郵件功能公用資料夾。</span><span class="sxs-lookup"><span data-stu-id="3778e-223">The recipient is a mailbox, mail user, group, or mail-enabled public folder in your organization.</span></span>

       <span data-ttu-id="3778e-224">或</span><span class="sxs-lookup"><span data-stu-id="3778e-224">or</span></span>

     - <span data-ttu-id="3778e-225">收件者的電子郵件地址位於公認的網域已設定為授權網域] 或 [內部轉送網域中您的組織，_並_將郵件已傳送或接收透過未驗證連線。</span><span class="sxs-lookup"><span data-stu-id="3778e-225">The recipient's email address is in an accepted domain that's configured as an authoritative domain or an internal relay domain in your organization, _and_ the message was sent or received over an authenticated connection.</span></span>

<span data-ttu-id="3778e-226">如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule) (機器翻譯)。</span><span class="sxs-lookup"><span data-stu-id="3778e-226">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3778e-227">相關主題</span><span class="sxs-lookup"><span data-stu-id="3778e-227">Related Topics</span></span>

[<span data-ttu-id="3778e-228">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="3778e-228">Encryption in Office 365</span></span>](encryption.md)

[<span data-ttu-id="3778e-229">設定全新的 Office 365 郵件加密功能</span><span class="sxs-lookup"><span data-stu-id="3778e-229">Set up new Office 365 Message Encryption capabilities</span></span>](set-up-new-message-encryption-capabilities.md)

[<span data-ttu-id="3778e-230">將商標新增至加密郵件</span><span class="sxs-lookup"><span data-stu-id="3778e-230">Add branding to encrypted messages</span></span>](add-your-organization-brand-to-encrypted-messages.md)

[<span data-ttu-id="3778e-231">Exchange Online 中的郵件流程規則 (傳輸規則)</span><span class="sxs-lookup"><span data-stu-id="3778e-231">Mail flow rules (transport rules) in Exchange Online</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[<span data-ttu-id="3778e-232">Exchange Online Protection 中郵件流程規則 （傳輸規則）</span><span class="sxs-lookup"><span data-stu-id="3778e-232">Mail flow rules (transport rules) in Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=506708)
