---
title: 收集電子文件探索診斷資訊
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 深入瞭解如何收集 Microsoft 支援案例的 eDiscovery 診斷資訊。
ms.openlocfilehash: 842f8baf770f178df3298bbfa911de26ce946ed0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926553"
---
# <a name="collect-ediscovery-diagnostic-information"></a>收集電子文件探索診斷資訊

當您開啟與核心 eDiscovery 或 Advanced eDiscovery 相關的支援案例時，偶爾 Microsoft 支援工程師需要您問題的特定資訊。 本文提供如何收集診斷資訊以協助工程師調查和解決問題的指導方針。 一般來說，您不需要先收集此資訊，直到 Microsoft 支援工程師要求您這麼做。

> [!IMPORTANT]
> 本文所述的指令程式和診斷資訊輸出可能包含有關組織中訴訟或內部調查的敏感資訊。 在將原始診斷資訊傳送至 Microsoft 支援之前，您應該查看資訊，並將任何敏感資訊 (，例如，將其他方的名稱或其他資訊以) 取代，以進行訴訟或調查 `XXXXXXX` 。 使用此方法也會向 Microsoft 支援工程師指出資訊已 redacted。

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>收集核心 eDiscovery 的診斷資訊

收集核心 eDiscovery 的診斷資訊以 Cmdlet 為基礎，因此您必須使用安全性 & 合規性中心 PowerShell。 下列 PowerShell 範例會執行 Cmdlet，然後將輸出儲存至指定的文字檔。 在大多數支援案例中，您只需要執行下列其中一個命令。

若要執行下列 Cmdlet，請連線[至安全性 & 合規性 </span> 中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。 連線之後，請執行下列一或多個命令，並確定以實際的物件名稱取代預留位置。

檢查所產生的文字檔並 redacting 機密資訊之後，將其傳送給 Microsoft 支援工程師，以在您的案例上運作。

> [!NOTE]
> 您也可以執行本節中的命令來收集 Microsoft 365 規範中心的 **內容搜尋** 頁面上所列之搜尋和匯出的診斷資訊。

### <a name="collect-information-about-searches"></a>收集搜尋的相關資訊

下列命令會收集用來調查內容搜尋問題或與核心 eDiscovery 案例相關聯之搜尋時有用的資訊。

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>收集搜尋動作的相關資訊

下列命令會收集資訊，以調查預覽、匯出或清除內容搜尋結果的問題，或與核心 eDiscovery 案例相關聯的搜尋。 您可以按一下 [ **匯出** ] 索引標籤上所列的匯出，識別搜尋動作的名稱。若要識別預覽和清除動作的名稱，您可以執行 **Get-ComplianceSearchAction** Cmdlet 以顯示所有動作的清單。 搜尋動作名稱的格式是透過附加 `_Preview` 、 `_Export` 或 `_Purge` 對應的搜尋名稱所構造。

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>收集 eDiscovery 保留的資訊

當核心 eDiscovery 案例相關聯的 eDiscovery 暫止未如期運作時，請執行下列命令來收集有關案例保留原則的資訊，以及 eDiscovery 保留的相關案例保留規則相關資訊。 在下列命令中， *案例保留原則名稱* 與 eDiscovery 保留的名稱相同。 您可以在核心 eDiscovery 案例的 [ **保留** ] 索引標籤中識別此名稱。

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>收集所有案例資訊

在某些情況下，Microsoft 支援人員在調查您的問題時，並不會體現出所需的資訊。 在此情況下，您可以收集核心 eDiscovery 案例的所有診斷資訊。 下列命令中的 *核心 eDiscovery 案例名稱*，與 Microsoft 365 規範中心的 **核心 ediscovery** 頁面上顯示之案例的名稱相同。

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>收集 Advanced eDiscovery 的診斷資訊

Advanced eDiscovery 案例中的 [**設定**] 索引標籤可讓您快速複製案例的診斷資訊。 診斷資訊會儲存至剪貼簿，這樣您就可以將其貼到文字檔，並傳送給 Microsoft 支援人員。

1. 移至 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ，然後按一下 [ **顯示所有 > EDiscovery > Advanced**。

2. 選取案例，然後按一下 [**設定**] 索引標籤。

3. 在 [ **案例資訊**] 下，按一下 [ **選取**]。

4. 在飛入頁面上，按一下 [ **複製診斷資訊** ]，將資訊複製到剪貼簿。

5. 在記事本) 中開啟文字檔 (，然後貼上文字檔中的資訊。

6. 儲存文字檔，並將其命名 `AeD Diagnostic Info YYYY.MM.DD` 為 (例如) 所示 `AeD Diagnostic Info 2020.11.03` 。

檢查檔案並 redacting 機密資訊之後，將其傳送給 Microsoft 支援工程師，以在您的案例上運作。