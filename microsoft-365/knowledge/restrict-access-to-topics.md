---
title: 限制存取 Microsoft Viva 主題中的主題
description: 如何排除主題以避免被探索。
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500873"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>限制存取 Microsoft Viva 主題中的主題

在 Microsoft Viva 中，您組織中的利益關係人可能會想要確定沒有找到特定主題，而且不會向您授權的使用者公開。 例如，您可能正在處理不想要公開其相關資訊的專案。 Office 365 網站、檔案及其他資源的許可權時，會讓使用者無法在主題中查看機密資訊，還有其他的防範措施可防止探索特定主題。

雖然知識系統管理員會控制設定以避免探索主題，但知識管理員及其他專案關係人必須知道其運作方式，這樣才能協同運作。

> [!Important] 
> 本文說明防止主題透過 AI 識別或在您的環境中另存為其他安全性保護的方式。 請務必注意，在 Viva 主題中，使用者不允許透過「Office 365 許可權」存取任何主題中的任何專案。 即使使用者可以查看主題，其檔案、網站和頁面也不會顯示其 Office 365 許可權給使用者。 確定正確設定敏感檔案的許可權應該是主要的安全性保護。

## <a name="prevent-topics-from-being-identified"></a>防止識別主題

知識管理員可以防止在初始編制索引中找到特定主題的存取權。 在 Microsoft 365 系統管理中心的 [Viva 主題管理員] 設定中，有兩種方式可以執行這項工作。
 
- [選取要從主題探索中排除的 SharePoint 網站](./topic-experiences-discovery.md#select-sharepoint-topic-sources)：您可以使用此設定來防止特定 SharePoint 網站在主題中進行編目。
- [依名稱排除主題](./topic-experiences-discovery.md#exclude-topics-by-name)：系統管理員可以使用此設定，以防止名稱探索特定主題。 在 Viva 主題管理員設定中，系統管理員可以上傳要排除在 CSV 檔案中的主題清單。 您可以排除具有主題名稱的確切或部分相符的主題。

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>防止特定使用者查看主題

知識系統管理員也可以 [選擇誰可以查看組織中的主題](./topic-experiences-knowledge-rules.md)。 此設定可讓您選取哪些授權的使用者可以查看所有主題。 例如，在試驗環境中，您可能只想讓一小組使用者能夠查看主題。

## <a name="remove-topics-from-being-viewed"></a>移除要查看的主題

知識管理員可以選擇 [移除主題](./manage-topics.md) ，讓使用者無法再看到這些主題。 在 **主題中心** 的 [**管理主題**] 頁面上，知識管理員可以選擇拒絕特定主題，以防止其被查看。 您可以移除主題，不論其是否處於建議或確認的狀態。

如有需要，您可以在以後將移除的主題重新加入為可查看的主題。 


## <a name="see-also"></a>請參閱



