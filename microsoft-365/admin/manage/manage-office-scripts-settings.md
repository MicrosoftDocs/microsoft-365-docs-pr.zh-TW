---
title: 管理 Office 腳本設定
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
ms.openlocfilehash: 12a80f277f6d17a8e7f5228f6948e70b7a93be11
ms.sourcegitcommit: 97ef8f846939c3d31bb0638edf07bb89463ace0b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/28/2020
ms.locfileid: "47300827"
---
# <a name="manage-office-scripts-settings"></a>管理 Office 腳本設定

Office 腳本可讓使用者在網頁上的 Excel 中錄製、編輯和執行腳本，以自動化工作。 Office 腳本可搭配電源自動運作，而且使用者可以使用 Excel Online (商務) 連接器，在活頁簿上執行腳本。 Microsoft 365 系統管理員可以從 Microsoft 365 系統管理中心管理 Office 腳本設定。

## <a name="before-you-begin"></a>在您開始之前

- 若要管理 Office 腳本設定，您必須是全域系統管理員。如需詳細資訊，請參閱 [關於系統管理員角色](../add-users/about-admin-roles.md)。

- 請確定貴組織中的使用者擁有有效的 Microsoft 365 或 Office 365 商業版或 EDU 方案授權，其中包含 Office 桌面應用程式的存取權，例如下列其中一個計畫：

    - Microsoft 365 商務標準版
    - Microsoft 365 Apps 商務版
    - Microsoft 365 Apps 企業版
    - Office 365 E3
    - Office 365 E5
    - Office 365 A3
    - Office 365 A5

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a>管理 Office 腳本及腳本的共用可用性

1. 在 Microsoft 365 系統管理中心中，移至 [ **設定** \> **組織設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">服務</a> ] 索引標籤。

2. 選取 [ **Office 腳本**]。

3. Office 腳本預設為開啟狀態，您組織中的每個人都可以存取和使用該功能及共用腳本。 若要關閉組織的 Office 腳本，請清除 [ **讓使用者能在 web 上的 Excel 中自動執行其工作** ] 核取方塊。

4. 如果您先前已關閉組織的 Office 腳本，且想要將其重新開啟，請選取 **[讓使用者能在網頁上自動使用 Excel**的工作]，然後指定誰可以存取和使用該功能：

    - 若要讓組織中的所有使用者都能存取及使用 Office 腳本，請將 **每個人** () 選取的預設值。 

    - 若只要允許特定群組的成員存取及使用 Office 腳本，請選取 [ **特定群組**]，然後輸入群組的名稱或電子郵件別名，以將其新增至 [允許] 清單。 您可以只將一個群組新增至允許清單，而且必須是下列其中一個類型：
        - Microsoft 365 群組
        - 通訊群組
        - 安全性群組
        - 擁有郵件功能的安全性群組
    
        若要深入瞭解不同類型的群組，請參閱 [比較群組](../create-groups/compare-groups.md)。

5. 若要讓能夠存取 Office 腳本的使用者與組織中的其他人共用其腳本，請選取 **[讓有權存取 Office 腳本的使用者能夠與組織中的其他人共用其腳本**。 不允許在組織外共用腳本。
 
    > [!NOTE]
    > 如果您稍後關閉組織的腳本共用，使用者仍可以執行先前共用的腳本。
 
6. 指定可以存取 Office 腳本的使用者可以共用其腳本：
    
    - 若要讓所有擁有 Office 腳本存取權的使用者都能共用其腳本，請將 **每個人** () 選取的預設值。

    - 若只要允許特定群組的成員存取 Office 腳本以共用其腳本，請選取 [ **特定群組**]，然後輸入群組的名稱或電子郵件別名，以將其新增至 [允許] 清單。 您可以只將一個群組新增至允許清單，而且必須是下列其中一個類型：
        - Microsoft 365 群組
        - 通訊群組
        - 安全性群組
        - 擁有郵件功能的安全性群組
    
        若要深入瞭解不同類型的群組，請參閱 [比較群組](../create-groups/compare-groups.md)。

7. 選取 [儲存]****。

    您可能需要長達48小時，Office 腳本設定的變更才會生效。

## <a name="next-steps"></a>後續步驟

由於 Office 腳本可搭配電源自動化運作，因此建議您複查現有的資料遺失防護 (DLP) 原則，以確保當使用者使用 Office 腳本時，組織的資料仍保持受保護狀態。 如需詳細資訊，請參閱 [資料遺失防護 (DLP) 原則](/power-automate/prevent-data-loss)。

## <a name="related-content"></a>相關內容

[Office 腳本技術檔](/office/dev/scripts/) (連結頁面) \
[Excel 中的 Office 腳本簡介](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (文章) \
[在 Excel 中為 Web (文章共用 Office 腳本](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b)) \
[在網頁上的 Excel 中記錄、編輯及建立 Office 腳本](/office/dev/scripts/tutorials/excel-tutorial) (文章) 