---
title: 設定基本行動與安全性
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 設定基本行動性和安全性，以保護和管理使用者的行動裝置。
ms.openlocfilehash: 38f122141b370468bc591df49b3e1891a8a66a43
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876861"
---
# <a name="set-up-basic-mobility-and-security"></a><span data-ttu-id="bb4b4-103">設定基本行動與安全性</span><span class="sxs-lookup"><span data-stu-id="bb4b4-103">Set up Basic Mobility and Security</span></span>

<span data-ttu-id="bb4b4-104">Microsoft 365 的內建基本行動性和安全性可協助您保護和管理使用者的行動裝置，例如 Iphone、Ipad、Androids 和 Windows phone。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-104">The built-in Basic Mobility and Security for Microsoft 365 helps you secure and manage users' mobile devices such as iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="bb4b4-105">您可以建立及管理裝置安全性原則、遠端抹除裝置資料，以及檢視詳細的裝置報告。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-105">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

<span data-ttu-id="bb4b4-106">Have questions?</span><span class="sxs-lookup"><span data-stu-id="bb4b4-106">Have questions?</span></span> <span data-ttu-id="bb4b4-107">如需協助解決常見問題的常見問題，請參閱 [基本行動性及安全性常見問題 (常見問題) ](frequently-asked-questions.md)。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-107">For a FAQ to help address common questions, see [Basic Mobility and Security Frequently-asked questions (FAQ)](frequently-asked-questions.md).</span></span> <span data-ttu-id="bb4b4-108">請注意，您無法使用委派的系統管理員帳戶來管理基本行動性和安全性。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-108">Be aware that you cannot use a delegated administrator account to manage Basic Mobility and Security.</span></span> <span data-ttu-id="bb4b4-109">如需詳細資訊，請參閱 [合作夥伴：提供委派的管理](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e)。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-109">For more info, see [Partners: Offer delegated administration](https://support.microsoft.com/office/partners-offer-delegated-administration-26530dc0-ebba-415b-86b1-b55bc06b073e).</span></span> 

<span data-ttu-id="bb4b4-110">裝置管理是安全性 & 規範中心的一部分，因此您必須先開始執行基本行動及安全性設定。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-110">Device management is part of the Security & Compliance Center so you'll need to go there to kick off Basic Mobility and Security setup.</span></span>

## <a name="activate-the-basic-mobility-and-security-service"></a><span data-ttu-id="bb4b4-111">啟動基本行動及安全性服務</span><span class="sxs-lookup"><span data-stu-id="bb4b4-111">Activate the Basic Mobility and Security service</span></span>

