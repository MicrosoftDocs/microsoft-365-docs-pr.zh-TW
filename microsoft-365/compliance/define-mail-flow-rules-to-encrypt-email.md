---
title: 定義郵件流規則以加密 Office 365 中的電子郵件
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
description: 系統管理員可以了解如何建立郵件流程規則 （傳輸規則） 來加密及解密使用 Office 365 郵件加密的郵件。
ms.openlocfilehash: a2f37bff8fa3fd45999a44341cfdb077b4f43e62
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595338"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages-in-office-365"></a>定義郵件流規則以加密 Office 365 中的電子郵件

身為 Office 365 全域管理員，您可以建立郵件流程規則 （也稱為傳輸規則） 來協助保護您傳送和接收的電子郵件訊息。 您可以設定規則以加密所有外寄的電子郵件，並移除加密，從加密的郵件來自組織內部或從組織傳送加密郵件的回覆。 若要建立這些規則，您可以使用 Exchange 系統管理中心 (EAC) 或 Exchange Online PowerShell。 除了整體加密的郵件，您也可以選擇啟用或停用使用者的個別郵件加密選項。

您無法在組織外加密來自寄件者的內送的郵件。

如果您最近移轉從 AD RMS Azure 資訊保護，您需要檢閱現有的郵件流程規則，以確保它們繼續在新環境中運作。 此外，如果您想要利用新的 Office 365 郵件加密 (OME) 功能給您透過 Azure 資訊保護，您必須更新您現有的郵件流程規則。 否則，您的使用者將會繼續收到加密的郵件，而不是新的、 無縫 OME 經驗會使用先前的 HTML 附件格式。 如果您尚未設定 OME 尚未，請參閱[設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)的資訊。

元件構成郵件流程規則及郵件流程規則的工作的方式的相關資訊，請參閱[Exchange Online 中的郵件流程規則 （傳輸規則）](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)。 如需有關使用 Azure 資訊保護郵件流程規則的運作方式的詳細資訊，請參閱[Azure 資訊保護標籤設定 Exchange Online 的郵件流程規則](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)。

