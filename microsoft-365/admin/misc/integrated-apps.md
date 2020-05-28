---
title: 開啟或關閉整合式應用程式
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 深入瞭解整合式應用程式，以及如何將其開啟以允許協力廠商應用程式存取使用者的 Microsoft 365 資訊。
ms.openlocfilehash: 070150662daeefb2a4d02c7e0940dfd242bd4b5f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399335"
---
# <a name="turning-integrated-apps-on-or-off"></a>開啟或關閉整合式應用程式

啟用整合式應用程式時，您組織中的使用者可以允許協力廠商應用程式存取其 Microsoft 365 資訊。 例如，當有人使用協力廠商應用程式時，該應用程式可能會要求行事曆的存取權限，以編輯 OneDrive 資料夾中的檔案。

## <a name="turning-integrated-apps-on-or-off"></a>開啟或關閉整合式應用程式
<a name="__toc379982114"> </a>

以下說明如何開啟或關閉整合式應用程式。

1. 在 Microsoft 365 系統管理中心中，移至 [**設定**] [設定] 頁面的 [服務] 索引標籤 \> **Settings** \> **Services** ，然後選取 [**整合式應用程式**]。

2. 在 [**整合式應用程式**] 頁面上，選取要開啟或關閉整合式應用程式的選項。

## <a name="more-info-on-integrated-apps"></a>更多整合式應用程式的資訊
<a name="__toc379982114"> </a>

整合式應用程式可以從您自己的組織內部建立，也可以來自其他組織或協力廠商。

開啟整合式應用程式並使用應用程式時，應用程式會在其存取使用者的資訊時，要求設定其需要的存取層級的權限。 使用者只能將存取其 Microsoft 365 資訊的應用程式授與存取權。 他們無法讓應用程式存取任何其他使用者的資訊。

在 Microsoft 365 中使用整合式應用程式時，有兩種許可權會使用：使用者許可權和系統管理員許可權。 例如，當您的組織已啟用整合式應用程式，而使用者使用的是協力廠商應用程式，應用程式可能會要求使用者權限以讀取其使用者的設定檔詳細資料、編輯或刪除使用者檔案、讀取網站集合中包含的項目，並為使用者傳送電子郵件。

![整合式應用程式使用者權限](../../media/bb9a6cf8-da39-4ac0-9e40-cde03a81c121.gif)

若管理員為組織中的所有使用者註冊應用程式，則系統會要求使用者提供許可權，讓應用程式存取組織中的資訊和資源。 之後，當組織中的其他使用者使用該應用程式時，應用程式就不會向他們要求權限。 當管理員註冊應用程式時，管理員必須確定他們能信任該應用程式的發行者。 如需註冊應用程式的詳細資訊，請參閱[新增、更新與移除應用程式](https://go.microsoft.com/fwlink/p/?LinkID=518600)。

![整合式應用程式管理員權限](../../media/e24aa504-bf10-446c-a9d5-45a6f2655187.gif)

如果關閉整合式應用程式，已安裝並有存取資訊權限的應用程式不會解除安裝，權限也不會移除。 即使已關閉整合式應用程式，管理員仍然可以註冊應用程式，讓使用者使用它們，並允許這些應用程式存取使用者的相關資訊。 如需移除已註冊的應用程式與其權限的詳細資訊，請參閱 [新增、更新與移除應用程式](https://go.microsoft.com/fwlink/?LinkID=518600&amp;clcid=0x409)。


