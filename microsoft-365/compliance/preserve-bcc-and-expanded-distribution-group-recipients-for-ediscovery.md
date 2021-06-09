---
title: 保留電子文件探索密件副本與展開的通訊群組收件者
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: In-Place 保留、訴訟暫止及 Microsoft 365 保留原則可讓您保留信箱內容，以符合法規遵從性和 eDiscovery 的需求。
ms.openlocfilehash: f00ed951fb68778b9c62ae874c2cca964bd6cb5c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927939"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>保留電子文件探索密件副本與展開的通訊群組收件者
  
In-Place 保留、訴訟暫止及[Microsoft 365 保留原則](./retention.md) (在安全性 & 規範中心內建立) ，可讓您保留信箱內容，以符合法規遵從性和 eDiscovery 的需求。 預設會在郵件的 [收件者] 和 [副本] 欄位中包含收件者的相關資訊。 不過，您的組織可能需要能夠搜尋並再現郵件之所有收件者的詳細資料。 這包括：
  
- **使用郵件的 [密件副本] 欄位進行位址** 的收件者：密件副本收件者會儲存在寄件者信箱中的郵件中，但不會包含在傳送給收件者之郵件的標頭中。 
    
- **展開的通訊群組** 收件者：接收郵件的收件者，因為這些收件者是通訊群組的成員，其位址是在 [收件者]、[副本] 或 [密件副本] 欄位中。 
    
Exchange Online 和 Exchange Server 2013 (累計更新7和更新版本) 保留密送和展開的通訊群組收件者的相關資訊。 您可以使用 Exchange 系統管理中心的 In-Place eDiscovery 搜尋來搜尋此資訊 (EAC) 或安全性 & 規範中心的內容搜尋。 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>如何保留密件副本收件者和展開的通訊群組收件者

如先前所述，Bcc'ed 收件者的相關資訊會儲存在寄件者信箱中的郵件。 這種資訊已編制索引，可供 eDiscovery 搜尋和保留使用。 
  
在您將信箱設為 In-Place 保留或訴訟資料暫止後，展開的通訊群組收件者的相關資訊會儲存在郵件中。 在 Office 365 中，也會在將 Microsoft 365 保留原則套用至信箱時儲存此資訊。 通訊群組成員資格是在傳送郵件時決定。 在傳送郵件後，群組成員資格的變更不會影響與郵件一起儲存的展開收件者清單。 
  
| 相關資訊 .。。 | 儲存在 .。。 | 預設會儲存？ | 可供存取 .。。 |
|:-----|:-----|:-----|:-----|
|收件者及抄送收件者  <br/> |寄件者和收件者信箱中的郵件屬性。  <br/> |是  <br/> |寄件者、收件者和合規性監察官  <br/> |
|密件副本收件者  <br/> |寄件者信箱中的郵件屬性。  <br/> |是  <br/> |寄件者和合規性監察官  <br/> |
|展開的通訊群組收件者  <br/> |寄件者信箱中的郵件屬性。  <br/> |否。 展開的通訊群組收件者資訊會儲存在信箱置於 In-Place 保留或訴訟資料暫止，或指派給 Microsoft 365 保留原則之後。  <br/> |法規遵循主管  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>搜尋傳送至 Bcc 和展開的通訊群組收件者的郵件

搜尋傳送給收件者的郵件時，eDiscovery 搜尋結果現在包括傳送給收件者所屬之通訊群組的郵件。 下表顯示 eDiscovery 搜尋中傳回傳送至 Bcc 和展開的通訊群組收件者之郵件的案例。
  
案例1： John 是 US-Sales 通訊群組的成員。 此表格顯示在王俊元透過通訊群組直接或間接將郵件傳送給 John 時的 eDiscovery 搜尋結果。
  
| 當您搜尋王俊元的信箱以傳送郵件時 .。。 | 而且會傳送郵件時使用 .。。 | 結果包含郵件？ |
|:-----|:-----|:-----|
|To： John  <br/> |John on TO  <br/> |是  <br/> |
|To： John  <br/> |US-Sales on TO  <br/> |是  <br/> |
|若要：美國銷售  <br/> |US-Sales on TO  <br/> |是  <br/> |
|抄送： John  <br/> |位於 CC 的 John  <br/> |是  <br/> |
|抄送： John  <br/> |US-Sales on CC  <br/> |是  <br/> |
|抄送：美國銷售  <br/> |US-Sales on CC  <br/> |是  <br/> |
   
