---
title: 疑難排解 Microsoft Defender for Endpoint 中的 SIEM 工具整合問題
description: 疑難排解搭配 Microsoft Defender for Endpoint 使用 SIEM 工具時可能發生的問題。
keywords: 疑難排解、siem、用戶端密碼、機密
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 60220d00ca1b612564b72103b9206e3d6d89dc60
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689446"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>為 SIEM 工具整合問題疑難排解

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

在您的 SIEM 工具中提取偵測時，您可能需要對問題進行疑難排解。

此頁面提供疑難排解可能遇到之問題的詳細步驟。


## <a name="learn-how-to-get-a-new-client-secret"></a>瞭解如何取得新的用戶端密碼
如果您的用戶端密碼到期，或您已在啟用 SIEM 工具應用程式時，誤放了您所提供的副本，您將需要取得新的機密。

1. 登入 [Azure 管理入口網站](https://portal.azure.com)。

2. 選取 **[Azure Active Directory]**。

3. 選取您的租使用者。

4. 按一下 [ **應用程式註冊**]。 然後在 [應用程式] 清單中，選取應用程式。

5. 選取機 **碼** 區段，然後提供重要描述並指定金鑰有效期限。

6. 按一下 **儲存**。 會顯示機碼值。

7. 複製此值，並將其儲存在安全的位置。


## <a name="error-when-getting-a-refresh-access-token"></a>取得重新整理存取權杖時的錯誤
如果您嘗試在使用威脅智慧 API 或 SIEM 工具時取得重新整理權杖時遇到錯誤，您必須在 Azure Active Directory 中新增相關應用程式的回復 URL。

1. 登入 [Azure 管理入口網站](https://ms.portal.azure.com)。

2. 選取 **[Azure Active Directory]**。

3. 選取您的租使用者。

4. 按一下 [ **應用程式註冊**]。 然後在 [應用程式] 清單中，選取應用程式。

5. 新增下列 URL:
   - 歐盟的歐盟： `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`
   - 英國： `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`
   - 美國：  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` 。
 
6. 按一下 **儲存**。

## <a name="error-while-enabling-the-siem-connector-application"></a>啟用 SIEM 連接器應用程式時發生錯誤
如果您嘗試啟用 SIEM 連接器應用程式時遇到錯誤，請檢查瀏覽器的快顯封鎖器設定。 當您啟用功能時，它可能會封鎖所開啟的新視窗。




>想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a>相關主題
- [在 Microsoft Defender for Endpoint 中啟用 SIEM 整合](enable-siem-integration.md)
- [設定 ArcSight 以拉入 Microsoft Defender for Endpoint 偵測](configure-arcsight.md)
- [向 SIEM 工具提取偵測](configure-siem.md)
- [Microsoft Defender for Endpoint 偵測欄位](api-portal-mapping.md)
- [使用 REST API 提取 Microsoft Defender for Endpoint 偵測](pull-alerts-using-rest-api.md)
