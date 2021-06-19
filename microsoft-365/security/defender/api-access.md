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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 03fd82cd5dc24653b6d67fa47cc225d355bfac45
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028796"
---
# <a name="access-the-microsoft-365-defender-apis"></a>存取 Microsoft 365 Defender APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用於：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 部分資訊與發行前版本產品有關，在正式發行之前可能會實質上進行修改。 Microsoft 對此處提供的資訊，不提供任何明確或隱含的瑕疵擔保。

Microsoft 365 Defender 會透過一組程式設計 APIs 來公開其大部分資料和動作。 這些 APIs 可協助您自動化工作流程，並充分利用 Microsoft 365 Defender 的功能。

一般來講，您必須採取下列步驟，才能使用 APIs：

- 建立 Azure Active Directory 應用程式
- 使用此應用程式取得存取 token
- 使用權杖存取 Microsoft 365 Defender API

> [!NOTE]
> API access 需要 OAuth 2.0 驗證。 如需詳細資訊，請參閱[OAuth 2.0 授權碼 Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

完成這些步驟之後，即可使用特定內容來存取 Microsoft 365 Defender API。

## <a name="application-context-recommended"></a>建議的應用程式內容 () 

在未登入使用者顯示的情況下，使用此內容來執行應用程式，例如背景服務或幕後程式。

1. 建立 Azure Active Directory 的 web 應用程式。
2. 將所需的許可權指派給應用程式。
3. 建立應用程式的索引鍵。
4. 使用 application 及其 key 取得安全性權杖。
5. 使用權杖存取 Microsoft 365 Defender API。

如需詳細資訊，請參閱 **[Create a app to access Microsoft 365 Defender （沒有使用者](api-create-app-web.md)**）。

## <a name="user-context"></a>使用者內容

使用此內容代表單一使用者執行動作。

1. 建立 Azure Active Directory 原生應用程式。
2. 將所需的許可權指派給應用程式。
3. 使用應用程式的使用者認證取得安全性權杖。
4. 使用權杖存取 Microsoft 365 Defender API。

如需詳細資訊，請參閱 **[建立應用程式，以代表使用者存取 Microsoft 365 Defender APIs](api-create-app-user-context.md)**。

## <a name="partner-context"></a>夥伴內容

當您需要跨 [多個承租人](/azure/active-directory/develop/single-and-multi-tenant-apps)向許多使用者提供應用程式時，請使用此內容。

1. 建立 Azure Active Directory 多租使用者應用程式。
2. 將所需的許可權指派給應用程式。
3. 從每個承租人取得應用程式的系統 [管理員同意](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) 。
4. 根據客戶的租使用者識別碼，使用使用者認證取得安全性權杖。
5. 使用權杖存取 Microsoft 365 Defender API。

如需詳細資訊，請參閱 **[Create a app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**。

## <a name="related-articles"></a>相關文章

- [Microsoft 365 DefenderAPIs 概述](api-overview.md)
- [OAuth 2.0 使用者登入和 API 存取的授權](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [使用 Azure Key Vault 管理伺服器應用程式中的機密](/learn/modules/manage-secrets-with-azure-key-vault/)
- [建立存取 Microsoft 365 的 "Hello world" 應用程式 APIs](api-hello-world.md)