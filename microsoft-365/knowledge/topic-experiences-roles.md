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
ms.openlocfilehash: 9f1d3667ee9eeb05201613c15dc360b2b006cecb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288068"
---
# <a name="microsoft-viva-topics-roles"></a>Microsoft Viva Topics 角色 

當您在 Microsoft 365 環境中使用 Viva 主題時，您的使用者可以具備下列角色：

- 主題檢視者
- 主題參與者
- 知識管理員
- 知識系統管理員

## <a name="topic-viewer"></a>主題檢視者

主題檢視器是您組織中可以查看其 SharePoint 新式網站中醒目提示的主題的使用者，Microsoft 搜尋透過 SharePoint 和 Office .com 和主題中心。 他們可以在主題頁面上查看主題的詳細資料。 

若要讓主題檢視者看到主題重點項目及其主題頁面，使用者必須：

- 由其 Microsoft 365 管理員[指派 Viva 主題授權](./set-up-topic-experiences.md#assign-licenses)。
- 獲准可看見主題。 這項工作是由 Microsoft 365 系統管理中心中的「Viva 主題設定」頁面的知識系統管理員所完成。

## <a name="topic-contributors"></a>主題參與者

主題參與者是貴組織中的使用者，不僅具有主題檢視者權限，還能編輯現有主題或建立新主題。 在 [curating] 主題頁面中，他們有一個重要的角色，可 (AI 或手動提供) ，以確保其品質。

具有主題投稿人許可權的使用者將會看到顯示在主題頁面上的 [ **編輯** ] 按鈕，讓他們可以進行更新及發佈主題。

主題參與者也可以透過主題中心建立及發佈新主題。

若要建立及編輯主題，使用者必須：

- 由其 Microsoft 365 管理員[指派 Viva 主題授權](./set-up-topic-experiences.md#assign-licenses)。
- [被指派許可權以建立及編輯主題](./topic-experiences-user-permissions.md)。 這項工作是由 Microsoft 365 系統管理中心中的「Viva 主題設定」頁面的知識系統管理員所完成。

## <a name="knowledge-managers"></a>知識管理員

知識管理員是在貴組織中管理主題的使用者。  主題管理是透過主題中心的 [管理主題] 頁面完成，只有知識管理員可以看到。

在 [管理主題] 頁面中，知識管理員可以執行下列工作：

- 檢視 AI 建議的主題。
- 請查看主題，以確認這些主題有效。
- 移除您不希望使用者看到的主題。

此外，知識管理員可以編輯現有的主題或建立新主題。

若要管理主題，使用者必須：

- 由其 Microsoft 365 管理員[指派 Viva 主題授權](./set-up-topic-experiences.md#assign-licenses)。
- [被指派管理主題](./topic-experiences-user-permissions.md)) 的許可權。 這項工作是由 Microsoft 365 系統管理中心中的「Viva 主題設定」頁面的知識系統管理員所完成。

具有良好整體知識的使用者可能是「知識管理員」角色的良好候選人。 這類人員可能不僅具備知道主題是否有效的知識，還可以知道公司內與這些主題相關的人員。

## <a name="knowledge-admins"></a>知識系統管理員

知識管理員是在您的 Microsoft 365 環境中設定及設定 Viva 主題的系統管理員。 他們也會在設定完成後管理 Viva 主題設定。 因為安裝和管理是在 Microsoft 365 系統管理中心中完成的，所以知識系統管理員角色需要您是全域 Microsoft 365 或 SharePoint 系統管理員。
在設定期間，知識管理員可以將 Viva 主題設定為：

- 選取要針對主題對哪些 SharePoint 網站進行編目。
- 選取哪些授權使用者可以檢視主題 (主題檢視者)。
- 選取哪些主題要排除免於識別。
- 選取哪些授權使用者可以建立和編輯主題 (主題參與者)。
- 選取哪些授權使用者可以管理主題 (知識管理員)。
- 為主題中心命名。

知識管理員必須能夠與組織中所有 Viva Topics 專案關係人協調，以了解如何進行設定。 例如，如果新專案有機密資訊，則需要通知知識管理員，以確保不會對 SharePoint 網站進行編目，也不需要排除特定的主題名稱。
