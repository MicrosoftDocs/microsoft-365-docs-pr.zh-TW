---
title: 設定連接器來封存 Twitter 資料
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
description: 瞭解系統管理員如何設定和使用原生連接器，將 Twitter 資料匯入 Microsoft 365。
ms.openlocfilehash: 277af8ea7367936c4c9528a8ca50ccd678745bf6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922255"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>設定連接器以封存 Twitter 資料 (預覽) 

使用 Microsoft 365 規範中心內的連接器，將來自 Twitter 的資料匯入並封存至 Microsoft 365。 在您設定及設定連接器之後，它會依排程的方式，連線到您組織的 Twitter 帳戶 () 、將專案內容轉換成電子郵件格式，然後將這些專案匯入 Microsoft 365 中的信箱。

在匯入 twitter 資料之後，您可以對 twitter 資料套用 Microsoft 365 合規性功能，例如訴訟暫止、內容搜尋、In-Place 封存、審核和 Microsoft 365 保留原則。 例如，當信箱處於訴訟暫止狀態或指派給保留原則時，將會保留 Twitter 資料。 您可以使用內容搜尋來搜尋協力廠商資料，或在 Advanced eDiscovery 案例中關聯 Twitter 資料與保管人一起儲存的信箱。 使用連接器在 Microsoft 365 中匯入及封存 Twitter 資料，可協助您的組織遵守政府和法規原則。

在匯入 Twitter 資料之後，您可以對儲存在信箱中的資料套用 Microsoft 365 合規性功能，例如訴訟暫止、內容搜尋、In-Place 封存、審核、通訊相容性及 Microsoft 365 保留原則。 例如，您可以使用內容搜尋來搜尋 Twitter 資料，或關聯在 Advanced eDiscovery 案例中與保管人一起儲存資料的信箱。 使用連接器在 Microsoft 365 中匯入及封存 Twitter 資料，可協助您的組織遵守政府和法規原則。

## <a name="before-you-set-up-a-connector"></a>在您設定連接器之前

完成下列先決條件之前，您可以在 Microsoft 365 規範中心內安裝和設定連接器，以便從組織的 Twitter 帳戶匯入及封存資料。

- 您的組織需要 Twitter 帳戶;您必須在設定連接器時登入此帳戶。

