---
title: 在 Microsoft Defender for Endpoint 中啟用 SIEM 整合
description: Enable SIEM integration 以接收您安全性資訊和事件管理 (SIEM) 解決方案中的偵測。
keywords: 啟用 siem connector、siem、connector、security 資訊和事件
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
ms.openlocfilehash: 87078bb7bfc6b38788fea2a6a4c3c9108be1d5b4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842959"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中啟用 SIEM 整合

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)


>想要體驗適用於端點的 Microsoft Defender 嗎？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink) 

啟用安全性資訊和事件管理 (SIEM) 整合，讓您可以從 Microsoft Defender 資訊安全中心提取偵測。 使用您的 SIEM 解決方案或直接連線至偵測到的 REST API 來提取偵測。

>[!NOTE]
>- [Microsoft Defender For Endpoint Alert](alerts.md) 是由一或多個偵測所組成。
>- [Microsoft Defender For Endpoint 偵測](api-portal-mapping.md) 是由裝置上發生的可疑事件及其相關警示詳細資料所組成。
>- Microsoft Defender for Endpoint Alert API 是最新的警示消耗 API，且包含每個警示的相關證據的詳細清單。 如需詳細資訊，請參閱 [Alert 方法和屬性](alerts.md) 和 [清單警示](get-alerts.md)。

## <a name="prerequisites"></a>必要條件

- 啟用此設定的使用者必須具有在 Azure Active Directory (AAD) 中建立應用程式的許可權。 這是具有下列角色的人員： 

  - 安全性管理員和全域系統管理員
  - 雲端應用程式系統管理員
  - 應用程式系統管理員
  - 服務主體的擁有者

- 在初始啟用期間，會顯示一個彈出畫面，以供輸入認證。 請確定您允許此網站的快顯視窗。

## <a name="enabling-siem-integration"></a>啟用 SIEM 整合 
1. 在功能窗格中，選取 [**設定**  >  **SIEM**]。

    ![SIEM 整合從設定 menu1 的影像](images/enable_siem.png)

    >[!TIP]
    >如果您嘗試啟用 SIEM 連接器應用程式時遇到錯誤，請檢查瀏覽器的快顯封鎖器設定。 當您啟用功能時，它可能會封鎖所開啟的新視窗。 

2. 選取 [ **啟用 SIEM 整合**]。 這會以預先填入的值來啟動 **SIEM connector access 詳細資料** 區段，且應用程式會在您的 Azure Active Directory (Azure AD) 租使用者下建立。

    > [!WARNING]
    >用戶端密碼只會顯示一次。 請確定您將其複本存放在安全的位置。<br>
     

    ![SIEM 整合從設定 menu2 的影像](images/siem_details.png)

3. 選擇您在組織中使用的 SIEM 類型。

   > [!NOTE]
   > 如果您選取 [HP ArcSight]，則需要儲存下列兩個設定檔：<br>
   > - WDATP-connector.jsonparser 屬性
   > - WDATP-連接器。屬性 <br>

   若要透過程式設計存取直接連線至偵測到的 REST API，請選擇 [ **一般 API**]。

4. 複製個別值，或選取 [ **將詳細資料儲存至** 檔案] 以下載包含所有值的檔案。

5. 選取 [ **產生權杖** ]，以取得存取和重新整理權杖。
  
   > [!NOTE]
   > 您需要每90天產生一個新的重新整理權杖。 

6. 依照指示，為 [Microsoft Defender For Endpoint 建立 AZURE AD 應用程式註冊](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp) ，並指派正確的許可權給它，以閱讀提醒。

您現在可以繼續設定 SIEM 解決方案，或透過程式設計存取來連線到偵測的 REST API。 設定 SIEM 解決方案以允許其從 Microsoft Defender 資訊安全中心接收偵測時，您必須使用權杖。

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a>整合 Microsoft Defender for Endpoint with IBM QRadar 
您可以設定 IBM QRadar 從 Microsoft Defender for Endpoint 收集偵測。 如需詳細資訊，請參閱 [IBM 知識中心](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)。

## <a name="see-also"></a>另請參閱
- [設定 HP ArcSight 以拉入 Microsoft Defender for Endpoint 偵測](configure-arcsight.md)
- [Microsoft Defender for Endpoint 偵測欄位](api-portal-mapping.md)
- [使用 REST API 提取 Microsoft Defender for Endpoint 偵測](pull-alerts-using-rest-api.md)
- [為 SIEM 工具整合問題疑難排解](troubleshoot-siem.md)
