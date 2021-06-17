---
title: 檢視受攻擊面縮小事件
description: 匯入自訂視圖，以查看攻擊面降低事件。
keywords: 事件檢視、入侵防護、審核、複查、事件
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f8de3d8b2d7c07f8d783ecbe85b7e4a9c612aae5
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985447"
---
# <a name="view-attack-surface-reduction-events"></a>檢視受攻擊面縮小事件

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 想要體驗適用於端點的 Microsoft Defender 嗎？ [註冊免費試用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)。

在事件檢視器中查看攻擊面降低事件，以監視哪些規則或設定可以運作。 您也可以判斷是否有任何設定過於「嘈雜」或會影響您的日常工作流程。

在評估功能時，複查事件會非常實用。 您可以啟用 [功能] 或 [設定] 的「審核」模式，然後查看已完全啟用時，會發生什麼事。

本文列出所有事件、其相關的功能或設定，並說明如何建立自訂視圖，以篩選至特定事件。

如果您有 E5 訂閱，並使用[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)，請在 Windows 安全性中深入報告事件、區塊和警告。

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>使用自訂的視圖查看攻擊面降低功能

在 Windows 事件檢視器中建立自訂視圖，只查看特定功能和設定的事件。 最簡單的方法是將自訂視圖匯入為 XML 檔案。 您可以直接從此頁面複製 XML。

您也可以手動流覽至該功能對應的事件區域。

### <a name="import-an-existing-xml-custom-view"></a>匯入現有的 XML 自訂視圖

1. 建立空的 .txt 檔案，並將您想要使用的自訂視圖的 XML 複製到 .txt 檔案中。 針對每個您想要使用的自訂視圖執行這項作業。 將檔案重新命名為下列 (確定您將類型從 .txt 變更為 .xml) ：
    - 受管理的資料夾存取事件自訂視圖： *cfa-events.xml*
    - Exploit protection 事件自訂視圖： *ep-events.xml*
    - 攻擊面減少事件自訂視圖： *asr-events.xml*
    - 網路/保護事件自訂視圖： *np-events.xml*

2. 在 [開始] 功能表中輸入 **事件檢視器**，然後開啟 **事件檢視器**。

3. 選取 [**動作** 匯  >  **入自訂視圖 ...** ]

  > [!div class="mx-imgBorder"]
  > ![動畫醒目提示在奇偶檢視器視窗左邊的匯入自訂視圖](images/events-import.gif)

4. 流覽至您要從中抽出之自訂視圖之 XML 檔案的位置，並加以選取。

5. 選取 [開啟]。

6. 它會建立自訂視圖，篩選為只顯示與該功能相關的事件。

### <a name="copy-the-xml-directly"></a>直接複製 XML

1. 在 [開始] 功能表中輸入 **事件檢視器**，然後開啟 Windows **事件檢視器**。

2. 在左窗格的 [ **動作**] 下，選取 [ **建立自訂視圖 ...]。**

  > [!div class="mx-imgBorder"]
  > ![動畫顯示 [事件檢視器] 視窗中的 [建立自訂視圖] 選項](images/events-create.gif)

3. 移至 [XML] 索引標籤，然後選取 [ **手動編輯查詢**]。 您會看到一則警告，指出您使用 [XML] 選項時，您無法使用 [ **篩選** ] 索引標籤編輯查詢。 選取 **[是]**。

4. 將您要篩選事件的功能的 XML 程式碼貼到 XML 區段中。

5. 選取 **[確定]**。 指定篩選的名稱。 這會建立自訂視圖，篩選為只顯示與該功能相關的事件。

### <a name="xml-for-attack-surface-reduction-rule-events"></a>針對攻擊面減少規則事件的 XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-controlled-folder-access-events"></a>受控制資料夾存取事件的 XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-exploit-protection-events"></a>用於 exploit protection 事件的 XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-network-protection-events"></a>網路保護事件的 XML

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

## <a name="list-of-attack-surface-reduction-events"></a>攻擊面降減事件清單

所有攻擊面降低事件都位於 [**應用程式及服務記錄檔] > Microsoft > Windows** ，然後是位於下表所列的資料夾或提供者。

您可以在 Windows 事件檢視器中存取這些事件：

1. 開啟 [ **開始** ] 功能表並輸入 **事件檢視器**，然後選取 **事件檢視器** 結果。
2. 展開 [**應用程式及服務記錄] > Microsoft > Windows** 然後移至下表中 [**提供者/來源**] 底下所列的資料夾。
3. 在子專案上按兩下以查看事件。 在事件中向裡移動，以找出您想要的事件。

   ![使用事件檢視器顯示的動畫](images/event-viewer.gif)

功能 | 提供者/來源 | 事件識別碼 | 描述
:-|:-|:-:|:-
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 1 | ACG 審核
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 第 | ACG 強制執行
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 個 | 不允許子進程審核
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 4  | 不允許子進程區塊
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 5  | 封鎖低誠信影像的審計
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 6  | 封鎖低誠信影像區塊
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 7  | 封鎖遠端影像審計
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 8  | 封鎖遠端影像區塊
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 9  | 停用 win32k 系統通話審計
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 10  | 停用 win32k 系統通話封鎖
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 第 | 程式碼完整性保護審計
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 12  | 程式碼完整性防護區塊
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 13 | EAF 審計
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 14  | 強制執行 EAF
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 8 | EAF + audit
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 16  | EAF + 強制執行
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 17  | IAF 審計
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 18  | 強制執行 IAF
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 19 | ROP StackPivot audit
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 共 | ROP StackPivot 強制執行
入侵防護 | Security-Mitigations (核心模式/使用者模式)  |  21 | ROP CallerCheck audit
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 22 | ROP CallerCheck 強制執行
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 至 | ROP SimExec audit
入侵防護 | Security-Mitigations (核心模式/使用者模式)  | 24 | ROP SimExec 強制執行
入侵防護 | WER-Diagnostics | 5  | CFG 區塊
入侵防護 | Win32K (運作)  | 260 | 不信任的字型
網路保護 | Windows Defender (操作)  | 5007 | 設定變更時的事件
網路保護 | Windows Defender (操作)  | 1125 | 在稽核模式中觸發網路保護時的事件
網路保護 | Windows Defender (操作)  | 1126 | 在封鎖模式中激發網路保護時的事件
受控資料夾存取權 | Windows Defender (操作)  | 5007 | 設定變更時的事件
受控資料夾存取權 | Windows Defender (操作)  | 1124 | 已審核的受管理資料夾存取事件
受控資料夾存取權 | Windows Defender (操作)  | 1123 | 封鎖的受管理資料夾存取事件
受控資料夾存取權 | Windows Defender (操作)  | 1127 | 封鎖的受管理資料夾存取區域寫入區塊事件
受控資料夾存取權 | Windows Defender (操作)  | 1128 | 已審核的受管理資料夾存取區域寫入區塊事件
攻擊面縮小 | Windows Defender (操作)  | 5007 | 設定變更時的事件
攻擊面縮小 | Windows Defender (操作)  | 1122 | 在稽核模式中觸發規則時的事件
攻擊面縮小 | Windows Defender (操作)  | 1121 | 在組塊模式中激發規則時的事件
