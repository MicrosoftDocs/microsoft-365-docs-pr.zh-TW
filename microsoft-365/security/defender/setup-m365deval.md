---
title: 設定您的 Microsoft 365 Defender 試用實驗室或試驗環境
description: Access Microsoft 365 的安全性中心，然後設定 Microsoft 365 Defender 試用實驗室環境
keywords: Microsoft 365 Defender 試用設定，請 Microsoft 365 Defender 試點設定，嘗試 Microsoft 365 Defender，Microsoft 365 Defender 評估實驗室安裝程式
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6db3003aa6465df90a3d2e4af55b28ccccf44100
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454730"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a>在實驗室環境中設定您的 Microsoft 365 Defender 試用版 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用於：**
- Microsoft 365 Defender 

本主題將引導您設定專用實驗室環境。 如需在生產中設定試用的詳細資訊，請參閱《新[評估與試驗 Microsoft 365 Defender](eval-overview.md)手冊》。 

## <a name="create-an-office-365-e5-trial-tenant"></a>建立 Office 365 E5 試用租使用者
>[!NOTE]
>如果您已經有現有的 Office 365 或 Azure Active Directory 訂閱，您可以略過 Office 365 E5 的試用租使用者建立步驟。

1. 移至 [Office 365 E5 的產品入口網站](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)，然後選取 [**免費試用版**]。

   ![影像 of_Office 365 E5 免費試用版頁面](../../media/mtp-eval-9.png)
  
2. 輸入您的電子郵件地址 (個人或公司) ，以完成試用註冊。 按一下 [ **設定帳戶**]。

   ![影像 of_Office 365 E5 試用版註冊設定] 頁面](../../media/mtp-eval-10.png)

3. 請填入您的名字、姓氏、商務電話號碼、公司名稱、公司規模和國家或地區。  

   ![影像 of_Office 365 E5 試用註冊設定頁面要求名稱、電話及公司詳細資料](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > 您在這裡設定的國家或地區決定 Office 365 將主控的資料中心區域。
  
4. 選擇您的驗證喜好設定：透過短信或來電。 按一下 [ **傳送驗證碼**]。 

   ![影像 of_Office 365 E5 試用註冊設定頁面要求驗證偏好設定](../../media/mtp-eval-12.png)

5. 為您的租使用者設定自訂的功能變數名稱，然後按 **[下一步]**。

   ![影像 of_Office 365 E5 試用註冊設定] 頁面，您可以在其中設定自訂功能變數名稱](../../media/mtp-eval-13.png)
 
6. 設定第一個身分識別，這將是租使用者的全域管理員。 填入 **名稱** 和 **密碼**。 按一下 [註冊]。

   ![影像 of_Office 365 E5 試用註冊設定] 頁面，您可以在這裡設定您的商務身分識別](../../media/mtp-eval-14.png)

7. 按一下 [**移至設定**] 以完成 Office 365 E5 試用租使用者布建。

   ![Office 365 E5 試用註冊安裝程式頁面的影像，提示按一下 [前往設定] 按鈕](../../media/mtp-eval-15.png)

