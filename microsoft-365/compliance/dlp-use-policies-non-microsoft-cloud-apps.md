---
title: 使用非 Microsoft cloud app 的資料遺失防護原則
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何對非 Microsoft cloud app 使用 dlp 原則。
ms.openlocfilehash: fbba87fc5bb3bbca7e67ba374e202098a22f4a5c
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300121"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a>使用非 Microsoft cloud app 的資料遺失防護原則 (預覽) 

資料遺失防護 (dlp) 原則的非 Microsoft cloud app 屬於 Microsoft 365 DLP 套件的一部分;您可以使用這些功能，在 Microsoft 365 服務中探索和保護機密專案。 如需所有 Microsoft DLP 產品的詳細資訊，請參閱 [瞭解資料遺失防護](dlp-learn-about-dlp.md)。

您可以使用 DLP 原則來監視和偵測敏感專案何時使用，並透過非 Microsoft cloud app 加以共用。 使用這些原則可提供您所需的可見度和控制，以確保它們已正確使用和受到保護，並可協助防範可能會損損的危險行為。

## <a name="before-you-begin"></a>開始之前

### <a name="skusubscriptions-licensing"></a>SKU/訂閱授權

開始使用 DLP 原則至非 Microsoft cloud app 之前，請先確認您的[Microsoft 365 訂閱](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)和任何附加元件。 若要存取及使用此功能，您必須具有下列其中一項訂閱或附加元件：

- Microsoft 365 E5
- Microsoft 365 E5 合規性
- Microsoft 365 E5 安全性

### <a name="permissions"></a>權限
建立 DLP 原則的使用者應該是：
- 全域系統管理員
- 合規性管理員
- 合規性資料管理員

### <a name="prepare-your-cloud-app-security-environment"></a>準備您的雲端 App 安全性環境

dlp 原則至非 Microsoft cloud app 使用雲端 App 安全性 DLP 功能。 若要使用它，您應該準備雲端 App 安全性環境。 如需相關指示，請參閱為 [您的應用程式設定立即可視性、保護和](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)控管動作。

### <a name="connect-a-non-microsoft-cloud-app"></a>連線非 Microsoft cloud app

若要使用 DLP 原則至特定的非 Microsoft cloud app，應用程式必須連接至雲端 App 安全性。 如需詳細資訊，請參閱：

- [連線箱](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [連線 Dropbox](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [連線G-套件](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [連線Salesforce](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [連線Cisco Webex](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

將雲端應用程式連線至雲端 App 安全性後，您可以為其建立 Microsoft 365 的 DLP 原則。

> [!NOTE]
> 您也可以使用 Microsoft Cloud App Security 來建立 DLP 原則至 Microsoft 雲端應用程式。 不過，建議使用 Microsoft 365 來建立及管理 DLP 原則至 Microsoft 雲端應用程式。

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a>建立非 Microsoft cloud app 的 DLP 原則

當您選取 DLP 原則的位置時，請開啟 **Microsoft Cloud App Security** 位置。

- 若要選取特定的應用程式或實例，請選取 **[選擇實例**]。
- 如果您未選取實例，則原則會使用 Microsoft Cloud App Security 租使用者中所有連接的應用程式。

   ![套用原則的位置](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US 和 Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

您可以針對每個支援的非 Microsoft cloud app 選擇各種動作。 每個應用程式都有不同的可能動作 (取決於雲端應用程式 API) 。

![建立規則](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

當您在 DLP 原則中建立規則時，您可以選取非 Microsoft cloud app 的動作。 若要限制協力廠商應用程式，請選取 [ **限制協力廠商應用程式**]。

![限制協力廠商應用程式](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

> [!NOTE]
> 套用至非 Microsoft 應用程式的 DLP 原則使用 Microsoft Cloud App Security。 建立非 Microsoft 應用程式的 DLP 原則時，會自動在 Microsoft Cloud App Security 中建立相同的原則。

如需建立及設定 DLP 原則的詳細資訊，請參閱 [Create test and 微調 dlp policy](./create-test-tune-dlp-policy.md)。

## <a name="see-also"></a>另請參閱

- [建立測試並調整 DLP 原則](./create-test-tune-dlp-policy.md)
- [預設的 DLP 原則快速入門](./get-started-with-the-default-dlp-policy.md)
- [從範本建立 DLP 原則](./create-a-dlp-policy-from-a-template.md)
