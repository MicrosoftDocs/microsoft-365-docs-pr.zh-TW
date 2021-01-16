---
title: 建立 iOS 裝置的 APNs 憑證
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: 以基本行動性和安全性管理 iOS 裝置。
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877077"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a><span data-ttu-id="40f03-103">建立 iOS 裝置的 APNs 憑證</span><span class="sxs-lookup"><span data-stu-id="40f03-103">Create an APNs certificate for iOS devices</span></span>

<span data-ttu-id="40f03-104">若要管理基本行動性和安全性中的 iOS 裝置（例如 Ipad 和 Iphone），請建立 APNs 憑證。</span><span class="sxs-lookup"><span data-stu-id="40f03-104">To manage iOS devices such as iPads and iPhones in Basic Mobility and Security, create an APNs certificate.</span></span>

1. <span data-ttu-id="40f03-105">使用您的全域系統管理員帳戶登入 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="40f03-105">Sign in to Microsoft 365 with your global admin account.</span></span>

2. <span data-ttu-id="40f03-106">在您的瀏覽器中輸入  [https://protection.office.com](https://protection.office.com/) 。</span><span class="sxs-lookup"><span data-stu-id="40f03-106">In your browser, type [https://protection.office.com](https://protection.office.com/).</span></span>

3. <span data-ttu-id="40f03-107">選取 [ **資料遺失防護**   >  **裝置管理**]，然後 **為 iOS 裝置選擇 APNs 憑證**。</span><span class="sxs-lookup"><span data-stu-id="40f03-107">Select  **Data loss prevention** > **Device management**, and choose **APNs Certificate for iOS devices**.</span></span>

4. <span data-ttu-id="40f03-108">在 [Apple 推播通知憑證設定] 頁面上，選擇 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="40f03-108">On the Apple Push Notification Certificate Settings page, choose **Next**.</span></span>

5. <span data-ttu-id="40f03-109">選取 [下載您的 CSR 檔案]，然後將憑證簽署要求儲存至電腦上您所記得的地方。</span><span class="sxs-lookup"><span data-stu-id="40f03-109">Select Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember.</span></span> <span data-ttu-id="40f03-110">選取  **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="40f03-110">Select  **Next**.</span></span>

6. <span data-ttu-id="40f03-111">在 [建立 APNs 憑證] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="40f03-111">On the Create an APNs certificate page:</span></span>  

    1. <span data-ttu-id="40f03-112">選取 Apple APNS 入口網站以開啟 Apple Push 憑證入口網站。</span><span class="sxs-lookup"><span data-stu-id="40f03-112">Select  Apple APNS Portal to open the Apple Push Certificates Portal.</span></span>

    2. <span data-ttu-id="40f03-113">Sign in with an Apple ID.</span><span class="sxs-lookup"><span data-stu-id="40f03-113">Sign in with an Apple ID.</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="40f03-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span><span class="sxs-lookup"><span data-stu-id="40f03-p102">Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.</span></span>

    3. <span data-ttu-id="40f03-116">選取 [  **建立憑證**]   並接受 [使用條款]。</span><span class="sxs-lookup"><span data-stu-id="40f03-116">Select  **Create a Certificate**  and accept the Terms of Use.</span></span>

    4. <span data-ttu-id="40f03-117">流覽至您從 Microsoft 365 下載到電腦的憑證簽署要求，然後選取 **[上傳**]。</span><span class="sxs-lookup"><span data-stu-id="40f03-117">Browse to the certificate signing request you downloaded to your computer from Microsoft 365, and select **Upload**.</span></span>

        <span data-ttu-id="40f03-118">將 Apple Push Certificate 入口網站建立的 APNs 憑證下載至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="40f03-118">Download the APNs certificate created by the Apple Push Certificate Portal to your computer.</span></span>

       >[!TIP]
       ><span data-ttu-id="40f03-119">If you're having trouble downloading the certificate, refresh your browser.</span><span class="sxs-lookup"><span data-stu-id="40f03-119">If you're having trouble downloading the certificate, refresh your browser.</span></span>

7. <span data-ttu-id="40f03-120">回到 [Microsoft 365]，然後選取 [**下一步]**   進入 [  **上傳 APNS 憑證**]   頁面。</span><span class="sxs-lookup"><span data-stu-id="40f03-120">Go back to Microsoft 365, and select **Next**  to get to the  **Upload APNS certificate** page.</span></span>

8. <span data-ttu-id="40f03-121"> Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span><span class="sxs-lookup"><span data-stu-id="40f03-121">Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.</span></span>

9. <span data-ttu-id="40f03-122">選取  **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="40f03-122">Select  **Finish**.</span></span>

<span data-ttu-id="40f03-123">若要完成安裝程式，請回到安全性 & 規範中心 > **安全性原則**   >  **裝置管理**   >  **管理設定**。</span><span class="sxs-lookup"><span data-stu-id="40f03-123">To complete setup, go back to the Security & Compliance Center > **Security policies** > **Device management** > **Manage settings**.</span></span>
