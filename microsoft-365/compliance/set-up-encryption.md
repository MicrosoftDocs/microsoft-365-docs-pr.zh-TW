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
description: 使用 Office 365 時，有些加密功能會預設為開啟狀態;您可以設定其他功能以符合某些規範或法律需求。
ms.openlocfilehash: e153c1e322adaea000cf686e857387d671b18a28
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051675"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>設定 Office 365 企業版中的加密

加密可防止未經授權的使用者讀取您的內容。 因為 [Office 365 中的加密](encryption.md) 可以使用各種技術和方法完成，所以沒有一個單一位置可供您開啟或設定加密。 本文提供您可以在資訊保護原則中設定或設定加密之各種方式的相關資訊。
  
> [!TIP]
> 如果您正在尋找有關加密的詳細技術詳細資料，請參閱 [Office 365 中有關加密的技術參考詳細資料](technical-reference-details-about-encryption.md)。
  
使用 Office 365 時，預設會提供數種加密功能。 您可以設定額外的加密功能，以符合某些規範或法律需求。 下表說明不同案例的數種加密方法。
  
|**案例**|**加密方法**|
|:-----|:-----|
|檔案儲存在 Windows 電腦上  <br/> |您可以使用 Windows 裝置上的 BitLocker，進行電腦層級的加密。 若您是企業系統管理員或 IT 專業人員，您可以使用 Microsoft 部署工具組 (MDT) 加以設定。 請參閱 [設定 BitLocker 的 MDT](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)。  <br/> |
|檔案儲存在行動裝置上  <br/> |某些類型的行動裝置會根據預設，加密儲存至這些裝置的檔。 透過 [內建行動裝置管理的 office 365 功能](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)，您可以設定原則，以判斷是否允許行動裝置存取 Office 365 中的資料。 例如，您可以設定原則，只允許加密內容的裝置存取 Office 365 資料。 請參閱 [建立及部署裝置安全性原則](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)。  <br/> 若要進一步控制行動裝置如何與 Office 365 互動，您可以考慮新增 [Microsoft Intune](/mem/intune/fundamentals/setup-steps)。  <br/> |
|您需要控制用來加密 Microsoft 資料中心中資料的加密金鑰  <br/> | 做為 Office 365 系統管理員，您可以控制組織的加密金鑰，然後設定 Office 365，以使用這些金鑰在 Microsoft 資料中心內加密您的資料。  <br/> [Office 365 中的客戶金鑰服務加密](customer-key-overview.md) <br/> |
|人們會透過電子郵件 (Exchange Online 進行通訊)   <br/> | 做為 Exchange Online 管理員時，您有數個選項可以設定電子郵件加密。 包括：  <br/>  使用 [Office 365 郵件加密 (OME) ](set-up-new-message-encryption-capabilities.md) 搭配 Azure Rights Management (azure RMS) 以允許人員在組織內部或外部傳送加密的郵件  <br/>  使用 [S/MIME 進行郵件簽署和加密](../security/defender-365-security/s-mime-for-message-signing-and-encryption.md) ，以加密及數位簽署電子郵件訊息  <br/>  使用 TLS 為 [其他組織設定安全郵件流程的連接器](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) <br/>  請參閱 [Office 365 中的電子郵件加密](./email-encryption.md)。  <br/> |
|檔案可以從小組網站或文件庫存取 (商務版或 SharePoint 線上) OneDrive  <br/> |當使用者使用儲存至 OneDrive 商務或 SharePoint 線上的檔案時，會使用 TLS 連線。 這會自動內置於 Office 365。 請參閱 [OneDrive For Business and SharePoint Online 中的資料加密](./data-encryption-in-odb-and-spo.md)。  <br/> |
|在線上會議和 IM 交談中共用檔案 (商務用 Skype Online)   <br/> |當使用者使用商務用 Skype Online 處理檔案時，TLS 可用於連線。 這會自動內置於 Office 365。 請參閱 [安全性和封存 (商務用 Skype Online) ](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)。  <br/> |
|檔案會在線上會議和 IM 交談 (Microsoft 小組中共用)   <br/> |當使用者使用 Microsoft 團隊處理檔案時，TLS 用於連線。 這會自動內置於 Office 365。 Microsoft 團隊目前不支援加密電子郵件的內嵌轉譯。 若要防止加密的電子郵件在 Microsoft 小組中以加密形式傳送，請參閱 [郵件加密常見問題](./ome-faq.md?view=o365-worldwide#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail)。  <br/> 

## <a name="additional-information"></a>其他資訊

若要深入瞭解包含加密選項的檔案保護解決方案，請參閱 [Office 365 中的檔案保護解決方案](https://www.microsoft.com/download/details.aspx?id=55523)。
