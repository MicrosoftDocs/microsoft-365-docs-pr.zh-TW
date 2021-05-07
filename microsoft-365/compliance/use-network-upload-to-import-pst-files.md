---
title: 使用網路上傳匯入組織的 PST 檔案
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 適用於系統管理員：了解如何使用網路上傳將多個 PST 檔案大量匯入 Microsoft 365 中的使用者信箱。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf7f471a4323c4c03f232e93d2f00b930e53aefe
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114339"
---
# <a name="use-network-upload-to-import-your-organizations-pst-files-to-microsoft-365"></a>使用網路上傳將組織的 PST 檔案匯入 Microsoft 365

> [!NOTE]
> 本文適用於系統管理員。 您是否正嘗試匯入 PST 檔案到自己的信箱？ 請參閱[從 Outlook .pst 檔案匯入電子郵件、連絡人和行事曆](https://go.microsoft.com/fwlink/p/?LinkID=785075)
  
以下是使用網路上傳將多個 PST 檔案大量匯入 Microsoft 365 信箱所需的逐步指示。 如需使用網路上傳將 PST 檔案大量匯入 Microsoft 365 信箱的常見問題集，請參閱[使用網路上傳將 PST 檔案匯入的常見問題集](./faqimporting-pst-files-to-office-365.yml#using-network-upload-to-import-pst-files)。
  
[步驟 1：複製 SAS URL 和安裝 AzCopy](#step-1-copy-the-sas-url-and-install-azcopy)

[步驟 2：將您的 PST 檔案上傳至 Microsoft 365](#step-2-upload-your-pst-files-to-office-365)

[(選用) 步驟 3：檢視已上傳的 PST 檔案清單](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[步驟 4：建立 PST 匯入對應檔案](#step-4-create-the-pst-import-mapping-file)

[步驟 5：建立 PST 匯入工作](#step-5-create-a-pst-import-job)

[步驟 6：篩選資料，並開始 PST 匯入工作](#step-6-filter-data-and-start-the-pst-import-job)

您只需執行步驟 1 一次就能將 PST 檔案匯入至 Microsoft 365 信箱。 執行上述步驟後，每當您要上傳及匯入整批的 PST 檔案時，請遵循步驟 2 到步驟 6 的指示操作。

## <a name="before-you-import-pst-files"></a>在您匯出 PST 檔案之前
  
- 您必須在 Exchange Online 中獲派信箱匯入匯出角色，才能將 PST 檔案匯入 Microsoft 365 信箱。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 您可以將信箱匯入匯出角色新增到組織管理角色群組。 或者，可以建立角色群組、指派信箱匯出匯入角色，然後將自己新增為成員。 如需詳細資訊，請參閱[管理角色群組](/Exchange/permissions-exo/role-groups)之＜新增角色至角色群組＞或＜建立角色群組＞一節。

    此外，若要在安全性與合規性中心建立匯入工作，必須符合以下其中一個條件：

  - 您必須在 Exchange Online 中受指派為 [郵件收件者] 角色。根據預設，此角色會指派給 [組織管理] 與 [收件者管理] 角色群組。

    或者

  - 您必須是組織中的全域系統管理員。

  > [!TIP]
    > 建議您在 Exchange Online 中建立新的角色群組，專門用來匯入 PST 檔案。若需要匯入 PST 檔案所需的最低權限等級，請將 [信箱匯入匯出] 及 [郵件收件者] 角色指派到新的角色群組，然後新增成員。
  
- 將 PST 檔案匯入 Microsoft 365 的唯一支援的方法是使用 AzCopy 工具，如本主題中所述。 您無法使用 Azure 儲存體總管直接將 PST 檔案上傳至 Azure 儲存體區域。

- 您必須將要欲匯入至 Microsoft 365 的 PST 檔案儲存於檔案伺服器上，或是貴組織的共用資料夾。 在步驟 2 中，您會執行 AzCopy 工具，以將儲存於檔案伺服器或是共用資料夾上的 PST 檔案上傳至 Microsoft 365。

- 大型 PST 檔案可能會影響 PST 匯入程序的效能。 我們建議您在步驟 2 中上傳到 Azure 儲存位置的每個 PST 檔案都不應超過 20 GB。

- 此程序包含複製及儲存包含存取金鑰的 URL 複本。 此資訊將在步驟 2 中用於上傳 PST 檔案，如果要檢視上傳到 Office 365 的 PST 檔案清單，則會在步驟 3 中使用。 請務必採取預防措施來保護此 URL，就如同您保護密碼或其他安全性相關資訊一樣。 例如，您可能會將其儲存於受密碼保護的 Microsoft Word 文件內，或是儲存於已加密的 USB 磁碟機中。 請參閱[相關資訊](#more-information)一節，以取得此 URL 和金鑰組合的範例。

- 您否可以將 PST 檔案匯入 Office 365 中的非作用中信箱。 您可以透過在 PST 匯入對應檔案的 `Mailbox` 參數中指定非作用中信箱的 GUID 來執行此操作。 如需詳細資訊，請參閱本主題中 **指示** 索引標籤上的步驟 4。 

- 您可以在 Exchange 混合部署中為主要信箱位於內部部署的使用者，將 PST 檔案匯入雲端型封存信箱。 您可以透過在 PST 匯入對應檔案中執行以下操作來進行：

  - 在 `Mailbox` 參數中指定使用者內部部署信箱的電子郵件地址。

  - 在 `IsArchive` 參數上指定 **TRUE** 值。

    如需詳細資訊，請參閱[步驟 4](#step-4-create-the-pst-import-mapping-file)。

- 匯入 PST 檔案之後，信箱的暫停保留設定會開啟為無限期。 這表示在關閉暫停保留或設定日期來關閉暫停之前，系統不會處理指派給信箱的保留原則。 為什麼這麼做？ 如果匯入信箱的郵件是舊郵件，則可能會被永久刪除 (清除)，因為根據信箱設定的保留設定，這些郵件的保留期限已過期。 將信箱置於暫停保留狀態可讓信箱擁有者有時間管理這些新匯入的郵件，或者讓您有時間變更信箱的保留設定。 有關管理暫停保留的建議，請參閱本主題中的[相關資訊](#more-information)章節。

- 根據預設，Microsoft 365 信箱可接收的郵件大小上限為 35 MB。 這是因為信箱的 *MaxReceiveSize* 屬性的預設值設定為 35 MB。 然而，Microsoft 365 中的接收郵件大小上限為 150 MB。 因此，如果匯入的 PST 檔案包含大於 35 MB 的項目，Office 365 匯入服務將自動將目標信箱上的 *MaxReceiveSize* 的屬性值變更為 150 MB。 這樣就可將最大 150 MB 的郵件匯入使用者信箱。

    > [!TIP]
    > 若要辨識信箱的郵件接收大小，可以在 Exchange Online PowerShell 中執行此命令：`Get-Mailbox <user mailbox> | FL MaxReceiveSize`。

- 如需有關 PST 匯入程序的進階概覽，請參閱本文中 [匯入程序的運作方式](#how-the-import-process-works)一節。

## <a name="step-1-copy-the-sas-url-and-install-azcopy"></a>步驟 1：複製 SAS URL 和安裝 AzCopy

第一個步驟是下載並安裝 AzCopy 工具，這是您在步驟 2 中將 PST 檔案上傳至 Office 365 所執行的工具。 您也會複製組織的 SAS URL。 此 URL 結合了組織的 Microsoft 雲端中，Azure 儲存體位置的網路 URL 和共用存取簽章 (SAS) 金鑰。 此金鑰提供您將 PST 檔案上傳至 Azure 儲存體位置所需要的權限。 請務必採取預防措施來保護 SAS URL。 其對您的組織來說獨一無二，並將用於步驟 2。

> [!IMPORTANT]
> 若要使用本文中記錄的網路上傳方法和命令語法來匯入 PST 檔案，您必須使用可在以下程序之步驟 6b 中下載的 AzCopy 版本。 您也可以從[這裡](https://aka.ms/downloadazcopy)下載該相同版本的 AzCopy。 不支援使用不同版本的 AzCopy。
  
1. 前往 [https://protection.office.com](https://protection.office.com)，然後使用您組織中系統管理員帳戶的認證來登入。

2. 在「安全性與合規性中心」的左窗格中，按一下 **[資料控管]** \> **[匯入]** \> **[匯入 PST 檔案]**。

    > [!NOTE]
    > 您必須獲派適當的權限，才能存取 [安全性與合規性中心] 中的 [匯入] 頁面。 如需詳細資訊，請參與 **開始之前** 這一節。 

3. 按一下 **[匯入 PST 檔案]** 頁面上的 ![[新增圖示]](../media/ITPro-EAC-AddIcon.gif) **[新增匯入工作]**。

    即會顯示匯入工作精靈。

4. 為 PST 匯入工作輸入名稱，然後按一下 [下一步]。 請使用小寫字母、數字、連字號和底線。 無法使用大寫字母，且名稱中不得包含空格。

5. 在 [您要上傳或傳送資料？] 頁面上、按一下 [上傳您的資料]，然後按一下 [下一步]。

    ![按一下 [上傳您的資料] 來建立網路上傳匯入工作。](../media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. 在 [匯入資料] 頁面上，執行以下兩個動作：

    ![在 [匯入資料] 頁面上複製 SAS URL 並下載 AzCopy 工具](../media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    1. 在步驟 2，按一下 [顯示網路上傳 SAS URL]。 顯示 SAS URL 後，按一下 [複製至剪貼簿] 然後貼上，並儲存到檔案中以便日後存取。

    2. 在步驟 3，按一下 **[下載 Azure AzCopy]** 以下載並安裝 AzCopy 工具。 在快顯視窗中，按一下 [執行] 來安裝 AzCopy。

   > [!NOTE]
   > 您可以讓 [匯入資料] 頁面保持開啟 (以防您需要再次複製 SAS URL) 或按一下 [取消] 來關閉。 

## <a name="step-2-upload-your-pst-files-to-office-365"></a>步驟 2：將您的 PST 檔案上傳至 Office 365

現在您已準備好使用 AzCopy.exe 工具將 PST 檔案上傳至 Office365。 此工具會上傳並儲存 PST 檔案至 Microsoft 雲端內的 Azure 儲存體位置。 如之前所說明，上傳 PST 檔案的 Azure 儲存位置與組織所在的地區性 Microsoft 資料中心是同一個。 若要完成此步驟，PST 檔案必須位於組織的檔案共用內或檔案伺服器中。 這就是此程序中所謂的來源目錄。 每次執行 AzCopy 工具時，您可指定不同的來源目錄。

> [!NOTE]
> 如之前所述，在步驟 2 中上傳到 Azure 儲存位置的每個 PST 檔案都不應超過 20 GB。 大於 20 GB 的 PST 檔案可能會影響您在步驟 6 中啟動的 PST 匯入程序效能。 此外，每個 PST 檔案都必須有一個唯一名稱。

1. 在您的本機電腦上開啟 [命令提示字元]。

2. 移至您在步驟 1 中安裝 AzCopy.exe 工具的目錄。 如果您將工具安裝於預設位置，請前往 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`。

3. 執行下列命令將 PST 檔案上傳至 Office365。

    ```powershell
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
    ```

    > [!IMPORTANT]
    > 您必須在上一個命令中指定目錄作為來源位置；您無法指定個別 PST 檔案。 系統會上傳來源目錄中的所有 PST 檔案。

    下表說明了 AzCopy.exe 參數與其需要的值。 您在先前步驟中所取得的資訊，會在這些參數內的值中使用。

    | 參數 | 描述 | 範例 |
    |:-----|:-----|:-----|
    | `/Source:` <br/> |指定貴組織內的來源目錄，而其包含將上傳至 Office365 的 PST 檔案。  <br/> 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |指定您在步驟 1 中所取得的 SAS URL。  <br/> 請務必使用雙引號 (" ") 括住此參數的值。<br/><br/>**注意事項：** 如果您在指令碼或批次檔案中使用 SAS URL，必須注意需要逸出的特定字元。 例如，您必須將 `%` 變更為 `%%`，並且將 `&` 變更為 `^&`。<br/><br/>**秘訣：**(可選) 您可以在 Azure 儲存體位置指定子資料夾以上傳 PST 檔案。 您可以透過在 SAS URL 中新增子資料夾位置 (在 “ingestiondata” 之後) 來執行此操作。 第一個範例未指定子資料夾。 這表示 PST 將會上傳到 Azure 儲存體位置的根目錄 (名為 *ingestiondata*)。 第二個範例會將 PST 檔案上傳到 Azure 儲存體位置的根目錄的子資料夾中 (名為 *PSTFiles*)。  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> 或  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |將詳細狀態訊息輸出到記錄檔。根據預設，在 %LocalAppData%\Microsoft\Azure\AzCopy 中，詳細資訊記錄檔的名稱為 AzCopyVerbose.log。如果您在此選項中指定現有檔案位置，詳細資訊記錄檔會附加至該檔案。  <br/> 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |此選擇性參數會指定遞迴模式，因此 AzCopy 工具會複製位於來源目錄之子資料夾下的 PST 檔案，該來源目錄是由 `/Source:` 參數所指定。  <br/> **注意：** 若您包含此參數，在上傳完成後，子資料夾中的 PST 檔案將在 Azure 儲存體位置中具有不同的檔案路徑名稱。 您將必須在於步驟 4 中建立的 CSV 檔案中，指定確切的檔案路徑名稱。  <br/> | `/S` <br/> |
    | `/Y` <br/> |當將 PST 檔案上傳到 Azure 儲存體位置時，此必要參數可允許使用唯寫 SA 權杖。 您在步驟 1 中取得的 SAS URL (並由 `/Dest:` 參數指定) 就是唯寫 SA URL，因此您必須包含此參數。 唯寫 SA URL 不會防止您使用 Azure 儲存體總管來檢視上傳到 Azure 儲存體位置的 PST 檔案清單。  <br/> | `/Y` <br/> |

這是 AzCopy.exe 工具針對各個參數使用實際值的語法範例︰

```powershell
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
```

在您執行命令後，便會顯示 PST 檔案上傳進度的狀態訊息。最終狀態訊息會顯示已成功上傳的檔案總數。

> [!TIP]
> 在您成功地執行 AzCopy.exe 命令，且確認所有的參數皆正確之後，將命令列語法複本儲存至相同的 (受保護) 檔案內，也就是您在步驟 1 複製所取得資訊的檔案。 每當您想要執行 AzCopy.exe 工具將 PST 檔案上傳至 Office365 時，您就可以複製此命令並在「命令提示字元」內貼上。 唯一您可能需要變更的值，就是 `/Source:` 參數的值。 這視 PST 檔案所在的來源目錄而定。

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>(選用) 步驟 3：檢視上傳到 Office 365 的 PST 檔案清單

這是一個選擇性的步驟，您可以安裝並使用 Microsoft Azure 儲存體總管 (這是免費的開放原始碼工具) 來檢視您已上傳到 Azure blob 的 PST 檔案清單。執行這項作業有兩個好處：
  
- 確認您組織中共用資料夾或檔案伺服器的 PST 檔案已成功上傳到 Azure blob。

- 確認每個上傳到 Azure blob 之 PST 檔案的檔名 (以及子資料夾路徑名稱，如果您有採用)。 當您要在下一個步驟中建立 PST 對應檔案時，這項功能很有幫助，因為您必須指定每個 PST 檔案的資料夾路徑名稱及檔名。 驗證這些名稱有助於減少 PST 對應檔中的潛在錯誤。

Microsoft Azure 儲存體總管位於 [預覽] 中。
  
> [!IMPORTANT]
> 您無法使用 Azure 儲存體總管來上傳或修改 PST 檔案。 使用 AzCopy 來匯入 PST 檔案是唯一支援的方法。 此外，您無法刪除已上傳到 Azure Blob 的 PST 檔案。 如果您嘗試刪除 PST 檔案，您會收到沒有必要權限的相關錯誤。 請注意，所有的 PST 檔案會自動從您的 Azure 儲存體刪除。 如果目前沒有進行中的匯入工作，則 **ingestiondata** 容器中的所有 PST 檔案都會在最近的匯入工作建立完成後 30 天刪除。
  
若要安裝 Azure 儲存體總管並連線到您 Azure 儲存體區域：
  
1. 下載並安裝 [Microsoft Azure 儲存體總管工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。

2. 開始使用 Microsoft Azure 儲存體總管。

3. 在 **連線至 Azure 儲存體** 對話方塊的 **選取資源** 頁面上，按一下 **Blob 容器**。
  
4. 在 **[選取驗證方法]** 頁面上，選取 **[共用存取簽章 (SAS)]** 選項，然後按一下 **[下一步]**。

5. 在 **[輸入連線資訊]** 頁面上，將步驟 1 中取得之 SAS URL 貼到 **Blob 容器 SAS URL** 下的方塊中，然後按一下 **[下一步]**。 貼上 SAS URL 之後， **[顯示名稱]** 下的方塊便會自動填入 **Ingestiondata**。

6. 在 **[摘要]** 頁面上，您可檢閱連線資訊、然後按一下 **[連線]**。

    **Ingestiondata** 容器已開啟。 其中包含您在步驟 2 中上傳的 PST 檔案。 **Ingestiondata** 容器位於 **[儲存體帳戶]** \> **(附加容器)** \> **[Blob 容器]** 底下。 
  
7. 當您使用 Microsoft Azure 儲存體總管完成後，以滑鼠右鍵按一下 [ingestiondata]，然後按一下 [中斷連線] 來中斷 Azure 儲存體區域的連線。 否則，您會在下一次嘗試附加時收到錯誤。
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>步驟 4：建立 PST 匯入對應檔案

在已為貴組織上傳 PST 檔案至 Azure 儲存體位置後，下一步便是建立指定 PST 檔案將匯入至哪些使用者信箱之逗點分隔值 (CSV) 檔案。當您建立 PST 匯入工作時，您將會在下一個步驟提交此 CSV 檔案。
  
1. [下載 PST 匯入對應檔案的副本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。

2. 開啟或儲存 CSV 檔案到您的本機電腦。下列範例顯示了一個已完成的 PST 匯入對應檔案 (在「記事本」中開啟)。若使用 Microsoft Excel 來編輯 CSV 檔案會較為簡單。

    ```console
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,PSTFiles,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,PSTFiles,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    CSV 檔案的第一列或「標題列」會列出參數，PST 匯入服務將使用這些參數來匯入 PST 檔案至使用者信箱。 每個參數名稱都是以逗號分隔。 在標題列下的每一列，代表了要匯入 PST 檔案至特定信箱的參數值。 您需要為每個要匯入至使用者信箱的 PST 檔案設定一列。 CSV 對應檔案中最多可以有 500 列。 若要匯入超過 500 列的 PST 檔案，您必須在步驟 5 中建立多個對應檔案並建立多個匯入工作。

    > [!NOTE]
    > 不要在標頭列以及 SharePoint 參數中作任何變更，在 PST 匯入過程中會忽略這些項目。 此外，請務必在對應檔案中，使用您的實際資料來取代預留位置資料。

3. 使用下列表格的資訊，將所需的資訊填入 CSV 檔案。

    | 參數 | 描述 | 範例 |
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定資料將會匯入至哪個服務。 若要將 PST 檔案匯入至使用者信箱，請使用 `Exchange`。  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |指定在 Azure 儲存體位置的資料夾位置，也就是在步驟 2 中上傳 PST 檔案的位置。  <br/> 若您並未在步驟 2 的 `/Dest:` 參數中加入選擇性子資料夾名稱，請在 CSV 檔案將此參數保留空白。 如果您包含子資料夾名稱，則請於此參數內指定 (請參閱第二個範例)。 此參數值區分大小寫。  <br/> 或者，「不要」在 `FilePath` 參數值中包含 "ingestiondata"。  <br/><br/> **重要：** 如果在步驟 2 的 `/Dest:` 參數的 SAS URL 中包含可選的子資料夾名稱，則檔案路徑名稱的大小寫必須與您使用的大小寫相同。 例如，如果您在步驟 2 中使用 `PSTFiles` 作為子資料夾名稱，然後在 CSV 檔案的 `FilePath` 參數中使用 `pstfiles`，則 PST檔案的匯入將失敗。 請務必在這兩個案例中使用相同的大小寫。  <br/> |(保留空白)  <br/> 或  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |指定將匯入至使用者信箱的 PST 檔案名稱。 此參數值區分大小寫。 在匯出工作的對應檔案中，每個 PST 檔案的檔案名稱必須是唯一的。 <br/> <br/>**重要：** CSV 檔案中 PST 檔案名稱的大小寫必須與步驟 2 中上傳到 Azure 儲存體位置的 PST 檔案相同。 例如，如果在 CSV 檔案中的 `Name` 參數中使用 `annb.pst`，但實際的 PST 檔案名稱為 `AnnB.pst`，則該 PST 檔案的匯入將失敗。 請確認 CSV 檔案中的 PST 名稱使用與實際 PST 檔案相同的大小寫。  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |指定將匯入 PST 檔案的信箱電子郵件地址。 您無法指定公用資料夾，因為 PST 匯入服務不支援將 PST 檔案匯入公用資料夾。  <br/> 若要將 PST 檔案匯入非作用中的信箱，您必須為此參數指定信箱 GUID。 若要取得此 GUID，請在 Exchange Online 中執行下列 PowerShell 命令：`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> <br/>**注意：** 有時候，您可能會有多個信箱具有相同的電子郵件地址，其中一個信箱是作用中信箱，另一個信箱則處於虛刪除 (或非作用中) 狀態。 在這些情況下，您必須指定信箱 GUID，以唯一識別要匯入 PST 檔案的目的地信箱。 若要取得作用中信箱的此 GUID，請執行下列 PowerShell 命令：`Get-Mailbox <identity of active mailbox> | FL Guid` 若要取得虛刪除 (或非作用中) 信箱的 GUID，請執行此命令：`Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`。  <br/> | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要匯入 PST 檔案至使用者的封存信箱。其中有兩個選項：<br/><br/>**FALSE：** 將 PST 檔案匯入使用者的主要信箱。  <br/> **TRUE：** 將 PST 檔案匯入使用者的封存信箱。 這會假設[使用者的封存信箱已啟用](enable-archive-mailboxes.md)。 <br/><br/>如果您將此參數設為 `TRUE`，則使用者的封存信箱不會啟用，該使用者的匯入工作會因此失敗。 如果某個使用者的匯入工作失敗 (原因是其封存並未啟用，且此屬性設為 `TRUE`)，匯入工作中的其他使用者不會受到影響。  <br/>  如果您將此參數保留空白，則 PST 檔案會匯入到使用者的主要信箱。  <br/> <br/>**注意：** 若要替主要信箱是內部部署的使用者將 PST 檔案匯入至雲端式封存信箱，只要為此參數指定 `TRUE`，然後替 `Mailbox` 參數指定該使用者之內部部署信箱的電子郵件地址即可。  <br/> | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定要匯入 PST 檔案的信箱資料夾。  <br/> <br/> 若此參數保留空白，PST 檔案將會匯入至名為「已匯入」的新資料夾，其位於信箱的根層級 (與「收件匣」資料夾及其他預設信箱資料夾為相同層級)。  <br/> <br/> 如果您指定 `/`，PST 檔案中的資料夾和項目會匯入目標信箱或封存中的資料夾結構的最上層。 如果目標信箱中有資料夾 (例如，[收件匣]、[寄件備份] 和 [刪除的郵件] 等預設資料夾)，系統會將 PST 中該資料夾的項目合併到目標信箱現有的資料夾。 例如，如果 PST 檔案包含 [收件匣] 資料夾，該資料夾中的項目會匯入到目標信箱中的 [收件匣] 資料夾。 如果新資料夾不存在於目標信箱的資料夾結構中，則會建立新的資料夾。  <br/><br/>  如果指定 `/<foldername>`，則 PST 檔案中的項目和資料夾會匯入名為 *\<foldername\>* 的資料夾。 例如，如果使用 `/ImportedPst`，則會將項目匯入名為 **ImportedPst** 的資料夾。 此資料夾將位於與 [收件匣] 資料夾相同層級的使用者信箱中。  <br/><br/> **秘訣：** 請考慮執行一些測試批次來嘗試使用這個參數，如此您便能決定哪裡是匯入 PST 檔案的最佳資料夾位置。  <br/> |(保留空白)  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此選用參數可指定用於以 ANSI 檔案格式匯入 PST 檔案的字碼頁數值。 此參數用於從中文、日文和韓文 (CJK) 組織匯入 PST 檔案，因為這些語言通常使用雙位元字元集 (DBCS) 進行字元編碼。 如果此參數不用於匯入使用 DBCS 作為信箱資料夾名稱的語言的 PST 檔案，則匯入後資料夾名稱通常會出現亂碼。  <br/><br/> 如需要用於此參數的支援值清單，請參閱[字碼頁識別碼](/windows/win32/intl/code-page-identifiers)。  <br/> <br/>**注意：** 如前所述，這是一個選用參數，您不必將其包含在 CSV 檔案中。 或者您可以包含它並在一或多列中將值保留為空白。  <br/> |(保留空白)  <br/> 或  <br/>  `932` (為 ANSI/OEM 日文的字碼頁識別碼)  <br/> |
    | `SPFileContainer` <br/> |針對 PST 匯入，請將此參數保留空白。  <br/> |不適用  <br/> |
    | `SPManifestContainer` <br/> |針對 PST 匯入，請將此參數保留空白。  <br/> |不適用  <br/> |
    | `SPSiteUrl` <br/> |針對 PST 匯入，請將此參數保留空白。  <br/> |不適用  <br/> |

## <a name="step-5-create-a-pst-import-job"></a>步驟 5：建立 PST 匯入工作

下一個步驟是在 Microsoft 365 的匯入服務中，建立 PST 匯入工作。 如先前所解釋，您會提交在步驟 4 中所建立的 PST 匯入對應檔案。 在您建立工作後，Microsoft 365 會分析 PST 檔案中的資料，然後讓您篩選實際匯入 PST 匯入對應檔案中指定信箱的資料 (請參閱[步驟 6](#step-6-filter-data-and-start-the-pst-import-job))。
  
1. 前往 [https://protection.office.com](https://protection.office.com)，然後使用您組織中系統管理員帳戶的認證來登入。 

2. 在「安全性與合規性中心」的左窗格中，按一下 **[資料控管] > [匯入] > [匯入 PST 檔案]**。

3. 按一下 **[匯入 PST 檔案]** 頁面上的 ![[新增圖示]](../media/ITPro-EAC-AddIcon.gif) **[新增匯入工作]**。

   > [!NOTE]
   > 您必須獲派適當的權限，才能存取 [安全性與合規性中心] 中的 [匯入] 頁面來建立匯入工作。 如需詳細資訊，請參與 **開始之前** 這一節。 

4. 為 PST 匯入工作輸入名稱，然後按一下 [下一步]。 請使用小寫字母、數字、連字號和底線。 無法使用大寫字母，且名稱中不得包含空格。

5. 在 [您要上傳或傳送資料？] 頁面上、按一下 [上傳您的資料]，然後按一下 [下一步]。

    ![按一下 [上傳您的資料] 來建立網路上傳匯入工作。](../media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. 在步驟 4 中的 [匯入資料] 頁面中，按一下 [我已完成上傳檔案] 和 [我可以存取對應檔案] 核取方塊，接著按 [下一步]。

    ![按一下步驟 4 的兩個核取方塊。](../media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. 在 [選取對應檔案] 頁面上，按一下 [選取對應檔案] 以提交您在步驟 4 中建立的 CSV 對應檔案。

    ![按一下 [選取對應檔案] 來提交為匯入工作建立的 CSV 檔案](../media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. 在 CSV 檔案名稱出現於 [對應檔案名稱] 後，按一下 [驗證] 來檢查您的 CSV 檔是否有錯誤。 

    ![按一下 [驗證] 檢查 CSV 檔是否有錯誤](../media/4680999d-5538-4059-b878-2736a5445037.png)
  
    CSV 檔案必須成功通過驗證，才能建立 PST 匯入工作。 檔案名稱成功驗證後會變更為綠色。 如果驗證失敗，按一下 [檢視記錄] 連結。 驗證錯誤報告隨即開啟，並針對檔案中每一列有問題項目提供錯誤訊息。

   > [!NOTE]
   > 如先前所述，對應檔案最多可以有 500 列。 如果對應檔案包含的列超過 500，驗證將會失敗。 若要匯入超過 500 列的 PST 檔案，您必須建立多個對應檔案和多個匯入工作。

9. 對應檔案驗證成功後，請檢閱條款和條件文件，然後按一下核取方塊。

10. 按一下 [儲存] 提交工作，並在工作成功建立後按一下 [關閉]。

    狀態彈出頁面隨即顯示，狀態為 **[分析中]**，而新匯入工作會顯示在 **[匯入 PST 檔案]** 頁面的清單中。

11. 按一下 [重新整理] [重新整理圖示]![](../media/O365-MDM-Policy-RefreshIcon.gif) 以更新顯示於 [狀態] 欄位的狀態資訊。 分析完成並準備匯入資料後，狀態將變更為 [分析完成]。

    您可以按一下匯入作業以顯示狀態彈出頁面，其中會包含有關匯入工作的更多詳細訊息，例如對應檔案中列出的每個 PST 檔案的狀態。

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>步驟 6：篩選資料，並開始 PST 匯入工作

在步驟 5 建立匯入工作後，Microsoft 365 會以安全的方式分析 PST 檔案中的資料，來識別 PST 檔案所含項目的保存時間和各種訊息類型。 分析完成且準備好匯入資料後，您可以選擇匯入 PST 檔案中所包含的所有資料，或設定控制匯入資料的篩選條件來調整要匯入的資料。
  
1. 在安全性與合規性中心中的 **[匯入 PST 檔案]** 頁面上，為您在步驟 5 建立的匯入工作按一下 **[準備好匯入到 Office 365]**。

    ![在您建立的匯入工作旁按一下 [準備好匯入到 Microsoft 365]](../media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    隨即會顯示彈出頁面，以及關於該匯入工作的 PST 檔案資訊和其他資訊。

2. 在彈出頁面上，按一下 [匯入到 Office 365]。

    隨即會顯示 [篩選您的資料]。 它包含 Office 365 對 PST 檔案執行分析後所產生的資料見解，包括有關資料壽命的資訊。 此時，您可以選擇篩選要匯入的資料或按原樣匯入所有資料。 

    ![您可以修剪 PST 檔案中的資料或匯入所有資料](../media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. 執行下列其中一項：

   1. 若要修剪您匯入的資料，請按一下 [是，我要在匯入前先篩選]。

      如需篩選 PST 檔案中的資料，然後開始匯入工作的逐步說明，請參閱[將 PST 檔案匯入 Office 365 時篩選資料](filter-data-when-importing-pst-files.md)。

      或者

   2. 若要匯入 PST 檔案中的所有資料，請按一下 [否，我想要匯入所有項目]，再按一下 [下一步]。

4. 如果選擇匯入所有資料，請按一下 [匯入資料] 以開始匯入工作。 

   匯入工作的狀態會顯示在 **[匯入 PST 檔案]** 頁面。 按一下 ![重新整理圖示](../media/O365-MDM-Policy-RefreshIcon.gif) [重新整理] 以更新 [狀態] 欄位中顯示的狀態資訊。 按一下 [匯入工作] 以顯示狀態彈出頁面，這會顯示匯入的每個 PST 檔案的狀態資訊。 

## <a name="more-information"></a>詳細資訊

- 為什麼要將 PST 檔案匯入 Microsoft 365？

  - 這是將組織的封存訊息資料匯入 Microsoft 365 的好方法。

  - 訊息資料儲存在雲端上，因此使用者從所有的裝置都能取得資料。

  - 其允許您將 Microsoft 365 合規性功能應用於匯入的 PST 檔案中的資料，進而有助於滿足您的組織的合規性需求。這包括：

  - 啟用[封存信箱](enable-archive-mailboxes.md) 和[自動延長封存](enable-unlimited-archiving.md)，為使用者提供額外的信箱儲存空間，以儲存您匯入的資料。

  - 將信箱置於[訴訟資料暫留](./create-a-litigation-hold.md)，以保留您匯入的資料。

  - 使用 [Microsoft eDiscovery](search-for-content.md) 工具搜尋您匯入的資料。

  - 使用 [Microsoft 365 保留原則](retention.md)來控制匯入資料的保留時間，以及保留期間到期後要採取的動作。

  - 搜尋[稽核記錄](search-the-audit-log-in-security-and-compliance.md)，以尋找會影響您匯入資料的信箱相關事件。

  - 將資料匯入[非作用中信箱](create-and-manage-inactive-mailboxes.md)以封存資料，來符合合規性目的。 

  - 使用[資料遺失防護原則](dlp-learn-about-dlp.md)來防止敏感資料洩露到組織外部。
  
- 以下是在步驟 1 所取得的共用存取簽章(SAS) URL 範例。 此範例也包含您在 AzCopy.exe 工具中，為了上傳 PST 檔案所執行命令的語法。 請務必採取預防措施來保護 SAS URL，就如同您保護密碼或其他安全性相關的資訊一樣。

    ```console
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    ```

- 如先前說明，PST 檔案匯入到信箱之後， Office 365 匯入服務的暫停保留設定會開啟 (為無限期)。 這表示 *RetentionHoldEnabled* 屬性設定為 **True**，因此系統不會處理指派給信箱的保留原則。 防止刪除或封存原則可防止刪除或封存較舊的郵件，這讓信箱擁有者有時間管理新匯入的郵件。 這裡是您管理此暫停保留可採取的一些步驟：

   - 一段時間之後，您可以執行 **Set-Mailbox -RetentionHoldEnabled $false** 命令來關閉暫停保留。 如需指示，請參閱[將信箱設為暫停保留](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)。

   - 您可以設定暫停保留，讓它在未來某一天關閉。 方法是執行 **Set-Mailbox -EndDateForRetentionHold *date*** 命令。 例如，假設今天的日期是 2016 年 6 月 1 日，而您想要在 30 天時關閉暫停保留，您可以執行下列命令：**Set-Mailbox -EndDateForRetentionHold 7/1/2016**。 在這個案例中，您會將 **RetentionHoldEnabled** 屬性設定成 *True*。 如需詳細資訊，請參閱 [Set-Mailbox](/powershell/module/exchange/set-mailbox)。

   - 您可以變更指派給信箱的保留原則設定，讓匯入的舊項目不會被立即刪除或移至使用者的封存信箱。 例如，您可以延長指派給信箱的刪除或封存原則的保留存留期。 在這個案例中，您會在變更保留原則設定之後，關閉信箱的暫停保留。 如需詳細資訊，請參閱[設定組織中的信箱封存和刪除原則](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。

### <a name="how-the-import-process-works"></a>程序的運作方式
  
您可以使用網路上傳選項和 Office 365 匯入服務將 PST 檔案大量匯入到使用者信箱。 網路上傳表示，您將 PST 檔案上傳至 Microsoft 雲端中的暫時儲存體區域。 然後 Office 365 匯入服務會從儲存體區域將 PST 檔案複製到目標使用者信箱。
  
以下是將 PST 檔案匯入 Office 365 中的信箱時使用網路上傳的程序說明。
  
![使用網路上傳將 PST 檔案匯入 Office 365 的工作流程](../media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **將 PST 匯入工具和金鑰下載到私人 Azure 儲存體位置：** 第一個步驟是下載 AzCopy 命令列工具和存取金鑰，以用於將 PST 檔案上傳到 Microsoft 雲端中 Azure 儲存體位置。 您可以從安全性與合規性中心的[匯入] 頁面取得這些工具和金鑰。 金鑰 (稱為安全存取簽章 (SAS)) 會提供您必要的權限，以將 PST 檔案上傳到私人且安全的 Azure 儲存體位置。 此便捷鍵專屬於貴組織，並在 PST 檔案上傳到 Microsoft Cloud 後，協助防止未經授權存取 PST 檔案。 若要匯入 PST 檔案，貴組織不必具有不同的 Azure 訂閱。 

2. **將 PST 檔案上傳到 Azure 儲存體位置：** 下一個步驟是使用 AzCopy.exe 工具 (於步驟 1 中下載) 將您的 PST 檔案上傳並儲存在 Azure 儲存體位置，該位置位於與貴組織所在位置相同的 Microsoft 資料中心。 若要上傳，您想要匯入的 PST 檔案必須位於組織中的檔案共用或檔案伺服器。

    可以執行一個選用步驟，以便在 PST 檔案上傳到 Azure 儲存體位置後檢視檔案清單。

3. **建立 PST 匯入對應檔案：** 將 PST 檔案上傳到 Azure 儲存體位置後，下一個步驟是建立逗點分隔值 (CSV) 檔案，以指定要匯入 PST 檔案的使用者信箱，請注意，PST 檔案可匯入使用者的主要信箱或封存信箱。 Office 365 匯入服務會使用 CSV 檔案中的資訊來匯入 PST 檔案。

4. **建立 PST 匯入工作：** 下一個步驟是在安全性與合規性中心的 **[匯入 PST 檔案]** 頁面建立 PST 匯入工作，然後提交上一個步驟中建立的 PST 匯入對應檔案。 建立匯入工作後，Microsoft 365 會分析 PST 檔案中的資料，然後讓您設定篩選條件，以控制哪些資料會實際匯入 PST 匯入對應檔案中指定的信箱。 

5. **篩選將匯入信箱的 PST 資料：** 建立匯入工作並開始後，Microsoft 365 會透過識別 PST 檔案中包含的項目的壽命和不同的訊息類型安全地分析 PST 檔案中的資料。 分析完成且準備好匯入資料後，您可以選擇匯入 PST 檔案中所包含的所有資料，或設定控制匯入資料的篩選條件來調整要匯入的資料。

6. **開始 PST 匯入工作：** 開始匯入工作後，Microsoft 365 會使用 PST 匯入對應檔案中的資訊，將 PST 檔案從 Azure 儲存體位置匯入至使用者信箱。 匯入工作的狀態資訊 (包括匯入的每個 PST 檔案的相關資訊) 會顯示在安全性與合規性中心的 [匯入 PST 檔案] 頁面。 匯入工作完成時，工作的狀態會設為 **完成**。
