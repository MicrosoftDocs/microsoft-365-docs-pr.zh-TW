---
title: 設定您的 Microsoft 365 Defender 試用版實驗室或試驗環境
description: Access Microsoft 365 資訊安全中心，然後設定您的 Microsoft 365 Defender 試用版實驗室環境
keywords: Microsoft 威脅防護試驗設定、Microsoft 威脅防護試驗設定、試用 Microsoft 威脅防護、Microsoft 威脅防護評估實驗室設定
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932979"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>設定您的 Microsoft 365 Defender 試用版實驗室環境 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


適用於：
- Microsoft 365 Defender 


建立 Microsoft 365 Defender 試用版實驗室或試驗環境並部署此為三階段程式：

|[![階段 1：準備](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[階段 1：準備](prepare-mtpeval.md) |![階段 2：設定](../../media/phase-diagrams/setup.png)<br/>階段 2：設定 |[![階段 3：上機](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[階段 3：上機](config-mtpeval.md) | [![返回試驗](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[回到試驗手冊](mtp-pilot.md) |
|--|--|--|--|
||*您目前在這裡！*  | | |


您目前處於設定階段。 採取存取 Microsoft 365 資訊安全中心的初始步驟，然後設定您的試驗實驗室或試驗環境。

註冊 Office 365 或 Azure Active Directory 訂閱以產生 *.onmicrosoft.com* 租使用者，您可以使用該租使用者註冊您的 Microsoft 365 E5 授權。 

>[!NOTE]
>如果您已經有現有的 Office 365 或 Azure Active Directory 訂閱，您可以略過 Office 365 E5 試用版或試驗租使用者建立步驟。

在這個階段，您將受指引到：
- 建立 Office 365 E5 試用版租使用者
- 啟用 Microsoft 365 試用版訂閱


## <a name="create-an-office-365-e5-trial-tenant"></a>建立 Office 365 E5 試用版租使用者
>[!NOTE]
>如果您已經有現有的 Office 365 或 Azure Active Directory 訂閱，您可以略過 Office 365 E5 試用版租使用者建立步驟。

1. 請前往 [Office 365 E5 產品](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 入口網站，然後選取 **免費試用**。

   ![365 of_Office 365 免費試用版頁面的影像](../../media/mtp-eval-9.png)
  
2. 在個人或公司 (電子郵件地址以完成) 。 按一下 **[設定帳戶**。

   ![365 E5 of_Office註冊設定頁面的圖像](../../media/mtp-eval-10.png)

3. 填入您的名字、姓氏、公司電話號碼、公司名稱、公司大小，以及國家/地區。  

   ![影像of_Office 365 E5 試用版註冊設定頁面，詢問名稱、電話和公司詳細資料](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > 您在這裡設定的國家/地區或區域會決定您的 Office 365 將託管的資料中心區域。
  
4. 選擇您的驗證喜好設定：透過文字訊息或通話。 按一下 **[傳送驗證碼**。 

   ![要求of_Office 365 E5 試用版註冊設定頁面的圖像](../../media/mtp-eval-12.png)

5. 設定租使用者自訂功能變數名稱，然後按一下 [下一 **步**。

   ![可在 of_Office 365 E5 試用版註冊設定頁面設定自訂功能變數名稱的影像](../../media/mtp-eval-13.png)
 
6. 設定第一個身分識別，該身分識別即為租使用者全域系統管理員。 填入 **名稱和****密碼**。 按一下 **[註冊**。

   ![可在 of_Office 365 E5 試用版註冊設定頁面設定商務身分識別的影像](../../media/mtp-eval-14.png)

7. 按一下 **[前往設定** 以完成 Office 365 E5 試用版租使用者設定。

   ![Office 365 E5 試用版註冊設定頁面的影像，提示您按一下 [執行設定按鈕](../../media/mtp-eval-15.png)

8. 將您的公司網域連接到 Office 365 租使用者。 [選擇性]選擇 **連接您已有的網域** ，然後輸入您的功能變數名稱。 按 **[下一步]**。

   ![365 of_Office 365 設定頁面的影像，您應該在這裡個人化您的登錄和電子郵件](../../media/mtp-eval-16.png)
 
9. 新增 TXT 或 MX 記錄以驗證網域擁有權。 一旦將 TXT 或 MX 記錄新增到您的網域後， **請選取驗證**。

   ![<of_Office 365 E5 設定頁面的圖像，您應該在這裡新增 MX 記錄的 TXT 以驗證您的網域](../../media/mtp-eval-17.png)
 
10. [選擇性]為租使用者建立更多使用者帳戶。 您可以按一下下一步來跳過 **此步驟**。

    ![可在 of_Office 365 E5 設定頁面新增更多使用者的影像](../../media/mtp-eval-18.png)
 
11. [選擇性]下載 Office App。 按一下 **[下一** 步， 略過此步驟。 

    ![可在 of_Office 365 E5 頁面安裝 Office 應用程式的影像](../../media/mtp-eval-19.png)

12. [選擇性]遷移電子郵件訊息。 同樣，您可以略過此步驟。

    ![圖像of_Office 365 E5 中，您可以在這裡設定是否要要遷移電子郵件訊息](../../media/mtp-eval-20.png)
 
13. 選擇線上服務。 選取 **Exchange，** 然後按一下 [下 **一步**。 

    ![可在 of_Office 365 E5 選擇線上服務的影像](../../media/mtp-eval-21.png)

14. 新增 MX、CNAME 和 TXT 記錄至您的網域。 完成後， **請選取驗證**。

    ![您可以在of_Office 365 E5 中新增 DNS 記錄的影像](../../media/mtp-eval-22.png)
 
15. 恭喜您，您已完成您的 Office 365 租使用者提供。

    ![365 E5 of_Office確認頁面的圖像](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>啟用 Microsoft 365 試用版訂閱

>[!NOTE]
>註冊試用版可給您 25 個使用者授權，一個月可以使用。 請參閱 [試用或購買 M365 訂閱以](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) 瞭解詳細資料。

1. 從 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)，按一下 [ **帳單** ，然後流覽至 **購買服務**。

2. 選取 **Microsoft 365 E5，** 然後按一下 [ **開始免費試用**。 

   ![365 of_Microsoft 365 開始免費試用頁面的圖像](../../media/mtp-eval-24.png)

3. 選擇您的驗證喜好設定：透過文字訊息或通話。 一旦決定好後，請輸入電話號碼，**然後根據您的選擇** 選取範圍選取給我或撥打給我。

   ![影像of_Microsoft 365 E5 開始免費試用頁面，要求聯絡人詳細資料以傳送驗證碼以證明您不是機器人](../../media/mtp-eval-25.png)
 
4. 輸入驗證碼，然後按一下 **[開始免費試用**。

   ![圖像of_Microsoft 365 E5 開始免費試用頁面，您可以在此填寫系統為了證明您不是機器人而送出驗證碼](../../media/mtp-eval-26.png)

5. 按一下 **[立即試用** 以確認您的 Microsoft 365 E5 試用版。

   ![影像of_Microsoft 365 E5 開始免費試用頁面，您應該在此頁面打卡以開始試用](../../media/mtp-eval-27.png)
 
6. 請前往 **Microsoft 365 系統管理中心**  >  **使用者**  >  **主動使用者**。 選取您的使用者帳戶，選取 **管理產品** 授權，然後將授權從 Office 365 E5 切換至 **Microsoft 365 E5。** 按一下 **[儲存]**。

   ![可在 of_Microsoft 365 系統管理中心頁面選取 Microsoft 365 E5 授權的圖像](../../media/mtp-eval-28.png)
 
7. 再次選取全域系統管理員帳戶，然後按一下 [ **管理使用者名稱**。

   ![可在 of_Microsoft 365 系統管理中心頁面選取帳戶，然後管理使用者名稱的影像](../../media/mtp-eval-29.png)

8. [選擇性]根據您在onmicrosoft.com選擇哪些專案，將網域從新網域變更為您自己的網域。 按一下 **[儲存變更]**。

   ![可在 of_Microsoft 365 系統管理中心頁面變更網域喜好設定的圖像](../../media/mtp-eval-30.png)



## <a name="next-step"></a>下一步
|[階段 3：設定&上](config-mtpeval.md) | 針對您的 Microsoft 365 Defender 試用版實驗室或試驗環境設定每個 Microsoft 365 Defender 基礎，並設置端點。
|:-------|:-----|
