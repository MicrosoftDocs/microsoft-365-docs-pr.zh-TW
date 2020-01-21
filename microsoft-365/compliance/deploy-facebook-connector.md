---
title: 部署封存 Facebook 資料的連接器
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
description: 系統管理員可以設定原生的連接器，以匯入並封存至 Office 365 的 Facebook 商務頁面。 此資料會匯入至 Office 365 之後，您可以使用合規性功能，例如合法持有、 內容搜尋和保留原則來管理您的組織 Facebook 資料的控管。
ms.openlocfilehash: bb348c6e08151d63e92973d3f262704357e40814
ms.sourcegitcommit: ce0651075aa7e3e1b189437f1990207dd10374b0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2020
ms.locfileid: "41247476"
---
# <a name="deploy-a-connector-to-archive-facebook-data"></a>部署封存 Facebook 資料的連接器

本文包含的逐步程序來部署使用 Office 365 匯入服務 Facebook 商務頁面的資料匯入至 Office 365 的連接器。 此程序的高階概觀與部署的 Facebook 連接器所需的必要條件清單，請參閱[使用連接器來封存 Facebook Office 365 （預覽） 中的資料](archive-facebook-data-with-sample-connector.md)。 

## <a name="step-1-download-the-package"></a>步驟 1： 下載套件

