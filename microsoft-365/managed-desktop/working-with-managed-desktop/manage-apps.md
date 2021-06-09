---
title: 在 Microsoft 受管理的電腦中管理應用程式
description: 如何更新部署至 Microsoft 受管理的電腦裝置的企業營運應用程式的相關資訊
keywords: Microsoft 受管理的電腦, Microsoft 365, 服務, 文件
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
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Microsoft 受管理的電腦中管理企業營運應用程式

<!--Application management -->

有幾種方式可管理您已架 Microsoft 受管理的電腦並部署至 Microsoft 受管理的電腦裝置之應用程式的應用程式更新。 您可以在 Microsoft 受管理的電腦入口網站或 Intune 中進行應用程式更新。 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>更新 Microsoft 受管理的電腦中的企業營運應用程式

**若要更新 Microsoft 受管理的電腦入口網站中的企業營運應用程式**
1. 登入[Microsoft 受管理的電腦管理入口網站](https://aka.ms/mmdportal)。
2. 在 [ **庫存**] 下，選取 [ **應用程式**]。  
3. 選取您要更新的應用程式，然後選取 [ **編輯**]。
4. 在 [ **管理**] 下，選取 [ **屬性**]。 
5. 按一下 [ **應用程式套件** 檔案]，然後流覽以上傳新的應用程式套件檔案。
6. 選取 **應用程式套件** 檔案。
7. 選取 [資料夾] 圖示，並流覽至更新應用程式檔案的位置。 選取 [開啟]。 使用套件資訊更新應用程式資訊。
8. 請確認 **應用程式版本** 反映的是更新的應用程式套件。 

更新的應用程式會部署至使用者的裝置。

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>更新 Intune 中的企業營運應用程式

**若要更新 Intune 中的企業營運應用程式**
1. 登入 [Azure 入口網站](https://portal.azure.com)。
2. 選取 [**所有服務**]  >  **Intune**。 Intune 位於 **監控 + 管理** 區段中。
3. 選取 [ **用戶端應用程式] > 應用程式**。
4. 在應用程式清單中尋找並選取您的應用程式。
5. 在 [ **一覽** ] 邊欄中，選取 [ **屬性**]。
6. 選取 **應用程式套件** 檔案。
7. 選取 [資料夾] 圖示，並流覽至更新應用程式檔案的位置。 選取 [開啟]。 使用套件資訊更新應用程式資訊。
8. 請確認 **應用程式版本** 反映的是更新的應用程式套件。

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>將應用程式還原為先前版本

如果部署新版本的應用程式時發現錯誤，您可以復原至先前的版本。 此處所述的程式是針對其類型列為 **Windows MSI 營運應用程式** 或 Windows 應用程式的應用程式， **(Win 32) 預覽**

**將企業營運應用程式還原為繼承應用程式**

1. 登入[Microsoft 受管理的電腦管理入口網站](https://aka.ms/mmdportal)。
2. 在 [ **庫存**] 下，選取 [ **應用程式**]。  
3. 選取您需要回復的應用程式，然後選取 [ **編輯**]。
4. 在 [ **管理**] 下，選取 [ **屬性**]。 
    - 若為 **Windows MSI 的企業應用程式 app** ，請選取 [**應用程式資訊**]，然後在 [**忽略應用程式版本**] 底下，選取 **[是]**。
    - **Windows 應用程式 (Win 32) 預覽** 應用程式，選取 **[應用程式資訊**]，選取 [**偵測規則**]，然後選取 [**新增**]。 
    如果有 MSI 規則，請確認 **msi 產品版本檢查** 是否設為 [ **否**]。
5. [Upload 舊版本的應用程式原始檔案](../get-started/deploy-apps.md)Microsoft 受管理的電腦管理入口網站。  

