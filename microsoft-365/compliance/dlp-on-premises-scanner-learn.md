---
title: 深入了解 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 資料外洩防護內部部署掃描器可將檔案活動的監視以及這些檔案的保護動作延伸到內部部署檔案共用、SharePoint 資料夾和文件庫。 檔案會由 Azure 資訊保護 (AIP) 掃描器掃描並保護
ms.openlocfilehash: fa1c14520c8ad0afa4856fdd8a1c59a0f71f400d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917809"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>深入了解 Microsoft 365 資料外洩防護內部部署掃描器 (預覽)

Microsoft 資料外洩防護內部部署掃描器是 Microsoft 365 資料外洩防護 (DLP) 套件的一部分，您可以使用這些功能探索並保護整個 Microsoft 365 服務的敏感性項目。 如需所有 Microsoft DLP 供應項目的詳細資訊，請參閱 [資料外洩防護概觀](data-loss-prevention-policies.md)。

**DLP 內部部署掃描器** 會耙梳檔案共用和 SharePoint 文件庫及資料夾中的內部部署待用資料，並尋找敏感性項目，而這類項目如果外泄會對組織造成風險或造成合規性政策違規的風險。 這可提供您所需的可見度和控制，以確保敏感性項目得到正確的使用與保護，並協助防治可能導致威脅入侵的風險行為。 DLP 內部部署掃描器會使用 [內建](sensitive-information-type-entity-definitions.md) 或 [自訂敏感性資訊](create-a-custom-sensitive-information-type.md) 類型、 [敏感度標籤](sensitivity-labels.md) 或檔案屬性來偵測敏感性資訊。 您可以在 [活動總管](data-classification-activity-explorer.md) 中查看使用者使用敏感度專案的相關資訊，而且您可以透過 [DLP 原則](create-test-tune-dlp-policy.md)強制執行這些專案上的保護動作。

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a>DLP 內部部署掃描器依賴 Azure 資訊保護掃描器

DLP 內部部署掃描器依賴 Azure 資訊保護 (AIP) 掃描器的完整執行來監視、標記和保護敏感性項目。 如果您不熟悉 AIP 掃描器，強烈建議您加以熟悉。 請參閱這些文章：

- [什麼是 Azure 資訊保護？](/azure/information-protection/what-is-information-protection)
- [什麼是 Azure 資訊保護統一標籤掃描器](/azure/information-protection/deploy-aip-scanner)
- [安裝和部署 Azure 資訊保護統一標籤掃描器的需求](/azure/information-protection/deploy-aip-scanner-prereqs)
- [教學課程：安裝 Azure 資訊保護 (AIP) 統一標籤掃描器](/azure/information-protection/tutorial-install-scanner)
- [設定和安裝 Azure 資訊保護統一標籤掃描器](/azure/information-protection/deploy-aip-scanner-configure-install)
- [Azure 資訊保護統一標籤用戶端-版本發行歷程記錄及支援原則](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a>DLP 內部部署掃描器動作

DLP 內部部署掃描器會利用以下四種方法的其中一項來偵測檔案：

- 敏感性資訊類型
- 敏感度標籤
- 檔案副檔名
- 僅 Office 檔案上的自訂文件屬性 

當偵測到的檔案在外泄時具有潛在風險，或違反合規性政策時，DLP 內部部署掃描器可以採取這四個動作中的其中一個動作。

|動作 |描述  |
|---------|---------|
|**禁止這些人存取儲存在內部部署掃描器中的檔案 - 所有人** | 強制執行時，此動作會禁止所有帳戶的存取權限，唯有內容擁有者、最後一個修改專案的帳戶，以及系統管理員除外。 它會在檔案層級自 NTFS/SharePoint 權限移除所有帳戶，但檔案擁有者、存放庫擁有者 (在內容掃描工作中的 [設定存放庫擁有者](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) 設定中所設）、最後修改者 (只能在 SharePoint 中識別) 和系統管理員除外。掃描器帳戶也會獲得檔案的 FC 權限。|
|**封鎖這些人員，使其無法存取儲存在內部部署掃描器中的檔案 - 封鎖全組織 (公用) 存取**    |強制執行時，此動作會從檔案存取控制清單 (ACL) 移除 **_所有人_*_、_*_NT AUTHORITY\已驗證的使用者_*_和 _*_網域使用者_** SID。 只有明確獲得檔案或父資料夾權限的使用者和群組才能存取檔案。|
|**設定檔案的權限**|強制執行時，此動作會強制檔案繼承其父資料夾的權限。 根據預設，只有在父資料夾的權限比檔案上已有的權限限制更嚴格時，才能強制執行此動作。 例如，如果檔案上的 ACL 設定為只允許 **_特定使用者_*_，且父資料夾設定為允許 _*_網域使用者_*_ 群組，則檔案不會繼承父資料夾權限。您可以選取 _* 即使父項權限較不嚴格也繼承** 選項來覆寫此行為。|
|**從不當位置移除檔案**|強制執行時，此動作會以 .txt 副檔名取代原始檔案，並且將原始檔案的一份副本位於隔離資料夾中。 

## <a name="whats-different-in-the-on-premises-scanner"></a>內部部署掃描器的不同處

在您深入了解內部部署掃描器之前，您必須先注意一些額外的概念。

### <a name="aip-repositories-and-content-scan-jobs"></a>AIP 存放庫和內容掃描工作

您必須建立 AIP 內容掃描工作，並識別出裝載著您希望 DLP 引擎評估之檔案的存放庫。 請確定在已建立之 AIP 內容掃描工作中啟用 DLP 規則。

### <a name="policy-tips"></a>原則提示

內部掃描器中未提供 [原則提示](use-notifications-and-policy-tips.md)。


### <a name="viewing-dlp-on-premises-scanner-events"></a>檢視 DLP 內部部署掃描器事件

您可以在 M365 合規性中心或 [活動總管](data-classification-activity-explorer.md) 中查看 DLP 內部部署掃描器。 

## <a name="next-steps"></a>後續步驟

現在您已了解 DLP 內部部署掃描器，接下來的步驟如下：

1. [開始使用 DLP 內部部署掃描器](dlp-on-premises-scanner-get-started.md)
2. [使用 DLP 內部部署掃描器](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>另請參閱

- [開始使用 Microsoft 資料外洩防護內部部署掃描器](dlp-on-premises-scanner-get-started.md)
- [使用 Microsoft 資料外洩防護內部部署掃描器](dlp-on-premises-scanner-use.md)
- [資料外洩防護概觀](data-loss-prevention-policies.md)
- [建立、測試及調整 DLP 原則](create-test-tune-dlp-policy.md)
- [開始使用活動總管](data-classification-activity-explorer.md)