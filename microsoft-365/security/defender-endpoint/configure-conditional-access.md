---
title: 在 Microsoft Defender ATP 中設定條件式存取
description: 深入瞭解在 Intune、Microsoft Defender Security Center 和 Azure 中執行條件式存取所需的步驟
keywords: 條件式存取、條件化、存取、裝置風險、風險層級、整合、intune 整合
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
ms.openlocfilehash: 0185d7875ac149909ef088d041383a1cf36a8a3a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165858"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中設定條件式存取

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

本節會引導您完成所有必須執行的步驟，才能正確地執行條件式存取。

### <a name="before-you-begin"></a>開始之前
>[!WARNING]
>請務必注意，此案例中不支援 Azure AD 註冊裝置。</br>
>只支援 Intune 註冊的裝置。


您必須確定您的所有裝置都已在 Intune 中註冊。 您可以使用下列任何選項，在 Intune 中註冊裝置：


- IT 系統管理員：如需如何啟用自動註冊的詳細資訊，請參閱 [Windows 註冊](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- 使用者：如需如何在 Intune 中註冊 Windows 10 裝置的詳細資訊，請參閱 [在 intune 中註冊您的 windows 10 裝置](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)
- 使用者替代：如需有關加入 Azure AD 網域的詳細資訊，請參閱 how [to： Plan a AZURE ad join 實現](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)。



在 Microsoft Defender 安全中心、Intune 入口網站和 Azure AD 入口網站中，您必須採取下列步驟。

請務必注意存取這些入口網站所需的角色，並執行條件式存取：
- **Microsoft Defender 安全中心** -您必須以全域系統管理員角色登入入口網站，才能開啟整合。
- **Intune** -您必須使用具有管理許可權的安全性系統管理員許可權登入入口網站。 
- **AZURE AD 入口網站** -您必須以全域系統管理員、安全性管理員或條件式存取管理員身分登入。


> [!NOTE]
> 您將需要 Microsoft Intune 環境（Intune managed 和 Azure AD 加入的 Windows 10 裝置）。

請執行下列步驟來啟用條件式存取：
- 步驟1：從 Microsoft Defender 安全中心開啟 Microsoft Intune 連線
- 步驟2：在 Intune 中開啟用於端點整合的 Defender
- 步驟3：在 Intune 中建立相容性原則
- 步驟4：指派原則 
- 步驟5：建立 Azure AD 條件式存取原則


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>步驟1：開啟 Microsoft Intune 連線
1. 在功能窗格中，選取 [**設定**  >  **高級功能**] [  >  **Microsoft Intune connection**]。
2. 將 Microsoft Intune 設定切換為 [ **開啟**]。
3. 按一下 [ **儲存喜好** 設定]。


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>步驟2：在 Intune 中開啟用於端點整合的 Defender
1. 登入 [Azure 入口網站](https://portal.azure.com)。
2. 選取 [**裝置規範**] [  >  **Microsoft Defender ATP**]。
3. 將 **[連線 Windows 10.0.15063 + 裝置至 Microsoft Defender 高級威脅防護]** 設定為 [ **開啟**]。
4. 按一下 **[儲存]**。


### <a name="step-3-create-the-compliance-policy-in-intune"></a>步驟3：在 Intune 中建立相容性原則
1. 在 [Azure 入口網站](https://portal.azure.com)中，選取 [ **所有服務**]、[在 **Intune** 上篩選]，然後選取 [ **Microsoft Intune**]。
2. 選取 [**裝置規範**  >  **原則**] [  >  **建立原則**]。
3. 輸入 **名稱** 和 **描述**。
4. 在 [ **平臺**] 中，選取 [ **Windows 10 和更新版本**]。
5. 在 [ **裝置健康情況** 設定] 中，設定 **[要求裝置位於或低於裝置威脅層級** ] 的首選層級：

   - **安全**：這是最安全的層級。 裝置不能有任何現有威脅，但仍然可以存取公司資源。 如果找到任何威脅，裝置就會評估為不相容。
   - **Low**：只有低層級威脅存在時，裝置才符合。 具有中低或高威脅層級的裝置不相容。
   - **中**：如果裝置上所發現的威脅為低或適中，裝置就符合。 如果偵測到高層級威脅，裝置會決定為不相容。
   - **High**：此層級是最低的安全性，可允許所有威脅層級。 因此，具有高、中度或低威脅層級的裝置會被視為相容性。

6. 選取 **[確定]**，並 **建立** 以儲存變更 (並建立) 原則。

### <a name="step-4-assign-the-policy"></a>步驟4：指派原則
1. 在 [Azure 入口網站](https://portal.azure.com)中，選取 [ **所有服務**]、[在 **Intune** 上篩選]，然後選取 [ **Microsoft Intune**]。
2. 選取 **裝置符合性**  >  **原則**> 選取您的 Microsoft Defender ATP 相容性原則。
3. 選取 [作業 **]**。
4. 包含或排除 Azure AD 群組，以指派原則。
5. 若要將原則部署至群組，請選取 [ **儲存**]。 原則所針對的使用者裝置會根據規範評估。

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>步驟5：建立 Azure AD 條件式存取原則
1. 在 [azure 入口網站](https://portal.azure.com)中，開啟 **Azure Active Directory**  >  **條件式存取**  >  **新原則**。
2. 輸入原則 **名稱**，然後選取 [ **使用者和群組**]。 使用 [包含] 或 [排除] 選項新增原則的群組，然後選取 [ **完成**]。
3. 選取 [ **Cloud app**]，然後選擇要保護的應用程式。 例如，選擇 [ **選取應用程式**]，然後選取 [ **Office 365 SharePoint 線上** 和 **office 365 Exchange Online**。 選取 **[完成]** 以儲存變更。

4. 選取  >  [**用戶端應用程式**] 以將原則套用至應用程式和瀏覽器的條件。 例如，選取 **[是]**，然後啟用 **瀏覽器** 和行動 **應用程式及桌面用戶端**。 選取 **[完成]** 以儲存變更。

5. 根據裝置符合性，選取 **[授** 與套用條件式存取]。 例如，選取 **[授與存取權**]  >  **需要將裝置標示為相容**。 選擇 [ **選取** ] 以儲存變更。

6. 選取 [ **啟用原則**]，然後 **建立** 以儲存變更。

如需詳細資訊，請參閱 [在 Intune 中使用條件式存取啟用 Microsoft DEFENDER ATP](https://docs.microsoft.com/intune/advanced-threat-protection)。

>想要體驗 Defender for Endpoint？ [註冊免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
