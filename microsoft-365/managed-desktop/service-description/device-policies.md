---
title: 裝置設定
description: 了解套用至 Microsoft 受管理的桌上型電腦裝置的預設原則。
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: e36c65bab3fa78fc27ee6228e78461b2e6b318dd
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866566"
---
# <a name="device-configuration"></a>裝置設定


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

當佈建新的 Microsoft 受管理的桌上型電腦裝置時，我們確定的右邊的設定，最佳化的 Microsoft 受管理的桌上型電腦是備妥。這包括一組設定為佈建程序的一部分的預設原則。若要避免發生衝突，不應該變更這些原則。 

裝置會送達使用簽章圖像，然後加入的 Azure Active Directory 網域的第一個使用者登入時。裝置將會自動安裝必要的原則和應用程式不需要所需的 IT 介入。

## <a name="why-mdm-over-group-policy"></a>為什麼要選擇 MDM 透過群組原則

有幾個原因，而不是群組原則使用行動裝置管理 (MDM)：

- 安全性-MDM 原則是更安全的現代世界中。群組原則被設計來搭配最內部 identity 時 MDM 設計旨在與雲端身分識別管理 (Azure Active Directory) 的最佳。
- 可靠性-MDM 原則提供更可靠的原則部署。此外，MDM 設定會覆寫群組原則物件 (GPO) 原則。開頭 Windows 10、 版本 1803、 MDM 設定將優先順序透過 「 群組原則 」 值，以支援客戶移至現代管理。 
- 對齊 Microsoft 受管理的桌上型電腦願景-提供更多監視對原則部署與支援群組型方法逐步導入的原則變更為暫停 / 繼續部署時所需的功能與。

如需詳細資訊，請參閱[行動裝置管理](https://docs.microsoft.com/windows/client-management/mdm/)。 

## <a name="default-policies"></a>預設原則

下表重點在於說明裝置佈建期間套用至所有的 Microsoft 受管理的桌上型電腦裝置的預設原則。所有偵測到未核准 Microsoft 受管理的桌上型電腦作業小組由 Microsoft 受管理的桌上型電腦管理物件的變更將會還原。

原則 | 描述
--- | ---
安全性標準 | [Microsoft 安全性基準](https://docs.microsoft.com/windows/device-security/windows-security-baselines)MDM 已針對 Microsoft 受管理的桌上型電腦的所有裝置。此基準線是業界標準設定。公開發行，以及測試，並保留 Microsoft 受管理的桌上型電腦裝置的 Microsoft 安全性專家已檢閱及應用程式保護現代工作場所中。<br><br>若要減輕威脅不斷演變安全性威脅橫向中的，將會更新和部署至每個 Windows 10 功能更新 Microsoft 受管理的桌上型電腦裝置的 Microsoft 安全性基準。<br><br>如需詳細資訊，請參閱[Windows 10 的安全性標準](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)。
Microsoft 受管理的桌上型電腦建議的安全性範本 | 一組的安全性基準最佳化的使用者經驗的建議變更。 這些變更都記載在[安全性 Addendum](#security-addendum)。更新原則 addendum 發生為所需的基礎。  
裝置規範 | 根據預設會針對 Microsoft 受管理的桌上型電腦的所有裝置所設定這些原則。裝置會報告為非符合其中一個下列安全性條件不符合時：<br>-啟用 BitLocker 裝置加密來保護裝置上的資料。如需詳細資訊，請參閱[概觀 （英文） 的 BitLocker 裝置加密的 Windows 10。](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-安全開機啟用並強制執行，以驗證裝置上的韌體影像之前他們可以執行。如需詳細資訊，請參閱[安全開機及裝置加密概觀 （英文)。](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>Microsoft 受管理的桌上型電腦裝置需要登入的密碼。
更新部署 | 用於 Windows Update for Business (WUfB) 執行逐步的軟體更新部署。IT 系統管理員無法修改部署群組原則設定。如需有關群組為基礎的部署的詳細資訊，請參閱[如何處理更新](../working-with-managed-desktop/updates.md)。
遙測 | 裝置會設為下已知的商業識別碼將增強的診斷資料提供給 Microsoft。Microsoft 受管理的桌上型電腦的一部分，IT 系統管理員可以變更這些設定。客戶的一般資料保護法規 (GDPR) 區域、 使用者可能會降低的診斷資料所提供的層級，但是會減少的服務。例如，Microsoft 受管理的桌上型電腦將無法收集必要上設定和原則以最佳服務效能與安全性需求中重複的資料。如需詳細資訊，請參閱[您組織中的設定 Windows 診斷資料。](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

 ## <a name="security-addendum"></a>安全性 addendum

 本節概要說明要部署為其他標準 Microsoft 受管理的桌上型電腦原則的原則。標準的原則會列於[預設原則](#default-policies)。此設定的設計與財務服務和高度規範產業記住： 最佳化的最安全的轉變成為，同時維持使用者產能。

 ### <a name="additional-security-policies"></a>其他安全性原則

 這些原則會新增至增加高度規範 industries 的安全性。 
 - **應用程式允許清單**： 必須受到組織在 Microsoft 受管理的桌上型電腦裝置上執行信任的應用程式。這可鎖定的環境。需要 onboarded 任何應用程式必須傳達給 Microsoft 受管理的桌上型電腦作業小組。如需詳細資訊，請參閱[Windows 防禦者裝置 Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide)。
 - **安全性監視**： Microsoft 將監視裝置使用[Windows 防禦者進階威脅保護](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)。如果威脅偵測到，Microsoft 將通知客戶、 隔離裝置，並從遠端修正問題。 

