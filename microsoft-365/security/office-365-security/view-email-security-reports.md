---
title: 檢視安全性中的電子郵件安全性報告&amp;合規性中心 Compromised 使用者，加密、 威脅保護狀態，惡意程式碼偵測、 上方惡意程式碼、 垃圾郵件偵測傳送和接收電子郵件、 使用者所報告的郵件、 讀取的報告、 偵測、 安全性資料、 安全性資訊
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 01/16/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 了解如何尋找並使用您的組織電子郵件安全性報告。 安全性中的電子郵件安全性報告可用&amp;合規性中心。
ms.openlocfilehash: c44944c8f392b2df8cfe4b9e1741ba4b7ea13382
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2020
ms.locfileid: "41209948"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a>檢視安全性與合規性中心內的電子郵件安全性報告

提供各種報告所[安全性&amp;合規性中心](https://protection.office.com)可協助您查看如何電子郵件安全性功能，例如 Office 365 中的反垃圾郵件、 反惡意程式碼及加密功能保護您的組織。 如果您有[必要權限](#what-permissions-are-needed-to-view-these-reports)，您可以檢視這些報告中的安全性&amp;合規性中心，移至**報表** \> **儀表板**。
  
![儀表板您瞭解進階威脅防護的運作方式](../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
您的電子郵件安全性報告包括下列：
- [危害使用者報告 (**新增 ！**)](#compromised-users-report-new)
- [加密報表](#encryption-report)
- [威脅防護狀態報告](#threat-protection-status-report) 
- [惡意程式碼偵測報告](#malware-detections-report) 
- [上方的惡意程式碼報告](#top-malware-report)
- [上方的寄件者和收件者的報告](#top-senders-and-recipients-report)
- [詐騙偵測報告](#spoof-detections-report)
- [垃圾郵件偵測報告](#spam-detections-report)
- [傳送和接收電子郵件報告](#sent-and-received-email-report)
- [使用者回報郵件報告](#user-reported-messages-report)


## <a name="compromised-users-report-new"></a>危害使用者報告 (**新增 ！**) 

這份報告，可與 Exchange Online Protection 中，任何人都顯示標示為 Suspicious 或受限的使用者，當帳戶輸入狀態指出的使用者帳戶的其中一個特別有用的資料可能有問題，或偶數的使用者帳戶的數目洩漏。 經常使用與危害使用者報告可以找出突發性，以及偶數的趨勢，標示可疑或有限狀態，讓的證據可能會有此問題： 安全性與您的租用戶同等重要的帳戶中。

![遭入侵的使用者報告為它會出現在 Office 365。](../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

## <a name="encryption-report"></a>加密報表

**加密報表**顯示已加密，透過您的組織原則，或透過使用者控制項的電子郵件的相關資訊。 貴組織的安全性小組可以找出模式並主動或套用調整機密電子郵件的原則，以使用此報告中資訊。

若要檢視此報告中，安全性 & 合規性中心，移至**報表** \> **儀表板** \> **加密報表**。

![加密報表](../media/encryptionreport-defaultview.png) 

報告第一次開啟時，您會看到在過去七 （7） 天適用於電子郵件訊息的加密方法的相關資料。 您可以變更的日期範圍，會顯示在報告中的 [**篩選器**的畫面右上角的詳細資料。

![加密報告篩選器](../media/encryptionreport-filters.png)   

您也可以使用 [**依細分**] 功能表來檢視資料的加密範本 （或方法）。

![加密方法或範本](../media/encryptionreport-breakdownby.png)

然後您可以使用 [**檢視資料**] 功能表變更檢視，以查看已加密郵件的頂端的五個收件者網域的計數。

![依據] 功能表的加密報表檢視資料](../media/encryptionreport-viewdataby.png)

在新的加密報告的彈性，您可以檢視趨勢，並採取適當的動作。 例如，如果您看到大量的使用者所加密的電子郵件，您可能要新增某些使用情況下，自動化加密加密原則。 （若要取得的說明，請參閱[定義郵件流規則以加密 Office 365 中的電子郵件](../../compliance/define-mail-flow-rules-to-encrypt-email.md)）。另一個範例是，如果您有可用的加密範本的數字，但沒有人正在使用這些，您可能會瀏覽是否使用者需要訓練該功能。 

使用此報告可讓您組織的安全性與合規性小組，以監視使用郵件加密的方式，以及是否進一步動作所需。 若要深入了解加密，請參閱[Office 365 中的電子郵件加密](../../compliance/email-encryption.md)。

## <a name="threat-protection-status-report"></a>威脅防護狀態報告

**威脅保護狀態**報表的智慧顯示的報告，已偵測並封鎖 Exchange Online protection 的惡意電子郵件。 這份報告可以用來檢視被識別為惡意程式碼的電子郵件或網路釣魚嘗試透過時間 （最多為 90 天），以及它可讓安全性系統管理員識別趨勢或判斷原則是否需要調整。

> [!NOTE]
> 威脅保護狀態報表是適用於擁有[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)或[Exchange Online Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop) (EOP); 客戶然而，ATP 客戶威脅保護狀態報表中顯示的資訊可能會包含不同資料比 EOP 客戶可能會看到的內容。 例如，EOP 客戶可以檢視電子郵件，但不是[在 SharePoint Online、 OneDrive 或 Microsoft Teams 中偵測到惡意檔案](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)的相關資訊，ATP 特有功能中偵測到的惡意程式碼的相關資訊。 （[深入了解更多關於 ATP 報告](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)）。
  
若要檢視此報告中，在[安全性&amp;合規性中心](https://protection.office.com)，請移至**報表** \> **儀表板** \> **威脅保護狀態**。
  
![威脅防護狀態報告](../media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
當您首次開啟威脅保護狀態報表時，報告顯示資料的過去 7 天的預設值;不過，您可以按一下 [**篩選**]，並 90 天的詳細資料變更日期範圍。 （如果您使用試用訂閱，您可能會受限於的 30 天的資料。）

這份報告是適用於檢視的效率和影響貴組織的[Exchange Online Protection 功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)，以及更長期的趨勢。 
  
![威脅保護狀態報告的篩選器](../media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
您也可以選擇是否要檢視的電子郵件被識別為惡意的資料，識別為網路釣魚嘗試，電子郵件或電子郵件被識別為包含惡意程式碼。
  
![威脅保護狀態報表檢視選項](../media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a>惡意程式碼偵測報告

**惡意程式碼偵測**報告 」 顯示為包含組織的惡意程式碼偵測到多少的內送和外寄郵件。 
  
若要檢視此報告中，在[安全性&amp;合規性中心](https://protection.office.com)，請移至**報表** \> **儀表板** \> **惡意程式碼偵測**。
  
![惡意程式碼偵測] 報告範例](../media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
類似其他報表，例如[威脅保護狀態報表](#threat-protection-status-report)，報告預設會顯示資料的過去 7 天。 不過，您可以選擇要變更的日期範圍**篩選器**。 
  
## <a name="top-malware-report"></a>上方的惡意程式碼報告

**Top 惡意程式碼**報告 」 顯示各種不同的[Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/eop-features)所偵測到的惡意程式碼。 
  
若要檢視此報告中，在[安全性&amp;合規性中心](https://protection.office.com)，請移至**報表** \> **儀表板** \> **頂端惡意程式碼**。
  
![SCC-EOP 上方惡意程式碼](../media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
當您將滑鼠停留在圓形圖扇形擴展時，您可以看到的惡意程式碼和為具有該惡意程式碼偵測到多少郵件類型的名稱。
  
按一下 （或點選），在新的瀏覽器視窗，您可以在哪裡取得報告的詳細的檢視中開啟報表。
  
![這份報告顯示上方的惡意程式碼偵測到您的組織](../media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
下方圖表中，您會看到偵測到惡意程式碼和為具有該惡意程式碼偵測到多少郵件的清單。
  
## <a name="top-senders-and-recipients-report"></a>上方的寄件者和收件者的報告

**Top 寄件者和收件者**的報告是顯示您上方的電子郵件寄件者圓形圖帶有子橫條圖。 
  
若要檢視此報告中，在[安全性&amp;合規性中心](https://protection.office.com)，請移至**報表** \> **儀表板** \> **頂端寄件者和收件者**。
  
![若要檢視此報告中，安全性&amp;合規性中心，移至報表\>儀表板\>頂端寄件者和收件者](../media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
當您將滑鼠停留在圓形圖扇形擴展時，您可以看到傳送或接收郵件計數。
  
按一下 （或點選），在新的瀏覽器視窗，您可以在哪裡取得報告的詳細的檢視中開啟報表。
  
用於**顯示資料**] 清單中選擇要檢視的主要寄件者，接收器、 垃圾郵件收件者、 惡意程式碼收件者的資料。 您也可以查看誰收到偵測到[Exchange Online](https://docs.microsoft.com/microsoft-365/security/office-365-security/what-is-eop)protection 的惡意程式碼。 
  
![使用 [顯示資料的清單以檢視特定的資訊](../media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
下方圖表中，您會看到誰上方的電子郵件寄件者或收件者，以及傳送或接收的指定的時間期間內郵件計數。
  
## <a name="spoof-detections-report"></a>詐騙偵測報告

**詐騙偵測**報告 」 可顯示已偵測到多少詐騙郵件，以及那些標籤哪些項目已被視為 「 良好 」 （詐騙郵件為合法的商業原因而完成）。 
  
若要檢視此報告中，在[安全性&amp;合規性中心](https://protection.office.com)，請移至**報表** \> **儀表板** \> **詐騙郵件**。
  
![安全性&amp;合規性中心，移至報表\>儀表板\>詐騙郵件](../media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
當您將滑鼠停留一天圖表中時，您可以看到多少詐騙郵件是透過。
  
按一下 （或點選），在新的瀏覽器視窗，您可以在哪裡取得報告的詳細的檢視中開啟報表。 若要深入了解反詐騙保護，請參閱[在 Office 365 中的反詐騙保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection)。
  
## <a name="spam-detections-report"></a>垃圾郵件偵測報告

[**垃圾郵件偵測**] 報告顯示封鎖的 Exchange Online 中的垃圾郵件內容。 郵件會計算每封郵件，而不是個別寄件者。 例如，如果電子郵件已傳送給組織中的 100 收件者，它就會計算成一封郵件。
  
若要檢視此報告中，在[安全性&amp;合規性中心](https://protection.office.com)，請移至**報表** \> **儀表板** \> **垃圾郵件偵測**。
  
![若要檢視此報告中，安全性&amp;合規性中心，移至報表\>儀表板\>EOP 垃圾郵件偵測](../media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
當您將滑鼠停留一天圖表中時，您可以看到多少個項目遭到封鎖該日，以及如何分類項目。 例如，您可以看到多少垃圾郵件進行篩選，以及多少個項目是來自封鎖的網際網路通訊協定 (IP) 位址。
  
按一下 （或點選），在新的瀏覽器視窗，您可以在哪裡取得報告的詳細的檢視中開啟報表。
  
![[垃圾郵件偵測] 報告會告訴您如何許多垃圾郵件被封鎖或篩選出](../media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
下方圖表中，您會看到所偵測到的垃圾郵件項目清單。 選取要檢視其他資訊，例如垃圾郵件項目已輸入或輸出、 其郵件識別碼，以及其收件者的項目。 若要深入了解反垃圾郵件保護，請參閱[Office 365 電子郵件反垃圾郵件保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)。
  
## <a name="sent-and-received-email-report"></a>傳送和接收電子郵件報告

**已傳送和接收的電子郵件**報告是智慧報表顯示資訊內送和外寄電子郵件，包括垃圾郵件偵測、 惡意程式碼，以及電子郵件被識別為 「 良好 」。 
  
若要檢視此報告中，在[安全性&amp;合規性中心](https://protection.office.com)，請移至**報表** \> **儀表板** \> **已傳送和接收的電子郵件**。
  
![若要檢視此報告中，安全性&amp;合規性中心，移至報表\>儀表板\>已傳送和接收的電子郵件](../media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
當您將滑鼠停留一天圖表中時，您可以看到多少郵件的來源，以及這些郵件分類的方式。 例如，您可以看到為包含惡意程式碼，偵測到多少郵件和多少被判定為垃圾郵件。
  
按一下 （或點選），在新的瀏覽器視窗，您可以在哪裡取得報告的詳細的檢視中開啟報表。
  
您可以使用**細分的**清單檢視類型，或方向 （內送和外寄） 的資訊。 
  
![使用 [自動換行向下依據] 清單來檢視資訊類型或方向](../media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
下方圖表中，您會看到一份電子郵件類別，例如**GoodMail**、 **SpamContentFiltered**，等等。 選取要檢視其他資訊，例如惡意程式碼，所採取的動作和是否電子郵件類別是傳入或傳出。
  
![此報表會告訴您有關反惡意程式碼、 反垃圾郵件和其他郵件偵測](../media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)

若要深入了解電子郵件智慧，請參閱[在 Office 365 中的郵件流程情報](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-intelligence-in-office-365)。
  
## <a name="user-reported-messages-report"></a>使用者回報郵件報告

**使用者回報郵件**報告會顯示使用者會回報為垃圾郵件、 網路釣魚企圖或良好郵件[報告訊息增益集](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)使用的電子郵件的相關資訊。
  
詳細資料可供每則訊息，包括傳遞的原因，這類垃圾郵件原則的例外狀況或組織設定的郵件流程規則。 若要檢視的詳細資訊，請在使用者報告] 清單中，選取項目，然後檢視資訊**摘要**和**詳細資料**] 索引標籤上。 
  
![User-Reported 郵件報告顯示標示為垃圾郵件、 非垃圾郵件或網路釣魚嘗試的郵件使用者。](../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
若要檢視此報告中，在[安全性&amp;合規性中心](https://protection.office.com)，執行下列其中一項：
  
- 移至**威脅管理，** \> **儀表板** \> **使用者報告的郵件**。
    
- 移至**威脅管理，** \> **檢閱** \> **使用者報告的郵件**。
    
![安全性&amp;合規性中心，選擇 [威脅管理\>檢閱\>使用者所報告的郵件](../media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> 在順序，如使用者回報郵件報告能夠正常運作，**必須先開啟稽核記錄功能**適用於 Office 365 環境。 這項工作通常是由在 Exchange Online 中獲派稽核記錄角色的人員完成。 如需詳細資訊，請參閱[開啟或關閉 Office 365 稽核記錄搜尋](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)。 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a>若要檢視這些報告需要哪些權限？

若要檢視及使用本文中所述的報告**您必須具有適當的角色指派給這兩種安全性&amp;規範中心和 Exchange 系統管理中心**。

- 針對「安全性與合規性中心」，您必須受指派下列其中一個角色：
    - 組織管理
    - 安全性系統管理員 (這可以在 Azure Active Directory 系統管理中心中指派 ([https://aad.portal.azure.com](https://aad.portal.azure.com))
    - 安全性讀取者

- 針對 Exchange Online，您必須在 Exchange 系統管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) 或 PowerShell Cmdlet (請參閱 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) 受指派下列其中一個角色：
    - 組織管理
    - 僅檢視組織管理
    - 僅檢視收件者角色
    - 合規性管理

若要深入了解，請參閱下列資源：

- [Office 365 安全性與合規性中心權限](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

- [Exchange Online 中的功能權限](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a>如果報表不顯示資料？

如果您不在報表中看到的資料，請仔細檢查您的原則已正確設定。 若要深入了解，請參閱[防範 Office 365 中的威脅](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。
  
## <a name="related-topics"></a>相關主題

[Office 365 電子郵件的反垃圾郵件保護](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)
  
[報告和 Office 365 安全性的深入解析&amp;合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/reports-and-insights-in-security-and-compliance)
  
[建立報表排程安全性&amp;合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-a-schedule-for-a-report)
  
[設定及下載自訂報告中的安全性&amp;合規性中心](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-and-download-a-custom-report)
  

