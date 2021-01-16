---
title: 疑難排解基本行動性和安全性
f1.keywords: NOCSH
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: 嘗試這些步驟來追蹤基本行動性和安全性問題
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876849"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>疑難排解基本行動性和安全性

如果您嘗試在基本行動及安全性登錄裝置時遇到問題，請嘗試在這裡的步驟來追蹤問題。 如果一般步驟未修正問題，請參閱其中一個後續章節，其中包含您的裝置類型的特定步驟。

## <a name="steps-to-try-first"></a>嘗試優先的步驟

若要開始，請檢查下列各項：

- 確定裝置尚未向其他行動裝置管理提供者（例如 Intune）註冊。

- 請確定裝置已設定為正確的日期和時間。

- 切換至裝置上的不同 WIFI 或蜂窩網路。

- 針對 Android 或 iOS 裝置，請在裝置上卸載並重新安裝 Intune 公司入口網站應用程式。 

## <a name="ios-phone-or-tablet"></a>iOS 電話或平板電腦

- 請確定您已設定 APNs 憑證。 如需詳細資訊，請參閱 [建立 iOS 裝置的 APNs 憑證](create-an-apns-certificate-for-ios-devices.md)。

- 在 ****   >  **[設定一般**   >  **設定檔 (] 或 [裝置管理)**] 中，確定尚未安裝管理設定檔。 如果是，請將其移除。

- 如果您看到錯誤訊息「裝置無法註冊，請登入 Microsoft 365，並確定包含 Exchange Online 的授權已指派給登入裝置的使用者。

- 如果您看到錯誤訊息「設定檔安裝失敗」，請嘗試下列其中一項：

    - 請確定 Safari 是裝置上的預設瀏覽器，而且 cookie 並未停用。

    - 重新開機裝置，然後流覽至 portal.manage.microsoft.com。 使用您的 Microsoft 365 使用者識別碼和密碼登入，並嘗試手動安裝設定檔。

## <a name="windows-rt"></a>Windows RT

- 確定您的網域已在 Microsoft 365 中設定，以使用基本行動性和安全性。 如需詳細資訊，請參閱 [設定基本行動性和安全性](set-up.md)。
    
- 請確定使用者正在選擇 [ **開啟**]，   而非選擇 [ **加入**]。

## <a name="windows-10-pc"></a>Windows 10 電腦

- 確定您的網域已在 Microsoft 365 中設定，以使用基本行動性和安全性。 如需詳細資訊，請參閱 [設定基本行動性和安全性](set-up.md)。
    
- 除非您有 Azure Active Directory Premium，否則請確定使用者正在選擇 [ **僅登錄裝置管理**   ]，而不是選擇 [ **連接]**。

## <a name="android-phone-or-tablet"></a>Android 手機或平板電腦

- 請確定裝置執行的是 Android 4.4 或更新版本。

- 請確定 Chrome 是最新的，且設定為預設瀏覽器。

- 如果您看到錯誤訊息「無法註冊此裝置」，請登入 Microsoft 365，並確定已將包含 Exchange Online 的授權指派給登入裝置的使用者。

- 檢查裝置上的通知區域，以查看是否有任何必要的使用者動作處於擱置狀態，如果是的話，請完成動作。