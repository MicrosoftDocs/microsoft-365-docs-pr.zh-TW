---
title: GDPR 的 Azure 資料主體要求
description: ''
keywords: Microsoft 365、Microsoft 365 教育版、Microsoft 365 文件、GDPR
author: BrendaCarter
localization_priority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: 8066b7a69b8f6a8ec2a75eea4a8816f4c3b3ef93
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2018
ms.locfileid: "26866788"
---
# <a name="azure-data-subject-requests-for-the-gdpr"></a>GDPR 的 Azure 資料主體要求

## <a name="introduction-to-data-subject-requests-dsrs"></a>資料主體要求 (DSR) 簡介

歐盟資料保護規範 (GDPR) 賦予人員 (在規範中稱為「資料主體」**) 權限，以管理由雇主或其他類型的公司或組織 (稱為「資料控制者」** 或簡稱「控制者」**) 收集而來的個人資料。個人資料在 GDPR 中的定義非常廣泛，係指與已識別或可識別的自然人相關的任何資料。GDPR 賦予資料主體對其個人資料的特定權限，這些權限包括取得個人資料副本、要求更正資料、限制資料的處理、刪除資料或以電子格式接收資料，以便轉交給其他控制者。由資料主體向控制者提出對其個人資料採取某項動作的正式要求，稱為「資料主體要求」** 或 DSR。

本指南會討論如何使用 Microsoft 產品、服務及系統管理工具，協助我們的控制者客戶找出並對個人資料採取動作，以回應 DSR；尤其是針對如何找出、存取與處理在 Microsoft 雲端中常駐的個人資料。以下是本指南中所述程序的快速概觀：

1.  ***探索***—使用搜尋和探索工具，讓您更輕鬆地找到可能是 DSR 主體的客戶資料。一旦收集了潛在回應文件，您就可以執行下列步驟中所述的一或多個 DSR 動作以回應要求。或者，您也可能判斷該要求不符合貴組織回應 DSR 的指導方針。

2.  ***存取***—擷取在 Microsoft 雲端中常駐的個人資料，若有要求，請製作可供資料主體使用的副本。

3.  ***修正***—在適用情況下，對個人資料進行變更或實行其他要求的動作。

4.  ***限制***—透過移除各種不同 Azure 服務的授權，或在可行處關閉所需的服務，對個人資料的處理設下限制。您也可以從 Microsoft 雲端中移除資料，並在內部部署或其他位置保留資料。

5.  ***刪除***—將會永久移除 Microsoft 雲端中常駐的個人資料。

6.  ***匯出***—將個人資料的電子副本 (以機器可讀取的格式) 提供給資料主體。

本指南中的每一節說明資料控制者組織可以採取的程序，以回應對 Microsoft 雲端中個人資料的 DSR。

<span id="_Toc511384801" class="anchor"><span id="_Toc511163872" class="anchor"><span id="_Toc511136229" class="anchor"><span id="_Toc511125162" class="anchor"><span id="_Toc511120749" class="anchor"><span id="_Toc511122656" class="anchor"><span id="_Toc508792503" class="anchor"></span></span></span></span></span></span></span>
### <a name="terminology"></a>術語

以下提供與本指南相關的詞彙定義。

-   *控制者—* 自然人或法人、公家機關、公司或其他主體，不論單獨或與其他單位聯合，會判斷處理個人資料的用途以及方式，其中此類處理的用途以及方式的判斷是根據聯盟與成員國法律，控制者人選或提名控制者的特定準則可由聯盟與成員國法律提供。

-   *個人資料*和 *資料主體—* 表示與已識別或可識別之自然人 (以下稱為「資料主體」) 相關的任何資訊；可識別的自然人是可以直接或間接識別的人員，尤其是藉由參照如名稱、身分證號碼、位置資料、線上識別碼，或特定於該自然人的身體、生理、基因、心理、經濟、文化或社會身份等一個或多個識別碼來識別。

-   *處理者—* 自然人或法人、公家機關、公司，或代表控制者處理個人資料的其他主體。

-   *客戶資料*—由客戶本身或客戶代表，透過企業服務所提供給 Microsoft 的所有資料，包括所有文字、音訊、視訊或影像檔案和軟體。客戶資料包括 (1) 使用者的識別資訊 (例如 Azure Active Directory 中的使用者名稱和連絡人資訊)，以及客戶上傳到特定服務或在特定服務中建立的客戶內容 (例如，Azure 儲存體帳戶中的客戶內容、Azure SQL Database 的客戶內容，或 Azure 虛擬機器中客戶的虛擬機器映像)。

