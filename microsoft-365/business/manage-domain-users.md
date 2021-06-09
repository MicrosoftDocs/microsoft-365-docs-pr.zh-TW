---
title: 將網域使用者同步處理至 Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 以商務用 Microsoft 365 同步處理域控制的使用者。
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578400"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>將網域使用者同步處理至 Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. 準備目錄同步處理 

在您從本機 Active Directory 網域同步處理使用者和電腦之前，請先複查[準備好目錄同步處理至 Microsoft 365](../enterprise/prepare-for-directory-synchronization.md)。 具體說來：

   - 請確定目錄中的下列屬性沒有重複專案： **mail**、 **proxyAddresses** 及 **userPrincipalName**。 這些值必須是唯一的，而且必須移除任何重複專案。
   
   - 建議您為每個本機使用者帳戶設定 **userPrincipalName** (UPN) 屬性，使其符合授權之 Microsoft 365 使用者所對應的主要電子郵件地址。 例如： *mary.shelley@contoso.com* ，而不是 *mary@contoso。*
   
   - 如果 Active Directory 網域以非可路由的尾碼（如 .com *或* *lan*）結束，請不要依 internet 路由尾碼（如 *.com* 或 *org*）來調整本機使用者帳戶的 UPN 尾碼，如 [準備目錄同步處理的非路由網域](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)中所述。 

在下列步驟 4 (4) 中 **執行 IdFix** ，也會確定內部部署 Active Directory 已準備好進行目錄同步處理。

## <a name="2-install-and-configure-azure-ad-connect"></a>2. 安裝及設定 Azure AD 連線

若要將您的使用者、群組和連絡人從本機 Active Directory 同步處理成 Azure Active Directory，請安裝 Azure Active Directory 連線和設定目錄同步處理。 

 1. 在系統 [管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)的左側，選取 [ **安裝程式** ]。

 2. 在 [登 **入及安全性**] 下，選擇 [**從您的組織的目錄同步處理使用者**] 底下的 [**查看**]。

 3. 在 [ **從您的組織的目錄同步處理使用者** ] 頁面上，選擇 [ **開始**]。

 4. 在第一個步驟中執行 IdFix 工具來準備目錄同步處理。

 5. 依照嚮導步驟下載 Azure AD 連線，並使用它來同步處理網域的使用者，以進行 Microsoft 365。


請參閱[設定 Microsoft 365 的目錄同步](../enterprise/set-up-directory-synchronization.md)處理以深入瞭解。

當您設定 Azure AD 連線的選項時，建議您啟用 **[密碼同步** 處理]、[**無縫單 Sign-On**] 和 [**密碼寫回** 功能] （Microsoft 365 for business]）。

> [!NOTE]
> 在 Azure AD 連線中，除了核取方塊之外，還有其他一些步驟可用於密碼回寫。 如需詳細資訊，請參閱 how [to：設定密碼回寫](/azure/active-directory/authentication/howto-sspr-writeback)。 

如果您也想要管理已加入網域的 Windows 10 裝置，請參閱 Microsoft 365 商務進階版設定已[加入網域的 Windows 10 裝置](manage-windows-devices.md)以設定混合式 Azure AD 聯結。