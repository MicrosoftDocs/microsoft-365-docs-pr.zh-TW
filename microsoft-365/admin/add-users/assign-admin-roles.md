---
title: 指派管理員角色 Microsoft 365 系統管理中心
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: eac4d046-1afd-4f1a-85fc-8219c79e1504
description: 瞭解如何將系統管理員角色指派給您公司中的使用者或多位使用者，以便他們可以在系統管理中心執行特定工作。
ms.openlocfilehash: e53d1a414d081ddb74a1c4784adcd982b6194691
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683208"
---
# <a name="assign-admin-roles"></a>指派系統管理員角色

如果您是購買 Microsoft 商務版訂閱的人員，您必須是全域系統管理員。這表示您對訂閱中的產品擁有無限制的控制，而且您可以存取大部分的資料。

如需詳細資訊，請參閱[系統管理員角色](about-admin-roles.md)。

當您加入新的使用者時，如果您不是指派系統管理員角色，則其為 *使用者角色* ，且沒有任何 Microsoft 系統管理中心的系統管理員許可權。 不過，如果您需要協助完成，您可以將系統管理員角色指派給使用者。 例如，如果您需要人員協助重設密碼，您不應該將其指派為全域系統管理員角色，您應該將密碼系統管理員角色指派給他們。 全域管理員過多，且對您的資料和線上業務擁有無限制的存取權，將是安全性風險。

## <a name="watch-add-an-adminbrbr"></a>觀賞：新增管理員<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfO] 

如果您覺得這段影片很有幫助，請查看[適用於小型企業和 Microsoft 365 新手的完整訓練系列](../../business-video/index.yml)。

## <a name="assign-admin-roles"></a>指派系統管理員角色 

您可以使用兩種不同的方式指派角色給使用者：

- 您可以移至使用者的詳細資料，以及 **管理角色** ，將角色指派給使用者。
- 或者，您可以移至 [ **角色** ] 並選取角色，然後將多個使用者新增至該角色。

### <a name="assign-admin-roles-to-users-using-roles"></a>使用角色將系統管理員角色指派給使用者

1. 在系統管理中心中，移至 [ **角色**]。 選擇 [ **AZURE AD** ] 或 [ **Intune** ] 索引標籤，以查看組織可使用的系統管理員角色。
2. 選取您要指派給使用者的系統管理員角色。
3. 選取 [指派的系統 **管理員**] [  >  **新增**]。
4. 輸入使用者的 **顯示名稱** 或使用者名稱，然後從建議 **清單中選取** 使用者。
5. 在您完成之前，新增多個使用者。
6. 選取 [ **儲存**]，然後將使用者新增至指派的系統管理員清單。

### <a name="assign-a-user-to-an-admin-role-from-active-users"></a>從作用中使用者將使用者指派給管理員角色

::: moniker range="o365-worldwide"

1. 在系統管理中心中，移至 [ **使用者** 作用中 > [使用者](https://go.microsoft.com/fwlink/p/?linkid=834822) ] 頁面。

::: moniker-end

::: moniker range="o365-germany"

1. 在系統管理中心中，移至 **[使用者]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[作用中使用者]</a> 頁面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在系統管理中心中，移至 **[使用者]** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[作用中使用者]</a> 頁面。

::: moniker-end

2. 在 [作用中 **使用者** ] 頁面上，選取您要變更其系統管理員角色的使用者。 在快顯視窗窗格中的 [ **角色**] 下，選取 [ **管理角色**]。

3. 選取要指派給使用者的系統管理員角色。 如果您找不到所要的角色，請選取清單底部的 [ **全部顯示** ]。

## <a name="assign-admin-roles-to-multiple-users"></a>指派系統管理員角色給多個使用者

如果您知道 PowerShell，請參閱 [使用 PowerShell 指派角色給使用者帳戶](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)。 這最適合用來指派角色給數百個使用者。
  
使用下列指示指派角色給數十個使用者。

## <a name="check-admin-roles-in-your-organization"></a>檢查組織中的系統管理員角色

您可能沒有適當的許可權可以指派系統管理員角色給其他使用者。 請確認您具備正確的許可權，或是要求其他管理員為您指派角色。

您可以以兩種不同的方式來檢查系統管理員角色許可權：

- 您可以移至使用者的詳細資料，並在 [**帳戶**] 頁面的 [**角色**] 中查看。
- 或者，您可以移至 [ **角色** ] 並選取 [管理員] 角色，然後選取 [指派的系統管理員] 以查看指派的使用者。

## <a name="related-content"></a>相關內容

[關於 Microsoft 365 系統管理員角色](about-admin-roles.md) (文章) \
[Azure Active Directory (文章中的系統管理員角色許可權](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)) \
[將角色指派給具有 PowerShell (文章的使用者帳戶](../../enterprise/assign-roles-to-user-accounts-with-microsoft-365-powershell.md)) \
[授權或移除](../misc/add-partner.md) 第三 (篇文章的夥伴關係) 