從 [版本] 區段中，GitHub 儲存機制中下載預先建立的套件<https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>。 在 [最新版本中，下載 zip 檔名為**SampleConnector.zip**。 您將此 zip 檔案上傳到步驟 4 中的 Azure。

## <a name="step-2-create-an-app-in-azure-active-directory"></a>步驟 2： 在 Azure Active Directory 中建立的應用程式

1. 移至 [<https://portal.azure.com>並使用 Office 365 全域系統管理員帳戶的認證登入。

    ![在 [AAD 中建立應用程式](media/FBCimage1.png)

2. 在左側的導覽窗格中，按一下 [ **Azure Active Directory**]。

    ![按一下 [Azure Active Directory](media/FBCimage2.png)

3. 在左側的導覽窗格中，按一下 [**應用程式註冊 （預覽）** ，然後按一下 [**新增註冊**。

    ![按一下 [* * 應用程式註冊 （預覽） * *，然後按一下 [* * 新註冊 * *](media/FBCimage3.png)

4. 註冊應用程式。 [重新導向 URI，選取 Web 應用程式類型] 下拉式清單中，然後輸入<https://portal.azure.com>URI] 方塊中。

   ![註冊應用程式](media/FBCimage4.png)

5. 複製 **（用戶端） 的應用程式識別碼**] 及 [**目錄 （承租人） 識別碼**，並將它們儲存到文字檔或其他安全的位置。 您在稍後步驟使用這些識別碼。

   ![複製應用程式識別碼] 及 [目錄識別碼，並將其儲存](media/FBCimage5.png)

6. 移至**新的應用程式的憑證 & 機密資料**

   ![移至新的應用程式的憑證 & 機密資料](media/FBCimage6.png)

7. 按一下 [**新的用戶端密碼**

   ![按一下 [新的用戶端密碼](media/FBCimage7.png)

8. 建立新的密碼。 在 [描述] 方塊中，輸入密碼，然後選擇的到期時間。 

    ![輸入密碼，然後選擇 [的到期時間](media/FBCimage8.png)

9. 複製密碼的值，並將它儲存到文字檔或其他儲存位置。 這是您在稍後步驟使用的 AAD 應用程式密碼。

   ![複製密碼的值，並將它儲存](media/FBCimage9.png)

10. 移至**資訊清單**，然後複製 identifierUris （這也稱為 AAD 應用程式的 Uri） 以反白顯示下列螢幕擷取畫面。 複製到文字檔或其他儲存位置的 AAD 應用程式的 Uri。 您在步驟 6 中使用。

   ![移至資訊清單，並將複製的 AAD 應用程式的 Uri](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a>步驟 3： 建立 Azure 儲存體帳戶

1. 移至 Azure 的首頁上，為您的組織。

    ![移至 Azure 的 [首頁] 頁面](media/FBCimage11.png)

2. 按一下 [**建立資源**，然後在 [搜尋] 方塊中輸入**儲存體帳戶**。

    ![按一下 [建立資源] 和 [類型儲存體帳戶](media/FBCimage12.png)

3. 按一下 [**儲存**]，然後按一下 [**儲存體帳戶**。

    ![按一下儲存，然後按一下 [儲存體帳戶](media/FBCimage13.png)

4. 在 [**建立儲存體帳戶**] 頁面上，在 [訂閱] 方塊中，選取**Pay-As-You-Go**或取決於哪些類型的 Azure 訂用帳戶必須**免費試用版**。 然後選取或建立資源群組。

    ![選取 [預付或免費試用版](media/FBCimage14.png)

5. 輸入儲存體帳戶的名稱。

    ![輸入儲存體帳戶的名稱](media/FBCimage15.png)

6. 檢閱，然後按一下 [**建立**]，以建立儲存體帳戶。

    ![建立儲存體帳戶](media/FBCimage16.png)

7. 在一段時間後按一下 [**重新整理**，然後按一下 [瀏覽至儲存體帳戶的 [**移至資源**。

    ![瀏覽至儲存體帳戶](media/FBCimage17.png)

8. 在左側的導覽窗格中，按一下 [**便捷鍵**。

    ![按一下 [便捷鍵](media/FBCimage18.png)

9. 複製**連接字串**，並將它儲存到文字檔或其他儲存位置。 您使用此建立 web 應用程式資源時。

    ![複製連接字串，並將它儲存](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a>步驟 4： 在 Azure 中建立新的 web 應用程式資源

1. 在 [**首頁**] 頁面在 Azure 入口網站中，按一下 [**建立資源\>每個項目\>Web 應用程式**。 在 [ **Web 應用程式**] 頁面上，按一下 [**建立**]。 

   ![建立新的 web 應用程式資源](media/FBCimage20.png)

2. 填入詳細資料 （如下所示），然後再建立 Web 應用程式。 請注意，您在 [**應用程式名稱**] 方塊中輸入的名稱，用於建立 Azure 應用程式服務的 URL;例如，fbconnector.azurewebsites.net。

   ![填入詳細資料，然後再建立 Web 應用程式](media/FBCimage21.png)

3. 移至新建立的 web 應用程式資源，按一下 [**應用程式設定**]，請在左側的導覽窗格中。 應用程式設定] 下按一下 [新增新的設定，新增下列三個設定： 使用的值 （從複製到文字檔先前的步驟）： 

    - **APISecretKey** – 您可以為密碼輸入任何值。 這用來存取在步驟 7 中的連接器 web 應用程式。

    - **StorageAccountConnectionString** -連接字串您在步驟 3 中建立 Azure 儲存體帳戶之後所複製的 Uri。

    - **tenantId** – 您在步驟 2 中的 Azure Active Directory 中建立 Facebook 連接器應用程式之後複製您 Office 365 組織租用戶識別碼。

    ![輸入應用程式設定](media/FBCimage22.png)

4. **一般設定**] 下按一下 [**上**旁**Always On**。 按一下 [**儲存**] 頁面的頂端儲存應用程式的設定。

   ![儲存應用程式設定](media/FBCimage23.png)

5. 最後一個步驟是將連接器 app 原始程式碼上傳至 Azure 中您在步驟 1 中下載。 在網頁瀏覽器中，移至 https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi。 例如，如果您的 Azure 應用程式資源 （這在本節中的步驟 2 中所命名） 的名稱是**fbconnector**，然後您會移至https://fbconnector.scm.azurewebsites.net/ZipDeployUi。 

6. 拖放到此頁面 SampleConnector.zip （，您在步驟 1 中下載）。 將檔案上傳並部署成功後，看起來類似下列的螢幕擷取畫面] 頁面上：

   ![將拖放到此頁面 SampleConnector.zip](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a>步驟 5： 註冊 Facebook 應用程式

1. 移至 [ <https://developers.facebook.com>，登入之帳戶的組織的 Facebook 商務頁面、 使用的認證，然後按一下 [**新增新的應用程式**。

   ![新增新的應用程式的 Facebook business 頁面](media/FBCimage25.png)

2. 建立新的應用程式識別碼。

   ![建立新的應用程式識別碼](media/FBCimage26.png)

3. 在左側的導覽窗格中，按一下 [**新增產品**]，然後按一下**Set Up**中 [ **Facebook 登入**] 磚。

   ![按一下 [新增產品](media/FBCimage27.png)

4. 在整合 Facebook 登入頁面上，按一下 [ **Web**]。

   ![按一下 [Web] 上的整合 Facebook 登入頁面](media/FBCimage28.png)

5. 新增 Azure 應用程式服務的 URL;例如`https://fbconnector.azurewebsites.net`。

   ![新增 Azure 應用程式服務 URL](media/FBCimage29.png)

6. 完成 [快速入門] 區段中的 Facebook 登入安裝程式。

   ![完成 [快速入門] 區段](media/FBCimage30.png)

7. 在左側的導覽窗格的 [ **Facebook 登入**，按一下 [**設定**]，並在**有效的 OAuth 重新導向 Uri** ] 方塊中新增的 OAuth 重新導向 URI。 使用格式**\<connectorserviceuri>/檢視/FacebookOAuth**、 其中 connectorserviceuri 的值是為您的組織; Azure 應用程式服務 URL例如， `https://fbconnector.azurewebsites.net`。

   ![有效的 OAuth 重新導向 Uri 方塊中新增的 OAuth 重新導向 URI](media/FBCimage31.png)

8. 在左側的導覽窗格中，按一下 [**新增產品**，然後按一下 [ **Webhooks。** **頁面**下拉功能表中，按一下 [**頁面]**。 

   ![按一下 [新增產品，然後按一下 [* * Webhooks](media/FBCimage32.png)

9. 新增 Webhooks 回呼 URL，並將確認語彙基元。 回呼的 URL，格式使用格式**<connectorserviceuri>/api/FbPageWebhook**、 其中 connectorserviceuri 的值是為您的組織; Azure 應用程式服務 URL例如`https://fbconnector.azurewebsites.net`。 

    驗證權杖應該類似強式密碼。 將驗證權杖複製到文字檔或其他儲存位置。

        ![Add the verify token](media/FBCimage33.png)

10. 測試和訂閱的端點摘要。

    ![測試及訂閱的端點](media/FBCimage34.png)

11. 新增隱私權 URL、 應用程式圖示和商業用途。 此外，將應用程式識別碼和應用程式密碼複製到文字檔或其他儲存位置。

    ![新增隱私權 URL、 應用程式圖示和商業用途](media/FBCimage35.png)

12. 將應用程式公開。

    ![公開應用程式](media/FBCimage36.png)

13. 將使用者新增至系統管理員或測試人員角色。

    ![將使用者新增至系統管理員或測試人員角色](media/FBCimage37.png)

14. 新增 [**網頁公用的內容存取**權限。

    ![dd] 頁面上的公用內容存取權限](media/FBCimage38.png)

15. 新增管理頁面的權限。

    ![新增管理頁面的權限](media/FBCimage39.png)

16. 取得由 Facebook 檢閱應用程式。

    ![取得由 Facebook 檢閱應用程式](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a>步驟 6： 設定連接器的 web 應用程式

1. 移至 https://\<AzureAppResourceName>.azurewebsites.net （其中 AzureAppResourceName 是您在步驟 4 中名為您 Azure 應用程式資源的名稱），例如，如果名稱為**fbconnector**，請移至`https://fbconnector.azurewebsites.net`。 應用程式的 [首頁] 頁面上看起來像下列螢幕擷取畫面中：

   ![移至您連接器 web app](media/FBCimage41.png)

2. 按一下 [**設定**] 頁面中，會顯示號。
 
   ![按一下 [設定] 頁面中，會顯示號](media/FBCimage42.png)

3. 在租用戶識別碼] 方塊中，輸入或貼上您的租用戶識別碼 （您在步驟 2 中所取得）。 在 [密碼] 方塊中，輸入或貼上 APISecretKey （，您在步驟 2 中所取得），，然後按一下要顯示 [**設定詳細資料**] 頁面上**設定的組態設定**。

    ![使用您的租用戶識別碼和密碼登入，然後移至設定詳細資料頁面](media/FBCimage43.png)

4. [**設定的詳細資訊**，請輸入下列組態設定 

   - **Facebook 應用程式識別碼**– 您在步驟 5 中所取得的 Facebook 應用程式的應用程式識別碼。
   - **Facebook 應用程式密碼**– 您在步驟 5 中所取得的 Facebook 應用程式的應用程式密碼。
   - **Facebook webhooks 驗證權杖**– 您在步驟 5 中建立的驗證權杖。
   - **AAD 應用程式識別碼**– 您在步驟 2 中建立的 Azure Active Directory 應用程式的應用程式識別碼。
   - **AAD 應用程式密碼**– 您在步驟 4 中建立的 APISecretKey 密碼的值。
   - **AAD 應用程式的 Uri** – AAD 應用程式在步驟 2; 中所取得的 Uri例如， `https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213`。
   - **App 觀點檢測機碼**– 保留此方塊空白。

5. 按一下 [**儲存**] 以儲存連接器設定。

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>步驟 7： 設立安全性 & 合規性中心中的自訂連接器

1. 移至 [ <https://protection.office.com> ，然後按一下 [**資訊控管\>匯入\>封存協力廠商資料**。

   ![移至安全性與合規性中心，按一下 [控管 > 匯入 > 封存協力廠商資料的資訊](media/FBCimage44.png)

2.  按一下 [**新增連接器**]，然後按一下 [ **Facebook 頁面**。

    ![新增 Facebook 連接器設定連接器](media/FBCimage46.png)

3.  在 [**新增連接器應用程式**] 頁面中，輸入下列資訊，然後按一下 [**驗證連接器**。

    - 在第一個方塊中，輸入連接器名稱，例如**Facebook**。
    - 在第二個方塊中，輸入或貼上您在步驟 4 中新增 APISecretKey 的值。
    - 在第三個方塊中，輸入或貼上的 Azure 應用程式服務 URL;例如`https://fbconnector.azurewebsites.net`。
 
    成功驗證連接器之後，按一下 [**下一步**]。
    
    ![在成功驗證連接器之後，按 [下一步]](media/FBCimage47.png)

4.  按一下 [**登入與連接器應用程式**。

    ![按一下 [登入與連接器應用程式](media/FBCimage45.png)

5. 輸入或貼上 APISecretKey 一次，然後按一下 [**連接器服務的登入**。

   ![輸入或貼上 APISecretKey，然後按一下 [登入] 按鈕](media/FBCimage48.png)

6. 按一下 [**登入與 Facebook**。

   ![按一下 [* * 與 Facebook 的登入](media/FBCimage49.png)

7. 在**登入 Facebook** ] 頁面上，使用登入認證之帳戶的組織的 Facebook 商務頁面。 請確定您指派給貴組織的 Facebook 商務頁面的管理員角色登入 Facebook 帳戶

   ![登入 Facebook](media/FBCimage50.png)

8. 按一下 [**選取頁面**，以選擇您想要在 Office 365 中封存的貴組織的業務頁面]。

   ![按一下 [選取頁面，以顯示貴組織的業務頁面](media/FBCimage51.png)

9. 受管理的 Facebook 帳戶，登入商務頁面清單隨即顯示。 選取 [封存，然後按一下 [**儲存**] 頁面。

    ![選取您想要保存組織 business 頁面](media/FBCimage52.png)

10. 按一下 [**完成**] 結束安裝程式的連接器服務應用程式]。

    ![按一下 [完成] 結束連接器服務應用程式](media/FBCimage53.png)

11. 在 [**設定篩選器**] 頁面中，您可以套用篩選器來匯入 （和封存） 特定天數的項目。 按 [下一步]****。

    ![套用篩選器來匯入特定天數的項目](media/FBCimage54.png)

12. 在 [**設定儲存體帳戶**] 頁面上，選取先前選取的 Facebook 商務頁面中的項目將會匯入至 Office 365 信箱。

    ![指定 Office 365 信箱項目從 Facebook 匯入封存](media/FBCimage55.png)

13. 檢閱您的設定，然後按一下 [**完成**] 以完成安全性 & 規範中心的連接器設定。

    ![檢閱連接器設定](media/FBCimage56.png)

14. 移至**封存協力廠商資料**頁面才能看見匯入程序的進度。

    ![移至封存協力廠商資料] 頁面上，以追蹤匯入程序](media/FBCimage58.png)
