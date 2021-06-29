---
title: 關閉或刪除案例
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
description: 瞭解 Advanced eDiscovery 案例所支援的調查或法律案例關閉或刪除時會發生什麼情況。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: efbcbe34e6d7d8b564bcfa0cf9bbd8a1fbb59709
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194623"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>關閉或刪除 Advanced eDiscovery 案例

當 Advanced eDiscovery 案例支援的法律案例或調查完成時，您可以關閉或刪除案例。 您也可以重新開啟已關閉的案例。

## <a name="close-a-case"></a>關閉案例

以下是關閉 Advanced eDiscovery 案例時會發生的情況：

- 如果案例包含處於保留狀態的內容位置，將會關閉這些保留。 關閉關閉後，30天的寬限期 (稱為 *延遲保留*) 會套用到保留的內容位置。 這有助於防止內容立即刪除，並可讓系統管理員在延遲保留期間到期時，搜尋或復原將會永久刪除的內容。 如需詳細資訊，請參閱 [移除 eDiscovery 保留中的內容位置](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)。

- 將案例結案只會關閉與該案例相關聯的保留。 如果內容位置上有其他保留， (例如訴訟暫止、核心 eDiscovery 保留或不同 Advanced eDiscovery 案例的保留，) 仍會保留這些保留。

- 此案例仍會列在 Microsoft 365 合規性中心中的 [eDiscovery] 頁面上。 已關閉案例的詳細資料、保留、搜尋和成員都會保留。

- 您可以在關閉案例後進行編輯。 例如，您可以在 Advanced eDiscovery 中新增或移除成員、建立搜尋、匯出搜尋結果，以及準備用於分析的搜尋結果。 作用中案例與已關閉案例的主要差異在於，案例關閉時會關閉保留。

若要關閉案例：

1. 在 [進階電子文件探索]**** 頁面上，選取您想要關閉的案例。

2. 在 [設定]**** 索引標籤上，按一下 [案例資訊]**** 底下的 ****[選取]。

   ![在 Advanced eDiscovery 案例中存取案例資訊飛出頁面](..\media\AeDSelectCaseInformation.png) 

3. 在 [ **案例資訊** 飛出] 頁面的底部，按一下 [ **動作**]，然後按一下 [ **關閉案例**]。

   關閉程序最多可能需要 60 分鐘才會完成。

## <a name="reopen-a-closed-case"></a>重新開啟已關閉的案例

當您重新開啟 Advanced eDiscovery 案例時，在關閉案例時，任何已就地保留都不會自動復原。 在重新開啟案例之後，您必須移至 [ **保留** ] 索引標籤，並開啟先前的保留。 若要開啟保留，請加以選取以顯示飛出視窗頁面，然後將 [狀態]**** 切換開關設定為 ****[開啟]。

若要重新開啟已關閉的案例：

1. 在 [進階電子文件探索]**** 頁面上，選取您想要重新開啟的案例。

2. 在 [設定]**** 索引標籤上，按一下 [案例資訊]**** 底下的 ****[選取]。

3. 在 [ **案例資訊** 飛出] 頁面的底部，按一下 [ **動作**]，然後按一下 [ **重新開啟案例**]。

   最多可能需要60分鐘的時間，重新開啟程式才會完成。

## <a name="delete-a-case"></a>刪除案例

您可以刪除作用中和關閉的 Advanced eDiscovery 案例。 當您刪除案例時，也會刪除與該案例相關聯的所有元件，例如監管人清單、通訊、搜尋、檢閱集和匯出作業。 案例會從 Microsoft 365 合規性中心中 **Advanced eDiscovery** 頁面上的案例清單中移除。 您無法復原或重新開啟已刪除的案例。

> [!NOTE]
> 在資料外泄案例中，移除考核集內專案的唯一方法是刪除 Advanced eDiscovery 案例。 其他的「搜尋及清除」方法不會從審閱集中移除專案。

您必須先刪除與案例相關聯的 *所有* 保留，才可刪除案例 () 中或已關閉。 這包括刪除狀態為 **Off** 的保留。

若要刪除與案例相關聯的保留：

1. 在您要刪除的 Advanced eDiscovery 案例中，移到 [**保留**] 索引標籤。

2. 按一下您要刪除的保留。

3. 在飛入頁面上，按一下 [ **刪除保留**]。

若要刪除案例：

1. 在 [進階電子文件探索]**** 頁面上，選取您想要刪除的案例。

2. 在 [設定]**** 索引標籤上，按一下 [案例資訊]**** 底下的 ****[選取]。

3. 在 [ **案例資訊** 飛出] 頁面的底部，按一下 [ **動作**]，然後按一下 [ **刪除案例**]。

