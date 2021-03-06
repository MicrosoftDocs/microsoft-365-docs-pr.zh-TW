---
title: Microsoft 受管理的電腦作業和監控
description: 神秘對各種變更程式執行什麼動作
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: e8fc583feb0d1ae1fc4ec4aa970b9dc19ae46fd9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286894"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft 受管理的電腦作業和監控

<!-- Operations and monitoring: -->

## <a name="change-management"></a>變更管理

在提供服務時，如硬體維護和安全性之類的項目責任權衡方式，會移轉至服務提供者 (Microsoft) 而非客戶 (您)。 不過，當向外延展更新時，您仍然需要確定非 Microsoft 和自訂的軟體仍會如預期的方式運作。

在內部部署產品中，您的組織假設管理變更的所有責任。

### <a name="balance-of-responsibility"></a>責任平衡

責任 | Microsoft 受管理的電腦服務 | Microsoft 365 用戶端軟體 | 內部部署用戶端和伺服器 | 非 Microsoft 和自訂軟體
----- | ----- | ----- | ----- | -----
提供新功能 | Microsoft | Microsoft | 兩者都要 | 客戶
測試品質保證的新功能 |  Microsoft | Microsoft | 兩者都要 | 客戶
溝通新功能的相關事宜 | 兩者都要 | 兩者都要 | 兩者都要 | 客戶
整合自訂軟體 | 兩者都要 | 兩者都要 | 客戶 | 客戶
套用安全性更新 | Microsoft | Microsoft | 客戶 | 客戶
維護系統軟體 | Microsoft | Microsoft | 客戶 | 客戶
用於部署的套件 | Microsoft | Microsoft | 客戶 | 客戶

### <a name="change-process-overview"></a>變更程式概述

以下摘要說明如何在 Microsoft 與客戶之間共用變更程式： 

<table>
<tr><th></th><th><p>Microsoft 的角色：</p></th><th><p>客戶的角色：</p></th></tr>
<tr><td>變更之前</td><td><ul><li>設定服務變更的期望。</li><li>在需要管理員動作的變更情況下，向客戶通知5天。</li><li>如需緊急變更，請在通知之前套用緩解。</li></ul></td><td><ul><li>了解對變更與通訊的期望。</li><li>定期讀取 Microsoft 受管理的電腦訊息中心。</li><li>檢視並更新內部的變更管理程序。</li><li>瞭解並檢查是否符合 Microsoft 受管理的電腦需求。 </li><li>必要時的認可與核准。</li></ul></td></tr><tr><td>變更期間</td><td><ul><li>發行及部署 Windows 10 和 Office 365 用戶端的每月安全性和非安全性更新。</li><li>監視資料信號並支援佇列的影響。</li></ul></td><td><ul><li>檢查 Microsoft 受管理的電腦訊息中心，並查看任何其他資訊。</li><li>採取任何必要動作（如果適用）及測試應用程式。</li><li>如果有經歷中斷/修正案例，請建立支援要求。</li></ul></td></tr><tr><td>變更之後</td><td><ul><li>收集客戶意見反應，以改進未來變更的首展。</li><li>監視資料信號並支援佇列的影響。</li></ul></td><td><ul><li>與您組織中的人員合作以採用變更。</li><li>回顧變更和採用管理程式，以取得效益的機會。</li><li>在 [系統管理意見反應] 工具中提供一般意見反應和特定的意見反應。</li><li>訓練使用者使用 Office 應用程式中的 Windows 意見反應中樞和笑臉按鈕，提供應用程式特定的意見反應。</li></ul></td></tr>
<table> 

### <a name="change-types"></a>變更類型

我們定期對此服務進行多種類型的變更。 這些變更和您負責處理的動作有不同的通訊通道。

並非所有變更對使用者或必要動作都會造成相同的影響。 有些人會根據其性質來規劃和部分計畫 (非安全性更新和安全性更新通常不會) 計畫。 根據變更的類型而定，通訊通道可能會有所不同。 下表列出 Microsoft 受管理的電腦服務可以預期的變更類型。

|   | 功能 | 非安全性更新 | 安全性
--- | --- | --- | ---
**變更類型** | -功能更新<br>-新功能或應用程式<br>過時的功能 | 問題的用戶端 Hotfix | 安全性更新
**事先通知** | 需要動作的變更需要5天的通知 | 否，每月版本都包含這類變更 | 否，每月版本都包含變更 
**通訊通道** | -訊息中心<br>-電子郵件警示 | -訊息中心<br>-電子郵件警示 | -訊息中心<br>-電子郵件警示
**需要全域系統管理員動作** | 有時候 | 很少 | 很少 
**動作類型** | 變更設定 | 向使用者傳達變更 | 變更系統管理員設定  
**需要測試** | 檢查商務應用程式，包括遠端存取服務 | 有時候 - 測試程序或自訂的修正程式 | 很少 
**變更範例** | -功能更新： IT 系統管理入口網站簡化支援票據提交和審閱<br>-新功能或應用程式： Windows 10 功能更新的 Semi-Annual 版本 | 根據客戶報告的錯誤的 Hotfix  |

## <a name="standard-operating-procedures"></a>標準運作程式

您可以在 microsoft 雲端實例中執行並運作 Microsoft 受管理的電腦服務，您可以在其中進行其他管理活動。 Microsoft 只負責 Microsoft 受管理的電腦特有的設定、設定和作業。

在內部部署產品中，您的組織會承擔管理安裝程式的所有責任，以及設定和操作活動。

