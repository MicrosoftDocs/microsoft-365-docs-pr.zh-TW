---
title: 自行註冊現有裝置
description: 登錄重複使用的裝置已經可能有自己，讓他們可以由 Microsoft 受管理的電腦
ms.prod: w10
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 1d9b390cc28002b4561d61fa1d6cc411f3b135f1
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112707"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="dd7e6-103">自行註冊現有裝置</span><span class="sxs-lookup"><span data-stu-id="dd7e6-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="dd7e6-104">本主題說明您可以重新使用的裝置您已經有，而且他們註冊 Microsoft 受管理電腦中的步驟。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="dd7e6-105">如果您正在使用全新的裝置，請改為按照中[自行註冊 Microsoft 受管理電腦中的新裝置](register-devices-self.md)的步驟。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="dd7e6-106">中[註冊裝置的協力廠商的步驟](register-devices-partner.md)會說明協力廠商的程序。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="dd7e6-107">Microsoft 受管理的電腦可搭配全新的裝置運作，或您可重複使用您可能已經擁有的裝置 (這需要您重新製作其映像)。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="dd7e6-108">您可以使用 Azure 入口網站上的 Microsoft 受管理的電腦來註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-108">You can register devices by using Microsoft Managed Desktop on the Azure Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="dd7e6-109">準備註冊現有裝置</span><span class="sxs-lookup"><span data-stu-id="dd7e6-109">Prepare to register existing devices</span></span>


<span data-ttu-id="dd7e6-110">若要登錄現有的裝置，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="dd7e6-111">取得每個裝置的硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="dd7e6-112">合併雜湊資料</span><span class="sxs-lookup"><span data-stu-id="dd7e6-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="dd7e6-113">[在 Microsoft 受管理的電腦中註冊裝置](#register-devices)。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-113">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="dd7e6-114">再次確認映像是否正確。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="dd7e6-115">交付裝置</span><span class="sxs-lookup"><span data-stu-id="dd7e6-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="dd7e6-116">取得硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="dd7e6-116">Obtain the hardware hash</span></span>

