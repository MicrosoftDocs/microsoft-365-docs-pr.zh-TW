---
title: 部署 Windows 10 企業版作為就地升級的現有裝置
description: 提供使用 Microsoft 端點設定管理員設定及部署 Windows 10 企業版映射的指導方針做為就地升級。
keywords: Microsoft 365，Microsoft 365 企業版，Microsoft 365 檔，Windows 10 企業版，部署，就地升級，Configuration Manager，Configuration Manager
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 1c90640fa49aa102d2a4c8420feedf659b5682f2
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011814"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>步驟2：將現有裝置的 Windows 10 企業版部署為就地升級

*本文適用于 Microsoft 365 企業版的 E3 和 E5 版本*

![階段 3：Windows 10 企業版](../media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

將目前執行 Windows 7 或 Windows 8.1 之電腦升級至 Windows 10 的最簡單途徑是透過就地升級。 您可以使用 Configuration Manager （Configuration Manager）任務順序，以完全自動化處理常式。 

如果您有現有的電腦正在執行 Windows 7 或 Windows 8.1，建議您在組織部署 Windows 10 時，建議使用此路徑。 這會利用 Windows 安裝程式（setup.exe）執行就地升級，這會自動保留現有作業系統版本中的所有資料、設定、應用程式及驅動程式。 這需要最少的 IT 工作，因為不需要任何複雜的部署基礎結構。

請遵循下列步驟，使用 Microsoft 端點 Configuration Manager 做為就地升級，以設定及部署 Windows 10 企業版映射。

## <a name="the-windows-10-deployment-with-configuration-manager-poster"></a>使用 Configuration Manager 的 Windows 10 部署海報

在橫向模式（17x11）中，Configuration Manager 海報是一個頁面。 按一下下方的圖像以在瀏覽器中查看 PDF。 

[![使用 Configuration Manager 海報部署 Windows 10](../media/windows10-deploy-inplaceupgrade/windows10-deployment-config-manager.png)](https://docs.microsoft.com/windows/deployment/media/Windows10DeploymentConfigManager.pdf)

您也可以以 [PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.pdf) 或 [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.vsdx) 格式下載此海報。

## <a name="part-1-verify-readiness-to-upgrade-windows"></a>第1部分：確認升級 Windows 的準備工作

首先，使用 Windows Analytics 的升級準備工作功能，針對組織中的電腦、應用程式和驅動程式提供強大的洞察力和建議，不需要額外的成本，也沒有其他基礎結構需求。 這項新服務會引導您使用以 Microsoft 建議的做法為基礎的工作流程升級和功能更新專案。 最新的庫存資料可讓您在升級專案中平衡成本和風險。

請參閱使用升級準備以深入瞭解、開始、使用及疑難排解升級準備工作中[的「管理 Windows 升級](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness)」。

接下來，遵循下列指南以使用 Configuration Manager （目前的分支）將 Windows 7 或更新版本的作業系統升級至 Windows 10。 就像任何高風險部署一樣，我們建議先備份使用者資料，然後再繼續進行。 OneDrive 雲端儲存已準備好用於授權的 Microsoft 365 使用者，而且可用於安全地儲存其檔案。 如需詳細資訊，請參閱[OneDrive 快速入門手冊](https://aka.ms/ODfBquickstartguide)。 若要存取此頁面，您必須以承租人系統管理員或全域管理員身分登入 Office 365 或 Microsoft 365 租使用者。

如需支援的 Configuration Manager 版本和對應的 Windows 10 用戶端版本清單，請參閱[Support For Configuration Manager 的 windows 10](https://docs.microsoft.com/mem/configmgr/core/plan-design/configs/support-for-windows-10)。

**若要驗證升級 Windows 的準備工作**

開始 Windows 10 部署之前，請先複查這些需求：

- **適用于升級的 windows 版本**-您的裝置必須執行可升級至 Windows 10 企業版的 windows 7 或 windows 8.1 版本。 如需支援的版本清單，請參閱[Windows 10 升級路徑](https://aka.ms/win10upgradepaths)。 
- **支援的裝置**-與 windows 8.1 相容的大部分電腦都會與 windows 10 相容。 您可能需要在 Windows 10 中安裝更新的驅動程式，裝置才能正常運作。 如需詳細資訊，請參閱[Windows 10 規格](https://aka.ms/windows10specifications)。
- **部署準備**-開始設定部署之前，請先確認下列事項：
    - Windows 10 安裝媒體-安裝媒體必須位於不同的磁片磁碟機上，且已安裝了 ISO。 您可以從「 [MSDN 訂戶下載](https://aka.ms/msdn-subscriber-downloads)」或「[大量授權服務中心](https://aka.ms/mvlsc)」取得 ISO。
    - 備份使用者資料-雖然使用者資料會在升級時進行遷移，但最佳作法是設定備份案例。 例如，將所有使用者資料匯出至 OneDrive 帳戶，BitLocker 為「已加密的 USB 快閃記憶體磁片磁碟機」或「網路檔案伺服器」。 如需詳細資訊，請參閱[在 Windows 中備份或傳輸資料](https://aka.ms/backuptransferdatawindows)。
- **環境準備**-您將使用現有的 Configuration Manager 伺服器結構來準備作業系統部署。 除了基本設定之外，還應該在 Configuration Manager 環境中進行下列設定：
    1. [擴充 Active Directory 架構](https://aka.ms/extendadschema)，並[建立系統管理容器](https://aka.ms/createsysmancontainer)。
    2. 啟用 Active Directory 樹系探索和 Active Directory 系統探索。 如需詳細資訊，請參閱[Configure Configuration Manager 的探索方法](https://aka.ms/configurediscoverymethods)。
    3. 建立內容和網站指派的 IP 範圍界限和邊界群組。 如需詳細資訊，請參閱[定義網站界限和設定管理員的邊界群組](https://aka.ms/definesiteboundaries)。
    4. 新增及設定 Configuration Manager reporting services 點角色。 如需詳細資訊，請參閱[在 Configuration Manager 中設定報告](https://aka.ms/configurereporting)。
    5. 為套件建立檔系統資料夾結構。
    6. 建立套件的 Configuration Manager 主控台資料夾結構。
    7. 安裝 Configuration Manager （目前分支）更新及其他任何 Windows 10 先決條件。

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a>第2部分：使用 Configuration Manager 新增 Windows 10 OS 映射
現在，您需要建立包含完整 Windows 10 安裝媒體的作業系統升級套件。 在下列步驟中，您將使用 Configuration Manager 建立 Windows 10 企業版 x64 的升級套件。

**使用 Configuration Manager 新增 Windows 10 OS 映射**

1. 使用 Configuration Manager 主控台，在 [**軟體庫**] 工作區中，以滑鼠右鍵按一下 [**作業系統升級套件**] 節點，然後選取 [**新增作業系統升級套件**]。
2. 在 [**資料來源**] 頁面上，指定 Windows 10 Enterprise x64 媒體的 UNC 路徑，然後選取 **[下一步]**。
3. 在 [**一般**] 頁面上，指定**Windows 10 Enterprise x64 Upgrade**，然後選取 **[下一步]**。 
4. 在 [**摘要**] 頁面上，選取 **[下一步]**，然後選取 [**關閉**]。 
5. 以滑鼠右鍵按一下建立的**Windows 10 Enterprise X64 更新**套件，然後選取 [**散佈內容**]。 
6. 選擇您的發佈點。

## <a name="part-3-configure-deployment-settings"></a>第3部分：設定部署設定
在這個步驟中，您將設定包含 Windows 10 升級設定的升級任務順序。 接著，您會識別要升級的裝置，然後將任務順序部署至這些裝置。

### <a name="create-a-task-sequence"></a>建立任務順序
若要建立升級任務順序，請執行下列步驟：
  
1. 在 Configuration Manager 主控台中，展開 [**軟體庫**] 工作區中的 [**作業系統**]。 
2. 在 [**任務順序**] 節點上按一下滑鼠右鍵，然後選取 [**建立任務順序**]。
3. 在 [**建立新的任務順序**] 頁面上，選取 [**從升級套件升級作業系統**]，然後選取 **[下一步]**。
4. 在 [**任務順序資訊**] 頁面上，指定**Windows 10 Enterprise x64 Upgrade**，然後選取 **[下一步]**。
5. 在 [**升級 Windows 作業系統**] 頁面上，選取 **[流覽]** ，然後選擇 [ **windows 10 Enterprise x64 升級作業系統升級] 套件**，選取 **[確定**]，然後選取 **[下一步**]。
6. 繼續執行剩下的嚮導頁面，然後選取 [**關閉**]。

### <a name="create-a-device-collection"></a>建立裝置集合
在您建立升級工作順序之後，您將需要建立包含您要升級之裝置的集合。

> [!NOTE]
> 使用下列設定來測試單一裝置上的部署。 當您準備就緒時，您可以使用不同的成員資格規則來包括裝置群組。 如需詳細資訊，請參閱[如何在 Configuration Manager 中建立集合](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/create-collections)。

1. 在 Configuration Manager 主控台中，于 [**資產與規範**] 工作區中，以滑鼠右鍵按一下 [**裝置集合**]，然後選取 [**建立裝置集合**]。 
2. 在 [建立裝置集合] 嚮導的 **[一般**] 頁面上，輸入下列設定，然後選取 **[下一步]**：
    - 名稱： Windows 10 企業版 x64 升級
    - 限制集合：所有系統
3. 在 [**成員資格規則**] 頁面上，選取 [ **Add rule** > **Direct rule** ] 以啟動 [建立直接成員資格規則] 嚮導。
4. 在 [建立直接成員資格規則] 嚮導的 [**歡迎**] 頁面上，選取 **[下一步**]。
5. 在 [**搜尋資源**] 頁面上，輸入下列設定，並將預留位置**值**文字取代為您要升級的裝置名稱： 
    - Resource 類別：系統資源
    - 屬性名稱： Name
    - 值： *PC0003*
6. 在 [**選取資源**] 頁面上，選取您的裝置，然後選取 **[下一步]**。
7. 完成 [建立直接成員資格規則] 嚮導和 [建立裝置集合] 嚮導。  
8. 複查 Windows 10 企業版 x64 升級集合。 在您看到您在集合中新增的機器之前，請勿繼續。

### <a name="create-an-operating-system-deployment"></a>建立作業系統部署
請遵循下列步驟建立任務順序的部署。

1. 在 Configuration Manager 主控台的 [**軟體庫**] 工作區中，以滑鼠右鍵按一下您在上一個步驟中建立的任務順序，然後選取 [**部署**]。
2. 在 [**一般**] 頁面上，選取**Windows 10 Enterprise x64 升級**集合，然後選取 **[下一步]**。
3. 在**內容**頁面上，選取 **[下一步]**。
4. 在 [**部署設定**] 頁面上，選取下列設定，然後選取 **[下一步]**：

    > [!NOTE]
    > 針對此測試部署，您會將目的設定為 [**可用**]，這需要使用者干涉才能啟動部署。 在實際執行環境中，您可能想要使用必要的目的來自動化部署，這包括設定其他選項（例如，在執行部署時排程）。 

    - 動作：安裝
    - 目的：可用

5. 在 [**排程**] 頁面上，接受預設設定，然後選取 **[下一步]**。
6. 在 [**使用者經驗**] 頁面上，接受預設設定，然後選取 **[下一步]**。
7. 在 [**提醒**] 頁面上，接受預設設定，然後選取 **[下一步]**。
8. 在 [**摘要**] 頁面上，選取 **[下一步]**，然後選取 [**關閉**]。

## <a name="part-4-start-the-windows-10-upgrade-task-sequence"></a>第4部分：啟動 Windows 10 升級任務順序
請遵循下列步驟，在您要升級的裝置上啟動 Windows 10 升級工作順序。
 
1. 登入 [Windows 電腦]，然後啟動**軟體中心**。
2. 選取您在上一個步驟中建立的任務順序，然後選取 [**安裝**]。
3. 當任務順序開始時，它會自動初始化就地升級程式，方法是使用必要的命令列參數來呼叫 Windows 安裝程式（Setup.exe），以執行自動升級，以保留所有資料、設定、應用程式及驅動程式。
4. 工作順序成功完成後，電腦將會完整升級至 Windows 10。

如果您在企業環境中使用 Windows 10 時遇到問題，可以參考[最常見的 Microsoft 支援解決方案，以取得最常見的問題](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions)。 這些資源包括 KB 文章、更新及文件庫文章。

在整個組織中部署更新的過程中，請使用 Windows Analytics 的更新合規性功能，為 Windows 10 裝置提供完整的作業系統更新規範、更新部署進度和失敗疑難排解的視圖。 此新服務使用診斷資料（包括安裝進度、Windows Update 設定及其他資訊），以提供這類洞察力，不需要額外成本，也不需要其他基礎結構需求。 不論它是用於商務用 Windows 更新或其他管理工具，您都可以保證您的裝置已正確更新。

請參閱[監視 Windows 更新和具有更新規範的 Windows Defender 防毒軟體](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor)，以深入瞭解、快速入門及使用更新規範。

作為過渡期的檢查點，您可以看到此步驟的[允出準則](windows10-exit-criteria.md#crit-windows10-step2)。

## <a name="next-step"></a>下一步

|||
|:-------|:-----|
|![步驟 3](../media/stepnumbers/Step3.png)| [使用 Windows Autopilot 為新裝置部署 Windows 10 企業版](windows10-deploy-autopilot.md) |
