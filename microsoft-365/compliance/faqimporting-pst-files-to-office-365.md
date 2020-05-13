---
title: 匯入 PST 檔案的常見問題集
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: '有關使用 Office 365 Import Service 將組織的 PST 檔案匯入至 Microsoft 365 信箱之系統管理員的常見問題。 '
ms.openlocfilehash: e2ddd464f2cfd421766fb9c4d1043533f5561b25
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208127"
---
# <a name="faq-about-importing-pst-files"></a>匯入 PST 檔案的常見問題集

**本文適用于系統管理員。您是否要將 PST 檔案匯入您自己的信箱？請參閱[從 Outlook .pst 檔案匯入電子郵件、連絡人及行事曆](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
以下是一些有關使用 Office 365 Import Service 將 PST 檔案大量匯入 Microsoft 365 信箱的常見問題。 如需如何匯入 PST 檔案的詳細資訊，請參閱[將 pst 檔案匯入至 Office 365 的概述](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365)。
  
## <a name="using-network-upload-to-import-pst-files"></a>使用網路上傳來匯入 PST 檔案

如需逐步指示，請參閱[使用網路上傳將 PST 檔案匯入 Office 365](use-network-upload-to-import-pst-files.md)。
  
 **必須具備哪些權限才能在 Office365 匯入服務中建立匯入工作？**
  
您必須在 Exchange Online 中獲派信箱匯入匯出角色，才能將 PST 檔案匯入 Microsoft 365 信箱。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. 如需詳細資訊，請參閱[管理 Exchange Online 中的角色](https://go.microsoft.com/fwlink/p/?LinkId=730688)之＜新增角色至角色群組＞或＜建立角色群組＞一節。
  
此外，若要在安全性與合規性中心建立匯入工作，必須符合以下其中一個條件：
  
- 您必須在 Exchange Online 中獲派郵件收件者角色。 根據預設，這個角色會指派給組織管理及收件者管理角色群組。
    
    或者
    
- 您必須是組織中的全域系統管理員。
    
> [!TIP]
> 建議您在 Exchange Online 中建立新的角色群組，專門用來將 PST 檔案匯入 Office 365。 若要獲得匯入 PST 檔案所需的最低權限等級，請將信箱匯入匯出及郵件收件者角色指派到新的角色群組，然後新增成員。 
  
 **哪些地區提供網路上傳服務？**
  
下列地區目前提供網路上傳：美國、加拿大、巴西、英國、法國、歐洲、印度、東亞洲、東南亞、日本、韓國和澳大利亞。 Network upload will be available in more regions soon.

> [!NOTE]
> 目前無法在德國和瑞士使用網路上傳 PST 檔案。 當這些國家/地區開放使用網路上傳時，將會更新此常見問題。
  
 **使用網路上傳匯入 PST 檔案的費用為何？**
  
Using network upload to import PST files is free.
  
這也表示 PST 檔案從 Azure 儲存體區域刪除之後，Microsoft 365 系統管理中心內完整匯入工作的檔案清單中就不會顯示這些檔案。 即使匯入工作仍然列在 **[將資料匯入 Office 365]** 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。 
  
 **哪些版本的 PST 檔案格式支援匯入 Office 365？**
  
有兩個版本的 PST 檔案格式支援此作業：ANSI 和 Unicode。 我們建議您使用 Unicode PST 檔案格式來匯入檔案。 不過，使用 ANSI PST 檔案格式的檔案 (例如，使用雙位元組字元集 (DBCS) 語言的檔案) 也可以匯入 Office 365。 如需有關匯入 ANSI PST 檔案的詳細資訊，請參閱[使用網路上傳將組織的 PST 檔案匯入 Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)中的步驟4。
  
此外，Outlook 2007 和更新版本的 PST 檔案也可以匯入 Office 365。
  
 **將我的 PST 檔案上傳到 Azure 儲存體區域之後，這些檔案會在 Azure 中保留多久的時間才會遭到刪除？**
  
使用網路上傳方法來匯入 PST 檔案會將這些檔案上傳到名為 **ingestiondata** 的 Azure Blob 容器。 如果安全性與合規性中心的 [匯入 PST 檔案]**** 頁面目前沒有進行中的匯入工作，則 Azure 中 **ingestiondata** 容器內的所有 PST 檔案都會在最近的匯入工作於安全性與合規性中心建立完成的後 30 天刪除。 這也表示您必須在 PST 檔案上傳到 Azure 的 30 天內，在安全性與合規性中心建立新的匯入工作 (如網路上傳指示中的步驟 5 所述)。 
  
這也表示 PST 檔案從 Azure 儲存體區域刪除之後，安全性與合規性中心內完整匯入工作的檔案清單中就不會顯示這些檔案。 即使匯入工作仍然列在安全性與合規性中心的 [匯入 PST 檔案]**** 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。 
  
 **需要多久的時間才能將 PST 檔案匯入信箱？**
  
這取決於您的網路容量，但將每 TB 的資料上傳到貴組織的 Azure 儲存體區域通常需要幾個小時的時間。 將 PST 檔案複製到 Azure 儲存體區域之後，系統會以每天至少 24 GB 的速率將 PST 檔案匯入至 Microsoft 365 信箱。 如果這樣的速率不符您的需求，建議您嘗試其他方法將電子郵件資料移轉到 Office 365。 如需詳細資訊，請參閱＜[將多個電子郵件帳戶移轉到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)＞。
  
如果不同的 PST 檔案需匯入到不同的目標信箱，匯入程序會同時進行；換句話說，系統會同時匯入每個 PST/信箱組合。 同樣地，如果多個 PST 檔案匯入到相同的信箱，則會同時匯入。
  
 PST 匯入處理程序如何處理重複的電子郵件項目?****

PST 匯入處理程序會檢查重複的項目，如果目標資料夾、目標信箱或目標封存中已有相同項目，則不會將資料從 PST 檔案複製到信箱或封存。 如果您重新匯入同一個 PST 檔案，並指定與前一個匯入工作指定之資料夾為不同的目標資料夾 (使用 PST 匯入對應檔案中的 TargetRootFolder 屬性)，則所有 PST 檔案中的項目將會重新匯入。

 **匯入 PST 檔案時，是否有郵件大小限制？**
  
是。 如果 PST 檔案包含大於 150 MB 的信箱項目，該項目會在匯入程序執行時略過。
  
 **PST 檔案匯入 Microsoft 365 信箱時是否會保留訊息屬性 (例如訊息的傳送或接收時間、收件者清單、和其他屬性)？**
  
是。 匯入程序不會變更任何原始的訊息中繼資料。
  
 **針對我要匯入至信箱的 PST 檔案，其資料夾階層數是否有上限？**
  
是。您無法匯入具有 300 或更多巢狀資料夾階層的 PST 檔案。
  
 **我是否可以使用網路上傳將 PST 檔案匯入 Office 365 中的非作用中的信箱？**
  
Yes, this capability is now available. 
  
 **我是否可以使用網路上傳將 PST 檔案匯入 Exchange 混合式部署中的線上封存信箱？**
  
是，我們現已推出這項功能。
  
 **我是否可以使用網路上傳方式將 PST 檔匯入 Exchange Online 的公用資料夾？**
  
否，您無法將 PST 檔案匯入公用資料夾。
  
## <a name="using-drive-shipping-to-import-pst-files"></a>使用磁碟機寄送來匯入 PST 檔案

如需逐步指示，請參閱[使用磁片磁碟機運送將 PST 檔案匯入 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md)。
  
 **必須具備哪些權限才能在 Office365 匯入服務中建立匯入工作？**
  
您必須獲派信箱匯入匯出角色，才能將 PST 檔案匯入 Microsoft 365 信箱。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 You can add the Mailbox Import Export role to the Organization Management role group. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member. 如需詳細資訊，請參閱[管理 Exchange Online 中的角色](https://go.microsoft.com/fwlink/p/?LinkId=730688)之＜新增角色至角色群組＞或＜建立角色群組＞一節。
  
此外，若要在安全性與合規性中心建立匯入工作，必須符合以下其中一個條件：
  
- 您必須在 Exchange Online 中獲派郵件收件者角色。 根據預設，這個角色會指派給組織管理及收件者管理角色群組。
    
    或者
    
- 您必須是組織中的全域系統管理員。
    
> [!TIP]
> 建議您在 Exchange Online 中建立新的角色群組，專門用來將 PST 檔案匯入 Office 365。 若要獲得匯入 PST 檔案所需的最低權限等級，請將信箱匯入匯出及郵件收件者角色指派到新的角色群組，然後新增成員。 
  
 **哪些地區提供磁碟機寄送服務？**
  
磁碟機寄送的服務範圍目前包括美國、加拿大、巴西、英國、歐洲、印度、東亞、東南亞、日本、大韓民國和澳洲。 我們會盡快在更多地區提供磁碟機寄送服務。

> [!NOTE]
> 目前在德國和瑞士不開放使用磁碟機寄送匯入 PST 檔案。 當這些國家/地區開放磁碟機寄送時，將會更新此常見問題。
  
 **有哪些商業授權合約支援磁碟機寄送？**
  
Microsoft Enterprise Agreement (EA) 提供將 PST 檔案匯入至 Microsoft 365 的磁碟機寄送服務。 Microsoft Products and Services Agreement (MPSA) 則沒有提供磁碟機寄送。
  
 **使用磁碟機寄送將 PST 檔案匯入至 Microsoft 365 的費用為何？**
  
使用磁碟機寄送將 PST 檔案匯入至 Microsoft 365 信箱的費用為每 GB 的資料 $2 美元。 例如，假設您寄送的硬碟含有 1,000 GB (即 1 TB) 的 PST 檔案，則費用為 $2,000 美元。 您可以與夥伴合作來支付匯入費用。 如需有關尋找合作夥伴的資訊，請參閱[尋找您的 Microsoft 365 合作夥伴或轉售商](https://go.microsoft.com/fwlink/p/?LinkId=785197)。
  
 **哪些類型的硬碟支援磁碟機寄送？**
  
Office 365 匯入服務只支援使用 2.5 吋固態硬碟 (SSD)，或是 2.5 吋或 3.5 吋 SATA II/III 內接式硬碟。 您可以使用最多 10 TB 的硬碟。 匯入作業時，只會處理硬碟上的第一個資料磁碟區。 資料磁碟區必須為 NTFS 格式。 若要將資料複製到硬碟，您可以直接使用 2.5 吋 SSD 或是 2.5 吋或 3.5 吋 SATA II/III 連接器進行連接，或者使用外接式 2.5 吋 SSD 或是 2.5 吋或 3.5 吋 SATA II/III USB 轉接頭進行外接。
  
> [!IMPORTANT]
> Office 365 匯入服務不支援隨附內建 USB 轉接頭的外接式硬碟。 此外，位於外部硬碟外殼內的碟無法使用。 請不要使用外接式硬碟。 
  
 **可以寄送幾個硬碟來進行單一匯入工作？**
  
最多可以寄送 10 個硬碟來進行單一匯入工作。
  
 **寄送硬碟之後，需要多久的時間才會送達 Microsoft 資料中心？**
  
這取決於幾個要素，例如您與 Microsoft 資料中心之間的距離，以及您使用什麼類型的運送選項來寄送硬碟 (例如，隔天送達、兩日送達或陸地運送)。大多數貨運公司提供追蹤號碼，讓您可以追蹤運送狀態。
  
 **硬碟送達 Microsoft 資料中心後，需要多久的時間才能將我的 PST 檔案上傳到 Azure？**
  
當您在 Microsoft 資料中心接收到硬碟後，需要7到10個工作日才能將 PST 檔案上傳至組織的 Azure 存放區。 PST 檔案會上傳至名為**ingestiondata**的 Azure blob 容器。 
  
 **需要多久的時間才能將 PST 檔案匯入信箱？**
  
PST 檔案上傳到 Azure 儲存體區域之後，Microsoft 365 會以安全的方式分析 PST 檔案中的資料，以識別 PST 檔案所含項目的存留期和各種訊息類型。 這項分析程序完成後，您就可以選擇匯入 PST 檔案中的所有資料，或設定篩選器來控制要匯入的資料。 開始匯入工作之後，PST 會以每天至少 24 GB 的速率匯入至 Microsoft 365 信箱。 如果這樣的速率不符您的需求，建議您嘗試其他方法將電子郵件資料匯入到 Office 365。 如需詳細資訊，請參閱＜[將多個電子郵件帳戶移轉到 Office 365 的方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)＞。
  
如果不同的 PST 檔案需匯入到不同的目標信箱，匯入程序會同時進行；換句話說，系統會同時匯入每個 PST/信箱組合。 同樣地，如果多個 PST 檔案匯入到相同的信箱，則會同時匯入。
  
 **Microsoft 將我的 PST 檔案上傳到 Azure 之後，這些檔案會在 Azure 中保留多久的時間才會刪除？**
  
在 [安全性 & 合規性中心的 [匯**入 PST**檔案] 頁面上建立最近的匯入工作30天之後，會刪除您組織之 Azure 儲存體位置中的所有 PST 檔案（在 blob 容器中稱為**ingestiondata**）。 
  
這也表示 PST 檔案從 Azure 儲存體區域刪除之後，安全性與合規性中心內完整匯入工作的檔案清單中就不會顯示這些檔案。 即使匯入工作仍然列在安全性與合規性中心的 [匯入 PST 檔案]**** 頁面上，但當您檢視較舊匯入工作的詳細資料時，PST 檔案清單可能為空白。 
  
 **哪些版本的 PST 檔案格式支援匯入至 Microsoft 365？**
  
有兩個版本的 PST 檔案格式支援此作業：ANSI 和 Unicode。 我們建議您使用 Unicode PST 檔案格式來匯入檔案。 不過，使用 ANSI PST 檔案格式的檔案 (例如，使用雙位元組字元集 (DBCS) 語言的檔案) 也可以匯入至 Microsoft 365。 如需有關匯入 ANSI PST 檔案的詳細資訊，請參閱[使用磁片磁碟機運送將 PST 檔案匯入至 Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)中的步驟3。
  
此外，Outlook 2007 和更新版本的 PST 檔案也可以匯入 Office 365。
  
 **匯入 PST 檔案時，是否有郵件大小限制？**
  
是。 如果 PST 檔案包含大於 150 MB 的信箱項目，該項目會在匯入程序執行時略過。
  
  PST 匯入處理程序如何處理重複的電子郵件項目?****

PST 匯入處理程序會檢查重複的項目，如果目標資料夾、目標信箱或目標封存中已有相同項目，則不會將資料從 PST 檔案複製到信箱或封存。 如果您重新匯入同一個 PST 檔案，並指定與前一個匯入工作指定之資料夾為不同的目標資料夾 (使用 PST 匯入對應檔案中的 TargetRootFolder 屬性)，則所有 PST 檔案中的項目將會重新匯入。
 
 **PST 檔案匯入 Microsoft 365 信箱時是否會保留訊息屬性 (例如訊息的傳送或接收時間、收件者清單、和其他屬性)？**
  
是。 匯入程序不會變更任何原始的訊息中繼資料
  
 **針對我要匯入至信箱的 PST 檔案，其資料夾階層數是否有上限？**
  
是。您無法匯入具有 300 或更多巢狀資料夾階層的 PST 檔案。
  
 **我是否可以使用磁碟機寄送將 PST 檔案匯入至 Microsoft 365 中的非作用中的信箱？**
  
是，我們現已推出這項功能。
  
 **我是否可以使用磁碟機寄送將 PST 檔案匯入 Exchange 混合式部署中的線上封存信箱？**
  
是，我們現已推出這項功能。
  
 **我是否可以使用磁碟機寄送方式將 PST 檔案匯入 Exchange Online 的公用資料夾？**
  
否，您無法將 PST 檔案匯入公用資料夾。
  
 **Microsoft 是否可以先將硬碟清空再寄回給我？**
  
否，Microsoft 無法先將硬碟清空再寄回給客戶。硬碟會以 Microsoft 當初收到的狀態寄回給您。
  
 **Microsoft 是否可以先將硬碟銷毀再寄回給我？**
  
否，Microsoft 不能破壞您的硬碟。硬碟會以 Microsoft 當初收到的狀態寄回給您。
  
 **哪些快遞服務支援將硬碟寄回客戶？**
  
如果您是位於美國或歐洲地區的客戶，Microsoft 會使用 FedEx 將硬碟寄回給您。針對所有其他區域，Microsoft 則會使用 DHL。
  
 **將硬碟寄回需要多少費用？**
  
實際的寄回費用取決於您將硬碟寄出的所在地區與 Microsoft 資料中心之間的距離。Microsoft 會從您的 FedEx 或 DHL 帳戶收取硬碟寄回費用。寄回費用需由您自行承擔。
  
 **我是否能使用自訂運送服務 (例如 FedEx 自訂運送) 將我的硬碟寄給 Microsoft？**
  
是。
  
 **如果我需要將硬碟寄到其他國家/地區，我需要採取什麼動作嗎？**
  
您寄給 Microsoft 的硬碟可能會跨國際邊界。在這種情況下，您必須負責確保硬碟和當中的資料可依據相關法律進口和/或出口。寄送硬碟之前，請與您的顧問確認磁碟機和當中的資料可以合法地寄到指定的 Microsoft 資料中心，以確保 Microsoft 能夠及時收到您的硬碟。
