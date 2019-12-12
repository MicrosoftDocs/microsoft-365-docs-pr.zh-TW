---
title: 偵測並修復 Outlook 規則及自訂表單資料隱碼攻擊的 Office 365 中
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 了解如何識別並修復 Outlook 規則及 Office 365 中的自訂表單資料隱碼攻擊
ms.openlocfilehash: d5f4a653463f4105df025bf29679465ca5335098
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970789"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks-in-office-365"></a><span data-ttu-id="93887-103">偵測並修復 Office 365 中 Outlook 規則與自訂表單插入式攻擊</span><span class="sxs-lookup"><span data-stu-id="93887-103">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>

<span data-ttu-id="93887-104">**摘要**了解如何識別並修復 Outlook 規則及 Office 365 中的自訂表單資料隱碼攻擊。</span><span class="sxs-lookup"><span data-stu-id="93887-104">**Summary** Learn how to recognize and remediate the Outlook rules and custom Forms injections attacks in Office 365.</span></span>

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a><span data-ttu-id="93887-105">什麼是 Outlook 規則及自訂表單資料隱碼攻擊？</span><span class="sxs-lookup"><span data-stu-id="93887-105">What is the Outlook Rules and Custom Forms injection attack?</span></span>

<span data-ttu-id="93887-106">攻擊者已在您的租用破壞帳戶，並取得之後，那里即將試，並建立的方式來保持連絡或回復之後找出並移除的方式。</span><span class="sxs-lookup"><span data-stu-id="93887-106">After an attacker has breached an account in your tenancy and gets in, they're are going to try and establish a way to stay in or a way to get back in after they are discovered and removed.</span></span> <span data-ttu-id="93887-107">這稱為建立持續性的機制。</span><span class="sxs-lookup"><span data-stu-id="93887-107">This is called establishing a persistence mechanism.</span></span> <span data-ttu-id="93887-108">他們可以執行此作業的兩種方法是藉由利用 Outlook 規則或插入至 Outlook 的自訂表單。</span><span class="sxs-lookup"><span data-stu-id="93887-108">Two ways that they can do this are by exploiting Outlook rules or by injecting custom forms into Outlook.</span></span>
<span data-ttu-id="93887-109">在這兩種情況下，規則] 或 [表單同步處理自雲端服務下桌面用戶端上，以便為完整的格式並重新安裝用戶端軟體不會排除資料隱碼攻擊的機制。</span><span class="sxs-lookup"><span data-stu-id="93887-109">In both cases, the rule or form is synced from the cloud service down to the desktop client, so a full format and re-install of the client software doesn't eliminate the injection mechanism.</span></span> <span data-ttu-id="93887-110">這是因為 Outlook 用戶端軟體重新連線到雲端信箱時它將會重新下載規則與從雲端的表單。</span><span class="sxs-lookup"><span data-stu-id="93887-110">This is because when the Outlook client software reconnects to the mailbox in the cloud it will re-download the rules and forms from the cloud.</span></span> <span data-ttu-id="93887-111">一旦規則及表單中的位置，攻擊者就會使用它們來執行遠端或自訂的程式碼，通常是在本機電腦上安裝惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="93887-111">Once the rules and forms are in place, the attacker uses them to execute remote or custom code, usually to install malware on the local machine.</span></span> <span data-ttu-id="93887-112">惡意程式碼再重新竊取認證，或執行其他非法活動。</span><span class="sxs-lookup"><span data-stu-id="93887-112">The malware then re-steals credentials or performs other illicit activity.</span></span>
<span data-ttu-id="93887-113">好消息是，如果您保留您修補的最新版本的用戶端，您不會為受到為目前的 Outlook 用戶端預設會封鎖這兩個機制。</span><span class="sxs-lookup"><span data-stu-id="93887-113">The good news here is that if you keep your clients patched to the latest version, you are not vulnerable to the threat as current Outlook client defaults block both mechanisms.</span></span>

<span data-ttu-id="93887-114">攻擊通常請依循下列模式：</span><span class="sxs-lookup"><span data-stu-id="93887-114">The attacks typically follow these patterns:</span></span>

<span data-ttu-id="93887-115">**利用規則**：</span><span class="sxs-lookup"><span data-stu-id="93887-115">**The Rules Exploit**:</span></span>

1. <span data-ttu-id="93887-116">攻擊者竊取的使用者名稱和密碼的其中一個使用者。</span><span class="sxs-lookup"><span data-stu-id="93887-116">The attacker steals the username and password of one of your users.</span></span>

2. <span data-ttu-id="93887-117">攻擊者然後登入該使用者的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="93887-117">The attacker then signs in to that users Exchange mailbox.</span></span> <span data-ttu-id="93887-118">信箱可以是在 Exchange online 或 Exchange 內部部署。</span><span class="sxs-lookup"><span data-stu-id="93887-118">The mailbox can either be in Exchange online or in Exchange on-premises.</span></span>

3. <span data-ttu-id="93887-119">攻擊者然後建立信箱信箱可接收電子郵件符合準則的規則時所觸發的轉寄規則。</span><span class="sxs-lookup"><span data-stu-id="93887-119">The attacker then creates a forwarding rule in the mailbox that is triggered when the mailbox receives an email that matches the criteria of the rule.</span></span> <span data-ttu-id="93887-120">規則的條件以及觸發電子郵件的內容是特製彼此。</span><span class="sxs-lookup"><span data-stu-id="93887-120">The criteria of rule and the contents of the trigger email are tailor-made for each other.</span></span>

4. <span data-ttu-id="93887-121">攻擊者通常使用其信箱的使用者所傳送的觸發電子郵件。</span><span class="sxs-lookup"><span data-stu-id="93887-121">The attacker sends the trigger email to the user who is using their mailbox normally.</span></span>

5. <span data-ttu-id="93887-122">收到電子郵件時，就會觸發規則。</span><span class="sxs-lookup"><span data-stu-id="93887-122">When the email is received, the rule is triggered.</span></span> <span data-ttu-id="93887-123">規則的巨集指令通常是以啟動遠端 (WebDAV) 伺服器上的應用程式。</span><span class="sxs-lookup"><span data-stu-id="93887-123">The action of the rule is usually to launch an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="93887-124">應用程式通常惡意程式碼、 [Powershell 帝國](https://www.powershellempire.com/)，例如在本機上安裝在使用者的電腦。</span><span class="sxs-lookup"><span data-stu-id="93887-124">The application typically installs malware, such as [Powershell Empire](https://www.powershellempire.com/), locally on the user's machine.</span></span>

7. <span data-ttu-id="93887-125">惡意程式碼讓駭客重新竊取使用者的使用者名稱與密碼或從本機電腦的其他認證，並執行其他惡意活動。</span><span class="sxs-lookup"><span data-stu-id="93887-125">The malware allows the attacker to re-steal the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

<span data-ttu-id="93887-126">**利用表單**：</span><span class="sxs-lookup"><span data-stu-id="93887-126">**The Forms Exploit**:</span></span>

1. <span data-ttu-id="93887-127">攻擊者竊取的使用者名稱和密碼的其中一個使用者。</span><span class="sxs-lookup"><span data-stu-id="93887-127">The attacker steals the username and password of one of your users.</span></span>

2. <span data-ttu-id="93887-128">攻擊者然後登入該使用者的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="93887-128">The attacker then sign in to that users Exchange mailbox.</span></span> <span data-ttu-id="93887-129">信箱可以是在 Exchange online 或 Exchange 內部部署。</span><span class="sxs-lookup"><span data-stu-id="93887-129">The mailbox can either be in Exchange online or in Exchange on-premises.</span></span>

3. <span data-ttu-id="93887-130">攻擊者再建立自訂郵件表單範本，並將它插入該使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="93887-130">The attacker then creates a custom mail form template and inserts it into the user's mailbox.</span></span> <span data-ttu-id="93887-131">當信箱可接收的電子郵件，需要載入自訂表單的信箱時，就會觸發自訂表單。</span><span class="sxs-lookup"><span data-stu-id="93887-131">The custom form is triggered when the mailbox receives an email that requires the mailbox to load the custom form.</span></span> <span data-ttu-id="93887-132">自訂表單和電子郵件的格式是特製彼此。</span><span class="sxs-lookup"><span data-stu-id="93887-132">The custom form and the format of email are tailor-made for each other.</span></span>
4. <span data-ttu-id="93887-133">攻擊者會觸發電子郵件傳送給通常使用其信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="93887-133">The attacker sends the trigger email to the user, who is using their mailbox normally.</span></span>

5. <span data-ttu-id="93887-134">載入表單時收到電子郵件時。</span><span class="sxs-lookup"><span data-stu-id="93887-134">When the email is received, the form is loaded.</span></span> <span data-ttu-id="93887-135">表單啟動遠端 (WebDAV) 伺服器上的應用程式。</span><span class="sxs-lookup"><span data-stu-id="93887-135">The form launches an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="93887-136">應用程式通常惡意程式碼、 [Powershell 帝國](https://www.powershellempire.com/)，例如在本機上安裝在使用者的電腦。</span><span class="sxs-lookup"><span data-stu-id="93887-136">The application typically installs malware, such as [Powershell Empire](https://www.powershellempire.com/), locally on the user's machine.</span></span>

7. <span data-ttu-id="93887-137">惡意程式碼讓駭客重新竊取使用者的使用者名稱與密碼或從本機電腦的其他認證，並執行其他惡意活動。</span><span class="sxs-lookup"><span data-stu-id="93887-137">The malware allows the attacker to re-steal the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a><span data-ttu-id="93887-138">查看規則及自訂表單資料隱碼攻擊看起來會像 Office 365？</span><span class="sxs-lookup"><span data-stu-id="93887-138">What a Rules and Custom Forms Injection attack might look like Office 365?</span></span>

<span data-ttu-id="93887-139">這些保存性機制不太可能會注意到您的使用者所且可能在某些情況下偶數會看不到它們。</span><span class="sxs-lookup"><span data-stu-id="93887-139">These persistence mechanisms are unlikely to be noticed by your users and may in some cases even be invisible to them.</span></span> <span data-ttu-id="93887-140">本文將告訴您如何尋找下面列出任何七個符號 （危害指標）。</span><span class="sxs-lookup"><span data-stu-id="93887-140">This article tells you how to look for any of the seven signs (Indicators of Compromise) listed below.</span></span> <span data-ttu-id="93887-141">如果您發現任何這些，您需要採取補救步驟。</span><span class="sxs-lookup"><span data-stu-id="93887-141">If you find any of these, you need to take remediation steps.</span></span>

- <span data-ttu-id="93887-142">規則的指標危害：</span><span class="sxs-lookup"><span data-stu-id="93887-142">Indicators of the Rules compromise:</span></span>

  - <span data-ttu-id="93887-143">規則動作是要啟動的應用程式。</span><span class="sxs-lookup"><span data-stu-id="93887-143">Rule Action is to start an application.</span></span>

  - <span data-ttu-id="93887-144">規則參考 EXE、 ZIP 或 URL。</span><span class="sxs-lookup"><span data-stu-id="93887-144">Rule References an EXE, ZIP, or URL.</span></span>

  - <span data-ttu-id="93887-145">在本機電腦中，尋找 [來自 Outlook PID 的新程序開始。</span><span class="sxs-lookup"><span data-stu-id="93887-145">On the local machine, look for new process starts that originate from the Outlook PID.</span></span>

- <span data-ttu-id="93887-146">自訂表單的指標危害：</span><span class="sxs-lookup"><span data-stu-id="93887-146">Indicators of the Custom forms compromise:</span></span>

  - <span data-ttu-id="93887-147">自訂表單存在另存為他們自己的郵件類別。</span><span class="sxs-lookup"><span data-stu-id="93887-147">Custom form present saved as their own message class.</span></span>

  - <span data-ttu-id="93887-148">郵件類別包含可執行程式碼。</span><span class="sxs-lookup"><span data-stu-id="93887-148">Message class contains executable code.</span></span>

  - <span data-ttu-id="93887-149">通常儲存在個人表單檔案庫] 或 [收件匣] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="93887-149">Usually stored in Personal Forms Library or Inbox folders.</span></span>

  - <span data-ttu-id="93887-150">表單是名為 IPM。附註。[自訂名稱]。</span><span class="sxs-lookup"><span data-stu-id="93887-150">Form is named IPM.Note.[custom name].</span></span>

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a><span data-ttu-id="93887-151">尋找這類攻擊的跡象，並確認它的步驟</span><span class="sxs-lookup"><span data-stu-id="93887-151">Steps for finding signs of this attack and confirming it</span></span>

<span data-ttu-id="93887-152">您可以使用下列兩種方法之一來確認攻擊：</span><span class="sxs-lookup"><span data-stu-id="93887-152">You can use either of these two methods to confirm the attack:</span></span>

- <span data-ttu-id="93887-153">手動檢查的規則和每個信箱使用 Outlook 用戶端的表單。</span><span class="sxs-lookup"><span data-stu-id="93887-153">Manually examine the rules and forms for each mailbox using the Outlook client.</span></span> <span data-ttu-id="93887-154">這個方法是徹底，但您只能用來檢查信箱使用者一次可以是相當耗時如果您有許多使用者檢查。</span><span class="sxs-lookup"><span data-stu-id="93887-154">This method is thorough, but you can only check mailbox user at a time which can be very time consuming if you have many users to check.</span></span> <span data-ttu-id="93887-155">它也可能導致您正在執行從存回之電腦的外洩。</span><span class="sxs-lookup"><span data-stu-id="93887-155">It can also result in a breach of the computer that you are running the check from.</span></span>

- <span data-ttu-id="93887-156">使用[Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 指令碼來自動傾印轉寄規則與自訂表單的每個使用者在您的租用中的所有郵件。</span><span class="sxs-lookup"><span data-stu-id="93887-156">Use the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script to automatically dump all the mail forwarding rules and custom forms for all the users in your tenancy.</span></span> <span data-ttu-id="93887-157">這是使用最少的額外負荷量的最快和最安全方法。</span><span class="sxs-lookup"><span data-stu-id="93887-157">This is the fastest and safest method with the least amount of overhead.</span></span>

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a><span data-ttu-id="93887-158">確認規則攻擊使用 Outlook 用戶端</span><span class="sxs-lookup"><span data-stu-id="93887-158">Confirm the Rules Attack Using the Outlook client</span></span>

1. <span data-ttu-id="93887-159">使用者以開啟使用者的 Outlook 用戶端。</span><span class="sxs-lookup"><span data-stu-id="93887-159">Open the users Outlook client as the user.</span></span> <span data-ttu-id="93887-160">使用者可能需要您在檢查其信箱上的規則的協助。</span><span class="sxs-lookup"><span data-stu-id="93887-160">The user may need your help in examining the rules on their mailbox.</span></span>

2. <span data-ttu-id="93887-161">請參閱[使用規則管理電子郵件訊息](https://support.office.com/article/c24f5dea-9465-4df4-ad17-a50704d66c59)文章如何在 Outlook 中開啟的規則介面上的程序。</span><span class="sxs-lookup"><span data-stu-id="93887-161">Refer to [Manage email messages by using rules](https://support.office.com/article/c24f5dea-9465-4df4-ad17-a50704d66c59) article for the procedures on how to open the rules interface in Outlook.</span></span>

3. <span data-ttu-id="93887-162">查詢規則，未建立使用者，或任何未預期的規則或規則的可疑的名稱。</span><span class="sxs-lookup"><span data-stu-id="93887-162">Look for rules that the user did not create, or any unexpected rules or rules with suspicious names.</span></span>

4. <span data-ttu-id="93887-163">規則動作的規則描述中尋找該開始和應用程式或參照。EXE、。ZIP 檔案，或啟動 URL。</span><span class="sxs-lookup"><span data-stu-id="93887-163">Look in the rule description for rule actions that start and application or refer to an .EXE, .ZIP file or to launching a URL.</span></span>

5. <span data-ttu-id="93887-164">尋找任何新的程序，開始使用 Outlook 處理序識別碼。</span><span class="sxs-lookup"><span data-stu-id="93887-164">Look for any new processes that start using the Outlook process ID.</span></span> <span data-ttu-id="93887-165">若要[尋找的程序識別碼](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="93887-165">Refer to [Find the Process ID](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).</span></span>

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a><span data-ttu-id="93887-166">若要確認表單的步驟來進行攻擊使用 Outlook 用戶端</span><span class="sxs-lookup"><span data-stu-id="93887-166">Steps to confirm the Forms attack using the Outlook client</span></span>

1. <span data-ttu-id="93887-167">使用者以開啟使用者的 Outlook 用戶端。</span><span class="sxs-lookup"><span data-stu-id="93887-167">Open the user Outlook client as the user.</span></span>

2. <span data-ttu-id="93887-168">請遵循使用者的 Outlook 版本中，[顯示 [開發人員] 索引標籤](https://support.office.com/article/e1192344-5e56-4d45-931b-e5fd9bea2d45)的步驟。</span><span class="sxs-lookup"><span data-stu-id="93887-168">Follow the steps in, [Show the Developer tab](https://support.office.com/article/e1192344-5e56-4d45-931b-e5fd9bea2d45) for the users version of Outlook.</span></span>

3. <span data-ttu-id="93887-169">在 Outlook 中開啟 [現在顯示開發人員] 索引標籤，然後按一下 [**設計表單**。</span><span class="sxs-lookup"><span data-stu-id="93887-169">Open the now visible developer tab in Outlook and click **design a form**.</span></span>

4. <span data-ttu-id="93887-170">從 [查詢] 清單**中**，選取 [**收件匣**。</span><span class="sxs-lookup"><span data-stu-id="93887-170">Select the **Inbox** from the **Look In** list.</span></span> <span data-ttu-id="93887-171">尋找任何自訂表單。</span><span class="sxs-lookup"><span data-stu-id="93887-171">Look for any custom forms.</span></span> <span data-ttu-id="93887-172">自訂表單很少，如果您有任何自訂表單完全，它是值得更深入的外觀。</span><span class="sxs-lookup"><span data-stu-id="93887-172">Custom forms are rare enough that if you have any custom forms at all, it is worth a deeper look.</span></span>

5. <span data-ttu-id="93887-173">調查任何自訂表單、 特別標示為隱藏。</span><span class="sxs-lookup"><span data-stu-id="93887-173">Investigate any custom forms, especially those marked as hidden.</span></span>

6. <span data-ttu-id="93887-174">開啟任何自訂表單，並在 [**表單**] 群組中按一下 [**檢視程式碼**，請參閱什麼執行時載入表單時。</span><span class="sxs-lookup"><span data-stu-id="93887-174">Open any custom forms and in the **Form** group click **View Code** to see what runs when the form is loaded.</span></span>

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a><span data-ttu-id="93887-175">若要確認的規則及表單的步驟來進行攻擊使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="93887-175">Steps to confirm the Rules and Forms attack using PowerShell</span></span>

<span data-ttu-id="93887-176">若要驗證規則的最簡單方式或自訂表單攻擊 」 會執行[Get AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 指令碼。</span><span class="sxs-lookup"><span data-stu-id="93887-176">The simplest way to verify a rules or custom forms attack is to run the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script.</span></span> <span data-ttu-id="93887-177">此指令碼連線至租用戶中的每個信箱和傾印的所有規則和表單到兩個.csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="93887-177">This script connects to every mailbox in your tenant and dumps all the rules and forms into two .csv files.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="93887-178">先決條件</span><span class="sxs-lookup"><span data-stu-id="93887-178">Pre-requisites</span></span>

<span data-ttu-id="93887-179">您必須擁有的全域系統管理員權限，因為指令碼連線至租用戶讀取的規則及表單中的每個信箱執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="93887-179">You will need to have a global administrator rights to run the script because the script connects to every mailbox in the tenancy to read the rules and forms.</span></span>

1. <span data-ttu-id="93887-180">登入您要執行的指令碼以本機系統管理員權限的電腦。</span><span class="sxs-lookup"><span data-stu-id="93887-180">Sign in to the machine that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="93887-181">下載或從 GitHub Get AllTenantRulesAndForms.ps1 指令碼複製到資料夾，會從中執行它。</span><span class="sxs-lookup"><span data-stu-id="93887-181">Download or copy the Get-AllTenantRulesAndForms.ps1 script from GitHub to a folder from which you will run it.</span></span> <span data-ttu-id="93887-182">指令碼會建立兩個日期加上戳記檔案，這個資料夾、 MailboxFormsExport-yyyy-公釐-dd.csv 及 MailboxRulesExport yyyy-公釐 dd.csv。</span><span class="sxs-lookup"><span data-stu-id="93887-182">The script will create two date stamped files to this folder, MailboxFormsExport-yyyy-mm-dd.csv, and MailboxRulesExport-yyyy-mm-dd.csv.</span></span>

3. <span data-ttu-id="93887-183">開啟身為系統管理員的 PowerShell 執行個體，然後開啟您儲存至指令碼的資料夾。</span><span class="sxs-lookup"><span data-stu-id="93887-183">Open a PowerShell instance as an administrator and open the folder you saved the script to.</span></span>

4. <span data-ttu-id="93887-184">執行此 PowerShell 命令列，如下所示`.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1</span><span class="sxs-lookup"><span data-stu-id="93887-184">Run this PowerShell command line as follows `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1</span></span>

#### <a name="interpreting-the-output"></a><span data-ttu-id="93887-185">解譯輸出</span><span class="sxs-lookup"><span data-stu-id="93887-185">Interpreting the output</span></span>

- <span data-ttu-id="93887-186">**MailboxRulesExport-*-yyyy-mm-dd*.csv**： 檢查巨集指令的條件，包括應用程式或可執行檔 （每個資料列的其中一個） 的規則：</span><span class="sxs-lookup"><span data-stu-id="93887-186">**MailboxRulesExport-*yyyy-mm-dd*.csv**: Examine the rules (one per row) for action conditions that include applications or executables:</span></span>

  - <span data-ttu-id="93887-187">**ActionType （欄 A）**： 如果您看到 「 ID_ACTION_CUSTOM 」 的值，此規則會可能惡意。</span><span class="sxs-lookup"><span data-stu-id="93887-187">**ActionType (column A)**: If you see the value "ID_ACTION_CUSTOM", the rule is likely malicious.</span></span>

  - <span data-ttu-id="93887-188">**IsPotentiallyMalicious （D 欄）**： 此值為"TRUE"，規則是否可能惡意。</span><span class="sxs-lookup"><span data-stu-id="93887-188">**IsPotentiallyMalicious (column D)**: If this value is "TRUE", the rule is likely malicious.</span></span>

  - <span data-ttu-id="93887-189">**ActionCommand （資料行 G）**： 這會列出應用程式或任何檔具有.exe、.zip 副檔名或參照至的 URL，不應該在那裡，項目規則是否可能惡意。</span><span class="sxs-lookup"><span data-stu-id="93887-189">**ActionCommand (column G)**: If this lists an application or any file with a .exe, .zip extension or an entry that refers to a URL, that is not supposed to be there, the rule is likely malicious.</span></span>

- <span data-ttu-id="93887-190">**MailboxFormsExport-*-yyyy-mm-dd*.csv**： 在 [一般] 自訂表單的用途是很少見。</span><span class="sxs-lookup"><span data-stu-id="93887-190">**MailboxFormsExport-*yyyy-mm-dd*.csv**: In general, the use of custom forms is very rare.</span></span> <span data-ttu-id="93887-191">如果您發現任何此活頁簿中，您會開啟該使用者的信箱，並檢查表單本身。</span><span class="sxs-lookup"><span data-stu-id="93887-191">If you find any in this workbook, you open that user's mailbox and examine the form itself.</span></span> <span data-ttu-id="93887-192">如果您的組織沒有不將它放有刻意，很可能是惡意。</span><span class="sxs-lookup"><span data-stu-id="93887-192">If your organization did not put it there intentionally, it is likely malicious.</span></span>

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a><span data-ttu-id="93887-193">如何停止和修復 Outlook 規則及表單攻擊</span><span class="sxs-lookup"><span data-stu-id="93887-193">How to stop and remediate the Outlook Rules and Forms attack</span></span>

<span data-ttu-id="93887-194">如果您發現這些攻擊的任何辨識項，補救很簡單，只要從信箱中刪除規則] 或 [表單。</span><span class="sxs-lookup"><span data-stu-id="93887-194">If you find any evidence of either of these attacks, remediation is simple, just delete the rule or form from the mailbox.</span></span> <span data-ttu-id="93887-195">您可以利用 Outlook 用戶端或使用遠端 PowerShell 移除的規則來進行此作業。</span><span class="sxs-lookup"><span data-stu-id="93887-195">You can do this with the Outlook client or using remote PowerShell to remove rules.</span></span>

### <a name="using-outlook"></a><span data-ttu-id="93887-196">使用 Outlook</span><span class="sxs-lookup"><span data-stu-id="93887-196">Using Outlook</span></span>

1. <span data-ttu-id="93887-197">識別使用者已與 Outlook 搭配使用的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="93887-197">Identify all the devices that the user has used with Outlook.</span></span> <span data-ttu-id="93887-198">他們將所有需要的潛在的惡意程式碼會清除。</span><span class="sxs-lookup"><span data-stu-id="93887-198">They will all need to be cleaned of potential malware.</span></span> <span data-ttu-id="93887-199">不允許使用者登入，並使用電子郵件，直到已清除所有的裝置。</span><span class="sxs-lookup"><span data-stu-id="93887-199">Do not allow the user to sign on and use email until all the devices are cleaned.</span></span>

2. <span data-ttu-id="93887-200">請依照下列每個裝置中[刪除規則](https://support.office.com/article/2f0e7139-f696-4422-8498-44846db9067f)的步驟。</span><span class="sxs-lookup"><span data-stu-id="93887-200">Follow the steps in [Delete a rule](https://support.office.com/article/2f0e7139-f696-4422-8498-44846db9067f) for each device.</span></span>

3. <span data-ttu-id="93887-201">如果您不確定相關的其他惡意程式碼存在，您可以設定的格式，並重新安裝在裝置上的所有軟體。</span><span class="sxs-lookup"><span data-stu-id="93887-201">If you are unsure about the presence of other malware, you can format and re-install all the software on the device.</span></span> <span data-ttu-id="93887-202">行動裝置的您可以依照製造商以將裝置重設成出廠預設值的影像。</span><span class="sxs-lookup"><span data-stu-id="93887-202">For mobile devices you can follow the manufacturers steps to reset the device to the factory image.</span></span>

4. <span data-ttu-id="93887-203">安裝最新版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="93887-203">Install the most up-to-date versions of Outlook.</span></span> <span data-ttu-id="93887-204">請記住，目前版本的 Outlook 預設會封鎖這兩種此類攻擊。</span><span class="sxs-lookup"><span data-stu-id="93887-204">Remember that the current version of Outlook blocks both types of this attack by default.</span></span>

5. <span data-ttu-id="93887-205">一旦已經移除所有的信箱的離線複本，重設使用者的密碼 （高品質其中會使用），如果已經尚未啟用 MFA，請遵循[Office 365 使用者設定多重要素驗證](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)] 中的步驟。</span><span class="sxs-lookup"><span data-stu-id="93887-205">Once all offline copies of the mailbox have been removed, reset the user's password (use a high-quality one) and follow the steps in [Setup multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) if MFA has not already been enabled.</span></span> <span data-ttu-id="93887-206">這可確保使用者的認證，不會公開透過其他方式 （例如網路釣魚或密碼重複使用）。</span><span class="sxs-lookup"><span data-stu-id="93887-206">This ensures that the user's credentials are not exposed via other means (such as phishing or password re-use).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="93887-207">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="93887-207">Using PowerShell</span></span>

<span data-ttu-id="93887-208">有兩個遠端 PowerShell 指令程式可移除或停用危險的規則。</span><span class="sxs-lookup"><span data-stu-id="93887-208">There are two remote PowerShell cmdlets you can use to remove or disable dangerous rules.</span></span> <span data-ttu-id="93887-209">請按照步驟。</span><span class="sxs-lookup"><span data-stu-id="93887-209">Just follow the steps.</span></span>

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a><span data-ttu-id="93887-210">Exchange 伺服器上的信箱的步驟</span><span class="sxs-lookup"><span data-stu-id="93887-210">Steps for mailboxes that are on an Exchange server</span></span>

1. <span data-ttu-id="93887-211">連線至 Exchange 伺服器使用遠端 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="93887-211">Connect to the Exchange server using remote PowerShell.</span></span> <span data-ttu-id="93887-212">遵循在 [[連線到 Exchange 伺服器使用遠端 PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)的步驟。</span><span class="sxs-lookup"><span data-stu-id="93887-212">Follow the steps in [Connect to Exchange servers using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="93887-213">如果您想要完全移除單一規則，多個規則或從信箱的所有規則使用[Remove-inboxrule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule)指令程式。</span><span class="sxs-lookup"><span data-stu-id="93887-213">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="93887-214">如果您想要保留規則，並使用[Disable-inboxrule](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx)指令程式，供進一步調查其內容。</span><span class="sxs-lookup"><span data-stu-id="93887-214">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx) cmdlet.</span></span>

#### <a name="steps-for-mailboxes-in-exchange-online"></a><span data-ttu-id="93887-215">在 Exchange Online 信箱的步驟</span><span class="sxs-lookup"><span data-stu-id="93887-215">Steps for mailboxes in Exchange Online</span></span>

1. <span data-ttu-id="93887-216">請依照[使用連線到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="93887-216">Follow the steps in [Connect to Exchange Online using PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="93887-217">如果您想要完全移除單一規則，多個規則或從信箱的所有規則使用[移除收件匣規則](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule)指令程式。</span><span class="sxs-lookup"><span data-stu-id="93887-217">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-Inbox Rule](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="93887-218">如果您想要保留規則，並使用[Disable-inboxrule](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx)指令程式，供進一步調查其內容。</span><span class="sxs-lookup"><span data-stu-id="93887-218">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https:https://docs.microsoft.com/powershell/module/exchange/mailboxes/disable-inboxrule/library/dd298120(v=exchg.160).aspx) cmdlet.</span></span>

## <a name="how-to-minimize-future-attacks"></a><span data-ttu-id="93887-219">如何減少未來的攻擊</span><span class="sxs-lookup"><span data-stu-id="93887-219">How to minimize future attacks</span></span>

### <a name="first-protect-your-accounts"></a><span data-ttu-id="93887-220">第一個： 保護您的帳戶</span><span class="sxs-lookup"><span data-stu-id="93887-220">First: protect your accounts</span></span>

<span data-ttu-id="93887-221">規則與表單攻擊才會使用攻擊之後他們有竊取或破壞您的使用者帳戶的其中一個。</span><span class="sxs-lookup"><span data-stu-id="93887-221">The Rules and Forms exploits are only used by an attacker after they have stolen or breached one of your user's accounts.</span></span> <span data-ttu-id="93887-222">因此，若要避免使用您的組織對這些攻擊的您第一步是積極地保護您的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="93887-222">So, your first step to preventing the use of these exploits against your organization is to aggressively protect your user accounts.</span></span> <span data-ttu-id="93887-223">其中一些帳戶會破壞的常用方法是透過網路釣魚或[密碼噴射](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/)攻擊。</span><span class="sxs-lookup"><span data-stu-id="93887-223">Some of the most common ways that accounts are breached are through phishing or [password spraying](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) attacks.</span></span>

<span data-ttu-id="93887-224">若要保護您的使用者帳戶，並特別是您系統管理員帳戶，最好是以[設定 Office 365 使用者的多重要素驗證](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="93887-224">The best way to protect your user accounts, and especially your administrator accounts, is to [set up multi-factor authentication for Office 365 users](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span> <span data-ttu-id="93887-225">您也應該：</span><span class="sxs-lookup"><span data-stu-id="93887-225">You should also:</span></span>

- <span data-ttu-id="93887-226">監視您的使用者帳戶是[存取和使用](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports)的方式。</span><span class="sxs-lookup"><span data-stu-id="93887-226">Monitor how your user accounts are [accessed and used](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports).</span></span> <span data-ttu-id="93887-227">您可能不會使初始資料外洩，但您將來偵測此類更快速地縮短持續時間和資料外洩的影響。</span><span class="sxs-lookup"><span data-stu-id="93887-227">You may not prevent the initial breach, but you will shorten the duration and the impact of the breach by detecting it sooner.</span></span> <span data-ttu-id="93887-228">您可以使用這些[Office 365 雲端 App 安全性原則](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)來監視您的帳戶與上不尋常的活動警訊：</span><span class="sxs-lookup"><span data-stu-id="93887-228">You can use these [Office 365 Cloud App Security policies](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) to monitor you accounts and alert on unusual activity:</span></span>

  - <span data-ttu-id="93887-229">**多個失敗的登入**： 這個原則設定檔環境和觸發提醒使用者有關學的比較基準，這可能表示嘗試外洩的單一工作階段中執行多個失敗的登入活動時。</span><span class="sxs-lookup"><span data-stu-id="93887-229">**Multiple failed login attempts**: This policy profiles your environment and triggers alerts when users perform multiple failed login activities in a single session with respect to the learned baseline, which could indicate an attempted breach.</span></span>

  - <span data-ttu-id="93887-230">**Impossible 旅行**： 這個原則設定檔環境和活動從相同的使用者在不同位置中偵測到兩個位置之間的預期的旅行時間較短的期間內時，會觸發警示。</span><span class="sxs-lookup"><span data-stu-id="93887-230">**Impossible travel**: This policy profiles your environment and triggers alerts when activities are detected from the same user in different locations within a time period that is shorter than the expected travel time between the two locations.</span></span> <span data-ttu-id="93887-231">這可能表示不同的使用者使用相同的認證。</span><span class="sxs-lookup"><span data-stu-id="93887-231">This could indicate that a different user is using the same credentials.</span></span> <span data-ttu-id="93887-232">偵測這個異常行為區間初始學習一段期間它可學習新使用者的活動模式的七天。</span><span class="sxs-lookup"><span data-stu-id="93887-232">Detecting this anomalous behavior necessitates an initial learning period of seven days during which it learns a new user's activity pattern.</span></span>

  - <span data-ttu-id="93887-233">**不尋常模擬活動 （依使用者）**： 此原則設定檔環境和使用者執行多個模擬的活動相對於基線學會，在單一工作階段中這可能表示嘗試外洩時，會觸發警示。</span><span class="sxs-lookup"><span data-stu-id="93887-233">**Unusual impersonated activity (by user)**: This policy profiles your environment and triggers alerts when users perform multiple impersonated activities in a single session with respect to the baseline learned, which could indicate an attempted breach.</span></span>

- <span data-ttu-id="93887-234">利用[Office 365 安全分數](https://securescore.office.com/)若要管理帳戶的安全性組態與行為這類的工具。</span><span class="sxs-lookup"><span data-stu-id="93887-234">Leverage a tool like [Office 365 Secure Score](https://securescore.office.com/) to manage account security configurations and behaviors.</span></span>

### <a name="second-keep-your-outlook-clients-current"></a><span data-ttu-id="93887-235">第二個： 您的 Outlook 用戶端維持最新狀態</span><span class="sxs-lookup"><span data-stu-id="93887-235">Second: Keep your Outlook clients current</span></span>

<span data-ttu-id="93887-236">根據預設，完全更新及修補版本的 Outlook 2013 和 2016年停用 「 啟動應用程式 」 規則] / [表單動作。</span><span class="sxs-lookup"><span data-stu-id="93887-236">Fully-updated and patched versions of Outlook 2013, and 2016 disable the "Start Application" rule/form action by default.</span></span> <span data-ttu-id="93887-237">這可確保，即使攻擊破壞帳戶，規則] 和 [表單動作會被封鎖。</span><span class="sxs-lookup"><span data-stu-id="93887-237">This will ensure that, even if an attacker breaches the account, the rule and form actions will be blocked.</span></span> <span data-ttu-id="93887-238">您可以藉由遵循[安裝 Office](https://support.office.com/article/2ab296f3-7f03-43a2-8e50-46de917611c5)更新的安裝最新的更新與安全性修補程式。</span><span class="sxs-lookup"><span data-stu-id="93887-238">You can install the latest updates and security patches by following the steps in [Install Office updates](https://support.office.com/article/2ab296f3-7f03-43a2-8e50-46de917611c5).</span></span>

<span data-ttu-id="93887-239">以下是 Outlook 2013 和 2016年用戶端的修補程式版本：</span><span class="sxs-lookup"><span data-stu-id="93887-239">Here are the patch versions for your Outlook 2013 and 2016 clients:</span></span>

- <span data-ttu-id="93887-240">**Outlook 2016**: 16.0.4534.1001 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="93887-240">**Outlook 2016**: 16.0.4534.1001 or greater.</span></span>

- <span data-ttu-id="93887-241">**Outlook 2013**: 15.0.4937.1000 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="93887-241">**Outlook 2013**: 15.0.4937.1000 or greater.</span></span>

<span data-ttu-id="93887-242">如需有關個別安全性修補程式的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="93887-242">For more information on the individual security patches, see:</span></span>

- [<span data-ttu-id="93887-243">Outlook 2016 安全性修補程式</span><span class="sxs-lookup"><span data-stu-id="93887-243">Outlook 2016 Security Patch</span></span>](https://support.microsoft.com/help/3191883)

- [<span data-ttu-id="93887-244">Outlook 2013 安全性修補程式</span><span class="sxs-lookup"><span data-stu-id="93887-244">Outlook 2013 Security Patch</span></span>](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a><span data-ttu-id="93887-245">第三個： 監視您的 Outlook 用戶端</span><span class="sxs-lookup"><span data-stu-id="93887-245">Third: Monitor your Outlook clients</span></span>

<span data-ttu-id="93887-246">請注意，即使與修補程式安裝的更新，它是以變更本機電腦設定若要重新啟用 「 啟動應用程式 」 行為攻擊者可能。</span><span class="sxs-lookup"><span data-stu-id="93887-246">Note that even with the patches and updates installed, it is possible for an attacker to change the local machine configuration to re-enable the "Start Application" behavior.</span></span> <span data-ttu-id="93887-247">您可以使用[進階群組原則管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/)來監視及強制執行您的用戶端上的本機電腦原則。</span><span class="sxs-lookup"><span data-stu-id="93887-247">You can use [Advanced Group Policy Management](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) to monitor and enforce local machine policies on your clients.</span></span>

<span data-ttu-id="93887-248">您可以查看是否 「 啟動應用程式 」 已重新啟用透過覆寫登錄中所使用的資訊[如何檢視使用 64 位元版本的 Windows 系統登錄](https://support.microsoft.com/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows)中。</span><span class="sxs-lookup"><span data-stu-id="93887-248">You can to see if "Start Application" has been re-enabled through an override in the registry by using the information in [How to view the system registry by using 64-bit versions of Windows](https://support.microsoft.com/help/305097/how-to-view-the-system-registry-by-using-64-bit-versions-of-windows).</span></span> <span data-ttu-id="93887-249">請檢查這些子機碼：</span><span class="sxs-lookup"><span data-stu-id="93887-249">Check these subkeys:</span></span>

- <span data-ttu-id="93887-250">**Outlook 2016**:`HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="93887-250">**Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span></span>

- <span data-ttu-id="93887-251">**Outlook 2013**:`HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="93887-251">**Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span></span>

<span data-ttu-id="93887-252">機碼 EnableUnsafeClientMailRules 外觀。</span><span class="sxs-lookup"><span data-stu-id="93887-252">Look for the key EnableUnsafeClientMailRules.</span></span> <span data-ttu-id="93887-253">如果它有且設為 1，已覆寫 Outlook 安全性修補程式和電腦很容易表單讀規則攻擊。</span><span class="sxs-lookup"><span data-stu-id="93887-253">If it is there and is set to 1, the Outlook security patch has been overridden and the computer is vulnerable to the Form/Rules attack.</span></span> <span data-ttu-id="93887-254">如果值為 0，會停用的 「 啟動應用程式 」 巨集指令。</span><span class="sxs-lookup"><span data-stu-id="93887-254">If the value is 0, the "Start Application" action is disabled.</span></span> <span data-ttu-id="93887-255">如果已安裝的 Outlook 更新及修補版本，而且此登錄機碼不存在，則系統不會受到攻擊。</span><span class="sxs-lookup"><span data-stu-id="93887-255">If the updated and patched version of Outlook is installed and this registry key is not present, then a system is not vulnerable to these attacks.</span></span>

<span data-ttu-id="93887-256">與內部部署 Exchange 安裝的客戶應該考慮封鎖舊版 Outlook 沒有可用的修補程式。</span><span class="sxs-lookup"><span data-stu-id="93887-256">Customers with on-premises Exchange installations should consider blocking older versions of Outlook that do not have patches available.</span></span> <span data-ttu-id="93887-257">可以[設定 Outlook 用戶端封鎖](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)」 文件中找到此程序的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="93887-257">Details on this process can be found in the article [Configure Outlook client blocking](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help).</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="93887-258">像網路安全專業人員一般保護 Office 365</span><span class="sxs-lookup"><span data-stu-id="93887-258">Secure Office 365 like a cybersecurity pro</span></span>

<span data-ttu-id="93887-259">您的 Office 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。</span><span class="sxs-lookup"><span data-stu-id="93887-259">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="93887-260">使用[Office 365 安全性藍圖的 30 天、 前 90 天及過後的頂端優先順序](security-roadmap.md)來實作 Microsoft 建議的最佳作法為保護您的 Office 365 租用戶。</span><span class="sxs-lookup"><span data-stu-id="93887-260">Use the [Office 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>

- <span data-ttu-id="93887-261">要在前 30 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="93887-261">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="93887-262">這些工作會有立即的影響，而且對您的使用者影響較低。</span><span class="sxs-lookup"><span data-stu-id="93887-262">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="93887-263">要在 90 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="93887-263">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="93887-264">這些工作需要多一些時間來計劃及實作，但是可以大幅改善您的安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="93887-264">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="93887-265">90 天之後。</span><span class="sxs-lookup"><span data-stu-id="93887-265">Beyond 90 days.</span></span> <span data-ttu-id="93887-266">這些增強功能會在您的前 90 天工作內建置。</span><span class="sxs-lookup"><span data-stu-id="93887-266">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="93887-267">請參閱：</span><span class="sxs-lookup"><span data-stu-id="93887-267">See also:</span></span>

- <span data-ttu-id="93887-268">[惡意 Outlook 規則](https://silentbreaksecurity.com/malicious-outlook-rules/)的相關規則向量 SilentBreak 安全性文章提供如何詳細的檢閱 Outlook 規則。</span><span class="sxs-lookup"><span data-stu-id="93887-268">[Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector provides a detailed review of how the Outlook Rules.</span></span>

- <span data-ttu-id="93887-269">關於 Mailrule Pwnage Sensepost 部落格上的[MAPI over HTTP 和 Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/)討論工具，稱為尺規，可讓您利用透過 Outlook 規則的信箱。</span><span class="sxs-lookup"><span data-stu-id="93887-269">[MAPI over HTTP and Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog about Mailrule Pwnage discusses a tool called Ruler that lets you exploit mailboxes through Outlook rules.</span></span>

- <span data-ttu-id="93887-270">[Outlook 表單與 shell](https://sensepost.com/blog/2017/outlook-forms-and-shells/)關於表單威脅向量 Sensepost 部落格上。</span><span class="sxs-lookup"><span data-stu-id="93887-270">[Outlook forms and shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) on the Sensepost blog about Forms Threat Vector.</span></span>

- [<span data-ttu-id="93887-271">尺規程式碼基底</span><span class="sxs-lookup"><span data-stu-id="93887-271">Ruler Codebase</span></span>](https://github.com/sensepost/ruler)

- [<span data-ttu-id="93887-272">尺規指標的危害</span><span class="sxs-lookup"><span data-stu-id="93887-272">Ruler Indicators of Compromise</span></span>](https://github.com/sensepost/notruler/blob/master/iocs.md)
