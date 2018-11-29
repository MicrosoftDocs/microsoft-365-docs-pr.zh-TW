---
title: Microsoft 受管理的桌上型電腦作業和監控
description: ''
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 00bdc95c191ce16be219cf0dc251f72eaf054e22
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866293"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft 受管理的桌上型電腦作業和監控

<!-- Operations and monitoring: -->


## <a name="change-management"></a>變更管理

查看 Microsoft 及客戶將共用 Microsoft 受管理的桌上型電腦服務的變更管理。線上服務與內部伺服器或用戶端比較不同的責任。 

### <a name="change-process-overview"></a>變更程序概觀 （英文)

以下是如何變更程序 Microsoft 及 customers 間共用的摘要。 



<table>
<tr><th></th><th><p>Microsoft 將會：</p></th><th><p>客戶將會：</p></th></tr>
<tr><td>變更之前</td><td><ul><li>通知客戶事先需要系統管理員巨集指令的變更 5 天。</li><li>緊急變更套用減輕前通知。</li></ul></td><td><ul><li>閱讀並瞭解通知電子郵件。</li><li>確認並核准、 需要時。</li></ul></td></tr><tr><td>變更期間</td><td><ul><li>部署 Windows 10 與 Office 的變更、 版本所需的安全性與非安全性更新。</li><li>監視任何未預期問題的遙測和支援擴大。</li></ul></td><td><ul><li>管理內部變更管理程序。</li><li>建立支援要求，如有需要。</li></ul></td></tr><tr><td>變更之後</td><td><ul><li>收集客戶意見反應以改善首度發行未來的變更。</li><li>監視任何未預期問題的遙測和支援擴大。</li></ul></td><td><ul><li>閱讀並瞭解通知電子郵件。</li><li>提供一般的意見反應及特定的意見反應在系統管理工具的意見反應。</li><li>訓練使用者以提供特定應用程式的意見反應在 Office 應用程式中使用 Windows 意見反應中心 」 及 「 Smile] 按鈕。</li></ul></td></tr>
<table> 






### <a name="change-types"></a>變更類型

有數種經常上的服務所做的變更。這些變更和客戶負責動作的通訊通道而異。

可預期下列類型的變更：

變更類型 | 通知 | 客戶巨集指令
--- | --- | ---
更新及新的服務元件的功能 | 電子郵件 | -傳達給使用者的變更<br><br> -依照需要 Microsoft 法案<br><br> 48 小時內必須採取動作
安全性每月的更新及基準設定更新 | 電子郵件、 安全性公告或一般弱點及曝光度 (CVE) 的項目 | -每月安全性更新將會使用我們的[更新管理策略](updates.md)來部署。<br><br> -設定以降低威脅會部署至整個組織，以保護組織。（這似乎不在客戶動作）
品質的更新，包括 hotfix、 服務更新與非安全性影響基準原則 | 電子郵件 | 會通知時所需。
緊急更新： service、 設定或軟體更新需要的以減輕：<br><br> 重要安全性風險<br><br> -可能遺失資料<br><br> 存取遙測資料 Microsoft 受管理的桌上型電腦裝置管理 | 會通知時所需。

## <a name="standard-operating-procedures"></a>標準作業系統程序

此服務會實作及 microsoft 21vianet 您對執行其他管理活動環境中。Microsoft 負責察覺 Microsoft 受管理的桌上型電腦特定安裝、 設定及作業。 

內部部署產品的組織採用上的管理作業以及設定活動的所有責任。

