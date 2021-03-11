---
title: 規劃 Microsoft 365 多地理位置
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
description: 了解什麼是 Microsoft 365 多地理位置、多地理位置的運作方式，以及哪些地理位置可用於儲存資料。
ms.openlocfilehash: ce8b752cc6a335249f9d8e03289fd16b04756ce9
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712339"
---
# <a name="plan-for-microsoft-365-multi-geo"></a>規劃 Microsoft 365 多地理位置

本指南是為多國公司 (MNC) 的系統管理員而設計，這些管理員會根據公司的目前位置將 Microsoft 365 租用戶擴充至其他地理位置，以符合資料落地要求。

在多地理位置組態中，Microsoft 365 租用戶由一個中央位置和一或多個衛星位置所組成。 這個單一租用戶跨越多個地理位置。 您的租用戶資訊，包括由 Azure Active Directory (Azure AD) 管理的地理位置。

以下是一些重要的多地理位置詞彙，可協助您了解設定的基本概念：

-   **租用戶** – 組織在 Microsoft 365 中的呈現方式，通常會有與其相關聯的一個或多個網域 (例如 https://contoso.sharepoint.com))。 

-   **地理位置** – 可用來裝載 Microsoft 365 租用戶中資料的地理位置。

-   **衛星位置**：您在 Microsoft 365 租用戶中設定來裝載資料的其他地理位置。 多地理位置租用戶橫跨多個地理位置，例如，北美洲和歐洲。

-   **慣用的資料位置 (PDL)** -個別使用者儲存 Exchange 和 OneDrive 資料的地理位置。 系統管理員可將此位置設定為已為租用戶設定的任何地理位置。 請注意，如果您變更已經擁有 OneDrive 網站的使用者的 PDL，他們的 OneDrive 資料將不會自動移動到新的地理位置。 如需詳細資訊，請參閱[將 OneDrive 文件庫移至不同的地理位置](move-onedrive-between-geo-locations.md)。 如果他們有 Exchange 信箱，則信箱會自動移至新的慣用資料位置。

啟用多地理位置需要四個關鍵步驟：

1.  與您的帳戶團隊合作來新增「Microsoft 365 多地理位置功能」服務方案。

2.  選擇您想要的衛星位置，並將其新增至您的租用戶。

3.  將使用者的慣用資料位置設定為想要的衛星位置。 為使用者佈建新 OneDrive 網站或 Exchange 信箱時，該網站或信箱會佈建到使用者的 PDL。

4.  請視需要將使用者現有 OneDrive 網站從中央位置移轉至其慣用的資料位置。 (當您設定使用者的 PDL 時，系統會自動移轉 Exchange 信箱。)

如需各步驟的詳細資料，請參閱[設定 Microsoft 365 多地理位置](multi-geo-tenant-configuration.md)。

> [!IMPORTANT]
> 請注意，Microsoft 365 多地理位置不是為效能最佳化優化而設計，其主要設計目的在滿足資料落地要求。 如需 Microsoft 365 效能最佳化的詳細資訊，請參閱 [Microsoft 365 的網路規劃與效能調整](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848)或連絡客戶支援小組。

您可以將下列位置設定為衛星位置，以便在其上裝載 OneDrive 和 SharePoint 網站，及 Exchange 信箱。 當您規劃多地理位置時，請列出您要新增至 Microsoft 365 租用戶的位置清單。 我們建議從一或兩個衛星位置開始，然後再視需要逐步擴充至更多地理位置。

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

設定多地理位置時，請考慮在移轉到 Microsoft 365 時合併內部部署基礎結構的可能性。比方說，如果您在新加坡和馬來西亞有內部部署伺服器陣列，然後您可以將他們合併至 APC 衛星位置中，提供的資料常駐要求可讓您執行此動作。

## <a name="best-practices"></a>最佳做法

我們建議您在 Microsoft 365 中建立測試使用者，以進行一些初步測試。 在您將生產使用者上架到 Microsoft 365 多地理位置之前，我們將與該使用者一起完成一些測試和驗證步驟。

與測試使用者一起完成測試後，請選取一個試驗組 (可以是您的 IT 部門的人員)，成為第一批在新地理位置使用 OneDrive 和 Exchange 的人。 在第一批人員當中，選取還沒有 OneDrive 的使用者。 我們建議這個試驗組不要超過五個人，之後再透過批次推出方法來逐步擴展。

每個使用者應具備 *慣用的資料位置*(PDL) 設定，以便 Microsoft 365 判斷佈建其 OneDrive 的地理位置。使用者慣用的資料位置必須與您所選的某個衛星位置或您的中心位置相符。當 PDL 不是強制性欄位時，我們建議為所有使用者設定 PDL。沒有 PDL 的使用者工作負載會佈建在中心位置。

建立使用者清單，並包含使用者主體名稱 (UPN) 與適當慣用資料位置的位置代碼。包含測試使用者與您起始的試驗群組來開始進行。您將需要此清單來設定程序。

如果您的使用者是從內部部署 Active Directory 系統同步到 Azure Active Directory，您必須將慣用資料位置設定為 Active Directory 屬性，並使用 Azure Active Directory Connect 進行同步。 您無法使用 Azure AD PowerShell為同步使用者直接設定慣用資料位置。 在 Active Directory 中設定 PDL 並對其進行同步的步驟會於 [Azure Active Directory Connect 同步：為 Microsoft 365 資源設定慣用資料位置](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)中說明。

多地理位置租用戶的管理可能與非多地理位置租用戶不同，因為許多 SharePoint 和 OneDrive 設定與服務具有多地理位置意識。我們建議您檢閱[管理多地理位置環境](administering-a-multi-geo-environment.md)，再繼續進行您的組態。

在 [多地理位置環境中讀取使用者的經驗](multi-geo-user-experience.md) ，以取得使用者在多地理位置環境中的體驗的詳細資料。

如需有關 Microsoft 365 多地理位置租用中 Teams 體驗的詳細資訊，請參閱[在 Microsoft 365 OneDrive 和 SharePoint Online 多地理位置租用中的 Teams 體驗](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo) (部分機器翻譯)。

若要開始設定 Microsoft 365 多地理位置，請參閱[設定 Microsoft 365 多地理位置](multi-geo-tenant-configuration.md)。

當您完成設定時，請記得視需要[移轉使用者的 OneDrive 文件庫](move-onedrive-between-geo-locations.md)，讓使用者在自己慣用的資料位置工作。

## <a name="related-topics"></a>相關主題

[Microsoft 365 多地理位置電子文件探索設定](https://docs.microsoft.com/microsoft-365/enterprise/multi-geo-ediscovery-configuration)
