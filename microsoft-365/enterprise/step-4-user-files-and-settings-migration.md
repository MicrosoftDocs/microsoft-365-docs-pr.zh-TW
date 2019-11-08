---
title: 步驟 4 - 使用者檔案和設定移轉
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何移轉使用者檔案和設定。
ms.openlocfilehash: 8b9bde4eb1ddf0951a2ab27795dadef9965f6a1c
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031488"
---
# <a name="step-4-user-files-and-settings-migration"></a>步驟 4：使用者檔案和設定移轉

將使用者的檔案和設定移至其新的或重新整理的電腦是很重要的程序，因此絕對不能失敗。 您可以手動遷移每一部電腦，也可以選擇下列其中一個方法來將此程序自動化。 無論選擇何種移轉方法，都必須解決三個主要的考量，分別是傳輸使用者的檔案、其設定，以及管理 Windows 10 的「開始」和工作列版面配置。

![](media/step-4-user-files-and-settings-migration-media/step-4-user-files-and-settings-migration-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-7.png" alt="Step 4" height="135" width="135" /></td>
<td><p><strong>步驟 4：使用者檔案和設定</strong> (英文)</p>
<p>重新整理或取代電腦時，將使用者狀態備份與還原自動化以節省時間。雲端檔案同步的新選項可讓您強制執行，將每個使用者的桌面、文件和圖片資料夾同步處理至 OneDrive，以從新的 Windows 安裝順利存取檔案。</p></td>
<td><a href="https://aka.ms/ddev4" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-17.png" alt="Step 4" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>儘管您可以繼續使用過去使用過的移轉程序，但在移轉至 Office 365 專業增強版時，建議您使用 OneDrive「已知資料夾移動」(如下所示)。 若要查看完整的桌面部署程序，請瀏覽[桌面部署中心](https://aka.ms/HowToShift)。
>

大型部署中最棘手且通常最需手動執行的其中一項工作就是移轉使用者的檔案和設定。本文將討論您可以使用的選項，以便將使用者移轉至新的、重新整理及影像重新處理的電腦。

## <a name="manual-migration"></a>手動移轉

若談到移至新電腦或新版本 Windows 時決定要保留哪些項目，部分使用者可能會想要保留所有內容，其他人則可能想利用這個機會清理磁碟機。因此，某些 IT 部門選擇手動處理使用者的檔案移轉，有時會讓支援小組造訪使用者，有時則會設立支援中心讓使用者將電腦帶給支援小組。兩種方法使用者都可以決定要傳輸及要捨棄的內容。

這對您的組織是否可行取決於您規劃的移轉規模。很明顯地，對於直接與使用者合作、了解使用者需求、將檔案複製到其新的或剛更新的電腦，這會受限於時間和實際情況。

如果您選擇手動移轉，可能需要評估是否能在 2020 年 1 月前完成工作，屆時 Windows 7 的支援將會終止。如果不確定，請使用下列其中一個自動化選項，或是尋求其他人的協助。

## <a name="automated-migration-using-usmt"></a>使用 USMT 自動化移轉 

對於大規模部署，您可以使用工作序列式部署自動化工具來自動化大部分程序，例如 System Center Configuration Manager 或 Microsoft Deployment Toolkit (MDT)。這兩種解決方案都運用使用者狀態移轉工具 (USMT) 作為端對端部署程序一部分。USMT 屬於 [Windows 評定及部署套件 (Windows ADK)](https://docs.microsoft.com/windows-hardware/get-started/adk-install)

USMT 會擷取使用者帳戶、使用者檔案、作業系統設定和應用程式設定，然後將這些移轉至新的 Windows 安裝中。同時也能讓 IT 系統管理員準確控制移轉內容，另外也可以選擇排除不想要的檔案類型，如音訊及視訊檔案，或可執行檔。

在移轉程序期間，您必須擁有足夠的伺服器可用儲存體容量，以做為暫時的移轉存放區。此處 USMT 提供兩個重要的功能。第一，它可以估計您在每個電腦上所需的儲存空間。其次，它可讓移轉存放區進行加密，降低資料儲存在檔案伺服器上時受到威脅的風險。

您在其中執行電腦重新整理且未格式化的主要 Windows 磁碟分割，您也可以使用 USMT 來使用硬式連結移轉存放區。此程序會在電腦上保留使用者狀態，而舊的作業系統和應用程式會移除並重新整理。還原程序來自相同的本機磁碟分割，這個選項大幅改善效能，並減少網路流量。

[使用者狀態移轉工具 (USMT) 概觀](https://docs.microsoft.com/windows/deployment/usmt/usmt-overview)

## <a name="onedrive-known-folder-move"></a>OneDrive 已知資料夾移動

如果使用者正在使用 OneDrive 或您將 OneDrive 新增為此部署的一部分，則您有新的可用選項。使用雲端同步處理使用者檔案，OneDrive 的「已知資料夾移動」功能提供的彈性層級，是本機網路式檔案移轉選項所無法提供的。如果在移轉之前啟用，可在新的或重新整理的電腦上提供安全存取，且不需要在您自己的伺服器上建立暫時的移轉存放區。它也可能會對使用者呈現完全透明。

[將 Windows 已知資料夾重新導向並移動至 OneDrive](https://docs.microsoft.com/onedrive/redirect-known-folders) (英文)

如果您已使用 OneDrive，您就會知道，使用者可以選取想要同步處理 OneDrive 或 SharePoint 至裝置的資料夾或位置，但實際上會造成使用者設定負擔。使用「已知資料夾移動」，可針對使用者設定檔中的文件、電腦和圖片資料夾，並在 OneDrive 上進行保護。使用者可以在這種情況下自行執行，或者您可以[使用群組原則設定強制執行](https://docs.microsoft.com/onedrive/use-group-policy?redirectSourcePath=%252fen-us%252farticle%252fUse-Group-Policy-to-control-OneDrive-sync-client-settings-0ecb2cf5-8882-42b3-a6e9-be6bda30899c)。

使用「已知資料夾移動」，使用者不變更工作流程，所有項目看起來在之前、期間及之後都相同，使用 OneDrive 的同步處理已完成。透過群組原則，您甚至可以選擇是否要通知使用者其文件、圖片和電腦在 OneDrive 中受保護。如果您選擇不要，會在背景中以無訊息方式進行。使用者只會在傳遞新電腦或電腦重新整理時發現。當使用者登入 OneDrive 帳戶時，這些檔案將可再次使用，且會還原到其新的電腦。當然，使用 OneDrive 表示可以隨時從手機和其他裝置安全存取檔案。

OneDrive 的驗證由 Azure Active Directory 提供，因此對於增加安全性，您可以輕鬆啟用多重要素驗證，並設定原則以控制 OneDrive 用來限制網路活動的上傳和下載頻寬。

您不需要同時移轉所有使用。您可能會想要階段推行群組原則設定，或[限制檔案同步處理至已加入網域的電腦](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenantSyncClientRestriction?view=sharepoint-ps)。

## <a name="start-menu-and-task-bar-customization"></a>自訂開始功能表和工作列

OneDrive 設計用來同步處理及保護檔案和資料夾；它不會同步處理應用程式或 Windows 設定。過去若要這麼做您可能會使用複製設定檔的方法來設定使用者的開始功能表和工具列設定的標準版面配置。在 Windows 10 專業版、企業版和教育版中，您可以使用群組原則、MDM、PowerShell 或佈建套件部署[自訂開始和工作列版面配置](https://docs.microsoft.com/windows/configuration/windows-10-start-layout-options-and-policies)。不需重新進行影像處理，只要覆寫包含版面配置的 .xml 檔案即可更新版面配置。

若要建立新的版面配置只需設定範例系統，並使用 PowerShell [Export-StartLayout](https://docs.microsoft.com/powershell/module/startlayout/export-startlayout?view=win10-ps) Cmdlet 來產生 XML 檔案，然後將此檔案放在網路共用，或在本機上快取為您部署順序的一部分；這只要在使用者登入時為可用的唯讀檔案。然後您可以使用原則或 [Import-StartLayout](https://docs.microsoft.com/powershell/module/startlayout/import-startlayout?view=win10-ps) Cmdlet 來參考此檔案。

## <a name="removing-unwanted-in-box-apps"></a>移除不想要的內建應用程式

Windows 10 包含許多實用的內建應用程式作為標準安裝，但您可能會想要從受管理的電腦移除部分，甚至設定安裝以防止傳回應用程式，例如 XBOX 或 Zune Music。您可以使用 [PowerShell Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) 命令來擷取這些應用程式的清單，並使用 [Remove-AppxPackage](https://technet.microsoft.com/library/hh856038.aspx) 命令移除不想要的部分。或者，您可以在部署之前離線裝載 Windows Image (.img) 檔案，並使用[部署映像服務與管理 (DISM)](https://docs.microsoft.com/windows-hardware/manufacture/desktop/what-is-dism) 命令列工具與 [Remove-AppxProvisionedPackage](https://docs.microsoft.com/powershell/module/dism/remove-appxprovisionedpackage?view=win10-ps) 命令擷取不想要的套件。

## <a name="next-step"></a>下一步

## <a name="step-5-security-and-compliance-considerationshttpsakamsmdd5"></a>[步驟 5：安全性與相容性考量事項](https://aka.ms/mdd5)

## <a name="previous-step"></a>上一步

## <a name="step-3-office-and-lob-app-deliveryhttpsakamsmdd3"></a>[步驟 3：Office 和 LOB 應用程式傳遞](https://aka.ms/mdd3)