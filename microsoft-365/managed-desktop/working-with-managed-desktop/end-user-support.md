---
title: 取得 Microsoft 受管理的電腦的使用者支援
description: 使用者如何取得服務和裝置的協助
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362603"
---
# <a name="getting-help-for-users"></a>為使用者取得協助

如果您已到達 [工作流程](../service-description/user-support.md) 中需要要求提升裝置存取或升級至 Microsoft 的點，請執行下列步驟：
 
>[!NOTE]
>這些支援選項不適用於測試群組中的裝置。

## <a name="elevation-requests"></a>提升要求

在您要求更高的裝置存取權之前，最好先檢查哪些動作最適合。

- **一般動作** 為此程式的目的，在疑難排解 Microsoft 受管理的電腦裝置的問題時，會進行定期執行。 範例包含：
    - 提升內建的系統疑難排解程式、命令提示字元，或 Windows PowerShell
    - 疑難排解商務營運應用程式
    - 使用變通辦法修正應該在設計 (運作的專案，例如 BitLocker 啟用或系統時間未更新) 
    - 提升裝置管理員執行的工作如更新驅動程式、卸載裝置或掃描新的變更

- **不建議採取的動作** 包括下列各項：
    - 安裝軟體或瀏覽器
    - 在 Windows 設定外安裝驅動程式（包括週邊設備的驅動程式）
    - 安裝 .msi 或 .exe 檔
    - 安裝 Windows 功能

- **不支援的動作** 包括下列各項：
    - 安裝與 Microsoft 受管理的電腦安全性或管理功能或作業相衝突的軟體或功能
    - 停用 Microsoft 受管理的電腦所需的 Windows 功能，例如 BitLocker
    - 修改組織所管理的設定

### <a name="to-request-elevation"></a>要求提升

1. 移至入口網站 [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) ，並以您的 Azure Active Directory 認證登入。
2. 選取 [ **新增提升要求**]。
3. 提供這些詳細資料：
    - 支援來自您自己支援票證系統的 **票證識別碼**。
    - **裝置名稱**：輸入裝置序號，然後從功能表中選取裝置。
    - **類別**：選取最符合您問題的類別。 如果 [沒有] 選項似乎是關閉的，請選取 [ **其他** ]，並在 [動作] 欄位的 **標題** 和 **方案** 中提供其他資訊。 您最好盡可能選取類別。
    - **子類別**：選取最符合問題的一種。 如果沒有任何選項似乎是關閉的，請選取 [ **其他** ]，並在 **標題** 中提供簡短的描述。 在 [ **行動計畫**] 中，提供您計畫在授與後採取的疑難排解步驟。
4. 選取 **[提交]**。


## <a name="escalation-requests"></a>上報要求


如果您需要將問題 [提升](../service-description/user-support.md#escalation-portal) 至 Microsoft，請遵循下列步驟：

1. 移至入口網站 [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) ，並以您的 Azure Active Directory 認證登入。
2. 選取 [ **呈報要求**]，然後選取 [ **新增呈報要求**]。
3. 提供這些詳細資料：
    - **類別**：選取最符合您問題的類別。
    - **Title**：提供非常簡短的描述。
    - **描述**：新增可協助我們小組瞭解問題的其他詳細資料。 如果您需要附加檔案，您可以在提交要求後回到要求。
    - **主要連絡人資訊**：提供如何聯繫主要人員，以與我們的小組合作的相關資訊。
4. 選取 **[提交]**。
5. 重新訪問相同入口網站中的票證，以與我們的小組互動。

> [!NOTE]
> 只有嚴重的 C 問題可透過此路徑上報。 如需其他問題，請與您的 IT 系統管理員聯繫以透過管理入口網站來歸檔要求。