8. 連線公司網域加入 Office 365 租使用者。 選選擇 [**連線您已擁有的網域**，然後輸入您的功能變數名稱。 按一下 ****[下一步]。

   ![影像 of_Office 365 E5 安裝頁面，您應該在其中個人化登入和電子郵件](../../media/mtp-eval-16.png)
 
9. 新增 TXT 或 MX 記錄以驗證網域擁有權。 將 TXT 或 MX 記錄新增至您的網域後，請選取 [ **驗證**]。

   ![影像 of_Office 365 E5 安裝頁面，您應該在這裡新增 TXT 的 MX 記錄以驗證您的網域](../../media/mtp-eval-17.png)
 
10. 選為您的租使用者建立更多使用者帳戶。 您可以按 **[下一步]** 略過此步驟。

    ![影像 of_Office 365 E5 安裝頁面，您可以在其中新增更多使用者](../../media/mtp-eval-18.png)
 
11. 選下載 Office 的應用程式。 按 **[下一步]** 略過此步驟。 

    ![影像 of_Office 365 E5 頁面，您可以在此頁面上安裝 Office 應用程式](../../media/mtp-eval-19.png)

12. 選遷移電子郵件。 您也可以略過此步驟。

    ![影像 of_Office 365 E5，您可以在其中設定是否要遷移電子郵件訊息](../../media/mtp-eval-20.png)
 
13. 選擇 [線上服務]。 選取 **Exchange** ，然後按 **[下一步]**。 

    ![影像 of_Office 365 E5，您可以在這裡選擇您的線上服務](../../media/mtp-eval-21.png)

14. 將 MX、CNAME 及 TXT 記錄新增至您的網域。 完成時，選取 [ **驗證**]。

    ![影像 of_Office 365 E5 您可以在這裡加入您的 DNS 記錄](../../media/mtp-eval-22.png)
 
15. 恭喜，您已完成對 Office 365 租使用者的布建。

    ![影像 of_Office 365 E5 安裝完成確認頁面](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>啟用 Microsoft 365 試用訂閱

>[!NOTE]
>註冊試用版可提供25個使用者授權供一個月使用。 如需詳細資訊，請參閱 [Try Or 購買 M365 訂閱](../../commerce/try-or-buy-microsoft-365.md) 。

1. 從 [Microsoft 365 系統管理中心](https://admin.microsoft.com/)，按一下 [**帳單**]，然後流覽至 [**購買服務**]。

2. 選取 **Microsoft 365 E5** ，然後按一下 [**開始免費試用**]。 

   ![影像 of_Microsoft 365 E5 開始免費試用頁面](../../media/mtp-eval-24.png)

3. 選擇您的驗證喜好設定：透過短信或來電。 決定之後，請輸入電話號碼、選取 [ **文字** ] 或 [ **呼叫我** ]，視您的選擇而定。

   ![Image of_Microsoft 365 E5 開始免費試用頁面，要求連絡人詳細資料傳送程式碼，以證明您不是機器人](../../media/mtp-eval-25.png)
 
4. 輸入驗證碼，然後按一下 [ **開始免費試用**]。

   ![影像 of_Microsoft 365 E5 開始免費試用頁面，您可以在此頁面上填寫驗證碼，以證明您不是機器人](../../media/mtp-eval-26.png)

5. 按一下 [**立即試用**] 以確認您的 Microsoft 365 E5 試用版。

   ![影像 of_Microsoft 365 E5 開始免費試用頁面，您應該在此頁面上時鐘立即試按鈕開始](../../media/mtp-eval-27.png)
 
6. 前往 **Microsoft 365 系統管理 Center**  >  **使用者** 作用中的使用者  >  ****。 選取您的使用者帳戶，選取 [**管理產品授權**]，然後將授權從 Office 365 E5 換成 **Microsoft 365 E5**。 按一下 **儲存**。

   ![Image of_Microsoft 365 Admin Center 頁面，您可以在其中選取 Microsoft 365 E5 授權](../../media/mtp-eval-28.png)
 
7. 再次選取全域管理員帳戶，然後按一下 [ **管理使用者名稱**]。

   ![Image of_Microsoft 365 系統管理中心] 頁面，您可以在其中選取 [帳戶]，然後管理使用者名稱](../../media/mtp-eval-29.png)

8. 選根據您在先前步驟中選取的專案，將網域從 *onmicrosoft.com* 變更為您自己的網域。 按一下 **[儲存變更]**。

   ![Image of_Microsoft 365 系統管理中心] 頁面，您可以在其中變更您的網域偏好設定](../../media/mtp-eval-30.png)



## <a name="next-step"></a>後續步驟
|[階段3：設定板載 &](config-m365d-eval.md) | 針對 Microsoft 365 Defender 試用實驗室或試驗環境設定每個 Microsoft 365 Defender pillar，並在您的端點上架。
|:-------|:-----|
