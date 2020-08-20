---
title: 使用 [保留標籤] 宣告記錄
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 使用 [保留標籤] 宣告記錄。
ms.openlocfilehash: d637817e8d1bcc8c72bfe011dfd288ac4e2d0298
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778513"
---
# <a name="declare-records-by-using-retention-labels"></a>使用 [保留標籤] 宣告記錄

>*[Microsoft 365 安全性與合規性的授權指引](https://aka.ms/ComplianceSD)*

若要將項目宣告為紀錄，您可使用 [保留標籤](retention.md#retention-labels) 將其內容標示為記錄。 您可以發佈這些標籤，讓使用者和系統管理員手動將這些標籤套用至內容，或自動將這些標籤套用到您想要標記為記錄的內容。

## <a name="configuring-retention-labels-to-declare-records"></a>設定 [保留標籤] 以宣告記錄

當您建立或設定了一個保留標籤時，選取選項將內容標記為記錄。

>[!NOTE] 
> 當您在 Microsoft 365 合規性中心中建立或設定 **資訊控管** 中的保留標籤時，無法使用將內容標記為記錄的選項。 而是必須使用 **記錄管理**。

若要將內容標示為記錄而建立一個新的保留標籤時：

1. 在 [Microsoft 365 合規性中心](https://compliance.microsoft.com) 中，移至 **[記錄管理]** \> **[檔案計畫]**。 選取在 **[檔案計畫]** 頁面上的 **[建立標籤]**。

2. 在精靈的 [標籤設定]**** 頁面上，選擇將內容分類為記錄的選項。
    
   ![按一下 [使用標籤以將內容分類為「記錄」] 核取方塊](../media/recordversioning6.png)

3. 視需要將保留標籤套用至 SharePoint 或 OneDrive 文件和 Exchange 電子郵件。 如需詳細指示：
    
    - [建立保留標籤，並在應用程式中使用這些標籤](create-apply-retention-labels.md)
    
    - [自動將保留標籤套用到內容](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a>將已設定的保留標籤套用至內容

將內容標示為記錄的保留標籤可供使用者在應用程式中套用：

- 針對 Exchange，任何信箱存取權的使用者都可以套用這些標籤。 
- 對於 SharePoint 和 OneDrive，預設 [成員] 群組 ([參與] 權限等級) 中的任何使用者都能套用這些標籤。

使用保留標籤將文件標示為記錄的範例：

![標記為記錄之文件的詳細資料窗格](../media/recordversioning7.png)

## <a name="next-steps"></a>後續步驟

若需記錄管理支援的案例清單，請參閱 [[記錄管理的常見案例]](get-started-with-records-management.md#common-scenarios-for-records-management)。
