---
title: 設定事件中樞
description: 瞭解如何設定事件中樞
keywords: 事件 hub、configure、insights
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985545"
---
# <a name="configure-your-event-hub"></a>設定事件中樞

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用於：**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

瞭解如何設定事件中樞，使其能從 Microsoft 365 Defender 中攝取事件。


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a>在事件 Hub 訂閱中設定必要的資源提供者


1. 登入 [Azure 入口網站](https://portal.azure.com)。
1. 選取 [ **訂閱] \> {***選取事件中心將部署到的訂閱***} \> 資源提供者**。
1. 確認已註冊 **Microsoft Insights** 提供者。 否則，請進行註冊。

![Microsoft Azure 中資源提供者的影像](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a>安裝 Azure Active Directory 應用程式註冊


>!記必須將系統管理員角色或 Azure Active Directory (AAD) 設定為允許非管理員註冊應用程式。 您也必須具有擁有者或使用者存取系統管理員角色，才能指派服務主體角色。  
>如需詳細資訊，請參閱[在入口網站中建立 Azure AD app & 服務主體-Microsoft 身分識別平臺 \| Microsoft](/azure/active-directory/develop/howto-create-service-principal-portal)檔。

1. 建立新的註冊 (，它原本會在 **Azure Active Directory \> 應用程式註冊 \> 新註冊** 中建立服務主體) 。

1. 填寫表單只顯示名稱 (不需要重新導向 URI) 。

    ![註冊應用程式的影像](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![概覽資訊的影像](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. 按一下 [憑證]，以建立機密。 **& 機密的 \> 新用戶端密碼**：

    ![憑證和機密的影像](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
>**您將無法再次存取用戶端密碼，因此請務必加以儲存**。

## <a name="setup-event-hub-namespace"></a>安裝程式事件中心命名空間


1. 建立事件中心命名空間：

    移 **至 [事件 \> 中心** ] [新增]，然後選取 [定價層]、[輸送量單位] 和 [自動增加] (需要符合您期望的負載的標準定價和功能) 。  
    如需詳細資訊，請參閱[定價-事件中樞 \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)

    >[!NOTE]
    > 您可以使用現有的事件中樞，但輸送量和縮放比例是在命名空間層級設定，因此建議您在 itsown 命名空間中放置事件中樞。

   ![事件中樞名稱空間的影像](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. 您也需要此事件 Hub 命名空間的資源識別碼。 移至您的 Azure 事件中心命名空間頁面 \> 屬性。 複製 [資源識別碼] 底下的文字，並將其記錄為在下方的 [M365 設定] 區段中使用。 

    ![屬性圖像](../../media/759498162a4e93cbf17c4130d704d164.png)

1. 在建立事件 Hub 命名空間之後，您將需要將應用程式註冊服務主體新增為 Reader、Azure 事件中樞資料接收器，以及將以投稿者登入 Microsoft 365 Defender 的使用者 (這也可以在資源群組或訂閱層級) 進行。

    這是在 **事件中樞命名空間 \> 存取控制中執行的 \> (IAM)** 在 **角色指派** 下新增及驗證：

    ![存取控制的影像](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a>安裝程式事件 Hub


**選項1：**

您可以在命名空間內建立事件中樞，而且 **所有** 事件種類 (您選取要匯出的表格) 會 **寫入至此事件** hub。

**選項2：**

您可以將每個資料表匯出至事件 Hub 命名空間中的不同事件集，而不是將所有的事件)  (類型匯出至事件 hub 命名空間內， (一個事件 hub 每個事件種類) 。  

在此選項中，Microsoft 365 Defender 將為您建立事件中心。  
>[!NOTE]
> 如果您使用的是 **不** 屬於事件中心叢集的事件中心命名空間，則只有在您定義的每個匯出設定中，只要 Azure 限制每個事件 Hub 命名空間有10個事件中樞，您就可以選擇最多10個事件種類 (表格中) 匯出。

例如：

![範例事件中樞的影像](../../media/005c1f6c10c34420d387f594987f9ffe.png)

如果您選擇此選項，您可以略過 [[設定 Microsoft 365 Defender 以傳送電子郵件表格]](#configure-microsoft-365-defender-to-send-email-tables)區段。

選取 **事件中心 \> + 事件中樞**，以在命名空間中建立事件中樞。

分割區計數可透過平行性增加額外輸送量，因此建議您根據預期的負載增加此數目。  
建議使用預設的郵件保留及捕獲值為1和 Off。

![建立事件中樞的影像](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

若為此事件中樞 (不命名空間) 您將需要使用 Send、聽取宣告來設定共用存取原則。 按一下您的 **事件中心 \> 共用訪問原則 \>** ，然後新增並授與其原則名稱 (未用於其他地方) 並檢查 **傳送** 和 **聆聽**。

![共用存取原則的影像](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>設定傳送電子郵件表格的 Microsoft 365 Defender


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a>安裝程式 Microsoft 365 Defender 透過事件中樞將電子郵件表格傳送至 Splunk


1. <https://security.microsoft.com>使用符合下列所有角色需求的帳戶，登入 Microsoft 365 Defender：

    - 參與者 role，位於事件中心 *命名空間* 資源層級或更高層，以供您要匯出的事件中樞。 若未這麼做，當您嘗試儲存設定時，您會收到匯出錯誤。

    - 受限於 Microsoft 365 Defender 和 Azure 之租使用者的全域系統管理員或安全性系統管理員角色。

    ![安全性入口網站影像](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. 按一下 [ **原始資料匯出 \> + 新增**]。

    現在您會使用以上所記錄的資料。

    **名稱**：這是本機的，應為您環境中的任何作用。

    **將事件轉寄給事件中樞**：選取此核取方塊。

    **事件-Hub 資源識別碼**：這是您在設定事件中樞時所記錄的事件 Hub 命名空間資源識別碼。

    **事件-Hub name**：如果您在事件 Hub 命名空間內建立事件中樞，請貼上您所記錄的事件中心名稱。

    如果您選擇讓 Microsoft 365 Defender 針對每個事件種類建立事件中樞 (表格) 為您，請將此欄位保留空白。

    **事件種類**：選取您要轉寄給事件中樞的高級搜尋表格，然後再移至您的自訂應用程式。 警示表來自 Microsoft 365 Defender，裝置資料表來自 microsoft defender for Endpoint (EDR) ，而電子郵件表格來自 microsoft defender for Office 365。 電子郵件事件會記錄所有的電子郵件交易。 同時也會記錄 SafeLinks) 、附件 (Safe 附件的 URL (及傳遞事件) ，而且可以加入 NetworkMessageId 欄位上的電子郵件事件。

    ![流式處理 API 設定的影像](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. 請務必按一下 [ **提交**]。

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a>驗證事件是否要匯出至事件 Hub


您可以執行基本的高級搜尋查詢，以驗證事件是否已傳送至事件 Hub。 選取 [ **搜尋 \> 高級搜尋 \> 查詢** ]，然後輸入下列查詢：

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

這會顯示最近一小時內加入所有其他表格的電子郵件數目。 如果您看到可匯出至事件中樞的事件，它也會顯示您。 如果此計數顯示0，您將看不到事件 Hub 中的任何資料。

![高級搜尋的影像](../../media/c305e57dc6f72fa9eb035943f244738e.png)

一旦您驗證有要匯出的資料，您就可以查看事件 Hub，以確認郵件已傳入。 這最多可能需要一小時。 
 
1. 在 Azure 中，移至 **事件中樞 \> 按一下 \> \> 事件中樞上的 [命名空間] 事件** 中心。  
1. 在 **[一覽**] 底下，向下並在 [訊息] 圖表中，您應該會看到傳入的郵件。 如果您沒有看到任何結果，則您的自訂應用程式無法接收任何郵件。

    ![包含郵件之 [概覽] 索引標籤的影像](../../media/e88060e315d76e74269a3fc866df047f.png)
