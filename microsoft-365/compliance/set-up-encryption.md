---
title: 設定 Office 365 企業版中的加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: 使用 Office 365 時，某些加密功能會預設為開啟狀態;您可以設定其他功能以符合某些規範或法律需求。
ms.openlocfilehash: 688d34d767a546cb97d940ab2141bb3edfabcda8
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625230"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>設定 Office 365 企業版中的加密

加密可防止未經授權的使用者讀取您的內容。 因為[Office 365 中的加密](encryption.md)可以使用各種技術和方法來完成，所以沒有一個單一位置可供您開啟或設定加密。 本文提供您可以在資訊保護原則中設定或設定加密之各種方式的相關資訊。

> [!TIP]
> 如果您正在尋找有關加密的詳細技術詳細資料，請參閱[Office 365 中的技術參考詳細資料](technical-reference-details-about-encryption.md)。

在 Office 365 中，預設會提供數種加密功能。 您可以設定額外的加密功能，以符合某些規範或法律需求。 下表說明不同案例的數種加密方法。

<br>

****

|案例|加密方法|
|---|---|
|檔案儲存在 Windows 電腦上|您可以使用 Windows 裝置上的 BitLocker 執行電腦層級的加密。 以企業系統管理員或 IT Pro，您可以使用 Microsoft 部署工具組 (MDT) 來設定此設定。 請參閱[設定 BitLocker 的 MDT](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)。|
|檔案儲存在行動裝置上|某些類型的行動裝置會根據預設，加密儲存至這些裝置的檔。 透過[內建適用於 Office 365 的行動裝置管理的功能](https://support.microsoft.com/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)，您可以設定原則，以判斷是否允許行動裝置存取 Office 365 中的資料。 例如，您可以設定只允許加密內容之裝置存取 Office 365 資料的原則。 請參閱 [建立及部署裝置安全性原則](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)。 <p> 若要進一步控制行動裝置如何與 Office 365 互動，您可以考慮加入[Microsoft Intune](/mem/intune/fundamentals/setup-steps)。|
|您需要控制用來加密 Microsoft 資料中心中資料的加密金鑰|做為 Office 365 管理員，您可以控制組織的加密金鑰，然後設定 Office 365，以使用這些金鑰在 Microsoft 資料中心內加密您的資料。 <p> [Office 365 中的客戶金鑰服務加密](customer-key-overview.md)|
|人們會透過電子郵件 (Exchange Online 進行通訊) |做為 Exchange Online 管理員，您有數個選項可以設定電子郵件加密。 包括： <ul><li>使用[Office 365 郵件加密 (OME) ](set-up-new-message-encryption-capabilities.md)搭配 azure Rights Management (azure RMS) ，以讓使用者在組織內部或外部傳送加密的郵件</li><li>使用 [S/MIME](/exchange/security-and-compliance/smime-exo/smime-exo) 加密及數位簽署電子郵件訊息</li><li>使用 TLS 為 [其他組織設定安全郵件流程的連接器](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)</li></ul> <p> 請參閱[Office 365 中的電子郵件加密](./email-encryption.md)。|
|檔案可以從小組網站或文件庫存取 (商務用 OneDrive 或 SharePoint 線上) |當使用者使用儲存至商務用 OneDrive 或 SharePoint 線上的檔案時，會使用 TLS 連接。 這會自動內建 Office 365。 請參閱[商務用 OneDrive 和 SharePoint Online 中的資料加密](./data-encryption-in-odb-and-spo.md)。|
|線上會議和 IM 交談 (商務用 Skype 線上中共用檔案) |當使用者使用商務用 Skype 線上處理檔案時，TLS 可用於連線。 這會自動內建 Office 365。 請參閱[安全性和封存 (商務用 Skype 線上) ](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。|
|檔案會在線上會議和 IM 交談 (Microsoft Teams 中共用) |當使用者使用 Microsoft Teams 來處理檔案時，TLS 可用於連線。 這會自動內建 Office 365。 Microsoft Teams 目前不支援加密電子郵件的內嵌轉譯。 若要防止在 Microsoft Teams 中加密的電子郵件登陸，請參閱[郵件加密常見問題](./ome-faq.yml?view=o365-worldwide&preserve-view=true#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-)。|
|

## <a name="additional-information"></a>其他資訊

若要深入瞭解包含加密選項的檔案保護解決方案，請參閱[Office 365 中的檔案保護解決方案](https://www.microsoft.com/download/details.aspx?id=55523)。
