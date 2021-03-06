---
title: 設定連接器來封存 Facebook 資料
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 瞭解如何設定 & 使用 Microsoft 365 規範中心內的連接器，將 & 封存資料從 Facebook 商務頁面匯入 Microsoft 365。
ms.openlocfilehash: 616466a3af83c1558184526aa463f68c10ef9e70
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921733"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>設定連接器以封存 Facebook 資料 (預覽) 

使用 Microsoft 365 規範中心內的連接器，將 Facebook 商務版頁面中的資料匯入並封存至 Microsoft 365。 在您設定及設定連接器之後，它會以排程的方式連線至 Facebook 商務頁面 () 、將 Facebook 專案的內容轉換為電子郵件訊息格式，然後將這些專案匯入 Microsoft 365 中的信箱。

在匯入 facebook 資料之後，您可以對 facebook 資料套用 Microsoft 365 規範功能（例如訴訟暫止、內容搜尋、In-Place 封存、審核、通訊合規性及 Microsoft 365 保留原則）。 例如，當信箱處於訴訟暫止狀態或指派給保留原則時，就會保留 Facebook 資料。 您可以使用內容搜尋來搜尋協力廠商資料，或關聯在 Advanced eDiscovery 案例中，與系統管理員一起儲存 Facebook 資料的信箱。 使用連接器在 Microsoft 365 中匯入和封存 Facebook 資料，可協助您的組織遵守政府和法規原則。

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>設定 Facebook 商務版網頁連接器的必要條件

完成下列先決條件之前，您可以在 Microsoft 365 規範中心內安裝和設定連接器，以便從組織的 Facebook 商務頁面匯入及封存資料。 

- 您的組織的商務頁面需要 Facebook 帳戶 (您必須在設定連接器) 時登入此帳戶。 目前，您只能從 Facebook 商務版頁面封存資料;您無法封存個別 Facebook 設定檔中的資料。

- 您的組織必須具有有效的 Azure 訂閱。 如果您沒有現有的 Azure 訂閱，您可以註冊下列其中一個選項：

    - [註冊免費的一年 Azure 訂閱](https://azure.microsoft.com/free)

    - [註冊隨付即用 Azure 訂閱](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Microsoft 365 訂閱隨附的[免費 Azure Active Directory 訂閱](use-your-free-azure-ad-subscription-in-office-365.md)不支援安全性 & 規範中心內的連接器。

- Facebook 商務頁面的連接器可以一天內匯入200000項總計。 如果一天內有超過200000的 Facebook 商務專案，就不會將這些專案匯入至 Microsoft 365。

- 在步驟 5) 中設定「Microsoft 365 規範中心」 (中的自訂連接器的使用者，必須在 Exchange Online 中指派「信箱匯入匯出」角色。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步驟1：在 Azure Active Directory 中建立應用程式

第一步是在 Azure Active Directory (AAD) 中註冊新的應用程式。 此應用程式對應到您在步驟4中所執行的 web 應用程式資源，以及 Facebook 連接器的步驟5。 

如需逐步指示，請參閱[在 Azure Active Directory 中建立應用程式](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)。

在完成此步驟 (，請使用上述逐步指示) ，將下列資訊儲存至文字檔。 這些值會在部署程式的後續步驟中使用。

- AAD 應用程式識別碼

- AAD 應用程式機密

- 租使用者識別碼

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>步驟2：將連接器 web 服務從 GitHub 部署至您的 Azure 帳戶

下一步是部署 Facebook Business pages connector 應用程式的原始程式碼，該應用程式會使用 Facebook API 來連線到 Facebook 帳戶並提取資料，以便您可以將資料匯入至 Microsoft 365。 您為組織部署的 facebook 連接器會將您的 facebook 商務頁面上的專案上傳至此步驟中建立的 Azure 儲存體位置。 在步驟 5) 中建立「Microsoft 365 規範中心」 (中的 facebook 商務頁面連接器之後，匯入服務會將 facebook 商務頁面資料從 Azure 儲存體位置複製到 Microsoft 365 組織中的信箱。 如先前在[必要條件](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages)區段中所述，您必須具備有效的 Azure 訂閱，才可建立 Azure 儲存體帳戶。

如需逐步指示，請參閱[將連接器 web 服務從 GitHub 部署至您的 Azure 帳戶](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。

在完成此步驟的逐步指示中，您將會提供下列資訊：

- APISecretKey：完成此步驟時，您會建立此密碼。 它會在步驟5中使用。

- TenantId：在步驟 1 Azure Active Directory 中建立 Facebook 連接器應用程式之後，您 Microsoft 365 組織所複製的租使用者識別碼。

完成此步驟後，請務必複製 Azure 應用程式服務 URL (例如， https://fbconnector.azurewebsites.net) 。 您必須使用此 URL，才能完成步驟3、步驟4及步驟 5) 。

## <a name="step-3-register-the-web-app-on-facebook"></a>步驟3：在 Facebook 上註冊 web 應用程式

下一步是在 Facebook 上建立及設定新的應用程式。 您在步驟5中建立的 Facebook 商務頁面連接器會使用 Facebook web app 與 Facebook API 互動，以從組織的 Facebook 商務版頁面中取得資料。

如需逐步指示，請參閱 [註冊 Facebook 應用程式](deploy-facebook-connector.md#step-3-register-the-facebook-app)。

在完成此步驟時 (請遵循) 的逐步指示，將下列資訊儲存至文字檔。 這些值是用來在步驟4中設定 Facebook 連接器應用程式。

- Facebook 應用程式識別碼

- Facebook 應用程式機密

- Facebook webhooks verify token

## <a name="step-4-configure-the-facebook-connector-app"></a>步驟4：設定 Facebook 連接器應用程式

下一步是將設定設定新增至您在步驟1中建立 Azure web app 資源時所上傳的 Facebook 連接器應用程式。 若要執行此動作，請移至連接器應用程式的首頁並加以設定。

如需逐步指示，請參閱 Configure the [Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)。

在此步驟完成過程中 (按逐步指示) ，提供下列資訊， (您在完成上述步驟之後，您已複製到文字檔) ：

- 在步驟3中取得的 Facebook 應用程式識別碼 () 

- 在步驟3中取得的 Facebook 應用程式機密 () 

- Facebook webhooks 驗證在步驟3中取得的 token () 

- Azure Active Directory (步驟1中取得的 AAD 應用程式識別碼的應用程式識別碼) 

- Azure Active Directory 應用程式機密 (步驟1中取得的 AAD 應用程式密碼) 

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>步驟5：設定 Microsoft 365 規範中心內的 Facebook 商務頁面連接器

最後一個步驟是在 Microsoft 365 規範中心內設定連接器，將您的 Facebook 商務頁面中的資料匯入 Microsoft 365 中的指定信箱。 完成此步驟之後，Microsoft 365 匯入服務將開始從您的 Facebook 商務版頁面匯入資料，以 Microsoft 365。

如需逐步指示，請參閱「[步驟5：設定 Microsoft 365 規範中心內的 Facebook 連接器](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center)」。 

在此步驟完成過程中 (按逐步指示) 中，您會提供下列資訊， (在完成步驟) 之後，您已複製到文字檔。

- 在步驟1中取得的 AAD 應用程式識別碼 () 

- 在步驟1中取得的 Azure 應用程式服務 URL (;例如， https://fbconnector.azurewebsites.net)

- 您在步驟2中建立的 APISecretKey () 