-   *系統所產生的記錄檔*–Microsoft 所產生的記錄檔及相關資料，可協助 Microsoft 向使用者提供企業服務。系統所產生的記錄檔主要包含經過假名化處理的資料 (例如唯一識別碼，通常由系統所產生，無法單獨用來識別個人，但可用來向使用者提供企業服務)。系統所產生的記錄檔也可能包含使用者的識別資訊 (例如使用者名稱)。

<span id="_Toc511384802" class="anchor"><span id="_Toc511163873" class="anchor"><span id="_Toc511136230" class="anchor"><span id="_Toc511125163" class="anchor"><span id="_Toc511120750" class="anchor"><span id="_Toc511122657" class="anchor"><span id="_Toc508792504" class="anchor"></span></span></span></span></span></span></span>

### <a name="how-to-use-this-guide"></a>如何使用本指南

本指南包含兩個部分：

**第 1 部分：回應資料主體對客戶資料的要求**—本指南中的第 1 部分討論了如何從您所撰寫資料的應用程式中，存取、修正、限制、刪除以及匯出資料。本節將詳細說明如何針對客戶內容以及識別資訊執行 DSR。

**第 2 部分：回應資料主體對系統所產生記錄檔的要求**—當您使用 Microsoft 企業服務時，Microsoft 會產生某些資訊 (稱為「系統所產生的記錄檔」) 以提供服務。本指南中的第 2 部分將討論如何針對 Azure 來存取、刪除及匯出這類資訊。

<span id="_Toc511384803" class="anchor"><span id="_Toc511163874" class="anchor"></span></span>

### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-service-accounts"></a>了解 Azure Active Directory 和 Microsoft 服務帳戶的 DSR

在考慮為企業客戶所提供的服務時，請務必了解要在指定的 Azure Active Directory (AAD) 範圍內執行 DSR。值得注意的是，DSR 一律會在指定的 AAD 租用戶中執行。如果使用者參與了多個租用戶，請務必強調特定的 DSR「只能」** 在接收到要求的指定租用戶範圍內執行。請務必了解這點，因為這代表由某個企業客戶所執行的 DSR **不會**影響相鄰企業客戶的資料。

在提供給企業客戶的服務範圍內，這點同樣也適用於 Microsoft 服務帳戶 (MSA)：對「與 AAD 租用戶相關聯的」** MSA 帳戶所執行的 DSR，**只會**針對租用戶中的資料。此外，在處理租用戶中的 MSA 帳戶時，請務必了解下列事項：

-   若 MSA 使用者建立了 Azure 訂用帳戶，我們會將該訂用帳戶視為 AAD 租用戶來處理。因此，DSR 的範圍會限制在租用戶內，如上所述。

-   若您刪除了透過 MSA 帳戶所建立的 Azure 訂用帳戶，**將不會影響到**實際的 MSA 帳戶。同樣地，如上所述，在 Azure 訂用帳戶中所執行的 DSR，會限制在租用戶本身的範圍內。

**在指定的租用戶外**，對 MSA 帳戶本身所執行的 DSR，會透過消費者隱私權儀表板來執行。請參閱《Windows 資料主體要求指南》以取得詳細資訊。

<span id="_Toc508792505" class="anchor"><span id="_Toc511384804" class="anchor"><span id="_Toc511163875" class="anchor"><span id="_Toc511136231" class="anchor"><span id="_Toc511125164" class="anchor"><span id="_Toc511120751" class="anchor"><span id="_Toc511122658" class="anchor"></span></span></span></span></span></span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a>第 1 部分：客戶資料的 DSR 指南

<span id="_Toc511384805" class="anchor"><span id="_Toc511163876" class="anchor"><span id="_Toc511136232" class="anchor"><span id="_Toc511125165" class="anchor"><span id="_Toc511120752" class="anchor"><span id="_Toc511122659" class="anchor"></span></span></span></span></span></span>

## <a name="executing-dsrs-against-customer-data"></a>針對客戶資料執行 DSR

Microsoft 透過 Azure 入口網站，提供了存取、刪除及匯出特定客戶資料的功能；您也可直接透過既有的應用程式開發介面 (API) 或特定服務的使用者介面 (UI) 來執行上述功能 (也稱為「產品內體驗」**)。在上述服務各自的參考文件中有詳細資料，說明這類的產品內體驗。

>[重要事項]  
> 支援產品內 DSR 的服務需要直接使用服務的應用程式開發介面 (API) 或使用者介面 (UI)，來描述適用的 CRUD (建立、讀取、更新、刪除) 作業。因此，除了在 Azure 入口網站中執行 DSR 以外，還必須另外在指定的服務中執行 DSR，才能完成指定資料主體的完整要求。請參閱特定服務的參考文件，以取得詳細資訊。

