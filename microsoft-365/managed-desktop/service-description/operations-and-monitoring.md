---
title: Microsoft 受管理電腦作業和監控
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5aee7c835643fab94cc7e233ea005c3f3a1b921c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602800"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft 受管理電腦作業和監控

<!-- Operations and monitoring: -->


## <a name="change-management"></a>變更管理

在提供服務時，如硬體維護和安全性之類的項目責任權衡方式，會移轉至服務提供者 (Microsoft) 而非客戶 (您)。 不過，您仍然必須確定該協力廠商及自訂軟體會繼續運作如預期般更新所導入時。

對於內部部署產品，您的組織會假設所有負責管理變更。

### <a name="balance-of-responsibility"></a>責任權衡方式

責任 | Microsoft 受管理的電腦服務 | Microsoft 365 用戶端軟體 | 內部部署用戶端和伺服器 | 3rd 廠商及自訂軟體
----- | ----- | ----- | ----- | -----
提供新功能 | Microsoft | Microsoft | 兩者都要 | 客戶
測試品質保證的新功能 |  Microsoft | Microsoft | 兩者都要 | 客戶
溝通新功能的相關事宜 | 兩者都要 | 兩者都要 | 兩者都要 | 客戶
整合自訂軟體 | 兩者都要 | 兩者都要 | 客戶 | 客戶
套用安全性更新 | Microsoft | Microsoft | 客戶 | 客戶
維護系統軟體 | Microsoft | Microsoft | 客戶 | 客戶
適用於部署套件 | Microsoft | Microsoft | 客戶 | 客戶


### <a name="change-process-overview"></a>變更處理程序概觀

以下是變更程序如何共用 Microsoft 與客戶之間的摘要。 



<table>
<tr><th></th><th><p>Microsoft 的角色：</p></th><th><p>客戶的角色：</p></th></tr>
<tr><td>變更之前</td><td><ul><li>設定服務變更的期望。</li><li>5 天前的需要管理員採取動作的變更通知客戶。</li><li>針對緊急變更，套用前通知緩和措施。</li></ul></td><td><ul><li>了解對變更與通訊的期望。</li><li>閱讀 Microsoft 受管理的桌上型電腦訊息中心定期。</li><li>檢視並更新內部的變更管理程序。</li><li>了解，並檢查 Microsoft 受管理電腦需求的相容性。 </li><li>認可並核准，必要時。</li></ul></td></tr><tr><td>變更期間</td><td><ul><li>版本和部署 Windows 10 和 Office 365 用戶端的每月的安全性和非安全性更新。</li><li>監視資料訊號及支援佇列的影響。</li></ul></td><td><ul><li>檢查 Microsoft 受管理電腦的訊息中心和檢閱任何其他資訊。</li><li>   如果適用的話，採取任何必要、 動作和測試應用程式。</li><li>如果遇到中斷/修復案例，建立支援要求。</li></ul></td></tr><tr><td>變更之後</td><td><ul><li>收集客戶的意見以改善未來的積存變更。</li><li>監視資料訊號及支援佇列的影響。</li></ul></td><td><ul><li>搭配採用變更您組織中的人員。</li><li>   檢閱變更和採用率管理程序，以提高商機效率的入侵。</li><li>提供一般意見，並在系統管理意見反應工具中的特定意見反應。</li><li>訓練使用者提供 Office 應用程式中使用 Windows 意見反應中樞和 [微笑] 按鈕的應用程式特定意見反應。</li></ul></td></tr>
<table> 






### <a name="change-types"></a>變更類型

有數種類型的定期服務所做的變更。 通訊通道的這些變更，以及客戶所負責的動作而異。

並非所有變更對使用者或必要動作都會造成相同的影響。 有些是計劃與某些意外的本質 （非安全性更新和安全性更新未通常計劃中）。 根據變更的類型，可能會不同的通訊通道。 下表列出您可以為 Microsoft 受管理的電腦服務預期變更的類型。

|   | 功能 |   非安全性更新 |  安全性
--- | --- | --- | ---
**變更類型** | -功能更新<br>-新功能或應用程式<br>-被取代的功能 | 問題的用戶端 Hotfix | 安全性修補程式
**事先通知** | 5 天通知需要採取動作的變更 |    否，這些都會包括在每月發行   | 否，這些都會包括在每月發行 
**通訊通道** | -訊息中心<br>電子郵件警示 | -訊息中心<br>電子郵件警示 | -訊息中心<br>電子郵件警示
**需要租用戶系統管理員採取動作** | 有時候 |  很少 |    很少 
**動作的類型** | 變更設定 | 向使用者傳達變更 | 變更系統管理員設定     
**需要測試** | 檢查商務應用程式，包括遠端存取服務 |  有時候 - 測試程序或自訂的修正程式 |   很少 
**變更的範例** | -功能更新： IT 系統管理員入口網站簡化支援票證提交及檢閱<br>-新功能或應用程式： 半年版本的 Windows 10 功能更新 | 根據客戶報告的錯誤的 Hotfix  |  


## <a name="standard-operating-procedures"></a>標準作業程序

Microsoft 受管理的電腦服務是實作，並由 Microsoft 運作，您可能會在此進行其他系統管理活動您 Microsoft 雲端執行個體中。 Microsoft 為負責 Microsoft 受管理的桌上型電腦特定安裝、 設定及作業。 

對於內部部署產品，您的組織都會採用所有負責管理安裝，以及設定和作業活動。

