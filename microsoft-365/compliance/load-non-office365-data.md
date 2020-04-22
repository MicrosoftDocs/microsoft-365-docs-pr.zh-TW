---
title: 將非 Microsoft 365 資料載入至證據
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 9eef3b38ceef7efc42e1f66c45069f51a0a95d45
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632628"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a>將非 Microsoft 365 資料載入至證據

在資料調查中，您可能需要分析的所有檔都不會位於 Microsoft 365。 使用非 Microsoft 365 內容匯入功能，您可以將不在 Microsoft 365 中的檔上傳至證據，以便在資料調查中進行分析。

## <a name="before-you-begin"></a>開始之前

使用此程式中所述的 [上傳非 Microsoft 365] 功能，您必須具備下列要求：

- Microsoft 365 或 Office 365 E5 訂閱。

- 將上傳非 Microsoft 365 內容的所有興趣人員，必須具有適當的 E5 或 E5 附加元件授權。

- 現有的 eDiscovery 案例。

- 所有檔案，可將收集到的資料夾中，每個保管人都有一個資料夾，而且資料夾的名稱為*alias@domainname*的此格式。 *Alias@domainname*必須是使用者的別名和網域。 您可以將所有*alias@domainname*資料夾收集至根資料夾。 根資料夾只能包含*alias@domainname*資料夾，根資料夾中一定沒有鬆散檔案。

- 一種帳戶，既可以是 eDiscovery 管理員，也可以是在具有非 Microsoft 365 內容資料夾結構存取權的電腦上安裝的 eDiscovery 管理員 Microsoft Azure Storage Tools。

- 安裝 AzCopy，您可以從這裡執行：https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a>將非 Microsoft 365 內容上傳至資料調查

1. 開啟**資料調查**，並前往將非 Microsoft 365 資料上傳至的調查。  按一下 [**證據**] 索引標籤，然後選取您想要將資料載入到其中的證據集。  如果您尚未建立證據集，現在可以這麼做。  最後，按一下 [**管理證據**]，然後在 [資料] 區段中**查看上傳**

2. 按一下 [**上傳**檔案] 按鈕，以啟動非 Microsoft 365 資料匯入嚮導。

![上傳檔案](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. 嚮導的第一個步驟只是為要上傳的檔案準備一個安全 Azure blob。  準備完成後，按一下 [**下一步：上傳檔案]** 按鈕。

![準備非 Microsoft 365 的資料匯入](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. 在 [**上傳**檔案] 步驟中，指定檔案的**位置路徑**，這是您規劃匯入的非 Microsoft 365 資料所在的位置。  設定正確的位置可確保 AzCopy 命令已正確更新。

> [!NOTE]
> 若尚未安裝 AzCopy，您可以從下列進行：https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

5. 按一下 [**複製至剪貼簿**] 連結，以複製預先定義的命令。 啟動 windows 命令提示字元，貼上命令，然後按 enter 鍵。  將檔案上傳至安全 Azure blob 儲存區，以進行下一個步驟。

![上傳非 Microsoft 365 資料匯入的檔案](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![使用 AzCopy 匯入非 Microsoft 365 資料](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. 最後，回到安全性 & 符合性，然後按一下 [**下一步：處理檔案]** 按鈕。  這會啟動上傳檔案的處理、文字提取及編制索引。  您可以在這裡或 [**工作**] 索引標籤中追蹤處理進度。 完成後，就會在證據集中使用新的檔案。  處理完成後，您可以關閉嚮導。

![非 Microsoft 365 Import 處理檔案](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

