---
title: 非 Office 365 資料載入辨識項
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: ee1e6f8a064567126d75b099cc3003e8a4d6a020
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/20/2019
ms.locfileid: "37077233"
---
# <a name="load-non-office-365-data-into-evidence"></a>非 Office 365 資料載入辨識項

並非所有文件，您可能需要與 Office 365 進階電子文件探索分析會存在於 Office 365 中。 使用非 Office 365 內容匯入您可以上傳文件與不存在於 Office 365 中插入工作集，它會使用進階電子文件探索分析的進階電子文件中的功能。 此程序將示範如何將非 Office 365 文件移入進階電子文件探索進行分析。

>[!Note]
>進階電子文件為您的組織需要與進階合規性附加元件或 E5 訂閱 Office 365 E3。 如果您不具有該計劃，並想要再試進階電子文件，您可以註冊 Office 365 企業版 E5 的試用版。

## <a name="before-you-begin"></a>開始之前
使用此程序所述的上傳非 Office 365 功能需要您：

- 使用進階合規性的附加元件或 E5 訂閱 Office 365 E3。

- 將上傳其非 Office 365 內容的所有 custodians 必須都擁有 E3 的進階合規性的附加元件或 E5 授權。

- 現有的 eDiscovery 案例。

- 上傳的所有檔案所都收集到資料夾，其中沒有 custodian 每一個資料夾，而且此格式*alias@domainname*中已有該資料夾的名稱。 *Alias@domainname*必須是 Office 365 的使用者別名及網域。 您可以收集所有*alias@domainname*資料夾到根資料夾。 根資料夾只能包含*alias@domainname*資料夾，必須有任何鬆散檔案的根資料夾中。

- EDiscovery 管理員或 eDiscovery 管理員 Microsoft Azure 儲存體工具具有存取權的非 Office 365 內容的資料夾結構的電腦上安裝帳戶。

- 安裝 AzCopy，您可以從這裡：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>非 Office 365 內容上傳至進階電子文件

1. EDiscovery 管理員或 eDiscovery 系統管理員，以開啟 [進階電子文件，然後將上傳到非 Office 365 資料的案例]。  按一下 [**工作集**] 索引標籤，然後選取您想要將非 Office 365 資料載入工作集。  如果您無法建立工作集，您可以立即執行。  最後，按一下 [**管理起步設定**然後非 Office 365 資料] 區段中的**檢視上傳**

2. 按一下 [**上傳檔案**] 按鈕來啟動非 Office 365 資料匯入精靈]。

![上傳檔案](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. 在精靈中的第一個步驟只會準備要上傳檔案的安全 Azure blob。  一旦準備 compelted 之後，按一下 [**下一步： 將檔案上傳**] 按鈕。

![非 Office 365 匯入-準備](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. 在 [**上傳檔案**] 步驟中，指定**的檔案位置路徑**] 中，這是您計劃匯入非 Office 365 資料所在的位置。  設定正確的位置可確保正確更新命令 AzCopy。

> [!NOTE]
> 如果您未安裝 AzCopy，您可以從這裡：https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. 按一下 [**複製到剪貼簿**] 連結，將複製的預先定義的命令。 啟動 windows 命令提示字元中，貼上命令並按 enter 鍵。  檔案就會上傳到安全的 Azure blob 儲存的下一個步驟。

![非-Office 365 匯入-上傳檔案](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![非 Office 365 匯入-AzCopy](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. 最後，傳回回到安全性 & 合規性，並按一下 [**下一步： 處理檔案**] 按鈕。  這將會引發處理、 文字擷取和編製索引的上傳的檔案。  您可以追蹤處理以下或在 [**工作**] 索引標籤中的進度。 完成之後，新的檔案則可在工作集。  處理完成後，您可以關閉精靈。

![非-Office 365 匯入的程序檔案](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

