---
title: Microsoft Defender for Endpoint service 的板載非 Windows 裝置
description: 設定非 Windows 裝置，使其可將感應器資料傳送至 Microsoft Defender for Endpoint service。
keywords: 板載非 Windows 裝置，macos，linux，裝置管理，設定 Microsoft Defender for Endpoint 裝置
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
ms.openlocfilehash: 777f5f63c4739f277ec24f826bc8a61a226fb65f
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339667"
---
# <a name="onboard-non-windows-devices"></a>將非 Windows 裝置上線

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**平臺**
- macOS
- Linux

>想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

Defender for Endpoint 可提供 Windows 和非 Windows 平臺的集中式安全性作業體驗。 您可以在 Microsoft 365 Defender 中查看不同支援作業系統 (OS) 中的警示，也能更好地保護組織的網路。 

您將需要知道與 distros 的 Defender for Endpoint 相容的確切 Linux 和 macOS 版本，以供整合運作。 如需詳細資訊，請參閱：
- [Linux 系統需求上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md#system-requirements)  
- [MacOS 系統需求上的 Microsoft Defender For Endpoint](microsoft-defender-endpoint-mac.md#system-requirements)。

## <a name="onboarding-non-windows-devices"></a>上架非 Windows 裝置
您必須對板載非 Windows 裝置採取下列步驟：
1. 選取您慣用的上架方式：

   - 若為 macOS 裝置，您可以選擇透過 Microsoft Defender for Endpoint 或協力廠商解決方案來進行板載。 如需詳細資訊，請參閱 [Mac 上的 Microsoft Defender For Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)。

   - 如果是其他非 Windows 裝置，請 **透過協力廠商整合選擇板載非 Windows 裝置**。   
    1. 在功能窗格中，選取 [**互通性**  >  **夥伴**]。 請確定已列出協力廠商解決方案。
    2. 在 [**夥伴應用程式**] 索引標籤中，選取支援非 Windows 裝置的合作夥伴。
    3. 選取 [ **開啟夥伴頁面** ] 以開啟夥伴的頁面。 依照頁面上提供的指示進行。
    4. 建立帳戶或訂閱夥伴解決方案之後，您應該會進入一個階段，您的組織中的承租人全域管理員要求接受來自夥伴應用程式的許可權要求。 請仔細閱讀許可權要求，確定它已與您所需的服務對齊。 

        
2. 遵循協力廠商解決方案的指示執行偵測測試。

## <a name="offboard-non-windows-devices"></a>下架非 Windows 裝置

1. 遵循協力廠商的檔，以中斷協力廠商解決方案與 Microsoft Defender for Endpoint 的連線。

2. 在您的 Azure AD 租使用者中移除協力廠商解決方案的許可權。
   1. 登入 [Azure 入口網站](https://portal.azure.com)。
   2. 選取 [ **Azure Active Directory > Enterprise 應用程式**]。
   3. 選取您想要下架的應用程式。
   4. 選取 [ **刪除** ] 按鈕。


## <a name="related-topics"></a>相關主題
- [將 Windows 10 裝置上線](configure-endpoints.md)
- [上架伺服器](configure-server-endpoints.md)
- [設定 Proxy 和網際網路連接設定](configure-proxy-internet.md)
- [疑難排解 Microsoft Defender 的端點上架問題](troubleshoot-onboarding.md)
