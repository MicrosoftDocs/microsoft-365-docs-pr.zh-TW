---
title: 部署封存 Twitter 資料的連接器
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 系統管理員可以設定原生的連接器，以匯入並封存至 Microsoft 365 Twitter 資料。 此資料會匯入至 Microsoft 365 之後，您可以使用合規性功能，例如合法持有、 內容搜尋和保留原則來管理您的組織 Twitter 資料的控管。
ms.openlocfilehash: 5a7d7749f99615d9fd6858be05cc63153cfe1d31
ms.sourcegitcommit: 9b390881fe661deb0568b4b86a5a9094f3c795f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269394"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a>部署封存 Twitter 資料的連接器

本文包含的逐步程序來部署您的組織 Twitter 帳戶的資料匯入至 Microsoft 365 使用 Office 365 匯入服務的連接器。 此程序的高階概觀與部署 Twitter 連接器所需的必要條件清單，請參閱[設定連接器，以封存 Twitter 資料](archive-twitter-data-with-sample-connector.md)。 

## <a name="step-1-create-an-app-in-azure-active-directory"></a>步驟 1: Azure Active Directory 中建立的應用程式

1. 移至 [<https://portal.azure.com>並使用 Office 365 全域系統管理員帳戶的認證登入。

   ![登入 Azure](media/TCimage01.png)

2. 在左側的導覽窗格中，按一下 [ **Azure Active Directory**]。

   ![移至 Azure Active Directory](media/TCimage02.png)

3. 在左側的導覽窗格中，按一下 [**應用程式註冊 （預覽）** ，然後按一下 [**新增註冊**。

   ![建立新的應用程式註冊](media/TCimage03.png)

4. 註冊應用程式。 **（選用） 的 [重新導向 URI**，選取**Web**應用程式類型] 下拉式清單中，然後輸入`https://portal.azure.com`URI] 方塊中。

   ![型別https://portal.azure.com的重新導向 URI ](media/TCimage04.png)

5. 複製 **（用戶端） 的應用程式識別碼**] 及 [**目錄 （承租人） 識別碼**，並將它們儲存到文字檔或其他安全的位置。 您在稍後步驟使用這些識別碼。

    ![複製並儲存應用程式識別碼] 及 [目錄識別碼](media/TCimage05.png)

6. 移至**新的應用程式的憑證 & 機密資料**，並在 [**用戶端密碼**] 下按一下 [**新的用戶端密碼**。

   ![建立新的用戶端密碼](media/TCimage06.png)

7. 建立新的密碼。 在 [描述] 方塊中，輸入密碼，然後選擇的到期時間。 

   ![輸入密碼，然後選擇 [到期時間](media/TCimage08.png)

8. 複製密碼的值，並將它儲存到文字檔或其他儲存位置。 這是您在稍後步驟使用的 AAD 應用程式密碼。

   ![複製並儲存密碼](media/TCimage09.png)

9. 移至**資訊清單**，然後複製 identifierUris （這也稱為 AAD 應用程式的 Uri） 以反白顯示下列螢幕擷取畫面。 複製到文字檔或其他儲存位置的 AAD 應用程式的 Uri。 您在步驟 6 中使用。

    ![複製並儲存的 AAD 應用程式的 Uri](media/TCimage10.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>步驟 2： 部署至您的 Azure 帳戶從 GitHub 連接器 」 的 web 服務

1. 移至[這個 GitHub 網站](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)，然後按一下 [**部署至 Azure**。

    ![移至 Azure 的 [首頁] 頁面](media/FBCimage11.png)

2. 按一下 [**部署至 Azure**之後，您將會重新導向至自訂的範本] 頁面上使用 Azure 入口網站。 填入的**基本概念**和**設定**詳細資料，然後按一下 [**購買**。

   ![按一下 [建立資源] 和 [類型儲存體帳戶](media/FBCimage12.png)

    - **訂閱：** 選取您想要部署 Twitter 連接器 web 服務，以您 Azure 訂用帳戶。
    
    - **資源群組：** 選擇或建立新的資源群組。 資源群組是保留 Azure 解決方案的相關的資源的容器。

    - **位置：** 選擇的位置。

    - **Web 應用程式名稱：** Web 應用程式提供連接器的唯一名稱。 對名稱必須是長度為 3 並 18 個字元之間。 此名稱用來建立 Azure 應用程式服務的 URL;例如，如果您提供**twitterconnector**的 Web 應用程式名稱然後 Azure 應用程式服務的 URL 將會是**twitterconnector.azurewebsites.net**。
    
    - **tenantId:** 您在步驟 1 中的 Azure Active Directory 中建立 Facebook 連接器應用程式之後複製您 Microsoft 365 組織租用戶識別碼。
    
   - **APISecretKey:** 您可以為密碼輸入任何值。 這用來存取在步驟 5 中的連接器 web 應用程式。

3. 部署成功後，看起來類似下列的螢幕擷取畫面] 頁面上：

    ![按一下儲存，然後按一下 [儲存體帳戶](media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a>步驟 3： 建立 Twitter 應用程式

1. 移至 [ https://developer.twitter.com，登入您的組織，開發人員帳戶使用的認證，然後按一下 [**應用程式**。

   ![移至 [ https://developer.twitter.com ，然後登入](media/TCimage25-5.png)
2. 按一下 [**建立應用程式**]。
   
   ![移至應用程式] 頁面上，若要建立的應用程式](media/TCimage26.png)

3. 在 [**應用程式詳細資料**，新增應用程式的相關資訊。

   ![輸入應用程式的相關資訊](media/TCimage27.png)

4. Twitter 開發人員儀表板上選取您剛建立的應用程式複製應用程式 ID 會顯示，並將它儲存到文字檔或其他儲存位置。 然後按一下 [**詳細資料**。
   
   ![複製並儲存應用程式識別碼](media/TCimage28.png)

5. **索引鍵和權杖**索引標籤上，在**消費者 API 機碼**下複製 API 祕密金鑰並將它儲存到文字檔或其他儲存位置。 然後按一下 [**建立**]，以產生的存取權杖及存取權杖的密碼，並複製這些文字檔案或其他儲存位置。
   
   ![複製並儲存至 API 祕密金鑰](media/TCimage29.png)

   然後按一下 [**建立**]，以產生的存取權杖及存取權杖的密碼，並複製這些文字檔案或其他儲存位置。

6. 按一下 [**權限**] 索引標籤，並設定權限，如下列螢幕擷取畫面所示：

   ![設定權限](media/TCimage30.png)

7. 儲存的權限設定之後，按一下 [**應用程式詳細資料**] 索引標籤，然後按一下 [**編輯 > 編輯詳細資料]**。

   ![編輯應用程式詳細資料](media/TCimage31.png)

8. 執行下列工作：

   - 選取核取方塊可允許登入 Twitter 連接器應用程式。
   
   - 新增的 OAuth 重新導向 Uri 使用下列格式： ** \<connectorserviceuri>/檢視/TwitterOAuth**、 其中*connectorserviceuri*的值是為您的組織; Azure 應用程式服務 URL例如， https://twitterconnector.azurewebsites.net/Views/TwitterOAuth。

    ![允許連接器 Twitter 登入，並將新增 OAuth 重新導向 Uri 的應用程式](media/TCimage32.png)

在 Twitter 開發人員 app 現已可使用。

## <a name="step-4-configure-the-connector-web-app"></a>步驟 4： 設定連接器的 web 應用程式 

1. 移至 https://\<AzureAppResourceName>.azurewebsites.net （其中**AzureAppResourceName**是您在步驟 4 中名為您 Azure 應用程式資源的名稱）。 例如，如果名稱為**twitterconnector**，請移至https://twitterconnector.azurewebsites.net。 應用程式的 [首頁] 頁面上看起來像下列螢幕擷取畫面中：

   ![移至 Azure 應用程式資源頁面](media/FBCimage41.png)

2. 按一下 [**設定**] 頁面中，會顯示號。

   ![按一下 [設定] 頁面中，會顯示號](media/FBCimage42.png)

3. 在租用戶識別碼] 方塊中，輸入或貼上您的租用戶識別碼 （您在步驟 2 中所取得）。 在 [密碼] 方塊中，輸入或貼上 APISecretKey （，您在步驟 2 中所取得），，然後按一下要顯示 [組態詳細資料] 頁面上**設定的組態設定**。

   ![使用租用戶識別碼和 API 祕密金鑰登入](media/TCimage35.png)

4. 輸入下列組態設定 

   - **Twitter Api 機碼：** 您在步驟 3 中建立的 Twitter 應用程式的應用程式識別碼。
   
   - **Twitter Api 密碼機碼：** 您在步驟 3 中建立的 Twitter 應用程式 API 祕密金鑰。
   
   - **Twitter 存取權杖：** 您在步驟 3 中建立存取權杖。
   
   - **Twitter 存取 Token 密碼：** 您在步驟 3 中建立的存取權杖的密碼。
   
   - **AAD 應用程式識別碼：** 您在步驟 1 建立的 Azure Active Directory 應用程式的應用程式識別碼
   
   - **AAD 應用程式密碼：** 您在步驟 1 建立的 APISecretKey 密碼值。

5. 按一下 [**儲存**] 以儲存連接器設定。

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>步驟 5： 設定 Microsoft 365 合規性中心中的 Twitter 連接器

1. 移至 [ [https://compliance.microsoft.com](https://compliance.microsoft.com) ，然後按一下 [從左側的 [**資料連接器**

2. 在 [ **Twitter****資料連接器 （預覽）** ] 頁面上，按一下 [**檢視**]。

3. 在**Twitter** ] 頁面上，按一下 [**新增連接器**]。

4. 在**服務中的條款**] 頁面上，按一下 [**接受**]。

5. 在**您的連接器應用程式新增認證**] 頁面中，輸入下列資訊，然後按一下 [**驗證連線**。

   ![輸入連接器應用程式的認證](media/TCimage38.png)

    - 在 [**名稱**] 方塊中，輸入連接器，例如**Twitter 說明控點**的名稱。
    
    - 在**連接器 URL** ] 方塊中，輸入或貼上的 Azure 應用程式服務 URL;例如`https://twitterconnector.azurewebsites.net`。
    
    - 在 [**密碼**] 方塊中，輸入或貼上您在步驟 2 中建立 APISecretKey 的值。
    
    - 在 [ **Azure 應用程式識別碼**] 方塊中，輸入或貼上的 Azure 應用程式應用程式 Id （也稱為*用戶端識別碼*） 值，您在步驟 1 中所取得。

6. 連線成功驗證之後，按一下 [**下一步**]。

7. 在 [**授權 Microsoft 365，以匯入資料**] 頁面上，輸入或貼上 APISecretKey 再次並再按一下 [**登入 web 應用程式**。

8. 按一下 [**登入與 Twitter**。

9. 在 Twitter 登入] 頁面上，登入您的組織 Twitter 帳戶使用的認證。

   ![Twitter 帳戶登入](media/TCimage42.png)

   登入後，[Twitter] 頁面上會顯示下列訊息、 「 Twitter 連接器工作成功設定。 」

10. 按一下 [**繼續**] 以完成 Twitter 連接器設定。

11. 在 [**設定篩選器**] 頁面上，您可以套用篩選器，一開始匯入特定天數的項目。 選取 [保留天數，，然後按一下 [**下一步**。

12. 在 [**選擇儲存位置**] 頁面上，輸入 Twitter 項目會被匯入，並再按 [**下一步**，Microsoft 365 信箱的電子郵件地址。

13. 在**提供系統管理員同意**，按一下**提供同意**，然後遵循的步驟。 您必須是全域系統管理員提供 Office 365 匯入服務來存取您的組織中資料的同意。

14. 按 [**下一步**檢閱連接器設定，然後按一下 [**完成**] 以完成連接器設定。

15. 在合規性中心] 中，移至**資料連接器**] 頁面上，然後按一下 [**連接器**] 索引標籤，若要查看匯入程序的進度。