類別 | Microsoft 會 | 客戶將
--- | --- | ---
網路 (proxy、封包檢查、VPN)   | 建議並與客戶一起規劃，以將企業使用者的風險降至最低。 | -建立要求要求資訊以進行規劃的設定變更，包括設定詳細資料、範圍、時程表及其他 Microsoft 供複查的相關詳細資料。<br>-只要 Microsoft 受管理的電腦作業已評估並建議，才套用變更一次。
服務帳戶 |-實施、安全地儲存和管理認證。<br> -對您的安全性作業小組進行未經授權的存取或使用這些認證。 | -建立要求要求資訊以進行規劃的設定變更，包括設定詳細資料、範圍、時程表及其他 Microsoft 供複查的相關詳細資料。<br>-只要 Microsoft 受管理的電腦作業已評估並建議，才套用變更一次。<br>-不指派原則、多重要素驗證、條件式存取或應用程式部署至 Microsoft 受管理的電腦服務帳戶。<br>-不要重設密碼或使用認證。<br>-如果在 Intune 或 Azure audit 記錄檔中看到可疑的活動（與這些服務帳戶相關），請開啟嚴重度 C 支援要求來 Microsoft 受管理的電腦作業。
裝置群組 | -在 Microsoft 受管理的電腦群組內實施及管理裝置的成員資格。<br>-使用 Microsoft 受管理的電腦群組來管理裝置的設定和更新的指派與發行。 | -建立要求要求資訊以進行規劃的設定變更，包括設定詳細資料、範圍、時程表及其他 Microsoft 供複查的相關詳細資料。<br>-只要 Microsoft 受管理的電腦作業已評估並建議，才套用變更一次。<br>-不修改任何 Microsoft 受管理的電腦群組的成員資格。<br>-僅使用群組來指派公司憑證（如 VPN、Windows Hello 用於商務或電子郵件加密，或公司 Wi-Fi 設定檔設定）。<br>-存在共同管理，請在部署 Configuration Manager 用戶端時，明確排除所有 Microsoft 受管理的電腦群組。
原則 | -實施及管理控制裝置內裝置設定狀態的 Microsoft 受管理的電腦原則。<br>-將更新部署到原則或 Windows，以增量方式使用裝置群組。<br> -明確排除以非 Microsoft 受管理的電腦群組為目標。 | -建立要求要求資訊以進行規劃的設定變更，包括設定詳細資料、範圍、時程表及其他 Microsoft 供複查的相關詳細資料。<br>-只要 Microsoft 受管理的電腦作業已評估並建議，才套用變更一次。<br>-不編輯或指派 Microsoft 受管理的電腦原則給未由 Microsoft 受管理的電腦服務管理的裝置或使用者。
適用於端點的 Microsoft Defender | 監視和調查 Microsoft 受管理的電腦服務範圍內的裝置。 | -建立要求要求資訊以進行規劃的設定變更，包括設定詳細資料、範圍、時程表及其他 Microsoft 供複查的相關詳細資料。<br>-僅在作業已評估並建議 Microsoft 受管理的電腦一次之後套用變更
商務用 Microsoft Store | 設定及維護 Microsoft 受管理的電腦服務的 Windows Autopilot 設定檔。 | -建立要求要求資訊以進行規劃的設定變更，包括設定詳細資料、範圍、時程表及其他 Microsoft 供複查的相關詳細資料。<br>-只要 Microsoft 受管理的電腦作業已評估並建議，才套用變更一次。<br>-不修改 Microsoft 受管理的電腦 Windows Autopilot 設定檔的設定，或是新增/移除指派的裝置。
憑證 | | -在憑證到期之前建立支援60要求，要求資訊以取得計畫的設定變更，包括設定詳細資料、範圍、時程表及其他 Microsoft 供複查的相關詳細資料。<br>-只要 Microsoft 受管理的電腦作業已評估並建議，才套用變更一次。<br>-更新所有必要的憑證，以設定憑證設定檔、VPN 設定檔，以及 Wi-Fi 設定檔。

## <a name="device-wipe-with-factory-reset"></a>以原回復位的裝置擦除

Microsoft 受管理的電腦作業小組可以在必要時，對服務中已登記的裝置執行出廠重設。 如果您需要將裝置送出至不同的員工，或是員工離開您的公司，重設會很有説明。

有幾個需求：

- 您的全域系統管理員必須提交服務要求。
- 在要求中包含裝置的電腦名稱稱。
- 在重設裝置之前，使用者帳戶必須位於 Azure AD 中。

受管理的桌面作業團隊會執行下列作業：

- 在 Intune 中查詢裝置名稱
- 傳送出廠重新設定命令至裝置

> [!NOTE]
> 在重設裝置之前，請勿從 Azure AD 移除使用者帳戶。 如果使用者不在 Azure AD 中，Intune 便無法將出廠重設指令傳送至裝置。

裝置會進入「全新的體驗」，並會再次套用所有預先安裝的應用程式和設定。 裝置的使用者需要重新提供初始安裝資訊。 

裝置重設後，您可以將其提供給組織中的其他人。 任何先前的使用者資料或企業資料都將會在裝置上。 下一個使用者將會完成先前人員使用新 Microsoft 受管理的電腦裝置所進行的相同處理常式。

BitLocker 是在此程式中的資料安全性重要元件。 在 Microsoft 受管理的電腦裝置上使用 BitLocker 加密，磁片磁碟機上的資料會在裝置重設後仍保持安全狀態。 磁片磁碟機上的所有資料將無法供下一個裝置的使用者使用。 如需詳細資訊，請參閱 [BitLocker 概述](/windows/security/information-protection/bitlocker/bitlocker-overview)。

如需詳細資訊，請參閱 [Factory reset a device](/intune/remote-actions/devices-wipe#factory-reset-a-device)。
