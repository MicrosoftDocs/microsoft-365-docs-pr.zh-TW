---
title: 管理 Microsoft 受管理電腦中的應用程式
description: 如何更新部署至 Microsoft 受管理的電腦裝置的線條營運應用程式的相關資訊
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation, Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600680"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>管理 Microsoft 受管理電腦中的行營運應用程式

<!--Application management -->

有幾種方式來管理應用程式在您上架到 Microsoft 受管理的電腦，並部署至您的 Microsoft 受管理的電腦裝置的應用程式更新。 您可以在 Microsoft 受管理電腦入口網站或 Intune 進行應用程式更新。 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>更新 Microsoft 受管理電腦中的行營運應用程式

**若要更新在 Microsoft 受管理電腦入口網站-營運應用程式**
1. 登入[Microsoft 受管理的桌上型電腦系統管理入口網站](https://aka.ms/mmdportal)。
2. 在 [**詳細目錄**] 下選取 [**應用程式**]。  
3. 選取您要更新的應用程式，然後選取 [**編輯**。
4. 在 [**管理**] 下選取 [**屬性**]。 
5. 按一下 [**應用程式套件檔案**，然後瀏覽至新的應用程式套件檔案上傳。
6. 選取 [**應用程式套件檔案**。
7. 選取 [資料夾] 圖示，然後瀏覽至您已更新的應用程式檔案的位置。 選取 [**開啟**]。 應用程式資訊會更新套件的資訊。
8. 確認**應用程式版本**會反映更新應用程式套件。 

更新應用程式會部署至使用者的裝置。

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>更新在 Intune 中的行營運應用程式

**若要更新您在 Intune 中的行營運應用程式**
1. 登入[Azure 入口網站](https://portal.azure.com)。
2. 選取 [**所有服務** > **Intune**。 Intune 會在**監視 + 管理**] 區段中。
3. 選取 [**用戶端應用程式 > 應用程式**。
4. 尋找並選取您的應用程式的應用程式] 清單中。
5. 在 [**概觀**] 刀鋒視窗中，選取**屬性**。
6. 選取 [**應用程式套件檔案**。
7. 選取 [資料夾] 圖示，然後瀏覽至您已更新的應用程式檔案的位置。 選取 [**開啟**]。 應用程式資訊會更新套件的資訊。
8. 確認**應用程式版本**會反映更新應用程式套件。

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>回復到舊版應用程式

如果沒有找到部署應用程式的新版本時的錯誤，您可以回復至先前的版本。 此處所述的程序是應用程式已列出類型為**Windows MSI-營運應用程式**或**Windows 應用程式 (Win 32)-預覽**

**若要回復為舊版-營運應用程式**

1. 登入[Microsoft 受管理的桌上型電腦系統管理入口網站](https://aka.ms/mmdportal)。
2. 在 [**詳細目錄**] 下選取 [**應用程式**]。  
3. 選取您要將回復，該應用程式，然後選取 [**編輯**。
4. 在 [**管理**] 下選取 [**屬性**]。 
    - **Windows MSI-營運應用程式**的應用程式，選取 [**應用程式資訊**]，然後在 [**略過 app 版本**] 中，選取 [**是]**。
    - **Windows 應用程式 (Win 32)-預覽**應用程式]，選取**應用程式資訊**，選取 [**偵測規則**]，然後選取 [**新增]**。 
    如果沒有 MSI 規則，確認**MSI 產品版本檢查**已設定為 [**否]**。
5. [將舊版的應用程式來源檔案上傳](../get-started/deploy-apps.md)至 Microsoft 受管理的桌上型電腦系統管理入口網站。  

