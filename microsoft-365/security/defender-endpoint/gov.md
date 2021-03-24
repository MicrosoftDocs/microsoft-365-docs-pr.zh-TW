---
title: 適用于美國政府客戶的 Microsoft Defender for Endpoint
description: 瞭解適用于美國政府客戶需求和功能的 Microsoft Defender for Endpoint
keywords: 政府，gcc，high，必要條件，功能，defender，defender atp，mdatp，端點，dod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 31928deddc2a504cc0b6c91af287e4977791c920
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059196"
---
# <a name="microsoft-defender-for-endpoint-for-us-government-customers"></a>適用于美國政府客戶的 Microsoft Defender for Endpoint

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Microsoft Defender for the us the us the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the the

這種服務可供 GCC、GCC 高階及 DoD 客戶使用，並以與商業性版本相同的預防、偵測、調查和修正功能為基礎。 不過，此服務的功能可用性有一些差異。

> [!NOTE]
> 如果您是在商業性使用 Defender for Endpoint 的 GCC 客戶，請參閱公用檔頁面。

## <a name="licensing-requirements"></a>授權需求
適用于美國政府客戶的 microsoft Defender for Endpoint 需要下列其中一項 Microsoft 大量授權提供：

### <a name="desktop-licensing"></a>桌面授權
GCC | GCC High | DoD
:---|:---|:---
Windows 10 企業版 E5 GCC | 適用于 GCC 高版的 Windows 10 企業版 E5 | DOD 的 Windows 10 企業版 E5
| | 適用于 GCC 高版的 Microsoft 365 E5 | 
| | 適用于 GCC 高版的 Microsoft 365 G5 安全性 | 
Microsoft Defender for Endpoint-GCC | 適用于 GCC 高版的 Microsoft Defender for Endpoint | DOD 的 Microsoft Defender 端點

### <a name="server-licensing"></a>伺服器授權
GCC | GCC High | DoD
:---|:---|:---
Microsoft Defender for Endpoint Server GCC | 適用于 GCC 高版的 Microsoft Defender for Endpoint Server | 用於 DOD 的 Microsoft Defender for Endpoint Server
伺服器的 Azure Defender | 伺服器的 Azure Defender-政府 | 伺服器的 Azure Defender-政府

> [!NOTE]
> DoD 授權只會在 DoD 正式供貨時提供。

<br>

## <a name="portal-urls"></a>入口網站 URLs
以下是適用于美國政府客戶的 Microsoft Defender for Endpoint 入口 URLs：

客戶類型 | 入口網站 URL
:---|:---
GCC | https://gcc.securitycenter.microsoft.us
GCC High | https://securitycenter.microsoft.us
DoD (預覽)  | https://securitycenter.microsoft.us

<br>

## <a name="endpoint-versions"></a>端點版本

### <a name="standalone-os-versions"></a>獨立作業系統版本
支援下列作業系統版本：

