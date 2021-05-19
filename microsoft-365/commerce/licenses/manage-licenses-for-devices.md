---
title: 管理裝置的授權
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: 瞭解如何將授權指派給群組，以用於裝置。
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: c590c2d47699c4c3cbea4b5145bea9e7c9fc79ec
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535659"
---
# <a name="manage-licenses-for-devices"></a>管理裝置的授權

如果您有 Microsoft 365 Apps 企業版 (裝置) 或 Microsoft 365 Apps 教育版 (裝置) ，您可以使用 Azure AD 群組將授權指派給裝置。 當裝置具有授權時，使用該裝置的任何人都可以使用 (先前命名 Office 365 專業增強版) 的 Microsoft 365 Apps 企業版。 例如，假設您有20個可擕式電腦及您組織中的人員所使用的平板電腦。 當您指派授權給每個裝置時，登入其中一個裝置的每個人都使用 Microsoft 365 Apps 企業版，而不需要自己的授權。

> [!IMPORTANT]
> Microsoft 365 Apps 企業版的裝置型授權，只會做為部分商業客戶和某些教育客戶的附加元件授權。 針對商業客戶，授權是 *Microsoft 365 Apps 企業版 (裝置)* ，且只能透過 Enterprise 合約/Enterprise 合約訂閱使用。 針對教育版客戶，授權是 *Microsoft 365 Apps 教育版 (裝置)* ，而且只能透過註冊教育版解決方案 (EES) 。 如需詳細資訊，請閱讀「 [教育](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education)版上的博客文章。 如需商用，請與您的 Microsoft 客戶代表聯繫。

若要開始，請在 Azure Active Directory 系統管理中心建立群組，然後將裝置指派至群組。 若要深入瞭解裝置授權（包括裝置需求、您可以使用的群組類型及如何設定 Microsoft 365 Apps 企業版以使用裝置授權），請參閱[裝置型授權 for Microsoft 365 Apps 企業版](/deployoffice/device-based-licensing)。

> [!IMPORTANT]
> 您必須是全域系統管理員，才可完成本文中的工作。

## <a name="assign-licenses-to-devices"></a>指派授權給裝置

當您指派授權給群組時，您可以將授權指派給群組中的所有裝置。 您只可以將一個預訂指派給任何單一群組。

1. 在 Microsoft 365 系統管理中心，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面。
2. 在 [**授權**] 頁面上，選擇 [**教育 (裝置的 Microsoft 365 Apps])** 或 **Microsoft 365 Apps 企業版 (裝置)**]。
3. 在下一個頁面上，選擇訂閱，然後選擇 [ **指派授權**]。
4. 在 [ **將授權指派給群組** ] 窗格中，開始輸入組名，然後從結果中加以選擇以將其新增至清單。
5. 選擇 [ **指派**]，然後選擇 [ **關閉**]。

## <a name="unassign-licenses-from-devices"></a>從裝置取消指派授權

當您取消指派群組中的授權時，會從群組內的所有裝置中移除授權。 所有應用程式及其相關聯的資料都是唯讀的。

1. 在系統管理中心中，移至 [**帳單**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">授權</a>] 頁面。
2. 在 [**授權**] 頁面上，選擇 [**教育 (裝置的 Microsoft 365 Apps])** 或 **Microsoft 365 Apps 企業版 (裝置)**]。
3. 在下一個頁面上，選擇訂閱，選取三個點 ([其他動作) ]，然後選擇 [未 **指派授權**]。
4. 在 [未 **指派的授權** ] 對話方塊中，選擇 [ **取消指派**]。
