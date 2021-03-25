---
title: 存取 Microsoft Defender for Endpoint APIs
ms.reviewer: ''
description: 瞭解如何使用 APIs，根據 Microsoft Defender ATP 功能自動化工作流程及創新
keywords: api，api，wdatp，open api，microsoft defender atp api，public api，支援的 api，警示，裝置，使用者，網域，ip，file，advanced 搜尋，查詢
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 70a8ba9d3ff864ca58c856714b00f0e8feba933a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164744"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>存取 Microsoft Defender for Endpoint APIs 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**適用於：** 
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



「！的 Defender」會透過一組程式設計 APIs 公開其資料和動作。 這些 APIs 可讓您以使用 Defender for Endpoint 功能來自動化工作流程及創新。 API 存取需要 OAuth 2.0 驗證。 如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

觀賞這段影片，以快速瞭解如何使用 Defender 的 Endpoint APIs。 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

一般來講，您必須採取下列步驟，才能使用 APIs：
- 建立 AAD 應用程式
- 使用此應用程式取得存取 token
- 使用權杖來存取適用于 Endpoint API 的 Defender


您可以使用 **應用程式內容** 或 **使用者內容**，存取適用于 Endpoint API 的 Defender。

- **應用程式內容：建議 ()** <br>
    由未登入使用者的執行中執行的應用程式所使用。 例如，以背景服務或守護程式形式執行的應用程式。

    必須採取的步驟，才能存取應用程式內容之 Endpoint API 的 Defender：

  1. 建立 AAD Web 應用程式。
  2. 將所需的許可權指派給應用程式，例如「讀取警示」、「隔離電腦」。 
  3. 建立此應用程式的索引鍵。
  4. 使用應用程式及其金鑰取得標記。
  5. 使用權杖來存取 Microsoft Defender ATP API

     如需詳細資訊，請參閱 [Get access with application coNtext](exposed-apis-create-app-webapp.md)。


- **使用者內容：** <br>
    用來代表使用者在 API 中執行動作。

    使用應用程式內容存取應用程式的 Endpoint API 時，所需採取的步驟：

  1. 建立 AAD 原生應用程式。
  2. 將所需的許可權指派給應用程式，例如「讀取警示」、「隔離電腦」等等。 
  3. 使用具有使用者認證的應用程式取得權杖。
  4. 使用權杖來存取 Microsoft Defender ATP API

     如需詳細資訊，請參閱 [Get access with user coNtext](exposed-apis-create-app-nativeapp.md)。


## <a name="related-topics"></a>相關主題
- [Microsoft Defender for Endpoint APIs](exposed-apis-list.md)
- [使用應用程式內容存取 Microsoft Defender for Endpoint](exposed-apis-create-app-webapp.md)
- [使用使用者內容存取 Microsoft Defender for Endpoint](exposed-apis-create-app-nativeapp.md)
