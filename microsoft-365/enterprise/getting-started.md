---
title: 快速入門 - 現代化電腦的部署
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
description: 現代化電腦的部署程序簡介。
ms.openlocfilehash: bb5c1433554e984676884fd2bac4fa5120c76996
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866531"
---
# <a name="getting-started---modern-desktop-deployment"></a>快速入門 - 現代化電腦的部署

雲端正改變電腦的管理方式，利用 Microsoft 智慧型雲端提供龐大的深入資訊來協助 IT 專業人員轉變為現代化電腦。這個系列是專門設計來協助您根據 Windows 10 與 Office 365 專業增強版規劃及轉變為現代化電腦。

<img src="media/getting-started-media/getting-started-media-1.png" alt="Desktop Deployment Wheel" style="background-color: #fff;" />

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-1.png" alt="Getting Started" height="130" width="130" /></td>
<td><p><strong>快速入門：人員、流程及技術指導方針</strong></p>
<p>探索現代化電腦的優點，重大變更、考量與先前的部署以及最佳做法，以確保順利轉移到 Windows 10 和 Office 365 專業增強版。</p></td>
<td><a href="https://aka.ms/ddev0" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-13.png" alt="Getting Started" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>在本系列中，我們會說明使用現有工具的最佳方法，為您介紹新技術、服務和雲端啟用的方法。若要查看完整的桌面部署程序，請瀏覽[現代化電腦部署中心](https://aka.ms/HowToShift) (英文)。
>

歡迎使用現代化電腦部署中心，我們了解如何協助您規劃及轉變為現代化電腦的中心位置。可讓您利用由最新的生產力、團隊合作和共同作業體驗提供的安全工作區。

如果您有一段時間未部署新的桌面環境，好消息是太多的部署程序已有所改善。過去的挑戰 (例如應用程式相容性) 可能是現今與新的工具比較不會發生的問題，且雲端提供的深入了解可讓您有信心、比以往更快且更有效率地往前邁進。

在本文中，我們將概述已變更的內容，然後瀏覽電腦部署轉輪。這會引導您完成您轉變至 Windows 10 以及 Office 365 專業增強版的建議步驟，詳細說明如何運用現有的工具和程序，同時採用現代化管理技術和方法。

## <a name="why-upgrade"></a>為什麼要升級？

將 Windows 10 和 Microsoft 智慧雲端合併可增強您的能力，為您的使用者提供最有能力、豐富且安全的工作區，並可以讓您簡化支援基礎結構。

現代化管理實務的其中一項重要租用戶是裝置一律為最新版本的。透過本系列，您將會看到所提供的新功能，可協助您移至 Windows 10 與 Office 365 專業增強版，以及如何保持取得上述兩項的最新半年度發行。

