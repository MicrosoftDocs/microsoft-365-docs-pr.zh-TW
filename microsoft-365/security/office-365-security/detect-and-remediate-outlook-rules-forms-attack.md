---
title: 偵測並修復 Outlook 規則和自訂表單注入攻擊。
f1.keywords:
- NOCSH
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
description: 瞭解如何在 Office 365 中識別及修復 Outlook 規則和自訂表單注入攻擊
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7d879d34a925354084e08d82f5e1724725c18825
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203068"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a><span data-ttu-id="b7ef4-103">偵測並修復 Outlook 規則和自訂表單注入攻擊</span><span class="sxs-lookup"><span data-stu-id="b7ef4-103">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b7ef4-104">**摘要** 瞭解如何在 Office 365 中識別及修復 Outlook 規則和自訂表單注入攻擊。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-104">**Summary** Learn how to recognize and remediate the Outlook rules and custom Forms injections attacks in Office 365.</span></span>

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a><span data-ttu-id="b7ef4-105">Outlook 規則和自訂表單植入攻擊是什麼？</span><span class="sxs-lookup"><span data-stu-id="b7ef4-105">What is the Outlook Rules and Custom Forms injection attack?</span></span>

<span data-ttu-id="b7ef4-106">當攻擊者破壞您租用中的帳戶並取得時，會嘗試並建立一種方式，以在發現及移除之後，繼續進行，或是取得的方式。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-106">After an attacker has breached an account in your tenancy and gets in, they're are going to try and establish a way to stay in or a way to get back in after they are discovered and removed.</span></span> <span data-ttu-id="b7ef4-107">這稱為建立持久性機制。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-107">This is called establishing a persistence mechanism.</span></span> <span data-ttu-id="b7ef4-108">使用 Outlook 規則或將自訂表單插入 Outlook 的兩種方法可以做到這一點。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-108">Two ways that they can do this are by exploiting Outlook rules or by injecting custom forms into Outlook.</span></span>
<span data-ttu-id="b7ef4-109">在這兩種情況下，規則或表單會從雲端服務同步處理至桌面用戶端，因此完整格式化及重新安裝用戶端軟體不會消除插入機制。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-109">In both cases, the rule or form is synced from the cloud service down to the desktop client, so a full format and re-install of the client software doesn't eliminate the injection mechanism.</span></span> <span data-ttu-id="b7ef4-110">這是因為當 Outlook 用戶端軟體重新連接至雲端中的信箱時，它會從雲端重新下載規則和表單。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-110">This is because when the Outlook client software reconnects to the mailbox in the cloud it will re-download the rules and forms from the cloud.</span></span> <span data-ttu-id="b7ef4-111">當規則和表單就緒後，攻擊者會使用它們來執行遠端或自訂程式碼，通常是在本機電腦上安裝惡意程式碼。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-111">Once the rules and forms are in place, the attacker uses them to execute remote or custom code, usually to install malware on the local machine.</span></span> <span data-ttu-id="b7ef4-112">惡意程式碼接著重新竊取認證或執行其他非法活動。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-112">The malware then re-steals credentials or performs other illicit activity.</span></span>
<span data-ttu-id="b7ef4-113">以下是一個好的資訊：如果您將用戶端保持在最新版本的補丁，您就不會因為目前的 Outlook 用戶端預設會封鎖這兩種機制，所以威脅不會受到威脅。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-113">The good news here is that if you keep your clients patched to the latest version, you are not vulnerable to the threat as current Outlook client defaults block both mechanisms.</span></span>

<span data-ttu-id="b7ef4-114">攻擊通常遵循下列模式：</span><span class="sxs-lookup"><span data-stu-id="b7ef4-114">The attacks typically follow these patterns:</span></span>

<span data-ttu-id="b7ef4-115">**規則會利用**下列專案：</span><span class="sxs-lookup"><span data-stu-id="b7ef4-115">**The Rules Exploit**:</span></span>

1. <span data-ttu-id="b7ef4-116">攻擊者竊取其中一個使用者的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-116">The attacker steals the username and password of one of your users.</span></span>

2. <span data-ttu-id="b7ef4-117">然後，攻擊者會登入該使用者的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-117">The attacker then signs in to that users Exchange mailbox.</span></span> <span data-ttu-id="b7ef4-118">信箱可以位於 Exchange online 中，也可以位於 Exchange 內部部署中。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-118">The mailbox can either be in Exchange online or in Exchange on-premises.</span></span>

3. <span data-ttu-id="b7ef4-119">然後，攻擊者會在信箱收到符合規則準則的電子郵件時，在觸發的信箱中建立轉移規則。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-119">The attacker then creates a forwarding rule in the mailbox that is triggered when the mailbox receives an email that matches the criteria of the rule.</span></span> <span data-ttu-id="b7ef4-120">規則的準則及觸發器電子郵件的內容是針對彼此進行量身定制的。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-120">The criteria of rule and the contents of the trigger email are tailor-made for each other.</span></span>

