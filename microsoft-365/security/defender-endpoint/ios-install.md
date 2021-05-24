---
title: 在 iOS 上以應用程式為基礎的 Microsoft Defender for Endpoint 部署
ms.reviewer: ''
description: 說明如何使用應用程式在 iOS 上部署 Microsoft Defender for Endpoint
keywords: microsoft，defender，Microsoft Defender for Endpoint，ios，應用程式，安裝，部署，卸載，intune
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6f2b9a1365a27bb7397aea51dcd5bc9e2631afe2
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624702"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a>在 iOS 上部署 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [適用於端點的 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要體驗 Defender for Endpoint？ [注册免費試用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

本主題說明如何在 Intune 公司入口網站註冊的裝置上的 iOS 上為端點部署 Defender。 如需 Intune 裝置註冊的詳細資訊，請參閱 [在 intune 中註冊 iOS/iPadOS 裝置](/mem/intune/enrollment/ios-enroll)。

## <a name="before-you-begin"></a>開始之前

- 確定您可以存取 [Microsoft 端點管理員管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。

- 確定已為您的使用者執行 iOS 註冊。 使用者必須具有指派的 Defender for Endpoint 授權，才能在 iOS 上使用 Defender for Endpoint。 如需指派授權的相關指示，請參閱 [指派授權給使用者](/azure/active-directory/users-groups-roles/licensing-groups-assign) 。

> [!NOTE]
> 現在，您可以在 [Apple App Store](https://aka.ms/mdatpiosappstore)中使用 iOS 上的 Microsoft Defender for Endpoint。

## <a name="deployment-steps"></a>部署步驟

透過 Intune 公司入口網站在 iOS 上為端點部署 Defender。

### <a name="add-ios-store-app"></a>新增 iOS 儲存應用程式

1. 在 [Microsoft 端點](https://go.microsoft.com/fwlink/?linkid=2109431)管理員系統管理中心中，移至 [**應用**  ->  **iOS/iPadOS**] [  ->  **新增**  ->  **iOS 儲存應用程式**]，然後按一下 [**選取**]。

    > [!div class="mx-imgBorder"]
    > ![Microsoft 端點管理員系統管理 Center1 的影像](images/ios-deploy-1.png)

1. 在 [新增應用程式] 頁面上，按一下 [ **搜尋應用程式存放區** ]，然後在搜尋列中輸入 **Microsoft Defender 端點** 。 在 [搜尋結果] 區段中，按一下 [ *Microsoft Defender 端點* ]，然後按一下 [ **選取**]。

1. 選取 [ **iOS 11.0** ] 做為最小作業系統。 查看應用程式的其餘資訊，然後按 **[下一步]**。

1. 在 [ *工作分派* ] 區段中，移至 [ **必要** ] 區段，然後選取 [ **新增群組**]。 然後，您可以選擇 (s) 上的使用者群組，以 iOS app 上的 Defender for Endpoint。 按一下 [**選取**]，然後按一下 **[下一步]**

    > [!NOTE]
    > 選取的使用者群組應該包含 Intune 登記的使用者。

    > [!div class="mx-imgBorder"]
    > ![Microsoft 端點管理員系統管理 Center2 的影像](images/ios-deploy-2.png)

1. 在 [ *複查 + 建立* ] 區段中，確認輸入的所有資訊正確無誤，然後選取 [ **建立**]。 在幾分鐘內，應順利建立端點應用程式，並且在頁面的右上角應該會顯示通知。

1. 在顯示的 [應用程式資訊] 頁面中，選取 [ **監視** ] 區段中的 [ **裝置安裝狀態** ]，以確認裝置安裝已成功完成。

    > [!div class="mx-imgBorder"]
    > ![Microsoft 端點管理員系統管理 Center3 的影像](images/ios-deploy-3.png)

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a>自動載入 VPN 設定檔 (簡化型架) 

> [!NOTE]
> 自動-載入 VPN 設定檔目前正在預覽中，此區段中所述的步驟在正式發行之前，可能會受到大量修改。

系統管理員可以設定 VPN 設定檔的自動設定。 這會自動設定 Defender for Endpoint VPN 設定檔，而不需要使用者在上架時執行此作業。 請注意，使用 VPN 是為了提供 Web 保護功能。 這不是一般 VPN，也就是本機/自我迴圈的 VPN，不會對裝置以外的流量進行流量。

1. 在 [Microsoft 端點](https://go.microsoft.com/fwlink/?linkid=2109431)管理員系統管理中心中，移至 [**裝置** 設定配置  ->  **檔**  ->  **建立設定檔**]。
1. 選擇 [ **平臺** 為 **iOS/iPadOS** ] 和 [ **配置檔案類型** 為 **VPN**]。 按一下 ****[建立]。
1. 輸入設定檔的名稱，然後按 **[下一步]**。
1. 選取 [連線類型的 **自訂 VPN** ]，然後在 [ **基礎 VPN** ] 區段中，輸入下列專案：
    - Connection Name = Microsoft Defender for Endpoint
    - VPN 伺服器位址 = 127.0.0。1
    - Auth 方法 = 「使用者名稱與密碼」
    - 分割隧道 = 停用
    - VPN 識別碼 = scmx
    - 在 [索引鍵-值] 組中，輸入機碼 **AutoOnboard** ，然後將值設定為 **True**。
    - 自動 VPN 的類型 = 隨選 VPN
    - 針對 [**需求規則**] 按一下 [**新增**]，然後選取 **[我想要建立 VPN**]，**我想要限制為 [所有網域**]。

    ![VPN 設定檔設定的螢幕擷取畫面](images/ios-deploy-8.png)

1. 按 [下一步] 並將設定檔指派給目標使用者。
1. 在 [ *複查 + 建立* ] 區段中，確認輸入的所有資訊正確無誤，然後選取 [ **建立**]。

## <a name="complete-onboarding-and-check-status"></a>完成上架和支票狀態

1. 一旦裝置上已安裝 iOS 的 Endpoint for Endpoint，您就會看到應用程式圖示。

    ![自動產生之智慧型電話描述的螢幕擷取畫面](images/41627a709700c324849bf7e13510c516.png)

2. 點擊 [Defender for Endpoint app] 圖示，然後依照螢幕指示完成上架步驟。 詳細資料包括 iOS 使用者接受 iOS 上的 Defender for Endpoint 所需的許可權。

3. 成功上架後，裝置會在 Microsoft Defender 資訊安全中心中的 [裝置] 清單上開始顯示。

    > [!div class="mx-imgBorder"]
    > ![自動產生之儲存格電話描述的螢幕擷取畫面](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a>針對監督模式設定 Microsoft Defender for Endpoint

在 iOS 應用程式上的 Microsoft Defender for Endpoint 具有 iOS/iPadOS 裝置的特殊能力，但前提是這些裝置類型的平臺已增加管理功能。 若要利用這些功能，終結點應用程式必須知道裝置是否處於監督模式。

### <a name="configure-supervised-mode-via-intune"></a>透過 Intune 設定監督模式

Intune 可讓您透過應用程式設定原則設定 iOS 應用程式的 Defender。

   > [!NOTE]
   > 受監視裝置的此應用程式設定原則只適用于受管理的裝置，而且應針對所有受管理的 iOS 裝置做為最佳作法。

1. 登入 Microsoft 端點管理員系統 [管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，然後移至 [**新增應用** 程式] 設定  >  **原則**  >  ****。 按一下 [ **受管理的裝置**]。

    > [!div class="mx-imgBorder"]
    > ![Microsoft 端點管理員系統管理 Center4 的影像](images/ios-deploy-4.png)

1. 在 [ *建立應用程式佈建原則* ] 頁面中，提供下列資訊：
    - 原則名稱
    - 平臺： Select iOS/iPadOS
    - 目標應用程式：從清單中選取 **Microsoft Defender ATP**

    > [!div class="mx-imgBorder"]
    > ![Microsoft 端點管理員系統管理 Center5 的影像](images/ios-deploy-5.png)

1. 在下一個畫面中，選取 [ **使用 configuration designer** 做為格式]。 指定下列屬性：
    - 設定機碼： issupervised
    - 數值型別：字串
    - 設定值： {{issupervised}}
    
    > [!div class="mx-imgBorder"]
    > ![Microsoft 端點管理員系統管理 Center6 的影像](images/ios-deploy-6.png)

1. 按 **[下一步]** 開啟 [ **範圍標記** ] 頁面。 範圍標記是選用的。 按 **[下一步]** 繼續。

1. 在 [ **工作分派** ] 頁面上，選取將要接收此設定檔的群組。 針對此案例，最佳作法是針對 **所有裝置**。 如需指派設定檔的詳細資訊，請參閱 [指派使用者和裝置設定檔](/mem/intune/configuration/device-profile-assign)。

   部署至使用者群組時，使用者必須先登入裝置，然後才能套用原則。

   按 [下一步 **]**。

1. 當您完成時，請在 [ **複查 + 建立** ] 頁面上，選擇 [ **建立**]。 新的設定檔會顯示在設定檔的清單中。

1. 接下來，針對增強型防網路釣魚功能，您可以在監督的 iOS 裝置上部署自訂設定檔。 請遵循下列步驟：
    - 從下載設定檔 [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)
    - 流覽至 **裝置**  ->  **iOS/iPadOS** 設定配置  ->  **檔**  ->  **建立設定檔**

    > [!div class="mx-imgBorder"]
    > ![Microsoft 端點管理員系統管理 Center7 的影像](images/ios-deploy-7.png)

    - 提供設定檔的名稱。 當系統提示您匯入設定設定檔檔案時，請選取上述下載的檔案。
    - 在 [ **工作分派** ] 區段中，選取您要套用此設定檔的裝置群組。 最佳作法是將此套用至所有受管理的 iOS 裝置。 按 [下一步 **]**。
    - 當您完成時，請在 [ **複查 + 建立** ] 頁面上，選擇 [ **建立**]。 新的設定檔會顯示在設定檔的清單中。

## <a name="next-steps"></a>後續步驟

[設定 iOS 功能上的端點的 Defender](ios-configure-features.md)
