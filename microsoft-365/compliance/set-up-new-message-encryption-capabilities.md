---
title: 設定全新的郵件加密功能
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 瞭解可與組織內外的人員進行受保護的電子郵件通訊的全新 Office 365 訊息加密功能。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9b738c0f93b8958e441b34b458942c2b34c16661
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228576"
---
# <a name="set-up-new-message-encryption-capabilities"></a>設定全新的郵件加密功能

新的 Office 365 郵件加密 (OME) 功能可讓組織與任何裝置上的任何人共用受保護的電子郵件。 使用者可以與其他 Microsoft 365 組織以及使用 Outlook.com、Gmail 和其他電子郵件服務的非客戶交換受保護的郵件。

遵循下列步驟以確保新的 OME 功能可在您的組織中使用。

## <a name="verify-that-azure-rights-management-is-active"></a>驗證 Azure 版權管理作用中

全新的 OME 功能利用 [Azure 版權管理服務 (Azure RMS)](/azure/information-protection/what-is-information-protection) 中的保護功能，它是 [Azure 資訊保護](/azure/information-protection/what-is-azure-rms)用來透過加密和存取控制保護電子郵件和文件的技術。

使用全新 OME 功能的唯一先決條件是必須在組織的租用戶中啟用 [Azure 版權管理](/azure/information-protection/what-is-azure-rms)。 如果是，Microsoft 365 會自動啟用新的 OME 功能，您不需要採取任何動作。

Azure RMS 也會對多數合格方案自動啟用，因此您也不需要對此採取任何動作。 如需詳細資訊，請參閱[啟用 Azure 版權管理](/azure/information-protection/activate-service)。

> [!IMPORTANT]
> 如果您使用 Active Directory 版權管理服務 (AD RMS) 搭配 Exchange Online，您需要先[移轉至 Azure 資訊保護](/azure/information-protection/migrate-from-ad-rms-to-azure-rms)，之後才能使用新的 OME 功能。 OME 與 AD RMS 不相容。

如需詳細資訊，請參閱：

- [要使用全新的 OME 功能，我需要什麼訂閱？](ome-faq.yml#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities-)可檢查您的訂閱方案是否包含 Azure 資訊保護 (其中包含 Azure RMS 功能)。
- [Azure 資訊保護](https://azure.microsoft.com/services/information-protection/)可取得購買合格訂閱的相關資訊。

### <a name="manually-activating-azure-rights-management"></a>手動啟用 Azure 版權管理

如果您已停用 Azure RMS，或如果它因任何原因無法自動啟用，您可以在以下位置手動啟用：

- **Microsoft 365 系統管理中心**：如需相關指示，請參閱 [如何從系統管理中心啟用 Azure 版權管理](/azure/information-protection/activate-office365)。
- **Azure 入口網站**：如需相關指示，請參閱 [如何從 Azure 入口網站中啟用 Azure 版權管理](/azure/information-protection/activate-azure)。

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>設定 Azure 資訊保護租用戶金鑰的管理

這是選擇性的步驟。 允許 Microsoft 管理 Azure 資訊保護的根金鑰是大部分組織的預設設定和建議的最佳做法。 如果是這種情況，您不需要執行任何動作。

有許多原因，例如合規性需求，可能要求您產生及管理您的根金鑰 (也稱為使用自己的金鑰 (BYOK))。 如果是這種情況，建議您完成所需的步驟，之後再設定全新的 OME 功能。 如需詳細資訊，請參閱[規劃及實作您的 Azure 資訊保護租用戶金鑰](/information-protection/plan-design/plan-implement-tenant-key)。

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>在 Exchange Online PowerShell 中驗證 新的 OME 設定

您可以驗證您的 Microsoft 365 租用戶已正確設定以使用 [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell) 中的新 OME 功能。

1. 使用具有 Microsoft 365 租用戶中全域系統管理員權限的帳戶[連線至 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

2. 執行 Get-IRMConfiguration Cmdlet。

     您應該會看到 $True AzureRMSLicensingEnabled 參數，這表示 OME 已設定租用戶中的值。 如果不是，請使用 Set-IRMConfiguration 將 AzureRMSLicensingEnabled 的值設為 $True 以啟用 OME。

3. 使用以下語法來執行 Test-IRMConfiguration Cmdlet：

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```

   **範例**：

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - 提供寄件者電子郵件是選擇性的，但會強制系統執行額外的檢查。 使用 Microsoft 365 租用戶中任何使用者的電子郵件地址。

     您的結果應該類似於：

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - 您的組織名稱將取代 *Contoso*。

   - 預設範本名稱可能與上方顯示的不同。 如需詳細資訊，請參閱[設定及管理 Azure 資訊保護的範本](/azure/information-protection/configure-policy-templates)。

4. 移除 Remove-PSSession Cmdlet 來與版權管理服務中斷連線。

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>後續步驟：定義郵件流程規則，以使用新 OME 功能

如果有先前設定的郵件流程規則可加密您的組織中的電子郵件，則必須更新現有規則，才能使用新的 OME 功能。針對新的部署，您必須建立新的電子郵件流程規則。

> [!IMPORTANT]
> 如果您不更新現有的郵件流程規則，您的使用者會繼續收到使用先前的 HTML 附件格式的加密電子郵件，而非新的無縫 OME 體驗。

郵件流程規則決定在何情況下應該加密電子郵件訊息，以及移除該加密的情況。 當您設定規則的動作時，符合規則條件的任何郵件在傳送時都會經過加密。

如需為 OME 建立郵件流程規則的步驟，請參閱[定義郵件流規則以加密 Office 365 中的電子郵件](define-mail-flow-rules-to-encrypt-email.md)。

若要更新現有規則，以使用新 OME 功能：

1. 在 Microsoft 365 系統管理中心，移至 [系統管理中心] > [Exchange]。
2. 在 Exchange 系統管理中心，移至 [郵件流程] > [規則]。
3. 對於每個規則，在 [執行下列動作] 中：
    - 選取 [修改郵件安全性]。
    - 選取 [套用 Office 365 郵件加密與權限保護]。
    - 從清單中選取 RMS 範本。
    - 選取 [儲存]。
    - 選取 [確定]。
