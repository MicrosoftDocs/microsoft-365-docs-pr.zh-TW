---
title: 裝置設定
description: 瞭解適用于 Microsoft 受管理的電腦裝置的預設原則。
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e4f07adb051dde24d374055d206955ad61df432a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920489"
---
# <a name="device-configuration"></a>裝置設定


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

設定新的 Microsoft 受管理的電腦裝置時，請確定其具有針對 Microsoft 受管理的電腦優化的適當設定。 該設定包括一組預設原則，設定為上架過程的一部分。 您可以盡可能使用行動裝置管理 (MDM) 來傳遞這些原則。 如需詳細資訊，請參閱行動 [裝置管理](/windows/client-management/mdm/)。 

>[!NOTE]
>若要避免衝突，請勿變更這些原則。

裝置會收到簽章圖像，然後在第一位使用者登入時加入 Azure Active Directory 網域。 裝置會自動安裝必要的原則和應用程式，而不需要您的 IT 人員介入。

## <a name="default-policies"></a>預設原則

此表格著重于在裝置布建期間套用至所有 Microsoft 受管理的電腦裝置的預設原則。 所有偵測到的變更，都不會由 Microsoft 受管理的電腦運作團隊核准成 Microsoft 受管理的電腦所管理的物件，將會還原。

原則 | 描述
--- | ---
安全性基準 | 針對所有 Microsoft 受管理的電腦裝置設定 MDM 的[Microsoft 安全性基準](/windows/device-security/windows-security-baselines)。 此基準為業界標準設定。 Microsoft 安全性專家已公開發行、經過測試，且已由 Microsoft 安全性專家檢查，以保持目前的工作場所安全 Microsoft 受管理的電腦裝置和應用程式。 <br><br>為了減輕不斷演變的安全性威脅環境中的威脅，Microsoft 安全性基準將會更新並部署至每個 Windows 10 功能更新的 Microsoft 受管理的電腦裝置。<br><br>如需詳細資訊，請參閱[Windows 安全性基準](/windows/security/threat-protection/windows-security-baselines)。
Microsoft 受管理的電腦建議的安全性範本 | 一組建議變更的安全性基準，可優化使用者體驗。  這些變更會記錄在 [安全性附錄](#security-addendum)中。 原則附錄更新會在必要時進行。  
更新部署 | 使用 Windows 更新為商務執行軟體更新逐步部署。 IT 系統管理員無法修改部署群組原則的設定。 如需以群組為基礎的部署的詳細資訊，請參閱[如何處理 Microsoft 受管理的電腦中的更新](updates.md)。
流量計費連接 | 根據預設，**設定 > 更新 > 高級選項**] 中的 (，例如，在關閉 LTE 網路) 時，就會關閉以流量計費連接的更新。 如果您想要允許所有使用者透過流量計費連線啟用更新，請 [提交變更要求](../working-with-managed-desktop/admin-support.md)，它會針對所有裝置開啟此設定。
| 裝置合規性 | 這些原則都是針對所有 Microsoft 受管理的電腦裝置進行設定。 從我們所需的安全性設定 drifts 時，裝置會報告為不相容。

## <a name="windows-diagnostic-data"></a>Windows 診斷資料

 裝置將設定為以已知的商業識別碼在 Microsoft 提供增強的診斷資料。 做為 Microsoft 受管理的電腦的一部分，IT 系統管理員無法變更這些設定。 針對一般資料保護法規中的客戶 (GDPR) 地區，使用者可以降低所提供的診斷資料層級，但會減少服務。 例如，Microsoft 受管理的電腦將無法收集必要的資料，以重複執行設定和原則，以最佳的效能與安全性需求。 如需詳細資訊，請參閱[設定組織中的 Windows 診斷資料。](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="security-addendum"></a>安全性附錄

 本節概述除了[預設原則](#default-policies)中所列的標準 Microsoft 受管理的電腦原則之外，將會部署的原則。 這項設定的設計是以金融服務和高管制行業為設計，在維護使用者生產力的同時，優化最高的安全性。

 ### <a name="additional-security-policies"></a>其他安全性原則

 新增這些原則，以加強高管制行業的安全性。 
 - **安全性監視**： Microsoft 將使用 [Microsoft Defender for Endpoint 來](/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)監視裝置。 如果偵測到威脅，Microsoft 會通知客戶、隔離裝置，並以遠端方式修正問題。 
 - **停用 PowerShell v2**： Microsoft 已移除2017年8月的 PowerShell V2。 已停用所有 Microsoft 受管理的電腦裝置上的此功能。 如需此變更的詳細資訊，請參閱[Windows PowerShell 2.0](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)（已過時）。