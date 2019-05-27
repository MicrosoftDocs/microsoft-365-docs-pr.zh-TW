---
title: 裝置設定
description: 了解套用至 Microsoft 受管理的電腦裝置的預設原則。
keywords: Microsoft 受管理的電腦，Microsoft 365 服務，文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9a7d2130775c9c5d99bba711254fc0f0ce540947
ms.sourcegitcommit: 3294b97a20ae0e5eb8ce6187310cc96b5050a215
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2019
ms.locfileid: "34422209"
---
# <a name="device-configuration"></a>裝置設定


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

當正在佈建在新的 Microsoft 受管理的電腦裝置時，我們確保正確設定，Microsoft 受管理的電腦，最適合就地。 這包括一組的預設原則，設定為上架程序的一部分。 若要避免發生衝突，不應該變更這些原則。 

裝置會送達使用簽章圖像，然後加入 Azure Active Directory 網域，當第一個使用者登入。 裝置會自動將會安裝必要的原則和應用程式不需要所需的 IT 介入。

## <a name="why-mdm-over-group-policy"></a>為什麼 MDM 透過群組原則

有幾個原因會使用行動裝置管理 (MDM)，而不是群組原則：

- 安全性-MDM 原則是更安全的新式世界。 群組原則被設計來運作起來最順暢與內部部署身分識別時 MDM 專為最佳與雲端身分識別管理 (Azure Active Directory)。
- 可靠性-MDM 原則提供更可靠的原則部署。 此外，MDM 設定覆寫群組原則物件 (GPO) 原則。 啟動與 Windows 10，版本 1803，MDM 設定將的優先順序透過 [群組原則的值，其支援客戶移至現代化的管理。 
- Microsoft 受管理電腦願景對齊-提供更多監視原則部署並支援群組為主的方法，逐步推行原則變更為暫停 / 繼續部署時所需的功能。

如需詳細資訊，請參閱[行動裝置管理](https://docs.microsoft.com/windows/client-management/mdm/)。 

## <a name="default-policies"></a>預設原則

此表格會醒目提示會套用至所有的 Microsoft 受管理的電腦裝置，裝置佈建期間的預設原則。 所有偵測到未核准由 Microsoft 受管理的桌上型電腦作業小組由 Microsoft 受管理的電腦物件的變更將會還原。

原則 | 描述
--- | ---
[比較基準安全性 | [Microsoft 安全性基準](https://docs.microsoft.com/windows/device-security/windows-security-baselines)MDM 會針對所有 Microsoft 受管理的電腦裝置。 此基準是業界標準的組態。 它公開發行，以及測試，並已檢閱過的 Microsoft 安全性專家將 Microsoft 受管理的電腦裝置和應用程式安全的現代化工作場所。 <br><br>若要降低威脅不斷演變安全性威脅橫向中的，會更新並部署至 Microsoft 受管理的電腦裝置的每個 Windows 10 功能更新的 Microsoft 安全性基準。<br><br>如需詳細資訊，請參閱 <<c0>適用於 Windows 10 安全性基準。
Microsoft 受管理電腦所建議的安全性範本 | 一系列安全性基準來最佳化使用者經驗的建議變更。  這些變更會記錄在[安全增訂版](#security-addendum)。 在需要時，就會更新原則增訂版。  
更新部署 | 使用商務 (WUfB) 的 Windows 更新，來執行逐步部署軟體更新。 IT 系統管理員無法修改部署群組原則設定。 如需有關群組為基礎的部署的詳細資訊，請參閱 <<c0>更新的處理方式。
診斷資料 | 裝置會設定增強的診斷資料提供給 Microsoft 下一個已知的商業識別碼。 Microsoft 受管理電腦的一部分，IT 系統管理員不能變更這些設定。 客戶的一般資料保護規定 (GDPR) 區域，使用者可以降低程度診斷資料提供，但會減少的服務。 例如，Microsoft 受管理電腦將無法收集來逐一查看上設定和原則，以最佳服務效能與安全性需求所需的資料。 如需詳細資訊，請參閱[貴組織中的設定 Windows 診斷資料。](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>安全性增訂版

 本節概述的原則，將會部署為其他標準 Microsoft 受管理電腦原則。 標準原則會列在 [[預設原則](#default-policies)。 此組態的設計與財務服務和高管制產業記住： 最佳化最安全的轉變成為，同時保有使用者產能。

 ### <a name="additional-security-policies"></a>額外的安全性原則

 若要提高安全性針對高管制產業新增這些原則。 
 - **應用程式允許清單**： 應用程式必須受到 Microsoft 受管理的電腦裝置上執行組織的信任。 此提供的鎖定的環境。 必須是上架任何應用程式必須向 Microsoft 受管理的桌上型電腦作業小組通訊。 如需詳細資訊，請參閱 < <b0>Windows Defender 裝置防護</b0>。
 - **安全性監視**： Microsoft 會監視使用[Windows Defender 進階威脅防護](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)的裝置。 如果偵測到威脅，Microsoft 將會通知客戶、 隔離裝置，並修正此問題： 從遠端。 
 - **停用 PowerShell V2**: Microsoft 已在 2017 年 8 月取代 PowerShell V2。 Microsoft 受管理電腦的所有裝置上已停用此功能。 如需有關此變更的詳細資訊，請參閱 < <b0>Windows PowerShell 2.0 deprecation </b0>。
