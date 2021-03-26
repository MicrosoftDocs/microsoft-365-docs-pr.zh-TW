---
title: 從 Microsoft Defender for Endpoint 向您的 SIEM 工具提取偵測
description: 瞭解如何使用 REST API 及設定支援的安全性資訊和事件管理工具來接收及提取偵測。
keywords: 設定 siem、安全性資訊和事件管理工具、splunk、arcsight、自訂指示器、rest api、警示定義、損等指示器
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 97a64c8537ff2a6f9948ed6ed056b8aa7379ce69
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222332"
---
# <a name="pull-detections-to-your-siem-tools"></a>向 SIEM 工具提取偵測

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a>使用安全性資訊和事件管理 (SIEM) 工具提取偵測

>[!NOTE]
>- [Microsoft Defender For Endpoint Alert](alerts.md) 是由一或多個偵測所組成。
>- [Microsoft Defender For Endpoint 偵測](api-portal-mapping.md) 是由裝置上發生的可疑事件及其相關警示詳細資料所組成。
>-Microsoft Defender for Endpoint Alert API 是最新的警示消耗 API，且包含每個警示的相關證據的詳細清單。 如需詳細資訊，請參閱 [Alert 方法和屬性](alerts.md) 和 [清單警示](get-alerts.md)。

Defender for Endpoint 支援安全性資訊和事件管理 (SIEM) 工具來提取偵測。 端點會透過 Azure 所主控的 HTTPS 端點公開警示。 端點可以設定為在 Azure Active Directory (AAD) 中使用 OAuth 2.0 驗證通訊協定來拉入您環境中所安裝之特定 SIEM 連接器的 AAD 應用程式的偵測。

SIEM 的 Defender 目前是透過專用的 SIEM 整合模型，支援下列特定的解決方案工具：

- IBM QRadar
- 微焦點 ArcSight

其他 SIEM 解決方案 (例如 Splunk、RSA NetWitness) ，都是透過以新的警示 API 為基礎的不同整合模型所支援。 如需詳細資訊，請查看 [ [夥伴應用程式](https://securitycenter.microsoft.com/interoperability/partners) ] 頁面，然後選取 [安全性資訊與分析] 區段以取得完整詳細資料。

若要使用其中一種支援的 SIEM 工具，您必須：

- [在 Defender for Endpoint 中啟用 SIEM 整合](enable-siem-integration.md)
- 設定支援的 SIEM 工具：
     - [設定微焦點 ArcSight 以拉入 Defender for Endpoint 偵測](configure-arcsight.md)
     - 設定 IBM QRadar 若要深入瞭解端點偵測以取得資訊，請參閱 [Ibm 知識中心](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)。

如需在偵測 API 中公開的欄位清單的詳細資訊，請參閱 [Defender For Endpoint 偵測欄位](api-portal-mapping.md)。
