---
title: Microsoft Defender ATP 中已連線的應用程式
ms.reviewer: ''
description: View 使用 standard OAuth 2.0 通訊協定的已連接夥伴應用程式，以進行驗證，並提供標記以搭配 Microsoft Defender ATP APIs 使用。
keywords: 合作夥伴、應用程式、協力廠商、連接、sentinelone、注意、bitdefender、corrata、morphisec、paloalto、ziften、更佳行動裝置
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 294d6cfa5f8bf6b883c37e527cb492e8d65fc94c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163596"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint 中連線的應用程式

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

連接的應用程式會使用 APIs 與使用 Defender 的端點平臺整合。 

應用程式使用 standard OAuth 2.0 通訊協定來驗證及提供與 Microsoft Defender for Endpoint APIs 搭配使用的權杖。  此外，Azure Active Directory (Azure AD) 應用程式允許租使用者管理員設定可使用對應的應用程式存取 APIs 的明確控制。
 
您必須遵循 [下列步驟](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro) ，才能將 APIs 與連接的應用程式搭配使用。
 
## <a name="access-the-connected-application-page"></a>存取連線的應用程式頁面
從左導覽功能表中，選取 [**夥伴] & APIs**  >  **連接的 AAD 應用程式**。

 
## <a name="view-connected-application-details"></a>查看連接的應用程式詳細資料
[連線的應用程式] 頁面會提供連線至您組織中之端點之 Azure AD 應用程式的相關資訊。 您可以查看已連接之應用程式的使用狀況：上次查看時間、過去24小時內的要求數量，以及過去30天的要求趨勢。

![連接應用程式的影像](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>編輯、重新設定或刪除連接的應用程式
[ **開啟應用程式設定** ] 連結會在 azure 入口網站中開啟對應的 [Azure AD 應用程式管理] 頁面。 從 Azure 入口網站，您可以管理許可權、重新設定或刪除連接的應用程式。