Categories |    動作
--- | ---
服務帳戶 |  Microsoft 將會：<br><br> -實作、 安全地儲存和管理認證<br><br> -通訊未經授權的存取或使用這些認證安全性作業小組<br><br><br><br>客戶將會：<br><br> -開啟之資訊的支援要求與 Microsoft 受管理的桌上型電腦作業時規劃可能會影響帳戶變更<br><br> -不將原則、 多重要素驗證、 設定格式化的條件 access 或應用程式部署指派給 Microsoft 受管理的桌上型電腦服務帳戶<br><br> -不會重設密碼或使用的認證<br><br> -開啟 Microsoft 受管理的桌上型電腦作業嚴重度 C 支援要求如果可疑活動觀察 Intune 或 Azure 稽核記錄檔中，這些服務帳戶的相關
裝置群組 | Microsoft 將會：<br><br> -實作和管理 Microsoft 受管理的桌上型電腦群組內的裝置的成員資格<br><br> -使用 Microsoft 受管理的桌上型電腦群組管理的工作分派與裝置的設定及更新版本<br><br><br><br>客戶將會：<br><br> -開啟資訊性支援要求與 Microsoft 受管理的桌上型電腦作業時規劃可能會影響群組的變更<br><br> -不修改任何 Microsoft 受管理的桌上型電腦群組的成員資格<br><br> -僅使用群組來指派服務，例如 VPN、 Windows Hello 商務或電子郵件加密或公司 Wi-fi 設定檔設定的公司憑證<br><br> -共同撰寫管理所在、 部署 Configuration Manager 用戶端時明確排除 Microsoft 受管理的桌上型電腦的所有群組
Policies |  Microsoft 將會：<br><br> -實作和管理控管設定裝置的狀態服務內的 Microsoft 受管理的桌上型電腦原則<br><br> -將更新部署至原則或 Windows、 逐漸使用裝置群組<br><br> -明確排除目標非的 Microsoft 受管理的桌上型電腦群組<br><br><br><br>客戶將會：<br><br> -開啟資訊性支援票證 Microsoft 受管理的桌上型電腦作業規劃可能會影響所需的設定裝置的狀態變更時<br><br> -無法編輯或 Microsoft 受管理的桌上型電腦原則指派給裝置或不受管理的 Microsoft 受管理的桌上型電腦服務的使用者
Windows Defender 進階威脅防護 | Microsoft 將會：<br><br> -監視及調查 Microsoft 受管理的桌上型電腦服務範圍內的裝置<br><br><br><br>客戶將會：<br><br> -開啟資訊性支援票證 Microsoft 受管理的桌上型電腦作業時規劃可能會影響 Microsoft 受管理的桌面安全性作業中心的監控或調查功能的變更
商務用 Microsoft Store |  Microsoft 將會：<br><br> -設定及維護 Microsoft 受管理的桌上型電腦服務的 Windows 自動駕駛儀上設定檔<br><br><br><br>客戶將會：<br><br> -開啟資訊性支援票證 Microsoft 受管理的桌上型電腦作業時規劃開啟可能會影響存放區權限或修改 Microsoft 受管理的桌上型電腦 Windows 自動駕駛儀上設定檔的變更<br><br> -不修改 Microsoft 受管理的桌上型電腦 Windows 自動駕駛儀上設定檔的組態或新增/移除已指派的裝置
憑證 |  客戶將會：<br><br> -開啟 Microsoft 受管理的桌上型電腦作業 60 天前任何憑證過期資訊性支援票證<br><br> -更新為設定所需的所有憑證： 憑證設定檔、 VPN 設定檔及 Wi-fi 設定檔



## <a name="device-wipe-with-factory-reset"></a>與原廠重設裝置抹除

受管理的桌面作業小組可以執行原廠重設需要可建立映像的 Microsoft 受管理的桌上型電腦管理裝置上。如果您需要將裝置提供給不同的員工、 或員工離職，這是很有幫助。 

有幾個需求：

- 客戶的租用戶系統管理員必須提交服務要求
- 我們需要裝置的電腦名稱
- 使用者帳戶必須是在之前我們執行重設的 Azure AD

受管理的桌上型電腦作業小組將會：

- 查閱中 Intune 的裝置名稱
- 傳送原廠重設之裝置的命令

>[!NOTE]
>請勿移除的使用者帳戶從之前的原廠重設的 Azure AD。如果使用者不在 Azure AD，Intune 無法傳送原廠重設之裝置的命令。 

裝置會開機成 OOBE，和所有預先安裝的應用程式和設定會套用一次。裝置的使用者必須提供資訊再次的初始設定。 

當已重設之裝置時，您可以到另一個人給予您組織中。無放使用者資料或企業資料將會在裝置上。下一個使用者會逐一相同的舊的人員沒有使用新的 Microsoft 受管理的桌上型電腦裝置的程序。

BitLocker 會在此程序中的資料安全性的重要元件。使用 Microsoft 受管理的桌上型電腦裝置上的 BitLocker 加密資料的磁碟機上仍會保留安全即使原廠重設已套用至裝置。磁碟機的任何資料不會提供給下一個使用者的裝置。如需詳細資訊，請參閱[BitLocker 概觀 （英文）](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)。

如需詳細資訊，請參閱[原廠重設裝置](https://docs.microsoft.com/intune/devices-wipe#factory-reset-a-device)。 
