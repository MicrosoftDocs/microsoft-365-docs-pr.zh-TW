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
description: 系統管理員可以使用 Office 365 郵件加密，瞭解如何建立郵件流程規則 (傳輸規則) 以加密及解密郵件。
ms.openlocfilehash: 5c0f67acdb5d8fbfff216742cab1c49732c4ab24
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939644"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>定義郵件流程規則以加密電子郵件

作為管理 Exchange Online 的系統管理員，您可以建立郵件流程規則 (也稱為傳輸規則) ，以協助保護您傳送和接收的電子郵件訊息。 您可以設定規則來加密任何外寄電子郵件訊息，並移除來自組織內部的加密郵件的加密，或從組織傳送的加密郵件回復。 您可以使用 Exchange 系統管理中心 (EAC) 或 Exchange Online PowerShell 建立這些規則。 除了整體加密規則，您也可以選擇啟用或停用使用者的個別郵件加密選項。

您無法對來自組織外部寄件者的輸入郵件進行加密。

如果您最近從 Active Directory RMS 遷移到 Azure 資訊保護，您必須複查現有的郵件流程規則，以確保它們繼續在您的新環境中運作。 此外，如果您想要利用新的 Office 365 郵件加密 (可透過 Azure 資訊保護 OME) 功能，您必須更新現有的郵件流程規則。 否則，您的使用者將繼續接收使用舊版 HTML 附件格式的加密郵件，而不是新的無縫 OME 經驗。 若尚未設定 OME，請參閱 [設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md) 以取得詳細資訊。

