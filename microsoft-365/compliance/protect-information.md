---
title: 保護資訊
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/26/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: 此登陸頁面提供在 Microsoft 365 和 Office 365 中保護資訊的連結和相關資訊。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3657fc674547013c8517b6121d6b2bbb636b7481
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127490"
---
# <a name="protect-information"></a>保護資訊

Microsoft 365 和 Office 365 包含可以套用至特定資料類型以保護資訊的功能。


|**功能**|**詳細資訊**|
|:-----|:-----|
|[敏感性標籤](sensitivity-labels.md) <br/> |使用靈敏度標籤，您可以分類及保護您的敏感內容。 保護選項包括標籤、浮水印和加密。 敏感度標籤使用 Azure 資訊保護。 如果您使用的是 Azure 資訊保護標籤，現在建議您避免在完成遷移之後，在其他系統管理中心中建立新標籤。 請參閱[Azure 資訊保護遷移](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)。 <br/> 請注意，[保留標籤](retention.md#retention-labels)不同于敏感度標籤。 保留標籤可協助您保留或刪除以您定義之原則為基礎的內容。 這些協助組織遵循業界法規和內部原則。|
|[資料遺失防護](data-loss-prevention-policies.md)（DLP）  <br/> |使用 DLP 原則，您可以識別、監視和自動保護 Office 365 中的機密資訊。 資料遺失防護原則可以使用敏感度標籤和敏感資訊類型來識別敏感資訊。 <br/> |
|[敏感資訊類型實體定義](sensitive-information-type-entity-definitions.md) <br/> |Microsoft 365 包含許多機密資訊類型，可供您用於 DLP 原則，以及使用敏感度和保留標籤進行自動分類。 機密資訊類型也可以搭配[Azure 資訊保護掃描器](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)使用，以在內部部署上分類及保護檔案。 敏感資訊類型定義自動化程式如何識別特定的資訊類型，例如健康情況服務號碼和信用卡號碼。   <br/> |
|[Office 365 郵件加密](ome.md)（OME）  <br/> |透過 Office 365 郵件加密，您的組織可以在組織內部和外部的人員之間傳送和接收加密的電子郵件。 Office 365 郵件加密可與 Outlook.com、Yahoo！、Gmail 及其他電子郵件服務搭配使用。 電子郵件加密可協助確保只有預定的收件者可以查看郵件內容。 <br/> |
|[Azure 資訊保護](https://docs.microsoft.com/azure/information-protection/)<br/> |Azure 資訊保護（有時稱為 AIP）可協助組織分類、標籤，並選擇性地保護檔和電子郵件。 管理員可以透過定義規則和條件來自動套用標籤。 使用者可以將標籤手動套用至檔案和郵件。 您也可以為使用者提供有關何時套用標籤的建議。<br/> 如果您使用的是敏感度標籤或 Office 郵件加密，您已在使用分類及保護功能。 如果您尚未將 Azure 資訊保護標籤遷移至 Office 365，請繼續在 Azure 資訊保護中進行管理。  <br/>您可以在內部部署執行[Azure 資訊保護掃描器](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)，以分類及保護 Windows Server、網路共用和 SharePoint 伺服器網站及文件庫上的檔案。 這可能是識別要遷移至 Office 365 之資料的第一步。
|使用客戶管理加密金鑰的 Azure 資訊保護 <br/> |有些組織必須具備業務需求或法規遵從性需求，才能保留加密金鑰的控制權。 這並不常見。 Azure 資訊保護可讓組織將您自己的金鑰（BYOK）移至服務。 如需詳細資訊，請參閱[攜帶您自己的金鑰（BYOK）以取得 Azure 資訊保護](https://docs.microsoft.com/azure/information-protection/byok-price-restrictions)。 若有需要在內部部署保留加密金鑰的客戶，也會提供另一個更複雜的選項，稱為保留您自己的金鑰（HYOK）。  如需詳細資訊，請參閱[保留您自己的金鑰（HYOK）以取得 Azure 資訊保護](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions)。 <br/> |
    

