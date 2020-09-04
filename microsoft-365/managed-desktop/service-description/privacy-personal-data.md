---
title: 隱私權和個人資料
description: 詳述服務收集、儲存及使用的資料
keywords: GDPR，保留，刪除，儲存，保留，處理，安全性，審核
ms.prod: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: e1b0c856a3bfb886521ee2c1a2115e4c29504862
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47363252"
---
# <a name="privacy-and-personal-data"></a>隱私權和個人資料

使用者可以在 Microsoft 受管理的電腦所管理的裝置上接收、傳送和儲存資料。 他們相信資料的隱私權受到保護，且只能以符合其預期的方式來使用。 本文說明 Microsoft Managed Desktop 如何收集、儲存、保留、處理、保護、共用、審核和匯出個人資料。 您也將瞭解系統管理員如何查看、更正和刪除個人資料。

Microsoft 受管理的桌面不會使用任何收集的個人資料，做為進行分析、廣告或行銷目的提供服務的一部分。

## <a name="data-collection-of-microsoft-managed-desktop"></a>Microsoft 受管理桌面的資料收集

當使用者在 Microsoft 受管理的桌面中登記公司裝置時，會使用 Windows 和 Microsoft Intune 處理資料收集–在技術層級。 這些來源會收集使用者裝置的個人資料，例如 Microsoft 受管理桌面的裝置名稱，以識別要管理的裝置，並與 Microsoft 受管理的桌面體驗一起提供。

