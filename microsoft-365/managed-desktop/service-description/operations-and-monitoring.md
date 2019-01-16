---
title: Microsoft 受管理的桌上型電腦作業和監控
description: ''
keywords: Microsoft 受管理的桌上型電腦、 [Microsoft 365 服務、 文件
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 12/18/2018
ms.openlocfilehash: 66945d44df150b5be9af9a9dfe52daa4d7468298
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "26866293"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft 受管理的桌上型電腦作業和監控

<!-- Operations and monitoring: -->


## <a name="change-management"></a>變更管理

提供，達到負載平衡的責任的硬體維護等安全性的服務更新切換到服務提供者 (Microsoft)，而不是客戶 （您） 中。不過，您仍然需要確定該協力廠商] 自訂軟體繼續運作如預期般更新所導時。

內部部署產品的組織會假設所有負責管理變更。

### <a name="balance-of-responsibility"></a>達到負載平衡的責任

責任 | Microsoft 受管理的桌上型電腦服務 | Microsoft 365 用戶端軟體 | 內部部署用戶端和伺服器 | 3rd 廠商及自訂的軟體
----- | ----- | ----- | ----- | -----
提供新功能 | Microsoft | Microsoft | 兩者 | 客戶
測試品質保證的新功能 |  Microsoft | Microsoft | 兩者 | 客戶
溝通新功能的相關事宜 | 兩者 | 兩者 | 兩者 | 客戶
整合自訂軟體 | 兩者 | 兩者 | 客戶 | 客戶
套用安全性更新 | Microsoft | Microsoft | 客戶 | 客戶
維護系統軟體 | Microsoft | Microsoft | 客戶 | 客戶
部署套件 | Microsoft | Microsoft | 客戶 | 客戶


### <a name="change-process-overview"></a>變更程序概觀 （英文)

以下是如何變更程序 Microsoft 及 customers 間共用的摘要。 



<table>
<tr><th></th><th><p>Microsoft 的角色：</p></th><th><p>客戶的角色：</p></th></tr>
<tr><td>變更之前</td><td><ul><li>設定服務變更的期望。</li><li>通知客戶事先需要系統管理員巨集指令的變更 5 天。</li><li>緊急變更套用減輕前通知。</li></ul></td><td><ul><li>了解對變更與通訊的期望。</li><li>閱讀 Microsoft 受管理的桌上型電腦訊息中心定期。</li><li>檢視並更新內部的變更管理程序。</li><li>了解，並檢查遵守 Microsoft 受管理的桌面需求。 </li><li>確認並核准、 需要時。</li></ul></td></tr><tr><td>變更期間</td><td><ul><li>釋出及部署 Windows 10 和 Office 365 用戶端的每月的安全性與非安全性更新。</li><li>監視資料有空及支援佇列的影響。</li></ul></td><td><ul><li>檢查 Microsoft 受管理的桌面訊息中心並檢閱任何額外的資訊。</li><li>   如果有的話，需要執行任何動作，並測試應用程式。</li><li>如果發生在分行符號/修正的案例，建立支援要求。</li></ul></td></tr><tr><td>變更之後</td><td><ul><li>收集客戶意見反應以改善首度發行未來的變更。</li><li>監視資料有空及支援佇列的影響。</li></ul></td><td><ul><li>搭配採用變更組織中的人員。</li><li>   檢閱機會取得效率的變更和採用管理程序。</li><li>提供一般的意見反應及特定的意見反應在系統管理工具的意見反應。</li><li>訓練使用者以提供特定應用程式的意見反應在 Office 應用程式中使用 Windows 意見反應中心 」 及 「 Smile] 按鈕。</li></ul></td></tr>
<table> 






### <a name="change-types"></a>變更類型

有數種經常上的服務所做的變更。這些變更和客戶負責動作的通訊通道而異。

並非所有的變更您的使用者在具有相同的影響或需要巨集指令。有些是計劃和一些因依其性質 （非安全性更新和安全性更新不通常預定中）。變更類型、 通訊通道可能會有所不同。下表列出您可以預期 Microsoft 受管理的桌上型電腦服務的變更類型。

|   | 功能 |   非安全性更新 |  安全性
--- | --- | --- | ---
**變更類型** | -功能更新<br>-新功能或應用程式<br>-被取代的功能 | 問題的用戶端 Hotfix | 安全性修補程式
**換頁通知** | 5 天需要巨集指令的變更通知 |    否，這些版本中所包含每月   | 否，這些版本中所包含每月 
**通訊通道** | -訊息中心<br>電子郵件通知 | -訊息中心<br>電子郵件通知 | -訊息中心<br>電子郵件通知<br>安全性公告或 CVE 
**需要用戶管理動作** | 有時候 |  很少 |    很少 
**動作類型** | 變更設定 | 向使用者傳達變更 | 變更系統管理員設定     
**需要測試** | 檢查商務應用程式，包括遠端存取服務 |  有時候 - 測試程序或自訂的修正程式 |   很少 
**變更的範例** | -功能更新： IT 管理員入口網站簡體中文支援票證提交及檢閱<br>-新功能或應用程式： 半年度版本的 Windows 10 功能更新 | 根據客戶報告的錯誤的 Hotfix  |  


## <a name="standard-operating-procedures"></a>標準作業系統程序

