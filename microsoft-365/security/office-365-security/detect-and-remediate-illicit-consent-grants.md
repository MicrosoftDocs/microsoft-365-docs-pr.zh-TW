---
title: 偵測並修正違法的同意授與
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: 瞭解如何辨識和修正非法同意授與 Microsoft Office 365 的攻擊。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a50ce58d91d2ff7b2e31e57830289c870364d9b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288284"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>偵測並修正違法的同意授與

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用於**
- [適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

**摘要** 了解如何識別並修正在 Office 365 中的非法同意授權。

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>什麼是 Office 365 中的非法同意授權攻擊？

在非法同意授權攻擊中，攻擊者會建立已註冊 Azure 的應用程式，要求存取連絡人資訊、電子郵件或文件等資料。 然後，攻擊者誘騙使用者授權該應用程式同意透過網路釣魚攻擊，或透過插入非法程式碼到信任的網站，來存取其資料。 在非法應用程式獲得授權之後，就擁有資料的帳戶層級存取權，而不需要組織帳戶。 一般補救步驟，例如重設遭入侵帳戶的密碼或要求帳戶的多重要素驗證 (MFA)，對這類型攻擊是無效的，因為這些是第三方應用程式，而且在組織外部。

這些攻擊採用一種互動模型，這種模型會假正在呼叫資訊的實體是自動化，而不是人。

> [!IMPORTANT]
> 您是否懷疑遇到違法的同意問題-從應用程式授與的許可權？ Microsoft Cloud App Security (MCAS) 具有偵測、調查和修正 OAuth 應用程式的工具。 此 MCAS 文章包含的教學課程，說明如何 [調查 OAuth 應用程式的風險](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth)。 您也可以設定 [OAuth 的應用程式原則](https://docs.microsoft.com/cloud-app-security/app-permission-policy) ，以調查應用程式要求的許可權，這些許可權是使用者授權這些應用程式，並廣泛核准或禁止這些許可權要求。

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Office 365 中的非法同意授權攻擊的外觀如何？

您必須搜尋「 **審計記錄** 檔」，以尋找此攻擊的簽署，也稱為折衷 (IOC) 。 如果組織擁有許多 Azure 註冊應用程式和大量使用者，最佳做法就是每週檢閱您的組織同意授權。

### <a name="steps-for-finding-signs-of-this-attack"></a>尋找此攻擊徵象的步驟

1. 開啟 **安全性 & 規範中心** ，網址為 <https://protection.office.com> 。

2. 流覽至 [ **搜尋** ]，然後選取 [ **審核記錄搜尋**]。

3. 搜尋 (所有活動和所有使用者) 並輸入開始日期和結束日期（如有需要），然後按一下 [ **搜尋**]。

4. 按一下 [ **篩選結果** ]，並在 [ **活動** ] 欄位中輸入應用程式同意。

5. 按一下結果以查看活動的詳細資料。 按一下 [ **詳細資訊** ] 以取得活動的詳細資料。 請檢查 IsAdminContent 是否設定為 True。

> [!NOTE]
>
> 在發生事件後，可在搜尋結果中顯示對應的審計記錄專案，最多可花30分鐘到24小時的時間。
>
> 在審核記錄中保留及可搜尋的審計記錄的時間長度，取決於您的 Microsoft 365 訂閱，特別是指派給特定使用者的授權類型。 如需詳細資訊，請參閱[稽核記錄](../../compliance/search-the-audit-log-in-security-and-compliance.md)。
>
> 如果這個值為 true，表示擁有全域系統管理員存取權的人員可能已獲得資料的廣泛存取權。 如果這是未預期的，請採取步驟以[確認攻擊](#how-to-confirm-an-attack)。

## <a name="how-to-confirm-an-attack"></a>如何確認攻擊

如果您有上面所列的一或多個 IOC 執行個體，則必須進一步調查，以明確確認發生了攻擊。 您可以使用下列三種方法中的任何一種來確認攻擊：

- 使用 Azure Active Directory 入口網站來清查應用程式及其權限。 此方法很徹底，但是一次只能檢查一個使用者，如果要檢查的使用者很多，這會非常耗時。

- 使用 PowerShell 來清查應用程式及其權限。 這是最快也最徹底的方法，而且負擔最小。

- 讓您的使用者個別檢查其應用程式和授權，並將結果報告給系統管理員以進行修正。

## <a name="inventory-apps-with-access-in-your-organization"></a>使用您組織中的存取權來清查應用程式。

您可以使用 Azure Active Directory 入口網站或 PowerShell 來為您使用者執行此動作，或請您的使用者個別列舉其應用程式存取權。

### <a name="steps-for-using-the-azure-active-directory-portal"></a>使用 Azure Active Directory 入口網站的步驟

您可以使用 [Azure Active Directory 入口網站](https://portal.azure.com/)來查閱任何個人使用者已獲授權的應用程式。

1. 使用系統管理權限登入 Azure 入口網站。

2. 選取 [Azure Active Directory] 刀鋒視窗。

3. 選取 [使用者]。

4. 選取您要檢閱的使用者。

5. 選取 [應用程式]。

這會顯示指派給使用者的應用程式，以及應用程式的許可權。

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>請您的使用者列舉其應用程式存取權的步驟

請您的使用者前往 https://myapps.microsoft.com，並在那裡查看自己的應用程式存取權。 他們應該能夠查看具有存取權的所有應用程式、查看相關的詳細資料 (包括存取範圍)，並能夠撤銷可疑或非法應用程式的權限。

### <a name="steps-for-doing-this-with-powershell"></a>使用 PowerShell 執行此動作的步驟

驗證非法同意授權攻擊的最簡單方法是執行 [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)，它會將您租用戶中所有使用者的所有 OAuth 同意授權與 OAuth 應用程式都傾印到一個 .csv 檔案中。

#### <a name="pre-requisites"></a>先決條件

- 已安裝 Azure AD PowerShell 程式庫。

- 將執行指令碼的租用戶的全域系統管理員權限。

- 將執行指令碼的電腦上的本機系統管理員。

> [!IMPORTANT]
> ***強烈建議*** 您在您的管理帳戶上需要多重要素驗證。 此指令碼支援 MFA 驗證。

1. 使用本機系統管理員權限登入您將執行指令碼的電腦。

2. 將 [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) 腳本從 GitHub 下載或複製到您要執行腳本的資料夾。 此資料夾與寫入輸出「permissions.csv」檔案的資料夾是同一個。

3. 以系統管理員身分開啟 PowerShell 執行個體，然後開啟您要儲存指令碼的資料夾。

4. 使用 [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) Cmdlet 連線至您的目錄。

5. 執行此 PowerShell 命令：

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

指令碼會產生一個名為「Permissions.csv」的檔案。 依照下列步驟尋找非法應用程式權限授權：

1. 在 [ConsentType] 欄 (欄 G) 中，搜尋值「AllPrinciples」。 AllPrincipals 許可權可讓用戶端應用程式存取租使用者的所有人內容。 原生 Microsoft 365 應用程式需要此許可權才能正確運作。 必須仔細檢閱具有此權限的每一個非 Microsoft 應用程式。

2. 在 [Permission] 欄 (欄 F) 中，檢閱每個委派的應用程式對內容所擁有的權限。 尋找「Read」和「Write」權限或「*.All」權限，並仔細加以檢閱，因為它們可能不適當。

3. 檢閱已獲同意授權的特定使用者。 如果高設定檔或高度影響使用者擁有不適當的同意，您應進一步調查。

4. 在 [ClientDisplayName] 欄 (欄 C) 中，尋找看起來可疑的應用程式。 應仔細檢查名稱拼錯、名稱超級簡單名稱或名稱像駭客的應用程式。

## <a name="determine-the-scope-of-the-attack"></a>判斷攻擊的範圍

當您完成清查應用程式存取之後，請複查 **審核記錄** 以判斷破壞的完整範圍。 搜尋受影響的使用者、非法應用程式有權存取您組織的時間範圍，以及應用程式擁有的權限。 您可以在 [Microsoft 365 安全性與合規性中心][](../../compliance/search-the-audit-log-in-security-and-compliance.md) 中搜尋 **稽核記錄**。

> [!IMPORTANT]
> 您必須在攻擊之前啟用 [信箱稽核][](../../compliance/enable-mailbox-auditing.md) 和 [系統管理員與使用者的活動稽核][](../../compliance/turn-audit-log-search-on-or-off.md)，才能獲得此訊息。

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>如何阻止及修復非法同意授權攻擊

當您識別出有非法權限的應用程式之後，有多種方式可移除該存取權。

- 您可以在 Azure Active Directory 入口網站中撤銷應用程式的權限，方法是：

  - 在 [Azure Active Directory 使用者] 刀鋒視窗中瀏覽至受影響的使用者。

  - 選取 [應用程式]。

  - 選取非法應用程式。

  - 按一下向下切入中的 [移除]。

- 您可以依照[移除-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant) 中的步驟，使用 PowerShell 撤銷 QAuth 同意授權。

- 您可以依照[移除-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment) 中的步驟，使用 PowerShell 撤銷服務應用程式角色指派。

- 您也可以完全停用受影響帳戶的登入，這將會進一步停用該帳戶中應用程式對資料的存取權。 當然，這對使用者的生產力並不理想，但是如果您正努力快速限制影響，這會是可行的短期補救。

- 您可以關閉租用戶的整合式應用程式。 這是一項重大步驟，會在整個租用戶範圍中停用使用者授權同意的能力。 這可防止您的使用者不小心授權存取惡意應用程式。 我們不建議您這麼做，因為這會嚴重影響使用者使用使用協力廠商應用程式的生產力。 若要這麼做，可以依照[開啟或關閉整合式應用程式](../../admin/misc/user-consent.md)中的步驟進行。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>像網路安全專業人員一般保護 Microsoft 365

您的 Microsoft 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。 使用 [Microsoft 365 安全性藍圖 - 前 30 天、前 90 天前和之後的最高優先順序](security-roadmap.md)來實作 Microsoft 建議用來保護您的 Microsoft 365 租用戶的最佳做法。

- 要在前 30 天內完成的工作。 這些工作會有立即的影響，而且對您的使用者影響較低。

- 要在 90 天內完成的工作。 這些工作需要多一些時間來計劃及實作，但是可以大幅改善您的安全性狀態。

- 90 天之後。 這些增強功能會在您的前 90 天工作內建置。

## <a name="see-also"></a>另請參閱：

- [我的應用程式清單中有未預期的應用程式](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)，在系統管理員知道有未預期應用程式具有資料存取權之後，此文章可引導系統管理員完成可能需要採取的不同動作。

- [整合應用程式與 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) 是同意與權限的高階概觀。

- [開發我的應用程式時發生問題](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)提供各種同意相關文章的連結。

- [Azure Active Directory (Azure AD) 中的應用程式按服務主體物件](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)提供應用程式模型核心的應用程式和服務主體物件的概觀。

- [管理應用程式的存取權](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)概述系統管理員用來管理使用者對應用程式的存取權的功能。