4. <span data-ttu-id="b7ef4-121">攻擊者會將觸發器電子郵件傳送至一般使用信箱的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-121">The attacker sends the trigger email to the user who is using their mailbox normally.</span></span>

5. <span data-ttu-id="b7ef4-122">收到電子郵件時，會觸發規則。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-122">When the email is received, the rule is triggered.</span></span> <span data-ttu-id="b7ef4-123">規則的動作通常是在遠端 (WebDAV) 伺服器上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-123">The action of the rule is usually to launch an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="b7ef4-124">應用程式通常會在使用者的電腦上，以本機方式安裝惡意程式碼，例如 [Powershell Empire](https://www.powershellempire.com/)。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-124">The application typically installs malware, such as [Powershell Empire](https://www.powershellempire.com/), locally on the user's machine.</span></span>

7. <span data-ttu-id="b7ef4-125">惡意程式碼可讓攻擊者重新竊取使用者的使用者名稱和密碼，或從本機機器重新竊取其他認證，以及執行其他惡意活動。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-125">The malware allows the attacker to re-steal the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

<span data-ttu-id="b7ef4-126">**表單利用**方式：</span><span class="sxs-lookup"><span data-stu-id="b7ef4-126">**The Forms Exploit**:</span></span>

1. <span data-ttu-id="b7ef4-127">攻擊者竊取其中一個使用者的使用者名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-127">The attacker steals the username and password of one of your users.</span></span>

2. <span data-ttu-id="b7ef4-128">然後，攻擊者會登入該使用者的 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-128">The attacker then sign in to that users Exchange mailbox.</span></span> <span data-ttu-id="b7ef4-129">信箱可以位於 Exchange online 中，也可以位於 Exchange 內部部署中。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-129">The mailbox can either be in Exchange online or in Exchange on-premises.</span></span>

3. <span data-ttu-id="b7ef4-130">然後，攻擊者會建立自訂的郵件表單範本，並將其插入使用者的信箱。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-130">The attacker then creates a custom mail form template and inserts it into the user's mailbox.</span></span> <span data-ttu-id="b7ef4-131">當信箱收到需要信箱載入自訂表單的電子郵件時，就會觸發自訂表單。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-131">The custom form is triggered when the mailbox receives an email that requires the mailbox to load the custom form.</span></span> <span data-ttu-id="b7ef4-132">自訂表單和電子郵件的格式是針對彼此進行量身定制。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-132">The custom form and the format of email are tailor-made for each other.</span></span>
4. <span data-ttu-id="b7ef4-133">攻擊者會將觸發器電子郵件傳送給使用者，該使用者一般會使用其信箱。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-133">The attacker sends the trigger email to the user, who is using their mailbox normally.</span></span>

5. <span data-ttu-id="b7ef4-134">當接收到電子郵件時，就會載入表單。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-134">When the email is received, the form is loaded.</span></span> <span data-ttu-id="b7ef4-135">表單會在遠端 (WebDAV) 伺服器上啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-135">The form launches an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="b7ef4-136">應用程式通常會在使用者的電腦上，以本機方式安裝惡意程式碼，例如 [Powershell Empire](https://www.powershellempire.com/)。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-136">The application typically installs malware, such as [Powershell Empire](https://www.powershellempire.com/), locally on the user's machine.</span></span>

7. <span data-ttu-id="b7ef4-137">惡意程式碼可讓攻擊者重新竊取使用者的使用者名稱和密碼，或從本機機器重新竊取其他認證，以及執行其他惡意活動。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-137">The malware allows the attacker to re-steal the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a><span data-ttu-id="b7ef4-138">規則和自訂表單植入攻擊可能類似于 Office 365？</span><span class="sxs-lookup"><span data-stu-id="b7ef4-138">What a Rules and Custom Forms Injection attack might look like Office 365?</span></span>

<span data-ttu-id="b7ef4-139">您的使用者可能會注意到這些持續性機制，但在某些情況下，您可能會看不到這些功能。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-139">These persistence mechanisms are unlikely to be noticed by your users and may in some cases even be invisible to them.</span></span> <span data-ttu-id="b7ef4-140">本文將告訴您如何在下面列出的任何 (的威脅) 中尋找7號徵兆。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-140">This article tells you how to look for any of the seven signs (Indicators of Compromise) listed below.</span></span> <span data-ttu-id="b7ef4-141">如果您找到上述任一項，您必須採取補救步驟。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-141">If you find any of these, you need to take remediation steps.</span></span>

- <span data-ttu-id="b7ef4-142">規則受損的指標：</span><span class="sxs-lookup"><span data-stu-id="b7ef4-142">Indicators of the Rules compromise:</span></span>

  - <span data-ttu-id="b7ef4-143">規則動作是要啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-143">Rule Action is to start an application.</span></span>

  - <span data-ttu-id="b7ef4-144">規則參照 EXE、ZIP 或 URL。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-144">Rule References an EXE, ZIP, or URL.</span></span>

  - <span data-ttu-id="b7ef4-145">在本機電腦上，尋找來自 Outlook P&ID 的新進程開始。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-145">On the local machine, look for new process starts that originate from the Outlook PID.</span></span>

- <span data-ttu-id="b7ef4-146">自訂表單受損的指標：</span><span class="sxs-lookup"><span data-stu-id="b7ef4-146">Indicators of the Custom forms compromise:</span></span>

  - <span data-ttu-id="b7ef4-147">顯示的自訂表單會另存為自己的郵件類別。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-147">Custom form present saved as their own message class.</span></span>

  - <span data-ttu-id="b7ef4-148">郵件類別包含可執行程式碼。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-148">Message class contains executable code.</span></span>

  - <span data-ttu-id="b7ef4-149">通常儲存在個人表單庫或 [收件匣] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-149">Usually stored in Personal Forms Library or Inbox folders.</span></span>

  - <span data-ttu-id="b7ef4-150">表單命名為 IPM。注意。[custom name]。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-150">Form is named IPM.Note.[custom name].</span></span>

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a><span data-ttu-id="b7ef4-151">尋找此攻擊之徵兆及確認的步驟</span><span class="sxs-lookup"><span data-stu-id="b7ef4-151">Steps for finding signs of this attack and confirming it</span></span>

<span data-ttu-id="b7ef4-152">您可以使用下列兩種方法之一來確認攻擊：</span><span class="sxs-lookup"><span data-stu-id="b7ef4-152">You can use either of these two methods to confirm the attack:</span></span>

- <span data-ttu-id="b7ef4-153">使用 Outlook 用戶端，手動檢查每個信箱的規則和表單。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-153">Manually examine the rules and forms for each mailbox using the Outlook client.</span></span> <span data-ttu-id="b7ef4-154">這種方法是完整的，但是您一次只能檢查信箱使用者，如果您有許多使用者可供檢查，就會非常耗費時間。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-154">This method is thorough, but you can only check mailbox user at a time which can be very time consuming if you have many users to check.</span></span> <span data-ttu-id="b7ef4-155">也可能會造成您正在執行檢查的電腦遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-155">It can also result in a breach of the computer that you are running the check from.</span></span>

- <span data-ttu-id="b7ef4-156">使用 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 腳本自動為您租使用者中的所有使用者轉儲所有的郵件轉寄規則和自訂表單。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-156">Use the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script to automatically dump all the mail forwarding rules and custom forms for all the users in your tenancy.</span></span> <span data-ttu-id="b7ef4-157">這是最快且最安全的方法，最少量的開銷。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-157">This is the fastest and safest method with the least amount of overhead.</span></span>

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a><span data-ttu-id="b7ef4-158">使用 Outlook 用戶端確認規則攻擊</span><span class="sxs-lookup"><span data-stu-id="b7ef4-158">Confirm the Rules Attack Using the Outlook client</span></span>

1. <span data-ttu-id="b7ef4-159">以使用者身分開啟使用者 Outlook 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-159">Open the users Outlook client as the user.</span></span> <span data-ttu-id="b7ef4-160">使用者可能需要協助您檢查其信箱上的規則。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-160">The user may need your help in examining the rules on their mailbox.</span></span>

2. <span data-ttu-id="b7ef4-161">如需如何在 Outlook 中開啟規則介面的程式，請參閱 [使用規則文章管理電子郵件訊息](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-161">Refer to [Manage email messages by using rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) article for the procedures on how to open the rules interface in Outlook.</span></span>

3. <span data-ttu-id="b7ef4-162">尋找使用者未建立的規則，或任何未預期的規則或具有可疑名稱的規則。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-162">Look for rules that the user did not create, or any unexpected rules or rules with suspicious names.</span></span>

4. <span data-ttu-id="b7ef4-163">請參閱規則描述，以取得啟動和應用程式或參考的規則動作。Exe。ZIP 檔或啟動 URL。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-163">Look in the rule description for rule actions that start and application or refer to an .EXE, .ZIP file or to launching a URL.</span></span>

5. <span data-ttu-id="b7ef4-164">尋找任何開始使用 Outlook 進程識別碼的新程式。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-164">Look for any new processes that start using the Outlook process ID.</span></span> <span data-ttu-id="b7ef4-165">請參閱 [尋找進程識別碼](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-165">Refer to [Find the Process ID](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).</span></span>

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a><span data-ttu-id="b7ef4-166">使用 Outlook 用戶端確認表單攻擊的步驟</span><span class="sxs-lookup"><span data-stu-id="b7ef4-166">Steps to confirm the Forms attack using the Outlook client</span></span>

1. <span data-ttu-id="b7ef4-167">以使用者身分開啟使用者 Outlook 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-167">Open the user Outlook client as the user.</span></span>

2. <span data-ttu-id="b7ef4-168">遵循中的步驟，顯示 Outlook 使用者版本的 [[開發人員]](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-168">Follow the steps in, [Show the Developer tab](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) for the users version of Outlook.</span></span>

3. <span data-ttu-id="b7ef4-169">開啟 Outlook 中的 [now visible developer] 索引標籤，然後按一下 [ **設計表單**]。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-169">Open the now visible developer tab in Outlook and click **design a form**.</span></span>

4. <span data-ttu-id="b7ef4-170">從 [**查找範圍**] 清單中選取 [**收件**匣]。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-170">Select the **Inbox** from the **Look In** list.</span></span> <span data-ttu-id="b7ef4-171">尋找任何自訂表單。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-171">Look for any custom forms.</span></span> <span data-ttu-id="b7ef4-172">自訂表單非常少見，如果您有任何自訂表單，則需要更深入的外觀。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-172">Custom forms are rare enough that if you have any custom forms at all, it is worth a deeper look.</span></span>

5. <span data-ttu-id="b7ef4-173">調查任何自訂表單，尤其是標示為隱藏的表單。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-173">Investigate any custom forms, especially those marked as hidden.</span></span>

6. <span data-ttu-id="b7ef4-174">開啟任何自訂表單，然後在 **表單** 群組中按一下 [ **View Code** ] （查看表單載入時執行的功能）。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-174">Open any custom forms and in the **Form** group click **View Code** to see what runs when the form is loaded.</span></span>

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a><span data-ttu-id="b7ef4-175">使用 PowerShell 確認規則和表單攻擊的步驟</span><span class="sxs-lookup"><span data-stu-id="b7ef4-175">Steps to confirm the Rules and Forms attack using PowerShell</span></span>

<span data-ttu-id="b7ef4-176">驗證規則或自訂表單攻擊的最簡單方法，就是執行 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-176">The simplest way to verify a rules or custom forms attack is to run the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script.</span></span> <span data-ttu-id="b7ef4-177">此腳本會連線至您租使用者中的每個信箱，並將所有規則和表單轉儲成兩個 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-177">This script connects to every mailbox in your tenant and dumps all the rules and forms into two .csv files.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="b7ef4-178">先決條件</span><span class="sxs-lookup"><span data-stu-id="b7ef4-178">Pre-requisites</span></span>

<span data-ttu-id="b7ef4-179">您必須具有全域系統管理員許可權，才能執行腳本，因為腳本會連線至租用中的每個信箱，以讀取規則和表單。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-179">You will need to have a global administrator rights to run the script because the script connects to every mailbox in the tenancy to read the rules and forms.</span></span>

1. <span data-ttu-id="b7ef4-180">以本機系統管理員許可權登入您將執行腳本的電腦。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-180">Sign in to the machine that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="b7ef4-181">將 Get-AllTenantRulesAndForms.ps1 腳本從 GitHub 下載或複製到要從中執行它的資料夾。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-181">Download or copy the Get-AllTenantRulesAndForms.ps1 script from GitHub to a folder from which you will run it.</span></span> <span data-ttu-id="b7ef4-182">腳本會為此資料夾建立兩個日期戳檔案，MailboxFormsExport-yyyy-mm-dd.csv 和 MailboxRulesExport-yyyy-mm-dd.csv。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-182">The script will create two date stamped files to this folder, MailboxFormsExport-yyyy-mm-dd.csv, and MailboxRulesExport-yyyy-mm-dd.csv.</span></span>

3. <span data-ttu-id="b7ef4-183">以系統管理員身分開啟 PowerShell 實例，然後開啟您用來儲存腳本的資料夾。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-183">Open a PowerShell instance as an administrator and open the folder you saved the script to.</span></span>

4. <span data-ttu-id="b7ef4-184">依下列方式執行此 PowerShell 命令列 `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1</span><span class="sxs-lookup"><span data-stu-id="b7ef4-184">Run this PowerShell command line as follows `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1</span></span>

#### <a name="interpreting-the-output"></a><span data-ttu-id="b7ef4-185">解讀輸出</span><span class="sxs-lookup"><span data-stu-id="b7ef4-185">Interpreting the output</span></span>

- <span data-ttu-id="b7ef4-186">\**MailboxRulesExport-*yyyy\*\*\*：) 針對包含應用程式或可執行檔的動作條件，檢查每一列 (的規則：</span><span class="sxs-lookup"><span data-stu-id="b7ef4-186">**MailboxRulesExport-*yyyy-mm-dd*.csv**: Examine the rules (one per row) for action conditions that include applications or executables:</span></span>

  - <span data-ttu-id="b7ef4-187">\*\*ActionType (欄位 A) \*\*：如果看到值 "ID_ACTION_CUSTOM"，該規則可能是惡意的。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-187">**ActionType (column A)**: If you see the value "ID_ACTION_CUSTOM", the rule is likely malicious.</span></span>

  - <span data-ttu-id="b7ef4-188">\*\*IsPotentiallyMalicious (欄) \*\*：如果此值為 "TRUE"，則此規則可能是惡意的。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-188">**IsPotentiallyMalicious (column D)**: If this value is "TRUE", the rule is likely malicious.</span></span>

  - <span data-ttu-id="b7ef4-189">\*\*ActionCommand (Column G) \*\*：如果這會列出應用程式或任何副檔名為 .exe、.zip 副檔名的專案，或是參考 URL 的專案，則該規則可能是惡意的。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-189">**ActionCommand (column G)**: If this lists an application or any file with a .exe, .zip extension or an entry that refers to a URL, that is not supposed to be there, the rule is likely malicious.</span></span>

- <span data-ttu-id="b7ef4-190">\**MailboxFormsExport-*yyyy-yyyy\*\*\*：一般說來，使用自訂表單非常少見。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-190">**MailboxFormsExport-*yyyy-mm-dd*.csv**: In general, the use of custom forms is very rare.</span></span> <span data-ttu-id="b7ef4-191">如果您在此活頁簿中找到任何的，請開啟該使用者的信箱，並檢查該表單本身。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-191">If you find any in this workbook, you open that user's mailbox and examine the form itself.</span></span> <span data-ttu-id="b7ef4-192">如果您的組織未有意放入該組織，可能是惡意的。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-192">If your organization did not put it there intentionally, it is likely malicious.</span></span>

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a><span data-ttu-id="b7ef4-193">如何停止和修復 Outlook 規則和表單攻擊</span><span class="sxs-lookup"><span data-stu-id="b7ef4-193">How to stop and remediate the Outlook Rules and Forms attack</span></span>

<span data-ttu-id="b7ef4-194">如果您發現其中任何一種攻擊的證據，修正很簡單，只需要從信箱中刪除規則或表單即可。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-194">If you find any evidence of either of these attacks, remediation is simple, just delete the rule or form from the mailbox.</span></span> <span data-ttu-id="b7ef4-195">您可以使用 Outlook 用戶端或使用遠端 PowerShell 來移除規則。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-195">You can do this with the Outlook client or using remote PowerShell to remove rules.</span></span>

### <a name="using-outlook"></a><span data-ttu-id="b7ef4-196">使用 Outlook</span><span class="sxs-lookup"><span data-stu-id="b7ef4-196">Using Outlook</span></span>

1. <span data-ttu-id="b7ef4-197">識別使用者已用於 Outlook 的所有裝置。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-197">Identify all the devices that the user has used with Outlook.</span></span> <span data-ttu-id="b7ef4-198">所有的潛在惡意程式碼都必須清除。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-198">They will all need to be cleaned of potential malware.</span></span> <span data-ttu-id="b7ef4-199">不允許使用者登入並使用電子郵件，直到所有裝置都已清除為止。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-199">Do not allow the user to sign on and use email until all the devices are cleaned.</span></span>

2. <span data-ttu-id="b7ef4-200">依照刪除每個裝置的 [規則](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) 中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-200">Follow the steps in [Delete a rule](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) for each device.</span></span>

3. <span data-ttu-id="b7ef4-201">如果您不確定是否存在其他惡意程式碼，您可以格式化及重新安裝裝置上的所有軟體。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-201">If you are unsure about the presence of other malware, you can format and re-install all the software on the device.</span></span> <span data-ttu-id="b7ef4-202">針對行動裝置，您可以遵循製造商的步驟，將裝置重設為出廠影像。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-202">For mobile devices you can follow the manufacturers steps to reset the device to the factory image.</span></span>

4. <span data-ttu-id="b7ef4-203">安裝最新版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-203">Install the most up-to-date versions of Outlook.</span></span> <span data-ttu-id="b7ef4-204">請記住，目前的 Outlook 版本會封鎖這兩種攻擊類型的預設值。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-204">Remember that the current version of Outlook blocks both types of this attack by default.</span></span>

5. <span data-ttu-id="b7ef4-205">移除信箱的所有離線副本之後，請重設使用者的密碼 (使用高品質的) ，然後在未啟用 MFA 時，依照 [為使用者設定多重要素驗證](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) 中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-205">Once all offline copies of the mailbox have been removed, reset the user's password (use a high-quality one) and follow the steps in [Setup multi-factor authentication for users](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) if MFA has not already been enabled.</span></span> <span data-ttu-id="b7ef4-206">這可確保使用者的認證不會透過其他方式公開 (例如網路釣魚或密碼重複使用) 。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-206">This ensures that the user's credentials are not exposed via other means (such as phishing or password re-use).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b7ef4-207">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7ef4-207">Using PowerShell</span></span>

<span data-ttu-id="b7ef4-208">您可以使用兩個遠端 PowerShell Cmdlet 來移除或停用危險的規則。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-208">There are two remote PowerShell cmdlets you can use to remove or disable dangerous rules.</span></span> <span data-ttu-id="b7ef4-209">只需遵循步驟。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-209">Just follow the steps.</span></span>

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a><span data-ttu-id="b7ef4-210">Exchange 伺服器上的信箱步驟</span><span class="sxs-lookup"><span data-stu-id="b7ef4-210">Steps for mailboxes that are on an Exchange server</span></span>

1. <span data-ttu-id="b7ef4-211">使用遠端 PowerShell 連接至 Exchange 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-211">Connect to the Exchange server using remote PowerShell.</span></span> <span data-ttu-id="b7ef4-212">依照 [[使用遠端 PowerShell 連線到 Exchange 伺服器]](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-212">Follow the steps in [Connect to Exchange servers using remote PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="b7ef4-213">如果您想要完全移除單一規則、多個規則或所有來自信箱的規則，請使用 [Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-213">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="b7ef4-214">如果您想要保留規則及其內容以進行進一步調查，請使用 [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-214">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

#### <a name="steps-for-mailboxes-in-exchange-online"></a><span data-ttu-id="b7ef4-215">Exchange Online 中的信箱步驟</span><span class="sxs-lookup"><span data-stu-id="b7ef4-215">Steps for mailboxes in Exchange Online</span></span>

1. <span data-ttu-id="b7ef4-216">依照 [[使用 PowerShell 連線到 Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-216">Follow the steps in [Connect to Exchange Online using PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b7ef4-217">如果您想要完全移除單一規則、多個規則或所有來自信箱的規則，請使用 [ [移除收件匣規則](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) ] Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-217">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-Inbox Rule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="b7ef4-218">如果您想要保留規則及其內容以進行進一步調查，請使用 [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-218">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

## <a name="how-to-minimize-future-attacks"></a><span data-ttu-id="b7ef4-219">如何最小化未來的攻擊</span><span class="sxs-lookup"><span data-stu-id="b7ef4-219">How to minimize future attacks</span></span>

### <a name="first-protect-your-accounts"></a><span data-ttu-id="b7ef4-220">第一種：保護您的帳戶</span><span class="sxs-lookup"><span data-stu-id="b7ef4-220">First: protect your accounts</span></span>

<span data-ttu-id="b7ef4-221">只有在竊取或破壞使用者的帳戶之後，攻擊者才會使用這些規則和表單攻擊。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-221">The Rules and Forms exploits are only used by an attacker after they have stolen or breached one of your user's accounts.</span></span> <span data-ttu-id="b7ef4-222">因此，避免對您的組織使用這些入侵的第一步，是要積極保護您的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-222">So, your first step to preventing the use of these exploits against your organization is to aggressively protect your user accounts.</span></span> <span data-ttu-id="b7ef4-223">一些最常見的帳戶破壞方式是透過網路釣魚或 [密碼 spraying](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) 攻擊。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-223">Some of the most common ways that accounts are breached are through phishing or [password spraying](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) attacks.</span></span>

<span data-ttu-id="b7ef4-224">保護使用者帳戶的最佳方法（特別是管理員帳戶）是為 [使用者設定多重要素驗證](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-224">The best way to protect your user accounts, and especially your administrator accounts, is to [set up multi-factor authentication for users](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span> <span data-ttu-id="b7ef4-225">您也應該：</span><span class="sxs-lookup"><span data-stu-id="b7ef4-225">You should also:</span></span>

- <span data-ttu-id="b7ef4-226">監視如何 [存取及使用](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports)您的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-226">Monitor how your user accounts are [accessed and used](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports).</span></span> <span data-ttu-id="b7ef4-227">您可能不會防止初始遭到破壞，但是您會儘早偵測，以縮短破壞的持續時間和破壞影響。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-227">You may not prevent the initial breach, but you will shorten the duration and the impact of the breach by detecting it sooner.</span></span> <span data-ttu-id="b7ef4-228">您可以使用這些 [Office 365 雲端 App 安全性原則](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) ，監控不尋常活動的帳戶和警示：</span><span class="sxs-lookup"><span data-stu-id="b7ef4-228">You can use these [Office 365 Cloud App Security policies](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) to monitor you accounts and alert on unusual activity:</span></span>

  - <span data-ttu-id="b7ef4-229">**多個失敗的登入嘗試**：這個原則設定檔您的環境，當使用者在與所學的基準相關的單一會話中執行多個失敗的登入活動時，便會觸發警示，這可能表示企圖遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-229">**Multiple failed login attempts**: This policy profiles your environment and triggers alerts when users perform multiple failed login activities in a single session with respect to the learned baseline, which could indicate an attempted breach.</span></span>

  - <span data-ttu-id="b7ef4-230">不**可能的旅行**：這項原則會在不同位置的相同使用者中偵測到活動時，在兩個位置之間的時間範圍內，以短于預期的旅行時間。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-230">**Impossible travel**: This policy profiles your environment and triggers alerts when activities are detected from the same user in different locations within a time period that is shorter than the expected travel time between the two locations.</span></span> <span data-ttu-id="b7ef4-231">這可能表示不同的使用者使用相同的認證。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-231">This could indicate that a different user is using the same credentials.</span></span> <span data-ttu-id="b7ef4-232">偵測到這種反常行為時，會有七天的初始學習週期，以瞭解新使用者的活動模式。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-232">Detecting this anomalous behavior necessitates an initial learning period of seven days during which it learns a new user's activity pattern.</span></span>

  - <span data-ttu-id="b7ef4-233">\*\*由使用者) 所 (的特殊模擬活動 \*\*：此原則設定檔您的環境，當使用者在與基線獲知相關的單一會話中執行多個類比活動時，便會觸發警示，這可能表示企圖遭到破壞。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-233">**Unusual impersonated activity (by user)**: This policy profiles your environment and triggers alerts when users perform multiple impersonated activities in a single session with respect to the baseline learned, which could indicate an attempted breach.</span></span>

- <span data-ttu-id="b7ef4-234">利用類似 [Office 365 安全分數](https://securescore.office.com/) 的工具來管理帳戶安全性設定和行為。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-234">Leverage a tool like [Office 365 Secure Score](https://securescore.office.com/) to manage account security configurations and behaviors.</span></span>

### <a name="second-keep-your-outlook-clients-current"></a><span data-ttu-id="b7ef4-235">第二：讓 Outlook 用戶端保持最新</span><span class="sxs-lookup"><span data-stu-id="b7ef4-235">Second: Keep your Outlook clients current</span></span>

<span data-ttu-id="b7ef4-236">完全更新及修補的 Outlook 2013 版本，而2016預設會停用「啟動應用程式」規則/表單動作。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-236">Fully-updated and patched versions of Outlook 2013, and 2016 disable the "Start Application" rule/form action by default.</span></span> <span data-ttu-id="b7ef4-237">這可確保即使攻擊者破壞帳戶，規則和表單動作也會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-237">This will ensure that, even if an attacker breaches the account, the rule and form actions will be blocked.</span></span> <span data-ttu-id="b7ef4-238">您可以遵循 [安裝 Office 更新](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)中的步驟，安裝最新的更新及安全性修補程式。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-238">You can install the latest updates and security patches by following the steps in [Install Office updates](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5).</span></span>

<span data-ttu-id="b7ef4-239">以下是 Outlook 2013 和2016用戶端的修補程式版本：</span><span class="sxs-lookup"><span data-stu-id="b7ef4-239">Here are the patch versions for your Outlook 2013 and 2016 clients:</span></span>

- <span data-ttu-id="b7ef4-240">**Outlook 2016**：16.0.4534.1001 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-240">**Outlook 2016**: 16.0.4534.1001 or greater.</span></span>

- <span data-ttu-id="b7ef4-241">**Outlook 2013**：15.0.4937.1000 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-241">**Outlook 2013**: 15.0.4937.1000 or greater.</span></span>

<span data-ttu-id="b7ef4-242">如需個別安全性修補程式的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b7ef4-242">For more information on the individual security patches, see:</span></span>

- [<span data-ttu-id="b7ef4-243">Outlook 2016 安全性修補程式</span><span class="sxs-lookup"><span data-stu-id="b7ef4-243">Outlook 2016 Security Patch</span></span>](https://support.microsoft.com/help/3191883)

- [<span data-ttu-id="b7ef4-244">Outlook 2013 安全性修補程式</span><span class="sxs-lookup"><span data-stu-id="b7ef4-244">Outlook 2013 Security Patch</span></span>](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a><span data-ttu-id="b7ef4-245">第三：監控 Outlook 用戶端</span><span class="sxs-lookup"><span data-stu-id="b7ef4-245">Third: Monitor your Outlook clients</span></span>

<span data-ttu-id="b7ef4-246">請注意，即使已安裝修補程式和更新，攻擊者還是可以變更本機電腦設定，以重新啟用「啟動應用程式」行為。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-246">Note that even with the patches and updates installed, it is possible for an attacker to change the local machine configuration to re-enable the "Start Application" behavior.</span></span> <span data-ttu-id="b7ef4-247">您可以使用 [高級群組原則管理](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) ，在用戶端上監視及強制執行本機電腦原則。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-247">You can use [Advanced Group Policy Management](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) to monitor and enforce local machine policies on your clients.</span></span>

<span data-ttu-id="b7ef4-248">您可以使用 [Windows 的64位版本](https://support.microsoft.com/help/305097)資訊，查看是否已透過登錄中的覆寫方式重新啟用 [啟動應用程式]。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-248">You can to see if "Start Application" has been re-enabled through an override in the registry by using the information in [How to view the system registry by using 64-bit versions of Windows](https://support.microsoft.com/help/305097).</span></span> <span data-ttu-id="b7ef4-249">請檢查下列子項：</span><span class="sxs-lookup"><span data-stu-id="b7ef4-249">Check these subkeys:</span></span>

- <span data-ttu-id="b7ef4-250">**Outlook 2016**： `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="b7ef4-250">**Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span></span>

- <span data-ttu-id="b7ef4-251">**Outlook 2013**： `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="b7ef4-251">**Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span></span>

<span data-ttu-id="b7ef4-252">尋找機碼 EnableUnsafeClientMailRules。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-252">Look for the key EnableUnsafeClientMailRules.</span></span> <span data-ttu-id="b7ef4-253">如果已存在，且已設定為1，Outlook 安全性修補程式已被取代，且電腦受到表單/規則攻擊的影響。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-253">If it is there and is set to 1, the Outlook security patch has been overridden and the computer is vulnerable to the Form/Rules attack.</span></span> <span data-ttu-id="b7ef4-254">如果值為0，就會停用「啟動應用程式」動作。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-254">If the value is 0, the "Start Application" action is disabled.</span></span> <span data-ttu-id="b7ef4-255">如果已安裝更新及修補的 Outlook 版本，但此登錄機碼不存在，系統就不會受到攻擊。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-255">If the updated and patched version of Outlook is installed and this registry key is not present, then a system is not vulnerable to these attacks.</span></span>

<span data-ttu-id="b7ef4-256">使用內部部署 Exchange 安裝的客戶應考慮封鎖舊版本的 Outlook，但沒有可用的修補程式。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-256">Customers with on-premises Exchange installations should consider blocking older versions of Outlook that do not have patches available.</span></span> <span data-ttu-id="b7ef4-257">有關此程式的詳細資訊，請參閱 [設定 Outlook 用戶端封鎖](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help)一文。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-257">Details on this process can be found in the article [Configure Outlook client blocking](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="b7ef4-258">像網路安全專業人員一般保護 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7ef4-258">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="b7ef4-259">您的 Microsoft 365 訂閱隨附一組功能強大的安全性功能，可供您用來保護您的資料和您的使用者。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-259">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="b7ef4-260">使用 [Microsoft 365 安全性藍圖 - 前 30 天、前 90 天前和之後的最高優先順序](security-roadmap.md)來實作 Microsoft 建議用來保護您的 Microsoft 365 租用戶的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-260">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="b7ef4-261">要在前 30 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-261">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="b7ef4-262">這些工作會有立即的影響，而且對您的使用者影響較低。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-262">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="b7ef4-263">要在 90 天內完成的工作。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-263">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="b7ef4-264">這些工作需要多一些時間來計劃及實作，但是可以大幅改善您的安全性狀態。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-264">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="b7ef4-265">90 天之後。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-265">Beyond 90 days.</span></span> <span data-ttu-id="b7ef4-266">這些增強功能會在您的前 90 天工作內建置。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-266">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7ef4-267">另請參閱：</span><span class="sxs-lookup"><span data-stu-id="b7ef4-267">See also:</span></span>

- <span data-ttu-id="b7ef4-268">[惡意的 Outlook 規則](https://silentbreaksecurity.com/malicious-outlook-rules/) SilentBreak 安全性文章關於規則向量可提供 Outlook 規則的詳細評論。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-268">[Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector provides a detailed review of how the Outlook Rules.</span></span>

- <span data-ttu-id="b7ef4-269">[MAPI OVER HTTP 和 Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) On the Sensepost Blog On Mailrule Pwnage 討論稱為尺規的工具，可讓您透過 Outlook 規則利用信箱。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-269">[MAPI over HTTP and Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog about Mailrule Pwnage discusses a tool called Ruler that lets you exploit mailboxes through Outlook rules.</span></span>

- <span data-ttu-id="b7ef4-270">Sensepost 博客上有關表單威脅向量的[Outlook 表單及 shell](https://sensepost.com/blog/2017/outlook-forms-and-shells/) 。</span><span class="sxs-lookup"><span data-stu-id="b7ef4-270">[Outlook forms and shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) on the Sensepost blog about Forms Threat Vector.</span></span>

- [<span data-ttu-id="b7ef4-271">尺規基本代碼</span><span class="sxs-lookup"><span data-stu-id="b7ef4-271">Ruler Codebase</span></span>](https://github.com/sensepost/ruler)

- [<span data-ttu-id="b7ef4-272">尺規指標洩露</span><span class="sxs-lookup"><span data-stu-id="b7ef4-272">Ruler Indicators of Compromise</span></span>](https://github.com/sensepost/notruler/blob/master/iocs.md)