作業系統版本 | GCC | GCC High | DoD (預覽) 
:---|:---|:---|:---
Windows 10，version 20H2 (搭配 [KB4586853](https://support.microsoft.com/help/4586853))  | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg) | ![是](images/svg/check-yes.svg)
Windows 10，版本 2004 (，含 [KB4586853](https://support.microsoft.com/help/4586853))  | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows 10，版本 1909 (，含 [KB4586819](https://support.microsoft.com/help/4586819))  | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows 10，版本 1903 (，含 [KB4586819](https://support.microsoft.com/help/4586819))  | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows 10，版本 1809 (，含 [KB4586839](https://support.microsoft.com/help/4586839))  | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows 10，版本 1803 (，含 [KB4598245](https://support.microsoft.com/help/4598245))  | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows 10，版本1709 | ![否](/security/defender-endpoint/images/svg/check-no)<br>附注：不支援 | ![Yes ](/security/defender-endpoint/images/svg/check-yes) With [KB4499147](https://support.microsoft.com/help/4499147)<br>附注：已 [過時](https://docs.microsoft.com/lifecycle/announcements/revised-end-of-service-windows-10-1709)，請升級 | ![否](/security/defender-endpoint/images/svg/check-no)<br>附注：不支援
Windows 10、版本1703及更早版本 | ![否](/security/defender-endpoint/images/svg/check-no)<br>附注：不支援 | ![否](/security/defender-endpoint/images/svg/check-no)<br>附注：不支援 | ![否](/security/defender-endpoint/images/svg/check-no)<br>附注：不支援
使用 [KB4586839](https://support.microsoft.com/help/4586839)) 的 Windows Server 2019 ( | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2016 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2012 R2 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2008 R2 SP1 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows 8.1 企業版 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows 8 Pro | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows 7 SP1 企業版 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows 7 SP1 Pro | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Linux | ![否](/security/defender-endpoint/images/svg/check-no) 在開發 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發
macOS | ![否](/security/defender-endpoint/images/svg/check-no) 在開發 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發
Android | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作
iOS | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作

> [!NOTE]
> 若已指定修補程式，必須在裝置上架之前部署，才能將 Defender 設定為正確的環境。

> [!NOTE]
> 使用 [Microsoft Monitoring Agent](configure-server-endpoints.md#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)嘗試使用 windows 10 或 windows Server 2019 之前的板載 windows 裝置？ 如果使用 [設定向導](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard)，或是使用 [命令列](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line) 或 [腳本](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation) -將 "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" 參數設定為1，則需要在 "Azure CLOUD" 底下選擇「azure US 政府」。

### <a name="os-versions-when-using-azure-defender-for-servers"></a>針對伺服器使用 Azure Defender 時的作業系統版本
[針對伺服器使用 Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp)時，可支援下列作業系統版本：

作業系統版本 | GCC | GCC High | DoD (預覽) 
:---|:---|:---|:---
Windows Server 2016 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2012 R2 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Windows Server 2008 R2 SP1 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)

<br>

## <a name="required-connectivity-settings"></a>必要的連線設定
如果 Proxy 或防火牆在預設情況下封鎖所有流量，並且只允許特定網域通過，請將可下載工作表中列出的網域新增到允許的網域清單中。

下列可供下載的試算表會列出您網路必須能夠連線的服務及其相關 URLs。 請確認沒有防火牆或網路篩選規則可拒絕這些 URLs 的存取權，或專門為使用者建立 *允許* 規則。

網域清單的試算表 | 描述
:-----|:-----
![Microsoft Defender for Endpoint URLs 試算表的縮圖影像](images/mdatp-urls.png)<br/> | 服務位置、地理位置和作業系統的特定 DNS 記錄試算表。 <br><br>[在這裡下載試算表。](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 

如需詳細資訊，請參閱 [Configure device proxy And Internet connectivity settings](configure-proxy-internet.md)。

> [!NOTE]
> 試算表也包含商用 URLs，請務必檢查「US .Gov」索引標籤。 <br> 篩選時，請查看標示為「US .Gov」的記錄，以及 geography 欄底下的特定雲端。

<br>

## <a name="api"></a>API
您必須使用下列 URIs，而不是 [API 檔](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro)中列出的公用 URIs：

端點類型 | GCC |  (預覽) 的 GCC High & DoD
:---|:---|:---
登錄 | `https://login.microsoftonline.com` | `https://login.microsoftonline.us`
適用于 Endpoint API 的 Defender | `https://api-gcc.securitycenter.microsoft.us` | `https://api-gov.securitycenter.microsoft.us`
SIEM | `https://wdatp-alertexporter-us.gcc.securitycenter.windows.us` | `https://wdatp-alertexporter-us.securitycenter.windows.us`

<br>

## <a name="feature-parity-with-commercial"></a>具有商業性的功能同位
「！的 Defender」已具備商務用產品的完整同位。 雖然我們的目標是將所有商業功能提供給我們的美國政府客戶，但仍有一些尚未提供的功能可供您選擇。

以下是2021年2月的已知空隙：

功能名稱 | GCC | GCC High | DoD (預覽) 
:---|:---|:---|:---
自動化調查和修正： Live 回應 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
自動化調查和修正：回應 Office 365 警示 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作
電子郵件通知 | ![否](/security/defender-endpoint/images/svg/check-no) 正在推出 | ![否](/security/defender-endpoint/images/svg/check-no) 正在推出 | ![否](/security/defender-endpoint/images/svg/check-no) 正在推出
評估實驗室 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
管理和 APIs：裝置健康情況與符合性報告 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
管理和 APIs：整合協力廠商產品 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發
管理和 APIs：資料流程 API | ![是](/security/defender-endpoint/images/svg/check-yes) | ![否](/security/defender-endpoint/images/svg/check-no) 在開發 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發
管理和 APIs：威脅防護報告 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
威脅 & 弱點管理 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
威脅分析 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Web 內容篩選 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發
整合： Azure Sentinel | ![是](/security/defender-endpoint/images/svg/check-yes) | ![否](/security/defender-endpoint/images/svg/check-no) 在開發 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發
整合： Microsoft Cloud App Security | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作
整合： Microsoft 合規性管理員 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作
整合： Microsoft Defender 身分識別 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作
整合： Microsoft Defender for Office 365 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作
整合： Microsoft 端點 DLP | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作
整合： Microsoft Intune | ![是](/security/defender-endpoint/images/svg/check-yes) | ![否](/security/defender-endpoint/images/svg/check-no) 在開發 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發
整合： Microsoft Power 自動化 & Azure 邏輯應用程式 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![否](/security/defender-endpoint/images/svg/check-no) 在開發 | ![否](/security/defender-endpoint/images/svg/check-no) 在開發
整合：商務用 Skype/小組 | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes) | ![是](/security/defender-endpoint/images/svg/check-yes)
Microsoft 威脅專家 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作 | ![否](/security/defender-endpoint/images/svg/check-no) 在工程處理積壓工作