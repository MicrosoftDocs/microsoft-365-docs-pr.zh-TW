---
title: 將 IRM 設定為使用內部部署 AD RMS 伺服器
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: 瞭解如何設定資訊版權管理 (IRM) Exchange Online 使用 Active Directory Rights management Service (AD RMS) server。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c42d793639a9efaf94e3222a172ea192d1e03d3
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227232"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>將 IRM 設定為使用內部部署 AD RMS 伺服器

若要搭配內部部署使用，Exchange Online 中的資訊版權管理 (IRM) 使用 Active Directory Rights Management Services (AD RMS) ，Windows Server 2008 和更新版本中的資訊保護技術。 系統會藉由將 AD RMS 權限原則範本套用至電子郵件，將 IRM 保護套用至電子郵件。 許可權會附加至郵件本身，使保護在線上及離線，以及組織防火牆內部和外部進行。

本主題示範如何設定 IRM 以使用 AD RMS 伺服器。 如需對 Azure Active Directory 和 Azure 版權管理使用 Office 365 郵件加密的新功能的詳細資訊，請參閱[Office 365 郵件加密常見問題](./ome-faq.yml)。

若要深入了解 Exchange Online 中的 IRM，請參閱 [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 完成此工作的預估時間：30 分鐘

- 您必須已獲指派權限，才能執行此程序或這些程序。 若要查看您需要的許可權，請參閱 [郵件原則及符合性許可權](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions) 主題中的「資訊版權管理」專案。

- AD RMS 伺服器必須執行 Windows Server 2008 或更新版本。 如需如何部署 AD RMS 的詳細資訊，請參閱 [安裝 AD rms](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11))叢集。