如需有關組成郵件流程規則的元件，以及郵件流程規則如何運作的詳細資訊，請參閱 [mail flow rules (transport rules) In Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。 如需郵件流程規則如何使用 Azure 資訊保護的詳細資訊，請參閱設定 [Exchange Online mail 流程規則以取得 azure 資訊保護標籤](/azure/information-protection/deploy-use/configure-exo-rules)。

> [!IMPORTANT]
> 在混合式 Exchange 環境中，只有在透過 Exchange Online 路由傳送電子郵件時，內部部署使用者才能使用 OME 傳送和接收加密郵件。 若要設定混合式 Exchange 環境中的 OME，您必須先 [使用混合式設定向導設定混合](/Exchange/exchange-hybrid) 式，然後再 [將郵件設定為從 Office 365 流向您的電子郵件伺服器](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) ，並 [將郵件設定為從您的電子郵件伺服器流向 Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。 將郵件設定為流過 Office 365 後，您就可以使用本指南來設定 OME 的郵件流程規則。

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>建立郵件流程規則，以新的 OME 功能加密電子郵件

您可以使用 EAC 來定義郵件流程規則，以使用新的 OME 功能來觸發郵件加密。

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>使用 EAC 建立以新的 OME 功能加密電子郵件的規則

1. 在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登 [入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 選擇 [ **管理** ] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [系統 **管理中心**] [ \> **Exchange**]。

4. 在 EAC 中，移至 [ **郵件流程** \> **規則** ]，然後選取 [ **新增** 新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。 如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](/exchange/exchange-admin-center)。

5. 在 [ **名稱**] 中，輸入規則的名稱，例如 [加密 DrToniRamos@hotmail.com 的郵件]。

6. 在 [套用 **此規則 if**] 中，選取條件，然後視需要輸入值。 例如，若要加密要 DrToniRamos@hotmail.com 的郵件：

   1. 在 [套用 **此規則 if**] 中，選取 **收件者為**。

   2. 從連絡人清單中選取現有名稱，或在 [ **檢查名稱** ] 方塊中輸入新的電子郵件地址。

      - 若要選取現有名稱，請從清單中進行選取，然後按一下 **[確定]**。

      - 若要輸入新名稱，請在 [ **檢查名稱** ] 方塊中輸入電子郵件地址，然後選取 [ **檢查名稱** \> **]**。

7. 若要新增更多條件，請選擇 [ **更多選項** ]，然後選擇 [ **新增條件** ]，然後從清單中選取。

   例如，若要在組織外部的收件者之外套用規則，請選取 [**新增條件**]，然後選取收件者在組織外 **外部/內部的收件** 者 \>  \> ****。

8. 若要使用新的 OME 功能來啟用加密，請從 **執行下列** 動作，選取 **[修改郵件安全性** ]，然後選擇 [套用 **Office 365 郵件加密和許可權保護**]。 從清單中選取 RMS 範本，然後選擇 [ **儲存**]，然後選擇 **[確定]**。
  
  範本清單包括所有預設範本和選項，以及您已建立供 Office 365 使用的任何自訂範本。 如果清單是空的，請確定您已使用 [設定新的 office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)中所述的新功能，來設定 Office 365 郵件加密。 如需預設範本的相關資訊，請參閱設定 [及管理 Azure 資訊保護的範本](/information-protection/deploy-use/configure-policy-templates)。 如需有關 [ **不要轉寄** ] 選項的詳細資訊，請參閱 [請勿轉寄選項的電子郵件](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 如需 **唯讀選項的** 詳細資訊，請參閱 [電子郵件加密專用選項](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

  如果您想要指定另一個動作，您可以選擇 [ **新增動作** ]。

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>使用 EAC 更新現有的郵件流程規則，以使用新的 OME 功能

1. 在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登 [入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 選擇 [ **管理** ] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [系統 **管理中心**] [ \> **Exchange**]。

4. 在 EAC 中，移至 [郵件流程] \> [規則]。

5. 在郵件流程規則清單中，選取您要修改的規則，以使用新的 OME 功能，然後選擇 [ **編輯** ![ 編輯圖示] ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。

6. 若要使用新的 OME 功能來啟用加密，請從 **執行下列** 動作，選擇 [ **修改郵件安全性** ]，然後選擇 [套用 **Office 365 郵件加密和許可權保護**]。 從清單中選取 RMS 範本，然後選擇 [ **儲存** ]，然後選擇 **[確定]**。

   範本清單包括所有預設範本和選項，以及您已建立供 Office 365 使用的任何自訂範本。 如果清單是空的，請確定您已設定 Office 365 郵件加密的新功能，如 [設定以 Azure 資訊保護為基礎的新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。 如需預設範本的相關資訊，請參閱設定 [及管理 Azure 資訊保護的範本](/information-protection/deploy-use/configure-policy-templates)。 如需有關 [不要轉寄] 選項的詳細資訊，請參閱 [請勿轉寄選項的電子郵件](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 如需只供加密之選項的詳細資訊，請參閱 [只對電子郵件加密選項](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   如果您想要指定另一個動作，您可以選擇 [ **新增動作** ]。

7. 從 [ **執行下列** 動作] 清單中，移除指派給 **修改郵件安全性** 的任何動作套用 \> **先前版本的 OME**。

8. 選擇 **[儲存]**。

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-the-new-ome-capabilities"></a>建立郵件流程規則，以使用新的 OME 功能來移除電子郵件的加密

您可以使用 EAC 來定義郵件流程規則，以使用新的 OME 功能來觸發移除郵件加密。

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>使用 EAC 來建立規則，以使用新的 OME 功能來移除電子郵件中的加密

您可以移除組織可存取的加密。 這表示使用組織所套用之加密的任何郵件，或是使用僅限加密的限制所保護的任何郵件。

1. 在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登 [入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 選擇 [ **管理** ] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [系統 **管理中心**] [ \> **Exchange**]。

4. 在 EAC 中，移至 [ **郵件流程** \> **規則** ]，然後選取 [ **新增** 新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。 如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](/exchange/exchange-admin-center)。

5. 在 [ **名稱**] 中，輸入規則的名稱，例如 [從外寄郵件移除加密]。

6. 在 [套用 **此規則** 條件] 中，選取應該從郵件中移除加密的條件。 新增 **寄件者位於** \> **組織內部**，_或_**收** 件者位於 \> **組織內**。

7. 在 **執行下列** 動作中，選取 **[修改郵件安全性** \> **移除 Office 365 訊息加密和許可權保護**]。

8. 選取 [儲存]。

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>建立沒有新功能的 Office 365 郵件加密的郵件流程規則

如果您還沒有將組織移至新的 OME 功能，Microsoft 建議您在組織合理時，規劃移至新的 OME 功能。 如需相關指示，請參閱 [設定以 Azure 資訊保護為基礎的新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。 否則，請參閱 [定義未使用新 OME 功能之 Office 365 郵件加密的郵件流程規則](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities)。

## <a name="related-topics"></a>相關主題

[Office 365 中的加密](encryption.md)

[設定全新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)

[將商標新增至加密郵件](add-your-organization-brand-to-encrypted-messages.md)

[Exchange Online 中的郵件流程規則 (傳輸規則)](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

[Exchange Online Protection 中的郵件流程規則 (傳輸規則)](../security/office-365-security/mail-flow-rules-transport-rules-0.md)
