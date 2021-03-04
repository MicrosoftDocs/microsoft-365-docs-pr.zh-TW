---
title: 合規性管理員的 Microsoft 規範設定分析器
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 瞭解如何使用 Microsoft 規範設定分析器，透過 Microsoft 合規性管理員快速開始和執行。
ms.openlocfilehash: 41315dd072e089bd61767181b17dffd5fba88281
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423424"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>合規性管理員的 Microsoft 規範設定分析器 (預覽) 

**本文內容：** 瞭解如何安裝和執行 Microsoft 規範設定 Analyzer 工具，快速開始使用 Microsoft 合規性管理員。

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Microsoft 規範設定分析器 (MCCA)  (預覽) 概述

Microsoft 規範設定分析器 (MCCA) 是一種預覽工具，可協助您開始使用 [Microsoft 合規性管理員](compliance-manager.md)。 MCCA 是一種以 PowerShell 為基礎的公用程式，會取得組織目前的設定，並針對 Microsoft 365 建議的最佳作法進行驗證。 這些最佳作法是以一組控制項為基礎，其中包含資料保護和資料控管的主要法規和標準。

MCCA 可協助您快速查看合規性管理員中的哪些改進動作適用于您目前的 Microsoft 365 環境。 MCCA 識別的每個動作都會提供您的實施建議，其中包含符合性管理員的直接連結，以及開始採取糾正動作的適當解決方案。