- 如需如何安裝及設定 Windows PowerShell 及連線到服務的詳細資料，請參閱[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 有問題嗎？在 Exchange 論壇中尋求協助。 論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。

## <a name="how-do-you-do-this"></a>該怎麼做？
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>步驟 1：使用 AD RMS 主控台從 AD RMS 伺服器匯出信任的發行網域 (TPD)

第一個步驟是將信任的發行網域 (TPD) 從內部部署 AD RMS 伺服器匯出至 XML 檔案。TPD 含有以下使用 RMS 功能所需的設定：

- 用於簽署憑證和授權及予以加密的伺服器授權人憑證

- 用於授權和發行的 URL

- 以 TPD 特定的 SLC 建立的 AD RMS 權限原則範本

當您匯入 TPD 時，它會儲存並保護 Exchange Online。

1. 開啟 Active Directory Rights Management Services 主控台，然後展開 AD RMS 叢集。

2. 在主控台樹狀目錄中，展開 **[信任原則]**，然後按一下 **[信任的發行網域]**。

3. 在結果窗格中，選取您想要匯出之網域的憑證。

4. 在 **[動作]** 窗格中按一下 **[匯出信任的發行網域]**。

5. 在 **[發行網域檔案]** 方塊中按一下 **[另存新檔]**，將檔案儲存至本機電腦上的特定位置。 輸入檔案名，確定指定副檔名，然後按一下 [  `.xml` **儲存**]。

6. 在 **[密碼]** 和 **[確認密碼]** 方塊中，輸入將用來加密信任發行網域檔案的強式密碼。當您將 TPD 匯入雲端架構電子郵件組織時，就必須指定這個密碼。

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>步驟2：使用 Exchange 管理命令介面將 TPD 匯入 Exchange Online

將 TPD 匯出至 XML 檔案之後，您就必須將它匯入 Exchange Online。匯入 TPD 時，也會一併匯入組織的 AD RMS 範本。匯入第一個 TPD 時，它會成為雲端架構組織的預設 TPD。如果您匯入了其他 TPD，可以使用 **Default** 參數，讓它成為提供給使用者的預設 TPD。

若要匯入 TPD，請在 Windows PowerShell 中執行下列命令：

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

您可以在 Active Directory Rights Management Services 主控台中取得 _ExtranetLicensingUrl_ 和 _IntranetLicensingUrl_ 參數的值。 請在主控台樹狀目錄中選取 AD RMS 叢集。 授權 URL 就會顯示在結果窗格中。 當內容必須解密以及 Exchange Online 必須判斷要使用的 TPD 時，電子郵件用戶端就會使用這些 URL。

當您執行此命令時，系統會提示您輸入密碼。 請輸入您從 AD RMS 伺服器匯出 TPD 時所指定的密碼。

例如，下列命令會使用您從 AD RMS 伺服器匯出並儲存至系統管理員帳戶桌面的 XML 檔案來匯入名為 Exported TPD 的 TPD。Name 參數是用來指定 TPD 的名稱。

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

如需詳細的語法及參數資訊，請參閱 [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain)。

#### <a name="how-do-you-know-this-step-worked"></a>如何才能了解此步驟是否正常運作？

若要確認您是否已成功匯入 TPD，請執行 **Get-RMSTrustedPublishingDomain** Cmdlet，以在 Exchange Online 組織中取得 tpd。 如需詳細資料，請參閱 [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain) 中的範例。

### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>步驟3：使用 Exchange 管理命令介面來發佈 AD RMS 許可權原則範本

匯入 TPD 之後，您必須確定 AD RMS 權限原則範本已發佈。  (以前稱為 Outlook Web App) 使用者，可將範本套用至電子郵件的 Outlook 網頁版，可看到分散式範本。

若要傳回預設 TPD 包含的所有範本清單，請執行下列命令：

```powershell
Get-RMSTemplate -Type All | fl
```

如果  _Type_ 參數的值為  `Archived` ，使用者將看不到該範本。 只有預設 TPD 中的分散式範本可用於 Outlook 網頁版。

若要發佈範本，請執行下列命令：

```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

例如，下列命令會匯入 Company Confidential 範本。

```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

如需詳細的語法及參數資訊，請參閱 [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) 與 [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate)。

**不要轉寄範本**

當您將預設 TPD 從內部部署組織匯入 Exchange Online 時，會匯入名為 **[不要轉寄]** 的 AD RMS 權限原則範本。根據預設，當您匯入預設 TPD 時，系統會發佈此範本。但是，您無法使用 **Set-RMSTemplate** 指令程式來修改 **[不要轉寄]** 範本。

當 **[不要轉寄]** 範本套用至郵件時，只有郵件中所列的收件者才能讀取郵件。此外，收件者無法進行下列作業：

- 將郵件轉寄給其他人員。

- 複製郵件的內容。

- 列印郵件。

> [!IMPORTANT]
> **[不要轉寄]** 範本無法防止使用者透過協力廠商螢幕擷取程式複製郵件中的資訊，也無法防止使用者手動抄錄資訊。

您可以在內部部署組織中的 AD RMS 伺服器上建立其他 AD RMS 權限原則範本，以符合您的 IRM 保護需求。如果您建立了其他 AD RMS 權限原則範本，就必須再次從內部部署 AD RMS 伺服器匯出 TPD，然後在雲端架構電子郵件組織中重新整理 TPD。

#### <a name="how-do-you-know-this-step-worked"></a>如何才能了解此步驟是否正常運作？

若要確認您是否已成功發佈和 AD RMS 許可權原則範本，請執行 **Get-RMSTemplate** Cmdlet 以檢查範本的屬性。 如需詳細資料，請參閱 [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) 中的範例。

### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>步驟4：使用 Exchange 管理命令介面來啟用 IRM

匯入 TPD 並發佈 AD RMS 權限原則範本之後，請執行以下命令以針對雲端架構電子郵件組織啟用 IRM。

```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

如需詳細的語法及參數資訊，請參閱 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)。

#### <a name="how-do-you-know-this-step-worked"></a>如何才能了解此步驟是否正常運作？

若要確認您是否已成功啟用 IRM，請執行[Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) Cmdlet 以檢查 Exchange Online 組織中的 IRM 設定。

## <a name="how-do-you-know-this-task-worked"></a>如何才能了解此工作是否正常運作？
<a name="sectionSection2"> </a>

若要確認您是否已成功匯入 TPD 並啟用 IRM，請執行下列動作：

- 使用 **Test-IRMConfiguration** 指令程式來測試 IRM 功能。 如需詳細資訊，請參閱 [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration)中的「範例1」。

- 從 [擴充] 功能表中選取 [**設定許可權**] 選項，以在 Outlook 網頁版和 IRM (中撰寫新郵件， ![) [其他選項] 圖示 ](../media/ITPro-EAC-MoreOptionsIcon.gif) 。
