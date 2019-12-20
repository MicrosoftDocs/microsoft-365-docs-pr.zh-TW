---
title: 階段 3：Windows 10 企業版基礎結構允出準則
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: 03/05/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: 請確定您的組態符合 Windows 10 企業版的 Microsoft 365 企業版準則。
ms.openlocfilehash: d51392572c78edb1a21f5edc3229057b9af3f514
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801218"
---
# <a name="phase-3-windows-10-enterprise-infrastructure-exit-criteria"></a>階段 3：Windows 10 企業版基礎結構允出準則

![階段 3：Windows 10 企業版](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

請確定您的 Windows 10 企業版基礎結構符合下列必要準則，而且您已將這些視為選擇性準則。

<a name="crit-windows10-step1"></a>
## <a name="required-your-microsoft-365-domains-are-added-and-verified"></a>必要：您的 Microsoft 365 網域已新增並經過驗證

已使用您的網際網路網域名稱 (例如 contoso.com) 設定 Office 365 和 Intune 訂用帳戶的 Azure AD 租用戶 (而不是使用只包含 “onmicrosoft.com” 的網域名稱)。 

如果不這麼做，您會受限於您可設定的驗證方法。例如，通過和同盟驗證無法使用 "onmicrosoft.com" 網域名稱。

如有需要，[步驟 1](windows10-prepare-your-org.md) 可協助您符合這項要求。

## <a name="optional-your-users-are-added-and-licensed"></a>選用：您的使用者已新增並或獲得授權

已新增您的使用者的對應帳戶 (不是直接新增到 Office 365 和 Intune 訂用帳戶的 Azure AD 租用戶，就是從您的內部部署 Active Directory Domain Services (AD DS) 同步處理目錄)。

新增使用者後，您可以將 Microsoft 365 企業版授權指派給他們 (不是直接指派為全域管理員或使用者管理員，就是透過群組成員資格自動指派)。

如有需要，[步驟 1](windows10-prepare-your-org.md) 可協助您使用此選項。

## <a name="optional-diagnostics-are-enabled"></a>選項：已啟用診斷

您已使用群組原則、Microsoft Intune、登錄編輯程式，或在命令提示字元啟用診斷資料設定。

如有需要，[步驟 1](windows10-prepare-your-org.md) 可協助您使用此選項。

<a name="crit-windows10-step2"></a>
## <a name="required-for-in-place-upgrade-created-a-configuration-manager-task-sequence-for-an-operating-system-deployment"></a>就地升級所需：已建立作業系統部署的 Configuration Manager 工作順序

若要啟動 Configuration Manager 工作順序，在執行 Windows 7 或 Windows 8.1 的裝置上進行就地升級，您必須：

- 設定適當的 Windows 診斷資料層級
- 確認升級 Windows 的整備度
- 建立 Configuration Manager 工作順序，其中包含裝置集合和使用 Windows 10 OS 影像的作業系統部署

一旦備妥，您就可以在準備好升級 Windows 的裝置上執行就地升級。若要從 Microsoft 365 企業版獲得最大好處，請儘可能多升級執行 Windows 7 和 Windows 8.1 的裝置。 

每個執行 Windows 10 企業版的裝置都可以享有 Microsoft 365 企業版的整合式解決方案好處。其餘執行 Windows 7 或 Windows 8.1 的裝置無法使用 Windows 10 企業版的雲端相關技術和進階安全性功能。

如有需要，[步驟 2](windows10-deploy-inplaceupgrade.md) 可協助您符合這項要求。

<a name="crit-windows10-step3"></a>
## <a name="required-for-new-devices-configured-windows-autopilot"></a>新裝置所需：已設定 Windows Autopilot

若要使用 Windows Autopilot 在新的裝置上部署及自訂 Windows 10 企業版，您必須：

- 設定適當的 Windows 診斷資料層級
- 設定 Windows Autopilot 的先決條件，其中包含：
   - 裝置註冊和 OOBE 自訂
   - OOBE 公司品牌推廣
   - Microsoft Intune 中的 MDM 自動註冊
   - Windows Autopilot 所用雲端服務的網路連線能力
- 已預先安裝 Windows 10 (版本 1703 或更新版本) 的裝置
- 為您的組織選取 Windows Autopilot Deployment 方案

Windows Autopilot 設定好之後，您就可以使用它來設定和自訂 Windows 10 企業版，以獲得全新的體驗 (OOBE)：

- 新裝置
- 已經在您的組織中完成全新安裝的裝置。 

Windows Autopilot 會設定裝置並將它連線到 Azure AD。

若沒有 Windows Autopilot，您必須手動設定新的裝置，包括 Azure AD 的連線。

如有需要，[步驟 3](windows10-deploy-autopilot.md) 可協助您符合這項要求。

<a name="crit-windows10-step4"></a>
## <a name="optional-you-are-using-windows-analytics-device-health-to-monitor-your-windows-10-enterprise-based-devices"></a>選用：您使用 Windows Analytics 裝置健全狀況來監視您的 Windows 10 企業版裝置

您使用了「透過裝置健全狀況監視裝置的健全狀況」中的資訊，偵測及矯正會影響使用者的問題。快速解決使用者問題可減少支援成本，並向您的使用者證明對 Windows 10 企業版的 IT 承諾，這可協助推動整個組織採用。 

如有需要，[步驟 4](windows10-enable-windows-analytics.md) 可協助您使用此選項。

<a name="crit-windows10-step5a"></a>
## <a name="required-you-are-using-windows-defender-antivirus-or-your-own-antimalware-solution"></a>必要：您是使用 Windows Defender 防毒軟體或自有的反惡意程式碼解決方案

您已部署 Windows Defender 防毒軟體或自有的防毒解決方案來保護執行 Windows 10 企業版的裝置，使其免於遭受惡意軟體攻擊。如果您已部署 Windows Defender 防毒軟體，您便已實作報告方法 (例如 Microsoft Endpoint Configuration Manager 或 Microsoft Intune) 來監視防毒事件和活動。

如有需要，[步驟 5](windows10-enable-security-features.md#windows10-sec-av) 可協助您符合這項要求。

<a name="crit-windows10-step5b"></a>
## <a name="required-you-are-using-windows-defender-exploit-guard"></a>必要：您是使用 Windows Defender 惡意探索防護

您已部署 Windows Defender 惡意探索防護來保護執行 Windows 10 企業版的裝置，使其免於遭到入侵，並已實作報告方法 (例如 Configuration Manager 或 Microsoft Intune) 來監視入侵事件和活動。

如有需要，[步驟 5](windows10-enable-security-features.md#windows10-sec-eg) 可協助您符合這項要求。

<a name="crit-windows10-step5c"></a>
## <a name="required-you-are-using-microsoft-defender-advanced-threat-protection-microsoft-365-e5-only"></a>必要：使用 Microsoft Defender 進階威脅防護 (僅限 Microsoft 365 E5)

您已部署 Microsoft Defender 進階威脅防護 (ATP)，以針對您的網路及執行 Windows 10 企業版的裝置偵測、調查及回應進階威脅。 

此外，您也已整合 Microsoft Defender ATP 與其他工具，以擴充其功能。

如有需要，[步驟 5](windows10-enable-security-features.md#windows10-sec-atp) 可協助您符合這項要求。

## <a name="results-and-next-steps"></a>結果和後續步驟

您的 Windows 10 企業版基礎結構已準備好可以在新裝置上開始安裝，以及在執行舊版 Windows 的裝置上開始就地升級，且您會使用 Windows 10 企業版的重要安全性功能。

|||
|:-------|:-----|
|![階段 4：Office 365 專業增強版](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)| 如果您會遵循 Microsoft 365 企業版的端對端部署階段，則下一個階段是 [Office 365 專業增強版](office365proplus-infrastructure.md)。 |
