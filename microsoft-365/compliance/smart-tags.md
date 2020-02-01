---
title: 設定進階電子文件中的智慧標籤
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: 智慧標籤可讓您套用機器學習功能檢閱進階電子文件探索案例中的內容時。 使用智慧標籤群組來顯示機器學習偵測模型，例如律師-委託人權限模型的結果。
ms.openlocfilehash: 9b3e1310baa06f53a3ee1dab5c371fb67d6ab95c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597400"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>設定進階電子文件中的智慧標籤

進階電子文件中的機器學習 (ML) 功能可協助您做出決策程序更有效率，檢閱區分大小的文件組中的檢閱時。 智慧標籤是帶的 ML 功能，以決定記錄的其中一種方法： 當期間檢閱標記的文件。 當您建立的智慧標籤群組時，然後您已與智慧標籤群組相關聯的 ML 模型的結果的決策會顯示在線具有 [標記] 群組中的標記。 這有助於看到 ML 結果在檢閱特定文件資訊中的行。

## <a name="how-to-set-up-a-smart-tag-group"></a>如何設定的智慧標籤群組

1. 在 [檢閱設定，按一下 [**管理檢閱設定**，然後按一下**管理標記**。

2. 按一下 [**新增標籤群組**，然後選取 [**新增智慧標籤群組**。

3. 選取您想要關聯至標籤群組 ML 模型。
    
   這會建立一個標記群組和*N*子標籤，其中*N*是可能輸出模型的數目。 例如，[律師-委託人權限偵測模型](attorney-privilege-detection.md)有兩個可能的輸出： 

   - **正數**– 包含律師-委託人特殊權限內容的標籤文件的使用。
   
   - **負值**– 使用不含律師-委託人特殊權限內容的標籤文件。
    
    如果您選取此模型，標記具有兩個的子系標記為建立群組 （一個子系標記名為**正值**與其他具名**負值**） 檢閱設定。 在這個範例中，每一個子系標記會對應至下列其中一個可能輸出律師-委託人權限偵測模型。

4. 或者，您可以重新命名 [標記] 群組及子系標記。 例如，您無法重新命名**誤判**標記**特殊權限**和**負數**的標記，以**不特殊權限**。

## <a name="how-to-use-smart-tags"></a>如何使用智慧標籤

檢閱文件時, 模型的結果會顯示適當的子系標記旁。 例如，如果您有律師-委託人權限偵測的智慧標籤群組，且您檢閱可能特殊權限的文件，該結論的原因會顯示適當的標籤旁。 請務必注意，標籤不會自動套用至文件。 檢閱者進行決策來標記文件。