<span data-ttu-id="dd7e6-117">Microsoft 受管理的電腦會藉由參照其硬體雜湊來唯一識別每個裝置。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="dd7e6-118">您可以從您已經在使用的裝置取得這項資訊的四個選項：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="dd7e6-119">請向您的 OEM 提供者索取 AutoPilot 註冊檔案，其中會包含硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="dd7e6-120">在[Configuration Manager](#configuration-manager)中建立自訂報告。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-120">Create a custom report in [Configuration Manager](#configuration-manager).</span></span>
- <span data-ttu-id="dd7e6-121">可以執行 Windows PowerShell 指令碼-由上每個裝置--使用[Active Directory](#active-directory-powershell-script-method) ] 或 [[手動](#manual-powershell-script-method)並收集檔案中的結果。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="dd7e6-122">啟動每個裝置 (但不要完成 Windows 設定體驗)，然後[收集卸除式快閃磁碟機上的雜湊](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="configuration-manager"></a><span data-ttu-id="dd7e6-123">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dd7e6-123">Configuration Manager</span></span>

<span data-ttu-id="dd7e6-124">您可以使用 Microsoft 端點 Configuration Manager 從現有的裝置，您想要註冊 Microsoft 受管理電腦收集硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd7e6-125">您想要取得這項資訊的任何裝置必須執行 Windows 10 版本 1703年或更新版本。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> <span data-ttu-id="dd7e6-126">您也需要為連接至 Configuration Manager （最新分支） 站台的 Configuration Manager 用戶端裝置。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-126">You also need a device that is a Configuration Manager client connected to the Configuration Manager (Current Branch) site.</span></span> <span data-ttu-id="dd7e6-127">您也需要報告點網站系統角色設定您環境中使用 SQL Server Reporting Services 啟用。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-127">You also need the Reporting Point Site System role set up in your environment with SQL Server Reporting Services enabled.</span></span> 

<span data-ttu-id="dd7e6-128">如果您已符合所有這些必要條件，就可以依照下列步驟收集的資訊：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-128">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="dd7e6-129">在 Configuration Manager 主控台中，選取 [**監視**]。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-129">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="dd7e6-130">在監視工作區中，依序展開 [**報告**]，然後選取**報告**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-130">In the Monitoring workspace, expand **Reporting**, and then select **Reports**.</span></span> 
3. <span data-ttu-id="dd7e6-131">在 [**首頁**] 索引標籤上 [**建立**] 區段中，選取**建立報表**，以開啟 [建立報表] 精靈。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-131">On the **Home** tab, in the **Create** section, select **Create Report** to open the Create Report wizard.</span></span> 
4. <span data-ttu-id="dd7e6-132">在 [**資訊**] 頁面上，設定這些設定：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-132">On the **Information** page, set these settings:</span></span> 
    - <span data-ttu-id="dd7e6-133">**名稱：** 指定報表的名稱。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-133">**Name:** Specify a name for the report.</span></span> 
    - <span data-ttu-id="dd7e6-134">**描述：** 指定報表的描述。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-134">**Description:** Specify a description for the report.</span></span> 
    - <span data-ttu-id="dd7e6-135">**伺服器：** 會顯示在其上您要建立此報表的報表伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-135">**Server:** Displays the name of the report server on which you are creating this report.</span></span> 
    - <span data-ttu-id="dd7e6-136">**路徑：** 選取 [**瀏覽]** 以指定您要儲存的報告的資料夾]。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-136">**Path:** Select **Browse** to specify a folder in which you want to store the report.</span></span> 
5. <span data-ttu-id="dd7e6-137"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="dd7e6-137">Select **Next**.</span></span> 
6. <span data-ttu-id="dd7e6-138">在 [**摘要**] 頁面上檢閱設定。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-138">On the **Summary** page, review the settings.</span></span> <span data-ttu-id="dd7e6-139">選取 [變更設定，或選取 [**下一步**建立報表設定管理員] 中的**上一步**]。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-139">Select **Previous** to change the settings or select **Next** to create the report in Configuration Manager.</span></span> 
7. <span data-ttu-id="dd7e6-140">在 [**完成**] 頁面上選取 [**關閉**] 結束精靈]，並開啟**報表產生器**輸入報表的設定值。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-140">On the **Completion** page, select **Close** to exit the wizard and open **Report Builder** to enter the report settings.</span></span> <span data-ttu-id="dd7e6-141">輸入您的使用者帳戶和密碼，如果出現提示，，然後選取 [ **[確定]。**</span><span class="sxs-lookup"><span data-stu-id="dd7e6-141">Enter your user account and password if you are prompted, and then select **OK.**</span></span> <span data-ttu-id="dd7e6-142">如果報表產生器未安裝在裝置上，系統會提示您安裝它。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-142">If Report Builder is not installed on the device, you are prompted to install it.</span></span> <span data-ttu-id="dd7e6-143">選取 [**執行，以安裝報表產生器**，這必要修改和建立報告。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-143">Select **Run to install Report Builder**, which is required to modify and create reports.</span></span> 


<span data-ttu-id="dd7e6-144">**在 「 Microsoft 報表產生器中**，提供報表的 SQL 陳述式，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-144">**In Microsoft Report Builder**, provide the SQL statement for the report and follow these steps:</span></span>

1. <span data-ttu-id="dd7e6-145">在左窗格中，選取**資料集**，並用滑鼠右鍵按一下要**新增的資料集**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-145">In the left pane, select **Datasets**, and then right-click to **Add Dataset**.</span></span>
2. <span data-ttu-id="dd7e6-146">移至 [**查詢**] 索引標籤，然後為*DataSet0*輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-146">Go to the **Query** tab, and then enter the name as *DataSet0*.</span></span> 
3. <span data-ttu-id="dd7e6-147">選取 [**我的報表中內嵌使用資料集**;報表產生器開啟。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-147">Select **Use a dataset embedded in my report**; Report Builder opens.</span></span>
4. <span data-ttu-id="dd7e6-148">在 [**報表產生器中**，選取 [**資料來源：**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-148">In **Report Builder**, select **Data source:**.</span></span> <span data-ttu-id="dd7e6-149">選取預設資料來源，應該啟動與 「 AutoGen 」。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-149">Select the default data source, which should start with "AutoGen".</span></span> 
5. <span data-ttu-id="dd7e6-150">選擇 [**查詢類型為文字**，，然後輸入此查詢：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-150">Choose **Query type as Text**, and then enter this query:</span></span>




```sql
SELECT comp.manufacturer0      AS Manufacturer,  
       comp.model0             AS Model,  
       bios.serialnumber0      AS Serial_Number,  
       mdm.devicehardwaredata0 AS HardwareHash  
FROM   Fn_rbac_gs_computer_system(@UserSIDs) comp

       INNER JOIN Fn_rbac_gs_pc_bios(@UserSIDs) bios  
               ON comp.resourceid = bios.resourceid  
       INNER JOIN Fn_rbac_gs_mdm_devdetail_ext01(@UserSIDs) mdm  
               ON comp.resourceid = mdm.resourceid
```




5. <span data-ttu-id="dd7e6-151">瀏覽至 [**欄位**] 索引標籤中，應該已經填入 wehre 值的**欄位名稱**] 和 [**來源] 欄位**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-151">Navigate to the **Field** tab, wehre values for **Field Name** and **Field Source** should already be populated.</span></span> <span data-ttu-id="dd7e6-152">如果不是，然後選取 [**新增**]，然後選取 [**查詢] 欄位**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-152">If they aren't, then select **Add**, and then select **Query Field**.</span></span> <span data-ttu-id="dd7e6-153">輸入的**欄位名稱**和**欄位來源**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-153">Enter the **Field Name** and **Field Source**.</span></span>
6. <span data-ttu-id="dd7e6-154">重複針對每一個這些值：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-154">Repeat for each of these values:</span></span> 
    - <span data-ttu-id="dd7e6-155">製造商</span><span class="sxs-lookup"><span data-stu-id="dd7e6-155">Manufacturer</span></span> 
    - <span data-ttu-id="dd7e6-156">Model</span><span class="sxs-lookup"><span data-stu-id="dd7e6-156">Model</span></span> 
    - <span data-ttu-id="dd7e6-157">Serial_Number</span><span class="sxs-lookup"><span data-stu-id="dd7e6-157">Serial_Number</span></span> 
    - <span data-ttu-id="dd7e6-158">HardwareHash</span><span class="sxs-lookup"><span data-stu-id="dd7e6-158">HardwareHash</span></span>
7. <span data-ttu-id="dd7e6-159">選取 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-159">Select **OK**.</span></span>

<span data-ttu-id="dd7e6-160">**接下來，定義報告顯示，並建立報告**遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-160">**Next, define the report display and create the report** by following these steps:</span></span>

1. <span data-ttu-id="dd7e6-161">選取**表格或矩陣**;會開啟新的精靈。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-161">Select **Table or Matrix**; a new wizard will open.</span></span>
2. <span data-ttu-id="dd7e6-162">在 **[選擇資料集**，選取 [**選擇現有的資料集，在這份報告或共用資料集**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-162">In **Choose a dataset**, select **Choose an existing dataset in this report or a shared dataset**.</span></span>  
3. <span data-ttu-id="dd7e6-163">選取**DataSet0** （預設值），然後再選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-163">Select **DataSet0** (the default), and then select **Next**.</span></span>
4. <span data-ttu-id="dd7e6-164">將**製造商**、**模型**和**序號**拖曳至 [**列群組**] 方塊。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-164">Drag **Manufacturer**, **Model**, and **Serial Number** into the **Row Groups** box.</span></span> <span data-ttu-id="dd7e6-165">將**HardwareHash**拖曳至 [**值**] 方塊，然後選取 [**下一步**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-165">Drag **HardwareHash** into the **Values** box and then select **Next**.</span></span>
5. <span data-ttu-id="dd7e6-166">清除核取方塊，**顯示小計和總計**] 及 [**展開/折疊群組**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-166">Clear the checkboxes for **Show subtotals and grand totals** and **Expand/collapse groups**.</span></span> <span data-ttu-id="dd7e6-167"> Select **Next**. </span><span class="sxs-lookup"><span data-stu-id="dd7e6-167">Select **Next**.</span></span>
6. <span data-ttu-id="dd7e6-168">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="dd7e6-168">Select **Finish**.</span></span>
7. <span data-ttu-id="dd7e6-169">選取 [若要執行您的報表的 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-169">Select **Run** to run your report.</span></span> <span data-ttu-id="dd7e6-170">確認報告提供您所預期的資訊。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-170">Verify that the report provides the information that you expect.</span></span> <span data-ttu-id="dd7e6-171">如有必要，選取 [**設計**回到修改報表的 [設計] 檢視。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-171">If necessary, select **Design** to return to the Design view to modify the report.</span></span>
8. <span data-ttu-id="dd7e6-172">選取 [將報告儲存至 report server 的 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-172">Select **Save** to save the report to the report server.</span></span> <span data-ttu-id="dd7e6-173">您可以監視工作區中的 [報告] 節點中執行新的報表。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-173">You can run the new report in the Reports node in the Monitoring workspace.</span></span> 

<span data-ttu-id="dd7e6-174">**最後，將報告匯出並使用它來註冊裝置**遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-174">**Finally, export the report and use it to register devices** by following these steps.</span></span> <span data-ttu-id="dd7e6-175">（您應只需要遵循步驟 1 和 2 的這一節，如果您在先前步驟後立即瀏覽。）：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-175">(You should only need to follow Steps 1 and 2 of this section if you have navigated away after the previous steps.):</span></span>

1. <span data-ttu-id="dd7e6-176">在 Configuration Manager 主控台中，選取 [**監視**]。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-176">In the Configuration Manager console, select **Monitoring**.</span></span>
2. <span data-ttu-id="dd7e6-177">在 [**監視**]，依序展開 [**報告**]，然後再選取 [**報告**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-177">In **Monitoring**, expand **Reporting**, and then select **Reports**.</span></span>
3. <span data-ttu-id="dd7e6-178">尋找您稍早建立的報告使用的名稱。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-178">Find the report using the name you created earlier.</span></span>
4. <span data-ttu-id="dd7e6-179">這份報告，以滑鼠右鍵按一下，並選取 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-179">Right-click this report, and select **Run**.</span></span>
5. <span data-ttu-id="dd7e6-180">在 [開啟] 對話方塊中，選取 [**匯出**，然後選取 [**另存為 CSV**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-180">In the dialog that opens, select **Export** and then select **Save as CSV**.</span></span>
6. <span data-ttu-id="dd7e6-181">此版本的報表從 Configuration Manager 進行通訊的所有 Windows 10 裝置擷取雜湊。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-181">This version of report extracts hashes from all Windows 10 devices that Configuration Manager communicates with.</span></span> <span data-ttu-id="dd7e6-182">您將需要篩選至您要註冊 Microsoft 受管理電腦只要那些裝置的結果。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-182">You will need to filter results to just those devices you plan to register with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="dd7e6-183">在 Configuration Manager 中的查詢不允許匯出的資料行名稱; 中的空格這就是為什麼步驟有您輸入 「 Serial_Number 」 和 「 HardwareHash。 」</span><span class="sxs-lookup"><span data-stu-id="dd7e6-183">The query in Configuration Manager doesn’t allow spaces in exported column names; that's why the steps had you enter "Serial_Number" and "HardwareHash."</span></span> <span data-ttu-id="dd7e6-184">有匯出的 CSV 檔案之後，您必須編輯讀取*序號*和*硬體雜湊*後，再繼續裝置註冊如下所示的報告標頭。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-184">Now that you have the exported CSV file, you must edit the report headers to read *Serial Number* and *Hardware Hash* as shown here before you proceed with device registration.</span></span>

<span data-ttu-id="dd7e6-185">現在您可以繼續[註冊裝置使用 Azure 入口網站](#register-devices-by-using-the-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-185">Now you can proceed to [Register devices by using the Azure Portal](#register-devices-by-using-the-azure-portal).</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="dd7e6-186">Active Directory PowerShell 指令碼方法</span><span class="sxs-lookup"><span data-stu-id="dd7e6-186">Active Directory PowerShell script method</span></span>

<span data-ttu-id="dd7e6-187">在 Active Directory 環境中，您可以使用`Get-MMDRegistrationInfo`PowerShell cmdlet，以使用 WinRM 從遠端收集從 Active Directory 群組中的裝置的資訊。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-187">In an Active Directory environment, you can use the `Get-MMDRegistrationInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="dd7e6-188">您也可以使用`Get-AD Computer`指令程式，以及如何取得篩選結果的特定硬體模型包含目錄的應用程式的名稱。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-188">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="dd7e6-189">若要這麼做，請先確認下列必要條件，然後再繼續進行步驟：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-189">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="dd7e6-190">WinRM 已啟用。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-190">WinRM is enabled.</span></span>
- <span data-ttu-id="dd7e6-191">您要註冊的裝置會在網路上作用中 （也就是說，它們是不中斷連線或關閉）。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-191">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="dd7e6-192">請確定您已有執行遠端裝置上的權限的網域認證參數。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-192">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="dd7e6-193">請確定 Windows 防火牆允許存取 WMI。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-193">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="dd7e6-194">若要這麼做，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-194">To do that, follow these steps:</span></span>
    1. <span data-ttu-id="dd7e6-195">開啟 [控制台] 中的 [ **Windows Defender 防火牆**，然後選取 [**允許應用程式或功能通過 Windows Defender 防火牆**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-195">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    2. <span data-ttu-id="dd7e6-196">在清單中尋找**Windows Management Instrumentation (WMI)** 啟用這兩個**私密與公開金鑰**，，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-196">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="dd7e6-197">以系統管理權限開啟 PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-197">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="dd7e6-198">執行*其中一個*這些指令碼：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-198">Run *either one* of these scripts:</span></span>
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. <span data-ttu-id="dd7e6-199">存取任何目錄其中可能會有的裝置的項目。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-199">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="dd7e6-200">移除*所有*目錄，包括 Windows Server Active Directory 網域服務和 Azure Active Directory 中的每個裝置的項目。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-200">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="dd7e6-201">請注意此移除可能需要幾個小時才能完全處理程序。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-201">Be aware that this removal could take a few hours to completely process.</span></span>
4. <span data-ttu-id="dd7e6-202">存取管理服務其中可能會有的裝置的項目。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-202">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="dd7e6-203">移除*所有*的管理服務，包括 Microsoft 端點組態管理員、 Microsoft Intune 和 Windows Autopilot 為每個裝置的項目。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-203">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manger, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="dd7e6-204">請注意此移除可能需要幾個小時才能完全處理程序。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-204">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="dd7e6-205">現在您可以繼續[註冊裝置](#register-devices)。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-205">Now you can proceed to [register devices](#register-devices).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="dd7e6-206">手動 PowerShell 指令碼方法</span><span class="sxs-lookup"><span data-stu-id="dd7e6-206">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="dd7e6-207">以系統管理權限開啟 PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-207">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="dd7e6-208">執行 `Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="dd7e6-208">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="dd7e6-209">執行 `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="dd7e6-209">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="dd7e6-210">合併的雜湊資料。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-210">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="dd7e6-211">快閃磁碟機方法</span><span class="sxs-lookup"><span data-stu-id="dd7e6-211">Flash drive method</span></span>

1. <span data-ttu-id="dd7e6-212">在您要註冊的裝置以外的裝置上，插入 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-212">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="dd7e6-213">以系統管理權限開啟 PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-213">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="dd7e6-214">執行 `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="dd7e6-214">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="dd7e6-215">開啟您要註冊的裝置，但*請勿開始設定體驗*。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-215">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="dd7e6-216">如果您不小心開始設定體驗，則必須重設裝置或重新製作其映像。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-216">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="dd7e6-217">插入 USB 磁碟機，然後按 SHIFT + F10。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-217">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="dd7e6-218">以系統管理權限開啟 PowerShell 提示字元，然後執行 `cd <pathToUsb>`。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-218">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="dd7e6-219">執行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="dd7e6-219">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="dd7e6-220">執行 `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="dd7e6-220">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="dd7e6-221">移除 USB 磁碟機，然後執行 `shutdown -s -t 0` 以關閉裝置</span><span class="sxs-lookup"><span data-stu-id="dd7e6-221">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="dd7e6-222">合併的雜湊資料。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-222">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="dd7e6-223">在您完成註冊前，請勿開啟您所註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-223">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="dd7e6-224">合併雜湊資料</span><span class="sxs-lookup"><span data-stu-id="dd7e6-224">Merge hash data</span></span>

<span data-ttu-id="dd7e6-225">如果您手動 PowerShell 或快閃磁碟機方法所收集硬體雜湊資料，您現在需要在結合成單一檔案，以完成註冊的 CSV 檔案中有資料。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-225">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="dd7e6-226">以下是讓註冊變輕鬆的範例 PowerShell 指令碼：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-226">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

<span data-ttu-id="dd7e6-227">合併到一個 CSV 檔案的雜湊資料，您現在可以繼續[註冊裝置](#register-devices)。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-227">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices).</span></span>

### <a name="register-devices"></a><span data-ttu-id="dd7e6-228">註冊裝置</span><span class="sxs-lookup"><span data-stu-id="dd7e6-228">Register devices</span></span>

<span data-ttu-id="dd7e6-229">CSV 檔案必須採用可供註冊的特定格式。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-229">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="dd7e6-230">如果您在先前步驟中自行收集了資料，檔案應該已經是正確的格式。如果您是向供應商取得檔案，則可能需要調整格式。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-230">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="dd7e6-231">為了方便起見，您可以下載這個 CSV 檔案的[範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-231">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="dd7e6-232">您的檔案必須包含**完全相同的欄標題**作為範例一 (製造商、型號等)，但您自己的資料適用於其他列。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-232">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="dd7e6-233">如果您使用範本，請在記事本這類的文字編輯工具中開啟範本，然後不妨將列 1 的所有資料維持原狀，只在列 2 以下輸入資料。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-233">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="dd7e6-234">如果您忘記變更任何範例資料，註冊將會失敗。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-234">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="dd7e6-235">使用 Azure 入口網站來註冊裝置</span><span class="sxs-lookup"><span data-stu-id="dd7e6-235">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="dd7e6-236">從 Microsoft 受管理的電腦的 [Azure 入口網站](https://aka.ms/mmdportal)，選取左側導覽窗格中的 [裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-236">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="dd7e6-237">選取 [+ 註冊裝置]\*\*\*\*；飛入視窗隨即開啟：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-237">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="dd7e6-238">[![在選取 [註冊裝置] 之後飛入，並列出裝置與已指派使用者、序號、狀態、上次查看日期和年限等欄](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="dd7e6-238">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](images/register-devices-flyin-sterile.png)](images/register-devices-flyin-sterile.png)</span></span>


[//]: # (事實並非如此。我們可以移除此注意事項 - 但現在暫且擱置，留待我們有機會討論。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="dd7e6-240">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-240">Follow these steps:</span></span>

1. <span data-ttu-id="dd7e6-241">在 [檔案上傳]\*\*\*\* 中，提供您先前建立的 CSV 檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-241">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="dd7e6-242">或者，您可以新增 [訂單識別碼]\*\*\*\* 或 [購買識別碼]\*\*\*\*，以便自行追蹤。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-242">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="dd7e6-243">這些值沒有格式需求。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-243">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="dd7e6-244">選取 [註冊裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-244">Select **Register devices**.</span></span> <span data-ttu-id="dd7e6-245">系統會將裝置新增至 [裝置] 刀鋒視窗\*\*\*\* 上標示為 [註冊擱置]\*\*\*\* 的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-245">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="dd7e6-246">註冊通常需要不到 10 分鐘的時間，而註冊成功時，裝置將會顯示為 [使用者就緒]\*\*\*\*，標示其已準備就緒並等待終端使用者開始使用。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-246">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="dd7e6-247">您可以在主要 [Microsoft 受管理的電腦 - 裝置]\*\*\*\* 頁面上監視裝置註冊的進度。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-247">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="dd7e6-248">其回報的可能狀態包括：</span><span class="sxs-lookup"><span data-stu-id="dd7e6-248">Possible states reported there include:</span></span>

| <span data-ttu-id="dd7e6-249">狀態</span><span class="sxs-lookup"><span data-stu-id="dd7e6-249">State</span></span> | <span data-ttu-id="dd7e6-250">描述</span><span class="sxs-lookup"><span data-stu-id="dd7e6-250">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="dd7e6-251">註冊擱置</span><span class="sxs-lookup"><span data-stu-id="dd7e6-251">Registration pending</span></span> | <span data-ttu-id="dd7e6-252">尚未完成註冊。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-252">Registration is not done yet.</span></span> <span data-ttu-id="dd7e6-253">稍後再回頭檢查。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-253">Check back later.</span></span> |
| <span data-ttu-id="dd7e6-254">註冊失敗</span><span class="sxs-lookup"><span data-stu-id="dd7e6-254">Registration failed</span></span> | <span data-ttu-id="dd7e6-255">無法完成註冊。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-255">Registration could not be completed.</span></span> <span data-ttu-id="dd7e6-256">如需詳細資訊，請參閱[針對裝置註冊進行疑難排解](#troubleshooting-device-registration)。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-256">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="dd7e6-257">使用者就緒</span><span class="sxs-lookup"><span data-stu-id="dd7e6-257">Ready for user</span></span> | <span data-ttu-id="dd7e6-258">註冊成功，且裝置現在已準備好交付給使用者。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-258">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="dd7e6-259">Microsoft 受管理的電腦將會逐步引導使用者完成首次設定，因此您不需要再做任何進一步的準備。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-259">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="dd7e6-260">作用中</span><span class="sxs-lookup"><span data-stu-id="dd7e6-260">Active</span></span> | <span data-ttu-id="dd7e6-261">裝置已交付給終端使用者並已向您的租用戶註冊。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-261">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="dd7e6-262">這也表示使用者經常使用該裝置。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-262">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="dd7e6-263">非作用中</span><span class="sxs-lookup"><span data-stu-id="dd7e6-263">Inactive</span></span> | <span data-ttu-id="dd7e6-264">裝置已交付給終端使用者並已向您的租用戶註冊。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-264">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="dd7e6-265">不過，使用者最近尚未使用裝置 (在過去 7 天內)。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-265">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="dd7e6-266">針對裝置註冊進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="dd7e6-266">Troubleshooting device registration</span></span>

| <span data-ttu-id="dd7e6-267">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="dd7e6-267">Error message</span></span> | <span data-ttu-id="dd7e6-268">詳細資料</span><span class="sxs-lookup"><span data-stu-id="dd7e6-268">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="dd7e6-269">找不到裝置</span><span class="sxs-lookup"><span data-stu-id="dd7e6-269">Device not found</span></span> | <span data-ttu-id="dd7e6-270">我們無法註冊這個裝置，因為我們找不到與所提供的製造商、型號或序號相符的裝置。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-270">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="dd7e6-271">請與您的裝置供應商確認這些值。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-271">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="dd7e6-272">硬體雜湊無效</span><span class="sxs-lookup"><span data-stu-id="dd7e6-272">Hardware hash not valid</span></span> | <span data-ttu-id="dd7e6-273">您為這個裝置提供的硬體雜湊格式不正確。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-273">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="dd7e6-274">再次確認硬體雜湊，然後重新提交。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-274">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="dd7e6-275">裝置已經註冊</span><span class="sxs-lookup"><span data-stu-id="dd7e6-275">Device already registered</span></span> | <span data-ttu-id="dd7e6-276">此裝置已經註冊到您的組織。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-276">This device is already registered to your organization.</span></span> <span data-ttu-id="dd7e6-277">無需採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-277">No further action required.</span></span> |
| <span data-ttu-id="dd7e6-278">其他組織所宣告的裝置</span><span class="sxs-lookup"><span data-stu-id="dd7e6-278">Device claimed by another organization</span></span> | <span data-ttu-id="dd7e6-279">此裝置已經由其他組織所宣告。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-279">This device has already been claimed by another organization.</span></span> <span data-ttu-id="dd7e6-280">請洽詢您的裝置供應商。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-280">Check with your device supplier.</span></span> |
| <span data-ttu-id="dd7e6-281">未預期的錯誤</span><span class="sxs-lookup"><span data-stu-id="dd7e6-281">Unexpected error</span></span> | <span data-ttu-id="dd7e6-282">無法自動處理您的要求。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-282">Your request could not be automatically processed.</span></span> <span data-ttu-id="dd7e6-283">連絡客戶支援並提供要求識別碼：<requestId></span><span class="sxs-lookup"><span data-stu-id="dd7e6-283">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="dd7e6-284">檢查映像</span><span class="sxs-lookup"><span data-stu-id="dd7e6-284">Check the image</span></span>

<span data-ttu-id="dd7e6-285">如果您的裝置來自 Microsoft 受管理的電腦合作夥伴供應商，映射應是正確的。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-285">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="dd7e6-286">如果您想要的話，也歡迎您自行套用映像。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-286">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="dd7e6-287">若要開始使用，請連絡您的 Microsoft 代表，他們會將映像的位置及其套用步驟提供給您。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-287">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="dd7e6-288">交付裝置</span><span class="sxs-lookup"><span data-stu-id="dd7e6-288">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd7e6-289">將裝置交給使用者之前，請確認您已取得並套用[適合該使用者的授權](../get-ready/prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-289">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="dd7e6-290">如果已套用所有授權，您可以[讓使用者準備好使用裝置](get-started-devices.md)，然後使用者即可啟動裝置並繼續進行 Windows 設定體驗。</span><span class="sxs-lookup"><span data-stu-id="dd7e6-290">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









