---
title: 使用磁片磁碟機運送來匯入您組織的 PST 檔案
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
ms.custom: seo-marvel-apr2020
description: 系統管理員可以透過將 pst 檔案複製到硬碟，然後再將其運送至 Microsoft，瞭解如何大量匯入 pst 檔案，以 Microsoft 365 信箱。
ms.openlocfilehash: a0858e3c1b6bcbe48a4060e8efaa3094768236fb
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684081"
---
# <a name="use-drive-shipping-to-import-your-organizations-pst-files"></a>使用磁片磁碟機運送來匯入您組織的 PST 檔案

**本文適用于系統管理員。您是否想要將 PST 檔案匯入您自己的信箱？請參閱 [從 Outlook .pst 檔案匯入電子郵件、連絡人及行事曆](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
使用 Office 365 匯入服務和磁片磁碟機運送將 PST 檔案大量匯入至使用者信箱。 磁碟機運送代表您將 PST 檔案複製到硬碟，並實際運送磁碟機給 Microsoft。 當 Microsoft 收到您的硬碟時，資料中心人員會將硬碟上的資料複製到 Microsoft 雲端中的儲存體區域。 然後，您就可以透過設定篩選來控制要匯入的資料，以裁切匯入至目標信箱的 PST 資料。 在您開始匯入工作之後，匯入服務會將 PST 資料從儲存體區域匯入至使用者信箱。 使用磁片磁碟機運送將 PST 檔案匯入至使用者信箱是將組織的電子郵件遷移至 Office 365 的一種方式。
  
以下是使用磁片磁碟機運送將 PST 檔案匯入至 Microsoft 365 信箱所需的步驟：
  
[步驟1：下載 secure storage key 和 PST Import 工具](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[步驟2：將 PST 檔案複製到硬碟](#step-2-copy-the-pst-files-to-the-hard-drive)

[步驟3：建立 PST 匯入對應檔案](#step-3-create-the-pst-import-mapping-file)

[步驟 4：在 Office 365 內建立 PST 匯入工作](#step-4-create-a-pst-import-job-in-office-365)

[步驟 5：運送硬碟給 Microsoft](#step-5-ship-the-hard-drive-to-microsoft)

[步驟 6：篩選資料，並開始 PST 匯入工作](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> 您必須執行步驟1一次，才能載入 secure storage key 和 import 工具。 執行這些步驟之後，請在每次您要將硬碟運送至 Microsoft 時，遵循步驟2到步驟6。 
  
有關使用磁片磁碟機運送將 pst 檔案匯入至 Office 365 的常見問題，請參閱[FAQs 使用磁片磁碟機運送來匯入 pst](./faqimporting-pst-files-to-office-365.yml#using-drive-shipping-to-import-pst-files)檔案。 
  
## <a name="before-you-import-pst-files"></a>在您匯出 PST 檔案之前

- 您必須在 Exchange Online 中獲派信箱匯入匯出角色，才能將 PST 檔案匯入 Microsoft 365 信箱。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 您可以將信箱匯入匯出角色新增到組織管理角色群組。 或者，可以建立角色群組、指派信箱匯出匯入角色，然後將自己新增為成員。 如需詳細資訊，請參閱[管理角色群組](/Exchange/permissions-exo/role-groups)之＜新增角色至角色群組＞或＜建立角色群組＞一節。
    
    此外，若要在 Microsoft 365 規範中心建立匯入工作，下列其中一項必須為真：
    
  - 您必須在 Exchange Online 中受指派為 [郵件收件者] 角色。根據預設，此角色會指派給 [組織管理] 與 [收件者管理] 角色群組。
    
    或者
    
  - 您必須是組織中的全域系統管理員。
    
    > [!TIP]
    > 建議您在 Exchange Online 中建立新的角色群組，專門用來將 PST 檔案匯入 Office 365。 若要獲得匯入 PST 檔案所需的最低權限等級，請將信箱匯入匯出及郵件收件者角色指派到新的角色群組，然後新增成員。 
  
- 您需要將想要複製到硬碟上的 PST 檔案，儲存於檔案伺服器上，或是貴組織的共用資料夾。 在步驟2中，您會執行 Azure 匯入匯出工具 (WAImportExport.exe) ，該工具會將儲存在此檔案伺服器或共用資料夾上的 PST 檔案複製到硬碟。

- 大型 PST 檔案可能會影響 PST 匯入程序的效能。 所以我們建議您複製到步驟2中硬碟上的每個 PST 檔案，不應大於 20 GB。
    
- 只有2.5 英寸的固態硬碟 (ssd) 或 3.5 2.5/III 的 SATA II/III 內部硬碟可搭配 Office 365 匯入服務使用。 您可以使用最多 10 TB 的硬碟。 匯入作業時，只會處理硬碟上的第一個資料磁碟區。 資料磁碟區必須為 NTFS 格式。 將資料複製到硬碟時，您可以使用2.5 寸 SSD 或 2.5-寸或 3.5-寸的 SATA II/III 連接器直接連接，也可以使用外部的「2.5-寸 SSD」或「2.5-寸」或「3.5-寸 SATA II/III」 USB 配接器，將其附加到外部磁片。
    
    > [!IMPORTANT]
    > Office 365 匯入服務不支援隨附內建 USB 轉接頭的外接式硬碟。 此外，位於外部硬碟外殼內的碟無法使用。 請不要使用外接式硬碟。 
  
- 您的 PST 檔案所複製到的硬碟，必須使用 BitLocker 加密。 您在步驟 2 中執行的 WAImportExport.exe 工具，會幫助您設定 BitLocker。 它還會產生 BitLocker 的加密金鑰，讓 Microsoft 資料中心人員用來存取磁片磁碟機，以將 PST 檔案上傳至 Microsoft 雲端中的 [Azure 儲存體] 區域。
    
- 您可以透過 Microsoft Enterprise 合約 (EA) 取得磁片磁碟機運送。 Microsoft Products and Services Agreement (MPSA) 則沒有提供磁碟機寄送。
    
- 使用磁片磁碟機運送將 PST 檔案匯入至 Microsoft 365 信箱所需的成本為 $2 USD 每 GB 的資料。 例如，假設您寄送的硬碟含有 1,000 GB (即 1 TB) 的 PST 檔案，則費用為 $2,000 美元。 您可以與夥伴合作來支付匯入費用。 如需有關尋找合作夥伴的資訊，請參閱[尋找您的 Microsoft 365 合作夥伴或轉售商](../admin/manage/find-your-partner-or-reseller.md)。
    
- 您或貴組織必須擁有 FedEx 或 DHL 的帳戶。 
    
  - 美國、巴西和歐洲的組織必須有 FedEx 帳戶。
    
  - 東亞、東南亞、日本、韓國共和國和澳大利亞的組織必須具有 DHL 帳戶。
    
    Microsoft 使用 (和計費) 此帳戶將硬碟傳回給您。
    
- 您運送至 Microsoft 的硬碟可能會跨越國際框線。 在此情況下，您負責確定要匯入和/或匯出的硬碟和其包含的資料，依照適用的法律。 運送硬碟之前，請向您的顧問確認磁碟機及資料可以合法的運送到指定的 Microsoft 資料中心。 這可協助確定它是以及時的方式到達 Microsoft。
    
- 此程序包含複製並儲存安全存放裝置金鑰和 BitLocker 加密金鑰。 請務必採取預防措施來保護這些金鑰，就如同您保護密碼或其他安全性相關的資訊一樣。 舉例來說，您可能會將這些資訊儲存於受密碼保護的 Microsoft Word 文件內，或是將它們儲存於已加密的 USB 磁碟機中。 請參閱 [More information](#more-information) 一節以取得這些機碼的範例。 
    
- 將 PST 檔案匯入至 Microsoft 365 信箱之後，信箱的保留功能設定會在無限期內開啟。 這表示在關閉暫停保留或設定日期來關閉暫停之前，系統不會處理指派給信箱的保留原則。 為什麼這麼做？ 如果匯入信箱的郵件是舊郵件，則可能會被永久刪除 (清除)，因為根據信箱設定的保留設定，這些郵件的保留期限已過期。 將信箱置於暫停保留狀態可讓信箱擁有者有時間管理這些新匯入的郵件，或者讓您有時間變更信箱的保留設定。 請參閱 [More information](#more-information) 一節以取得管理保留功能的建議。 
    
- 根據預設，Microsoft 365 信箱可接收的郵件大小上限為 35 MB。 這是因為信箱的 *MaxReceiveSize* 屬性的預設值設定為 35 MB。 然而，Microsoft 365 中的接收郵件大小上限為 150 MB。 因此，如果匯入的 PST 檔案包含大於 35 MB 的項目，Office 365 匯入服務將自動將目標信箱上的 *MaxReceiveSize* 的屬性值變更為 150 MB。 這樣就可將最大 150 MB 的郵件匯入使用者信箱。 
    
    > [!TIP]
    > 若要辨識信箱的郵件接收大小，可以在 Exchange Online PowerShell 中執行此命令：`Get-Mailbox <user mailbox> | FL MaxReceiveSize`。 
  
- 您否可以將 PST 檔案匯入 Office 365 中的非作用中信箱。 您可以透過在 PST 匯入對應檔案的 `Mailbox` 參數中指定非作用中信箱的 GUID 來執行此操作。 如需詳細資訊，請參閱「 [步驟3：建立 PST 匯入對應](#step-3-create-the-pst-import-mapping-file) 檔案」。 
    
- 您可以在 Exchange 混合部署中為主要信箱位於內部部署的使用者，將 PST 檔案匯入雲端型封存信箱。 您可以透過在 PST 匯入對應檔案中執行以下操作來進行：
    
  - 在 `Mailbox` 參數中指定使用者內部部署信箱的電子郵件地址。 
    
  - 在 `IsArchive` 參數上指定 **TRUE** 值。 
    
    如需詳細資訊，請參閱「 [步驟3：建立 PST 匯入對應](#step-3-create-the-pst-import-mapping-file) 檔案」。 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a>步驟1：下載 secure storage key 和 PST Import 工具

第一個步驟是下載 secure storage key 和工具，並在步驟2中用來將 PST 檔案複製到硬碟。
  
> [!IMPORTANT]
> 您必須使用 Azure 匯入/匯出工具版本 1 (WAimportExportV1) 使用磁片磁碟機貨運方法成功匯入 PST 檔案。 Azure 匯入/匯出工具的版本2不受支援，因此使用它將無法正確地為匯入工作準備硬碟磁碟機。 請遵循此步驟中的程式，以確定從 Microsoft 365 合規性中心下載 Azure 匯入/匯出工具。 
  
1. 前往 <https://compliance.microsoft.com>，然後使用您組織中系統管理員帳戶的認證來登入。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [**資訊管理** 匯 \> **入**]。
    
    > [!NOTE]
    > 如先前所述，您必須獲指派適當的許可權，才能存取「Microsoft 365 規範中心」中的 [匯 **入**] 頁面。 
  
3. 在 [匯 **入** ] 索引標籤上，按一下 [ ![ 新增新的匯 ](../media/ITPro-EAC-AddIcon.gif) **入工作**]。
    
4. 在 [匯入工作] 嚮導中，輸入 PST 匯入工作的名稱，然後按 **[下一步]**。 請使用小寫字母、數字、連字號和底線。 無法使用大寫字母，且名稱中不得包含空格。
    
5. 在 [ **選擇匯入工作類型** ] 頁面上，按一下 **其中一個實體位置的 [運送硬碟** ]，然後按 **[下一步]**。
    
    ![按一下 [將硬碟運送至我們的其中一個實體位置]，以建立磁片磁碟機運送匯入工作](../media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. 在 [匯入資料] 頁面上，執行以下兩個動作： 
    
    ![在 [匯入資料] 頁面上複製 secure storage key 並下載 Azure 匯入匯出工具](../media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    a. 在 [步驟 2] 中，按一下 **[顯示 secure storage key**]。 顯示儲存金鑰之後，按一下 [ **複製到剪貼簿** ]，然後將其貼上並儲存至檔案，讓您日後可以存取。
    
    b. 在步驟3中，**下載 azure 匯入/匯出工具**，以下載及安裝 azure 匯入/匯出 (版本 1) 工具。
    
    - 在快顯視窗中，按一下 [**另** 存新檔]，將 \>  WaImportExportV1.zip 檔案儲存至本機電腦上的資料夾。 
    
    - 解壓縮 WaImportExportV1.zip 檔案。
    
7. 按一下 [ **取消** ] 關閉嚮導。 
    
    當您在步驟4中建立匯入工作時，您會回到 Microsoft 365 規範中心的匯 **入** 頁面。 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a>步驟2：將 PST 檔案複製到硬碟

下一個步驟是使用 WAImportExport.exe 工具，將 PST 檔案複製到硬碟。 這個工具會使用 BitLocker 加密硬碟、將 PST 複製到硬碟，並建立日誌檔案，儲存複製程序的相關資訊。 若要完成此步驟，PST 檔案必須位於貴組織的檔案共用內或檔案伺服器中。 在下列程序中，這就是所謂的 [來源目錄]。 

 如先前所述，您複製到硬碟的每個 PST 檔案都不應該大於 20 GB。 大於 20 GB 的 PST 檔案可能會影響您在步驟 6 中啟動的 PST 匯入程序效能。
  
> [!IMPORTANT]
> 在硬碟首次執行 WAImportExport.exe 工具之後，每次您都必須使用不同的語法。 此語法會在此程式的步驟4中說明，將 PST 檔案複製到硬碟。 
  
1. 在您的本機電腦上開啟 [命令提示字元]。
    
    > [!TIP]
    > 如果您以系統管理員身分執行命令提示字元 (當您開啟時選取「以系統管理員身分執行」)，在命令提示字元視窗中，將顯示錯誤訊息。這可以協助您進行關於執行 WAImportExport.exe 工具問題的疑難排解。 
  
2. 移至您在步驟 1 中安裝 WAImportExport.exe 工具的目錄。
    
3. 首次執行下列命令，您會使用 WAImportExport.exe 來將 PST 檔案複製到硬碟。

    ```powershell
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /blobtype:BlockBlob /encrypt /logdir:<Log file location>
    ```

    下表說明了參數與其需要的值。
    
    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `/j:` <br/> |指定日誌檔的名稱。此檔案會儲存到與 WAImportExport.exe 工具所在位置相同的資料夾。您送交給 Microsoft 的每個硬碟都必須有一個日誌檔案。每次您執行 WAImportTool.exe，將 PST 檔案複製到硬碟時，資訊都將會附加到該磁碟機的日誌檔。 
  <br/> Microsoft 資料中心人員使用日誌檔中的資訊，將硬碟與您在步驟4中建立的匯入工作產生關聯，並將 PST 檔案上傳至 Microsoft 雲端的 Azure 儲存體區域。  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |指定當硬碟連接至本機電腦時的磁碟機代號。  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |指定複製工作階段的名稱。工作階段的定義是每次執行 WAImportExport.exe 工具，將檔案複製到硬碟的動作。PST 檔案會複製到資料夾，該資料夾是以此參數所指定的工作階段名稱來命名。   <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |指定貴組織內的來源目錄，該目錄包含在工作階段期間要複製的 PST 檔案。 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |在 Microsoft 雲端的 [Azure 儲存體] 區域中，指定要上傳 pst 的目的地目錄。 您必須使用值  `ingestiondata/` 。 請務必使用雙引號 (" ") 括住此參數的值。  <br/> 您也可以選擇性地新增額外的檔案路徑至此參數的值。 例如，您可以使用硬碟磁碟機上來原始目錄的檔案路徑， (轉換為 URL 格式) （在參數中指定）  `/srcdir:` 。 例如，  `\\FILESERVER01\PSTs` 變更為  `FILESERVER01/PSTs` 。 在此情況下，您仍必須包含  `ingestiondata` 在檔路徑中。 所以在這個範例中，參數的值  `/dstdir:` 將是  `"ingestiondata/FILESERVER01/PSTs"` 。  <br/> 新增其他檔案路徑的原因之一，是您具有相同檔名的 PST 檔案。  <br/> > [!NOTE]> 如果包含選用的路徑名，則在將 pst 檔案上傳至 Azure 儲存體區域之後，它的命名空間會包含該 pst 檔案的路徑名和名稱;例如， `FILESERVER01/PSTs/annb.pst` 。 如果您未包含 pathname，則命名空間只是 PST 檔案名;例如  `annb.pst` 。           | `/dstdir:"ingestiondata/"` <br/> 或者  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |指定您在步驟 1 中所取得的安全存放裝置帳戶金鑰。 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/blobtype:` <br/> |會指定要將 PST 檔案匯入至 Azure 儲存體區域的 blob 類型。 若要匯入 PST 檔案，請使用 value **BlockBlob**。 此為必要參數。   <br/> | `/blobtype:BlockBlob` <br/> |
    | `/encrypt` <br/> |此參數會開啟硬碟的 BitLocker。首次執行 WAImportExport.exe 工具時需要此參數。  <br/> 當您使用參數時，BitLocker 加密金鑰會複製到日誌檔及所建立的記錄檔 `/logfile:` 。 如先前所解釋，檔案會儲存到與 WAImportExport.exe 工具所在位置相同的資料夾。  <br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |此選擇性參數會指定要儲存記錄檔的資料夾。 若未指定，記錄檔會儲存在 WAImportExport.exe 工具所在的相同資料夾中。 請務必使用雙引號 (" ") 括住此參數的值。  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    這是 WAImportExport.exe 工具針對各個參數使用實際值的語法範例︰
    
    ```powershell
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" blobtype:BlockBlob /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    在您執行命令後，便會顯示 PST 檔案複製到硬碟進度的狀態訊息。最終狀態訊息會顯示已成功複製的檔案總數。 
    
4. 以後每次您執行 WAImportExport.ext 工具，將 PST 檔案複製到相同的硬碟時，都要執行此命令。

    ```powershell
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> /blobtype:BlockBlob 
    ```

    這是以後執行工作階段，將 PST 檔案複製到相同的硬碟時的語法範例。  

    ```powershell
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/" /blobtype:BlockBlob
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a>步驟3：建立 PST 匯入對應檔案

在 Microsoft 資料中心人員將 pst 檔案從硬碟上傳至 Azure 儲存體區域之後，匯入服務會使用 PST 匯入對應檔案中的資訊，這是逗號分隔值， (CSV) 檔，可指定要匯入 PST 檔案的使用者信箱。 當您建立 PST 匯入工作時，您將會在下一個步驟提交 CSV 檔案。
  
1. [下載 PST 匯入對應檔案的副本](https://go.microsoft.com/fwlink/p/?LinkId=544717)。
    
2. 開啟或儲存 CSV 檔案到您的本機電腦。下列範例顯示了一個已完成的 PST 匯入對應檔案 (在「記事本」中開啟)。若使用 Microsoft Excel 來編輯 CSV 檔案會較為簡單。

    ```text
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,FILESERVER01/PSTs,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,,,,,
    ```

    CSV 檔案的第一列或「標題列」會列出參數，PST 匯入服務將使用這些參數來匯入 PST 檔案至使用者信箱。 每個參數名稱都是以逗號分隔。 在標題列下的每一列，代表了要匯入 PST 檔案至特定信箱的參數值。 每個已複製到硬碟的 PST 檔案都需要一列。 請務必在對應檔案中，使用您的實際資料來取代預留位置資料。

    > [!NOTE]
    > 不要在標頭列以及 SharePoint 參數中作任何變更，在 PST 匯入過程中會忽略這些項目。 
  
3. 使用下列表格的資訊，將所需的資訊填入 CSV 檔案。
    
    |**參數**|**描述**|**範例**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |指定資料將會匯入至哪個服務。 若要將 PST 檔案匯入至使用者信箱，請使用 `Exchange`。  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> | 指定當硬碟送出至 Microsoft 時，Azure 儲存體區域中的資料夾位置，PST 檔案會複製到該位置。  <br/>  您在 CSV 檔案的此欄中新增的內容，取決於您在上一個步驟中為參數所指定的專案  `/dstdir:` 。 如果來源位置上有子資料夾，則參數中的值 `FilePath` 必須包含子資料夾的相對路徑; 例如，/folder1/user1/。  <br/>  如果您使用  `/dstdir:"ingestiondata/"` ，請在 CSV 檔案中將此參數保留空白。  <br/>  如果您包含參數值的選用路徑名  `/dstdir:` (例如，  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` 請在 CSV 檔案中使用該路徑名 (不包含此參數的 "ingestiondata" ) 。 此參數值區分大小寫。  <br/>  或者，「不要」在 `FilePath` 參數值中包含 "ingestiondata"。 請將此參數保留空白，或是只指定選用的 pathname。  <br/> > [!IMPORTANT]> 檔案路徑名稱的大小寫必須與上一個步驟中的參數所指定的大小寫相同  `/dstdir:` 。 例如，如果您在  `"ingestiondata/FILESERVER01/PSTs"` 上一個步驟中用於子資料夾名稱，但接著  `fileserver01/psts` 在 CSV 檔案的  `FilePath` 參數中使用，則會失敗的 PST 檔案匯入。 請務必在這兩個案例中使用相同的大小寫。           |(保留空白)  <br/> 或  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |指定將匯入至使用者信箱的 PST 檔案名稱。 此參數值區分大小寫。  <br/> > [!IMPORTANT]在 CSV 檔案中> pst 檔案名的情況，必須與上傳至步驟2中 Azure 儲存體位置的 pst 檔案相同。 例如，如果在 CSV 檔案中的 `Name` 參數中使用 `annb.pst`，但實際的 PST 檔案名稱為 `AnnB.pst`，則該 PST 檔案的匯入將失敗。 請確認 CSV 檔案中的 PST 名稱使用與實際 PST 檔案相同的大小寫。           | `annb.pst` <br/> |
    | `Mailbox` <br/> |指定將匯入 PST 檔案的信箱電子郵件地址。 您無法指定公用資料夾，因為 PST 匯入服務不支援將 PST 檔案匯入公用資料夾。  <br/> 若要將 PST 檔案匯入非作用中的信箱，您必須為此參數指定信箱 GUID。 若要取得此 GUID，請在 Exchange Online 中執行下列 PowerShell 命令：`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> > [!NOTE]> 有時候，您可能會有多個信箱具有相同的電子郵件地址，其中一個信箱是作用中的信箱，另一個信箱位於虛刪除的 (或非使用中的) 狀態。 在這些情況下，您必須指定信箱 GUID，以唯一識別要匯入 PST 檔案的目的地信箱。 若要取得作用中信箱的此 GUID，請執行下列 PowerShell 命令：`Get-Mailbox <identity of active mailbox> | FL Guid` 若要取得虛刪除 (或非使用中) 信箱的 GUID，請執行下列命令：  `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid` 。           | `annb@contoso.onmicrosoft.com` <br/> 或  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | 指定是否要匯入 PST 檔案至使用者的封存信箱。其中有兩個選項：<br/> **FALSE** 將 PST 檔案匯入至使用者的主要信箱。  <br/> **TRUE** 匯入 PST 檔案至使用者的封存信箱。 這會假設[使用者的封存信箱已啟用](enable-archive-mailboxes.md)。 如果您將此參數設為 `TRUE`，則使用者的封存信箱不會啟用，該使用者的匯入工作會因此失敗。 如果某個使用者的匯入工作失敗 (原因是其封存並未啟用，且此屬性設為 `TRUE`)，匯入工作中的其他使用者不會受到影響。  <br/>  如果您將此參數保留空白，則 PST 檔案會匯入到使用者的主要信箱。  <br/> **注意：** 若要替主要信箱是內部部署的使用者將 PST 檔案匯入至雲端式封存信箱，只要為此參數指定 `TRUE`，然後替 `Mailbox` 參數指定該使用者之內部部署信箱的電子郵件地址即可。  <br/> | `FALSE` <br/> 或  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | 指定要匯入 PST 檔案的信箱資料夾。  <br/>  如果您將此參數保留空白，則會將 PST 匯入至信箱的根層級上的 [匯入] （ (與「收件匣」資料夾相同的層級，以及其他預設信箱資料夾) 中的 [匯 **入** ] 的新資料夾。  <br/>  如果您指定  `/` ，PST 檔案中的專案將直接匯入至使用者的 [收件匣] 資料夾。  <br/>  如果指定  `/<foldername>` ，PST 檔案中的專案將會匯入名為的資料夾中  *\<foldername\>* 。 例如，如果使用 `/ImportedPst`，則會將項目匯入名為 **ImportedPst** 的資料夾。 此資料夾將位於與 [收件匣] 資料夾相同層級的使用者信箱中。  <br/> |(保留空白)  <br/> 或  <br/>  `/` <br/> 或  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |此選用參數可指定用於以 ANSI 檔案格式匯入 PST 檔案的字碼頁數值。 此參數用於從中文、日文和韓文 (CJK) 組織匯入 PST 檔案，因為這些語言通常使用雙位元字元集 (DBCS) 進行字元編碼。 如果此參數不用於匯入使用 DBCS 作為信箱資料夾名稱的語言的 PST 檔案，則匯入後資料夾名稱通常會出現亂碼。  <br/> 如需要用於此參數的支援值清單，請參閱[字碼頁識別碼](/windows/win32/intl/code-page-identifiers)。  <br/> > [!NOTE]> 如先前所述，這是選用參數，您不需要將它包含在 CSV 檔案中。 或者您可以包含它並在一或多列中將值保留為空白。           |(保留空白)  <br/> 或  <br/>  `932` (為 ANSI/OEM 日文的字碼頁識別碼)  <br/> |
    | `SPFileContainer` <br/> |針對 PST 匯入，請將此參數保留空白。  <br/> |不適用  <br/> |
    | `SPManifestContainer` <br/> |針對 PST 匯入，請將此參數保留空白。  <br/> |不適用  <br/> |
    | `SPSiteUrl` <br/> |針對 PST 匯入，請將此參數保留空白。  <br/> |不適用  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a>步驟 4：在 Office 365 中建立 PST 匯入工作

下一個步驟是在 Office 365 的匯入服務中，建立 PST 匯入工作。 如先前所述，您提交您在步驟3中建立的 PST 匯入對應檔案。 在您建立工作之後，匯入服務會使用對應檔中的資訊，將 pst 檔案複製到指定 Azure 儲存體的使用者信箱後，將 pst 檔案匯入至指定的使用者信箱，並建立及啟動匯入工作。
  
1. 前往 <https://compliance.microsoft.com>，然後使用您組織中系統管理員帳戶的認證來登入。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [**資訊管理** 匯 \> **入**]。

3. 在 [匯 **入** ] 索引標籤上，按一下 [ ![ 新增新的匯 ](../media/ITPro-EAC-AddIcon.gif) **入工作**]。

    > [!NOTE]
    > 如先前所述，您必須獲指派適當的許可權，才能存取「Microsoft 365 規範中心」中的 [匯 **入**] 頁面。
  
4. 為 PST 匯入工作輸入名稱，然後按一下 [下一步]。 請使用小寫字母、數字、連字號和底線。 無法使用大寫字母，且名稱中不得包含空格。

5. 在 [ **選擇匯入工作類型** ] 頁面上，按一下 **其中一個實體位置的 [運送硬碟** ]，然後按 **[下一步]**。
  
6. 在 [步驟 6] 中，按一下 [ **我已準備好硬碟磁碟機]，並可以存取必要的磁片磁碟機日誌** 檔，而且可以存取 **對應** 檔案核取方塊，然後按 **[下一步]**。

    ![按一下步驟6中的兩個核取方塊。](../media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. 在 [ **選取磁片磁碟機** ] 頁面上，按一下 [ **選取磁片磁碟機**]，然後移至 WAImportExport.exe 工具所在的相同資料夾。 在步驟 2 中所建立的日誌檔案已複製到此資料夾。

    ![按一下 [選取磁片磁碟機檔案] 以提交您執行 WAImportExport.exe 工具時所建立的日誌檔。](../media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. 選取日誌檔;例如， `PSTHDD1.jrn` 。

    > [!TIP]
    > 當您在步驟2中執行 WAImportExport.exe 工具時，會使用該參數指定日誌檔的名稱  `/j:` 。
  
9. 在 [ **磁片磁碟機** 檔案名] 底下顯示磁碟機檔的名稱後，按一下 [ **驗證** ]，檢查磁片磁碟機中是否有錯誤。

    ![按一下 [驗證] 驗證您選取的磁片磁碟機檔案](../media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    必須成功驗證磁片磁碟機檔，才能建立 PST 匯入工作。 檔案名稱成功驗證後會變更為綠色。 如果驗證失敗，按一下 [檢視記錄] 連結。 開啟驗證錯誤報表，其中含有有關檔案失敗原因的錯誤訊息。 

    > [!NOTE]
    > 您必須針對您運送至 Microsoft 的每個硬碟，新增及驗證日誌檔。 
  
10. 針對您運送至 Microsoft 的每個硬碟新增及驗證日誌檔之後，按 **[下一步]**。
    
11. 按一下 [ ![ 新增圖示 ](../media/ITPro-EAC-AddIcon.gif) **選取對應檔** ]，送出您在步驟3中建立的 PST 匯入對應檔案。 

    ![按一下 [選取對應檔案] 來提交為匯入工作建立的 CSV 檔案](../media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. 在 CSV 檔案名稱出現於 [對應檔案名稱] 後，按一下 [驗證] 來檢查您的 CSV 檔是否有錯誤。 

    ![按一下 [驗證] 檢查 CSV 檔是否有錯誤](../media/4680999d-5538-4059-b878-2736a5445037.png)
  
    CSV 檔案必須成功通過驗證，才能建立 PST 匯入工作。 檔案名稱成功驗證後會變更為綠色。 如果驗證失敗，按一下 [檢視記錄] 連結。 驗證錯誤報告隨即開啟，並針對檔案中每一列有問題項目提供錯誤訊息。 

13. 在成功驗證 PST 對應檔案之後，請按 **[下一步]**。

14. 在 [ **提供連絡人資訊** ] 頁面上的 [可用] 方塊中，輸入您的連絡人資訊。 

    顯示您運送硬碟的 Microsoft 位置的位址。 此位址會根據您的 Microsoft 資料中心位置自動產生。 請將此地址複製到檔案，或取得螢幕擷取畫面。

15. 閱讀條款與條件檔，按一下核取方塊，然後按一下 [ **儲存** ] 提交匯入工作。 

    當成功建立匯入工作時，會顯示「狀態」頁面，說明磁片磁碟機運送過程的後續步驟。

16. 在 [匯 **入**] 索引標籤上，按一下 [重新整理圖示重新整理]， ![ 在匯 ](../media/O365-MDM-Policy-RefreshIcon.gif) 入工作清單中顯示新的磁片磁碟機運送匯入工作。 狀態設定為 [ **等候追蹤號碼**]。 您也可以按一下 [匯入] 工作以顯示 [狀態彈出] 頁面，其中包含有關匯入工作的詳細資訊。

## <a name="step-5-ship-the-hard-drive-to-microsoft"></a>步驟 5：運送硬碟給 Microsoft

下一步是將硬碟運送至 Microsoft，然後提供運送的追蹤號碼，並傳回運送資訊的磁片磁碟機運送工作。 Microsoft 在接收到該磁片磁碟機後，資料中心人員需要7到10個工作天，將您的 PST 檔案上傳到組織的 Azure 儲存體區域。
  
> [!NOTE]
> 如果您未在建立匯入工作的14天內提供追蹤號碼和傳回發貨資訊，匯入工作會到期。 如果發生這種情況，您必須建立新的磁片磁碟機運送匯入工作 (請參閱「[步驟4：在 Office 365 中建立 PST 匯入工作](#step-4-create-a-pst-import-job-in-office-365)」) ，然後重新提交磁片磁碟機檔及 PST 匯入對應檔案。
  
### <a name="ship-the-hard-drive"></a>運送硬碟

當您運送硬碟給 Microsoft 時，請記住下列事項︰
  
- 請勿運送 SATA-USB 配接器;您只需運送硬碟。

- 請妥善包裝硬碟；例如，使用防靜電包裝袋或氣泡紙包裝。

- 使用您所選擇的出貨承運業者運送硬碟給 Microsoft。

- 將硬碟運送到您在步驟 4 中，建立匯入工作時所顯示的 Microsoft 地點。 請務必在寄送地址中包含「Office 365 匯入服務」。

- 在您運送硬碟後，請務必寫下出貨承運業者的名稱及追蹤號碼。在下一個步驟中您將提供這些資訊。
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a>輸入追蹤號碼，以及其他的送貨資訊

在您運送硬碟給 Microsoft 之後，請在 [匯入] 服務頁面完成下列程序。
  
1. 前往 <https://compliance.microsoft.com>，然後使用您組織中系統管理員帳戶的認證來登入。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [**資訊管理] > 匯入**。

3. 在 [匯 **入** ] 索引標籤上，按一下您想要輸入追蹤號碼的磁片磁碟機運送工作。

4. 在 [狀態彈出] 頁面上，按一下 [ **輸入追蹤號碼**]。

5. 請提供下列的送貨資訊︰

   1. **傳遞載波** 輸入您用來將硬碟運送至 Microsoft 的傳遞載波名稱。 

   2. **追蹤號碼** 輸入磁片磁碟機運送的追蹤號碼。 

   3. **退回承運人帳戶號碼** 為 [ **退回承運人**] 底下所列的承運人輸入您組織的帳戶號碼。 Microsoft 會使用 (和計費) 此帳戶將您的硬碟送回給您。 美國和歐洲的組織必須具有 FedEx 的帳戶。 亞洲和世界各地的組織必須具有 DHL 的帳戶。

6. 按一下 **[儲存]** 以儲存此資訊供匯入工作使用。 

    在 [匯 **入**] 索引標籤上，按一下 [重新整理圖示重新整理] ![ ](../media/O365-MDM-Policy-RefreshIcon.gif) 以更新磁片磁碟機運送匯入工作的資訊。 請注意，現在狀態設定為 **[磁碟機在運輸中]**。

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>步驟 6：篩選資料，並開始 PST 匯入工作

當 Microsoft 收到您的硬碟後，[匯 **入 PST** 檔案] 頁面上的匯入工作狀態會變更為 [ **已接收的磁片磁碟機**]。 資料中心人員使用日誌檔中的資訊，將您的 PST 檔案上傳到組織的 Azure 儲存體區域。 此時，其狀態變更為 [ **正在匯入**]。 如先前所述，在接收您的硬碟以上傳 PST 檔案之後，將需要7到10個工作日。
  
將 PST 檔案上傳至 Azure 後，狀態會變更為 [ **正在進行分析**]。 這表示 Microsoft 365 會以安全且安全的方式來分析 PST 檔案 (中的資料，) 以找出專案的年齡及 PST 檔案中包含的不同郵件類型。 分析完成且資料可供匯入時，會將匯入工作的狀態變更為 [ **分析完成**]。 此時，您可以選擇匯入 PST 檔案中所包含的所有資料，也可以透過設定篩選來控制要匯入哪些資料，以裁切匯入的資料。
  
1. 前往 <https://compliance.microsoft.com>，然後使用您組織中系統管理員帳戶的認證來登入。

2. 在 Microsoft 365 規範中心的左功能窗格中，按一下 [**資訊管理**] * * [匯入] * * * \> 。

3. 在 [匯 **入**] 索引標籤上，選取您在步驟4中建立的匯入工作，然後按一下 [匯 **入至 Office 365**]。
  
    隨即會顯示彈出頁面，以及關於該匯入工作的 PST 檔案資訊和其他資訊。

4. 按一下 [匯 **入至 Office 365**]。

5. 隨即會顯示 [篩選您的資料]。 它包含 Office 365 對 PST 檔案執行分析後所產生的資料見解，包括有關資料壽命的資訊。 此時，您可以選擇篩選要匯入的資料或按原樣匯入所有資料。 

    ![您可以修剪 PST 檔案中的資料或匯入所有資料](../media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. 執行下列其中一項動作：

    a. 若要修剪您匯入的資料，請按一下 [是，我要在匯入前先篩選]。

    如需篩選 PST 檔案中的資料，然後開始匯入工作的逐步說明，請參閱[將 PST 檔案匯入 Office 365 時篩選資料](filter-data-when-importing-pst-files.md)。

    或

    b. 若要匯入 PST 檔案中的所有資料，請按一下 [否，我想要匯入所有項目]，再按一下 [下一步]。

7. 如果選擇匯入所有資料，請按一下 [匯入資料] 以開始匯入工作。 

    匯入工作的狀態會顯示在 [匯 **入 PST 檔** ] 頁面上。 按一下 ![重新整理圖示](../media/O365-MDM-Policy-RefreshIcon.gif) [重新整理] 以更新 [狀態] 欄位中顯示的狀態資訊。 按一下 [匯入工作] 以顯示狀態彈出頁面，這會顯示匯入的每個 PST 檔案的狀態資訊。 當匯入完成，且已匯入 PST 檔案到使用者信箱時，狀態將變更為 **[已完成]**。

## <a name="view-a-list-of-the-pst-files-uploaded-to-microsoft-365"></a>查看上傳至 Microsoft 365 的 PST 檔案清單

您可以安裝及使用 Microsoft Azure 儲存體總管 (這是免費的開放式來源工具) ，以查看 Microsoft 資料中心人員 (將其上傳的 PST 檔案清單，) 到組織的 Azure 儲存體區域。 您可以執行下列動作，確認您傳送至 Microsoft 的硬碟上的 PST 檔案已成功上傳至 Azure 儲存體區域。
  
> [!IMPORTANT]
> 您無法使用 Azure 儲存體總管來上傳或修改 PST 檔案。 將 PST 檔案匯入至 Microsoft 365 唯一支援的方法是使用 AzCopy。 此外，您無法刪除已上傳到 Azure Blob 的 PST 檔案。 如果您嘗試刪除 PST 檔案，您會收到有關沒有必要許可權的錯誤。 所有 PST 檔案都會自動從您的 Azure 儲存體區域中刪除。 如果沒有任何匯入工作進行中，則在建立最近的匯入工作30天之後，會刪除 * * ingestiondata * * 容器中的所有 PST 檔案。
  
請執行下列步驟，取得組織 (SAS) URL 的共用存取簽名。 此 URL 是用於組織的 Microsoft 雲端中 Azure 儲存體位置之網路 URL 的組合，以及一個 SAS 金鑰。 這個機碼提供您存取組織之 Azure 儲存體位置的必要許可權。

若要安裝 Azure 儲存體總管並連線到您 Azure 儲存體區域：

1. 前往 <https://compliance.microsoft.com>，然後使用您組織中系統管理員帳戶的認證來登入。

2. 在 Microsoft 365 規範中心的左窗格中，按一下 [**資訊管理] > 匯入**。

3. 在 [匯 **入** ] 索引標籤上，按一下 [ ![ 新增新的匯 ](../media/ITPro-EAC-AddIcon.gif) **入工作**]。

4. 在 [匯入工作] 嚮導中，輸入 PST 匯入工作的名稱，然後按 **[下一步]**。 請使用小寫字母、數字、連字號和底線。 無法使用大寫字母，且名稱中不得包含空格。

5. 在 [**選擇匯入工作類型**] 頁面上，按一下 [ **Upload 資料**]，然後按 **[下一步]**。

6. 在步驟 2，按一下 [顯示網路上傳 SAS URL]。

7. 顯示 URL 後，將其複製並儲存至檔案。 請務必複製完整 URL。

    > [!IMPORTANT]
    > 請務必採取預防措施來保護 SAS URL。 任何人都可以使用此方法來存取組織的 Azure 存放區。
  
8. 按一下 [ **取消** ] 關閉 [匯入工作] 嚮導。

9. 下載並安裝 [Microsoft Azure 儲存體總管工具](https://go.microsoft.com/fwlink/p/?LinkId=544842)。

10. 啟動 Microsoft Azure 儲存體總管工具、以滑鼠右鍵按一下左邊窗格中的 [儲存體帳戶]，然後再按一下 [連線至 Azure 儲存體]。

    ![以滑鼠右鍵按一下 [儲存體帳戶]，接著按一下 [連線至 Azure 儲存體]](../media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
11. 按一下 [使用共用存取簽章 (SAS) URI 或連線字串]，然後按一下 [下一步]。

12. 按一下 [ **使用 SAS URI**]，然後在 [ **URI**] 底下的方塊中貼上您在步驟1中取得的 SAS URL，然後按 **[下一步]**。

13. 在 [連線摘要] 頁面上，您可檢閱連線資訊、然後按一下 [連線]。

    **Ingestiondata** 容器已開啟。 包含您的硬碟上的 PST 檔案。 **ingestiondata** 容器位於 [儲存體帳戶] \> **(附加 SAS 的服務) \> [Blob 容器]**。

    ![[Azure 儲存體總管] 會顯示您上傳的 PST 檔案清單](../media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
14. 當您使用 Microsoft Azure 儲存體總管完成後，以滑鼠右鍵按一下 [ingestiondata]，然後按一下 [中斷連線] 來中斷 Azure 儲存體區域的連線。 否則，您會在下一次嘗試附加時收到錯誤。 

    ![以滑鼠右鍵按一下 [擷取]，然後按一下 [中斷連線]，以中斷與 Azure 儲存體區域之間的連線](../media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)

## <a name="troubleshooting-tips"></a>疑難排解提示

- **若由於 PST 匯入 CSV 對應檔案中的錯誤而導致匯入工作失敗，會發生什麼事？** 若由於對應檔案中的錯誤而導致匯入工作失敗，您不需要將硬碟 reship 至 Microsoft，即可建立匯入工作。 這是因為您為磁片磁碟機運送匯入工作所送出之硬碟上的 PST 檔案，已上傳至組織的 Azure 儲存體區域。 在此情況下，您只需要修正 PST Import CSV 對應檔案中的錯誤，然後建立新的「網路上傳」匯入工作並提交修改後的 CSV 對應檔案。 若要建立及啟動新的網路上傳的匯入工作，請參閱「[步驟5：在 Microsoft 365 中建立 pst 匯入工作](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job) [」和步驟6：篩選資料，並啟動](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job)[使用網路上傳將 pst 檔案匯入 Office 365] 主題中的 [使用網路上傳]。 
    
    > [!NOTE]
    > 若要協助您疑難排解 pst Import CSV 對應檔，請使用 [Azure 儲存體總管](#view-a-list-of-the-pst-files-uploaded-to-microsoft-365)工具，在您的硬碟上，用來查看已上傳至 Azure 儲存體區域之 pst 檔案的 **ingestiondata** 容器中的資料夾結構。 對應檔案錯誤通常是因 FilePath 參數中不正確的值所造成。 此參數會指定 [Azure 存放區] 中 PST 檔案的位置。 請參閱在 [步驟 3](#step-3-create-the-pst-import-mapping-file)的 table 中 FilePath 參數的描述。 如先前所述，  `/dstdir:` 當您在 [步驟2中執行](#step-2-copy-the-pst-files-to-the-hard-drive)WAImportExport.exe 工具時，此參數會指定 Azure 儲存體區域中 PST 檔案的位置。 
  
## <a name="more-information"></a>其他相關資訊

- 磁片磁碟機運送是一種有效的方式，可將大量的封存郵件資料匯入 Microsoft 365，以利用組織所提供的相容性功能。 將封存資料匯入使用者信箱之後，您可以：

  - 啟用封存 [信箱](enable-archive-mailboxes.md) 和 [自動展開的](enable-unlimited-archiving.md) 封存，為使用者提供更多有關資料的信箱儲存空間。 

  - 將信箱設為保留資料的 [訴訟暫止狀態](./create-a-litigation-hold.md) 。 

  - 使用 Microsoft [eDiscovery 工具](search-for-content.md) 來搜尋資料。 

  - 套用[Microsoft 365 保留原則](retention.md)，以控制保留資料的時間長度，以及保留期間到期後要採取的動作。 

  - 在 [審計記錄](search-the-audit-log-in-security-and-compliance.md) 檔中搜尋與此資料相關的事件。 

  - 將資料匯入非使用中的 [信箱](create-and-manage-inactive-mailboxes.md) ，封存資料以進行相容性目的。 

  - 保護您的組織避免敏感資訊的 [資料遺失](dlp-learn-about-dlp.md) 。 

- 以下是安全存放裝置帳戶金鑰和 BitLocker 加密金鑰的範例。此範例也會包含您要複製 PST 檔案到硬碟，所執行的 WAImportExport.exe 命令的語法。請務必採取預防措施來保護這些項目，就如同您保護密碼或其他安全性相關的資訊一樣。

    ```text
    Secure storage account key: 

    yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==

    BitLocker encryption key:

    397386-221353-718905-535249-156728-127017-683716-083391

  COMMAND SYNTAX

  First time:

  WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /blobtype:BlockBlob /encrypt /logdir:<Log file location>

  Subsequent times:

  WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> /blobtype:BlockBlob 

  EXAMPLES

  First time:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER1\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /blobtype:BlockBlob /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"

  Subsequent times:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER1\PSTs\SecondBatch" /dstdir:"ingestiondata/" /blobtype:BlockBlob
    ```

- 如先前說明，PST 檔案匯入到信箱之後， Office 365 匯入服務的暫停保留設定會開啟 (為無限期)。 這表示  *RentionHoldEnabled*  屬性已設定為，  `True` 因此不會處理指派給信箱的保留原則。 防止刪除或封存原則可防止刪除或封存較舊的郵件，這讓信箱擁有者有時間管理新匯入的郵件。 這裡是您管理此暫停保留可採取的一些步驟： 

  - 經過一段時間之後，您可以執行此命令來關閉保留功能  `Set-Mailbox -RetentionHoldEnabled $false` 。 如需指示，請參閱[將信箱設為暫停保留](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)。

  - 您可以設定暫停保留，讓它在未來某一天關閉。 您可以執行此命令來執行此動作  `Set-Mailbox -EndDateForRetentionHold <date>` 。 例如，假設今天的日期是2016年6月1日，而您想要在30天內關閉保留功能，您可以執行下列命令：  `Set-Mailbox -EndDateForRetentionHold 7/1/2016` 。 在此情況下，您可以將  *RentionHoldEnabled*  屬性設定為  *True*。 如需詳細資訊，請參閱 [Set-Mailbox](/powershell/module/exchange/set-mailbox)。

  - 您可以變更指派給信箱的保留原則設定，讓匯入的舊項目不會被立即刪除或移至使用者的封存信箱。 例如，您可以延長指派給信箱的刪除或封存原則的保留存留期。 在這個案例中，您會在變更保留原則設定之後，關閉信箱的暫停保留。 如需詳細資訊，請參閱[設定組織中的信箱封存和刪除原則](set-up-an-archive-and-deletion-policy-for-mailboxes.md)。
