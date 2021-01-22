---
title: 應用程式監控&報告 - 資訊安全中心
description: 瞭解如何深入瞭解貴組織的雲端 App 使用。 包含不同類型的應用程式、其風險層級和警示。
keywords: 安全性， 惡意攻擊， Microsoft 365， M365， 資訊安全中心， 監視器， 報告， 應用程式
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930519"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Microsoft 365 資訊安全中心的應用程式監控與報告

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


這些報告可提供貴組織中雲端 App 使用方式的深入見解。 包含不同類型的應用程式、其風險層級和警示。

## <a name="monitor-email-accounts-at-risk"></a>監視有風險的電子郵件帳戶

**電子郵件保護** 功能會顯示有風險之電子郵件帳戶。 您可以選取帳戶，在 Microsoft Defender 資訊安全中心進一步調查。

![電子郵件保護卡片](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>監控使用者授予的應用程式許可權

**雲端 App 安全性 - OAuth App** 會列出由雲端 App 安全性所發現，使用者已授予許可權的應用程式。 雲端 App 安全性的風險目錄包含超過 16，000 個應用程式，會使用 70 種以下的風險管理進行評估。

這些風險來自于一般資訊，例如應用程式發行者。 然後，它移到安全性措施和控制措施，例如應用程式是否支援靜態加密或提供使用者活動的稽核記錄。

![雲端 App 安全性 OAuth 應用程式卡片](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>監控雲端 App 使用者帳戶

**用於查看的雲端 App 帳戶** 會列出可能需要注意的帳戶。

![雲端 App 帳戶以用於評論卡片](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>瞭解使用哪些雲端應用程式

**雲端應用程式 (類別)** 會顯示組織中所使用的應用程式類型。 它會連結至雲端 App 安全性中的雲端探索儀表板。 詳細資訊請參閱快速 [入門：使用您發現的應用程式](https://docs.microsoft.com/cloud-app-security/discovered-apps)。  

![已發現雲端應用程式類別卡片](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>監控使用者存取雲端應用程式的地方

**雲端 App 活動位置會顯示** 使用者存取雲端 App 的位置。

![雲端應用程式活動位置卡片](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>監控基礎結構工作負載的健康情況

**基礎結構健康** 情況會顯示 Azure Defender 中基礎結構工作負載的健康情況狀態警示。

Azure Defender 針對內部部署和雲端工作負載提供 Office 365 的統一安全性管理和 Defender。 您可以收集、搜尋及分析不同來源的安全性資料，包括防火牆和其他合作夥伴解決方案。

詳細資訊請參閱 Azure [Defender 檔](https://docs.microsoft.com/azure/security-center/)。

![基礎結構健康狀態卡片](../../media/infrastructure-health.png)
