---
title: 步驟 6 - 作業系統部署與功能更新
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/30/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 深入了解作業系統部署與功能更新的選項。
ms.openlocfilehash: 24b6cf30398031cf2bf4032795013338fec39ffb
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085210"
---
# <a name="step-6-os-deployment-and-feature-updates"></a>步驟 6：作業系統部署與功能更新

![](../media/step-6-os-deployment-and-feature-updates-media/step-6-os-deployment-and-feature-updates-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-9.png" alt="Step 6" height="144" width="144" /></td>
<td><p><strong>步驟 6：作業系統部署與功能更新</strong></p>
<p>工作序列型部署是用於自動化大型、階段部署，以進行裸機安裝、電腦重新整理和電腦取代。升級工作序列也會協助您保持在最新的主要半年更新。Windows Autopilot 是最近的新增功能，讓新電腦收購程序現代化。</p></td>
<td><a href="https://aka.ms/ddev6" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-19.png" alt="Step 6" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>作業系統部署和功能更新是我們建議的部署程序中的第六個步驟，其說明了 Windows 10 作業系統部署、升級與功能更新。 若要查看完整的桌面部署程序，請瀏覽[桌面部署中心](https://aka.ms/HowToShift)。
>

如果您到目前為止已遵循部署程序轉輪，您應至少已部分完成裝置和應用程式整備的步驟、準備好基礎結構、設定並收集應用程式套件、計劃就位可移轉使用者檔案及設定預設設定，以及計劃好保留您現有的安全性控制項，並可能部署新的控制項。

現在我們已達到一個階段，您結合這些片段以盡可能自動化來安裝 Windows 10 和 Office 365 專業增強版，以及所需的驅動程式、應用程式和其他任何所需項目。

最後，作業系統部署成功的最佳評量是符合使用者預期並避免中斷工作。在此步驟中，您會開始測試和部署以在分階段部署中試用使用者。這裡有一個提示，在您擴大部署之前，您必須直接跳到部署程序轉輪的步驟 8 – [使用者通訊和訓練](https://aka.ms/mdd8) (英文) 以確保使用者收到通知，並準備好以他們的方式進行變更，且您可以使用分階段部署透過連續驗證來測量您呈現的速度。

## <a name="windows-imaging-process"></a>Windows 映像程序

大部分的組織使用電腦映像程序來設定和擷取 Windows 的複製，包括幾個已安裝的標準應用程式基本組，或是僅包含應用程式執行階段和更新的較細映像事件。若要這麼做，最好是使用此程序的虛擬機器，以避免任何非預期的驅動程式相關相容性問題並進行自動化目的。

如果進行映像擷取路由，最好盡量自動化以確保最佳品質的映像和重複的程序。對於大部分的部署，也建議擷取之前盡可能不要在 Windows 映像中進行自訂和預先安裝的應用程式。這稱為「細映像」的方法，可節省網路上的整體頻寬，方法是減少映像內的應用程式的數目。從細的基底映像開始，您可以在所需的應用程式、語言和設定上堆疊以動態為使用者量身訂做。

在建置及擷取程序期間，Microsoft Endpoint Configuration Manager (最新分支) 和 Microsoft 部署工具組等工具會使用系統準備工具 – 或 Sysprep – 以及「一般化」命令以在他們擷取 Windows 10 安裝作為映像之前封裝映像。

擷取的映像將會有 Windows 映像 – 或 WIM – 格式如標準 Windows 安裝媒體。一旦您自訂 WIM 檔案之後，可以使用另一個工作順序作為在 Configuration Manager 或 Microsoft 部署工具組中作業系統部署的一部分來執行部署相關的工作，以在您套用 Windows 映像之前和之後套用映像並執行工作。

[建立 Windows 10 參照映像](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/create-a-windows-10-reference-image)

[建立安裝作業系統的工作順序](https://docs.microsoft.com/configmgr/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

### <a name="deployment-types"></a>部署類型

您準備好自訂映像後，安裝或移轉類型將可分為下列類別：

  - 首先，**裸機部署**。這個狀況是用來將映像部署到全新的磁碟機，或是在您不想保留任何資料磁碟的電腦上重新安裝映像

  - 第二，類似於裸機，是**電腦重新整理，** 具有使用者狀態保留在磁碟上\*或在安裝完成後會加以還原的主要差異

  - 最後一個則是**電腦取代**。這正如其名，您會將電腦取代為另一部電腦。在此情況下，通常會從第一部電腦將使用者檔案備份至中央位置，然後將這些檔案還原至第二部電腦。

這三種案例有共通點，它們會使用工作順序來執行，且每次都可套用自訂映像。

[深入了解 Windows 10 部署案例](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)

### <a name="in-place-upgrade-using-task-sequence-automation"></a>使用工作順序自動化就地升級

除了這些部署類型之外，現在還提供新的選項作為 Windows 10 的 Microsoft Endpoint Configuration Manager (最新分支) 工作序列，以及使用工作序列的就地升級。

從舊版 Windows 的就地升級不需要工作順序，但在企業規模中部署時則是建議的方法。就地升級無法讓您使用應用程式套用自訂映像，但您可以使用離線服務更新預設 install.wim。例如，您可以確認它在執行升級之前已套用最新的 Windows 更新。

就地升級會使用 Windows 安裝程式。安裝程式引擎會執行多個小型的預先安裝檢查以尋找已知的相容性問題。它也會保留使用者狀態和應用程式，並只會移除與所安裝 Windows 10 版本不相容的項目。透過此選項，會保留先前安裝的應用程式與使用者狀態。就地升級也可讓您復原到先前安裝的作業系統 (若疑難排解需要)。

[使用 setup.exe 的 Windows 10 升級前驗證](https://blogs.technet.microsoft.com/mniehaus/2015/08/23/windows-10-pre-upgrade-validation-using-setup-exe/)

![](../media/step-6-os-deployment-and-feature-updates-media/step-6-os-deployment-and-feature-updates-media-3.png)

就地升級案例可用來從舊版 Windows 移轉到 Windows 10，以及從舊版 Windows 10 進行升級。在 Windows 安裝程式完成升級之後，您的工作順序可以繼續執行及升級應用程式 (如 Office)、取代驅動程式以及套用個人化設定。同樣地，您可以使用升級工作順序在執行升級之前執行預先安裝工作或檢查。

[使用 Configuration Manager 執行就地升級至 Windows 10](https://docs.microsoft.com/windows/deployment/upgrade/upgrade-to-windows-10-with-system-center-configuraton-manager)

[建立工作順序以在 Configuration Manager 中升級作業系統](https://docs.microsoft.com/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

### <a name="phased-deployment"></a>階段式部署

當您計劃部署時，您將電腦目標設為裸機、重新整理、取代和升級路徑。在此情況下，建議的方法是使用類似電腦上集合的分階段部署。如此一來，您可以在增加部署規模之前驗證相容性、傳遞和自動化、使用者接受、網路頻寬耗用以及其他因素。

![](../media/step-6-os-deployment-and-feature-updates-media/step-6-os-deployment-and-feature-updates-media-4.png)

### <a name="recommended-tools-microsoft-endpoint-configuration-manager-current-branch-and-the-microsoft-deployment-toolkit"></a>建議的工具：Microsoft Endpoint Configuration Manager (最新分支) 和 Microsoft 部署工具組

無論您選擇的部署類型，您需要確認可預測性和重複性盡可能為自動化。Microsoft 提供兩個解決方案可使用自動化的工作順序自動化作業系統部署：

  - **[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/core/understand/introduction)** (ConfigMgr) (英文) 提供內建作業系統部署功能，可加強軟體發佈與軟體更新管理的功能。ConfigMgr 已廣泛用於各種規模的組織，並支援所有四個 Windows 部署類型。或者，您也可以將 ConfigMgr 與 Microsoft Intune 整合以新增其他功能來部署和裝置管理。

  - 其他常用的部署選項是免費的 **[Microsoft 部署工具組](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/get-started-with-the-microsoft-deployment-toolkit)** (MDT) (英文) 通常是由小型及中型規模的組織用來進行作業系統部署。這幾乎不需要基礎結構。MDT 與 Windows 部署服務 (WDS) 整合以進行網路開機。它支援所有四種部署類型以及應用程式安裝、驅動程式和設定。當然，MDT 甚至可與 Configuration Manager 整合。

![](../media/step-6-os-deployment-and-feature-updates-media/step-6-os-deployment-and-feature-updates-media-5.png)

### <a name="windows-autopilot"></a>Windows Autopilot

Windows 10 的新選項使用Windows Autopilot 將新電腦設定配置為硬體更新周期的一部分。 您可以在這裡可以與支援的硬體供應商合作，自訂預設的 Windows 安裝體驗 - 例如，透過減少提供給使用者的選項，如授權合約或診斷資料設定。

接著，當使用者在安裝程式期間使用其 Azure AD 認證登入電腦時，裝置會註冊為 Microsoft Intune，也可以接管部署程序及套用應用程式、軟體更新設定與合規性原則。Windows Autopilot 也可以選擇性地防止使用者在佈建完成之前存取第一個工作階段。

[Windows Autopilot 概觀](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)

[Windows Autopilot 必要條件](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot#prerequisites)

## <a name="windows-update-for-business-for-feature-updates"></a>商務用 Windows 更新功能更新

商務用 Windows Update是一項免費服務，透過將裝置直接連線到 Windows Update 服務，IT 專業人員可以使 Windows 10 裝置始終保持最新狀態。 可以透過群組原則或 MDM 解決方案 (如 Microsoft Intune) 來設定商務用 Windows Update，並可讓 IT 專業人員建立[部署通道](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)以驗證新組建。 這項工具已整合至現有管理工具中，如 Windows Server Update Services (WSUS)、Microsoft Endpoint Configuration Manager (最新分支) 和 Microsoft Intune。 此外，商務用 Windows Update支援點對點傳送，以協助優化頻寬效率並減少網路擁塞。

如需商務用 Windows Update 的詳細資訊，請參閱以下文件：

- [使用商務用 Windows Update 部署更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [設定商務用 Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb)
- [整合商務用 Windows Update 與現有的管理工具](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)
- [使用群組原則來設定商務用 Windows Update](https://docs.microsoft.com/windows/deployment/update/waas-wufb-group-policy)
- [使用 Microsoft Intune 來設定商務用 Windows Update](https://docs.microsoft.com/intune/windows-update-for-business-configure)

## <a name="next-step"></a>下一步 

## <a name="step-7-windows-and-office-servicinghttpsakamsmdd7"></a>[步驟 7：Windows 和 Office 服務](https://aka.ms/mdd7)

## <a name="previous-step"></a>上一步

## <a name="step-5-security-and-compliance-considerationshttpsakamsmdd5"></a>[步驟 5：安全性與相容性考量事項](https://aka.ms/mdd5)
