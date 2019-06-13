---
title: 使用 Microsoft 諮詢服務
description: 準備與步驟遵循以搭配使用 MCS 来封裝您的應用程式
keywords: Microsoft 受管理的電腦、 Microsoft 365、 服務、 文件、 應用程式，MCS，封裝
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 39a5102d045d9ed79b631a3b477bd1c72dea76de
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/12/2019
ms.locfileid: "34918720"
---
# <a name="working-with-microsoft-consulting-services"></a>使用 Microsoft 諮詢服務

您可以邀請與 Microsoft 諮詢服務 (MCS) 若要取得您封裝搭配 Microsoft 受管理的電腦使用的應用程式。 確切詳細資料，使用您的帳戶代表連絡 MCS 和您的特定應用程式封裝專案的範圍。

## <a name="roles-and-responsibilities"></a>角色和責任

若要搭配 MCS 應用程式封裝，**您必須提供下列項目**：

- 來源安裝程式檔案 （例如，setup.exe 或.msi）。
- 指定詳細資料的最終安裝應該看起來大概安裝指示。 例如，應該會有應用程式的桌面捷徑嗎？ 應用程式的可見性為何？ 應用程式連線至伺服器，並若是如此，哪一種？ <!--For details, see the [application packaging request template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx). -->
- 您必須執行您自己的接受度測試來確認應用程式在您的環境中的需要般運作。

**這些動作會負責 MCS:**

- 檢查應用程式會禁止或限制 Microsoft 受管理電腦環境中。
- 測試安裝、 啟動和解除安裝的應用程式，以確保與 Windows 10 相容性。 如果 MCS 」 會探索的相容性問題，他們會交給修復的[桌面應用程式保證](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure)程式應用程式。
- 封裝您的規格的應用程式，然後藉由使用 Microsoft Intune 來測試應用程式部署。

## <a name="app-delivery-schedule"></a>應用程式傳遞排程

啟動封裝程序將應用程式資訊上傳至 Microsoft 受管理電腦入口網站。 封裝小組會檢閱新的提交每個星期四。 檢閱並封裝之後, 的封裝應用程式會傳遞下列星期五。 最多五個應用程式每週可封裝開始，但服務可以調整以符合您的需求。

![顯示應用程式檢閱、 封裝，並傳遞日期的行事曆](images/MCS-cal.png)

一旦應用程式已送達，您就會收到通知。 此時，您必須 21 天關閉執行接受度測試並簽署 Microsoft 受管理電腦入口網站中的工作。 如果您接受度測試期間發現應用程式的一些問題拒絕 Microsoft 受管理電腦入口網站中的應用程式，您將了解及解決問題 MCS packager 與連線透過電子郵件。

## <a name="testing-accounts-and-environment"></a>測試帳戶和環境

針對封裝小組，以完成移轉至 Microsoft Intune 我們建議您提供特定的權限：
 
-   Microsoft Intune 應用程式部署功能來新增及指派應用程式封裝程式存取 
-   測試群組、 使用者帳戶和授權 packagers 能夠測試應用程式

MCS 會使用這些權限來執行下列動作：
 
-   確保虛擬機器設定為 Microsoft 受管理的電腦上都有適用於應用程式
-   將應用程式上傳至 Microsoft Intune 部署到您的使用者

沒有這些權限，很可能 MCS 往前移，但他們將無法上傳至您環境的應用程式。


