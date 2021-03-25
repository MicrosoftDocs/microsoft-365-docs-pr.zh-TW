---
title: 使用 Configuration Manager 管理 Microsoft Defender for Endpoint
description: 瞭解如何使用 Configuration Manager 管理 Microsoft Defender for Endpoint
keywords: 遷移後、管理、作業、維護、使用狀況、Configuration Manager、windows defender 高級威脅防護、atp、edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: bd6b6bd2721b686ab10922d09a9e94b9ebcce522
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185644"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>使用 Configuration Manager 管理 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Microsoft Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


建議使用 [microsoft Intune [管理員](https://docs.microsoft.com/mem)] （包括 [Microsoft intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) (Intune) 和 [microsoft endpoint Configuration (管理員](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)) ，以管理組織的威脅防護功能， (也稱為端點) ）。 
- [深入瞭解端點管理員](https://docs.microsoft.com/mem/endpoint-manager-overview)
- [使用 Configuration Manager 和 Intune 在 Windows 10 裝置上共同管理 Microsoft Defender for Endpoint](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>使用 Configuration Manager 設定 Microsoft Defender for Endpoint

|工作  |可深入了解的資源  |
|---------|---------|
|若尚未 **安裝 Configuration Manager 主控台**，請將其安裝<br/><br/>*如果您還沒有設定管理器主控台，請使用這些資源來取得並安裝。* |[取得安裝媒體](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[安裝 Configuration Manager 主控台](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**使用 Configuration Manager 至** Microsoft Defender for Endpoint 的板載裝置 <br/><br/> *如果您有裝置 (或端點) 尚未架至 Microsoft Defender for Endpoint，您可以使用 Configuration Manager 來執行。*   |[使用 Configuration Manager 的 Microsoft Defender for Endpoint 的板載](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|為用戶端電腦 (端點 **管理反惡意程式碼原則和 Windows 防火牆安全性**) <br/><br/>*設定 endpoint protection 功能（包括 Microsoft Defender for Endpoint、exploit protection、application control、反惡意程式碼、防火牆設定等等）。*  |[Configuration Manager： Endpoint Protection](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|選擇在組織裝置上 **更新反惡意軟體更新的方法** <br/><br/>*使用 Configuration Manager 中的 Endpoint Protection 時，您可以選擇數種方式，讓組織裝置上的反惡意軟體定義保持在最新狀態。* |[設定 Endpoint Protection 的定義更新](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[使用 Configuration Manager 傳送定義更新](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**啟用網路保護** ，以協助防止員工在網際網路上使用惡意內容的應用程式 <br/><br/>*我們建議您先在測試環境中使用 [審計模式](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) ，以查看哪些應用程式會封鎖，然後再進行部署。* |[使用 Configuration Manager 開啟網路保護](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**設定受管理的資料夾存取** 權以防護勒索軟體 <br/><br/>*「受管理的資料夾存取」也稱為 antiransomware protection。*   |[Endpoint protection：受控資料夾存取權](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[啟用 Microsoft Endpoint Configuration 管理中的受控資料夾存取](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>設定您的 Microsoft Defender 安全中心

若尚未這麼做，請 **將您的 Microsoft Defender 安全中心設定** ([https://securitycenter.windows.com](https://securitycenter.windows.com)) 以查看提醒、設定威脅防護功能，以及查看組織整體安全性狀況的詳細資訊。 

您也可以設定使用者是否可以在 Microsoft Defender Security Center 中看到哪些功能。

- [Microsoft Defender 安全中心概述](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Endpoint protection： Microsoft Defender 安全中心](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>後續步驟

- [取得威脅和弱點管理的概述](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [流覽 Microsoft Defender Security Center security operations 儀表板](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [使用 Intune 管理 Microsoft Defender for Endpoint](manage-atp-post-migration-intune.md)
