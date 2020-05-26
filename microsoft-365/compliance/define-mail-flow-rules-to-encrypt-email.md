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
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>定義郵件流程規則以加密電子郵件

以全域管理員的身分，您可以建立郵件流程規則（也稱為傳輸規則），以協助保護您傳送和接收的電子郵件訊息。 您可以設定規則來加密任何外寄電子郵件訊息，並移除來自組織內部的加密郵件的加密，或從組織傳送的加密郵件回復。 您可以使用 Exchange 系統管理中心（EAC）或 Exchange Online PowerShell 來建立這些規則。 除了整體加密規則，您也可以選擇啟用或停用使用者的個別郵件加密選項。

您無法對來自組織外部寄件者的輸入郵件進行加密。

如果您最近從 AD RMS 遷移至 Azure 資訊保護，您必須複查現有的郵件流程規則，以確保它們繼續在您的新環境中運作。 此外，如果您想要利用 Azure 資訊保護可供您使用的新 Office 365 郵件加密（OME）功能，您必須更新現有的郵件流程規則。 否則，您的使用者將繼續接收使用舊版 HTML 附件格式的加密郵件，而不是新的無縫 OME 經驗。 若尚未設定 OME，請參閱[設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)以取得詳細資訊。

如需組成郵件流程規則的元件，以及郵件流程規則如何運作的詳細資訊，請參閱[郵件流程規則（傳輸規則）中的 Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。 如需郵件流程規則如何使用 Azure 資訊保護的詳細資訊，請參閱設定[Exchange Online mail 流程規則以取得 azure 資訊保護標籤](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。

> [!IMPORTANT]
> 在混合式 Exchange 環境中，只有在透過 Exchange Online 路由傳送電子郵件時，內部部署使用者才能使用 OME 傳送和接收加密郵件。 若要設定混合式 Exchange 環境中的 OME，您必須先[使用混合式設定向導設定混合](https://docs.microsoft.com/Exchange/exchange-hybrid)式，然後再[將郵件設定為從 Office 365 流向您的電子郵件伺服器](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server)，並[將郵件設定為從您的電子郵件伺服器流向 Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。 將郵件設定為流過 Office 365 後，您就可以使用本指南來設定 OME 的郵件流程規則。

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>建立郵件流程規則，以新的 OME 功能加密電子郵件

您可以使用 EAC 來定義郵件流程規則，以使用新的 OME 功能來觸發郵件加密。

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>使用 EAC 建立以新的 OME 功能加密電子郵件的規則

1. 在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 選擇 [**管理**] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [系統**管理中心**] [ \> **Exchange**]。

4. 在 EAC 中，移至 [**郵件流程** \> **規則**]，然後選取 [**新增**新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。 如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 [**名稱**] 中，輸入規則的名稱，例如 [加密 DrToniRamos@hotmail.com 的郵件]。

6. 在 [套用**此規則 if**] 中，選取條件，然後視需要輸入值。 例如，若要加密要 DrToniRamos@hotmail.com 的郵件：

   1. 在 [套用**此規則 if**] 中，選取**收件者為**。

   2. 從連絡人清單中選取現有名稱，或在 [**檢查名稱**] 方塊中輸入新的電子郵件地址。

      - 若要選取現有名稱，請從清單中進行選取，然後按一下 **[確定]**。

      - 若要輸入新名稱，請在 [**檢查名稱**] 方塊中輸入電子郵件地址，然後選取 [**檢查名稱** \> **]**。

7. 若要新增更多條件，請選擇 [**更多選項**]，然後選擇 [**新增條件**]，然後從清單中選取。

   例如，若要在組織外部的收件者之外套用規則，請選取 [**新增條件**]，然後選取收件者在組織外**外部/內部的收件**者 \> **Outside the organization** \> ** **。

8. 若要使用新的 OME 功能來啟用加密，請從**執行下列**動作，選取 **[修改郵件安全性**]，然後選擇 [套用**Office 365 郵件加密和許可權保護**]。 從清單中選取 RMS 範本，然後選擇 [**儲存**]，然後選擇 **[確定]**。
  
  範本清單包括所有預設範本和選項，以及您已建立供 Office 365 使用的任何自訂範本。 如果清單是空的，請確定您已使用[設定新的 office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)中所述的新功能，來設定 Office 365 郵件加密。 如需預設範本的相關資訊，請參閱設定[及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。 如需有關 [**不要轉寄**] 選項的詳細資訊，請參閱[請勿轉寄選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 如需只供**加密**之選項的詳細資訊，請參閱[僅限加密選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

  如果您想要指定另一個動作，您可以選擇 [**新增動作**]。

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>使用 EAC 更新現有的郵件流程規則，以使用新的 OME 功能

1. 在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 選擇 [**管理**] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [系統**管理中心**] [ \> **Exchange**]。

4. 在 EAC 中，移至 [郵件流程]**** \> [規則]****。

5. 在郵件流程規則清單中，選取您要修改的規則，以使用新的 OME 功能，然後選擇 [**編輯** ![ 編輯圖示] ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 。

6. 若要使用新的 OME 功能來啟用加密，請從**執行下列**動作，選擇 [**修改郵件安全性**]，然後選擇 [套用**Office 365 郵件加密和許可權保護**]。 從清單中選取 RMS 範本，然後選擇 [**儲存**]，然後選擇 **[確定]**。

   範本清單包括所有預設範本和選項，以及您已建立供 Office 365 使用的任何自訂範本。 如果清單是空的，請確定您已設定 Office 365 郵件加密的新功能，如[設定以 Azure 資訊保護為基礎的新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。 如需預設範本的相關資訊，請參閱設定[及管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。 如需有關 [**不要轉寄**] 選項的詳細資訊，請參閱[請勿轉寄選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 如需只供**加密**之選項的詳細資訊，請參閱[僅限加密選項的電子郵件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   如果您想要指定另一個動作，您可以選擇 [**新增動作**]。

7. 從 [**執行下列**動作] 清單中，移除指派給**修改郵件安全性**的任何動作套用 \> **先前版本的 OME**。

8. 選擇 [儲存]****。

## <a name="create-mail-flow-rules-to-remove-encryption-for-outgoing-email-messages-with-the-new-ome-capabilities"></a>建立郵件流程規則，以使用新的 OME 功能移除外寄電子郵件的加密

您可以使用 EAC 來定義郵件流程規則，以使用新的 OME 功能來觸發移除郵件加密。

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>使用 EAC 來建立規則，以使用新的 OME 功能來移除電子郵件中的加密

1. 在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 選擇 [**管理**] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [系統**管理中心**] [ \> **Exchange**]。

4. 在 EAC 中，移至 [**郵件流程** \> **規則**]，然後選取 [**新增**新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。 如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 [**名稱**] 中，輸入規則的名稱，例如 [從外寄郵件移除加密]。

6. 在 [套用**此規則**條件] 中，選取應該從郵件中移除加密的條件。 新增**寄件者位於** \> **組織內**。 現在，新增其他條件以設定特定的收件者，例如**收件者位於** \> **組織外**。

7. 在**執行下列**動作中，選取 **[修改郵件安全性** \> **移除 Office 365 訊息加密和許可權保護**]。

8. 選取 [儲存]****。

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>建立沒有新功能的 Office 365 郵件加密的郵件流程規則

如果您尚未將組織移至新的 OME 功能，請使用這些工作來定義郵件流程規則，以加密組織的郵件。 Microsoft 建議您在組織合理的情況時，安排移至新的 OME 功能。 如需相關指示，請參閱[設定以 Azure 資訊保護為基礎的新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>使用 EAC 來建立郵件流程規則，以加密不含新 OME 功能的電子郵件

1. 在網頁瀏覽器中，使用已被授與全域系統管理員許可權的公司或學校帳戶登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 選擇 [**管理**] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [系統**管理中心**] [ \> **Exchange**]。

4. 在 EAC 中，移至 [**郵件流程** \> **規則**]，然後選取 [**新增**新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。 如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 [**名稱**] 中，輸入規則的名稱，例如 [加密 DrToniRamos@hotmail.com 的郵件]。

6. 在 [套用**此規則**] 選取條件時，必要時輸入值。 例如，若要加密要 DrToniRamos@hotmail.com 的郵件：

   1. 在 [套用**此規則 if**] 中，選取**收件者為**。

   2. 從連絡人清單中選取現有名稱，或在 [**檢查名稱**] 方塊中輸入新的電子郵件地址。

      - 若要選取現有名稱，請從清單中進行選取，然後按一下 **[確定]**。

      - 若要輸入新名稱，請在 [**檢查名稱**] 方塊中輸入電子郵件地址，然後選取 [**檢查名稱** \> **]**。

7. 若要新增更多條件，請選擇 [**更多選項**]，然後選取 [**新增條件**]，然後從清單中選取。

   例如，若要在組織外部的收件者之外套用規則，請選取 [**新增條件**]，然後選取收件者在組織外**外部/內部的收件**者 \> **Outside the organization** \> ** **。

8. 若要在不使用新 OME 功能的情況下啟用加密，請在**執行下列**動作中，選取 **[修改郵件安全性**] 套用 \> **舊版的 OME**，然後選擇 [**儲存**]。

  如果您收到未啟用 IRM 授權的錯誤，則表示尚未為您的組織設定 OME。 如果您想要立即設定 OME，則必須將它設定為使用新的 OME 功能。 如需詳細資訊，請參閱[在 Azure 資訊保護上建立新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。 Microsoft 不再支援設定新的 OME 部署，沒有新功能。

  如果您想要指定另一個動作，您可以選擇 [**新增動作**]。

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>使用 Exchange Online PowerShell 建立郵件流程規則，以加密不含新 OME 功能的電子郵件

1. 連線至 Exchange Online PowerShell。 如需詳細資訊，請參閱＜[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)＞。

2. 使用**New-TransportRule** Cmdlet 來建立規則，並將_ApplyOME_參數設為 `$true` 。

   本範例要求所有傳送至 DrToniRamos@hotmail.com 的電子郵件都必須加密。

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   > [!NOTE]
   > 
   > - 新規則的唯一名稱是「Dr Toni Ramos 的加密規則」。
   > 
   > - _SentTo_參數會指定郵件收件者（透過名稱、電子郵件地址、辨識名稱等）。 在此範例中，收件者會透過電子郵件地址 "DrToniRamos@hotmail.com" 加以識別。
   > 
   > - _SentToScope_參數會指定郵件收件者的位置。 在此範例中，收件者的信箱是在 hotmail 中，而且不是組織的一部分，因此 `NotInOrganization` 會使用此值。
   
   如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule)。

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>從加密的電子郵件回復中移除加密，但不含新的 OME 功能

當您的電子郵件使用者傳送加密郵件時，這些郵件的收件者便可使用加密的回復來回應。 您可以建立郵件流程規則，以自動移除回復的加密，使組織中的電子郵件使用者不必登入加密入口網站以進行查看。 您可以使用 EAC 或 Windows PowerShell Cmdlet 來定義這些規則。 若尚未使用新的 OME 功能，您只能解密從組織內部傳送的郵件，或是對從組織內傳送的郵件回復的郵件進行解密。 您無法解密來自組織外部的加密郵件。

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>使用 EAC 來建立刪除電子郵件回復加密的規則，而不使用新的 OME 功能

1. 在網頁瀏覽器中，使用已獲授與系統管理員許可權的公司或學校帳戶登[入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 選擇 [**管理**] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [系統**管理中心**] [ \> **Exchange**]。

4. 在 EAC 中，移至 [**郵件流程** \> **規則**]，然後選取 [**新增**新圖示] 以 ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。 如需使用 EAC 的詳細資訊，請參閱 exchange [Online 中的 exchange 系統管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 [**名稱**] 中，輸入規則的名稱，例如 [移除來自傳入郵件的加密]。

6. 在 [套用**此規則**] 中，選取應該從郵件中移除加密的情況，例如**收件者位於** \> **組織內**。

7. 在**執行下列**動作中，選取 **[修改郵件安全性** \> **移除舊版 OME**]。

8. 選取 [儲存]****。

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>使用 Exchange Online PowerShell 建立規則，以從加密的電子郵件回復中移除加密，但不使用新的 OME 功能

1. 連線至 Exchange Online PowerShell。 如需詳細資訊，請參閱＜[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)＞。

2. 使用**New-TransportRule** Cmdlet 來建立規則，並將_RemoveOME_參數設為 `$true` 。

   此範例會移除傳送給組織中收件者的所有郵件的加密。

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   > [!NOTE]
   > 
   > - 新規則的唯一名稱是「移除來自傳入郵件的加密」。
   > 
   > - _SentToScope_參數會指定郵件收件者的位置。 在此範例中， `InOrganization` 會使用 value 值，表示：
   > 
   >   - 收件者是組織中的信箱、郵件使用者、群組或擁有郵件功能的公用資料夾。
   > 
   >     或
   > 
   >   - 收件者的電子郵件地址位於已設定為授權網域或組織內部轉送網域的公認網域中，_且_透過已驗證的連線來傳送或接收郵件。

如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule)。

## <a name="related-topics"></a>相關主題

[Office 365 中的加密](encryption.md)

[設定全新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)

[將商標新增至加密郵件](add-your-organization-brand-to-encrypted-messages.md)

[Exchange Online 中的郵件流程規則 (傳輸規則)](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Exchange Online Protection 中的郵件流程規則 (傳輸規則)](https://go.microsoft.com/fwlink/p/?LinkId=506708)
