---
title: Microsoft 受管理的電腦應用程式需求
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1ca08e84bf27a64ba7515b6f4c0307c94621601c
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280101"
---
# <a name="microsoft-managed-desktop-app-requirements"></a>Microsoft 受管理的電腦應用程式需求

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
為了確保效能、 可靠性和服務性的 Microsoft 受管理的電腦裝置的商務應用程式的客戶的行必須不嚴重影響使用者體驗，或修改安全性轉變成為。 因此，您想要部署至 Microsoft 受管理的電腦裝置的商務應用程式必須符合本主題中的需求。

## <a name="application-condition"></a>應用程式的狀況

請務必應用程式不產生負面影響 Microsoft 受管理的桌上型電腦環境。 以下是要部署的應用程式的應用程式必須符合的需求。 對於任何指定應用程式或驅動程式，Microsoft 可能撤回提及提供任何需求。 Microsoft 可能決定要移除的任何應用程式或造成負面影響效能和可靠性的 Microsoft 受管理的電腦裝置的驅動程式。

## <a name="centrally-managed-apps"></a>集中管理的應用程式

透過 Microsoft Intune、 Microsoft 網上商店或 Microsoft 網上商店商務;，則必須部署所有應用程式和 Microsoft 受管理的裝置上安裝驅動程式如果有的話驅動程式也會透過 Windows Update 服務部署。 

## <a name="prohibited-app-classes"></a>禁止之應用程式的類別

Microsoft 受管理的電腦裝置上不允許特定應用程式類型：
- 3rd 廠商防病毒、 安全性或稽核軟體
- 在 Office 365 專業增強版之前的 Microsoft Office 版本
- 安裝或將彙整其他 3rd 廠商軟體應用程式

## <a name="restricted-app-behaviors"></a>受限制的應用程式行為

某些應用程式行為產生負面影響的使用者經驗，或可能呈現 Microsoft 受管理的電腦裝置安全性風險。 不允許沒有特定的 Microsoft 受管理電腦環境中執行從 Microsoft 應用程式具有下列行為。

使用者經驗：
- 安裝背景服務
- 將自己新增至 Windows 啟動路徑
- 取決於驅動程式的應用程式
- 3rd 廠商網頁瀏覽器

安全性：
- 提高使用者的權限
- 做為應用程式存放區，或具有內建的擴充管理員
- 有已知的安全性弱點
- 加密或限制存取使用者資料
- 是不帶正負號，或使用不會縮合至受信任的根憑證簽署


## <a name="driver-deployment"></a>驅動程式部署

Microsoft 受管理電腦只支援可透過 Windows Update 或收件匣隨 Microsoft 受管理裝置的裝置驅動程式。 

如果應用程式需要特定執行它的驅動程式會被視為受限制的應用程式，且需要部署至 Microsoft 受管理的電腦。 