Microsoft 受管理的桌面不會自行收集資料，以提供其服務 (，但 [IT 系統管理員連絡人資訊](#it-admin-contact-information)除外。 相反地，Microsoft 受管理的桌面會重複使用其他來源（如 Windows 和 Microsoft Intune）已收集的資料。 Microsoft 受管理的桌面使用這些服務從已註冊的裝置收集的資料：

- Microsoft 受管理的桌面所管理之裝置的 Windows 診斷資料會傳送至 Microsoft 的 Windows 診斷資料儲存區。
- Microsoft 受管理的桌上型電腦使用 [現代管理](https://docs.microsoft.com/learn/modules/introduction-to-modern-management-in-microsoft-365/) 來管理已註冊的裝置。 在此情況下，裝置必須在租使用者的 Azure Active Directory 中註冊。
- 若要將其高度優化和安全的設定散佈至註冊的裝置，Microsoft 受管理的桌面會使用 Microsoft Intune。
- Microsoft 受管理的桌面對使用該服務的客戶，使用 Microsoft Defender Advanced Thread Protection 中的安全性智慧資料。

## <a name="data-storage-and-sources-in-microsoft-managed-desktop"></a>Microsoft 受管理電腦中的資料儲存區和來源

Microsoft 受管理的桌面取得資料後，必須提供其服務、儲存及處理該資料，如下所示：

### <a name="storing-data-storage-location-and-data-retention"></a>儲存資料、儲存位置及資料保留

Microsoft Managed Desktop 會將其資料儲存在下列一或多個 Microsoft storage services 中：

- Azure SQL
- Azure 儲存體

Microsoft 受管理的桌面會將其資料儲存在美國。 Microsoft 受管理的桌面會保留最多30天的個人資料。

## <a name="data-usage-of-microsoft-managed-desktop"></a>Microsoft 受管理電腦的資料使用量

Microsoft 受管理的桌面會使用下列資料：


| 資料來源 |與 Microsoft 受管理的電腦搭配使用  |
|---------|---------|
|Azure Active Directory 資料     | 用於租使用者系統管理員所建立的報表，可在 Microsoft Managed Desktop Admin 入口網站中使用。        |
|Intune 資料     | 用於租使用者系統管理員所建立的報表，可在 Microsoft Managed Desktop Admin 入口網站中使用。        |
|Microsoft Defender 進階威脅防護 (ATP)     |  用於解決 Microsoft Managed Desktop 的安全性作業中心在已註冊裝置上偵測到的安全性威脅 (SOC) 。  |
|Windows 診斷資料     |用來判斷受管理裝置的更新狀態，以及提供並改善 Microsoft 受管理的電腦即服務 (ITaaS) 產品。         |
|系統管理員連絡人資料     | 由 Microsoft Managed Desktop 用來與租使用者系統管理員通訊。        |


### <a name="entities-processed-by-microsoft-managed-desktop"></a>Microsoft 受管理的桌面所處理的實體

Microsoft 受管理的桌面處理這些實體以提供服務：

- 裝置資料
- 裝置安全性設定
- 裝置作業系統和硬體
- 裝置健康情況的匯總資訊
- 裝置診斷資訊
- 租使用者資料
- Azure Active Directory 資源
- 原則和設定資料
- Microsoft Defender ATP 中繼資料
- Windows 診斷資料
- 產品和服務使用方式資料

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Microsoft 受管理的桌面所用的身分識別資料，會根據組織在訂閱 Microsoft online 服務（例如 Office 365 或 Azure）時所提供的位址，在地理位置儲存。 請參閱 [Microsoft Azure （「我的客戶資料」的位置）](http://azuredatacentermap.azurewebsites.net/) ，以取得顯示 Azure Active Directory 資料中心的地圖。

如需 Azure 用於資料存放區之地區的詳細資訊，請參閱 [Azure Active Directory –您的資料所在位置](https://msit.powerbi.com/view?r=eyJrIjoiODdjOWViZDctMWRhZS00ODUzLWI4MmQtNWM5NjBkZTBkNjFlIiwidCI6IjcyZjk4OGJmLTg2ZjEtNDFhZi05MWFiLTJkN2NkMDExZGI0NyIsImMiOjV9)。

### <a name="microsoft-intune"></a>Microsoft Intune

Intune 資料可以儲存在一些不同的地區，例如歐洲北美 (愛爾蘭) 和歐洲西部 (荷蘭) 。 您的 IT 系統管理員會建立租使用者帳戶，並選擇當其初次登錄 Intune 服務時，將儲存資料的國家。 如需 Intune 使用的資料中心位置清單，請參閱 [Microsoft Intune-我的客戶資料在哪裡？](http://intunedatacentermap.azurewebsites.net/)。 如需有關 Intune 之資料儲存區和使用的詳細資訊，請參閱 [Intune 中的資料收集](https://docs.microsoft.com/intune/privacy-data-collect)。

### <a name="microsoft-defender-advanced-threat-protection"></a>Microsoft Defender 進階威脅防護

Microsoft Defender Advanced 威脅防護 (ATP) 資料可以儲存在數種不同的地區。 因此，Microsoft Azure 資料中心在歐洲同盟、英國和美國（如 [Microsoft DEFENDER atp）的資料儲存位置](http://intunedatacentermap.azurewebsites.net/)中所述，都是以 microsoft Azure 資料中心的方式運作。 如需 Microsoft Defender ATP 資料儲存區和使用的詳細資訊，請參閱 [Microsoft DEFENDER atp 收集的資料為何？](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy#what-data-does-microsoft-defender-atp-collect)

### <a name="windows-10"></a>Windows 10

如 [Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)中所述，「microsoft 收集的個人資料可能會在您的地區、美國，以及 microsoft 或其子公司、子公司或服務提供者運作設施的任何其他國家/地區儲存及處理。 [...]通常，主要儲存位置是在客戶的地區或美國，通常是另一個地區的資料中心備份。 會選擇儲存位置 (s) ，以高效運作，以提升效能，並建立冗余，以在發生中斷或其他問題時，保護資料。 我們採取下列步驟，以確保根據此陳述的條款和資料所在位置的法律需求，處理我們在此隱私權聲明下收集的資料。

如需有關 Windows 10 之診斷資料集合的詳細資訊，請參閱 Microsoft 隱私權聲明中的「 [我們儲存及處理個人資料的地方](https://privacy.microsoft.com/privacystatement#mainwherewestoreandprocessdatamodule) 」一節。

## <a name="data-access-protection"></a>資料存取保護

以下列幾種方式限制直接存取 Microsoft 受管理桌面的內部資料存放區：

- 它需要工程組長層級核准。
- 它會進行審核，且時間有限。
- 它需要使用高度安全且受限制的工作站。
- 儲存時，會加密所有資料。
- 沒有進行中的存取。
- 存取 Microsoft 受管理電腦的內部管理入口網站需要高安全性和限制的工作站。

## <a name="processing-personal-data-in-a-compliant-manner"></a>以相容的方式處理個人資料
Microsoft 受管理的電腦使用 ISO 驗證的系統處理個人資料。 如需詳細資訊，請參閱 [規範](../intro/compliance.md)。

## <a name="profiling-and-marketing"></a>分析與行銷

Microsoft 受管理的桌面不會使用任何收集的個人資料，做為進行分析、廣告或行銷目的提供服務的一部分。

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR 和 CCPA 的資料主體要求

[GDPR) 的歐盟一般資料保護法規 (](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) ，可將法規中 (已知之人員的權力視為資料主旨) ，以管理由雇主或其他類型的代理商或組織所收集的個人資料 (稱為資料控制者或僅限審計員) 。 依據 GDPR，個人資料的定義非常廣泛，舉凡與已識別或可識別自然人相關的任何資料皆屬之。 GDPR 為資料主體提供其個人資料的特定權限；這些權限包括取得個人資料副本、要求對該資料進行更正、限制對該資料的處理、刪除該資料，或是以電子格式接收該資料以移至另一個控制者。 由資料主體向控制者提出以對其個人資料採取行動的正式要求，稱為資料主體要求或 DSR。

同樣地，加州消費者隱私權法案 (CCPA) 會為加州消費者提供隱私權權利和義務，包含與 GDPR 的資料主體許可權類似的許可權，例如刪除、存取和接收 (可攜性) 其個人資訊的權利。 CCPA 也會提供某些披露的披露，針對其他分類為 "sales" 的資料傳輸，防範歧視時防範歧視和「自願退出/自願」的需求。 銷售的廣泛定義，包括出於有價值的考量而共用資料。 如需 CCPA 的詳細資訊，請參閱[加州消費者隱私法](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa?view=o365-worldwide)和[常見問題集](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq?view=o365-worldwide)。

下一節將討論 Microsoft Managed Desktop 如何協助控制器尋找、存取及處理 Microsoft 受管理的桌面所使用的個人資料或個人資訊。

> [!NOTE]
> 如果您正在尋找 GDPR 的一般資訊，請參閱服務信任入口網站的 [GDPR 區段](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) 。

### <a name="it-admin-contact-information"></a>IT 系統管理員連絡人資訊

租使用者管理員可以直接在 Microsoft 受管理的桌面入口網站的 [系統管理員連絡人] 區段中查看、更正和刪除個人資料。

### <a name="user-related-personal-data"></a>使用者相關個人資料

除此之外，Microsoft 受管理的電腦不會自行收集個人資料。 相反地，它會依賴和使用其他 Microsoft 企業版線上服務收集的個人資料。 IT 系統管理員希望回應他們的使用者要求以查看、更正和刪除其個人資料，可使用 Microsoft 受管理桌面所依賴之基礎服務的個別功能。 如果您有興趣查看或刪除這些服務所使用的個人資料，請先參閱 GDPR 文章的 [Azure 資料主體要求](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure) 。

此外，使用下列指導方針來執行 Microsoft 受管理桌面服務的 Dsr，取決於個人資料的集合：

- [Azure Active Directory](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-intune?view=o365-worldwide)
- [Microsoft Defender ATP](https:/docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- [Windows 10](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
