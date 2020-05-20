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
description: 瞭解當已關閉或刪除高級 eDiscovery 案例所支援的調查或法律案例時，會發生什麼事。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e64f5cc0483129396a28cbf657778001e5d372a7
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292409"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>關閉或刪除高級 eDiscovery 案例

當高級 eDiscovery 案例所支援的法律案例或調查完成時，您可以關閉或刪除案例。 您也可以重新開啟已關閉的案例。

## <a name="close-a-case"></a>關閉案例

以下是當您關閉高級 eDiscovery 案例時會發生的情況：

- 如果案例包含保留的任何內容位置，將會關閉那些保留。 這可能會導致內容被使用者或自動化程式（如刪除原則）永久刪除或清除。

- 關閉案例只會關閉與該案例相關聯的保留。 如果有其他保留內容位置（例如訴訟暫止、核心 eDiscovery 保留，或來自不同高級 eDiscovery 案例的保留），則仍會保留這些保留。

- 此案例仍列在 Microsoft 365 規範中心的 eDiscovery 頁面上。 已關閉案例的詳細資料、保留、搜尋及成員都會保留。

- 您可以在關閉案例後進行編輯。 例如，您可以在高級 eDiscovery 中新增或移除成員、建立搜尋、匯出搜尋結果，以及準備用於分析的搜尋結果。 使用中案例和關閉案例之間的主要差異是關閉案例時關閉保留狀態。

若要關閉案例：

1. 在 [**高級電子**檔探索] 頁面上，選取您要關閉的案例。

2. 在 [**設定**] 索引標籤的 [**案例資訊**] 下，按一下 [**選取**]。

3. 按一下 [**關閉案例**]。

   完成關閉程式可能需要長達60分鐘的時間。

## <a name="reopen-a-closed-case"></a>重新開啟已關閉的案例

當您重新開啟高級 eDiscovery 案例時，在關閉案例時，任何已就地保留的保留都不會自動復原。 在重新開啟案例之後，您必須移至 [**保留**] 索引標籤，並開啟先前的保留。 若要開啟保留，請選取它以顯示飛入頁面，然後將**狀態**切換設定為 [**開啟**]。

若要重新開啟已關閉的案例：

1. 在 [**高級電子**檔探索] 頁面上，選取您要刪除的案例。

2. 在 [**設定**] 索引標籤的 [**案例資訊**] 下，按一下 [**選取**]。

3. 按一下 [**重新開啟案例**]。

   最多可能需要60分鐘的時間，重新開啟程式才會完成。

## <a name="delete-a-case"></a>刪除案例

您可以刪除現用和關閉的高級 eDiscovery 案例。 當您刪除案例時，所有與案例相關聯的元件（例如保管人清單、通訊、搜尋、複查集和匯出工作）都會遭到刪除。 案例會從 Microsoft 365 規範中心的 [**高級 eDiscovery** ] 頁面上的案例清單中移除。 您無法復原或重新開啟已刪除的案例。

> [!NOTE]
> 在資料外泄案例中，移除考核集內專案的唯一方法是刪除高級 eDiscovery 案例。 其他的「搜尋及清除」方法不會從審閱集中移除專案。

在您可以刪除案例之前（不論是作用中或已關閉），您必須先刪除與案例相關聯的*所有*保留。 這包括刪除狀態為**Off**的保留。

若要刪除與案例相關聯的保留：

1. 在您要刪除的高級 eDiscovery 案例中，移至 [**保留**] 索引標籤。

2. 按一下您要刪除的保留。

3. 在飛入頁面上，按一下 [**刪除保留**]。

若要刪除案例：

1. 在 [**高級電子**檔探索] 頁面上，選取您要刪除的案例。

2. 在 [**設定**] 索引標籤的 [**案例資訊**] 下，按一下 [**選取**]。

3. 按一下 [**刪除案例**]。
