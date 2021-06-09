---
title: 隱私權和個人資料
description: 詳述服務收集、儲存及使用的資料
keywords: GDPR，保留，刪除，儲存，保留，處理，安全性，審核
ms.service: m365-md
ms.sitesec: library
author: jaimeo
manager: laurawi
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
audience: Admin, ITPro
ms.localizationpriority: normal
ms.openlocfilehash: 3f1a251d98be5b3a9fefa5c1f6d5d5562516d5d5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908171"
---
# <a name="privacy-and-personal-data"></a>隱私權和個人資料

使用者可以在 Microsoft 受管理的電腦所管理的裝置上接收、傳送和儲存資料。 他們相信資料的隱私權受到保護，且只能以符合其預期的方式來使用。 本文說明 Microsoft 受管理的電腦如何收集、儲存、保留、處理、保護、共用、審核和匯出個人資料。 您也將瞭解系統管理員如何查看、更正和刪除個人資料。

Microsoft 受管理的電腦不會使用任何收集的個人資料，做為進行分析、廣告或行銷目的提供服務的一部分。

## <a name="data-collection-of-microsoft-managed-desktop"></a>Microsoft 受管理的電腦的資料集合

當使用者在 Microsoft 受管理的電腦中登記公司裝置時，會使用 Windows 和 Microsoft Intune 處理資料收集–在技術層級。 這些來源會收集使用者裝置的個人資料，例如 Microsoft 受管理的電腦的裝置名稱，以找出要管理及隨 Microsoft 受管理的電腦體驗提供的裝置。

