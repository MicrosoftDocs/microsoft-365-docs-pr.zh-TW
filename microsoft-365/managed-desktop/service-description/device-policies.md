---
title: 裝置設定
description: 瞭解適用于 Microsoft 受管理的桌面裝置的預設原則。
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 7086774c046ac28ffa467168e3b5b1affb508ec8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840322"
---
# <a name="device-configuration"></a>裝置設定


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

當您設定新的 Microsoft 受管理桌面裝置時，請確定其具有針對 Microsoft Managed Desktop 優化的正確設定。 該設定包括一組預設原則，設定為上架過程的一部分。 您可以盡可能使用行動裝置管理 (MDM) 來傳遞這些原則。 如需詳細資訊，請參閱行動 [裝置管理](https://docs.microsoft.com/windows/client-management/mdm/)。 

>[!NOTE]
>若要避免衝突，請勿變更這些原則。

裝置會收到簽章圖像，然後在第一位使用者登入時加入 Azure Active Directory 網域。 裝置會自動安裝必要的原則和應用程式，而不需要您的 IT 人員介入。

## <a name="default-policies"></a>預設原則

此表格會顯示在裝置布建期間套用至所有 Microsoft 受管理桌面裝置的預設原則。 Microsoft Managed Desktop Operations 團隊未批准所有已偵測到的變更，將會還原 Microsoft managed Desktop 所管理的物件。

原則 | 描述
--- | ---
安全性基準 | 為所有 Microsoft 受管理的桌面裝置設定 MDM 的[Microsoft 安全性基準](https://docs.microsoft.com/windows/device-security/windows-security-baselines)。 此基準為業界標準設定。 Microsoft 安全性專家已公開發行、經過測試，且已由 Microsoft 安全性專家檢查，以維護現代辦公裝置中的 Microsoft 受管理桌面裝置和應用程式的安全性。 <br><br>為了減輕不斷演變的安全性威脅環境中的威脅，使用每個 Windows 10 功能更新時，Microsoft 安全性基準將更新並部署至 Microsoft 受管理的桌面裝置。<br><br>如需詳細資訊，請參閱 [Windows 安全性基準](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)。
Microsoft 受管理的桌面推薦的安全性範本 | 一組建議變更的安全性基準，可優化使用者體驗。  這些變更會記錄在 [安全性附錄](#security-addendum)中。 原則附錄更新會在必要時進行。  
更新部署 | 使用 Windows Update for Business 執行軟體更新逐步部署。 IT 系統管理員無法修改部署群組原則的設定。 如需以群組為基礎的部署的詳細資訊，請參閱 [Microsoft Managed Desktop 中的更新的處理方式](updates.md)。
流量計費連接 | 根據預設， **> 更新 > 高級選項** 的 [設定] 中的「 (例如 LTE 網路) 等方式來更新。 如果您想要允許所有使用者透過流量計費連線啟用更新，請 [提交變更要求](../working-with-managed-desktop/admin-support.md)，它會針對所有裝置開啟此設定。
| 裝置合規性 | 這些原則是針對所有 Microsoft 受管理的桌面裝置進行設定。 從我們所需的安全性設定 drifts 時，裝置會報告為不相容。

## <a name="windows-diagnostic-data"></a>Windows 診斷資料

 裝置將設定為以已知的商業識別碼在 Microsoft 提供增強的診斷資料。 在 Microsoft 受管理的電腦中，IT 系統管理員無法變更這些設定。 針對一般資料保護法規中的客戶 (GDPR) 地區，使用者可以降低所提供的診斷資料層級，但會減少服務。 例如，Microsoft 受管理的電腦將無法收集必要的資料，以重複執行設定和原則，以最佳的效能與安全性需求。 如需詳細資訊，請參閱 [在您的組織中設定 Windows 診斷資料。](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>安全性附錄

 本節概述除了 [預設原則](#default-policies)中所列的標準 Microsoft 受管理桌面原則之外，將部署的原則。 這項設定的設計是以金融服務和高管制行業為設計，在維護使用者生產力的同時，優化最高的安全性。

 ### <a name="additional-security-policies"></a>其他安全性原則

 新增這些原則，以加強高管制行業的安全性。 
 - **安全性監視**： Microsoft 將使用 [Microsoft Defender for Endpoint 來](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)監視裝置。 如果偵測到威脅，Microsoft 會通知客戶、隔離裝置，並以遠端方式修正問題。 
 - **停用 PowerShell v2**： Microsoft 已移除2017年8月的 PowerShell V2。 在所有 Microsoft 受管理的桌面裝置上，此功能已停用。 如需此變更的詳細資訊，請參閱 [Windows PowerShell 2.0 過時](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)。
