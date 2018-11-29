---
title: 裝置設定
description: 了解套用至 Microsoft 受管理的桌上型電腦裝置的預設原則。
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 5a97f44641ac38a8785bde66819dbfffffee946d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866566"
---
# <a name="device-configuration"></a>裝置設定


<!--This topic is the target for a "Learn more" link in the Enterprise Agreement (aka.ms/dev-config); do not delete.-->

<!-- Device configuration and Security Addendum-->

當佈建新的 Microsoft 受管理的桌上型電腦裝置時，我們確定的右邊的設定，最佳化的 Microsoft 受管理的桌上型電腦是備妥。這包括一組預設原則設定為佈建程序的一部分。若要避免發生衝突，不應該變更這些原則。 

裝置會送達使用簽章圖像，然後加入的 Azure Active Directory 網域的第一個使用者登入時。裝置將會自動安裝必要的原則和應用程式不需要所需的 IT 介入。

## <a name="why-mdm-over-group-policy"></a>為什麼要選擇 MDM 透過群組原則

有幾個原因，而不是群組原則使用行動裝置管理 (MDM)：

- 安全性-MDM 原則是更安全的現代世界中。群組原則設計目的在於運作起來最順暢與內部部署的身分識別。設計旨在與雲端身分識別管理 (Azure Active Directory (Azure AD)) 的最佳 MDM。
- 可靠性-MDM 原則提供更可靠的原則部署。MDM 設定會覆寫群組原則物件 (GPO) 原則。啟動與 Windows 10、 版本 1803、 MDM 設定將優先順序透過 「 群組原則 」 值。此為 [客戶移至現代管理支援。 
- 對齊 Microsoft 受管理的桌上型電腦願景-更妥善地原則部署在監控。支援逐步導入的原則變更響鈴型方法具有為暫停 / 繼續部署時所需的功能。

## <a name="default-policies"></a>預設原則

此表重點預設原則套用至所有的 Microsoft 受管理的桌上型電腦裝置裝置佈建期間。若要避免發生衝突，不應該變更這些原則。所有偵測到未核准 Microsoft 受管理的桌上型電腦作業小組由 Microsoft 受管理的桌上型電腦管理物件的變更將會還原。

原則 | 描述
--- | ---
安全性標準 | [Microsoft 安全性基準](https://docs.microsoft.com/windows/device-security/windows-security-baselines)MDM 已針對 Microsoft 受管理的桌上型電腦的所有裝置。此基準線是業界標準設定。公開發行，以及測試，並保留 Microsoft 受管理的桌上型電腦裝置的 Microsoft 安全性專家已檢閱及應用程式保護現代工作場所中。<br><br>若要減輕威脅不斷演變安全性威脅橫向中的，將會更新和部署至每個 Windows 10 功能更新 Microsoft 受管理的桌上型電腦裝置的 Microsoft 安全性基準。<br><br>如需詳細資訊，請參閱[Windows 10 的安全性標準](https://blogs.technet.microsoft.com/secguide/2017/10/18/security-baseline-for-windows-10-fall-creators-update-v1709-final/)。
Microsoft 受管理的桌上型電腦建議的安全性範本 | 一組的安全性基準最佳化的使用者經驗的建議變更。 這些變更都記載在[安全性 Addendum](#security-addendum)。更新原則 addendum 發生為所需的基礎。  
裝置規範 | 根據預設會針對 Microsoft 受管理的桌上型電腦的所有裝置所設定這些原則。裝置會報告為非符合其中一個下列安全性條件不符合時：<br>-啟用 BitLocker 裝置加密來保護裝置上的資料。如需詳細資訊，請參閱[概觀 （英文） 的 BitLocker 裝置加密的 Windows 10。](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)<br>-安全開機啟用並強制執行，以驗證裝置上的韌體影像之前他們可以執行。如需詳細資訊，請參閱[安全開機及裝置加密概觀 （英文)。](https://docs.microsoft.com/windows-hardware/drivers/bringup/secure-boot-and-device-encryption-overview)<br>-若要存取 Microsoft 受管理的桌上型電腦裝置所需的密碼。
更新部署 | 用於 Windows Update for Business (WUfB) 執行逐步的軟體更新部署。IT 系統管理員無法修改部署鈴響原則設定。如需有關響鈴為基礎的部署的詳細資訊，請參閱[如何處理更新](../working-with-managed-desktop/updates.md)。
遙測 | 裝置會設為 [已知的商業識別碼將增強診斷資料提供給 Microsoft。客戶的一般資料保護法規 (GDPR) 區域、 使用者可能會降低診斷資料所提供的層的級。您可以自訂，但是會減少的服務。如需詳細資訊，請參閱[您組織中的設定 Windows 診斷資料。](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enhanced-level)

## <a name="advanced-policies"></a>進階的原則

 這些是可以設定為更安全/鎖定環境、 高度規範 industries 的其他原則。

 原則 | 描述
 --- | ---
 進階的功能 | Windows 資訊保護 (WIP) 與 Azure 資訊保護 (AIP) 可用來保護企業資料只允許存取特定個人或應用程式/服務的子集。如需詳細資訊，請參閱<br>- [保護使用 Windows 資訊保護貴企業之資料](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip)<br>- [Azure 資訊保護用戶端管理員手冊](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)<br>- [受管理的 Microsoft 桌面安全性 Addendum](#security-addendum)

 ## <a name="security-addendum"></a>安全性 addendum

 本節概要說明要部署為其他標準 Microsoft 受管理的桌上型電腦原則的原則。標準的原則會列於[預設原則](#default-policies)。此設定的設計與財務服務和高度規範產業記住： 最佳化的最安全的轉變成為，同時維持使用者產能。

已發佈**的安全性標準**變更，會停用 [[**不要顯示 UI 網路選取項目**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowslogon#windowslogon-dontdisplaynetworkselectionui)] 設定。

 ### <a name="additional-security-policies"></a>其他安全性原則

 這些原則會新增至增加高度規範 industries 的安全性。 
 - **應用程式允許清單**： 必須受到組織在 Microsoft 受管理的桌上型電腦裝置上執行信任的應用程式。這可鎖定的環境。需要 onboarded 任何應用程式必須傳達給 Microsoft 受管理的桌上型電腦作業小組。如需詳細資訊，請參閱[Windows 防禦者裝置 Guard](https://docs.microsoft.com/windows/device-security/device-guard/device-guard-deployment-guide)。
 - **安全性監視**： Microsoft 將監視裝置使用[Windows 防禦者進階威脅保護](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)。如果威脅偵測到，Microsoft 將通知客戶、 隔離裝置，並從遠端修正問題。 
 - **利用 Guard**： 我們將確認 Microsoft 受管理的桌上型電腦裝置一定安全的最新的安全性更新、 作業系統與應用程式] 使用 [ [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)。攻擊 Guard 會設定為下列值：

 設定 | 原則
 --- | ---
 標幟竊取 Windows 本機安全性授權子系統的認證 | 僅用於審核
 將插入其他程序的 office 應用程式 | 僅用於審核
 Office 應用程式/巨集建立可執行檔內容 | 封鎖
 Office 相關應用程式啟動子程序 | 僅用於審核
 從 Office 巨集程式碼 Win32 匯入 | 封鎖
 模糊化的 js/vbs/ps/巨集程式碼 | 封鎖
 從網際網路 （無例外） 下載 Js/vbs 執行承載 | 封鎖
 從 PSExec 及 WMI 命令的程序建立 | 僅用於審核
 不受信任與不帶正負號 USB 從執行的程序 | 封鎖
 不符合普遍性、 保留時間或信任的清單準則的可執行檔 | 僅用於審核
 執行可執行檔的內容放從電子郵件 | 封鎖
 進階的 ransomware 保護 | 僅用於審核