若要瞭解 MCCA 的其他資源，請造訪 [GitHub 上的讀我檔案指示](https://github.com/OfficeDev/MCCA#overview)。 此頁面提供有關必要條件的詳細資訊，並提供完整的安裝指示。 您不需要 GitHub 帳戶即可存取此頁面。

**可用性**： MCCA 可供所有使用 Office 365 和 Microsoft 365 授權和美國政府社區 (GCC) 適中和 GCC 高客戶的組織使用，並提供將服務擴充為 DOD 客戶的計畫。

## <a name="install-mcca-and-run-a-report"></a>安裝 MCCA 並執行報告

您可以使用 Windows PowerShell 安裝 MCCA 工具。 下載及安裝工具後，您不需要重複這些步驟，即可執行報告。 每次開啟 MCCA 時，它會詢問您登入認證，並且會產生新的更新報告。

#### <a name="step-1-install-windows-powershell"></a>步驟1：安裝 Windows PowerShell
若要開始，您需要有 Exchange Online PowerShell 模組 (v 2.0.3 或以上 PowerShell 圖庫中提供的) 。 [取得安裝指示](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)。

#### <a name="step-2-install-mcca"></a>步驟2：安裝 MCCA

若要安裝 MCCA，請在系統管理員模式中使用 PowerShell 開始。 請遵循下列步驟：

1. 選取 [Windows **開始** ] 按鈕。
2. 輸入 **PowerShell**，在 [ **Windows PowerShell** 上按一下滑鼠右鍵，然後選取 [ **以系統管理員身分執行**]。
1. 請在命令提示字元處，輸入：

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>步驟3：執行報告

安裝 MCCA 後，您可以執行 MCCA 並產生報告。 若要執行報告：

1. 開啟 PowerShell
2. 執行下列 Cmdlet：

    ```powershell
    Get-MCCAReport
    ```
   如果您是擁有 GCC 的高客戶，您必須提供額外的輸入參數來執行報告：

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. MCCA 執行後，它會進行初始版本檢查，並要求認證。 在輸入的使用者名稱提示字元下，使用您的 Microsoft 365 帳戶電子郵件地址登入 ([查看符合建立報告) 的角色](#role-based-reporting) 。 然後在密碼提示字元處輸入您的密碼。

您的報告將會花大約2-5 分鐘的時間來產生。 完成後，瀏覽器視窗隨即開啟，並顯示您的 HTML 報告。 每次執行工具時，它會要求您的認證，並產生新的報告。 此報告儲存在本機的下列目錄中：

C:\Users \<username> \AppData\Local\Microsoft\MCCA。 

您可以從這個目錄存取先前產生的報告。

## <a name="understanding-your-report"></a>瞭解您的報表

您的報表會根據資料的產生日期和時間來反映資料。 上一節提供有關何時產生、您的組織名稱和租使用者識別碼的詳細資料。

#### <a name="geolocation-based-reporting"></a>以地理位置為基礎的報表

[ **附注** ] 區段會顯示您的報表是根據租使用者的地理位置自訂。 工具中所列的建議會與您的國家或地區有關。

您的地理位置選擇是用來評估敏感資訊類型 (其與該地理位置相關的) ，並產生與您的國家或地區相關的報表。 根據您租使用者中的資料，選擇 [geolocations]。

若要變更您的報表位置資訊，您必須提供地理位置 ( 地理) 輸入參數。 您可以選擇一個或多個適用于您租使用者的 geolocations。

遵循下列指示，根據特定位置執行報告：

1. 開啟 PowerShell
2. 若要指定特定區域，您可以使用下表中與國家或地區相對應的編號來執行 Cmdlet。 以逗號隔開，以輸入多個數位。 例如，下列 Cmdlet 會執行 Asia-Pacific 和日本的自訂報告：

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  國家/地區 | 
  | :------------- | :------------: |
  | 1  | 亞太地區 |
  | 2  | 澳洲 |
  | 3  | 加拿大 |
  | 4  | 歐洲 (除外法國) /中東/非洲 |
  | 5  | 法國 |
  | 6  | 印度 |
  | 7  | 日本 |
  | 8  | 韓國 |
  | 9  | 北美 (（加拿大除外）)  |
  | 10  | 南美洲 |
  | 11  | 南非 |
  | 12  | 瑞士 |
  | 13  | 阿拉伯聯合大公國 |
  | 14  | 英國 |


 > [!NOTE]
> 報告一定會包括 MCCA 支援的國際機密資訊類型，例如 SWIFT 程式碼、信用卡號碼等等。

#### <a name="role-based-reporting"></a>以角色為基礎的報表

您的報表也會根據您的角色進行自訂。

下表顯示哪些角色可以存取報表的哪些區段。 組織內的其他角色 (未列在下表中) 可能無法執行該工具，也可能會執行該工具，並對最終報告中的資訊存取有限。

![MCCA 角色](../media/compliance-manager-mcca-roles.png "MCCA 角色")

例外狀況：
1. 使用者將無法產生「用於 Exchange Online 的 IRM」一節中的 IP 報告。
2. 使用者將能夠產生「用於 Exchange Online 的 IRM」一節中的 IP 報告。
3. 使用者將能夠對「在 O365 啟用通訊法規遵從性」一節中，產生 IP 的報告。
4. 使用者將無法產生「在 Office 365 中啟用審核」一節中的 IP 報告。
5. 使用者將會產生「在 Office 365 中啟用審核」一節中的 IP 報告。

#### <a name="solutions-summary-section"></a>解決方案摘要區段

報告的 [ **解決方案摘要** ] 區段提供您的組織可在合規性管理員中採取的改進動作，以協助改善您的相容性狀況。

![MCCA-解決方案摘要](../media/compliance-manager-mcca-solutions.png "MCCA 解決方案摘要畫面")

MCCA 會根據合規性管理員中建議的改進動作評估您目前的設定。 本節會列出 MCCA 工具所識別的任何改進動作（如有需要注意）。

每個 Microsoft 解決方案旁邊都有色彩編碼方塊，指出與合規性管理員中的改進動作相對應的專案數。 動作會分解成三個狀態狀態：

- **確定**：符合建議條件的動作，在此時間不需要注意
- **改進**：需要注意的動作
- **建議**：不需要注意，但我們建議最佳作法的動作
 
選取方塊以查看改進和建議。

**具有改進狀態的專案**

選取 [改進動作] 右邊的 [ **改善** ] 標籤旁的下拉式清單。 您將會看到有關您目前設定的快速摘要和詳細資料，以及建議的改進動作。 摘要包括合規性管理員中的直接連結、Microsoft 365 規範中心中適用的解決方案，以及相關的檔。

按一下 [合規性管理員] 連結，可將您帶到尚未執行之解決方案內所有改進動作的篩選視圖。 您可以從這裡看到您可以達到的點數，以提升您的 [合規性分數](compliance-score-calculation.md)和其適用的評估，以及適用的規章和認證。

針對 DLP，有一個 **修正腳本** 按鈕，可根據建議的建議，提供預先產生的 PowerShell 腳本。 您可以將它直接複製並貼到您的 PowerShell 主控台。 它會在測試模式中建立 DLP 原則

**具有建議狀態的專案**

選取 [改進動作] 右邊的 **建議** 標籤旁的下拉式清單。 您將會看到組織目前與「改進」動作相關的 Microsoft 365 環境摘要，以及建議的最佳作法。

## <a name="resources"></a>資源

如需有關安裝、設定和使用 MCCA 的詳細資訊，請參閱 [GitHub (上的讀我檔案指示](https://github.com/OfficeDev/MCCA#overview)) 沒有 GitHub 帳戶。

如需 Windows PowerShell 的詳細資訊，請從 [使用 PowerShell 檔](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7)開始。 另請參閱 [啟動 Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)。
