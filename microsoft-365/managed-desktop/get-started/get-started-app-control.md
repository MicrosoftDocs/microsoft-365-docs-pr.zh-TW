---
title: 快速入門應用程式控制
description: ''
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170686"
---
# <a name="get-started-with-app-control"></a>快速入門應用程式控制

在您的環境中啟用應用程式控制之前，請務必複查並瞭解[Microsoft 管理的桌面如何執行它](../service-description/app-control.md)和您的角色與責任。

Microsoft 受管理的桌面在取得安全基礎原則方面的難度更具挑戰性，以簡化應用程式控制。 您的 IT 管理員仍必須在測試環中測試您的應用程式，並檢查記錄檔是否有任何警告或錯誤。 若應用程式需要例外，您可以將要求歸檔，或 Microsoft 受管理的桌面作業可能會根據最先偵測的人員而定。

## <a name="initial-deployment-of-apps"></a>應用程式的初始部署

當您第一次部署應用程式時，Microsoft 受管理的桌面必須評估其目前的行為。 啟用應用程式控制的確切步驟取決於您的環境中是否已部署裝置。

### <a name="devices-already-in-use"></a>裝置已在使用中

如果已有至少一個 Microsoft 受管理的桌面裝置正在使用中，請遵循下列步驟：

1. 使用 Microsoft Managed Desktop Operations 開啟服務票證，以要求我們開啟應用程式控制。 作業會將[審核原則](../service-description/app-control.md#audit-policy)部署至所有裝置。
2. [測試您的應用程式](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app)，以查看是否有任何封鎖。 若應用程式遭到封鎖，請開啟 [[簽署者要求](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)]。 
3. 當您完成測試（任何結果）時，請通知作業，注意任何擱置的簽署者要求。 作業會逐步將原則部署到遵循此排程的部署群組：

|部署群組  |原則類型  |時程  |
|---------|---------|---------|
|測試     |  審計       |  Day 0       |
|名字     | Enforced        | 第 1 天        |
|快速     | Enforced        |  第 3 天       |
|廣泛     | Enforced        |  第 7 天       |

您可以隨時開啟另一個服務要求，以在部署期間隨時暫停或回退此部署的一部分。

### <a name="devices-not-yet-in-use"></a>尚未使用的裝置

若尚未使用任何裝置，請使用 Microsoft Managed Desktop Operations 開啟服務票證，以要求我們開啟應用程式控制。 作業會逐步將原則部署到遵循此排程的部署群組：

|部署群組  |原則類型  |時程  |
|---------|---------|---------|
|測試     |  審計       |  Day 0       |
|名字     | Enforced        | 第 1 天        |
|快速     | Enforced        |  第 3 天       |
|廣泛     | Enforced        |  第 7 天       |

您可以隨時開啟另一個服務要求，以在部署期間隨時暫停或回退此部署的一部分。