Microsoft 受管理的電腦除了[IT 系統管理員連絡人資訊](#it-admin-contact-information)之外，不會自行收集資料，以提供其服務 (。 相反地，Microsoft 受管理的電腦重複使用已收集其他來源（例如 Windows 和 Microsoft Intune）的資料。 Microsoft 受管理的電腦會使用這些服務從已註冊的裝置收集的資料：

- 從 Microsoft 受管理的電腦所管理的裝置 Windows 診斷資料會傳送至 Microsoft 的 Windows 診斷資料儲存區。
- Microsoft 受管理的電腦會使用[現代管理](/learn/modules/introduction-to-modern-management-in-microsoft-365/)來管理已註冊的裝置。 在「新式管理」的一部分中，裝置必須在租使用者的 Azure Active Directory 中登記。
- 若要將其高度優化和安全的設定散佈至已註冊的裝置，Microsoft 受管理的電腦會使用 Microsoft Intune。
- Microsoft 受管理的電腦會使用 Microsoft Defender Advanced Thread Protection 的安全性智慧資料，以供使用該服務的客戶使用。

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>資料儲存區和 Microsoft 受管理的電腦中的資料來源

Microsoft 受管理的電腦取得資料後，必須提供其服務、儲存及處理該資料的處理過程如下：

### <a name="storing-data-storage-location-and-data-retention"></a>儲存資料、儲存位置及資料保留

Microsoft 受管理的電腦將其資料儲存在下列一或多個 Microsoft storage services 中：

- Azure SQL
- Azure 儲存體
- Dynamics 365

Microsoft 受管理的電腦會將其資料儲存在美國。 個人資料 Microsoft 受管理的電腦會保留最長30天，但不包括 Microsoft Defender for Endpoint 收集的 Microsoft 受管理的電腦裝置的警示資料。 實際的警示資料 (可以包含個人資料) 儲存180天。 已移除個人資料的警示資料會儲存多達兩年。 在遵守一般資料保護法規 (GDPR) 和加州消費者隱私權法案 (CCPA) ，Microsoft 受管理的電腦會為儲存在警示資料中的任何個人資料提供資料主體許可權。

### <a name="staff-location"></a>員工位置

Microsoft 受管理的電腦作業和安全性作業小組位於美國和印度。

## <a name="data-usage-of-microsoft-managed-desktop"></a>Microsoft 受管理的電腦的資料使用量

Microsoft 受管理的電腦使用此資料：


| 資料來源 |搭配 Microsoft 受管理的電腦使用  |
|---------|---------|
|Azure Active Directory 資料     | 用於租使用者系統管理員所建立的報表，可在 Microsoft 受管理的電腦管理入口網站中使用。        |
|Intune 資料     | 用於租使用者系統管理員所建立的報表，可在 Microsoft 受管理的電腦管理入口網站中使用。        |
|適用於端點的 Microsoft Defender     |  用於使用 Microsoft 受管理的電腦的安全性作業中心 (SOC) 中偵測到已註冊裝置上的安全性威脅。  |
|Windows 診斷資料     |用來判斷受管理裝置的更新狀態，以及提供並改善 Microsoft 受管理的電腦的 IT 即服務 (ITaaS) 服務。         |
|系統管理員連絡人資料     | 由 Microsoft 受管理的電腦用於與租使用者系統管理員通訊。        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Microsoft 受管理的電腦所處理的實體

Microsoft 受管理的電腦處理這些實體以提供服務：

- 裝置資料
- 裝置安全性設定
- 裝置作業系統和硬體
- 裝置健康情況的匯總資訊
- 裝置診斷資訊
- 租使用者資料
- Azure Active Directory 資源
- 原則和設定資料
- Microsoft Defender 用於端點中繼資料和警示資料
- Windows 診斷資料
- 產品和服務使用方式資料

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Microsoft 受管理的電腦所用的身分識別資料會根據組織在訂閱 Microsoft online 服務（如 Office 365 或 Azure）的位址，在地理位置 Azure Active Directory 儲存。 請參閱[Microsoft Azure —我的客戶資料在哪裡？](http://azuredatacentermap.azurewebsites.net/)用於顯示 Azure Active Directory 資料中心的地圖。

如需 Azure 用於資料存放區之地區的詳細資訊，請參閱[Azure Active Directory –您的資料所在位置](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)。

### <a name="microsoft-intune"></a>Microsoft Intune

Intune 資料可以儲存在一些不同的地區，例如歐洲北美 (愛爾蘭) 和歐洲西部 (荷蘭) 。 您的 IT 系統管理員會建立租使用者帳戶，並選擇當其初次登錄 Intune 服務時，將儲存資料的國家。 如需 Intune 使用的資料中心位置清單，請參閱[Microsoft Intune-我的客戶資料在哪裡？](http://intunedatacentermap.azurewebsites.net/)。 如需有關 Intune 之資料儲存區和使用的詳細資訊，請參閱 [Intune 中的資料收集](/intune/privacy-data-collect)。

### <a name="microsoft-defender-for-endpoint"></a>適用於端點的 Microsoft Defender

Microsoft Defender for Endpoint data 可以儲存在幾個不同的地區。 基於此原因，當[Microsoft defender for endpoint （資料儲存位置）](http://intunedatacentermap.azurewebsites.net/)時，會在歐洲同盟的 Microsoft Azure 資料中心中運作端點。 如需資料儲存區與 Defender for Endpoint 使用的詳細資訊，請參閱 [Microsoft Defender For endpoint 收集的資料為何？](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

如 [Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)中所述，「microsoft 收集的個人資料可能會在您的地區、美國，以及 microsoft 或其子公司、子公司或服務提供者運作設施的任何其他國家/地區儲存及處理。 [...]通常，主要儲存位置是在客戶的地區或美國，通常是另一個地區的資料中心備份。 會選擇儲存位置 (s) ，以高效運作，以提升效能，並建立冗余，以在發生中斷或其他問題時，保護資料。 我們採取下列步驟，以確保根據此陳述的條款和資料所在位置的法律需求，處理我們在此隱私權聲明下收集的資料。

如需 Windows 10 之診斷資料集合的詳細資訊，請參閱 Microsoft 隱私權聲明中的「[我們儲存及處理個人資料的地方](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule)」一節。

## <a name="data-access-protection"></a>資料存取保護

直接存取 Microsoft 受管理的電腦的內部資料儲存區的方式有幾種限制：

- 它需要工程組長層級核准。
- 它會進行審核，且時間有限。
- 它需要使用高度安全且受限制的工作站。
- 儲存時，會加密所有資料。
- 沒有進行中的存取。
- 存取 Microsoft 受管理的電腦的內部管理入口網站需要高安全性和限制的工作站。

## <a name="processing-personal-data-in-a-compliant-manner"></a>以相容的方式處理個人資料
Microsoft 受管理的電腦使用 ISO 驗證系統處理個人資料。 如需詳細資訊，請參閱 [規範](../intro/compliance.md)。

## <a name="profiling-and-marketing"></a>分析與行銷

Microsoft 受管理的電腦不會使用任何收集的個人資料，做為進行分析、廣告或行銷目的提供服務的一部分。

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 和 CCPA 的資料主體要求

[GDPR) 的歐盟一般資料保護法規 (](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) ，可將法規中 (已知之人員的權力視為資料主旨) ，以管理由雇主或其他類型的代理商或組織所收集的個人資料 (稱為資料控制者或僅限審計員) 。 依據 GDPR，個人資料的定義非常廣泛，舉凡與已識別或可識別自然人相關的任何資料皆屬之。 GDPR 為資料主體提供其個人資料的特定權限；這些權限包括取得個人資料副本、要求對該資料進行更正、限制對該資料的處理、刪除該資料，或是以電子格式接收該資料以移至另一個控制者。 由資料主體向控制者提出以對其個人資料採取行動的正式要求，稱為資料主體要求或 DSR。

同樣地，CCPA 為加州消費者提供隱私權權利和義務，包含與 GDPR 的資料主體許可權類似的許可權，例如刪除、存取和接收 (可攜性) 其個人資訊的許可權。 CCPA 也會提供某些披露的披露，針對其他分類為 "sales" 的資料傳輸，防範歧視時防範歧視和「自願退出/自願」的需求。 銷售的廣泛定義，包括出於有價值的考量而共用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](/compliance/regulatory/offering-ccpa?view=o365-worldwide)和[常見問題集](/compliance/regulatory/ccpa-faq?view=o365-worldwide)。

下一節將討論 Microsoft 受管理的電腦如何協助控制器尋找、存取及處理 Microsoft 受管理的電腦所使用的個人資料或個人資訊。

> [!NOTE]
> 如果您正在尋找 GDPR 的一般資訊，請參閱服務信任入口網站的 [GDPR 區段](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) 。

### <a name="it-admin-contact-information"></a>IT 系統管理員連絡人資訊

租使用者管理員可以查看、更正和刪除自己的個人資料 (例如自己的連絡人資訊) 直接在 Microsoft 受管理的電腦入口網站的 [系統管理連絡人] 區段中。

## <a name="microsoft-defender-for-endpoint-alert-data"></a>Microsoft Defender for Endpoint 警示資料

安全性管理員可以要求在其環境中的 Microsoft 受管理的電腦受管理裝置上，針對與 Microsoft Defender for Endpoint 警示相關的個人資料要求解壓縮或刪除。 安全性管理員應該登入 Microsoft 受管理的電腦[管理入口網站](https://aka.ms/memadmin)，並提交支援要求。 選取 [支援 **變更要求****類型**]、 **[** **安全性**] 及 [**其他**]**子** 類別，然後在描述中提供相關的裝置名稱，以及提取或刪除資料的要求。

### <a name="user-related-personal-data"></a>使用者相關個人資料

除此之外，Microsoft 受管理的電腦不會自行收集個人資料。 相反地，它會依賴和使用其他 Microsoft Enterprise 線上服務收集的個人資料。 IT 系統管理員希望回應他們的使用者要求以查看、更正和刪除其個人資料，可使用 Microsoft 受管理的電腦所依據之基礎服務的個別功能。 如果您有興趣查看或刪除這些服務所使用的個人資料，請先參閱 GDPR 文章的 [Azure 資料主體要求](/compliance/regulatory/gdpr-dsr-Azure) 。

此外，您可以使用下列指導方針來 dsr 服務 Microsoft 受管理的電腦取決於個人資料的集合：

- [Azure Active Directory](/compliance/regulatory/gdpr-dsr-Azure?view=o365-worldwide)
- [Microsoft Intune](/compliance/regulatory/gdpr-dsr-Intune?view=o365-worldwide)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](/windows/privacy/windows-10-and-privacy-compliance)