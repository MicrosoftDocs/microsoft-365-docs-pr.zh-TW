---
title: 在 Advanced eDiscovery 中設定智慧標籤
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
description: 智慧標籤可讓您在 Advanced eDiscovery 案例中審閱內容時，套用機器學習功能。 使用智慧標籤群組來顯示機器學習偵測模型的結果，例如律師-用戶端許可權模型。
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081080"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>在 Advanced eDiscovery 中設定智慧標籤

Machine learning (ML) 功能 Advanced eDiscovery 可協助您在審閱集中查看案例檔時，讓決策過程更有效率。 智慧標籤是可讓決策記錄的 ML 功能：在複查期間為檔加上標籤的方式。 當您建立智慧標籤群組時，您與智慧標籤群組相關聯 ML 模型的結果會以單行顯示標籤群組中的標記。 這有助於您在查看特定檔時，以線上顯示 ML 結果資訊。

## <a name="how-to-set-up-a-smart-tag-group"></a>設定智慧標籤群組的方式

1. 在 [審閱集] 中，按一下 [ **管理複查集** ]，然後按一下 [ **管理標記**]。

2. 按一下 [ **新增標記群組** ]，然後選取 [ **新增智慧標籤群組**]。

3. 選取您要與標記群組產生關聯的 ML 模型。
    
   這會建立一個標記群組和 *N* 個子標記，其中 *N* 是模型的可能輸出數目。 例如， [律師-用戶端許可權偵測模型](attorney-privilege-detection.md) 有兩個可能的輸出： 

   - **正值** –用於標記包含律師費-用戶端許可權內容的檔。
   
   - **負數** –用於標記不含律師-用戶端許可權內容的檔。
    
    如果選取此模型，便會建立含有兩個子標記的標籤群組， (一個名為 **正值** 的子標記，另一個名為的 **負數**) 用於複查集。 在此範例中，每個子標記會對應至「律師-用戶端許可權偵測模型」的其中一個可能輸出。

4. 您也可以選擇性地重新命名 tag 群組和子標記。 例如，您可以將 **正值** 標籤重新命名為 **特權** 標籤，而 **否定** 標籤將不會有任何 **許可權**。

## <a name="how-to-use-smart-tags"></a>如何使用智慧標籤

當您審閱檔時，模型的結果會顯示在適當的子標記旁邊。 例如，如果您有用於律師-用戶端許可權偵測的智慧標籤群組，且您檢查了可能具有特權的檔，則該結論的原因會顯示在適當的標記旁邊。 請務必注意，標記不會自動套用至檔。 檢閱者會決定如何標記檔。
