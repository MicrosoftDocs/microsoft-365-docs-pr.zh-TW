---
title: 限制存取主題
description: 如何排除主題以避免被探索。
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698869"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a>限制對主題經驗中主題的存取權

在主題經驗中，您組織中的專案關係人可能會想要確定沒有探索特定主題，而且不會向您的授權使用者公開。 例如，您可能正在處理不想要公開其相關資訊的專案。 雖然 Office 365 網站、檔案及其他資源的許可權會讓使用者無法在主題中查看機密資訊，但還有其他一些防範措施可以避免探索特定主題。

雖然知識系統管理員會控制知識網路設定，以防止發現主題，但知識管理員及其他專案關係人必須知道這是如何進行的，如此才能協同運作。

> [!Important] 
> 本文說明防止主題透過 AI 識別或在您的環境中另存為其他安全性保護的方式。 請務必注意，在主題經驗中，如果使用者不允許透過 Office 365 許可權來存取任何專案，就不允許使用者在該主題中查看任何專案。 即使使用者可以查看主題，但他們的檔案、網站和頁面沒有可供查看的 Office 365 許可權。 確定正確設定敏感檔案的許可權應該是主要的安全性保護。

## <a name="prevent-topics-from-being-identified"></a>防止識別主題

知識管理員可以防止在初始編制索引中找到特定主題的存取權。 有兩種方法可在 Microsoft 365 系統管理中心的 [知識網路系統管理員設定] 中執行這項作業。
 
- [選取要從主題探索中排除的 SharePoint 網站](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)：您可以使用此設定來防止特定 SharePoint 網站在主題中進行編目。
- [依名稱排除主題](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)：系統管理員可以使用此設定，以防止名稱探索特定主題。 在 [知識網路系統管理員] 設定中，系統管理員可以上傳要排除在 CSV 檔案中的主題清單。 您可以排除具有主題名稱的確切或部分相符的主題。

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>防止特定使用者查看主題

知識系統管理員也可以 [選擇誰可以查看組織中的主題](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)。 此設定可讓您選取哪些授權的使用者可以查看所有主題。 例如，在試驗環境中，您可能只想讓一小組使用者能夠查看主題。

## <a name="remove-topics-from-being-viewed"></a>移除要查看的主題

知識管理員可以選擇 [移除主題](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) ，讓使用者無法再看到這些主題。 在 **主題中心** 的 [**管理主題**] 頁面上，知識管理員可以選擇拒絕特定主題，以防止其被查看。 您可以移除主題，不論其是否處於建議或確認的狀態。

如有需要，您可以在以後將移除的主題重新加入為可查看的主題。 


## <a name="see-also"></a>請參閱



  