<span id="_Discover" class="anchor"><span id="_Toc508792508" class="anchor"><span id="_Toc511122661" class="anchor"><span id="_Toc511120754" class="anchor"><span id="_Toc511125167" class="anchor"><span id="_Toc511136234" class="anchor"><span id="_Toc511163877" class="anchor"><span id="_Toc511384806" class="anchor"></span></span></span></span></span></span></span></span>
## <a name="step-1-discover"></a>步驟 1：探索

回應 DSR 的第一個步驟是先找出個人資料，也就是要求的主體。第一個步驟 (尋找並檢閱上述的個人資料)，可協助您判斷 DSR 是否符合貴組織的需求，以便接受或拒絕。第一個步驟 (尋找並檢閱上述的個人資料)，可協助您判斷 DSR 是否符合貴組織的需求，以便接受或拒絕。例如，在找出並檢閱個人資料後，您可能因為這樣做會對其他人的權利和自由造成負面影響，而判斷要求不符合貴組織的需求。

找到資料後，接著您可以執行指定的動作來滿足資料主體的要求。

<span id="_Toc511384807" class="anchor"><span id="_Toc511163878" class="anchor"><span id="_Toc511136235" class="anchor"><span id="_Toc511125168" class="anchor"><span id="_Toc511120755" class="anchor"><span id="_Toc511122662" class="anchor"></span></span></span></span></span></span>
### <a name="azure-active-directory"></a>Azure Active Directory