案例2：王俊元會透過通訊群組) 直接或透過通訊群組，將電子郵件傳送至 John (到/抄送) 和插孔 (Bcc。 下表顯示 eDiscovery 搜尋結果。
  
| 當您搜尋 .。。 | 已傳送的郵件 .。。 | 結果包含郵件？ | 附註 |
|:-----|:-----|:-----|:-----|
|王俊元的信箱  <br/> |To/Cc： John  <br/> |是  <br/> |會顯示指示是否已 Bcc'ed 的插座。  <br/> |
|王俊元的信箱  <br/> |密送：插座  <br/> |是  <br/> |會顯示指示是否已 Bcc'ed 的插座。  <br/> |
|王俊元的信箱  <br/> |Bcc：透過通訊群組的插座 ()   <br/> |是  <br/> |在電子檔探索搜尋預覽、匯出及記錄檔中，Bcc'ed 通訊群組的成員清單（已展開郵件時即會顯示）。  <br/> |
|John 的信箱  <br/> |To/Cc： John  <br/> |是  <br/> |沒有任何指示的密件副本收件者。  <br/> |
|John 的信箱  <br/> |Bcc： (直接或透過通訊群組) 的插座  <br/> |否  <br/> |密送資訊不會儲存在傳送給收件者的郵件中。 您必須搜尋寄件者的信箱。  <br/> |
|插座的信箱  <br/> |收件者/Cc： John (直接或透過通訊群組)   <br/> |是  <br/> |To/Cc 資訊會包含在傳遞給所有收件者的郵件中。  <br/> |
|插座的信箱  <br/> |Bcc： (直接或透過通訊群組) 的插座  <br/> |否  <br/> |密送資訊不會儲存在傳送給收件者的郵件中。 您必須搜尋寄件者的信箱。  <br/> |
   
## <a name="frequently-asked-questions"></a>常見問題集

 **問。[密件副本收件者] 資訊的存放位置和位置是什麼？**
  
答： 寄件者信箱中的原始郵件預設會保留密件副本收件者資訊。 如果 Bcc 收件者是通訊群組，則只有在寄件者的信箱處於保留狀態或指派給 Microsoft 365 保留原則時，才會展開通訊群組成員資格。
  
 **問。展開的通訊群組收件者的清單是在何時和何處儲存？**
  
答： 在傳送郵件時展開群組成員資格。 展開的通訊群組成員清單會儲存于寄件者信箱中的原始郵件。 寄件者的信箱必須處於「In-Place 保留」、「訴訟暫止」或「指派給 Microsoft 365 保留原則」。
  
 **問。[收件者/副本收件者] 可以查看 Bcc'ed 的收件者？**
  
答： 否。 此資訊不會包含在郵件頭中，也不會顯示在/抄送收件者。 寄件者可以查看儲存在其信箱中的原始郵件中的 [密件副本] 欄位。 合規性監察官可以在搜尋寄件者的信箱時，看到此資訊。
  
 **問。如何確定已展開的通訊群組收件者永遠都能保留？**
  
答： 為了確保展開的通訊群組成員永遠會以郵件保留，請[將所有信箱](/Exchange/policy-and-compliance/holds/place-all-mailboxes-on-hold)保留或建立整個組織 Microsoft 365 保留原則。 
  
 **問。支援的群組類型為何？**
  
答： 支援通訊群組、擁有郵件功能的安全性群組和動態通訊群組。 
  
 **問。已展開並儲存在郵件中的通訊群組收件者數目是否有限制？**
  
答： 最多可保留10000個通訊群組的成員。
  
 **問。是否支援嵌套的通訊群組？**
  
答： 是，已展開25層級的嵌套通訊群組。
  
 **問。密送和展開的通訊群組收件者資訊的顯示位置在哪裡？**
  
答： 密送和展開的通訊群組收件者資訊在執行 eDiscovery 搜尋時對合規性監察官是可見的。 密送和展開的通訊群組收件者會包含在複製到探索信箱的搜尋結果中，或匯出至 PST 檔案和包含在搜尋結果中的 eDiscovery 記錄檔中。 「密件副本收件者」資訊也會出現在搜尋預覽中。
  
 **問。當通訊群組的成員在組織的全域通訊清單中隱藏 (GAL) 時，會發生什麼事？**
  
答： 沒有任何影響。 如果收件者隱藏了收件者，這些收件者仍會包含在展開的通訊群組的收件者清單中。