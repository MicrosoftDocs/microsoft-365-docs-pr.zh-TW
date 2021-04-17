---
title: 資料遺失防護原則提示參考
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: 瞭解如何將原則提示新增至資料遺失防護 (DLP) 原則通知使用者他們使用與 DLP 原則衝突的內容。
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 693f511b6303fb07d393c62efb4a61631b844474
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876799"
---
# <a name="data-loss-prevention-policy-tips-reference"></a>資料遺失防護原則提示參考

在下列情況下，Outlook Web Access 中的 DLP 原則秘訣可用於 DLP 原則中適用于 Exchange 工作負載的所有條件、例外狀況和動作：

**條件：**

- 寄件者是
- Sender Domain 是
- 收件者是的成員
- 標頭包含字或片語
- 標頭符合模式
- 檔案大小等於或大於
- 郵件類型為
- 郵件重要性為
- 內容字元集包含文字
- 主旨或內文包含文字或片語
- 主旨或內文符合模式
- 內容字元集包含文字
- 內容接收來源
- 寄件者覆寫原則提示
- 郵件大小等於或大於
- Sender AD 屬性包含字詞或片語
- 寄件者 AD 屬性符合模式
- 檔內容包含文字或片語
- 檔內容符合模式

**行動：**

- 轉寄郵件以核准給寄件者的管理員
- 將郵件轉寄給特定核准者
- 將郵件重新導向至特定使用者
- 將收件者新增至 [收件者] 方塊
- 將收件者新增至 [抄送] 方塊
- 將收件者新增至 [密件副本] 方塊
- 將寄件者的管理員新增為收件者
- 新增 HTML 免責聲明
- 前置電子郵件主題
- 移除 O365 郵件加密和許可權保護
- 移除

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a>Outlook 2013 和更新版本支援顯示僅限某些條件和例外的原則提示

目前，Outlook 2013 和更新版本支援顯示原則提示的原則，但不含下列所述條件和對應例外狀況之外的任何條件或例外狀況：

- 內容包含的 (只適用于機密資訊類型。 不支援敏感度標籤) 
- 內容已共用

請注意，所有條件都適用于在 Outlook 用戶端應用程式中撰寫的電子郵件，其將會符合內容，並強制執行內容的保護動作。 不過，向使用者顯示原則提示，但除了上述所述的任何情況之外，還不支援任何條件。

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types"></a>Outlook 2013 和更新版本支援只顯示某些敏感資訊類型的原則提示

在桌面 (2013 和更新版本) 中，會偵測到顯示 DLP 原則提示的預置資訊類型清單，如下所示：

