---
title: 將應用程式固定至使用者的應用程式啟動器
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: 作為全域系統管理員，您最多可以將三個應用程式上插至使用者的應用程式啟動器。
ms.openlocfilehash: 786368f1236c7a86a6fbd0dd863ad0296cb65fac
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579263"
---
# <a name="pin-apps-to-your-users-app-launcher"></a>將應用程式固定至使用者的應用程式啟動器

您可以使用 Azure Active Directory 入口網站中的控制項，最多可為您組織中的所有使用者上插上第三個應用程式，以 Office .com 和應用程式啟動器。 您也可以組織應用程式群組。 您新增的任何應用程式以後都可以由使用者取消固定。 若要為您的使用者固定應用程式，您必須是雲端應用程式管理員或 Azure Active Directory 中的應用程式管理員，或 Office 365 中的全域管理員。 如需系統管理員角色的詳細資訊，請參閱在 Microsoft 365 中 Azure Active Directory 和系統[管理角色](../add-users/about-admin-roles.md)[中的系統管理員角色](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 

如需有關應用程式啟動器和 Office .com 的詳細資訊，請參閱 office.com [app 啟動器](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)和[更新至和-Office 365 應用程式啟動器](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503)博客文章。

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a>使用 Azure Active Directory 入口網站來固定應用程式

1. 前往 Microsoft 365 系統管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。
2. 在左側導覽中，選擇 [**全部顯示**]，然後在 [系統 **管理中心**] 底下，選擇 [ **Azure Active Directory**]。
3. 在 **Azure Active Directory** 中，選擇 [ **Enterprise 應用程式**  >  **使用者設定**]。
4. 在 [ **Office 365 設定**] 區段中，選擇 [**新增應用程式**]。
5. 選擇您要固定至使用者應用程式啟動器的應用程式，然後選擇 [ **新增**]。

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365 固定應用程式的設定。":::

### <a name="pin-a-custom-app"></a>固定自訂應用程式

> [!NOTE]
> 使用者介面會指出是否需要購買其他 Azure AD 授權，才能使用此功能。 如需詳細資訊，請參閱[Azure Active Directory 定價](https://azure.microsoft.com/pricing/details/active-directory/)。

1. 在 **Azure Active Directory** 中，選擇 [所有應用程式] 頁面上方的 [ **Enterprise 應用程式**  >  **新應用程式**]。 
2. 在 [**新增應用程式**] 頁面上，選擇 [**非圖庫] 應用** 程式，如果您在 Azure Active Directory 的預覽版本中，請選擇 [**建立您自己的應用程式**]。 
3. 輸入應用程式的名稱，然後在 [ **使用者和群組** ] 索引標籤中指派使用者。
4. 使用 [ **屬性** ] 索引標籤可上傳應用程式的圖示。
5. 若要指派應用程式的 URL，請在 [ **單一登入** ] 索引標籤中，選擇 [ **連結** ]，然後輸入 url。
6. 選擇 **[儲存]**。

## <a name="create-application-collections"></a>建立應用程式集合

您也可以為組織中的使用者建立應用程式集合。 如需相關指示，請參閱在 [Azure 入口網站中的我的應用程式入口網站上建立集合](/azure/active-directory/manage-apps/access-panel-collections)。