1. <span data-ttu-id="bb4b4-112">使用您的全域系統管理員帳戶登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-112">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="bb4b4-113">移至 [ [啟用基本行動及安全性](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)]。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-113">Go to [Activate Basic Mobility and Security](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span>

   <span data-ttu-id="bb4b4-114">啟用基本行動性和安全性可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-114">It can take some time to activate Basic Mobility and Security.</span></span> <span data-ttu-id="bb4b4-115">完成後，您會收到一封電子郵件，說明接下來要採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-115">When it finishes, you'll receive an email that explains the next steps to take.</span></span>

## <a name="set-up-mobile-device-management"></a><span data-ttu-id="bb4b4-116">設定行動裝置管理</span><span class="sxs-lookup"><span data-stu-id="bb4b4-116">Set up Mobile Device Management</span></span>

<span data-ttu-id="bb4b4-117">當服務準備好時，請完成下列步驟以完成安裝程式。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-117">When the service is ready, complete the following steps to finish setup.</span></span>

### <a name="step-1-required-configure-domains-for-basic-mobility-and-security"></a><span data-ttu-id="bb4b4-118">步驟1： (必要) 設定網域以取得基本行動性和安全性</span><span class="sxs-lookup"><span data-stu-id="bb4b4-118">Step 1: (Required) Configure domains for Basic Mobility and Security</span></span>

<span data-ttu-id="bb4b4-119">如果您沒有與 Microsoft 365 相關聯的自訂網域，或者您不是管理 Windows 裝置，則可以略過本節。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-119">If you don't have a custom domain associated with Microsoft 365 or if you're not managing Windows devices, you can skip this section.</span></span> <span data-ttu-id="bb4b4-120">否則，您必須在您的 DNS 主機上新增網域的 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-120">Otherwise, you'll need to add DNS records for the domain at your DNS host.</span></span> <span data-ttu-id="bb4b4-121">如果您已新增記錄，請在使用 Microsoft 365 設定網域時，全部都是設定。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-121">If you've added the records already, as part of setting up your domain with Microsoft 365, you're all set.</span></span> <span data-ttu-id="bb4b4-122">在您新增記錄之後，您組織中使用您自訂網域的電子郵件地址登入之 Windows 裝置的 Microsoft 365 使用者會重新導向，以登錄基本行動性和安全性。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-122">After you add the records, Microsoft 365 users in your organization who sign in on their Windows device with an email address that uses your custom domain are redirected to enroll in Basic Mobility and Security.</span></span>

<span data-ttu-id="bb4b4-123">需要設定記錄的協助嗎？</span><span class="sxs-lookup"><span data-stu-id="bb4b4-123">Need help setting up the records?</span></span> <span data-ttu-id="bb4b4-124">尋找您的網域註冊機構，並選取 [註冊機構名稱]，以移至 [[新增 dns 記錄] 以連接您的網域](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)時，在清單中建立 dns 記錄的逐步說明。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-124">Find your domain registrar and select the registrar name to go to step-by-step help for creating DNS record in the list provided in [Add DNS records to connect your domain](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span> <span data-ttu-id="bb4b4-125">使用這些指示來建立簡化的 Windows 登記中所述的 CNAME 記錄， [而不使用 AZURE AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium)。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-125">Use those instructions to create CNAME records described in [Simplify Windows enrollment without Azure AD Premium](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#simplify-windows-enrollment-without-azure-ad-premium).</span></span>

<span data-ttu-id="bb4b4-126">新增這兩個 CNAME 記錄後，請回到安全性 & 合規性中心，然後移至 [**資料遺失防護**  >  **裝置管理**   ] 以完成下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-126">After you add the two CNAME records, go back to the Security & Compliance Center and go to **Data loss prevention** > **Device management** to complete the next step.</span></span>

### <a name="step-2-required-configure-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="bb4b4-127">步驟2： (必要) 設定 iOS 裝置的 APNs 憑證</span><span class="sxs-lookup"><span data-stu-id="bb4b4-127">Step 2: (Required) Configure an APNs Certificate for iOS devices</span></span>

<span data-ttu-id="bb4b4-128">若要管理的 iOS 裝置如 iPad 和 Iphone，您必須建立 APNs 憑證。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-128">To manage iOS devices like iPad and iPhones, you need to create an APNs certificate.</span></span>

1. <span data-ttu-id="bb4b4-129">使用您的全域系統管理員帳戶登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-129">Sign in to  Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="bb4b4-130">在您的瀏覽器類型：中  [https://protection.office.com](https://protection.office.com/) 。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-130">In your browser type: [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="bb4b4-131">選取 [ **資料遺失防護**   >  **裝置管理**]，然後 **為 iOS 裝置選擇 APNs 憑證**。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-131">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="bb4b4-132">在 [Apple 推播通知憑證設定] 頁面上，選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-132">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="bb4b4-133">選取 [ **下載您的 CSR** 檔案]   ，然後將憑證簽署要求儲存至電腦上您所記得的地方。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-133">Select **Download your CSR file** and save the Certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="bb4b4-134">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-134">Select **Next**.</span></span>

6. <span data-ttu-id="bb4b4-135">在 [建立 APNs 憑證] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="bb4b4-135">On the Create an APNs certificate page:</span></span>

   - <span data-ttu-id="bb4b4-136">選取 Apple APNS 入口網站以開啟 Apple Push 憑證入口網站。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-136">Select Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>
   - <span data-ttu-id="bb4b4-137">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="bb4b4-137">Sign in with an Apple ID.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="bb4b4-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="bb4b4-p107">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

   - <span data-ttu-id="bb4b4-140">選取 [建立憑證] 並接受 [使用條款]。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-140">Select Create a Certificate and accept the Terms of Use.</span></span>
   - <span data-ttu-id="bb4b4-141">流覽至您從 Microsoft 365 和 selectUpload 下載到電腦的憑證簽署要求。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-141">Browse to the Certificate signing request you downloaded to your computer from Microsoft 365 and selectUpload.</span></span>
   - <span data-ttu-id="bb4b4-142">Download the APN certificate created by the Apple Push Certificate Portal to your computer.</span><span class="sxs-lookup"><span data-stu-id="bb4b4-142">Download the APN certificate created by the Apple Push Certificate Portal to your computer.</span></span>

     > [!TIP]
     > <span data-ttu-id="bb4b4-143">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="bb4b4-143">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="bb4b4-144">請回到 Microsoft 365，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-144">Go back to Microsoft 365 and select **Next**.</span></span>

8. <span data-ttu-id="bb4b4-145"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="bb4b4-145">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="bb4b4-146">選取  **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-146">Select  **Finish**.</span></span>

### <a name="step-3-recommended-set-up-multi-factor-authentication"></a><span data-ttu-id="bb4b4-147">步驟3： (建議) 設定多重要素驗證</span><span class="sxs-lookup"><span data-stu-id="bb4b4-147">Step 3: (Recommended) Set up multi-factor authentication</span></span>

<span data-ttu-id="bb4b4-148">由於要求第二種驗證格式，MFA 可協助您保護登入 Microsoft 365 以進行行動裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-148">MFA helps secure the sign in to Microsoft 365 for mobile device enrollment by requiring a second form of authentication.</span></span> <span data-ttu-id="bb4b4-149">使用者在輸入其工作帳戶密碼後，必須在其行動裝置上認可來電、文字訊息或代理程式更新。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-149">Users are required to acknowledge a phone call, text message, or app notification on their mobile device after correctly entering their work account password.</span></span> <span data-ttu-id="bb4b4-150">他們只能在第二個驗證表單完成後註冊其裝置。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-150">They can enroll their device only after this second form of authentication is completed.</span></span> <span data-ttu-id="bb4b4-151">在使用基本行動性和安全性的使用者裝置登錄之後，使用者只可以存取其工作帳戶的 Microsoft 365 資源。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-151">After user devices are enrolled in Basic Mobility and Security, users can access Microsoft 365 resources with only their work account.</span></span>

<span data-ttu-id="bb4b4-152">若要瞭解如何在 Azure AD 入口網站中開啟 MFA，請參閱 [設定多重要素驗證](https://go.microsoft.com/fwlink/p/?LinkId=519255)。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-152">To learn how to turn on MFA in the Azure AD portal, see [Set up multi-factor authentication](https://go.microsoft.com/fwlink/p/?LinkId=519255).</span></span>

<span data-ttu-id="bb4b4-153">設定 MFA 後，請回到安全性 & 合規性中心，並流覽至「 **資料遺失防護**」   >  **裝置管理**   >  **裝置原則**，   以完成下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-153">After you set up MFA, go back to the Security & Compliance Center and navigate to  **Data loss prevention** > **Device management** > **Device policies** to complete the next step.</span></span>

### <a name="step-4-recommended-manage-device-security-policies"></a><span data-ttu-id="bb4b4-154">步驟4： (建議) 管理裝置安全性原則</span><span class="sxs-lookup"><span data-stu-id="bb4b4-154">Step 4: (Recommended) Manage device security policies</span></span>

<span data-ttu-id="bb4b4-155">下一步是建立及部署裝置安全性原則，以協助保護您的 Microsoft 365 組織資料。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-155">The next step is to create and deploy device security policies to help protect your Microsoft 365 organization data.</span></span> <span data-ttu-id="bb4b4-156">例如，您可以在三次登入失敗之後建立一個原則，以鎖定裝置，以鎖定裝置，以防止資料遺失（如果使用者在非活動狀態和擦除裝置上鎖定裝置）。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-156">For example, you can help prevent data loss if a user loses their device by creating a policy to lock devices after five minutes of inactivity and wipe devices after three sign-in failures.</span></span>

1. <span data-ttu-id="bb4b4-157">使用您的全域系統管理員帳戶登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-157">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="bb4b4-158">選取 [ [啟用行動裝置管理](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx)]。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-158">Select [Activate Mobile Device Management](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx).</span></span> <span data-ttu-id="bb4b4-159">如果服務已啟動，則改為啟用步驟，您會看到 [管理裝置](https://admin.microsoft.com/adminportal/home#/MifoDevices)的連結   。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-159">If the service is activated, instead the activation steps you'll see a link to [Manage Devices](https://admin.microsoft.com/adminportal/home#/MifoDevices) .</span></span>

3. <span data-ttu-id="bb4b4-160">移至 [ **裝置原則**]。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-160">Go to **Device policies**.</span></span>

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="基本安全性和行動性原則設定":::

4. <span data-ttu-id="bb4b4-162">遵循以 [基本行動性和安全性建立裝置安全性原則中](create-device-security-policies.md)的步驟，建立及部署適用于貴組織的裝置安全性原則。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-162">Create and deploy device security policies appropriate for your organization following the steps in [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).</span></span>

> [!TIP]
>
> - <span data-ttu-id="bb4b4-163">當您建立新的原則時，您可能會想要設定原則，以允許在使用者裝置與原則不相容的情況下進行存取和報告原則侵犯。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-163">When you create a new policy, you might want to set the policy to allow access and report policy violation where a user device isn't compliant with the policy.</span></span> <span data-ttu-id="bb4b4-164">這可讓您查看原則所影響的行動裝置數目，而不會封鎖對 Microsoft 365 的存取。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-164">This allows you see how many mobile devices are impacted by the policy without blocking access to Microsoft 365.</span></span>
>
> - <span data-ttu-id="bb4b4-165">在您將新的原則部署給組織中的每個人之前，我們建議您在少量使用者所使用的裝置上進行測試。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-165">Before you deploy a new policy to everyone in your organization, we recommend you test it on the devices used by a small number of users.</span></span>
>
> - <span data-ttu-id="bb4b4-166">此外，在您部署原則之前，請讓您的組織知道使用基本行動性和安全性登錄裝置的潛在影響。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-166">Also, before you deploy policies, let your organization know the potential impacts of enrolling a device in Basic Mobility and Security.</span></span> <span data-ttu-id="bb4b4-167">根據您設定原則的方式，不遵循 (不相容裝置之原則的裝置) 可以封鎖存取 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-167">Depending on how you set up the policies, devices that don't comply with policies (non-compliant devices) could be blocked from accessing Microsoft 365.</span></span> <span data-ttu-id="bb4b4-168">不相容的裝置也可能會在擦除裝置時，在已註冊的裝置上安裝應用程式、相片和其他個人資訊。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-168">Non-compliant devices might also have apps installed, photos, and other personal information which, on an enrolled device, could be deleted if the device is wiped.</span></span> <span data-ttu-id="bb4b4-169">如需詳細資訊，請參閱 [在基本行動及安全性中清除行動裝置](wipe-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-169">For more info, see [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).</span></span>

## <a name="make-sure-users-enroll-their-devices"></a><span data-ttu-id="bb4b4-170">請確定使用者已註冊其裝置</span><span class="sxs-lookup"><span data-stu-id="bb4b4-170">Make sure users enroll their devices</span></span>

<span data-ttu-id="bb4b4-171">在您建立並部署行動裝置管理原則之後，組織中的每一個已授權的 Microsoft 365 使用者在下次從其行動裝置登入 Microsoft 365 時，該使用者就會收到註冊郵件。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-171">After you've created and deployed a mobile device management policy, each licensed Microsoft 365 user in your organization that the device policy applies receives an enrollment message the next time they sign into Microsoft 365 from their mobile device.</span></span> <span data-ttu-id="bb4b4-172">他們必須先完成註冊和啟用步驟，才能存取 Microsoft 365 電子郵件和檔。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-172">They must complete the enrollment and activation steps before they can access Microsoft 365 email and documents.</span></span> <span data-ttu-id="bb4b4-173">如需詳細資訊，請參閱 [使用基本行動性和安全性註冊行動裝置](enroll-your-mobile-device.md)。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-173">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb4b4-174">如果註冊程式不支援使用者的慣用語言，使用者可能會在其行動裝置上以其他語言接收註冊通知和步驟。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-174">If a user's preferred language isn't supported by the enrollment process, users might receive enrollment notification and steps on their mobile devices in another language.</span></span> <span data-ttu-id="bb4b4-175">在行動裝置上，目前不支援所有 Microsoft 365 中支援的語言註冊程式。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-175">Not all languages supported in Microsoft 365 are currently supported for the enrollment process on mobile devices.</span></span>

<span data-ttu-id="bb4b4-176">必須有 Android 或 iOS 裝置的使用者，才能安裝公司入口網站應用程式作為註冊過程的一部分。</span><span class="sxs-lookup"><span data-stu-id="bb4b4-176">Users with Android or iOS devices are required to install the Company Portal app as part of the enrollment process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bb4b4-177">相關主題</span><span class="sxs-lookup"><span data-stu-id="bb4b4-177">Related Topics</span></span>

[<span data-ttu-id="bb4b4-178">基本行動與安全性的功能</span><span class="sxs-lookup"><span data-stu-id="bb4b4-178">Capabilities of Basic Mobility and Security</span></span>](capabilities.md)<br/>
[<span data-ttu-id="bb4b4-179">在基本行動性和安全性中建立裝置安全性原則</span><span class="sxs-lookup"><span data-stu-id="bb4b4-179">Create device security policies in Basic Mobility and Security</span></span>](create-device-security-policies.md)