- ABA 路由號碼
- 阿根廷國家身分識別 (DNI) 號碼
- 澳大利亞銀行帳戶號碼
- 澳大利亞醫療帳戶號碼
- 澳大利亞護照號碼
- 澳大利亞稅收檔編號
- Azure DocumentDB 驗證金鑰  
- Azure IAAS 資料庫連接字串和 Azure SQL 連接字串  
- Azure IoT 連接字串  
- Azure 發佈設定密碼  
- Azure Redis Cache Connection String  
- Azure SAS  
- Azure 服務匯流排連接字串  
- Azure 儲存體帳戶金鑰  
- Azure 儲存體帳戶金鑰 (泛型)   
- 比利時國民編碼
- 巴西 CPF 號碼
- 巴西法人編號 (CNPJ) 
- 巴西全國身分識別卡 (RG) 
- 加拿大銀行帳戶號碼
- 加拿大駕駛執照號碼
- 加拿大健康情況服務號碼
- 加拿大護照號碼
- 加拿大個人健康身分識別號碼 (PHIN) 
- 加拿大社交保險號碼
- 智利身分識別卡號碼
- 中國居民身分識別卡 (中國) 號碼
- 信用卡號碼
- 克羅埃西亞身分證號碼  
- 克羅埃西亞個人識別 (OIB) 碼  
- 捷克個人身分識別號碼  
- 丹麥個人識別碼
- 藥物執行代理商 (DEA) 號碼
- 歐盟轉帳卡號碼
- 歐盟駕駛執照號碼  
- 歐盟國身分識別號碼  
- 歐盟護照號碼  
-  (SSN) 或同等識別碼的歐盟社會安全號碼  
- 歐盟)  (TIN 的納稅識別號  
- 芬蘭國民身分證
- 芬蘭護照號碼
- 法國駕照編號
- 法國國民身分證 (CNI)
- 法國護照號碼
- 法國社會安全號碼 (INSEE)
- 德國駕照編號
- 德國護照號碼
- 德國身分證號碼
- 希臘國民身分證  
- 香港身分識別卡 (HKID) 號碼
-  (平移) 的印度永久帳戶號碼
- 印度唯一識別碼 (Aadhaar) 號碼
- 印尼身分識別卡 (KTP) 號碼
- 國際銀行帳號 (IBAN)
- 國際分類的疾病 (ICD-10-釐米)   
- 疾病 (ICD-9 釐米) 的國際分類  
- IP 位址
- 愛爾蘭個人公用服務 (PPS) 號碼 
- 以色列銀行帳戶號碼
- 以色列國家識別碼
- 義大利駕照編號
- 日本銀行帳戶號碼
- 日本駕照編號
- 日本護照號碼
- 日本居民登記號碼
- 日本社交保險號碼 (SIN) 
- 日本住家電話卡號碼
- 馬來西亞身分識別卡號碼
- 荷蘭公民服務 (BSN) 號碼  
- 紐西蘭健康情況號碼的部
- 挪威身分識別號碼  
- 菲律賓統一多用途識別碼號碼
- 波蘭身分證明卡
- 波蘭國民身分證 (PESEL)
- 波蘭護照
- 葡萄牙公民證號碼
- 沙烏地阿拉伯國際身分識別
- 新加坡國家註冊身分識別卡 (NRIC) 號碼
- 南非識別號碼  
- 韓國居民登記號碼
- 西班牙社會安全號碼 (SSN)
- SQL Server 連接字串  
- 瑞典國民身分證號
- 瑞典護照號碼
- SWIFT 代碼
- 臺灣國家 ID
- 臺灣護照號碼
- 臺灣居民憑證 (ARC/TARC) 
- 泰國人口識別碼
- 土耳其國身分識別號碼
- 英國駕照號碼
- 英國選民名冊編號
- 英國國民健保服務號碼
- 英國國民保險號碼 (NINO)
- 美國/英國 護照號碼
- 美國銀行帳戶號碼
- 美國駕駛執照號碼
- ITIN) 的美國個別納稅人識別號碼 (
-  (SSN) 的 U.S. 社會安全號碼

請注意，除了上述現成的敏感資訊類型之外，還支援 DLP 原則提示的自訂敏感資訊類型。

## <a name="data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types"></a>端點的資料遺失防護只支援某些敏感資訊類型的原則秘訣

在位於端點裝置上的檔中，會偵測到的現成敏感資訊類型清單如下：

- ABA 路由號碼 
- 阿根廷國家身分識別 (DNI) 號碼 
- 澳大利亞銀行帳戶號碼 
- 澳大利亞醫療帳戶號碼 
- 澳大利亞護照號碼 
- 澳大利亞稅收檔編號 
- 澳大利亞商務電話號碼 
- 澳大利亞公司號碼 
- 奧地利駕駛執照號碼 
- 奧地利身分識別卡 
- 奧地利護照號碼 
- 奧地利的社會安全號碼 
- 奧地利納稅識別號碼 
- 奧地利增值 (加值稅) 號碼 
- Azure DocumentDB 驗證金鑰 
- Azure IAAS 資料庫連接字串和 Azure SQL 連接字串 
- Azure IoT 連接字串 
- Azure 發佈設定密碼 
- Azure Redis Cache Connection String 
- Azure SAS 
- Azure 服務匯流排連接字串 
- Azure 儲存體帳戶金鑰 
- Azure 儲存體帳戶金鑰 (泛型)  
- 比利時駕駛執照號碼 
- 比利時國民編碼 
- 比利時護照號碼 
- 比利時增值的納稅號碼 
- 巴西 CPF 號碼 
- 巴西法人編號 (CNPJ)  
- 巴西全國身分識別卡 (RG)  
- 保加利亞駕駛執照號碼 
- 保加利亞護照號碼 
- 保加利亞統一的民事編號 
- 加拿大銀行帳戶號碼 
- 加拿大駕駛執照號碼 
- 加拿大健康情況服務號碼 
- 加拿大護照號碼 
- 加拿大個人健康身分識別號碼 (PHIN)  
- 加拿大社交保險號碼 
- 智利身分識別卡號碼 
- 中國居民身分識別卡 (中國) 號碼 
- 信用卡號碼 
- 克羅地亞駕駛執照號碼 
- 克羅埃西亞身分證號碼 
- 克羅地亞國際身分識別卡號碼 
- 克羅地亞護照號碼 
- 克羅埃西亞個人識別 (OIB) 碼 
- CSCAN-AZURE0060 Azure 儲存體帳戶共用存取簽名 
- CSCAN-GENERAL0140 一般對稱金鑰 
- 賽普勒斯駕照編號 
- 賽普勒斯身分識別卡片 
- 賽普勒斯護照號碼 
- 賽普勒斯納稅識別號碼 
- 捷克文駕駛執照號碼 
- 捷克個人身分識別號碼 
- 捷克共和國護照號碼 
- 丹麥駕照編號 
- 丹麥護照號碼 
- 丹麥個人識別碼 
- 藥物執行代理商 (DEA) 號碼 
- 愛沙尼亞駕照編號 
- 愛沙尼亞護照號碼 
- 愛沙尼亞個人識別碼 
- 歐盟轉帳卡號碼 
- 歐盟駕駛執照號碼 
- 歐盟國身分識別號碼 
- 歐盟護照號碼 
-  (SSN) 或同等識別碼的歐盟社會安全號碼 
- 歐盟)  (TIN 的納稅識別號 
- 芬蘭駕照編號 
- 芬蘭歐洲健康情況保險業號碼 
- 芬蘭國民身分證 
- 芬蘭護照號碼 
- 法國駕照編號 
- 法國健康保險業號碼 
- 法國國民身分證 (CNI) 
- 法國護照號碼 
- 法國社會安全號碼 (INSEE) 
- 法國納稅識別號碼 (numéro SPI。 )  
- 法國加值稅收號碼 
- 德國駕照編號 
- 德國護照號碼 
- 德國身分證號碼 
- 德國納稅識別號碼 
- 德國加值稅號碼 
- 希臘駕駛執照號碼 
- 希臘國民身分證 
- 希臘護照號碼 
-  (AMKA) 的希臘社會安全號碼 
- 希臘所得稅識別號碼 
- 香港身分識別卡 (HKID) 號碼 
- 匈牙利文社會安全號碼 (TAJ)  
- 匈牙利增值銷售稅編號 
- 匈牙利駕照號碼 
- 匈牙利護照號碼 
- 匈牙利個人身分識別號碼 
- 匈牙利納稅識別號碼 
-  (平移) 的印度永久帳戶號碼 
- 印度唯一識別碼 (Aadhaar) 號碼 
- 印尼身分識別卡 (KTP) 號碼 
- 國際銀行帳號 (IBAN) 
- 國際分類的疾病 (ICD-10-釐米)  
- 疾病 (ICD-9 釐米) 的國際分類 
- IP 位址 
- 愛爾蘭駕照編號 
- 愛爾蘭護照號碼 
- 愛爾蘭個人公用服務 (PPS) 號碼 
- 以色列銀行帳戶號碼 
- 以色列國家識別碼 
- 義大利駕照編號 
- 義大利會計代碼 
- 義大利護照號碼 
- 義大利值增加的納稅號碼 
- 日本銀行帳戶號碼 
- 日本駕照編號 
- 日本護照號碼 
- 日本居民登記號碼 
- 日本社交保險號碼 (SIN)  
- 日本我的數位公司 
- 日本我的數位個人 
- 日本住家電話卡號碼 
- 拉脫維亞駕駛執照號碼 
- 拉脫維亞護照號碼 
- 拉脫維亞個人程式碼 
- 立陶宛駕照編號 
- 立陶宛護照號碼 
- 立陶宛個人程式碼 
- Luxemburg 駕駛執照號碼 
- Luxemburg (自然個人的國家識別號碼)  
- Luxemburg 非自然人員 (的本國識別碼)  
- Luxemburg 護照號碼 
- 馬來西亞身分識別卡號碼 
- 馬爾他駕照編號 
- 馬爾他身分識別卡號碼 
- 馬爾他護照號碼 
- 馬爾他納稅識別碼編號 
- 荷蘭公民服務 (BSN) 號碼 
- 荷蘭駕駛執照號碼 
- 荷蘭護照號碼 
- 荷蘭稅務識別號碼 
- 荷蘭增值納稅號碼 
- 紐西蘭銀行帳戶號碼 
- 紐西蘭駕駛執照號碼 
- 紐西蘭 Inland 收入數目 
- 紐西蘭健康情況號碼的部 
- 紐西蘭社交 Welfare 號碼 
- 挪威身分識別號碼 
- 菲律賓統一多用途識別碼號碼 
- 波蘭駕照編號 
- 波蘭身分證明卡 
- 波蘭國民身分證 (PESEL) 
- 波蘭護照 
- 波蘭納稅識別號碼 
- 波蘭文 REGON 編號 
- 葡萄牙公民證號碼 
- 葡萄牙駕駛執照號碼 
- 葡萄牙護照號碼 
- 葡萄牙納稅識別號碼 
- 羅馬尼亞駕照編號 
- 羅馬尼亞護照號碼 
- 羅馬尼亞個人數值碼 (CNP)  
-  (國內) 的俄文護照號碼 
-  (國際) 的俄文護照號碼 
- 沙烏地阿拉伯國際身分識別 
- 新加坡國家註冊身分識別卡 (NRIC) 號碼 
- 斯洛伐克駕照編號 
- 斯洛伐克護照號碼 
- 斯洛伐克個人號碼 
- 斯洛維尼亞駕照編號 
- 斯洛維尼亞護照號碼 
- 斯洛維尼亞納稅識別號碼 
- 斯洛維尼亞唯一主公民號碼 
- 南非識別號碼 
- 韓國居民登記號碼 
- 西班牙 DNI 
- 西班牙駕照編號 
- 西班牙護照號碼 
- 西班牙社會安全號碼 (SSN) 
- 西班牙納稅識別號碼 
- SQL Server 連接字串 
- 瑞典駕駛執照號碼 
- 瑞典國民身分證號 
- 瑞典護照號碼 
- 瑞典納稅識別號碼 
- SWIFT 代碼 
- 瑞士社會安全號碼 AHV 
- 臺灣國家 ID 
- 臺灣護照號碼 
- 臺灣居民憑證 (ARC/TARC)  
- 泰國人口識別碼 
- 土耳其國身分識別號碼 
- 英國駕照號碼 
- 英國選民名冊編號 
- 英國國民健保服務號碼 
- 英國國民保險號碼 (NINO) 
- 英國。 唯一的納稅人參考編號 
- 美國/英國 護照號碼 
- 美國銀行帳戶號碼 
- 美國駕駛執照號碼 
- ITIN) 的美國個別納稅人識別號碼 ( 
-  (SSN) 的 U.S. 社會安全號碼 
-  (國內) 的烏克蘭護照號碼 
-  (國際) 的烏克蘭護照號碼 
 
請注意，除了上述現成的敏感資訊類型之外，也會偵測自訂的機密資訊類型

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a>跨 Microsoft 應用程式的 DLP 原則提示的支援清單

|**應用程式和平臺**|**DLP 原則提示支援**|**支援的敏感資訊類型**|**支援的謂語和動作**|**Comments**|
|:--|:--|:--|:--|:--|
|**Outlook Web Access**|:::image type="icon" source="../media/rightmrk.png" border="false":::|全部|Subset|請參閱 [資料遺失防護原則提示參考](#data-loss-prevention-policy-tips-reference)|
|**Outlook Win32 (Outlook 2013 及以上)**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subset|Subset|請參閱 [outlook 2013 和更新版本支援僅顯示某些條件和例外狀況的原則提示](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) ，以及 [outlook 2013 和更新版本支援顯示只](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-sensitive-information-types) 針對敏感資訊類型支援的原則提示，以及支援在 OUTLOOK Win32 上顯示 DLP 原則提示的 dlp 條件及動作的詳細資料。|
|**Outlook Mobile (iOS、Android) /Outlook Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|無|無|Outlook mobile 不支援 DLP 原則秘訣|
|**適用于商務網頁用戶端的 Sharepoint Online/單一磁片磁碟機**|:::image type="icon" source="../media/rightmrk.png" border="false":::|全部|DLP 中的所有 SPO/ODB 謂語和動作||
|**適用于 Business Win32 用戶端的 Sharepoint Win32/單一磁片磁碟機**|:::image type="icon" source="../media/crsmrk.png" border="false":::|無|無|Sharepoint 或 OneDrive 桌面用戶端應用程式不支援 DLP 原則提示|
|**Word、Excel、Powerpoint Web 用戶端**|:::image type="icon" source="../media/rightmrk.png" border="false":::|全部|DLP 中的所有 SPO/ODB 謂語和動作|如果檔主控于 SPO 或 ODB web app 上，且已加蓋 DLP 原則，則支援 DLP 原則提示。|
|**Word、Excel、Powerpoint Mobile 用戶端**|:::image type="icon" source="../media/crsmrk.png" border="false":::|無|無|Office 行動應用程式不支援 DLP 原則秘訣。|
|**小組 Web/小組的桌面/小組行動/小組 Mac**|:::image type="icon" source="../media/rightmrk.png" border="false":::|全部|DLP 原則中的所有團隊謂語|當郵件標示為「此郵件已標記為「已標示」時，就會顯示原則提示。 我可以做什麼？ 按一下連結時，使用者可以查看偵測到的敏感資訊類型，並在系統管理員允許的情況下，覆寫或報告問題。請注意，檔案不會顯示任何原則提示。 當收件者嘗試存取檔時，如果不允許存取權，他們可能會遭到拒絕存取。|
|**Win32 端點裝置**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subset|DLP 原則中的所有端點 DLP 謂詞和動作|[在端點上查看資料遺失防護支援僅限某些敏感資訊類型的原則秘訣](#data-loss-prevention-on-endpoint-supports-policy-tips-for-only-some-sensitive-information-types)|
|**Mac 裝置**|:::image type="icon" source="../media/crsmrk.png" border="false":::|無|無|目前無法在 Mac 裝置上強制進行資料遺失防護|
|**協力廠商 cloud app**|:::image type="icon" source="../media/crsmrk.png" border="false":::|無|無|資料外洩防護|
|**部署**|:::image type="icon" source="../media/crsmrk.png" border="false":::|無|無||
|**Word、Excel、Powerpoint Win32 用戶端**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Subset|Subset|WXP 用戶端應用程式的原則提示可用於儲存在 Sharepoint Online 上的檔或一個用於商務用的磁片磁碟機，以取得完全符合下列條件的所有 DLP 原則，或 DLP 原則中的其中一個條件或動作的子集：</br> <ul><li>內容包含機密資訊類型</li><li>存取範圍 (內容是內部或外部共用) </li><li>通知使用者 (原則提示/使用者通知) </li><li>封鎖所有人</li><li>事件報告</li></ul></br> 如果有任何其他條件或動作出現，該原則的 DLP 原則提示就不會出現在 Word、Excel 或 PowerPoint 的桌面應用程式中。|
||||||