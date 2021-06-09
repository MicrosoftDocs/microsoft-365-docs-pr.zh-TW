---
title: 取代郵件加密檢視器應用程式
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 郵件加密 (OME) 檢視器應用程式已從2018中的 Android 和 Apple 書店中移除。
ms.openlocfilehash: bb96601a8a542d53f6732ab9316051c1a820ba46
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741520"
---
# <a name="deprecating-message-encryption-viewer-app"></a>取代郵件加密檢視器應用程式

在2018年8月15日，我們 Office 365 郵件加密 (OME) Viewer mobile app 從 Android 和 Apple 店鋪中移除。 需要有 Office 365 郵件加密檢視器行動裝置應用程式，才能閱讀使用 Apple 和 Android 手機上舊版 OME 加密的電子郵件訊息和附件。 除了移除 OME Viewer 應用程式之外，我們並未對舊版的 OME 進行其他任何變更。
  
## <a name="changes-from-august-2018"></a>自八月2018的變更

如 9 2017 月宣佈所宣佈，我們已發佈[Office 365 郵件加密](https://aka.ms/ome2017)的新版本，因此使用者可以將加密及受保護的郵件傳送給組織內部或外部的任何人，而不需要行動應用程式。 自那時起，我們已新增其他功能：
  
- [僅加密範本](https://aka.ms/encryptonly)

- [用於解密附件的控制項](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

使用此變更後，使用者將無法再從8月1日開始下載 Office 365 郵件加密檢視器行動應用程式。 因此，郵件收件者可能無法讀取某些 Android 和 Apple 行動裝置上舊版 OME 所加密的郵件。 不過，他們仍然可以在個人電腦上透過桌面瀏覽器)  (讀取這些郵件。 已下載應用程式的使用者仍可以使用該應用程式。
  
## <a name="why-this-change-was-made"></a>為何進行此變更

新版本的 OME 不再需要行動應用程式讀取受保護的電子郵件和附件。 使用新 OME 功能的客戶可以在 Outlook 行動裝置和非客戶可以在瀏覽器中查看受保護的郵件，以查看受保護的郵件。
  
要求使用者下載行動應用程式的另一個障礙是讓客戶能夠查看受保護的郵件。 新的 Office 365 郵件加密功能可提供更佳的移動體驗。
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>我仍然可以使用舊版的 Office 365 郵件加密

[！附注] 舊版本的 Office 365 郵件加密將不會被取代，但我們對新版本的 Office 365 郵件加密進行很重要的增強功能，這可讓使用者輕鬆地對機密資料進行加密及許可權保護，使其不需要使用者直接讀取 Outlook (桌面、行動和 web) 中的任何人。 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>我需要做什麼才能準備這項變更

如果您的組織目前將加密的附件傳送給需要 OME 檢視器應用程式的收件者，則應該更新您的檔和訓練資源。
  
建議您更新現有的 Exchange 郵件流程規則，以使用目前版本的 OME，讓您的組織能夠利用新的和改善的功能。 在您設定新的 OME 功能之後，收件者不需要 OME Viewer 應用程式，即可在行動裝置上讀取加密的郵件。
  
Microsoft 建議您在組織合理的情況時，安排移至新的 OME 功能。 如需相關指示，請參閱[Set up new Office 365 郵件加密功能](set-up-new-message-encryption-capabilities.md)。 如果您想要進一步瞭解新功能的運作方式，請參閱[Office 365 郵件加密](ome.md)。
  

