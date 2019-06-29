---
title: 裝置設定
description: 瞭解適用于 Microsoft 受管理的電腦裝置的預設原則。
keywords: Microsoft 受管理的桌面、Microsoft 365、服務、檔
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4e41494e853b79d843c5365beea7f01c5ca41308
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390480"
---
# <a name="device-configuration"></a>裝置設定


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

在布建新的 Microsoft 受管理電腦裝置時, 請確定正確設定 (適用于 Microsoft 受管理的桌面) 已優化。 這包括設定為上架程式一部分的一組預設原則。 若要避免衝突, 不應該變更這些原則。 

裝置會使用簽章圖像, 然後在第一位使用者登入時加入 Azure Active Directory 網域。 裝置會自動安裝所需的原則和應用程式, 而不需要任何 IT 介入。

## <a name="why-mdm-over-group-policy"></a>為何 MDM over 群組原則

使用行動裝置管理 (MDM), 而不是群組原則有幾個原因:

- Security-MDM 原則在現代世界中更安全。 群組原則的設計是最適合使用內部部署身分識別, 而 MDM 設計為最適合雲端身分識別管理 (Azure Active Directory)。
- 可靠性-MDM 原則可提供更可靠的原則部署。 此外, MDM 設定會覆寫群組原則物件 (GPO) 原則。 從 Windows 10 版本1803開始, MDM 設定會優先于群組原則值, 以支援移至新式管理的客戶。 
- 與 Microsoft 受管理的桌面願景保持一致-提供更全面的原則部署監視, 並支援以群組為基礎的方法, 讓您可以在必要時以暫停/繼續部署的方式, 逐步推出原則變更。

如需詳細資訊, 請參閱行動[裝置管理](https://docs.microsoft.com/windows/client-management/mdm/)。 

## <a name="default-policies"></a>預設原則

此表格會突出顯示在裝置布建期間套用至所有 Microsoft 受管理電腦裝置的預設原則。 Microsoft 受管理的桌面作業小組未核准所有偵測到的變更, 將會還原 Microsoft 受管理的桌面所管理的物件。

原則 | 描述
--- | ---
安全性基準 | 為所有 Microsoft 受管理的電腦裝置設定 MDM 的[Microsoft 安全性基準](https://docs.microsoft.com/windows/device-security/windows-security-baselines)。 此基準是業界標準的設定。 它已公開發行、經過測試, 而且已由 Microsoft 安全性專家進行過檢查, 讓 Microsoft 受管理的桌面裝置和應用程式在現代的工作場所中保持安全。 <br><br>若要減輕不斷演變的安全性威脅中的威脅, 請使用每個 Windows 10 功能更新, 將 Microsoft 安全性基準更新並部署至 Microsoft 受管理的桌面裝置。<br><br>如需詳細資訊, 請參閱[Windows 10 的安全性基準](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)。
Microsoft 受管理的桌面建議的安全性範本 | 安全性基準的一組建議變更, 可優化使用者體驗。  這些變更會記錄在[安全性附錄](#security-addendum)中。 原則附錄的更新會視需要而定。  
更新部署 | 使用 Windows Update for Business (WUfB) 執行逐步部署軟體更新。 IT 系統管理員無法修改部署群組原則的設定。 如需以群組為基礎的部署的詳細資訊, 請參閱[如何處理更新](../working-with-managed-desktop/updates.md)。
診斷資料 | 裝置將設定為在已知的商業識別碼下提供增強型診斷資料給 Microsoft。 在 Microsoft 受管理的電腦中, IT 系統管理員無法變更這些設定。 對於一般資料保護規定 (GDPR) 地區的客戶, 使用者可以減少所提供的診斷資料層級, 但將會降低服務的能力。 例如, Microsoft 受管理的桌面將無法收集必要的資料, 以依據設定和原則來提供最佳的效能和安全性需求。 如需詳細資訊, 請參閱[在您的組織中設定 Windows 診斷資料。](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>安全性附錄

 本節概述將部署為標準 Microsoft 受管理電腦原則的其他原則。 標準原則會列在 [[預設原則](#default-policies)] 中。 這項設定是由金融服務和高度管制的行業所設計: 優化最安全的想法, 同時維持使用者的生產力。

 ### <a name="additional-security-policies"></a>其他安全性原則

 新增這些原則是為了提升高管制行業的安全性。 
 - **應用程式允許清單**: 應用程式必須受組織信任, 才能在 Microsoft 受管理的電腦裝置上執行。 這會提供鎖定的環境。 任何需要架的應用程式必須傳送至 Microsoft 受管理的桌面作業小組。 如需詳細資訊, 請參閱[Windows Defender Device Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide)。
 - **安全性監視**: Microsoft 會使用[Windows Defender Advanced 威脅防護](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)來監視裝置。 如果偵測到威脅, Microsoft 會通知客戶、隔離裝置, 並從遠端修正問題。 
 - **Disable Powershell v2**: Microsoft 已在2017年8月推出的 PowerShell V2 已被取代。 此功能已在所有 Microsoft 受管理的電腦裝置上停用。 如需此變更的詳細資訊, 請參閱[Windows PowerShell 2.0 過時](https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/)。
