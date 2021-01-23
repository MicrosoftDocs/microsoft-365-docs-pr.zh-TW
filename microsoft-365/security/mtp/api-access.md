---
title: 存取 Microsoft 365 Defender APIs
description: 瞭解如何存取 Microsoft 365 Defender APIs
keywords: access、api、application coNtext、user coNtext、aad 應用程式、存取權杖
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ea787adfba0afb425da5f6ea0f6609f96e06b378
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932151"
---
# <a name="access-the-microsoft-365-defender-apis"></a>存取 Microsoft 365 Defender APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

適用於：

- Microsoft 365 Defender

> [!IMPORTANT]
> 一些與 prereleased 產品相關的資訊，在正式發行之前，可能會受到大量修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender 會透過一組程式設計 APIs 來公開其大部分資料和動作。 這些 APIs 可協助您自動化工作流程，並充分利用 Microsoft 365 Defender 的功能。

一般來講，您必須採取下列步驟，才能使用 APIs：

- 建立 Azure Active Directory 應用程式
- 使用此應用程式取得存取 token
- 使用權杖來存取 Microsoft 365 Defender API

> [!NOTE]
> API access 需要 OAuth 2.0 驗證。 如需詳細資訊，請參閱 [OAuth 2.0 授權碼流程](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

完成這些步驟之後，即可使用特定內容來存取 Microsoft 365 Defender API。

## <a name="application-context-recommended"></a>建議的應用程式內容 () 

在未登入使用者顯示的情況下，使用此內容來執行應用程式，例如背景服務或幕後程式。

1. 建立 Azure Active Directory web 應用程式。
2. 將所需的許可權指派給應用程式。
3. 建立應用程式的索引鍵。
4. 使用 application 及其 key 取得安全性權杖。
5. 使用權杖來存取 Microsoft 365 Defender API。

如需詳細資訊，請參閱 **[Create a app to Access Microsoft 365 Defender （沒有使用者](api-create-app-web.md)**）。

## <a name="user-context"></a>使用者內容

使用此內容代表單一使用者執行動作。

1. 建立 Azure Active Directory 原生應用程式。
2. 將所需的許可權指派給應用程式。
3. 使用應用程式的使用者認證取得安全性權杖。
4. 使用權杖來存取 Microsoft 365 Defender API。

如需詳細資訊，請參閱 **[建立應用程式以代表使用者存取 Microsoft 365 Defender APIs](api-create-app-user-context.md)**。

## <a name="partner-context"></a>夥伴內容

當您需要跨 [多個承租人](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)向許多使用者提供應用程式時，請使用此內容。

1. 建立 Azure Active Directory 多方租使用者應用程式。
2. 將所需的許可權指派給應用程式。
3. 從每個承租人取得應用程式的系統 [管理員同意](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) 。
4. 根據客戶的租使用者識別碼，使用使用者認證取得安全性權杖。
5. 使用權杖來存取 Microsoft 365 Defender API。

如需詳細資訊，請參閱 **[Create a app with partner access To Microsoft 365 Defender APIs](api-partner-access.md)**。

## <a name="related-articles"></a>相關文章

- [Microsoft 365 Defender APIs 概述](api-overview.md)
- [OAuth 2.0 使用者登入和 API 存取的授權](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [使用 Azure Key Vault 管理伺服器應用程式中的機密](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [建立存取 Microsoft 365 APIs 的「Hello world」應用程式](api-hello-world.md)
