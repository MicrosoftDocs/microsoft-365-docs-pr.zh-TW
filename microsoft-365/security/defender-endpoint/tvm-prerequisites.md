---
title: 必要條件 & 許可權-威脅與弱點管理
description: 開始使用威脅與弱點管理之前，請確定您有相關的設定和許可權。
keywords: 威脅 & 弱點管理許可權必要條件，威脅與弱點管理許可權必要條件，Microsoft Defender for Endpoint TVM 許可權必要條件，弱點管理
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c0544665ea4e9b1ceafa645a2dcc96a224b0c242
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843947"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>必要條件 & 許可權-威脅與弱點管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**

- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [威脅及弱點管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

確定您的裝置：

- 會架至 Microsoft Defender for Endpoint
- 執行 [支援的作業系統和平臺](tvm-supported-os.md)
- 在您的網路中安裝並部署下列必要更新，以提升您的漏洞評估偵測速度：

> 發行 | 安全性更新 KB 編號及連結
> :---|:---
> Windows 10版本1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) 和 [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
> Windows 10版本1803 | [KB4493464](https://support.microsoft.com/help/4493464) 和 [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
> Windows 10版本1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> Windows 10版本1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- 會架[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)和[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) ，以協助修正威脅與弱點管理所找到的威脅。 如果您使用的是 Configuration Manager，請將主控台更新為最新的版本。
    - **附注**：如果您已啟用 intune 連線，您可以在建立修復要求時，取得建立 intune 安全性工作的選項。 如果未設定 connection，則不會顯示此選項。
- 在 [裝置] 頁面中至少有一個可以查看的安全性建議
- 已標記或標示為共同管理

## <a name="relevant-permission-options"></a>相關許可權選項

1. 使用已指派安全性管理員或全域系統管理員角色的帳戶登入 Microsoft Defender 資訊安全中心。
2. 在功能窗格中，選取 [**設定 > 角色**]。

如需詳細資訊，請參閱 [建立及管理以角色為基礎的存取控制角色](user-roles.md)

### <a name="view-data"></a>查看資料

- **安全性作業** -查看入口網站中的所有安全性作業資料
- **威脅及弱點管理**-View 威脅與弱點管理入口網站中的資料

### <a name="active-remediation-actions"></a>主動修正動作

- **安全性作業** -採取回應動作、核准或取消未決修正動作、管理允許/封鎖的自動化和指示器清單
- **威脅及弱點管理例外** 狀況-建立新的例外狀況及管理作用中的例外狀況
- **威脅與弱點管理修正處理**-提交新的修復要求、建立票證，以及管理現有的修復活動

如需詳細資訊，請參閱 [RBAC 許可權選項](user-roles.md#permission-options)

## <a name="related-articles"></a>相關文章

- [威脅與弱點管理概述](next-gen-threat-and-vuln-mgt.md)
- [支援的作業系統和平台](tvm-supported-os.md)
- [指派裝置值](tvm-assign-device-value.md)
- [威脅與弱點管理儀表板](tvm-dashboard-insights.md)

