---
title: 使用 AD RMS 的 Exchange Online 郵件加密
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
ms.custom:
- seo-marvel-apr2020
description: 瞭解如何設定 Exchange Online IRM 使用內部部署 Active Directory Rights Management Service (AD RMS) ，以滿足組織的需求。
ms.openlocfilehash: d98cf5c762cd4dac0cbad6d25a3cc766d5c5310a
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876272"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>使用 AD RMS 的 Exchange Online 郵件加密

為了防止資訊外洩，Exchange Online 包含資訊版權管理 (IRM) 功能，可針對電子郵件訊息和附件提供線上和離線保護。 您可以設定 Exchange Online IRM 使用內部部署 Active Directory Rights Management Service (AD RMS) （如有需要），以滿足組織的需求。 這並不常見。 如果您不需要使用 AD RMS，請改用[Office 365 郵件加密](ome.md)。 

IRM 保護可由 Microsoft Outlook 中的使用者或網頁上的 Outlook 套用，也可以由系統管理員使用傳輸保護規則或 Outlook 保護規則來套用。 IRM 可協助您和使用者控制能夠存取、轉寄、列印或複製電子郵件中之機密資料的人員。
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>Office 365 郵件加密 (OME) 和 Azure Active Directory 的 IRM 的運作方式變更

在2017年9月為止，當您為組織設定新的 Office 365 郵件加密功能時，您也會設定 IRM，以搭配 azure Rights Management (azure RMS) 使用。 您不再使用 Azure RMS 單獨設定 IRM。 相反地，OME 及 rights management 會順利地一起運作。 如需新功能的詳細資訊，請參閱[Office 365 郵件加密常見問題](./ome-faq.yml)。 如果您已準備好開始使用組織內的新 OME 功能，請參閱[設定以 Azure 資訊保護為基礎的新 Office 365 郵件加密功能](./set-up-new-message-encryption-capabilities.md)。
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>IRM 與 Exchange Online 和 Active Directory Rights Management Services 的運作方式

Exchange OnlineIRM 使用內部部署 Active Directory Rights Management Services (AD RMS) ，Windows Server 2008 和更新版本中的資訊保護技術。 系統會藉由將 AD RMS 權限原則範本套用至電子郵件，將 IRM 保護套用至電子郵件。 許可權會附加至郵件本身，使保護在線上及離線，以及組織防火牆內部和外部進行。
  
使用者可以將範本套用至電子郵件訊息，以控制收件者對郵件的許可權。 透過將 AD RMS 權限原則套用至郵件，即可控制如轉寄、從郵件擷取資訊、儲存郵件或列印郵件等動作。
  
您可以將 IRM 設定為使用執行 Windows server 2008 或更新版本的 AD RMS 伺服器。 您可以使用這個 AD RMS 伺服器來管理雲端架構組織的 AD RMS 權限原則範本。 Outlook 也會仰賴 AD RMS 伺服器，讓使用者將 IRM 保護套用至他們所傳送的郵件。 如需詳細資訊，請參閱 [將 IRM 設定為使用內部部署 AD RMS 伺服器](configure-irm-to-use-an-on-premises-ad-rms-server.md)。 
  
啟用之後，您就可以依照下列方式，將 IRM 保護套用至郵件：
  
- **使用者可以使用網頁上的 Outlook 和 Outlook，手動套用範本。** 使用者可以從 [ **設定許可權** ] 清單中選取範本，將 AD RMS 許可權原則範本套用至電子郵件。 當使用者傳送受 IRM 保護的郵件時，使用受保護格式的任何附加檔案也會受到與郵件相同的 IRM 保護。 IRM 保護會套用至與 Word、Excel 和 PowerPoint 相關聯的檔案，以及 .xps 檔案和附加的電子郵件訊息。 
    
- **系統管理員可以使用傳輸保護規則，在網頁上同時將 IRM 保護套用至 Outlook 和 Outlook。** 您可以建立傳輸保護規則，以 IRM 保護郵件。 請設定傳輸保護規則動作，以便將 AD RMS 權限原則範本套用至符合規則條件的郵件。 啟用 IRM 之後，組織的 AD RMS 權限原則範本就可以搭配名為 **套用權限保護到具有下列條件的郵件** 的傳輸保護規則動作使用。
    
- **管理員可以建立 Outlook 保護規則。** Outlook 保護規則會根據郵件條件（包括寄件者的部門、郵件的寄件者，以及收件者位於組織內部或外部），自動將 IRM 保護套用至 Outlook 2010 Outlook (中) 的郵件。 如需詳細資訊，請參閱[Create an Outlook Protection Rule](/exchange/create-an-outlook-protection-rule-exchange-2013-help)。