[適用於 IT 專業人員的 Windows 10](https://www.microsoft.com/zh-TW/itpro/windows-10) (英文)

## <a name="what-has-changed"></a>有什麼變更

讓我們先了解上一個桌面部署開始已變更及改善之處。如果您還沒有轉變您的電腦環境，您可能還在使用 Windows 7 和 Office 2010 或 Office 2013。如果您是如此，就會發現自您上次重大升級開始有幾件事有所進化。以下是一些核心變更：

**身分識別與存取管理**現代化電腦具有雲端產能、安全性和管理服務，其核心擁有身分識別與存取管理服務：Azure Active Directory。這可允許在您的雲端服務之間進行單一登入和安全連線。這表示您將需要 Azure AD 就位。這可讓您充分利用 Microsoft 365 服務，例如 Office 365、Intune 或 Windows Autopilot。

[Microsoft 365](https://www.microsoft.com/zh-TW/microsoft-365/default.aspx)

**保護開機前環境安全** 64 位元 UEFI 韌體會取代 BIOS。這不僅可加快啟動時間，在 Windows 10 中啟動許多現代化安全性功能時也是必須的。Windows 10 會在 BIOS 上執行，但強烈建議使用 UEFI。如果您尚未從 BIOS 切換為 UEFI 和 64 位元，現在正是時候。有一些工具可協助您在 Windows 10 升級期間或之後進行此切換。

[使用 MBR2GPT 從 BIOS 轉換為 UEFI](https://technet.microsoft.com/zh-TW/windows/mt782786.aspx) (英文)

**雲端裝置管理** Microsoft Intune 等服務，可讓您像其他行動裝置一樣在同一個地方管理您的 Windows 10 裝置。Microsoft Intune 的特點是使用 System Center Configuration Manager 共同管理 Windows 10 裝置。您可以使用 System Center Configuration Manager 來協助您轉換為 Windows 10，然後新增 Microsoft Intune。System Center Configuration Manager 搭配使用，會變成貴組織內的智慧型 Edge，並連線至 Microsoft 智慧型雲端。無論使用者裝置位於何處，是否在貴組織連線或在公用雲端連線，這都能讓您管理使用者的裝置。

[Windows 10 裝置的共同管理](https://docs.microsoft.com/zh-TW/sccm/core/clients/manage/co-management-overview) (英文)

**雲端部署服務**當您取得的新電腦時，我們已引進新的雲端服務，可協助您部署 Microsoft 365 裝置。這稱為 Windows Autopilot 部署服務。Autopilot 會整合您的硬體提供者，且新電腦會在 Autopilot 中自動註冊。這可讓新電腦直接出貨給使用者。當電腦第一次啟動時，會快速設定為貴組織所需的設定，並針對使用者的特定需求進行自訂。

[Windows Autopilot](https://www.microsoft.com/zh-TW/windowsforbusiness/windows-autopilot) (英文)

**隨選即用部署**佈建 Office 桌面應用程式時，Office 365 專業增強版是慣用的選項。這可讓您存取 Office 中所開發的最新創新功能，如此您就不需要等待幾年的時間即可使用新功能。您也可以使用稱為「隨選即用」的新安裝。

「隨選即用」與過去的 MSI 套件截然不同。「隨選即用」較快、較輕，且會使用程式資料流讓使用者在幾分鐘內即可啟動並執行，並在背景中進行更新。別擔心，這仍然是 Office 的本機複本，您可以繼續使用現有的部署工具s – 例如 System Center Configuration Manager – 來佈建及設定應用程式。

[Office 365 專業增強版部署指南](https://docs.microsoft.com/zh-TW/DeployOffice/deployment-guide-for-office-365-proplus) (英文)

**半年度更新**一旦移至 Windows 10 和 Office 365 專業增強版後，每半年會提供更新並含新功能。但隨著 Microsoft 能夠從雲端提供深入資訊來協助您，就可以快速且充滿自信地推出這些更新至數百或數千個裝置。例如就地升級，功能更新保留應用程式、從先前版本的資料和設定。

## <a name="the-deployment-process-wheel"></a>部署程序轉輪

在您開始之前，可能需要建立高層級的計劃，並取得新進人員所需的贊助。我們的部署程序轉輪概述重要的步驟，可協助您找出在下列部署區域中管理的核心小組成員和資源。

**[步驟 1：裝置和應用程式整備](https://aka.ms/mdd1)** 為了成功部署，您必須先知道您所擁有的項目。這表示取得您裝置和應用程式的詳細目錄，並驗證相容性。

若要協助進行這項工作，您可以在雲端服務 Windows Analytics 中找到可用工具。Windows Analytics 可讓您深入發掘收集自數億部電腦的相容性情報與遙測，來評估裝置上執行的應用程式和驅動程式，如此您可以建立您電腦空間的完備性。您甚至可以從 Windows Analytics 匯出一份「準備好進行部署的電腦」清單至 System Center Configuration Manager (如果您使用)，可讓您在準備好時建立資料導向的目標電腦集合。

[開始使用升級整備](https://docs.microsoft.com/zh-TW/windows/deployment/upgrade/upgrade-readiness-get-started) (英文)

**[步驟 2：目錄和網路整備](https://aka.ms/mdd2)** 如果您尚未進行，下一步可以實作 Azure Active Directory 以進行身分識別與存取管理。您也需要準備網路，以移動其中的系統映像、應用程式套件、使用者檔案及更新。這表示會有大量的其他資料；您的網路必須有能力處理這項額外負荷，而不會影響貴組織的日常工作。我們提供多種網路最佳化，從頻寬節流和對等選項到動態頻寬清除及差異化更新。

[BranchCache 與對等快取](https://blogs.technet.microsoft.com/swisspfe/2018/01/25/branch-cache-vs-peer-cache/) (英文)

**[步驟 3：Office 和企業營運應用程式傳遞](https://aka.ms/mdd3)** (英文) 在 Windows 繼續支援 MIS 安裝之際，現在也支援較新的安裝機制，適合用於自動化部署和持續更新。Office 365 專業增強版和 Windows 2019 用戶端使用「隨選即用」，您可能需要讓一些 UWP 應用程式可供使用，您可能會逐漸發現要部署協力廠商應用程式及內部開發的企業營運應用程式，其是使用新的 MSIX 封裝應用程式。這個步驟可確保您的應用程式準備好可自動化部署，且您已準備好成功，無論您的應用程式是否使用「隨選即用」、MSIX、傳統 MSI 部署，或是您所設定業務的 Microsoft Store 中部署的 UWP 應用程式。

[MSIX 簡介](https://blogs.msdn.microsoft.com/sgern/2018/06/15/msix-intro/) (英文)

**[步驟 4：使用者檔案和設定移轉](https://aka.ms/mdd4)** (英文) 這在任何電腦取代或重新整理循環中都是重要的步驟：您必須確保使用者的檔案、資料和設定移動成功，且在移轉過程中會加以保留。此步驟涵蓋手動或自動移轉的可用選項，包含已知和新的選項。

如同先前的更新，使用者狀態移轉工具會繼續成為自動化此程序時很有價值的工具，且會保持為使用 System Center Configuration Manager 或 Microsoft Deployment Toolkit 協調移轉不可或缺的一部分。但是在移轉過程中，移動這些資料可能是電腦取代項目的時間瓶頸，因為傳送期間有時候每部電腦會涉及兩次數百 GB 的物理情況 – 先從現有的電腦，然後再返回新的電腦。OneDrive 所啟用的新選項是「已知資料夾移動」，會在部署之前在雲端大量同步處理使用者文件、圖片及電腦檔案。

[將 Windows 已知資料夾重新導向並移動至 OneDrive](https://docs.microsoft.com/zh-TW/onedrive/redirect-known-folders) (英文)

**[步驟 5：安全性與合規性](https://aka.ms/mdd5)** 安全性與合規性是移至 Windows 10 和 Office 365 專業增強版時具有許多優點的區域。請務必熟悉新的內建功能，並與既有的功能比較。例如，Windows 10 中使用虛擬化安全性的新功能可防止認證竊盜、防止瀏覽器的漏洞和惡意程式碼執行，方法是隔離作業系統的核心程序及秘密。此外，「進階威脅防護」等雲端服務可提供整合的平台，以強化安全性、外洩後偵測、調查及回應。進階的威脅防護也可以保護您免於受到惡意電子郵件附件、不安全的超連結等攻擊。

[Microsoft Security](https://www.microsoft.com/zh-TW/security/default.aspx) (英文)

**[步驟 6：作業系統部署與功能更新](https://aka.ms/mdd6)** (英文) 在一切就緒後，下一步就是部署作業系統映像。進行大量的重擔可以使用 System Center Configuration Manage 順序和基礎結構來完成。建議的方法是以階段部署，首先設定目標，並使用一組代表硬體和應用程式部署至貴組織中的「早期採納者群組」。然後，您可以使用這些裝置和使用者的資料逐漸將目標設定為更多部電腦。

[在 System Center Configuration Manager 中部署作業系統的簡介](https://docs.microsoft.com/zh-TW/sccm/osd/understand/introduction-to-operating-system-deployment) (英文)

**[步驟 7：Windows 和 Office 服務](https://aka.ms/mdd7)** (英文) 這代表您維護使用者電腦大小方式的主要轉變。您可以利用 Windows 10 (以及 Office 365 專業增強版) 的這項移動，將管理 Windows (和 Office) 改變為一項服務。取代每隔幾年的大型技術轉變，您會持續將全新的功能、體驗和保護帶給您的使用者。半年度功能更新每年秋季及春季會提供全新的功能，而每月累積的品質更新將會包含安全性、可靠性和錯誤 (bug) 修正。雖然您可以選擇部署 Office 2019 用戶端，但強烈建議您移至 Office 專業增強版。這會遵循 Windows 的類似服務方案，也可讓使用者定期獲得 Office 應用程式的更新。

![](media/getting-started-media/getting-started-media-2.png)

[Windows 即服務概觀](https://docs.microsoft.com/zh-TW/windows/deployment/update/waas-overview) (英文)

**[步驟 8：使用者通訊和訓練](https://aka.ms/mdd8)** (英文) 最後這個步驟對於推動使用新功能以提升團隊合作、通訊、安全性等至關重要。在廣泛部署目標為早期採納者週期外的使用者之前，建議您推行使用者通訊和訓練。這將有助於推動在 Office、Windows 或其他企業營運應用程式和服務中的新功能使用方式所需變更。如需協助，我們透過 Microsoft FastTrack 提供免費線上訓練。此外，我們已發佈免費的範例通訊計劃和時間表，搭配電子郵件和社交及內部網路範本來協助您推出 Windows 10。身為 Microsoft 365 或 Office 365 的組織，貴組織可能也符合資格且直接支援。

## <a name="next-step"></a>下一步

現在您已了解新功能和差異，我們已概要說明建議的部署程序轉輪。透過此可供您轉變現代化電腦的端對端指導方針和工具體驗，我們開始吧。

## <a name="step-1-device-and-app-readinesshttpsakamsmdd1"></a>[步驟 1：裝置和應用程式整備](https://aka.ms/mdd1) (英文)

