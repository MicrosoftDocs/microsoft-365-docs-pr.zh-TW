---
title: Exchange 多地理位置
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: 深入瞭解 Exchange Online 中的多地理位置功能，例如功能限制和信箱位置。
ms.openlocfilehash: 4c8f873039cd14251931125f5af2c04b7cbfe719
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694302"
---
# <a name="multi-geo-capabilities-in-exchange-online"></a>Exchange Online 中的多地理位置功能

在多地理位置環境中，您可以以每個使用者為基礎選取 Exchange Online 信箱內容 (待用資料) 的位置。

您可以透過以下方式，將信箱在衛星地理位置：

- 直接在衛星地理位置中建立新的 Exchange Online 信箱。

- 藉由變更使用者的慣用資料位置，將現有的 Exchange Online 信箱移至衛星地理位置。

- 從內部部署 Exchange 組織直接將信箱上線至衛星地理位置。

## <a name="mailbox-placement-and-moves"></a>信箱放置及移動

在 Microsoft 完成必要的多地理位置組態步驟之後，Exchange Online 會採用 Azure AD 中使用者物件上的 **PreferredDataLocation** 屬性。

Exchange Online 會從 Azure AD 將 **PreferredDataLocation** 屬性同步處理到 Exchange Online 目錄服務中的 **MailboxRegion** 屬性。 **MailboxRegion** 的值決定將放置使用者信箱和任何相關聯封存信箱所在的地理位置。 您無法將使用者的主要信箱和封存信箱設定位於不同地理位置。 每個使用者物件只能設定單一地理位置。

- 在具有現有信箱的使用者上設定 **PreferredDataLocation** 時，信箱將會放在重新配置佇列，並且會自動移至指定的地理位置。

- 在沒有現有信箱的使用者上設定 **PreferredDataLocation** 時，當您佈建信箱，會將信箱佈建到指定的地理位置。

- 未對使用者指定 **PreferredDataLocation** 時，當您佈建信箱，就會在中心地理位置佈建信箱。

- 如果 **PreferredDataLocation** 程式碼不正確 (例如，為 NAN，而不是) ，將會在中央地理位置中布建信箱。

**注意**：多地理位置功能和商務用 Skype Online 區域裝載的會議都使用使用者物件上的 **PreferredDataLocation** 屬性來尋找服務。 如果您在使用者物件上為區域裝載的會議設定 **PreferredDataLocation** 值，這些使用者的信箱將會於 Microsoft 365 租用戶上啟用多地理位置後，自動移到指定的地理位置。

## <a name="feature-limitations-for-multi-geo-in-exchange-online"></a>Exchange Online 中的多地理位置功能限制

- Exchange 系統管理中心 (EAC) 中提供的安全性與合規性功能 (例如，稽核與電子文件探索)，在多地理位置組織中無法使用。 相反地，您必須使用 [Microsoft 365 安全性與合規性中心](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8)來設定安全性與合規性功能。

- Mac 版 Outlook 使用者在您將他們的信箱移動到新地理位置時，可能會暫時無法存取其線上封存資料夾。 當使用者的主要信箱和封存信箱位於不同地理位置時，會發生此情況，因為跨地理位置信箱移動可能在不同的時間完成。

- 使用者無法在 Outlook 網頁版 (先前稱為 Outlook Web App 或 OWA) 中跨地理位置共用 *信箱資料夾*。 例如，歐盟的使用者無法使用 Outlook 網頁版來開啟位於美國信箱中的共用資料夾。 不過，如同[在另一個瀏覽器視窗中，使用 Outlook Web App 開啟另一個人的信箱](https://support.office.com/article/A909AD30-E413-40B5-A487-0EA70B763081#__toc372210362)中所述，Outlook 網頁版使用者可以使用不同的瀏覽器視窗來開啟不同地理位置的其他信箱。

  **注意**：Windows 上的 Outlook 中支援跨地理位置信箱資料夾共用。

- 多地理位置組織中支援公用資料夾。 不過，公用資料夾必須保持在中央地理位置。 您無法將公用資料夾移動至衛星地理位置。

- 在地理位置環境中，不支援跨地理位置信箱稽核。 例如，如果指派給使用者的權限可以存取不同地理位置的共用信箱，則該使用者執行的信箱動作不會記錄在共用信箱的信箱稽核記錄中。 如需詳細資訊，請參閱[管理信箱稽核](../compliance/enable-mailbox-auditing.md?view=o365-worldwide)。
