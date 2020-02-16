---
title: 將 IRM 設定為使用內部部署 AD RMS 伺服器
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: 本主題示範如何設定 IRM 以使用 AD RMS 伺服器。
ms.openlocfilehash: d9d1dee8ca0992f1e2f9cb344baba4f245d3ca37
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078493"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a><span data-ttu-id="612f1-103">將 IRM 設定為使用內部部署 AD RMS 伺服器</span><span class="sxs-lookup"><span data-stu-id="612f1-103">Configure IRM to use an on-premises AD RMS server</span></span>
  
<span data-ttu-id="612f1-104">與內部部署搭配使用，資訊版權管理 (IRM) 設定 Exchange Online 中使用 Active Directory Rights Management Services (AD RMS)，在 Windows Server 2008 和更新版本的資訊保護技術。</span><span class="sxs-lookup"><span data-stu-id="612f1-104">For use with on-premises deployments, Information Rights Management (IRM) in Exchange Online uses Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later.</span></span> <span data-ttu-id="612f1-105">系統會藉由將 AD RMS 權限原則範本套用至電子郵件，將 IRM 保護套用至電子郵件。</span><span class="sxs-lookup"><span data-stu-id="612f1-105">IRM protection is applied to email by applying an AD RMS rights policy template to an email message.</span></span> <span data-ttu-id="612f1-106">權限會附加到郵件本身，以便進行保護作業的線上及離線和內部和外部組織的防火牆。</span><span class="sxs-lookup"><span data-stu-id="612f1-106">Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.</span></span>
  
<span data-ttu-id="612f1-107">本主題示範如何設定 IRM 以使用 AD RMS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="612f1-107">This topic shows you how to configure IRM to use an AD RMS server.</span></span> <span data-ttu-id="612f1-108">如需使用 Office 365 郵件加密與 Azure Active Directory 和 Azure Rights Management 的新功能的資訊，請參閱[Office 365 郵件加密常見問題集](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)。</span><span class="sxs-lookup"><span data-stu-id="612f1-108">For information about using the new capabilities for Office 365 Message Encryption with Azure Active Directory and Azure Rights Management, see the [Office 365 Message Encryption FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e).</span></span>
  
