---
title: 存取 Microsoft 365 Defender APIs
description: 瞭解如何存取 Microsoft 365 Defender APIs
keywords: access、api、application coNtext、user coNtext、aad 應用程式、存取權杖
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bf7a6a70cefda7bfac83d42f8e8dd6355c479914
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845011"
---
# <a name="access-the-microsoft-365-defender-apis"></a>存取 Microsoft 365 Defender APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender

>[!IMPORTANT] 
>一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


 Microsoft 365 Defender 會透過一組程式設計 APIs 來公開其大部分資料和動作。 這些 APIs 可讓您根據 Microsoft 365 Defender 功能來自動化工作流程及創新。 API 存取需要 OAuth 2.0 驗證。 如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。


一般來講，您必須採取下列步驟，才能使用 APIs：
- 建立 AAD 應用程式
- 使用此應用程式取得存取 token
- 使用權杖來存取 Microsoft 365 Defender API


您可以存取 Microsoft 365 Defender API with **Application coNtext** 或 **User coNtext** 。

- **應用程式內容：建議 ()** <br>
    由未登入使用者的執行中執行的應用程式所使用。 例如，以背景服務或守護程式形式執行的應用程式。

    必須採取的步驟，才能存取 Microsoft 365 Defender API 與應用程式內容：

  1. 建立 AAD Web 應用程式。
  2. 將所需的許可權指派給 applicationFor 範例（ **Incident）。全部** 、 **AdvancedHunting、read** 。 
  3. 建立此應用程式的索引鍵。
  4. 使用應用程式及其金鑰取得標記。
  5. 使用權杖來存取 Microsoft 365 Defender API

     如需詳細資訊，請參閱 [Get access with application coNtext](api-create-app-web.md)。


- **使用者內容：** <br>
    用來代表使用者在 API 中執行動作。

    必須採取的步驟，才能存取 Microsoft 365 Defender API 與應用程式內容：
  1. 建立 AAD 原生應用程式。
  2. 將所需的許可權指派給應用程式。 例如，AdvancedHunting **讀取、讀取** 。 **AdvancedHunting.Read**
  3. 使用具有使用者認證的應用程式取得權杖。
  4. 使用權杖來存取 Microsoft 365 Defender API

     如需詳細資訊，請參閱 [Get access with user coNtext](api-create-app-user-context.md)。


## <a name="related-topics"></a>相關主題
- [Microsoft 365 Defender APIs](api-supported.md)
- [使用應用程式內容存取 Microsoft 365 Defender](api-create-app-web.md)
- [使用使用者內容存取 Microsoft 365 Defender](api-create-app-user-context.md)
