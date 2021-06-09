---
title: 將非 Microsoft 365 資料載入到檢閱集
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 瞭解如何在 Advanced eDiscovery 情況下，將非 Microsoft 365 資料匯入檢查集，以進行分析。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903499"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>將非 Microsoft 365 資料載入到檢閱集

不是所有需要在 Advanced eDiscovery 中分析的檔都位於 Microsoft 365 中。 運用進階電子文件探索中的非 Microsoft 365 資料匯入功能，您可以將不在 Microsoft 365 中的文件上傳至檢閱集。 本文說明如何將您的非 Microsoft 365 檔移入 Advanced eDiscovery 以進行分析。

## <a name="requirements-to-upload-non-office-365-content"></a>上傳非 Office 365 內容的需求

使用本文所述的上傳非 Microsoft 365 功能時，需要具備下列各項：

- 您要將非 Microsoft 365 內容關聯的所有保管人都必須指派適當的授權。 如需詳細資訊，請參閱[立即開始使用 Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses)。

- 現有的 Advanced eDiscovery 案例。

- 您必須先將保管人新增至案例，才能將非 Microsoft 365 資料上傳及關聯。

- 非 Microsoft 365 資料必須是進階電子文件探索支援的檔案類型。 如需詳細資訊，請參閱[進階電子文件探索中支援的檔案類型](supported-filetypes-ediscovery20.md)。

- 所有上傳到檢閱集的檔案都必須位於資料夾中，其中，每個資料夾分別與特定監管人相關聯。 這些資料夾的名稱必須使用下列命名格式：*alias@domainname*。 alias@domainname 必須是使用者的 Microsoft 365 別名和網域。 您可以收集根資料夾中的所有 alias@domainname 資料夾。 根資料夾只能包含 alias@domainname 資料夾。 不支援根資料夾中的鬆散檔案。

   您想要上傳的非 Microsoft 365 資料的資料夾結構，會類似下列範例：

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   在此案例中，abraham.mcmahon@contoso.com、jewell.gordon@contoso.com 和 staci.gonzalez@contoso.com 是保管人的 SMTP 位址。

   ![非 Microsoft 365 資料上傳資料夾結構](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- 指派給「eDiscovery 管理員」角色群組 (並新增為 eDiscovery 管理員) 的帳戶。

- 安裝在可存取非 Microsoft 365 內容資料夾結構的電腦上的 AzCopy v 8.1 工具。 若要安裝 AzCopy，請參閱[Windows 上的轉接 AzCopy 中的資料](/previous-versions/azure/storage/storage-use-azcopy)。 請務必在預設位置（ **% ProgramFiles (x86) % \ Microsoft SDKs\Azure\AzCopy**）安裝 AzCopy。 您必須使用 AzCopy app-v 8.1。 其他版本的 AzCopy 在 Advanced eDiscovery 中載入非 Microsoft 365 資料時可能無法運作。


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>Upload 非 Microsoft 365 內容寫入 Advanced eDiscovery

1. 以 eDiscovery 管理員或 ediscovery 管理員的身分開啟 Advanced eDiscovery，然後移至即將上傳非 Microsoft 365 資料的情況。  

2. 按一下 [**複查集**]，然後選取要上傳非 Microsoft 365 資料的複查集。  如果您沒有審校集，您可以建立一個。 
 
3. 在檢閱集中，按一下 [管理檢閱集 **]**，然後按一下 [非 Microsoft 365 資料 **]** 動態磚上的 [檢視上傳 **]**。

4. 按一下 [上傳檔案 **]** 以開始資料匯入精靈。

   ![上傳檔案](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   精靈的第一個步驟會準備由 Microsoft 提供的安全 Azure 儲存體位置，以供上傳檔案。  準備完成時，[下一步: 上傳檔案 **]** 按鈕會變成作用中。

   ![非 Microsoft 365 匯入：準備](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. 按 [下一步: 上傳 **]**。

6. 在 [ **Upload** 檔案] 頁面上，執行下列動作：

   ![非 Microsoft 365 匯入： Upload 檔案](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. 在 [檔案 **位置**] 方塊中，驗證或輸入根資料夾位置，您已在該位置儲存您想要上傳的非 Microsoft 365 資料。 例如，在 [ **開始之前] 區段** 中所顯示範例檔案的位置，您可以輸入 **%USERPROFILE\Downloads\nonO365**。 提供正確的位置，可確保路徑上顯示的 AzCopy 命令已正確更新。

   b. 按一下 [ **複製到剪貼簿** ]，複製方塊中所顯示的命令。

7. 啟動 Windows 命令提示字元，貼上您在上一個步驟中複製的命令，然後按 **enter** 啟動 AzCopy 命令。  在您開始命令之後，會將非 Microsoft 365 檔案上傳到在步驟4中準備的 Azure 儲存體位置。

   ![非 Microsoft 365 匯入： AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > 如先前所述，您必須使用 AzCopy app-v 8.1，以順利使用 **Upload** 檔案] 頁面上提供的命令。 如果提供的 AzCopy 命令失敗，請參閱[Advanced eDiscovery 中 AzCopy 疑難排解](troubleshooting-azcopy.md)。

8. 回到安全性 & 合規性中心，然後按一下 **[下一步：處理** 檔案]。  這會初始化上傳至 Azure 儲存體位置的非 Microsoft 365 檔案的處理、文字擷取和索引。  

9. 透過查看名為 [**將非 Microsoft 365 資料新增至審閱集**] 的工作，追蹤處理 [**處理** 檔案] 頁面或 [**工作**] 索引標籤上之檔案的進度。  工作完成後，會在 [檢查] 集中使用新的檔案。

   ![非 Microsoft 365 匯入：處理檔](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. 處理完成後，您可以關閉精靈。