> [!IMPORTANT]
> 混合式 Exchange 環境中，內部部署使用者可以傳送電子郵件會路由傳送到 Exchange Online 時，才使用 OME 加密的郵件。 若要設定 OME 混合式 Exchange 環境中，您需要[設定混合式使用混合組態精靈](https://docs.microsoft.com/Exchange/exchange-hybrid)的第一個，然後[將郵件設定為從您的電子郵件伺服器到 Office 365 的流程](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)。 一次您已設定郵件來經過 Office 365，則您也可以使用這份指導的 OME 設定郵件流程規則。

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>建立郵件流程規則來加密與新的 OME 功能的電子郵件

您可以定義郵件流程規則的觸發郵件加密與新的 OME 功能使用 EAC。

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>使用 EAC 來建立加密與新的 OME 功能的電子郵件訊息的規則

1. 在網頁瀏覽器中使用已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。

2. 選擇 [**管理**] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。

4. 在 EAC 中，移至 [**郵件流程** \> **規則**，然後選擇 [**新增** ![[新增] 圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。 如需使用 EAC 的詳細資訊，請參閱[Exchange 系統管理中心在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 [**名稱**] 中，輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。

6. 在 [**套用此規則情況**選擇一個條件，並輸入值，如果需要的話。 例如，若要加密郵件移至 [DrToniRamos@hotmail.com:

   1. 在 [**套用此規則情況**，請選取 [**收件者**。

   2. 從連絡人清單中選取現有名稱，或在 [**檢查名稱**] 方塊中輸入新的電子郵件地址。

      - 若要選取現有名稱，從清單中選取它，然後按一下 [**確定]**。

      - 若要輸入新名稱，在 [**檢查名稱**] 方塊中輸入的電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。

7. 若要新增更多條件，請選擇 [**更多選項]** 然後選擇 [**新增條件**，並從清單中選取。

   例如，只有當收件者是在組織外，請套用規則，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外部的** \> **[確定]**。

8. 若要啟用加密使用全新的 OME 功能，從**執行下列動作**，選取 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。 從清單中選取的 RMS 範本，選擇 [**儲存**]，然後選擇 [**確定]**。
  
  範本的清單包含所有的預設範本及 Office 365 所使用的選項，以及您已建立的任何自訂範本。 如果清單是空的請確定您已設定 Office 365 郵件加密與新功能[設定新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)所述。 如需預設範本的資訊，請參閱[設定與管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。 [**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 [**僅限加密**] 選項的相關資訊，請參閱[僅加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

  如果您想要指定另一個動作，您可以選擇**新增巨集指令**。

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>使用 EAC 來更新現有郵件流程規則，以使用全新的 OME 功能

1. 在網頁瀏覽器中使用已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。

2. 選擇 [**管理**] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。

4. 在 EAC 中，移至 [郵件流程]**** \> [規則]****。

5. 在 [郵件流程規則] 清單中選取您想要修改以使用全新的 OME 功能]，然後選擇 [**編輯**的規則![編輯圖示](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。

6. 若要啟用加密使用全新的 OME 功能，從**執行下列動作**，選擇 [**修改郵件安全性**，然後選擇**適用於 Office 365 郵件加密和權限保護**。 從清單中選取的 RMS 範本，選擇 [**儲存]** ，然後選擇 [**確定]**。

   範本的清單包含所有的預設範本及 Office 365 所使用的選項，以及您已建立的任何自訂範本。 如果清單是空的請確定您已設定 Office 365 郵件加密與新功能如所述[設定頂端的 Azure 資訊保護為基礎的新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。 如需預設範本的資訊，請參閱[設定與管理 Azure 資訊保護的範本](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。 [**不要轉寄**] 選項的相關資訊，請參閱[不要轉寄電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。 [**僅限加密**] 選項的相關資訊，請參閱[僅加密的電子郵件] 選項](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

   如果您想要指定另一個動作，您可以選擇**新增巨集指令**。

7. 從**執行下列動作**] 清單中，移除任何已指派給**修改郵件安全性**的動作\>**套用 OME 的舊版本**。

8. 選擇 [儲存]****。

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>建立郵件流程規則的 Office 365 郵件加密沒有的新功能

如果您還尚未移您的 Office 365 組織至全新的 OME 功能，可用於這些工作定義郵件流規則以加密您組織的郵件。 Microsoft 建議您先將移至全新的 OME 功能，只要是合理的貴組織的計劃。 如需相關指示，請參閱[設定以 Azure 資訊保護基礎所建置的全新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>使用 EAC 來建立郵件流程規則來加密電子郵件，而不需要全新的 OME 功能

1. 在網頁瀏覽器中使用已授與全域系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。

2. 選擇 [**管理**] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。

4. 在 EAC 中，移至 [**郵件流程** \> **規則**，然後選擇 [**新增** ![[新增] 圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。 如需使用 EAC 的詳細資訊，請參閱[Exchange 系統管理中心在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 [**名稱**] 中，輸入規則名稱，例如 Encrypt mail for DrToniRamos@hotmail.com。

6. 在 [**套用此規則情況**選擇一個條件，並輸入值，如果需要的話。 例如，若要加密郵件移至 [DrToniRamos@hotmail.com:

   1. 在 [**套用此規則情況**，請選取 [**收件者**。

   2. 從連絡人清單中選取現有名稱，或在 [**檢查名稱**] 方塊中輸入新的電子郵件地址。

      - 若要選取現有名稱，從清單中選取它，然後按一下 [**確定]**。

      - 若要輸入新名稱，在 [**檢查名稱**] 方塊中輸入的電子郵件地址，然後選取 [**檢查名稱** \> **[確定]**。

7. 若要新增更多條件，選擇 [**更多選項]** 然後選取 [**新增條件，** 並從清單中選取。

   例如，只有當收件者是在組織外，請套用規則，選取 [**新增條件**，然後選取 [**收件者是外部/內部** \> **組織外部的** \> **[確定]**。

8. 若要啟用加密，而不使用全新的 OME 功能中**執行下列動作**,，請選取 [**修改郵件安全性** \> **套用 OME 舊版**]，然後選擇 [**儲存**。

  如果您收到未啟用 IRM 授權，則您尚未為您的組織尚未設定 OME 的錯誤。 如果您想要立即設定 OME，您必須使用全新的 OME 功能將其設定。 如需資訊，請參閱[設定以 Azure 資訊保護基礎所建置的全新 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。 Microsoft 不再支援的 OME 沒有的新功能的新部署的設定。

  如果您想要指定另一個動作，您可以選擇**新增巨集指令**。

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>使用 Exchange Online PowerShell 來建立郵件流程規則來加密電子郵件，而不需要全新的 OME 功能

1. 連線至 Exchange Online PowerShell。 如需詳細資訊，請參閱＜[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)＞。

2. 使用**New-transportrule**指令程式建立規則，並將_ApplyOME_參數設定為`$true`。

   這個範例需要所有傳送到 DrToniRamos@hotmail.com 的電子郵件訊息必須經過加密。

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   **附註**：

   - 新規則的唯一名稱是 「 Dr Toni Ramos 加密規則 」。

   - _SentTo_參數會指定 （由名稱、 電子郵件地址、 辨別的名稱等識別）。 郵件收件者。 在這個範例中，收件者的電子郵件地址 」 DrToniRamos@hotmail.com 」 會識別。

   - _SentToScope_參數會指定郵件的收件者的位置。 在這個範例中，收件者的信箱位於 hotmail 和不屬於 Office 365 組織，因此值`NotInOrganization`使用。

   如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)。

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>移除但全新的 OME 功能未加密的電子郵件回覆的加密

當您的電子郵件使用者傳送加密的郵件時，這些郵件的收件者可以回覆與加密回覆。 您可以建立郵件流程規則來自動移除加密回覆讓組織中的電子郵件使用者不必登入加密入口網站來檢視它們。 您可以使用 EAC 或 Windows PowerShell cmdlet 來定義這些規則。 如果您不尚未使用全新的 OME 功能，您可以只解密郵件的 [寄件者在您的組織或回覆郵件從組織內傳送的郵件。 您無法解密加密來自組織外的郵件。

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>使用 EAC 來建立移除全新的 OME 功能不加密的電子郵件回覆中加密的規則

1. 在網頁瀏覽器中使用已授與系統管理員權限，[登入 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)工作或學校帳戶。

2. 選擇 [**管理**] 磚。

3. 在 Microsoft 365 系統管理中心中，選擇 [**系統管理中心** \> **Exchange**。

4. 在 EAC 中，移至 [**郵件流程** \> **規則**，然後選擇 [**新增** ![[新增] 圖示](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **建立新的規則**。 如需使用 EAC 的詳細資訊，請參閱[Exchange 系統管理中心在 Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 [**名稱**] 中，輸入規則名稱，例如 Remove encryption，從內送郵件。

6. 在**套用此規則，如果**選取 [從郵件，例如**收件者位於**應該移除加密的條件\>**組織內**。

7. 在 [**執行下列動作**，選取 [**修改郵件安全性** \> **OME 的先前版本中移除**。

8. 選取 [儲存]****。

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>使用 Exchange Online PowerShell 來建立規則，以移除全新的 OME 功能不加密的電子郵件回覆的加密

1. 連線至 Exchange Online PowerShell。 如需詳細資訊，請參閱＜[連線至 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)＞。

2. 使用**New-transportrule**指令程式建立規則，並將_RemoveOME_參數設定為`$true`。

   此範例會移除所有傳送到 Office 365 組織中收件者的郵件中的加密。

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   **附註**：

   - 新規則的唯一名稱是 「 Remove encryption from incoming mail 」。

   - _SentToScope_參數會指定郵件的收件者的位置。 在這個範例中，此值`InOrganization`值用來表示：

     - 收件者是信箱、 郵件使用者、 群組或組織中的擁有郵件功能公用資料夾。

       或

     - 收件者的電子郵件地址位於公認的網域已設定為授權網域] 或 [內部轉送網域中您的組織，_並_將郵件已傳送或接收透過未驗證連線。

如需詳細的語法和參數資訊，請參閱 [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule)。

## <a name="related-topics"></a>相關主題

[Office 365 中的加密](encryption.md)

[設定全新的 Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)

[將商標新增至加密郵件](add-your-organization-brand-to-encrypted-messages.md)

[Exchange Online 中的郵件流程規則 (傳輸規則)](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Exchange Online Protection 中的郵件流程規則 (傳輸規則)](https://go.microsoft.com/fwlink/p/?LinkId=506708)
