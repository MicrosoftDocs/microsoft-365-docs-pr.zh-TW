---
title: 隱私權資訊-iOS 的 Microsoft Defender 端點
ms.reviewer: ''
description: 描述 iOS 的 Microsoft Defender for Endpoint 隱私權資訊
keywords: microsoft、defender、atp、ios、原則、綜述
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 52694322c7f084df777a8e97fe5b84cc3cb4e6d1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058396"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-for-ios"></a>隱私權資訊-iOS 的 Microsoft Defender 端點

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> IOS 的 Defender for a 使用 VPN 提供 Web 保護功能。 這不是一般 VPN，也就是本機或自行迴圈的 VPN，不會對裝置以外的流量進行流量。 **Microsoft 或您的組織未看到您的流覽活動。**

IOS 的 defender for Endpoint 會從您設定的 iOS 裝置收集資訊，並將其儲存在您擁有 Defender for Endpoint 的相同承租人中。 收集此資訊有助於讓 iOS 安全、更新、如期執行，以及支援服務的情況下，取得端點的資訊。

如需資料儲存區的詳細資訊，請參閱 [Microsoft Defender Endpoint data storage and 隱私權](data-storage-privacy.md)。

## <a name="required-data"></a>必要資料 

必要資料包含的資料，使 iOS 端點可以像預期的方式運作。 此資料對於服務的運作很重要，而且可以包含與使用者、組織、裝置及應用程式相關的資料。 

以下是所收集的資料類型清單： 

### <a name="web-page-or-network-information"></a>網頁或網路資訊 

- 僅當偵測到惡意的連線或網頁時，才會使用網站的功能變數名稱。 

### <a name="device-and-account-information"></a>裝置和帳戶資訊 

- 諸如日期 & time、iOS 版本、CPU 資訊和裝置識別碼的裝置資訊，其中裝置識別碼是下列其中一項： 

    - Wi-Fi 配接器 MAC 位址 

    - 隨機產生的全域唯一識別碼 (GUID)  

- 租使用者、裝置和使用者資訊 

    - Azure Active Directory (AD) 裝置識別碼和 Azure 使用者識別碼-在 Azure Active Directory 上分別識別裝置，使用者。 

    - Azure 租使用者識別碼-識別您的組織在 Azure Active Directory 中的 GUID。 

    - Microsoft Defender for Endpoint org ID-與裝置所屬之企業相關聯的唯一識別碼。 可讓 Microsoft 識別是否有問題影響一組選擇的企業和受影響的企業數目。 

    - 使用者主體名稱-使用者的電子郵件識別碼。 

### <a name="product-and-service-usage-data"></a>產品和服務使用方式資料 

僅針對裝置上安裝的 Microsoft Defender for Endpoint 應用程式收集下列資訊。 

- 應用程式套件資訊，包括名稱、版本及應用程式升級狀態。 

- 在應用程式中執行的動作。 

- IOS 所產生的崩潰報告記錄。 

- 記憶體使用狀況資料。 

## <a name="optional-data"></a>選用的資料 

選用的資料包括來自用戶端的診斷資料和意見資料。 選用的診斷資料為額外資料，可協助我們進行產品改善，並提供增強的資訊來協助我們偵測、診斷以及修正問題。 此資料僅用於診斷目的，不是服務本身的必要條件。 

選用的診斷資料包括： 

- 用於 Defender for Endpoint 的應用程式、CPU 及網路使用量。 

- 由系統管理員所設定的 Defender for Endpoint 的功能。 

透過使用者提供的應用程式意見反應收集意見資料。 

- 使用者的電子郵件地址（如果使用者選擇提供的話）。

- 意見反應類型 (微笑、frown、構思) 和使用者提交的任何意見反應批註。 

如需詳細資訊，請參閱 [隱私權的詳細](https://aka.ms/mdatpiosprivacystatement)資訊。


