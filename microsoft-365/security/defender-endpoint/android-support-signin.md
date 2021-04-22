---
title: 在 Android 上疑難排解 Microsoft Defender for Endpoint 上的問題
description: 在 Android 上疑難排解 Microsoft Defender for Endpoint 的問題
keywords: microsoft，defender，Microsoft Defender for Endpoint，mde，android，cloud，connectivity，通訊
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5f57d14427ef68280a065489e068955db9e5045a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934798"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Android 上 Microsoft Defender for Endpoint 的問題疑難排解

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

當您上架裝置時，您可能會在安裝應用程式之後看到 [登入] 問題。

在上架期間，您在裝置上安裝應用程式之後，您可能會遇到登入問題。

本文提供的解決方案可協助您解決登錄問題。  

## <a name="sign-in-failed---unexpected-error"></a>登入失敗-未預期的錯誤
登 **入失敗：未***預期的錯誤，請稍後再試*

![[登入失敗] 錯誤的圖像意外錯誤](images/f9c3bad127d636c1f150d79814f35d4c.png)

**消息：**

意外錯誤，請稍後再試

**原因：**

您的裝置上安裝了舊版本的「Microsoft 驗證者」應用程式。

**解決 方案：**

從 Google Play Store 安裝最新版本和 [Microsoft 驗證](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) 者，然後再試一次

## <a name="sign-in-failed---invalid-license"></a>登入失敗-不正確授權

登 **入失敗：** *不正確授權，請洽詢系統管理員*

![登入失敗的影像請洽詢系統管理員](images/920e433f440fa1d3d298e6a2a43d4811.png)

**訊息：** *授權無效，請與系統管理員聯繫*

**原因：**

您沒有指派 Microsoft 365 授權，或您的組織沒有 Microsoft 365 企業版訂閱的授權。

**解決 方案：**

請與您的系統管理員聯繫以取得協助。

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>有些 OEM 裝置上沒有封鎖網頁網路頁面

**適用于：** 僅限特定 Oem

-   **Xiaomi**

在某些 Xiaomi 裝置上，不會封鎖由 Defender for Android 的 Endpoint 所偵測到的網路釣魚和有害 web 威脅。 下列功能在這些裝置上無法運作。

![網站的圖像報告為不安全](images/0c04975c74746a5cdb085e1d9386e713.png)


**原因：**

Xiaomi 裝置包含新的許可權模型。 這可讓 Android 的 Defender Endpoint 在後臺執行時，不顯示快顯視窗。

Xiaomi 裝置許可權：「在後臺執行時顯示快顯視窗」。

![快顯視窗的圖像設定](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

**解決 方案：**

在 Xiaomi 裝置上啟用必要的許可權。

- 在背景中執行時，顯示快顯視窗。
