---
title: 建立 iOS 裝置的 APNs 憑證
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
description: 以基本行動性和安全性管理 iOS 裝置。
ms.openlocfilehash: 8b41c1c6c891a5d6cb98a6a381c65aa0310a1761
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336795"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>建立 iOS 裝置的 APNs 憑證

若要管理基本行動性和安全性中的 iOS 裝置（例如 Ipad 和 Iphone），請建立 APNs 憑證。

1. 使用您的全域系統管理員帳戶登入 Microsoft 365。
    
2. 在您的瀏覽器中輸入  [https://protection.office.com](https://protection.office.com/) 。
    
3. 選取 [ **資料遺失防護**   >  **裝置管理**]，然後**為 iOS 裝置選擇 APNs 憑證**。    

4. 在 [Apple 推播通知憑證設定] 頁面上，選擇 **[下一步]**。
    
5. 選取 [下載您的 CSR 檔案]，然後將憑證簽署要求儲存至電腦上您所記得的地方。 選取  **[下一步]**。
    
6. 在 [建立 APNs 憑證] 頁面上：  

    1. 選取 Apple APNS 入口網站以開啟 Apple Push 憑證入口網站。
    
    2. Sign in with an Apple ID.   

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. 選取 [  **建立憑證**]   並接受 [使用條款]。
    
    4. 流覽至您從 Microsoft 365 下載到電腦的憑證簽署要求，然後選取 **[上傳**]。
    
        將 Apple Push Certificate 入口網站建立的 APNs 憑證下載至您的電腦。
    
       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. 回到 [Microsoft 365]，然後選取 [**下一步]**   進入 [  **上傳 APNS 憑證**]   頁面。
    
8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.
    
9. 選取  **[完成]**。
    
若要完成安裝程式，請回到安全性 & 規範中心 > **安全性原則**   >  **裝置管理**   >  **管理設定**。
