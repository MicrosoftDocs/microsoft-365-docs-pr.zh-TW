---
title: 雲端解決方案供應商的其他資訊
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 摘要：與從 Microsoft Cloud Deutschland 進行遷移相關的雲端解決方案提供者的其他資訊。
ms.openlocfilehash: 843552c55acba57c5c2da4a1a885d65cb4e59d84
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984913"
---
# <a name="additional-information-for-cloud-solution-providers"></a>雲端解決方案供應商的其他資訊

雲端解決方案供應商 (Csp) 支援客戶必須在從 Microsoft Cloud Deutschland 遷移至新的德國資料中心區域時採取額外的步驟。

## <a name="partner-tenant-migration"></a>合作夥伴租使用者遷移

將不會遷移協力廠商 Microsoft Cloud Deutschland 承租人。 相反地，會為新的德國資料中心區域中的每個 Microsoft 合作夥伴建立新的 Office 365 服務租使用者。

CSP 客戶租使用者將遷移至新的德國資料中心區域，並連結至相同合作夥伴的新 Office 365 服務租使用者。 客戶轉換後，合作夥伴可以使用德國資料中心區域的新 Office 365 服務租使用者管理客戶。

## <a name="missing-subscriptions-in-azure"></a>Azure 中遺失訂閱

[訂閱和授權轉換 (階段 3) ](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)完成之後，雲端方案提供者將無法存取 Azure 訂閱。

若要復原存取權，請遵循下列步驟，以 [提升管理所有 Azure 訂閱和管理群組的存取權](/azure/role-based-access-control/elevate-access-global-admin)。