類別 |    Microsoft 將會 | 客戶會
--- | --- | ---
網路 （proxy、 封包檢查，VPN）  | 通知並計劃與客戶的商務使用者的風險降至最低。 | 建立要求的計劃的設定變更，包括設定詳細資料、 範圍、 時間表和 Microsoft，以檢閱其他相關詳細資料資訊的支援要求。<br>-Microsoft 受管理的桌上型電腦作業已評估，並建議您之後僅適用於變更。
服務帳戶 |-實作、 安全地儲存和管理認證。<br> -未經授權的存取或使用這些認證的安全性操作小組進行通訊。 | 建立要求的計劃的設定變更，包括設定詳細資料、 範圍、 時間表和 Microsoft，以檢閱其他相關詳細資料資訊的支援要求。<br>-Microsoft 受管理的桌上型電腦作業已評估，並建議您之後僅適用於變更。<br>-未指派原則、 多重要素驗證、 條件式存取或應用程式部署至 Microsoft 受管理的桌上型電腦服務帳戶。<br>-不重設密碼，或使用的認證。<br>-如果可疑的活動就觀察到 Intune 或 Azure 稽核記錄檔中，與這些服務帳戶，請開啟 Microsoft 受管理的桌上型電腦作業的嚴重度 C 支援要求。
裝置群組 | -實作及管理 Microsoft 受管理的電腦群組內的裝置的成員資格。<br>-使用 Microsoft 受管理的電腦群組來管理工作分派和裝置的組態和更新版本。 | 建立要求的計劃的設定變更，包括設定詳細資料、 範圍、 時間表和 Microsoft，以檢閱其他相關詳細資料資訊的支援要求。<br>-Microsoft 受管理的桌上型電腦作業已評估，並建議您之後僅適用於變更。<br>-不修改任何 Microsoft 受管理的電腦群組的成員資格。<br>-僅用於群組指派公司的憑證，例如 VPN、 Windows Hello 企業或電子郵件加密] 或 [公司的 Wi-fi 設定檔設定的服務。<br>-共同管理所在，明確地部署 Configuration Manager 用戶端時，排除所有 Microsoft 受管理的電腦群組。
原則 |  -實作和管理，進而管理服務內的裝置的組態狀態的 Microsoft 受管理電腦原則。<br>-將更新部署至原則或 Windows，逐漸使用裝置群組。<br> -明確排除目標非-Microsoft 受管理的電腦群組。 | 建立要求的計劃的設定變更，包括設定詳細資料、 範圍、 時間表和 Microsoft，以檢閱其他相關詳細資料資訊的支援要求。<br>-Microsoft 受管理的桌上型電腦作業已評估，並建議您之後僅適用於變更。<br>-無法編輯，或將 Microsoft 受管理電腦原則指派到裝置或未受 Microsoft 受管理的電腦服務的使用者。
Windows Defender 進階威脅防護   | 監視及調查 Microsoft 受管理的電腦服務範圍內的裝置。 | 建立要求的計劃的設定變更，包括設定詳細資料、 範圍、 時間表和 Microsoft，以檢閱其他相關詳細資料資訊的支援要求。<br>-Microsoft 受管理的桌上型電腦作業已評估，並建議您之後，僅適用於變更
商務用 Microsoft Store |  設定及維護的 Microsoft 受管理的電腦服務的 Windows Autopilot 設定檔。 | 建立要求的計劃的設定變更，包括設定詳細資料、 範圍、 時間表和 Microsoft，以檢閱其他相關詳細資料資訊的支援要求。<br>-Microsoft 受管理的桌上型電腦作業已評估，並建議您之後僅適用於變更。<br>-不修改 Microsoft 受管理的桌上型電腦 Windows Autopilot 設定檔的設定，或新增/移除指派的裝置。
憑證 | | 建立支援要求 60 天前的憑證到期、 要求在計劃的設定變更，包括設定詳細資料、 範圍、 時間表和 Microsoft，以檢閱其他相關詳細資料的資訊。<br>-Microsoft 受管理的桌上型電腦作業已評估，並建議您之後僅適用於變更。<br>-更新所設定的憑證設定檔、 VPN 設定檔，以及 Wi-fi 設定檔的所有憑證。




## <a name="device-wipe-with-factory-reset"></a>使用原廠重設裝置資料抹除

Microsoft 受管理的桌上型電腦作業小組可以執行時所需的服務中註冊裝置的原廠重設。 如果您需要將裝置授與不同的員工，或是如果員工離開公司，這是很有幫助。 

有幾個需求：

- 客戶的租用戶系統管理員必須提交服務要求
- 我們需要裝置的電腦名稱
- 使用者帳戶必須是我們執行重設之前的 Azure AD 中

受管理的桌上型電腦作業小組會：

- Intune 中的裝置名稱查閱
- 傳送原廠重設命令到裝置

>[!NOTE]
>請勿移除的使用者帳戶從原廠重設之前的 Azure AD。 如果使用者不在 Azure AD，Intune 無法傳送原廠重設命令到裝置。 

裝置會開機成 OOBE，且所有預先安裝的應用程式和設定會套用一次。 裝置的使用者必須提供資訊一次的初始設定。 

當已重設裝置時，您可以到另一個人提供您組織中。 沒有任何一個舊版使用者的資料或企業資料將會在裝置上。 下一位使用者就會通過經歷相同的前一個人沒有使用新的 Microsoft 受管理的電腦裝置的程序。

BitLocker 是在此程序中的資料安全性的重要元件。 使用 Microsoft 受管理的電腦裝置上的 BitLocker 加密，磁碟機上的資料安全即使物件之後仍然原廠重設已套用至裝置。 磁碟機的任何資料無法向下一個使用者的裝置。 如需詳細資訊，請參閱[〈 BitLocker 概觀 〉](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)。

如需詳細資訊，請參閱[原廠重設裝置](https://docs.microsoft.com/intune/remote-actions/devices-wipe#factory-reset-a-device)。 
