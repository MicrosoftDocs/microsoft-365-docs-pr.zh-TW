---
title: 步驟 3 - Office 和 LOB 應用程式傳遞
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解如何傳遞 Office 和 LOB 應用程式。
ms.openlocfilehash: 2bae1f159f7c8ae947d4afddfe1e608cdd8bc85b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866773"
---
# <a name="step-3-office-and-lob-app-delivery"></a>步驟 3：Office 和 LOB 應用程式傳遞

現在您已準備好提供 Office 和企業營運應用程式。有許多方法可以使用，包括一些有趣的新選項。請花一些時間來了解，並選出符合目前需求的最佳方法。

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><strong>步驟 3：Office 和 LOB 應用程式傳遞</strong></p>
<p>請確定您的應用程式已封裝並且準備好進行自動化安裝。了解隨選即用封裝與 Office 365 專業增強版如何給予您設定、傳遞及將 Office 應用程式保持在最新狀態的新選項。</p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>Office 和 LOB 應用程式傳遞是我們所建議部署程序轉輪中的第三個步驟，涵蓋安裝及管理 Office 及 LOB 的多個選項。若要成功進行部署，請勿略過前兩個步驟。若要查看完整的桌面部署程序，請瀏覽[現代化電腦的部署中心](https://aka.ms/HowToShift) (英文)。
>

某些應用程式僅適用於 32 位元或 64 位元編譯版本其中一個，而其他包括 Office 365 專業增強版則同時是 32 位元和 64 位元原生編譯程式碼，而您要做的其中一項最大決策就是決定要部署哪個版本。若要利用新裝置上其他運算能力及 RAM，建議您使用 64 位元版本，但在開始前，您必須先找出可能會產生的任何增益集或檔案相關的相容性問題。在繼續之前，可能需要您再次瀏覽步驟 1 裝置和應用程式整備。

如果沒有任何問題，建議您將所有應用程式部署為 64 位元版本，包括 Microsoft Office。64 位元原生編譯應用程式可提供最佳效能，是承受未來考驗的最佳選擇。

在 Windows 上安裝應用程式有許多方法與模型，讓我們來看看您的傳遞選項。

[Windows 10 應用程式管理](https://docs.microsoft.com/zh-TW/windows/application-management/)

## <a name="msi-based-deployments"></a>MSI 型部署

針對企業營運應用程式，您可能使用 MSI 型套件或可執行檔，並將應用程式安裝為 OS 部署工作順序的一部分。Windows 10 仍會繼續使用這些套件

System Center Configuration Manager 和 Microsoft Intune 等軟體部署工具也經過最佳化以提供 MSI 封裝的應用程式。在 Windows 10 上驗證應用程式之後，即可將 System Center Configuration Manager (最新分支) 用於應用程式傳遞。如果使用 Microsoft Intune 的公司入口網站，您可以延伸選擇，將獲得 IT 批准組織可用的應用程式包含最新的應用程式，且使用者可自行選取所需項目。

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a>電腦影像

應用程式傳遞的另一個常見方法是電腦影像。在此情況下，應用程式安裝會透過工作順序或在範本電腦上以手動方式進行，然後會擷取系統映像並預先安裝必要的應用程式。以影像方式建立及擷取可以在佈建新電腦時節省時間，但請記得，映像內的作業系統和應用程式會快速過期。在 Windows 10 和 Office 365 專業增強版中的累計更新模型可協助解決這個問題，但無法完全消除。這也是為什麼我們建議您使用精簡映像的方式，您的應用程式會在部署時間從映像外部進行安裝。

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

如果您想在映像中包含 Office 365 專業增強版，請記住，這會使用使用者型啟用，而無法由系統管理員預先啟用。使用 Office 部署工具在影像裝置上預先安裝 Office，並跳過使用者登入。使用者可以登入，受指派啟用，並充分利用其他運用首次登入的功能。

[建立安裝作業系統的工作順序](https://docs.microsoft.com/zh-TW/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system) (英文)

## <a name="click-to-run"></a>隨選即用 

Office 365 專業增強版使用隨選即用來安裝，隨選即用取代了 Windows 即將推出的 Office 2019 每個版本中的 MSI 型封裝。它會帶來許多好處，包括更快速的安裝、更快且更有效率的更新以及更簡潔的解除安裝

透過隨選即用提供的程式會在您電腦上的虛擬應用程式環境中執行，因此能與其他應用程式共存，而不發生衝突；這些程式也會如 MSI 型套件佔去約一半的磁碟空間。因為隨選即用支援程式串流，透過串流最常使用的功能，使用者就可以在幾分鐘內開始使用 Office 應用程式，而不需先等候 Office 完整安裝。這不只對於初始部署很重要，這表示更新可以順暢地在背景中串流，將對使用者的影響降至最低。

如果您使用 System Center Configuration Manager，您仍然可以使用它來廣泛部署 Office 365 專業增強版。System Center Configuration Manager (最新分支) 擁有更新的 Office 自訂工具的原生支援，隨選即用在安裝時間的套件自訂，以及安裝後軟體更新管理的原生支援。

[Office 365 專業增強版部署指南](https://docs.microsoft.com/zh-TW/deployoffice/deployment-guide-for-office-365-proplus) (英文)

[升級至 Office 365 專業增強版時，移除 Office 現有的 MSI 版本](https://docs.microsoft.com/zh-TW/deployoffice/upgrade-from-msi-version)

[使用 Configuration Manager 管理 Office 365 ProPlus](https://docs.microsoft.com/zh-TW/sccm/sum/deploy-use/manage-office-365-proplus-updates)

[使用 Microsoft Intune 將 Office 365 應用程式指派給 Windows 10 裝置](https://docs.microsoft.com/zh-TW/intune/apps-add-office365)

## <a name="browser-based-apps"></a>瀏覽器型應用程式

有幾個項目需考慮，以確認您的瀏覽器型應用程式可以繼續正常運作。如果您有特定的網站和應用程式與 Microsoft Edge 有相容性問題，您可以使用企業模式網站清單，以便使用 Internet Explorer 11 時網站會自動開啟。

此外，如果您知道您的內部網路網站使用 Microsoft Edge 無法正常運作，則可以設定所有內部網路網站自動使用 Internet Explorer 11 開啟。此程序會使用 XML 檔案來控制 IE11 是否用於每個網站，並使用群組原則來強制執行設定。

到目前為止，我們探討了已知的部署方法。但還有兩種應用程式部署的新方法您可能可以考慮。

[什麼是企業模式](https://docs.microsoft.com/zh-TW/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

## <a name="microsoft-store-for-business"></a>商務用 Microsoft Store 

商務用 Microsoft Store 提供彈性的方式來大規模探索、取得、管理和發佈免費與付費應用程式到 Windows 10 裝置。身為 IT 系統管理員，您可以將精選 Microsoft Store 應用程式以及您的自訂應用程式，發佈到您自己的私人存放區，並視需要指派及重複使用授權。使用者僅能導向至這個存放區，因此只能尋找和安裝核准的應用程式。

Microsoft Store 應用程式可原生內建為 UWP 應用程式，或者您可以使用 Desktop Bridge 為 Store 重新封裝現有的應用程式，並新增適用於 Windows 10 的新式體驗。除了您用來推出 Windows 10 體驗的程式碼，應用程式會維持不變，並繼續以完全信任使用者模式執行。

## <a name="msix-containerization"></a>MSIX 容器化

應用程式封裝的新選項是 MSIX。MSIX 使用 Windows 提供的容器化技術，結合隨選即用、UWP 和 MSI 封裝的最佳層面。具備工具可將現有的安裝程式如 EXE、MSI、APPV 和 APPX 直接移轉到 MSIX，MSIX 容器化為許多目前使用中的安裝技術提供統一的路徑。目前的 Windows 版本中包含 MSIX 支援：執行 Windows 10 RS5 或更新版本的任何裝置，包含要安裝及執行 MSIX 封裝應用程式所需的所有項目。Windows 10 會動態整合收到的 MSIX 容器，同時讓應用程式與作業系統保持分離。

容器化表示可以完全解除安裝和移除套件，與現在許多可能會在系統上留下項目的 MSI 和 EXE 型套件不同。這也表示您只需要標準使用者認證即可安裝應用程式，而不需要擁有系統管理員認證才能安裝 MSIX 容器。MSIX 容器的更新也更有效率。更新發行時，使用區塊層級差異表示只會套用新的二進位檔，減少更新承載，可耗用較少的網路頻寬更快速地進行部署。

您可以透過 [MSIX 技術社群網站](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)找到更多 MSIX 相關資訊

## <a name="next-step"></a>下一步

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[步驟 4：使用者檔案和設定](https://aka.ms/mdd4) (英文)

## <a name="previous-step"></a>上一步

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[步驟 2：目錄和網路整備](https://aka.ms/mdd2) 