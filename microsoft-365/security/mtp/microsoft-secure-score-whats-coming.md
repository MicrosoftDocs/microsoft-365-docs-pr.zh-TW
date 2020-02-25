---
title: 什麼 Microsoft 安全分數即將？
description: 說明 Microsoft 安全分數 Microsoft 365 安全性中心、 詳細資料的計算方式，以及安全性系統管理員可以預期。
keywords: 安全性、 惡意程式碼、 Microsoft 365、 M365，安全分數資訊安全中心、 改進動作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55c7cb34c5484eaf8f6693be0ce439e33a82550f
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266965"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>什麼 Microsoft 安全分數即將？

若要讓 Microsoft 安全分數較佳的安全性狀態代表並改善可用性，我們會在不久的將來進行一些變更。 您的成績和最大可能分數會變更。 不過，這並不表示您的安全性狀態變更。

若要深入了解最近的變更，請參閱[What's new in Microsoft 安全分數？](microsoft-secure-score.md#whats-new)

## <a name="march-2nd-2020"></a>2nd 2020 年 3 月

### <a name="removing-improvement-actions-from-intune"></a>從 Intune 移除改進動作

提供從 Intune Microsoft 安全分數改進動作的評估之後, 我們決定它們並不提供在組織中的裝置安全性狀態的有用表示法。 而不將重點放在原則，我們正在努力帶來安全性控制的直接評估之裝置的組態狀態。

會移除下列 Intune 改進動作：

- 啟用 Microsoft Intune 行動裝置管理
- Android 版建立 Microsoft Intune 合規性原則
- 建立工作 Android 版的 Microsoft Intune 合規性原則
- Android 版建立 Microsoft Intune 應用程式防護原則
- 建立 iOS 版 Microsoft Intune 應用程式保護原則
- 標記裝置與指定為不符合任何 Microsoft Intune 合規性原則
- 建立 iOS 版 Microsoft Intune 合規性原則
- 建立 macOS Microsoft Intune 合規性原則
- 建立 Windows 的 Microsoft Intune 合規性原則
- Android 版建立 Microsoft Intune 設定設定檔
- 建立工作 Android 版的 Microsoft Intune 設定設定檔
- 建立 macOS 的 Microsoft Intune 設定設定檔
- 建立 iOS 版 Microsoft Intune 設定設定檔
- 建立 Windows 的 Microsoft Intune 設定設定檔
- 啟用 Microsoft Intune 中的增強型的 jailbreak 偵測
- 需要修正的所有裝置、 防毒和防火牆啟用
- 啟用 Windows Defender ATP 整合至 Microsoft Intune
- 建立 Microsoft Intune Windows 資訊保護原則
- 需要有進階安全性設定的所有裝置
- 每週檢閱封鎖的裝置報告

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>移除不符合預期可靠的度量單位的改進動作

若要確保 Microsoft 安全分數才有意義，以及改進的每一個動作是可以測量且可靠，我們會移除下列改進動作。

- 開啟稽核資料記錄
- 探索風險並不相容的陰影 IT 應用程式
- 檢閱權限 & 封鎖風險 OAuth 應用程式連線至您的環境
- 在 SharePoint online 的文件庫設定版本設定

### <a name="mfa-improvement-action-updates"></a>MFA 改進動作更新

若要反映適用於企業以確保 upmost 安全性時，套用原則可搭配其業務需求，Microsoft 安全分數會移除三個改進動作圍繞多重要素驗證，並新增兩個。

會移除三個：

- 登錄所有使用者的多重要素驗證
- 需要 MFA 的所有使用者
- 需要 MFA 的 Azure AD 特殊權限角色

新增新的改進動作：

- 確定所有的使用者可以完成的安全存取多重要素驗證
- 需要 MFA 的系統管理角色

 這些新的改進動作將會需要透過您的目錄中註冊您的使用者或系統管理員針對多重要素驗證 (MFA)，以及建立正確的一組原則符合貴組織的需求。 主要目標是有彈性，同時確保所有使用者和系統管理員可以驗證與多重因素或風險式身分識別驗證提示。 可能需要的表單具有多個範圍的決策或設定安全性的預設值 （即將年 3 月 16），可讓 Microsoft 決定何時 MFA 的挑戰使用者套用的原則。

### <a name="removing-review-improvement-actions"></a>移除 「 檢閱 」 改進動作

之一的安全分數原則是分數應依照標準化預定且更容易與相關。 具有不是可以測量或可採取行動的改進動作具有已造成混淆。 一個 Microsoft 安全分數僅合理時的每個建議有清除影響分數。 檢閱改進動作不會測量至其他改進動作為相同的標準。  

基於這些理由，將會暫時移除所有需要檢閱頻率的改進動作。 在您的組件上不需要採取任何動作。

## <a name="march-16th-2020"></a>16 2020 年 3 月

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>移除不符合預期可靠的度量單位的改進動作

若要確保 Microsoft 安全分數才有意義，以及改進的每一個動作是可以測量且可靠，我們會移除下列改進動作。

- 商務用 OneDrive 中儲存使用者文件
- 設定 Office 365 ATP 安全附件原則
- 若要確認 Url 設定 Office 365 安全連結
- 不允許 [信箱委派]
- 允許匿名來賓共用網站和文件的連結

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Azure AD 改進動作支援安全的預設值

Microsoft 安全分數會更新改進動作來支援[Azure AD 中預設的安全性](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)，方便大家來協助保護您的組織使用的常見的攻擊的預先設定的安全性設定。

它會影響下列改進動作：

- 確定所有的使用者可以完成的安全存取多重要素驗證
- 需要 MFA 的系統管理角色
- 啟用原則，以封鎖舊版驗證
