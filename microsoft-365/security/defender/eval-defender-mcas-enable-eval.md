---
title: 為 Microsoft Cloud App Security 啟用評估環境
description: 瞭解 Microsoft Defender 內 MCAS 的架構，以 Office 365 和瞭解 Microsoft 365 Defender 產品之間的互動。
keywords: Microsoft 365 Defender 試用版，請嘗試 Microsoft 365 Defender，評估 Microsoft 365 Defender，Microsoft 365 Defender 評估實驗室，Microsoft 365 Defender 試驗，網路安全性，高級持續性威脅，企業安全性，裝置，裝置，身分識別，使用者，資料，應用程式，事件，自動化調查和修正，高級搜尋
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457762"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a>為 Microsoft Cloud App Security 啟用評估環境


**適用於：**

- Microsoft 365 Defender

本文是設定 Microsoft Cloud App Security 評估環境之程式中的[步驟2之 2](eval-defender-mcas-overview.md) 。 如需此程式的詳細資訊，請參閱 [概述文章](eval-defender-mcas-overview.md)。

本文將引導您逐步瞭解存取雲端 App 安全性入口網站及設定必要的整合，以收集雲端應用程式流量資料。

若要探索您環境中使用的雲端應用程式，您可以執行下列其中一項或兩項操作：

- 與 Microsoft Defender for Endpoint 整合，透過雲端探索快速取得並執行。 這種原生整合可讓您立即開始在網路上的 Windows 10 裝置之間收集雲端流量的資料。
- 若要探索所有連接至網路之裝置存取的所有雲端應用程式，請在防火牆和其他 proxy 上部署雲端 App 安全性的記錄收集器。 這樣會從您的端點收集資料，並將其傳送至雲端 App 安全性以進行分析。 雲端 App 安全性原本會與某些協力廠商 proxy 整合，以取得更多功能。

本文包含這兩種方法的指導方針。

使用下列步驟來設定 Microsoft Cloud App Security。

![在 microsoft Defender 評估環境中啟用 microsoft Microsoft Cloud App Security 的步驟](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [步驟1。連線至雲端 App 安全性入口網站](#step-1-connect-to-the-cloud-app-security-portal)
- [步驟2。與 Microsoft Defender for Endpoint 整合](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [步驟3。在防火牆和其他 proxy 上部署雲端 App 安全性記錄收集器](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [步驟4。查看雲端探索儀表板，以查看您的組織正在使用哪些應用程式](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a>步驟 1. 連線至雲端 App 安全性入口網站

若要驗證授權並聯機至雲端 App 安全性入口網站，請參閱[快速入門：開始使用 Microsoft Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)。 

如果您不能立即連線至入口網站，您可能需要將 IP 位址新增至防火牆的允許清單。 請參閱[基本設定雲端 App 安全性](/cloud-app-security/general-setup)。

如果仍有問題，請複查 [網路需求](/cloud-app-security/network-requirements)。

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>步驟 2. 與 Microsoft Defender for Endpoint 整合

Microsoft Cloud App Security 與 Microsoft Defender for Endpoint 本來進行整合。 整合可簡化 Cloud Discovery 的推出、將雲端探索功能延伸至公司網路以外，並啟用裝置型調查。 這種整合會顯示從 IT 管理的 Windows 10 裝置存取的雲端應用程式和服務。 

如果您已設定 Microsoft Defender for Endpoint，設定與雲端 App 安全性的整合是 Microsoft 365 Defender 中的切換。 整合開啟之後，您可以回到雲端 App 安全性入口網站，並在雲端探索儀表板中查看豐富的資料。

若要完成這些工作，請參閱[Microsoft Defender For Endpoint integration with Microsoft Cloud App Security](/cloud-app-security/mde-integration)。 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a>步驟 3. 在防火牆和其他 proxy 上部署雲端 App 安全性記錄收集器

若要在連接至網路的所有裝置上進行覆蓋率，請在防火牆和其他 proxy 上部署雲端 App 安全性的記錄收集器，以從端點收集資料，並將資料傳送至雲端 App 安全性進行分析。 

如果您使用下列其中一個安全網頁閘道 (SWG) ，雲端 App 安全性可提供無縫的部署和整合：
- Zscaler
- iboss
- Corrata
- Menlo 安全性

如需整合這些網路裝置的詳細資訊，請參閱 [設定雲端探索](/cloud-app-security/set-up-cloud-discovery)。 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>步驟 4： 查看雲端探索儀表板，以查看您的組織正在使用哪些應用程式

雲端探索儀表板的設計可讓您深入瞭解組織中的雲端應用程式的使用方式。 它會深入瞭解使用哪些類型的應用程式、開啟的警示，以及組織中應用程式的風險層級。 

若要開始使用雲端探索儀表板，請參閱使用已 [探索的應用程式](/cloud-app-security/discovered-apps)。

## <a name="next-steps"></a>後續步驟

步驟3之3：[試驗 Microsoft Cloud App Security](eval-defender-mcas-pilot.md)

回到 [[評估 Microsoft Cloud App Security](eval-defender-mcas-overview.md)的總覽

回到[評估與試驗 Microsoft 365 Defender](eval-overview.md)概述