---
title: 管理 [Office 指令碼] 設定
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: 瞭解如何管理組織中使用者的 Office 腳本設定。
ms.openlocfilehash: e0cb52c4a8f48ff2310c83ffce61e08a0236ed59
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572306"
---
# <a name="manage-office-scripts-settings"></a>管理 [Office 指令碼] 設定

[Office 腳本](/office/dev/scripts)可讓使用者在網頁上 Excel 中記錄、編輯和執行腳本，以自動化工作。 Office腳本可與 Power Automate 搭配使用 Excel 線上 (商務) 連接器上的使用者，在活頁簿上執行腳本。 Microsoft 365 系統管理員可以從 Microsoft 365 系統管理中心管理 Office 腳本設定。

## <a name="before-you-begin"></a>開始之前

- 若要管理 Office 腳本設定，您必須是全域系統管理員。如需詳細資訊，請參閱[關於系統管理員角色](../add-users/about-admin-roles.md)。

- 請確定貴組織中的使用者擁有 Microsoft 365 的有效授權，或 Office 365 商用或 EDU plan，其中包含 Office 桌面應用程式的存取權，例如下列其中一個計畫：

    - Microsoft 365 商務標準版
    - Microsoft 365 Apps 商務版
    - Microsoft 365 Apps 企業版
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>管理 Office 腳本和共用腳本的可用性

1. 在 Microsoft 365 系統管理中心，移至 [**設定** \> **組織設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">服務</a>] 索引標籤。

2. 選取 [ **Office 腳本**]。

3. Office預設會開啟腳本，而且您組織中的每個人都可以存取和使用該功能及共用腳本。 若要關閉組織的 Office 腳本，請清除 [**讓使用者能在 Excel 網頁版中自動執行其** 工作] 核取方塊。

4. 如果您先前已關閉組織 Office 腳本，並想要將其重新開啟，請選取 [**讓使用者在 Excel 網頁版中自動執行其** 工作]，然後指定可以存取和使用該功能的使用者：

    - 若要讓組織中的所有使用者都能存取及使用 Office 腳本，請讓所有 **人都** (選取的預設) 。

    - 若只要允許特定群組的成員存取及使用 Office 腳本，請選取 [**特定群組**]，然後輸入群組的名稱或電子郵件別名，以將其新增至 [允許] 清單。 您可以只將一個群組新增至允許清單，而且必須是下列其中一個類型：
        - Microsoft 365 群組
        - 通訊群組
        - 安全性群組
        - 擁有郵件功能的安全性群組
    
        若要深入瞭解不同類型的群組，請參閱 [比較群組](../create-groups/compare-groups.md)。

5. 若要讓能夠存取 Office 腳本的使用者與組織中的其他人共用其腳本，請選取 **[讓具有 Office 腳本的存取權與組織中的其他人共用其腳本**]。 不允許在組織外共用腳本。
 
    > [!NOTE]
    > 如果您稍後關閉組織的腳本共用，使用者仍可以執行先前共用的腳本。
 
6. 指定可以存取 Office 腳本的使用者可以共用其腳本：
    
    - 若要讓所有可存取 Office 腳本的使用者共用其腳本，請讓所有 **人都** (選取的預設) 。

    - 若只要允許特定群組的成員存取 Office 腳本以共用其腳本，請選取 [**特定群組**]，然後輸入群組的名稱或電子郵件別名，以將其新增至 [允許] 清單。 您可以只將一個群組新增至允許清單，而且必須是下列其中一個類型：
        - Microsoft 365 群組
        - 通訊群組
        - 安全性群組
        - 擁有郵件功能的安全性群組
    
        若要深入瞭解不同類型的群組，請參閱 [比較群組](../create-groups/compare-groups.md)。

7. 若要允許使用者在 Power Automate 流程內執行其 Office 腳本，請選取 [**允許存取 Office 腳本的使用者以 Power Automate 執行其腳本**。 這可讓使用者使用 [Excel Online (商務) 連接器的](/connectors/excelonlinebusiness)[**執行腳本**] 選項，來新增流程步驟。

    - 若要讓所有可存取 Office 腳本的使用者，在資料流程中使用腳本，請將 **每個人都** (選取的預設) 。

    - 若只要允許特定群組的成員存取 Office 腳本以在資料流程中使用腳本，請選取 [**特定群組**]，然後輸入群組的名稱或電子郵件別名，以將其新增至 [允許] 清單。 您可以只將一個群組新增至允許清單，而且必須是下列其中一個類型：
        - Microsoft 365 群組
        - 通訊群組
        - 安全性群組
        - 擁有郵件功能的安全性群組

        若要深入瞭解不同類型的群組，請參閱 [比較群組](../create-groups/compare-groups.md)。

    - 若要深入瞭解搭配 Power Automate 使用 Office 腳本的詳細資訊，請參閱[with Power Automate 執行 Office 腳本](/office/dev/scripts/develop/power-automate-integration)。

8. 選取 [儲存 **]**。

    最多可能需要48個小時，Office 腳本設定的變更才會生效。

## <a name="next-steps"></a>後續步驟

由於 Office 腳本可搭配 Power Automate 使用，因此建議您檢查現有的資料遺失防護 (DLP) 原則，以確保當使用者使用 Office 腳本時，組織的資料仍保持受保護狀態。 如需詳細資訊，請參閱 [資料遺失防護 (DLP) 原則](/power-automate/prevent-data-loss)。

## <a name="related-content"></a>相關內容

[Office 腳本技術檔](/office/dev/scripts/) (連結頁面) \
[Excel (文章中 Office 腳本簡介](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a)) \
[在網頁 (文章 Excel 中共用 Office 腳本](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b)) \
[在 Excel 網頁版 (篇文章中記錄、編輯及建立 Office 腳本](/office/dev/scripts/tutorials/excel-tutorial)) 
