---
title: Microsoft Viva Topics 角色
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: 深入瞭解 Viva 主題中的使用者角色。
ms.openlocfilehash: 6d93046a96b60779c3cd3bd6c6aa600cb443118f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917353"
---
# <a name="microsoft-viva-topics-roles"></a>Microsoft Viva Topics 角色 

當您在 Microsoft 365 環境中使用 Viva 主題時，您的使用者可以具備下列角色：
-   主題檢視器
-   主題參與者
-   知識管理員
-   知識管理

## <a name="topic-viewer"></a>主題檢視器

主題檢視器是您組織中可以查看其 SharePoint 現代網站中醒目提示的主題的使用者、Microsoft 搜尋透過 SharePoint 和 Office.com 及主題中心。 他們可以在主題頁面上查看主題的詳細資料。 

若要在主題檢視器中看到主題的突出顯示及其主題頁面，使用者必須：
-   由其 Microsoft 365 系統管理員[指派 Viva 主題授權](./set-up-topic-experiences.md#assign-licenses)。
-   允許具有主題的可見度。 這項工作是由 Microsoft 365 系統管理中心中的 [Viva 主題設定] 頁面上的知識系統管理員所完成。


## <a name="topic-contributors"></a>主題參與者

主題參與者是貴組織中的使用者，不僅具備主題檢視器的許可權，還可以編輯現有的主題或建立新的主題。 在 [curating] 主題頁面中，他們有一個重要的角色，可 (AI 或手動提供) ，以確保其品質。

具有主題投稿人許可權的使用者將會看到顯示在主題頁面上的 [ **編輯** ] 按鈕，讓他們可以進行更新及發佈主題。

主題參與者也可以透過主題中心建立併發布新主題。

若要建立及編輯主題，使用者必須：

-   由其 Microsoft 365 系統管理員[指派 Viva 主題授權](./set-up-topic-experiences.md#assign-licenses)。
-   [被指派許可權以建立及編輯主題](./topic-experiences-user-permissions.md#change-who-has-permissions-to-do-tasks-on-the-topic-center)。 這項工作是由 Microsoft 365 系統管理中心中的 [Viva 主題設定] 頁面上的知識系統管理員所完成。

## <a name="knowledge-managers"></a>知識管理員

知識管理員是管理組織中主題的使用者。  主題管理是透過主題中心的 [管理主題] 頁面進行，只對知識管理員顯示。

在 [管理主題] 頁面中，知識管理員可以執行下列工作：
-   查看 AI-建議的主題。
-   請查看主題，以確認這些主題有效。
-   移除您不希望使用者看到的主題。

此外，知識管理員也可以編輯現有的主題或建立新的主題。

若要管理主題，使用者必須：
-   由其 Microsoft 365 系統管理員[指派 Viva 主題授權](./set-up-topic-experiences.md#assign-licenses)。
-   [被指派管理主題](./topic-experiences-user-permissions.md#change-who-has-permissions-to-do-tasks-on-the-topic-center)) 的許可權。 這項工作是由 Microsoft 365 系統管理中心中的 [Viva 主題設定] 頁面上的知識系統管理員所完成。

具有良好整體知識的使用者可能是「知識管理員」角色的良好候選人。 這類人員可能不僅具備知道主題是否有效的知識，還可以知道公司內與這些主題相關的人員。


## <a name="knowledge-admins"></a>知識系統管理員

知識管理員是在您的 Microsoft 365 環境中設定及設定 Viva 主題的系統管理員。 他們也會在設定完成後管理 Viva 主題設定。 因為安裝和管理是在 Microsoft 365 系統管理中心完成，所以知識系統管理員角色需要您是 Microsoft 365 全域或 SharePoint 管理員。
在設定期間，知識管理員可以將 Viva 主題設定為：

-   選取要為主題編目的 SharePoint 網站。
-   選取哪些已授權的使用者可以查看主題 (主題檢視器) 。
-   選取要排除識別的主題。
-   選取可建立及編輯主題的授權使用者 (主題) 參與者。
-   選取可管理 (知識管理員相關主題的授權使用者) 。
-   為主題中心命名。

知識管理員必須能夠與組織中的所有 Viva 主題進行協調，以瞭解如何進行設定。 例如，如果新專案有機密資訊，則需要通知知識管理員，以確保不會對 SharePoint 網站進行編目，也不需要排除特定的主題名稱。


## <a name="see-also"></a>請參閱