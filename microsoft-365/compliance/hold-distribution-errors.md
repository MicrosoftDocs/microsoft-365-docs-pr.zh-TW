---
title: 疑難排解電子文件探索保留錯誤
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 疑難排解在核心 eDiscovery 中套用至保管人和非 custodial 資料來源的法律封存相關錯誤。
ms.openlocfilehash: 3bd417f2eb6bfb8de8d4b5ccaeb48e6ae1c888eb
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860384"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a>疑難排解電子文件探索保留錯誤

本文討論 eDiscovery 保留可能發生的常見問題，以及如何解決這些問題。 本文也包含建議的做法，可協助您緩解或避免這些問題。

## <a name="recommended-practices"></a>建議的做法

若要減少與 eDiscovery 保留相關的錯誤數，建議採用下列做法：

- 如果保留分配仍處於擱置狀態，且狀態為 [ `On (Pending)` 或] `Off (Pending)` ，請等到保留分配完成之後，再進行進一步的更新。

- 將更新合併到單一大量要求中的 eDiscovery 保留，而不是針對每個交易重複更新保留原則。 例如，若要使用 [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) Cmdlet 將多個使用者信箱新增至現有的保留原則，請執行命令 (或新增為腳本) 的程式碼區塊，使其只執行一次，才能新增多個使用者。

  **正確**

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   **不正確**

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   在上述錯誤的範例中，Cmdlet 會執行五個不同的時間來完成任務。 如需將使用者新增至保留原則的建議作法的詳細資訊，請參閱 [more information](#more-information) 一節。

- 在取得 eDiscovery 保留問題的 Microsoft 支援服務之前，請遵循 [錯誤/問題中的步驟： [保留未同步](#errorissue-holds-dont-sync) 處理] 區段以重試保留發佈。 此處理程式通常會解決暫時問題，包括內部伺服器錯誤。

## <a name="errorissue-holds-dont-sync"></a>錯誤/問題：保留未同步處理

如果您在將保管人和資料來源置於保留狀態時看到下列錯誤訊息，請使用解決步驟來對問題進行疑難排解。

> 資源：部署原則所花費的時間超過預期。 更新最終部署狀態可能需要另外2小時，所以請在幾小時內回來查看。

> 由於暫時性的 Office 365 資料中心問題，無法將原則部署至內容來源。 目前的原則不會套用到來源中的任何內容，因此不會影響已封鎖的部署。 若要修正此問題，請嘗試重新部署原則。

> 對不起，由於暫時性的內部伺服器錯誤，我們無法對原則執行所要求的變更。 請在30分鐘後再試一次。

### <a name="resolution"></a>解決方案

1. 連線至[安全性 & 規範中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)並執行 eDiscovery hold 的下列命令：

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. 檢查 *DistributionDetail* 參數中的值。 尋找如下的錯誤：

   > 錯誤：資源：部署原則所花費的時間超過預期。 更新最終部署狀態可能需要另外2小時，所以請在幾小時內回來查看。

3. 嘗試在有問題的保留原則上執行 **Set-CaseHoldPolicy RetryDistribution** 命令;例如：

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a>其他資訊

- 在「建議的做法」一節中，針對多位使用者更新保留原則的指導，是由系統封鎖保留原則同時更新所產生的結果。 這表示當更新的保留原則套用至新的內容位置，且保留原則處於擱置狀態時，無法將其他內容位置新增至保留原則。 以下是一些您應記住的事項，以協助您緩解此問題：
  
  - 每次更新保留更新時，就會立即進入暫止狀態。 [擱置狀態] 狀態表示正在將保留套用至內容位置。
  
  - 如果您有執行迴圈的腳本，並將各位置新增至原則一 (類似于「建議做法」) 一節中所示的錯誤範例），第一個內容位置 (例如，使用者信箱) 會啟動觸發擱置狀態的同步處理常式。 這表示在後續的迴圈中新增至原則的其他使用者會產生錯誤。
  
  - 如果您的組織使用執行迴圈的腳本來更新保留原則的內容位置，您必須更新腳本，讓它更新單一大量作業 (中的位置，如「建議的做法」) 一節中所示的正確範例中所示。
