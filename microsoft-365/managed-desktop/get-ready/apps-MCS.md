---
title: 使用 Microsoft 諮詢服務
description: 使用 MCS 封裝應用程式的準備工作和步驟
keywords: Microsoft 受管理的電腦、Microsoft 365、服務、文件、應用程式、MCS、封裝
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 04b0c7905c83be2afa46abcfb2d4bb5cd9735e06
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909223"
---
# <a name="working-with-microsoft-consulting-services"></a>使用 Microsoft 諮詢服務

您可以與 Microsoft 諮詢服務 (MCS) 接洽，以便使用 Microsoft 受管理的電腦封裝您的應用程式。 如需確切的詳細資訊，請與您的客戶代表連絡 MCS，以定義特定應用程式封裝專案範圍。

## <a name="roles-and-responsibilities"></a>角色和責任

若要使用 MCS 應用程式封裝，**您必須提供下列項目**：

- 來源 installer 檔案 (例如，setup.exe 或 .msi) 。
- 安裝指示，指定安裝完成的外觀詳細資訊。 例如，應用程式應該有桌面快速鍵嗎？ 應用程式可見度應該為何？ 應用程式應該連線到伺服器嗎？若是如此，哪一個伺服器？ 如需詳細資訊，請參閱[應用程式封裝要求範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)。
- 您必須執行自己的接受度測試，以驗證此應用程式在您的環境中能夠正常運作。

**MCS 將處理下列動作：**

- 檢查此應用程式在 Microsoft 受管理的電腦環境中是否禁止或受限制。
- 測試安裝、啟動及解除安裝應用程式，以確保與 Windows 10 相容。 如果 MCS 發現相容性問題，會將應用程式交付到[桌面應用程式保證](/fasttrack/win-10-desktop-app-assure)以進行修復。
- 以您的規格封裝應用程式，然後使用 Microsoft Intune 測試應用程式部署。

## <a name="app-delivery-schedule"></a>應用程式交付排程

將應用程式資訊上傳到 Microsoft 受管理的電腦入口網站來啟動封裝程序。 封裝小組每星期四都會檢閱新的提交。 檢閱和封裝之後，封裝的應用程式會在下星期五交付。 一開始每週最多可以封裝五個應用程式，但能根據您的需求調整服務。

![行事曆顯示應用程式在星期四輸入 (在此範例中為 21 日)，第二天做媒體驗證，下星期一封裝 (25 日)，之後的星期五交付應用程式 (29 日)](../../media/MCS-cal.png)

應用程式交付之後，您會收到通知。 在該點，您有21天的時間可執行接受度測試，並核准 Microsoft 受管理的桌面入口網站中的工作。 如果您在接受度測試期間發現應用程式有些問題，請在 Microsoft 受管理的電腦入口網站中拒絕該應用程式，您將會透過電子郵件與 MCS 封裝程式連線，以了解並解決這個問題。

## <a name="testing-accounts-and-environment"></a>測試帳戶和環境

若要讓打包小組完成對 Microsoft Intune 的遷移，我們建議您提供某些許可權：
 
-   封裝程式的 Microsoft Intune App 部署功能的存取權，以新增並指派應用程式 
-   搭配封裝程式的測試群組、使用者帳戶和授權，以便能夠測試應用程式

MCS 將使用這些權限來執行下列動作：
 
-   確保應用程式能夠在 Microsoft 受管理的電腦設定之虛擬機器上正常運作
-   將應用程式上傳到 Microsoft Intune，以便部署至您的使用者

若沒有這些使用權限，MCS 可能會繼續進行，但無法將應用程式上傳到您的環境。