- 您的組織必須具有有效的 Azure 訂閱。 如果您沒有現有的 Azure 訂閱，您可以註冊下列其中一個選項：

    - [註冊免費的一年 Azure 訂閱](https://azure.microsoft.com/free) 

    - [註冊隨付即用 Azure 訂閱](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Microsoft 365 訂閱隨附的[免費 Azure Active Directory 訂閱](use-your-free-azure-ad-subscription-in-office-365.md)不支援安全性 & 規範中心內的連接器。

- Twitter 連接器可以在一天內匯入全部200000專案。 如果一天內有200000以上的 Twitter 專案，則不會將這些專案匯入至 Microsoft 365。

- 在步驟 5) 中設定「Microsoft 365 規範中心」 (中的 Twitter 連接器的使用者，必須在 Exchange Online 中指派「信箱匯入匯出」角色。 依預設，此角色不會指派給 Exchange Online 內的任何角色群組。 您可以將信箱匯入匯出角色新增至 Exchange Online 中的「組織管理」角色群組。 或者，您可以建立角色群組、指派信箱匯入匯出角色，然後將適當的使用者新增為成員。 如需詳細資訊，請參閱「在 Exchange Online 中管理角色群組」一文中的 [[建立角色群組](/Exchange/permissions-exo/role-groups#create-role-groups)或[修改角色](/Exchange/permissions-exo/role-groups#modify-role-groups)群組] 區段。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步驟1：在 Azure Active Directory 中建立應用程式

第一步是在 Azure Active Directory (AAD) 中註冊新的應用程式。 此應用程式會對應至您在您的 Twitter 連接器的步驟2中所執行的 web 應用程式資源。

如需逐步指示，請參閱[在 Azure Active Directory 中建立應用程式](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)。

在完成此步驟時 (請遵循) 的逐步指示，將下列資訊儲存至文字檔。 這些值將會在部署程式的後續步驟中使用。

- AAD 應用程式識別碼

- AAD 應用程式機密

- 租使用者識別碼

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>步驟2：將連接器 web 服務從 GitHub 存放庫部署至您的 Azure 帳戶

下一步是部署 Twitter 連接器應用程式的原始程式碼，該應用程式會使用 Twitter API 連線到 Twitter 帳戶並提取資料，以便將資料匯入至 Microsoft 365。 您為組織部署的 Twitter 連接器會將您組織的 twitter 帳戶中的專案上傳至此步驟中建立的 Azure 儲存體位置。 在「步驟 5) 」的 Microsoft 365 規範 (中心] 中建立 twitter 連接器之後，Microsoft 365 匯入服務會將 Twitter 資料從 Azure 儲存體位置複製到 Microsoft 365 中的信箱。 如先前在[您設定 connector](#before-you-set-up-a-connector)區段中所述，您必須具備有效的 Azure 訂閱，才可建立 Azure 儲存體帳戶。

若要部署 Twitter 連接器應用程式的原始程式碼：

1. 移[至此 GitHub 網站](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)。

2. 按一下 [ **部署至 Azure**]。

如需逐步指示，請參閱[將連接器 web 服務從 GitHub 部署至您的 Azure 帳戶](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。

當您遵循逐步指示來完成此步驟時，您會提供下列資訊。

- APISecretKey：完成此步驟時，您會建立此密碼。 它會在步驟5中使用。

- tenantId：在步驟 1 Azure Active Directory 中建立 Twitter 應用程式之後，您所複製之 Microsoft 365 組織的租使用者識別碼。

完成此步驟後，請務必複製 app 服務 URL (例如， `https://twitterconnector.azurewebsites.net`) 。 您必須使用此 URL，才能完成步驟3、步驟4及步驟 5) 。

## <a name="step-3-create-developer-app-on-twitter"></a>步驟3：建立 Twitter 上的開發人員應用程式

下一步是建立及設定 Twitter 上的開發人員應用程式。 您在步驟7中建立的自訂連接器會使用 Twitter 應用程式與 Twitter API 互動，以從組織的 Twitter 帳戶取得資料。

如需逐步指示，請參閱 [建立 Twitter 應用程式](deploy-twitter-connector.md#step-3-create-the-twitter-app)。

在完成此步驟時 (請遵循) 的逐步指示，將下列資訊儲存至文字檔。 這些值將用於設定步驟4中的 Twitter 連接器應用程式。

- Twitter API 金鑰

- Twitter API 金鑰

- Twitter 存取權杖

- Twitter 存取權杖機密

## <a name="step-4-configure-the-twitter-connector-app"></a>步驟4：設定 Twitter 連接器應用程式

下一步是將設定設定新增至您在步驟2中部署的 Twitter 連接器應用程式。 若要執行此動作，請移至連接器應用程式的首頁並加以設定。

如需逐步指示，請參閱 Configure the [connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)。

在此步驟完成過程中 (按逐步指示) 中，您將會提供下列資訊， (在完成上述步驟) 之後，您已複製到文字檔：

- 在步驟3中取得的 Twitter API 金鑰 () 

- 在步驟3中取得的 Twitter API 私密金鑰 () 

- 在步驟3中取得的 Twitter 存取權杖 () 

- 在步驟3中取得的 Twitter 存取權杖機密 () 

- Azure Active Directory (步驟1中取得的 AAD 應用程式識別碼的應用程式識別碼) 

- Azure Active Directory 應用程式機密 (步驟1中取得的 AAD 應用程式密碼) 

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>步驟5：在 Microsoft 365 規範中心內設定 Twitter 連接器

最後一個步驟是在 Microsoft 365 規範中心內設定 Twitter 連接器，將您組織的 twitter 帳戶中的資料匯入 Microsoft 365 中的指定信箱。 完成此步驟之後，Microsoft 365 匯入服務將開始從您組織的 Twitter 帳戶匯入資料，以 Microsoft 365。

如需逐步指示，請參閱[在 Microsoft 365 規範中心內設定 Twitter 連接器](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center)。 

在此步驟完成過程中 (按逐步指示) 中，您將會提供下列資訊， (在完成步驟) 之後，您已複製到文字檔。

- 在步驟2中取得的 Azure 應用程式服務 URL (;例如， `https://twitterconnector.azurewebsites.net`) 

- 您在步驟2中建立的 APISecretKey () 