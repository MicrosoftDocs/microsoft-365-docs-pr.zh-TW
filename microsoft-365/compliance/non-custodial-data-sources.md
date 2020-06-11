---
title: 將非 custodial 資料來源新增至高級 eDiscovery 案例
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
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以將非 custodial 資料來源新增至高級 eDiscovery 案例，並在資料來源上保留。 非 custodial 資料來源會重新編制索引，因此會重新處理被視為部分索引的任何內容，使其完整且可快速搜尋。
ms.openlocfilehash: 618d39bfb7be6cd260c88cdf4c57501747f440f1
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695496"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>將非 custodial 資料來源新增至高級 eDiscovery 案例

在高級 eDiscovery 案例中，它不一定會符合您在案例中建立 Microsoft 365 資料來源與系統管理員的需求。 不過，您可能還需要將該資料與案例產生關聯，以便進行搜尋、將其新增至審閱集，以及加以審閱。 新功能稱為「*非 custodial 資料來源*」，可讓您將資料新增至案例，而不必將資料關聯至保管人。 它也會將相同的高級 eDiscovery 功能套用至可用於與保管人相關聯之資料的非 custodial 資料。 您可以套用至非 custodial 資料的兩個最實用功能是保留，並使用[高級索引](indexing-custodian-data.md)處理。

## <a name="add-a-non-custodial-data-source"></a>新增非 custodial 的資料來源

請遵循下列步驟，在高級 eDiscovery 案例中新增及管理非 custodial 的資料來源。

1. 在「**高級 eDiscovery**首頁」上，按一下您要新增資料的案例。

2. 在 [**來源**] 頁面上，按一下 [**資料位置**] 索引標籤，然後按一下 [**新增資料位置**]。

3. 按一下 [**新增資料位置**]，然後選擇您想要新增至案例的資料來源。 您可以新增多個信箱和網站。

4. 在嚮導的 [**選擇位置**] 頁面上，將信箱或網站（或兩者）新增為案例的非 custodial 資料來源。

5. 新增資料來源之後，請按 **[下一步]**。

6. 在 [**就地保留**] 頁面上，選取或取消選取相關的核取方塊，以選擇要保留的資料來源。

7. 確認 [保留] 選項，然後按一下 [**提交**]。

   您新增的每個非 custodial 資料來源都會列在 [**資料來源**] 頁面上。

   此外，在案例的 [**工作**] 索引標籤上會建立並顯示名為*重新編制索引非 custodial 資料*的工作。 在建立工作之後，起始的高級索引處理常式和資料來源都會重新編制索引。

## <a name="managing-the-hold-on-non-custodial-data-sources"></a>在非 custodial 資料來源上管理保留

在非 custodial 資料來源上進行保留後，會自動建立包含案例所有非 custodial 資料來源的保留原則。 當您放置其他非 custodial 資料來源時，會將它們新增至此保留原則。

1. 在案例的**首頁**上，按一下 [**保留**] 索引標籤。

2. 在 [**保留**] 頁面上，按一下 [ ** \<GUID\> NCDSHOLD**]，其中 GUID 值是唯一的案例。

3. 在飛入頁面上，按一下 [**編輯保留**]，以查看保留中的所有非 custodial 資料來源。

您可以在非 custodial 資料來源上執行下列管理工作：

- 您可以編輯 [保留]，以在案例中建立套用至所有非 custodial 資料來源的查詢型保留。

- 您可以從保留中釋放非 custodial 的資料來源。 釋放資料來源並不會從案例中移除非 custodial 資料來源。 它只會移除放在資料來源上的保留。
