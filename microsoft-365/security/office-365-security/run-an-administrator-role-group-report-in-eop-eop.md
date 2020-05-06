---
title: 執行 EOP 中的系統管理員角色群組報告
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
ms.custom:
- seo-marvel-apr2020
description: 在本文中，您將瞭解如何在 Exchange Online Protection （EOP）中執行系統管理員角色群組報告。
ms.openlocfilehash: d3c4db8079a71ba054f323617d3ade65083a3a04
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034453"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>執行 EOP 中的系統管理員角色群組報告

 當系統管理員在系統管理員角色群組中新增或移除成員時，Exchange Online Protection （EOP）會記錄每個事件。 當您在 Exchange 系統管理中心（EAC）中執行系統管理員角色群組報告時，專案會顯示為搜尋結果，並包含受影響的角色群組、變更角色群組成員資格的人員，以及進行的成員資格更新。 使用此報告可監視指派給組織使用者的系統管理權限變更。

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始之前有哪些須知？

- 預估完成時間：2 分鐘

- 若要開啟 Exchange 系統管理中心，請參閱 exchange [Online Protection 中的 exchange 系統管理中心](exchange-admin-center-in-exchange-online-protection-eop.md)。

- 您必須已獲指派權限，才能執行此程序或這些程序。若要查看您需要的權限，請參閱 [EOP 中的功能權限](feature-permissions-in-eop.md)主題的「報告」一節。

- 如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 有問題嗎？ 在 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) 論壇中尋求協助。

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>使用 EAC 執行系統管理員角色群組報告

執行系統管理員角色群組報告，以在特定時間範圍內尋找組織中管理角色群組的變更。

1. 在 EAC 中，瀏覽至 **[相符性管理]** \> **[稽核]**，然後選擇 **[執行系統管理員角色群組報告]**。

2. 選擇 **[開始日期]** 和 **[結束日期]**。依預設，報告會搜尋過去兩週以來對系統管理員角色群組所做的變更。

3. 若要檢視特定角色群組的變更，請按一下 **[選取角色群組]**。在後續的對話方塊中選取一或多個角色群組，然後按一下 **[確定]**。您也可以將欄位留白，以尋找所有變更的角色群組。

4. Click **Search**.

如果使用您指定的準則找到任何變更，它們會出現在結果窗格中。按一下搜尋結果中的角色群組，即可在詳細資料窗格中查看變更。

## <a name="how-do-you-know-this-worked"></a>如何知道這是否正常運作？

如果您已經成功執行系統管理員角色群組報告，已在日期範圍內變更的角色群組會顯示在搜尋結果窗格中。如果沒有任何結果，則表示在指定的日期範圍內，沒有對角色群組進行任何變更。如果您認為應該有結果，請變更日期範圍，然後重新執行報告。

## <a name="monitor-changes-to-role-group-membership"></a>監視角色群組成員資格的變更

在角色群組中新增或移除成員時，搜尋結果會顯示在詳細資料窗格中，指出角色群組成員資格已經更新，並列出目前的成員。結果不會明確表示已新增或移除哪一位使用者。

若要判斷是否已新增或移除某位使用者，您必須比較報告中的兩個個別項目。例如，以下是 **HelpDesk** 角色群組的記錄項目：

> 1/27/2018 4:43 PM <br> 系統管理員 <br> Updated members:Administrator;annb,florencef;pilarp <br> 2/06/2018 10:09 AM <br> 系統管理員 <br> Updated members:Administrator;annb;florencef;pilarp;tonip <br> 2/19/2018 2:12 PM <br> 系統管理員 <br> Updated members:Administrator;annb;florencef;tonip

在此範例中，系統管理員使用者帳戶做了以下變更：

- 在2/06/2018 上，他們新增了使用者 tonip。

- 在2/19/2018 上，他們移除使用者 pilarp。