Microsoft 受管理的桌上型電腦服務會實作與 microsoft 21vianet 您可能會在此進行其他系統管理活動您 Microsoft cloud 執行個體中。Microsoft 負責察覺 Microsoft 受管理的桌上型電腦特定安裝、 設定及作業。 

內部部署產品的組織採用上所有負責管理安裝，以及設定和操作的活動。

Categories |    Microsoft 將 | 將客戶
--- | --- | ---
網路 （proxy、 封包檢查、 VPN）  | 通知及規劃與客戶商務使用者的風險降至最低。 | 建立並要求的計劃的組態變更，包括設定詳細資料、 範圍、 時間表和 Microsoft 可供檢閱的其他相關詳細資料資訊的支援要求。<br>-一旦 Microsoft 受管理的桌上型電腦作業有評估與建議僅適用於變更。
服務帳戶 |-實作、 安全地儲存和管理認證。<br> -通訊未經授權的存取或使用這些認證的安全性操作小組。 | 建立並要求的計劃的組態變更，包括設定詳細資料、 範圍、 時間表和 Microsoft 可供檢閱的其他相關詳細資料資訊的支援要求。<br>-一旦 Microsoft 受管理的桌上型電腦作業有評估與建議僅適用於變更。<br>-未指派原則、 多重要素驗證、 設定格式化的條件 access 或應用程式部署至 Microsoft 受管理的桌上型電腦服務帳戶。<br>-不會重設密碼或使用的認證。<br>-如果可疑活動觀察 Intune 或 Azure 這些服務帳戶相關的稽核記錄中開啟 Microsoft 受管理的桌上型電腦作業嚴重度 C 支援要求。
裝置群組 | -實作及管理 Microsoft 受管理的桌上型電腦群組內的裝置的成員資格。<br>-使用 Microsoft 受管理的桌上型電腦群組管理的工作分派和裝置的設定及更新版本。 | 建立並要求的計劃的組態變更，包括設定詳細資料、 範圍、 時間表和 Microsoft 可供檢閱的其他相關詳細資料資訊的支援要求。<br>-一旦 Microsoft 受管理的桌上型電腦作業有評估與建議僅適用於變更。<br>-不修改任何 Microsoft 受管理的桌上型電腦群組的成員資格。<br>-僅使用 「 群組指派服務，例如 VPN、 Windows Hello 商務或電子郵件加密或公司 Wi-fi 設定檔設定的公司憑證。<br>-共同撰寫管理所在、 部署 Configuration Manager 用戶端時明確排除 Microsoft 受管理的桌上型電腦的所有群組。
Policies |  -實作和管理控管設定裝置的狀態服務內的 Microsoft 受管理的桌上型電腦原則。<br>-部署更新至原則或 Windows、 逐漸使用裝置群組。<br> -明確排除目標非的 Microsoft 受管理的桌上型電腦群組。 | 建立並要求的計劃的組態變更，包括設定詳細資料、 範圍、 時間表和 Microsoft 可供檢閱的其他相關詳細資料資訊的支援要求。<br>-一旦 Microsoft 受管理的桌上型電腦作業有評估與建議僅適用於變更。<br>-無法編輯或 Microsoft 受管理的桌上型電腦原則指派給裝置或不受管理的 Microsoft 受管理的桌上型電腦服務的使用者。
Windows Defender 進階威脅防護 | 監視與調查 Microsoft 受管理的桌上型電腦服務範圍內的裝置。 | 建立並要求的計劃的組態變更，包括設定詳細資料、 範圍、 時間表和 Microsoft 可供檢閱的其他相關詳細資料資訊的支援要求。<br>-一旦 Microsoft 受管理的桌上型電腦作業有評估與建議，僅適用於變更
商務用 Microsoft Store |  設定及維護 Microsoft 受管理的桌上型電腦服務的 Windows 自動駕駛儀上設定檔。 | 建立並要求的計劃的組態變更，包括設定詳細資料、 範圍、 時間表和 Microsoft 可供檢閱的其他相關詳細資料資訊的支援要求。<br>-一旦 Microsoft 受管理的桌上型電腦作業有評估與建議僅適用於變更。<br>-不修改 Microsoft 受管理的桌上型電腦 Windows 自動駕駛儀上設定檔的設定，或新增/移除已指派的裝置。
憑證 | | 建立支援要求 60 天前的憑證過期、 要求的計劃的組態變更，包括設定詳細資料、 範圍、 時間表和 Microsoft 可供檢閱的其他相關詳細資料資訊。<br>-一旦 Microsoft 受管理的桌上型電腦作業有評估與建議僅適用於變更。<br>-更新所需設定憑證設定檔、 VPN 設定檔及 Wi-fi 設定檔的所有憑證。




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

當已重設之裝置時，您可以到另一個人給予您組織中。沒有任何一個舊版使用者的資料或企業資料將會在裝置上。下一個使用者會逐一相同的舊的人員沒有使用新的 Microsoft 受管理的桌上型電腦裝置的程序。

BitLocker 會在此程序中的資料安全性的重要元件。使用 Microsoft 受管理的桌上型電腦裝置上的 BitLocker 加密資料的磁碟機上仍會保留安全即使原廠重設已套用至裝置。磁碟機的任何資料不會提供給下一個使用者的裝置。如需詳細資訊，請參閱[BitLocker 概觀 （英文）](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)。

如需詳細資訊，請參閱[原廠重設裝置](https://docs.microsoft.com/intune/devices-wipe#factory-reset-a-device)。 
