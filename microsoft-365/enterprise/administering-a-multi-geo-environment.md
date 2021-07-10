---
title: 管理多地理位置環境
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: 系統管理員可以瞭解如何在多地理位置環境中管理 SharePoint 和 OneDrive 服務。
ms.openlocfilehash: 4c5215b855b8ca1840035b39fcfbddde419c13d8
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362315"
---
# <a name="administering-a-multi-geo-environment"></a>管理多地理位置環境

查看 Microsoft 365 服務在多地理位置環境中的運作方式。

## <a name="administrator-experience"></a>管理員經驗

[SharePoint 系統管理中心](https://admin.microsoft.com/sharepoint)的左側導覽中有 [**地理位置**] 索引標籤，可讓您查看和管理您的地理位置。 使用此頁面來新增或刪除租使用者的地理位置。

## <a name="audit-log-search"></a>稽核記錄檔搜尋

可以從 Microsoft 365 稽核記錄搜索頁面取得所有衛星位置的統一[稽核記錄](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)。 您可以看到跨地理位置的所有稽核記錄項目，例如，北美洲與歐洲使用者的活動會在一個組織視圖中顯示，然後您可以套用現有的篩選器，以查看特定使用者的活動。

## <a name="bcs-secure-store-apps"></a>BCS、Secure Store、應用程式

BCS、Secure Store 及應用程式在每個衛星位置中都有個別的執行個體，因此 Sharepoint Online 系統管理員應該從每個衛星位置中個別管理及設定這些服務。

## <a name="compliance-admin-center"></a>合規性系統管理中心

有一個適用于多地理位置租使用者的中央合規性中心： [Microsoft 365 合規性系統管理中心](https://compliance.microsoft.com/)。

## <a name="ediscovery"></a>eDiscovery

根據預設，多地理位置租用戶的電子文件探索管理員或系統管理員只能在該租用戶的中央位置進行電子文件探索。 Office 365 全域系統管理員必須指派電子文件探索管理員權限，以允許其他人執行電子文件探索，並在其適用的合規性安全性篩選中指派「地區」參數，以將進行電子文件探索的區域指定為衛星位置，否則將不會為該衛星位置執行任何電子文件探索。 若要設定地區的法規遵循安全性篩選器，請參閱[設定 Office 365 多地理位置電子文件探索](multi-geo-ediscovery-configuration.md)。

## <a name="exchange-mailboxes"></a>Exchange 信箱

如果使用者的 PDL 變更，系統會自動移動使用者的 Exchange 信箱。 建立新的信箱時，如果使用者的 PDL 未設定任何值，信箱會佈建到使用者的 PDL 或中央位置。

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>資訊保護 (IP) 資料遺失防護 (DLP) 原則

您可以視整個租用戶或適用使用者的需求，在安全性和合規性中心為商務用 OneDrive、SharePoint 和 Exchange 設定 IP DLP 原則和範圍原則。 例如：如果您想為衛星位置的使用者選取原則，請選取將原則套用到特定 OneDrive 並輸入使用者的 OneDrive URL。 如需建立 DLP 原則的一般指導方針，請參閱[資料外洩防護原則概觀](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)。

系統會根據 DLP 原則對每個地理位置的適用性來自動同步處理這些原則。

對某個地理位置中的所有使用者執行資訊保護和資料外洩防護原則，不是 UI 中的可用選項，您反而必須選取該原則適用的帳戶，或將該原則全域套用至所有帳戶。

## <a name="microsoft-powerapps"></a>Microsoft PowerApps

為衛星位置建立的 PowerApps 將使用位於該租用戶中央位置的端點。 Microsoft PowerApps 不是多地理位置服務。 

## <a name="power-automate"></a>Power Automate

為衛星位置建立的流程將使用位於該租用戶預設地理位置的端點。  Power Automate 不是多地理位置服務。 

## <a name="sharepoint-storage-quota"></a>SharePoint 儲存空間配額

根據預設，多重地理環境的所有地理位置會共用可用的租用戶儲存空間配額。  您也可以為特定的地理位置分配特定配額，以管理儲存空間配額。 如需詳細資訊，請參閱[多地理位置環境中的 SharePoint 儲存空間配額](sharepoint-multi-geo-storage-quota.md)。

## <a name="sharing"></a>共用

系統管理員可以設定並管理每個位置的共用原則。 每個地理位置中的 OneDrive 和 SharePoint 網站只會遵守對應的地理位置特定的共用設定。 (例如，您可以允許在中央位置[外部共用](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85)，但不能在衛星位置外部共用，反之亦然。) 請注意，共用設定不允許在地理位置之間設定共用限制。

## <a name="stream"></a>Stream

上傳至資料流程的影片會儲存在上載人員的 OneDrive。 會議錄製會儲存在每個記錄會議的出席者的 OneDrive 中。

## <a name="taxonomy"></a>分類

我們使用您公司中央位置主控的主機，針對不同地理位置的企業管理中繼資料，支援統一的[分類法](/sharepoint/managed-metadata)。 我們建議您從中央位置管理全域分類法，並只將特定位置的詞彙增到衛星位置的分類法。 全域分類法詞彙將同步到衛星位置。

如需詳細資訊與開發人員指導方針，請參閱[管理多地理位置租用戶中的中繼資料](/sharepoint/dev/solution-guidance/multigeo-managedmetadata)。

## <a name="user-profile-application"></a>使用者設定檔應用程式

每個地理位置都有一個[使用者設定檔應用程式](/sharepoint/manage-user-profiles)。 系統會在每位使用者的地理位置主控其設定檔資訊，且該設定檔資料可供該地理位置的系統管理員使用。

如果您有自訂的設定檔屬性，則建議您使用跨地理位置的相同設定檔結構描述，然後在所有的地理位置或所需的位置填入自訂設定檔屬性。 如需如何以程式設計方式填入使用者設定檔資料的指導方針，請參閱[大量使用者設定檔更新 API](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online)。

如需詳細資訊與開發人員指導方針，請參閱[在多地理位置租用戶中使用使用者設定檔](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience)。

## <a name="yammer"></a>Yammer

Yammer 不是多地理位置工作負載。 儲存在 Yammer 中的 Yammer 執行緒都會放置在租使用者的中央位置。 Yammer 正在推出會將 Yammer 檔案儲存在 SharePoint 中的檔案儲存變更。 儲存在 SharePoint 中的 Yammer 檔案將會放入與 Yammer 群組相關聯的 SharePoint 網站。 SharePoint 群組網站是以 PDL 邏輯為基礎，如[SharePoint 網站和群組](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups)中所述。