<span data-ttu-id="612f1-109">若要深入了解 Exchange Online 中的 IRM，請參閱 [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="612f1-109">To learn more about IRM in Exchange Online, see [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="612f1-110">開始之前有哪些須知？</span><span class="sxs-lookup"><span data-stu-id="612f1-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="612f1-111">完成此工作的預估時間：30 分鐘</span><span class="sxs-lookup"><span data-stu-id="612f1-111">Estimated time to complete this task: 30 minutes</span></span>

- <span data-ttu-id="612f1-112">您必須已獲指派權限，才能執行此程序或這些程序。</span><span class="sxs-lookup"><span data-stu-id="612f1-112">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="612f1-113">若要查看您需要的權限，請參閱[通訊原則及符合性權限](https://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)主題中的 「 資訊版權管理 」 項目。</span><span class="sxs-lookup"><span data-stu-id="612f1-113">To see what permissions you need, see the "Information Rights Management" entry in the [Messaging policy and compliance permissions](https://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 

- <span data-ttu-id="612f1-114">AD RMS 伺服器必須執行 Windows Server 2008 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="612f1-114">The AD RMS server must be running Windows Server 2008 or later.</span></span> <span data-ttu-id="612f1-115">如需如何部署 AD RMS 的詳細資訊，請參閱[安裝 AD RMS 叢集](https://go.microsoft.com/fwlink/?LinkId=210873)。</span><span class="sxs-lookup"><span data-stu-id="612f1-115">For details about how to deploy AD RMS, see [Installing an AD RMS Cluster](https://go.microsoft.com/fwlink/?LinkId=210873).</span></span>

- <span data-ttu-id="612f1-116">如需如何安裝及設定 Windows PowerShell 及連線到服務的詳細資料，請參閱[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)。</span><span class="sxs-lookup"><span data-stu-id="612f1-116">For details about how to install and configure Windows PowerShell and connect to the service, see [Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span></span>

- <span data-ttu-id="612f1-117">如需適用於本主題中程序的快速鍵相關資訊，請參閱 [Exchange Online 中 Exchange 系統管理中心的鍵盤快速鍵](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="612f1-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="612f1-118">有問題嗎？</span><span class="sxs-lookup"><span data-stu-id="612f1-118">Having problems?</span></span> <span data-ttu-id="612f1-119">在 Exchange 論壇中尋求協助。</span><span class="sxs-lookup"><span data-stu-id="612f1-119">Ask for help in the Exchange forums.</span></span> <span data-ttu-id="612f1-120">論壇的網址為：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="612f1-120">Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="how-do-you-do-this"></a><span data-ttu-id="612f1-121">該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="612f1-121">How do you do this?</span></span>
<span data-ttu-id="612f1-122"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="612f1-122"><a name="sectionSection1"> </a></span></span>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a><span data-ttu-id="612f1-123">步驟 1：使用 AD RMS 主控台從 AD RMS 伺服器匯出信任的發行網域 (TPD)</span><span class="sxs-lookup"><span data-stu-id="612f1-123">Step 1: Use the AD RMS console to export a trusted publishing domain (TPD) from an AD RMS server</span></span>

<span data-ttu-id="612f1-p106">第一個步驟是將信任的發行網域 (TPD) 從內部部署 AD RMS 伺服器匯出至 XML 檔案。TPD 含有以下使用 RMS 功能所需的設定：</span><span class="sxs-lookup"><span data-stu-id="612f1-p106">The first step is to export a trusted publishing domain (TPD) from the on-premises AD RMS server to an XML file. The TPD contains the following settings needed to use RMS features:</span></span>
  
- <span data-ttu-id="612f1-126">用於簽署憑證和授權及予以加密的伺服器授權人憑證</span><span class="sxs-lookup"><span data-stu-id="612f1-126">The server licensor certificate (SLC) used for signing and encrypting certificates and licenses</span></span>

- <span data-ttu-id="612f1-127">用於授權和發行的 URL</span><span class="sxs-lookup"><span data-stu-id="612f1-127">The URLs used for licensing and publishing</span></span>

- <span data-ttu-id="612f1-128">以 TPD 特定的 SLC 建立的 AD RMS 權限原則範本</span><span class="sxs-lookup"><span data-stu-id="612f1-128">The AD RMS rights policy templates that were created with the specific SLC for that TPD</span></span>

<span data-ttu-id="612f1-129">當您匯入 TPD 時，已儲存並保護在 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="612f1-129">When you import the TPD, it's stored and protected in Exchange Online.</span></span>
  
1. <span data-ttu-id="612f1-130">開啟 Active Directory Rights Management Services 主控台，然後展開 AD RMS 叢集。</span><span class="sxs-lookup"><span data-stu-id="612f1-130">Open the Active Directory Rights Management Services console, and then expand the AD RMS cluster.</span></span>

2. <span data-ttu-id="612f1-131">在主控台樹狀目錄中，展開 **[信任原則]**，然後按一下 **[信任的發行網域]**。</span><span class="sxs-lookup"><span data-stu-id="612f1-131">In the console tree, expand **Trust Policies**, and then click **Trusted Publishing Domains**.</span></span>

3. <span data-ttu-id="612f1-132">在結果窗格中，選取您想要匯出之網域的憑證。</span><span class="sxs-lookup"><span data-stu-id="612f1-132">In the results pane, select the certificate for the domain you want to export.</span></span>

4. <span data-ttu-id="612f1-133">在 **[動作]** 窗格中按一下 **[匯出信任的發行網域]**。</span><span class="sxs-lookup"><span data-stu-id="612f1-133">In the **Actions** pane, click **Export Trusted Publishing Domain**.</span></span>

5. <span data-ttu-id="612f1-134">在 **[發行網域檔案]** 方塊中按一下 **[另存新檔]**，將檔案儲存至本機電腦上的特定位置。</span><span class="sxs-lookup"><span data-stu-id="612f1-134">In the **Publishing domain file** box, click **Save As** to save the file to a specific location on the local computer.</span></span> <span data-ttu-id="612f1-135">輸入檔案名稱，並確定指定`.xml`檔案名稱副檔名，然後按一下 [**儲存**。</span><span class="sxs-lookup"><span data-stu-id="612f1-135">Type a file name, making sure to specify the  `.xml` file name extension, and then click **Save**.</span></span>

6. <span data-ttu-id="612f1-p108">在 **[密碼]** 和 **[確認密碼]** 方塊中，輸入將用來加密信任發行網域檔案的強式密碼。當您將 TPD 匯入雲端架構電子郵件組織時，就必須指定這個密碼。</span><span class="sxs-lookup"><span data-stu-id="612f1-p108">In the **Password** and **Confirm Password** boxes, type a strong password that will be used to encrypt the trusted publishing domain file. You will have to specify this password when you import the TPD to your cloud-based email organization.</span></span> 

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a><span data-ttu-id="612f1-138">步驟 2： 使用 Exchange 管理命令介面將 TPD 匯入 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="612f1-138">Step 2: Use the Exchange Management Shell to import the TPD to Exchange Online</span></span>

<span data-ttu-id="612f1-139">將 TPD 匯出至 XML 檔案之後，您就必須將它匯入 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="612f1-139">After the TPD is exported to an XML file, you have to import it to Exchange Online.</span></span> <span data-ttu-id="612f1-140">匯入 TPD 時，也會一併匯入組織的 AD RMS 範本。</span><span class="sxs-lookup"><span data-stu-id="612f1-140">When a TPD is imported, your organization's AD RMS templates are also imported.</span></span> <span data-ttu-id="612f1-141">匯入第一個 TPD 時，它會成為雲端架構組織的預設 TPD。</span><span class="sxs-lookup"><span data-stu-id="612f1-141">When the first TPD is imported, it becomes the default TPD for your cloud-based organization.</span></span> <span data-ttu-id="612f1-142">如果您匯入了其他 TPD，可以使用 **Default** 參數，讓它成為提供給使用者的預設 TPD。</span><span class="sxs-lookup"><span data-stu-id="612f1-142">If you import another TPD, you can use the **Default** switch to make it the default TPD that is available to users.</span></span> 
  
<span data-ttu-id="612f1-143">若要匯入 TPD，請在 Windows PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="612f1-143">To import the TPD, run the following command in Windows PowerShell:</span></span>
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

<span data-ttu-id="612f1-144">您可以取得值， _ExtranetLicensingUrl_和_IntranetLicensingUrl_參數，在 [Active Directory Rights Management Services 主控台。</span><span class="sxs-lookup"><span data-stu-id="612f1-144">You can obtain the values for the  _ExtranetLicensingUrl_ and  _IntranetLicensingUrl_ parameters in the Active Directory Rights Management Services console.</span></span> <span data-ttu-id="612f1-145">請在主控台樹狀目錄中選取 AD RMS 叢集。</span><span class="sxs-lookup"><span data-stu-id="612f1-145">Select the AD RMS cluster in the console tree.</span></span> <span data-ttu-id="612f1-146">授權 URL 就會顯示在結果窗格中。</span><span class="sxs-lookup"><span data-stu-id="612f1-146">The licensing URLs are displayed in the results pane.</span></span> <span data-ttu-id="612f1-147">當內容必須解密以及 Exchange Online 必須判斷要使用的 TPD 時，電子郵件用戶端就會使用這些 URL。</span><span class="sxs-lookup"><span data-stu-id="612f1-147">These URLs are used by email clients when content has to be decrypted and when Exchange Online needs to determine which TPD to use.</span></span>
  
<span data-ttu-id="612f1-148">當您執行此命令時，系統提示您輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="612f1-148">When you run this command, you'll be prompted for a password.</span></span> <span data-ttu-id="612f1-149">請輸入您從 AD RMS 伺服器匯出 TPD 時所指定的密碼。</span><span class="sxs-lookup"><span data-stu-id="612f1-149">Enter the password that you specified when you exported the TPD from your AD RMS server.</span></span>
  
<span data-ttu-id="612f1-p112">例如，下列命令會使用您從 AD RMS 伺服器匯出並儲存至系統管理員帳戶桌面的 XML 檔案來匯入名為 Exported TPD 的 TPD。Name 參數是用來指定 TPD 的名稱。</span><span class="sxs-lookup"><span data-stu-id="612f1-p112">For example, the following command imports the TPD named Exported TPD using the XML file that you exported from your AD RMS server and saved to the desktop of the Administrator account. The Name parameter is used to specify a name to the TPD.</span></span>
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

<span data-ttu-id="612f1-152">如需詳細的語法及參數資訊，請參閱 [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx)。</span><span class="sxs-lookup"><span data-stu-id="612f1-152">For detailed syntax and parameter information, see [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="612f1-153">如何才能了解此步驟是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="612f1-153">How do you know this step worked?</span></span>

<span data-ttu-id="612f1-154">若要確認您已成功匯入 TPD，請執行**Get-rmstrustedpublishingdomain**指令程式來擷取 Exchange Online 組織中的 Tpd。</span><span class="sxs-lookup"><span data-stu-id="612f1-154">To verify that you have successfully imported the TPD, run the **Get-RMSTrustedPublishingDomain** cmdlet to retrieve TPDs in your Exchange Online organization.</span></span> <span data-ttu-id="612f1-155">如需詳細資料，請參閱 [Get-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx) 中的範例。</span><span class="sxs-lookup"><span data-stu-id="612f1-155">For details, see the examples in [Get-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx).</span></span>
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a><span data-ttu-id="612f1-156">步驟 3： 使用 Exchange 管理命令介面來發佈 AD RMS 權限原則範本</span><span class="sxs-lookup"><span data-stu-id="612f1-156">Step 3: Use the Exchange Management Shell to distribute an AD RMS rights policy template</span></span>

<span data-ttu-id="612f1-157">匯入 TPD 之後，您必須確定 AD RMS 權限原則範本已發佈。</span><span class="sxs-lookup"><span data-stu-id="612f1-157">After you import the TPD, you must make sure an AD RMS rights policy template is distributed.</span></span> <span data-ttu-id="612f1-158">看到 Outlook 的網頁 （原先稱為 Outlook Web App） 使用者，可以再套用電子郵件訊息的範本已發佈的範本。</span><span class="sxs-lookup"><span data-stu-id="612f1-158">A distributed template is visible to Outlook on the web (formerly known as Outlook Web App) users, who can then apply the templates to an email message.</span></span>
  
<span data-ttu-id="612f1-159">若要傳回預設 TPD 包含的所有範本清單，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="612f1-159">To return a list of all templates contained in the default TPD, run the following command:</span></span>
  
```powershell
Get-RMSTemplate -Type All | fl
```

<span data-ttu-id="612f1-160">如果_Type_參數的值是`Archived`，使用者看不到該範本。</span><span class="sxs-lookup"><span data-stu-id="612f1-160">If the value of the  _Type_ parameter is  `Archived`, the template isn't visible to users.</span></span> <span data-ttu-id="612f1-161">只有已發佈的範本的預設 TPD 中可用的網頁型 Outlook 中。</span><span class="sxs-lookup"><span data-stu-id="612f1-161">Only distributed templates in the default TPD are available in Outlook on the web.</span></span>
  
<span data-ttu-id="612f1-162">若要發佈範本，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="612f1-162">To distribute a template, run the following command:</span></span>
  
```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

<span data-ttu-id="612f1-163">例如，下列命令會匯入 Company Confidential 範本。</span><span class="sxs-lookup"><span data-stu-id="612f1-163">For example, the following command imports the Company Confidential template.</span></span>
  
```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

<span data-ttu-id="612f1-164">如需詳細的語法及參數資訊，請參閱 [Get-RMSTemplate](https://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) 與 [Set-RMSTemplate](https://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx)。</span><span class="sxs-lookup"><span data-stu-id="612f1-164">For detailed syntax and parameter information, see [Get-RMSTemplate](https://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) and [Set-RMSTemplate](https://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx).</span></span>
  
<span data-ttu-id="612f1-165">**不要轉寄範本**</span><span class="sxs-lookup"><span data-stu-id="612f1-165">**The Do Not Forward template**</span></span>
  
<span data-ttu-id="612f1-166">當您將預設 TPD 從內部部署組織匯入 Exchange Online 時，會匯入名為 **[不要轉寄]** 的 AD RMS 權限原則範本。</span><span class="sxs-lookup"><span data-stu-id="612f1-166">When you import the default TPD from your on-premises organization into Exchange Online, one AD RMS rights policy template named **Do Not Forward** is imported.</span></span> <span data-ttu-id="612f1-167">根據預設，當您匯入預設 TPD 時，系統會發佈此範本。</span><span class="sxs-lookup"><span data-stu-id="612f1-167">By default, this template is distributed when you import the default TPD.</span></span> <span data-ttu-id="612f1-168">但是，您無法使用 **Set-RMSTemplate** 指令程式來修改 **[不要轉寄]** 範本。</span><span class="sxs-lookup"><span data-stu-id="612f1-168">You can't use the **Set-RMSTemplate** cmdlet to modify the **Do Not Forward** template.</span></span> 
  
<span data-ttu-id="612f1-p117">當 **[不要轉寄]** 範本套用至郵件時，只有郵件中所列的收件者才能讀取郵件。此外，收件者無法進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="612f1-p117">When the **Do Not Forward** template is applied to a message, only the recipients addressed in the message can read the message. Additionally, recipients can't do the following:</span></span>
  
- <span data-ttu-id="612f1-171">將郵件轉寄給其他人員。</span><span class="sxs-lookup"><span data-stu-id="612f1-171">Forward the message to another person.</span></span>

- <span data-ttu-id="612f1-172">複製郵件的內容。</span><span class="sxs-lookup"><span data-stu-id="612f1-172">Copy content from the message.</span></span>

- <span data-ttu-id="612f1-173">列印郵件。</span><span class="sxs-lookup"><span data-stu-id="612f1-173">Print the message.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="612f1-174">**[不要轉寄]** 範本無法防止使用者透過協力廠商螢幕擷取程式複製郵件中的資訊，也無法防止使用者手動抄錄資訊。</span><span class="sxs-lookup"><span data-stu-id="612f1-174">The **Do Not Forward** template can't prevent information in a message from being copied with third-party screen capture programs, cameras, or users manually transcribing the information</span></span> 
  
<span data-ttu-id="612f1-175">您可以在內部部署組織中的 AD RMS 伺服器上建立其他 AD RMS 權限原則範本，以符合您的 IRM 保護需求。</span><span class="sxs-lookup"><span data-stu-id="612f1-175">You can create additional AD RMS rights policy templates on the AD RMS server in your on-premises organization to meet your IRM protection requirements.</span></span> <span data-ttu-id="612f1-176">如果您建立了其他 AD RMS 權限原則範本，就必須再次從內部部署 AD RMS 伺服器匯出 TPD，然後在雲端架構電子郵件組織中重新整理 TPD。</span><span class="sxs-lookup"><span data-stu-id="612f1-176">If you create additional AD RMS rights policy templates, you have to export the TPD from the on-premises AD RMS server again and refresh the TPD in the cloud-based email organization.</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="612f1-177">如何才能了解此步驟是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="612f1-177">How do you know this step worked?</span></span>

<span data-ttu-id="612f1-178">若要確認您已成功發佈和 AD RMS 權限原則範本，請執行**Get-rmstemplate**指令程式，以檢查範本的內容。</span><span class="sxs-lookup"><span data-stu-id="612f1-178">To verify that you have successfully distributed and AD RMS rights policy template, run the **Get-RMSTemplate** cmdlet to check the template's properties.</span></span> <span data-ttu-id="612f1-179">如需詳細資料，請參閱 [Get-RMSTemplate](https://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) 中的範例。</span><span class="sxs-lookup"><span data-stu-id="612f1-179">For details, see the examples in [Get-RMSTemplate](https://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx).</span></span>
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a><span data-ttu-id="612f1-180">步驟 4： 使用 Exchange 管理命令介面來啟用 IRM</span><span class="sxs-lookup"><span data-stu-id="612f1-180">Step 4: Use the Exchange Management Shell to enable IRM</span></span>

<span data-ttu-id="612f1-181">匯入 TPD 並發佈 AD RMS 權限原則範本之後，請執行以下命令以針對雲端架構電子郵件組織啟用 IRM。</span><span class="sxs-lookup"><span data-stu-id="612f1-181">After you import the TPD and distribute an AD RMS rights policy template, run the following command to enable IRM for your cloud-based email organization.</span></span>
  
```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

<span data-ttu-id="612f1-182">如需詳細的語法及參數資訊，請參閱 [Set-IRMConfiguration](https://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="612f1-182">For detailed syntax and parameter information, see [Set-IRMConfiguration](https://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="612f1-183">如何才能了解此步驟是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="612f1-183">How do you know this step worked?</span></span>

<span data-ttu-id="612f1-184">若要確認您已成功啟用 IRM，請執行[Get-irmconfiguration](https://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx)指令程式，以檢查 Exchange Online 組織中的 IRM 組態。</span><span class="sxs-lookup"><span data-stu-id="612f1-184">To verify that you have successfully enabled IRM, run the [Get-IRMConfiguration](https://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) cmdlet to check IRM configuration in the Exchange Online organization.</span></span>
  
## <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="612f1-185">如何才能了解此工作是否正常運作？</span><span class="sxs-lookup"><span data-stu-id="612f1-185">How do you know this task worked?</span></span>
<span data-ttu-id="612f1-186"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="612f1-186"><a name="sectionSection2"> </a></span></span>

<span data-ttu-id="612f1-187">若要確認您是否已成功匯入 TPD 並啟用 IRM，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="612f1-187">To verify that you have successfully imported the TPD and enabled IRM, do the following:</span></span>
  
- <span data-ttu-id="612f1-188">使用 **Test-IRMConfiguration** 指令程式來測試 IRM 功能。</span><span class="sxs-lookup"><span data-stu-id="612f1-188">Use the **Test-IRMConfiguration** cmdlet to test IRM functionality.</span></span> <span data-ttu-id="612f1-189">如需詳細資訊，請參閱[Test-irmconfiguration](https://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx)中的 「 範例 1 」。</span><span class="sxs-lookup"><span data-stu-id="612f1-189">For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx).</span></span>

- <span data-ttu-id="612f1-190">撰寫新郵件在 outlook 網頁版和 IRM 保護，即可以選取 [**設定權限**選項從延伸功能表 (![更多選項圖示](../media/ITPro-EAC-MoreOptionsIcon.gif))。</span><span class="sxs-lookup"><span data-stu-id="612f1-190">Compose a new message in Outlook on the web and IRM-protect it by selecting **Set permissions** option from the extended menu ( ![More Options Icon](../media/ITPro-EAC-MoreOptionsIcon.gif)).</span></span>