[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) Microsoft 的雲端式、多租用戶目錄與身分識別管理服務。您可以使用 [Azure 入口網站](https://portal.azure.com/)找出使用者的識別資訊，例如客戶和員工的使用者設定檔及使用者工作資訊，其中包含在您 [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) 環境中的個人資料。

這在想要尋找或變更特定使用者的個人資料時尤其有用。您也可以新增或變更使用者設定檔與工作資訊。您必須使用目錄的全域系統管理員帳戶來登入。

#### <a name="how-do-i-locate-or-view-user-profile-and-work-information"></a>如何找出或檢視使用者設定檔及工作資訊？

1. 請用目錄的全域系統管理員帳戶來登入 [Azure 入口網站](https://portal.azure.com/)。

1. 請選取 [所有服務]****、在文字方塊中輸入 [使用者和群組]****，然後選取 [輸入]****。

     ![選取所有的服務](media/azure-dsr_image3.png)

3. 在 [使用者和群組]**** 刀鋒視窗上，選取 [使用者]****。

     ![選取使用者](media/azure-dsr_image9.png)

4.  請在 [使用者和群組 - 使用者]**** 刀鋒視窗中，從清單中選取使用者；然後在所選使用者的刀鋒視窗中，選取 [設定檔]**** 以檢視可能包含個人資料的使用者設定檔資訊。

    ![選取設定檔](media/azure-dsr_image5.png)

5. 若您需要新增或變更使用者設定檔資訊，可以這麼做；然後請在命令列中選取 [儲存]****。

<!-- steps 6 and 7 not in original 
6. On the blade for the selected user, select **Work Info** to view user work information that may contain personal data.

     ![Select work info](media/azure-dsr_image11.png)

7. If you need to add or change user work information, you can do so, and then, in the command bar, select **Save.**

end of text to isolate -->

<span id="_Toc511384808" class="anchor"><span id="_Toc511163879" class="anchor"><span id="_Toc511136236" class="anchor"><span id="_Toc511125169" class="anchor"><span id="_Toc511120756" class="anchor"><span id="_Toc511122663" class="anchor"></span></span></span></span></span></span>

### <a name="service-specific-interfaces"></a>服務特定介面

Microsoft 提供直接透過既有的應用程式開發介面 (API) 或特定服務的使用者介面 (UI)，來探索客戶資料的能力。在上述服務各自的參考文件中有詳細資料，說明了適用的 CRUD (建立、讀取、更新、刪除) 作業。

<span id="_Access" class="anchor"><span id="_Toc508792512" class="anchor"><span id="_Ref511119401" class="anchor"><span id="_Toc511122664" class="anchor"><span id="_Toc511120757" class="anchor"><span id="_Toc511125170" class="anchor"><span id="_Toc511136237" class="anchor"><span id="_Toc511163880" class="anchor"><span id="_Toc511384809" class="anchor"><span id="_Hlk503968195" class="anchor"></span></span></span></span></span></span></span></span></span></span>
## <a name="step-2-access"></a>步驟 2：存取

找到包含個人資料且可能會回應 DSR 的客戶資料之後，您與貴組織有權決定要將哪些資料提供給資料主體。您可以提供他們實際文件的副本、經過適當刪減的版本，或您認為適合分享的部分螢幕擷取畫面。對於這些存取要求的每項回應，您都必須擷取一份文件副本，或其他包含回應資料的項目。

當您提供副本給資料主體時，可能需要移除或刪減關於其他資料主體的個人資訊，以及任何機密資訊。

<span id="_Using_Content_Search_1" class="anchor"></span>以下說明如何取得資料副本以便回應 DSR 存取要求。

<span id="_Rectify" class="anchor"><span id="_Ref511119463" class="anchor"><span id="_Toc511122665" class="anchor"><span id="_Toc511120758" class="anchor"><span id="_Toc511125171" class="anchor"><span id="_Toc511136238" class="anchor"><span id="_Toc511163881" class="anchor"><span id="_Toc511384810" class="anchor"></span></span></span></span></span></span></span></span>

### <a name="azure-active-directory"></a>Azure Active Directory

<span id="_Forms_1" class="anchor"></span>Microsoft 提供入口網站與產品內體驗，讓企業客戶的租用戶系統管理員能夠管理 DSR 存取要求。DSR 存取要求存取要求可允許針對下列使用者個人資料進行存取，包括：(a) 使用者的識別資訊和 (b) 服務所產生的記錄。

<span id="_Toc511384811" class="anchor"><span id="_Toc511163882" class="anchor"><span id="_Toc511136239" class="anchor"><span id="_Toc511125172" class="anchor"><span id="_Toc511120759" class="anchor"><span id="_Toc511122666" class="anchor"></span></span></span></span></span></span>
### <a name="service-specific-interfaces"></a>服務特定介面

Microsoft 提供直接透過既有的應用程式開發介面 (API) 或特定服務的使用者介面 (UI)，來探索客戶資料的能力。在上述服務各自的參考文件中有詳細資料，說明了適用的 CRUD (建立、讀取、更新、刪除) 作業。

<span id="_Sway" class="anchor"><span id="_Toc508792516" class="anchor"><span id="_Toc511122667" class="anchor"><span id="_Toc511120760" class="anchor"><span id="_Toc511125173" class="anchor"><span id="_Toc511136240" class="anchor"><span id="_Toc511163883" class="anchor"><span id="_Toc511384812" class="anchor"></span></span></span></span></span></span></span></span>
## <a name="step-3-rectify"></a>步驟 3：修正

若資料主體要求您修正貴組織資料中常駐的個人資料，您和貴組織需要判斷是否適合接受要求。修正資料可能包含採取下列動作，例如：從文件或其他類型的項目中，編輯、刪減或移除個人資料。修正 Microsoft 支援服務和 FastTrack 資料最方便的方式如下所示。

<span id="_Toc511384813" class="anchor"><span id="_Toc511163884" class="anchor"><span id="_Toc511136241" class="anchor"><span id="_Toc511125174" class="anchor"><span id="_Toc511120761" class="anchor"><span id="_Toc511122668" class="anchor"></span></span></span></span></span></span>
### <a name="azure-active-directory"></a>Azure Active Directory

根據特定的 Microsoft 服務，企業客戶可管理 DSR 修正要求，包括有限的編輯功能。身為資料處理者，Microsoft 不提供對系統所產生記錄檔的更正功能；因為這種記錄檔可反映出實際的活動，並構成 Microsoft 服務中所發生事件的歷史記錄。至於 Azure Active Directory，我們提供了有限的編輯功能，可讓您修正使用者的識別資訊，以下會進一步說明。

#### <a name="azure-active-directory-rectifycorrect-inaccurate-or-incomplete-personal-data"></a>Azure Active Directory：修正/更正不正確或不完整的個人資料

您可以使用 [Azure 入口網站](https://portal.azure.com/)來更正、更新或刪除使用者的識別資訊，例如客戶和員工的使用者設定檔及使用者工作資訊，其中包含在您 [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) 環境中的個人資料，例如使用者名稱、工作職稱、地址或電話號碼。您必須使用目錄的全域系統管理員帳戶來登入。

##### <a name="how-do-i-correct-or-update-user-profile-and-work-information-in-azure-active-directory"></a>如何更正或更新 Azure Active Directory 中的使用者設定檔及工作資訊？

1.  請用目錄的全域系統管理員帳戶來登入 [Azure 入口網站](https://portal.azure.com/)。

2.  請選取 [所有服務]****、在文字方塊中輸入 [使用者和群組]****，然後選取 [輸入]****。

    ![選取所有的服務](media/azure-dsr_image3.png)

3.  在 [使用者和群組]**** 刀鋒視窗上，選取 [使用者]****。
         
    ![選取使用者](media/azure-dsr_image9.png)

4.  請在 [使用者和群組 - 使用者]**** 刀鋒視窗中，從清單中選取使用者；然後在所選使用者的刀鋒視窗中，選取 [設定檔]**** 以檢視需要更正或更新的使用者設定檔資訊。

    ![選取設定檔](media/azure-dsr_image5.png)

5.  請更正或更新該資訊，然後在命令列中選取 [儲存]****。

6.  在所選使用者的刀鋒視窗中，選取 [工作資訊]**** 以檢視需要更正或更新的使用者工作資訊。

    ![選取工作的資訊](media/azure-dsr_image4.png)

7.  請更正或更新該使用者工作資訊，然後在命令列中選取 [儲存]****。

<span id="_Toc511384814" class="anchor"><span id="_Toc511163885" class="anchor"><span id="_Toc511136242" class="anchor"><span id="_Toc511125175" class="anchor"><span id="_Toc511120762" class="anchor"><span id="_Toc511122669" class="anchor"></span></span></span></span></span></span>
### <a name="service-specific-interfaces"></a>服務特定介面

Microsoft 提供直接透過既有的應用程式開發介面 (API) 或特定服務的使用者介面 (UI)，來探索客戶資料的能力。在上述服務各自的參考文件中有詳細資料，說明了適用的 CRUD (建立、讀取、更新、刪除) 作業。

<span id="_Gain_access_to" class="anchor"><span id="_Toc508792521" class="anchor"><span id="_Toc511122670" class="anchor"><span id="_Toc511120763" class="anchor"><span id="_Toc511125176" class="anchor"><span id="_Toc511136243" class="anchor"><span id="_Toc511163886" class="anchor"><span id="_Toc511384815" class="anchor"></span></span></span></span></span></span></span></span>
## <a name="step-4-restrict"></a>步驟 4：限制

<span id="_Delete" class="anchor"></span>資料主體可能會要求您限制對其個人資料的處理。我們提供了 Azure 入口網站，以及既有的應用程式開發介面 (API) 或使用者介面 (UI)。這些體驗讓企業客戶的租用戶系統管理員能透過資料匯出和資料刪除的組合，來管理這樣的 DSR。客戶可 (1) 匯出使用者個人資料的電子副本，包括 (a) 帳戶、(b) 系統所產生的記錄檔，和 (c) 相關的記錄檔；以及 (2) 刪除帳戶和 Microsoft 系統中常駐相關的資料。

<span id="_Toc508792528" class="anchor"><span id="_Toc511122671" class="anchor"><span id="_Toc511120764" class="anchor"><span id="_Toc511125177" class="anchor"><span id="_Toc511136244" class="anchor"><span id="_Toc511163887" class="anchor"><span id="_Toc511384816" class="anchor"></span></span></span></span></span></span></span>
## <a name="step-5-delete"></a>步驟 5：刪除

從組織的客戶資料中移除其個人資料的「抹除的權利」，是 GDPR 中的關鍵保護機制。這是指移除個人資料，包括移除稽核記錄資訊以外的所有個人資料和系統所產生的記錄檔。對使用者進行**虛刪除** (請參閱下方的詳細資料) 後，該帳戶會先停用 30 天。若在 30 天不採取任何進一步的動作，該使用者將會**永久刪除** (同樣請參閱下方的詳細資料)。從**永久刪除**時算起，使用者帳戶、個人資料和系統所產生的記錄檔會在 30 天內抹去。若租用戶系統管理員立即發出**永久刪除**的指令，使用者帳戶、個人資料和系統所產生的記錄檔，會在指令發出後 30 天內抹去。

>[重要事項] 您必須是租用戶系統管理員，才能從租用戶中刪除使用者。

<span id="_Toc511384817" class="anchor"><span id="_Toc511163888" class="anchor"><span id="_Toc511136245" class="anchor"><span id="_Toc511125178" class="anchor"><span id="_Toc511120765" class="anchor"><span id="_Toc511122672" class="anchor"><span id="_Ref511119801" class="anchor"></span></span></span></span></span></span></span>

### <a name="delete-a-user-and-associated-data-through-the-azure-portal"></a>透過 Azure 入口網站刪除使用者以及相關聯的資料

收到資料主體的刪除要求後，您可以使用 Azure 入口網站，同時刪除使用者和相關聯的個人資訊，以及系統所產生的記錄檔。

刪除這些資料也表示從租用戶中刪除使用者。最初會對使用者進行虛刪除，這表示租用戶系統管理員可以在標示為虛刪除後 30 天內復原該帳戶。30 天之後，帳戶就會自動且永久地從租用戶中刪除。在那 30 天之前，您可以從資源回收筒將遭到虛刪除的使用者手動刪除。

以下是從租用戶中刪除使用者的高層級程序。

1.  移至 Azure 入口網站並找出該使用者。

2.  刪除使用者。一開始刪除使用者時，該使用者的帳戶會傳送至資源回收筒。**此時，只是對使用者進行虛刪除，這表示該帳戶已停用，但是尚未從 Azure Active Directory 中抹去。**

3.  請移至最近刪除的使用者清單，並永久刪除該使用者。**此時使用者就會永久刪除 (也稱為實刪除)，這表示帳戶已從 Azure Active directory 中抹去**

##### <a name="to-delete-a-user-from-an-azure-tenant"></a>若要從 Azure 租用戶中刪除使用者

1.  請開啟 Azure 入口網站，選取 [Azure Active Directory]**** 刀鋒視窗，然後選取 [使用者]****。

    [使用者 - 所有使用者]**** 刀鋒視窗隨即出現。

    ![找出使用者](media/azure-dsr_image8.png)

2.  勾選想要刪除的使用者旁邊的核取方塊、選取 [刪除使用者]****，然後選取 [是]****。

    ![使用者管理](media/azure-dsr_image9.png)

3.  在 [顯示]**** 下拉式方塊中，選取 [最近刪除的使用者]****。

    ![檢視使用者設定檔](media/azure-dsr_image10.png)

4.  再次選取相同的使用者、選取 [永久刪除]****，然後在詢問您是否確定的方塊中選取 [是]****。

>[重要事項]  
>請注意，按一下 [是]**** 代表您會永久刪除使用者和所有相關的資料，以及系統所產生的記錄檔，而且無可挽回。若您不慎誤刪，就必須手動將使用者新增回租用戶中。相關聯的資料和系統所產生的記錄檔則無法復原。

   ![檢視使用者工作資訊](media/azure-dsr_image11.png)

<span id="_Export" class="anchor"><span id="_Step_6:_Export" class="anchor"><span id="_Toc511116629" class="anchor"><span id="_Toc511122673" class="anchor"><span id="_Toc511120766" class="anchor"><span id="_Toc511125179" class="anchor"><span id="_Toc511136246" class="anchor"><span id="_Toc511163889" class="anchor"><span id="_Toc508792534" class="anchor"></span></span></span></span></span></span></span></span></span>

### <a name="service-specific-interfaces"></a>服務特定介面

Microsoft 提供直接透過既有的應用程式開發介面 (API) 或特定服務的使用者介面 (UI)，來探索客戶資料的能力。在上述服務各自的參考文件中有詳細資料，說明了適用的 CRUD (建立、讀取、更新、刪除) 作業。

<span id="_Toc511384819" class="anchor"><span id="_Toc511163890" class="anchor"><span id="_Toc511136247" class="anchor"><span id="_Toc511125180" class="anchor"><span id="_Toc511120767" class="anchor"><span id="_Toc511122674" class="anchor"></span></span></span></span></span></span>
## <a name="step-6-export"></a>步驟 6：匯出

<span id="_Power_BI_2" class="anchor"></span>「資料可攜帶權」允許資料主體以 (「經過結構化、常用的、機器可讀取的、互通的」) 電子格式，要求其個人資料的副本，並可傳輸給其他資料控制者。Azure 可支援這點；我們讓貴組織能以原生 JSON 格式，將資料匯出到您指定的Azure 儲存體容器。

>[重要事項] 您必須是租用戶系統管理員，才能從租用戶中匯出使用者資料。

<span id="_Toc511384820" class="anchor"><span id="_Toc511163891" class="anchor"><span id="_Toc511136248" class="anchor"><span id="_Toc511125181" class="anchor"><span id="_Toc511120768" class="anchor"><span id="_Toc511122675" class="anchor"><span id="_Ref511119875" class="anchor"></span></span></span></span></span></span></span>
### <a name="azure-active-directory"></a>Azure Active Directory

至於客戶資料，Microsoft 提供了入口網站與產品內體驗，讓企業客戶的租用戶系統管理員能夠管理使用者識別資訊的匯出要求。

<span id="_Toc511384821" class="anchor"><span id="_Toc511163892" class="anchor"></span></span>
### <a name="service-specific-interfaces"></a>服務特定介面

Microsoft 提供直接透過既有的應用程式開發介面 (API) 或特定服務的使用者介面 (UI)，來探索客戶資料的能力。在上述服務各自的參考文件中有詳細資料，說明了適用的 CRUD (建立、讀取、更新、刪除) 作業。

<span id="_Toc511384822" class="anchor"><span id="_Toc511163893" class="anchor"><span id="_Toc511136250" class="anchor"><span id="_Toc511125183" class="anchor"><span id="_Toc511120770" class="anchor"><span id="_Toc511122677" class="anchor"></span></span></span></span></span></span>
## <a name="part-2-system-generated-logs"></a>第 2 部分：系統所產生的記錄檔


Microsoft 也讓您能夠存取、刪除及匯出特定與使用者的 Azure 使用方式相關聯、並由系統所產生的記錄檔。

>[!Important]
> 系統不支援限制或修正系統所產生記錄檔的能力。系統所產生的記錄檔構成了 Microsoft 雲端中所進行的實際動作和診斷資料，對這類資料的修改會危害動作的歷程記錄，並增加詐騙和安全性風險。

<span id="_Toc511384823" class="anchor"><span id="_Toc511163894" class="anchor"><span id="_Toc511136252" class="anchor"><span id="_Toc511125185" class="anchor"><span id="_Toc511120772" class="anchor"><span id="_Toc511122679" class="anchor"></span></span></span></span></span></span>
## <a name="executing-dsrs-against-system-generated-logs"></a>針對系統所產生的記錄檔執行 DSR

Microsoft 透過 Azure 入口網站，提供了存取、刪除及匯出特定由系統所產生記錄檔的功能；您也可直接透過特定服務的程式開發介面或使用者介面，來執行上述功能。在上述服務各自的參考文件中有詳細資料說明。

>[!Important]  
> 支援產品內 DSR 的服務需要直接使用服務的應用程式開發介面 (API) 或使用者介面 (UI)。因此，除了在 Azure 入口網站中執行 DSR 以外，**還必須另外在指定的服務中執行 DSR，才能完成指定資料主體的完整要求。請參閱特定服務的參考文件，以獲得進一步的詳細資料。**

<span id="_Toc511384824" class="anchor"><span id="_Toc511163895" class="anchor"><span id="_Toc511136253" class="anchor"><span id="_Toc511125186" class="anchor"><span id="_Toc511120773" class="anchor"><span id="_Toc511122680" class="anchor"><span id="_Ref511119063" class="anchor"><span id="_Toc508792552" class="anchor"><span id="_Toc509825622" class="anchor"></span></span></span></span></span></span></span></span></span>
## <a name="step-1-access"></a>步驟 1：存取 

貴組織內與特定使用者的 Azure 使用方式相關聯、並由系統所產生的記錄檔，只能由租用戶管理員存取。針對存取要求所擷取的資料會以機器可讀取的格式提供；且會以檔案的形式提供，讓使用者知道與資料相關聯的是哪些服務。如上所述，所擷取的資料不會包含可能造成服務安全性受損的資料。

<span id="_Toc511384825" class="anchor"><span id="_Toc511163896" class="anchor"><span id="_Toc511136254" class="anchor"><span id="_Toc511125187" class="anchor"><span id="_Toc511120774" class="anchor"><span id="_Toc511122681" class="anchor"><span id="_Toc511119129" class="anchor"></span></span></span></span></span></span></span>
### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft 提供入口網站與產品內體驗，讓企業客戶的租用戶系統管理員能夠管理 DSR 存取要求。存取要求可允許針對下列使用者個人資料進行存取，包括：(a) 使用者的識別資訊和 (b) 服務所產生的記錄。程序與「第 1 部分步驟 2：存取」中 Azure Active Directory 一節所述的相同。

<span id="_Toc511384826" class="anchor"><span id="_Toc511163897" class="anchor"><span id="_Toc511136255" class="anchor"><span id="_Toc511125188" class="anchor"><span id="_Toc511120775" class="anchor"><span id="_Toc511122682" class="anchor"><span id="_Toc511119130" class="anchor"></span></span></span></span></span></span></span>
### <a name="service-specific-interfaces"></a>服務特定介面

Microsoft 提供直接透過既有的應用程式開發介面 (API) 或特定服務的使用者介面 (UI)，來探索客戶資料的能力。在上述服務各自的參考文件中有詳細資料，說明了適用的 CRUD (建立、讀取、更新、刪除) 作業。

<span id="_Toc511384827" class="anchor"><span id="_Toc511163898" class="anchor"><span id="_Toc511136256" class="anchor"><span id="_Toc511125189" class="anchor"><span id="_Toc511120776" class="anchor"><span id="_Toc511122683" class="anchor"><span id="_Toc508792553" class="anchor"><span id="_Toc509825623" class="anchor"></span></span></span></span></span></span></span></span>
## <a name="step-2-delete"></a>步驟 2：刪除

租用戶管理員是貴組織內唯一可以針對 Azure 租用戶中特定使用者，執行 DSR 刪除要求的人員。

<span id="_Toc511384828" class="anchor"><span id="_Toc511163899" class="anchor"><span id="_Toc511136257" class="anchor"><span id="_Toc511125190" class="anchor"><span id="_Toc511120777" class="anchor"><span id="_Toc511122684" class="anchor"><span id="_Toc511119563" class="anchor"></span></span></span></span></span></span></span>
### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft 提供入口網站與產品內體驗，讓企業客戶的租用戶系統管理員能夠管理 DSR 刪除要求。DSR 刪除要求遵循與「第 1 部分步驟 5：刪除」中＜透過 Azure 入口網站刪除使用者帳戶及其相關的資料＞一節所述的相同步驟。

<span id="_Toc511384829" class="anchor"><span id="_Toc511163900" class="anchor"><span id="_Toc511136258" class="anchor"><span id="_Toc511125191" class="anchor"><span id="_Toc511120778" class="anchor"><span id="_Toc511122685" class="anchor"><span id="_Toc511119564" class="anchor"></span></span></span></span></span></span></span>
### <a name="service-specific-interfaces"></a>服務特定介面

Microsoft 提供直接透過既有的應用程式開發介面 (API) 或特定服務的使用者介面 (UI)，來探索客戶資料的能力。在上述服務各自的參考文件中有詳細資料，說明了適用的 CRUD (建立、讀取、更新、刪除) 作業。

<span id="_Toc511384830" class="anchor"><span id="_Toc511163901" class="anchor"><span id="_Toc511136259" class="anchor"><span id="_Toc511125192" class="anchor"><span id="_Toc511120779" class="anchor"><span id="_Toc511122686" class="anchor"><span id="_Toc508792554" class="anchor"><span id="_Toc509825624" class="anchor"></span></span></span></span></span></span></span></span>

## <a name="step-3-export"></a>步驟 3：匯出

貴組織內與特定使用者的 Azure 使用方式相關聯、並由系統所產生的記錄檔，只能由租用戶管理員存取。針對匯出要求所擷取的資料會以機器可讀取的格式提供；且會以檔案的形式提供，讓使用者知道與資料相關聯的是哪些服務。如上所述，所擷取的資料不會包含可能造成安全性或服務穩定性受損的資料。

<span id="_Toc511384831" class="anchor"><span id="_Toc511163902" class="anchor"></span></span>
### <a name="export-system-generated-logs-using-the-azure-portal"></a>使用 Azure 入口網站匯出系統所產生的記錄檔

您收到資料主體的匯出要求之後，可以使用 Azure 入口網站來匯出與特定使用者相關聯、由系統產生的記錄檔。

以下是從您的租用戶中匯出資料的高層級程序。

1.  移至 Azure 入口網站並代表使用者建立匯出要求。

2.  匯出資料，並將檔案傳送給使用者。

##### <a name="to-export-a-users-info-from-an-azure-tenant"></a>若要從 Azure 租用戶匯出使用者的資訊

1.  請開啟 Azure 入口網站，選取 [所有服務]****、在篩選中輸入 [原則]**，然後選取 [原則]****。

     ![所有服務篩選 ](media/azure-dsr_image12.png)

2.  請在 [原則]**** 刀鋒視窗上，依次選取 [使用者隱私權]****、[管理使用者要求]****、[新增匯出要求]****。

    ![新增匯出要求 ](media/azure-dsr_image13.png)

3.  完成**匯出資料要求**：

    ![新的匯出資料要求](media/azure-dsr_image14.png)

-   **使用者。** 請輸入要求匯出的 Azure Active Directory 使用者的電子郵件地址。

-   **訂用帳戶。** 請選取用於報告資源使用量和計算服務費用的帳戶。這也是您 Azure 儲存體帳戶的所在位置。

-   **儲存體帳戶。** 請選取您的 Azure 儲存體 (Blob) 所在的位置。如需詳細資訊，請參閱 [Microsoft Azure 儲存體 (Blob 儲存體) 簡介](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage)文件。

-   **容器。** 請建立新的 (或選取現有的) 容器，作為使用者所匯出隱私權資料的儲存位置。

4.  請選取 [建立]****。

匯出要求會進入**擱置**狀態。您可以在 [使用者隱私權 - 概觀]**** 刀鋒視窗上，檢視報告狀態。
>
>[重要事項]  
>因為個人資料可能來自多個系統，有可能匯出程序需要長達 1 個月才能完成。

<span id="_Toc511384832" class="anchor"><span id="_Toc511163903" class="anchor"></span></span>

### <a name="service-specific-interfaces"></a>服務特定介面

Microsoft 提供直接透過既有的應用程式開發介面 (API) 或特定服務的使用者介面 (UI)，來探索客戶資料的能力。在上述服務各自的參考文件中有詳細資料，說明了適用的 CRUD (建立、讀取、更新、刪除) 作業。

## <a name="notify-about-exporting-or-deleting-issues"></a>匯出或刪除問題的通知
如果您從 Azure 入口網站匯出或刪除資料時遇到問題，請前往 Azure 入口網站 [協助 + 支援]**** 刀鋒視窗，並在 [訂閱管理 > 其他安全性和法規遵循要求> 隱私權刀鋒視窗和 GDPR 要求]**** 下提交新票證。

#### <a name="learn-more"></a>深入了解
[Microsoft 信任中心](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)