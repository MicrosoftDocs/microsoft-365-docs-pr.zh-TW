---
title: 移除離職員工-簡介
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 遵循此方案中的步驟，從 Microsoft 365 中移除前任員工，並保護組織的資料。
ms.openlocfilehash: a613d4931c730dffe195954da97af86c683041bf
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52634241"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>概覽：移除前任員工和安全資料

我們常遇到的問題是：「我應該在員工離開組織時，應如何保護資料並保護存取？」 本文將說明如何封鎖 Microsoft 365 的存取，您應該採取的措施來保護您的資料，以及如何允許其他員工存取資料。

:::image type="content" source="../../media/delete-user-overview.png" alt-text="螢幕擷取畫面：刪除離職員工的步驟":::

## <a name="before-you-begin"></a>開始之前

您必須是全域系統管理員，才可完成此方案中的步驟。

## <a name="solution-remove-a-former-employee"></a>解決方案：移除離職員工

> [!IMPORTANT]
> 雖然我們已編號此方案中的步驟，而且您不需要以完全順序完成此方案，我們建議您以這種方式執行步驟。

:::image type="content" source="../../media/delete-user-account.png" alt-text="螢幕擷取畫面：從組織中移除離職員工的步驟":::

|||
|:-----|:-----|
|**步驟** <br/> |**這樣做的原因** <br/> |
|[步驟 1-防止離職員工登入並封鎖 Microsoft 365 服務的存取權](remove-former-employee-step-1.md) <br/> |這會封鎖您的離職員工 Microsoft 365，並防止人員存取 Microsoft 365 服務。 <br/> |
|[步驟 2-儲存離職員工信箱的內容](remove-former-employee-step-2.md) <br/> |這適用于即將進行員工工作的人員，或是否有訴訟。 <br/> |
|[步驟 3-將離職員工的電子郵件轉寄給另一個員工或轉換成共用信箱](remove-former-employee-step-3.md) <br/> |這讓離職員工的電子郵件地址也能繼續保持有效。如果客戶或合作夥伴仍將電子郵件傳送到離職員工的地址，這樣做可讓他們與接掌工作的人員取得聯繫。 <br/> |
|[步驟 4-授予另一個員工 OneDrive 和 Outlook 資料的存取權](remove-former-employee-step-6.md) <br/> |如果您只移除使用者的授權，但不刪除帳戶，則使用者 OneDrive 中的內容將會保留，即使超過 30 天後仍可存取。 <br/><br/> 在您刪除帳戶之前，您應該授與其他使用者 OneDrive 和 Outlook 的存取權。 在您刪除員工的帳戶之後，其 OneDrive 和 Outlook 中的內容會保留 **30** 天。 不過，在此30天內，您可以還原使用者的帳戶，並取得其內容的存取權。 如果您還原使用者的帳戶，OneDrive 和 Outlook 內容仍可供您在30天之後存取。 <br/> |
|[步驟 5-清除並封鎖離職員工的行動裝置](remove-former-employee-step-4.md) <br/> |從手機或平板電腦中移除您的業務資料。  <br/> |
|[步驟 6-移除並刪除離職員工的 Microsoft 365 授權](remove-former-employee-step-7.md) <br/> |當您移除授權時，您可將授權指派給其他人員。或者，您也可以刪除授權，這樣就不必在雇用另一位人員之前繼續付費。<br/><br/> 當您移除或刪除授權時，使用者的舊電子郵件、連絡人及行事曆會保留 **30 天**，然後永久刪除。 如果您移除或刪除使用者的授權，但不刪除帳戶，則使用者 OneDrive 中的將會保留，即使超過 30 天後仍可存取。  <br/> |
|[步驟 7-刪除離職員工的使用者帳戶](remove-former-employee-step-7.md) <br/> |這會從您的系統管理中心移除帳戶。 保持有條不紊。 <br/> |

## <a name="related-content"></a>相關內容

[還原使用者](restore-user.md) (文章) \
[將新員工新增至 Microsoft 365](add-new-employee.md) (文章)\
[將授權指派給使用者](../manage/assign-licenses-to-users.md) (文章)\
[從使用者取消指派授權](../manage/remove-licenses-from-users.md) (文章) 