---
title: 自行註冊現有裝置
description: 登錄已重新使用的裝置，使其可由 Microsoft 受管理的電腦進行管理
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: abe9e63eb4fcd31993bd26822dc445ff0e48e369
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101482"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="f4b0e-103">自行註冊現有裝置</span><span class="sxs-lookup"><span data-stu-id="f4b0e-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="f4b0e-104">本主題說明重新使用已有的裝置的步驟，並在 Microsoft 受管理的電腦中註冊這些裝置。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="f4b0e-105">如果您正在使用全新的裝置，請依照直接在[Microsoft 管理的桌面中註冊新裝置](register-devices-self.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="f4b0e-106">合作夥伴的程式會記錄在協力廠商，以[供協力廠商註冊裝置](register-devices-partner.md)。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="f4b0e-107">Microsoft 受管理的電腦可搭配全新的裝置運作，或您可重複使用您可能已經擁有的裝置 (這需要您重新製作其映像)。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="f4b0e-108">您可以使用 Microsoft Managed Desktop Admin 入口網站來註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-108">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="f4b0e-109">準備註冊現有的裝置</span><span class="sxs-lookup"><span data-stu-id="f4b0e-109">Prepare to register existing devices</span></span>


<span data-ttu-id="f4b0e-110">若要註冊現有的裝置，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="f4b0e-111">取得每個裝置的硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="f4b0e-112">合併雜湊資料</span><span class="sxs-lookup"><span data-stu-id="f4b0e-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="f4b0e-113">[在 Microsoft 受管理的電腦中註冊裝置](#register-devices)。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-113">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="f4b0e-114">再次確認映像是否正確。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="f4b0e-115">交付裝置</span><span class="sxs-lookup"><span data-stu-id="f4b0e-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="f4b0e-116">取得硬體雜湊</span><span class="sxs-lookup"><span data-stu-id="f4b0e-116">Obtain the hardware hash</span></span>

<span data-ttu-id="f4b0e-117">Microsoft 受管理的電腦會藉由參照其硬體雜湊來唯一識別每個裝置。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="f4b0e-118">您有四個選項可從您已在使用的裝置取得此資訊：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="f4b0e-119">請向您的 OEM 提供者索取 AutoPilot 註冊檔案，其中會包含硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="f4b0e-120">在[Configuration Manager](#configuration-manager)中建立自訂報告。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-120">Create a custom report in [Configuration Manager](#configuration-manager).</span></span>
- <span data-ttu-id="f4b0e-121">在每個裝置上使用[Active Directory](#active-directory-powershell-script-method)或[手動](#manual-powershell-script-method)執行 Windows PowerShell script--並收集檔案中的結果。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="f4b0e-122">啟動每個裝置 (但不要完成 Windows 設定體驗)，然後[收集卸除式快閃磁碟機上的雜湊](#flash-drive-method)。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="configuration-manager"></a><span data-ttu-id="f4b0e-123">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f4b0e-123">Configuration Manager</span></span>

<span data-ttu-id="f4b0e-124">您可以使用 Microsoft 端點 Configuration Manager 來收集您要使用 Microsoft Managed Desktop 註冊的現有裝置的硬體雜湊。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4b0e-125">您要取得此資訊的任何裝置都必須執行 Windows 10、版本1703或更新版本。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> <span data-ttu-id="f4b0e-126">您也需要一個裝置，該裝置會連接到設定管理員 (目前的分支) 網站。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-126">You also need a device that is a Configuration Manager client connected to the Configuration Manager (Current Branch) site.</span></span> <span data-ttu-id="f4b0e-127">您也需要在啟用 SQL Server Reporting Services 的環境中設定報告點網站系統角色。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-127">You also need the Reporting Point Site System role set up in your environment with SQL Server Reporting Services enabled.</span></span> 

<span data-ttu-id="f4b0e-128">如果您已符合所有這些必要條件，您可以遵循下列步驟來收集資訊：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-128">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="f4b0e-129">在 Configuration Manager 主控台中，選取 [**監視**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-129">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="f4b0e-130">在 [監視] 工作區中，展開 [**報告**]，然後選取 [**報告**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-130">In the Monitoring workspace, expand **Reporting**, and then select **Reports**.</span></span> 
3. <span data-ttu-id="f4b0e-131">在 [**首頁**] 索引標籤上，選取 [**建立**] 區段中的 [**建立報告**] 以開啟 [建立報表] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-131">On the **Home** tab, in the **Create** section, select **Create Report** to open the Create Report wizard.</span></span> 
4. <span data-ttu-id="f4b0e-132">在 [**資訊**] 頁面上，設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-132">On the **Information** page, set these settings:</span></span> 
    - <span data-ttu-id="f4b0e-133">**名稱：** 指定報表的名稱。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-133">**Name:** Specify a name for the report.</span></span> 
    - <span data-ttu-id="f4b0e-134">**描述：** 指定報表的描述。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-134">**Description:** Specify a description for the report.</span></span> 
    - <span data-ttu-id="f4b0e-135">**伺服器：** 顯示您要建立此報告的報表伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-135">**Server:** Displays the name of the report server on which you are creating this report.</span></span> 
    - <span data-ttu-id="f4b0e-136">**路徑：** 選取 **[流覽]** 以指定您要用來儲存報告的資料夾。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-136">**Path:** Select **Browse** to specify a folder in which you want to store the report.</span></span> 
5. <span data-ttu-id="f4b0e-137">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-137">Select **Next**.</span></span> 
6. <span data-ttu-id="f4b0e-138">在 [**摘要**] 頁面上，複查設定。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-138">On the **Summary** page, review the settings.</span></span> <span data-ttu-id="f4b0e-139">選取 [**上一**步] 以變更設定，或選取 **[下一步]** 以在 Configuration Manager 中建立報告。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-139">Select **Previous** to change the settings or select **Next** to create the report in Configuration Manager.</span></span> 
7. <span data-ttu-id="f4b0e-140">在 [**完成**] 頁面上，選取 [關閉]，**結束**嚮導並開啟**報表**產生器以輸入報表設定。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-140">On the **Completion** page, select **Close** to exit the wizard and open **Report Builder** to enter the report settings.</span></span> <span data-ttu-id="f4b0e-141">出現提示時，請輸入您的使用者帳戶和密碼，然後選取 **[確定]。**</span><span class="sxs-lookup"><span data-stu-id="f4b0e-141">Enter your user account and password if you are prompted, and then select **OK.**</span></span> <span data-ttu-id="f4b0e-142">如果裝置上未安裝報表建立器，系統會提示您進行安裝。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-142">If Report Builder is not installed on the device, you are prompted to install it.</span></span> <span data-ttu-id="f4b0e-143">選取 [執行]，以安裝修改及建立報表所需的**報表**產生器。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-143">Select **Run to install Report Builder**, which is required to modify and create reports.</span></span> 


<span data-ttu-id="f4b0e-144">**在 Microsoft Report Builder 中**，提供報表的 SQL 語句，然後遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-144">**In Microsoft Report Builder**, provide the SQL statement for the report and follow these steps:</span></span>

1. <span data-ttu-id="f4b0e-145">在左窗格中，選取 [**資料集**]，然後以滑鼠右鍵按一下以**新增資料集**。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-145">In the left pane, select **Datasets**, and then right-click to **Add Dataset**.</span></span>
2. <span data-ttu-id="f4b0e-146">移至 [**查詢**] 索引標籤，然後輸入名稱為*DataSet0*。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-146">Go to the **Query** tab, and then enter the name as *DataSet0*.</span></span> 
3. <span data-ttu-id="f4b0e-147">選取 [**使用內嵌在我的報表中的資料集**];報表建立器隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-147">Select **Use a dataset embedded in my report**; Report Builder opens.</span></span>
4. <span data-ttu-id="f4b0e-148">在**報表**建立器中，選取 [**資料來源：**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-148">In **Report Builder**, select **Data source:**.</span></span> <span data-ttu-id="f4b0e-149">選取 [預設資料來源]，其開頭應為 "AutoGen"。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-149">Select the default data source, which should start with "AutoGen".</span></span> 
5. <span data-ttu-id="f4b0e-150">選擇 [**查詢類型] 做為 [文字**]，然後輸入下列查詢：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-150">Choose **Query type as Text**, and then enter this query:</span></span>




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




5. <span data-ttu-id="f4b0e-151">流覽至 [**欄位**] 索引標籤， **Field Name** Wehre 功能變數名稱和**欄位來源**的值應該已經填滿。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-151">Navigate to the **Field** tab, wehre values for **Field Name** and **Field Source** should already be populated.</span></span> <span data-ttu-id="f4b0e-152">如果不是，請選取 [**新增**]，然後選取 [**查詢欄位**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-152">If they aren't, then select **Add**, and then select **Query Field**.</span></span> <span data-ttu-id="f4b0e-153">輸入功能變數名稱**和\*\*\*\*欄位來源**。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-153">Enter the **Field Name** and **Field Source**.</span></span>
6. <span data-ttu-id="f4b0e-154">針對下列每個值重複：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-154">Repeat for each of these values:</span></span> 
    - <span data-ttu-id="f4b0e-155">製造商</span><span class="sxs-lookup"><span data-stu-id="f4b0e-155">Manufacturer</span></span> 
    - <span data-ttu-id="f4b0e-156">Model</span><span class="sxs-lookup"><span data-stu-id="f4b0e-156">Model</span></span> 
    - <span data-ttu-id="f4b0e-157">Serial_Number</span><span class="sxs-lookup"><span data-stu-id="f4b0e-157">Serial_Number</span></span> 
    - <span data-ttu-id="f4b0e-158">HardwareHash</span><span class="sxs-lookup"><span data-stu-id="f4b0e-158">HardwareHash</span></span>
7. <span data-ttu-id="f4b0e-159">選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-159">Select **OK**.</span></span>

<span data-ttu-id="f4b0e-160">**接下來，依照下列步驟定義報告顯示並建立報告**：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-160">**Next, define the report display and create the report** by following these steps:</span></span>

1. <span data-ttu-id="f4b0e-161">選取**表格或矩陣**;隨即會開啟新的嚮導。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-161">Select **Table or Matrix**; a new wizard will open.</span></span>
2. <span data-ttu-id="f4b0e-162">在 **[選擇資料集**] 中，選取 **[選擇此報告中的現有資料集] 或 [共用資料集**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-162">In **Choose a dataset**, select **Choose an existing dataset in this report or a shared dataset**.</span></span>  
3. <span data-ttu-id="f4b0e-163">選取 [ **DataSet0** (預設) ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-163">Select **DataSet0** (the default), and then select **Next**.</span></span>
4. <span data-ttu-id="f4b0e-164">將**Manufacturer**、 **Model**和**序數**拖曳至 [**列群組**] 方塊中。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-164">Drag **Manufacturer**, **Model**, and **Serial Number** into the **Row Groups** box.</span></span> <span data-ttu-id="f4b0e-165">將**HardwareHash**拖曳至 [**值**] 方塊中，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-165">Drag **HardwareHash** into the **Values** box and then select **Next**.</span></span>
5. <span data-ttu-id="f4b0e-166">清除 [**顯示小計和**總計] 的核取方塊，然後**展開/折疊群組**。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-166">Clear the checkboxes for **Show subtotals and grand totals** and **Expand/collapse groups**.</span></span> <span data-ttu-id="f4b0e-167">選取 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-167">Select **Next**.</span></span>
6. <span data-ttu-id="f4b0e-168">Select **Finish**.</span><span class="sxs-lookup"><span data-stu-id="f4b0e-168">Select **Finish**.</span></span>
7. <span data-ttu-id="f4b0e-169">選取 [**執行**] 執行您的報表。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-169">Select **Run** to run your report.</span></span> <span data-ttu-id="f4b0e-170">驗證報告是否提供您預期的資訊。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-170">Verify that the report provides the information that you expect.</span></span> <span data-ttu-id="f4b0e-171">如有必要，請選取 [**設計**] 以回到設計檢視，以修改報告。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-171">If necessary, select **Design** to return to the Design view to modify the report.</span></span>
8. <span data-ttu-id="f4b0e-172">選取 [**儲存**]，將報告儲存至報表伺服器。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-172">Select **Save** to save the report to the report server.</span></span> <span data-ttu-id="f4b0e-173">您可以在監控工作區的 [報表] 節點中執行新報告。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-173">You can run the new report in the Reports node in the Monitoring workspace.</span></span> 

<span data-ttu-id="f4b0e-174">**最後，請遵循下列步驟，匯出報表並使用它來註冊裝置**。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-174">**Finally, export the report and use it to register devices** by following these steps.</span></span> <span data-ttu-id="f4b0e-175"> (如果您已在先前的步驟之後流覽過，您只需要遵循本節中的步驟1和2。 ) ：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-175">(You should only need to follow Steps 1 and 2 of this section if you have navigated away after the previous steps.):</span></span>

1. <span data-ttu-id="f4b0e-176">在 Configuration Manager 主控台中，選取 [**監視**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-176">In the Configuration Manager console, select **Monitoring**.</span></span>
2. <span data-ttu-id="f4b0e-177">在 [**監視**] 中，展開 [**報告**]，然後選取 [**報告**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-177">In **Monitoring**, expand **Reporting**, and then select **Reports**.</span></span>
3. <span data-ttu-id="f4b0e-178">使用您先前建立的名稱尋找報表。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-178">Find the report using the name you created earlier.</span></span>
4. <span data-ttu-id="f4b0e-179">以滑鼠右鍵按一下此報告，然後選取 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-179">Right-click this report, and select **Run**.</span></span>
5. <span data-ttu-id="f4b0e-180">在開啟的對話方塊中，選取 [**匯出**]，然後選取 [**另存為 CSV**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-180">In the dialog that opens, select **Export** and then select **Save as CSV**.</span></span>
6. <span data-ttu-id="f4b0e-181">這個報告版本會從 Configuration Manager 通訊的所有 Windows 10 裝置提取雜湊。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-181">This version of report extracts hashes from all Windows 10 devices that Configuration Manager communicates with.</span></span> <span data-ttu-id="f4b0e-182">您將需要篩選結果，只顯示您計畫要向 Microsoft Managed Desktop 註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-182">You will need to filter results to just those devices you plan to register with Microsoft Managed Desktop.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="f4b0e-183">Configuration Manager 中的查詢不允許匯出的欄名稱中包含空格;這就是步驟您可以輸入 "Serial_Number" 和 "HardwareHash" 的原因。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-183">The query in Configuration Manager doesn’t allow spaces in exported column names; that's why the steps had you enter "Serial_Number" and "HardwareHash."</span></span> <span data-ttu-id="f4b0e-184">現在，您已匯出 CSV 檔案，您必須編輯報告標頭，以讀取如下所示的*序號*和*硬體雜湊*，然後再繼續進行裝置註冊。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-184">Now that you have the exported CSV file, you must edit the report headers to read *Serial Number* and *Hardware Hash* as shown here before you proceed with device registration.</span></span>

<span data-ttu-id="f4b0e-185">現在您可以[使用管理入口網站繼續註冊裝置](#register-devices-by-using-the-admin-portal)。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-185">Now you can proceed to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="f4b0e-186">Active Directory PowerShell script 方法</span><span class="sxs-lookup"><span data-stu-id="f4b0e-186">Active Directory PowerShell script method</span></span>

<span data-ttu-id="f4b0e-187">在 Active Directory 環境中，您可以使用 `Get-MMDRegistrationInfo` PowerShell Cmdlet，以遠端從 Active Directory 群組中的裝置，使用 WinRM 來收集資訊。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-187">In an Active Directory environment, you can use the `Get-MMDRegistrationInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="f4b0e-188">您也可以使用 `Get-AD Computer` Cmdlet，取得目錄中所含特定硬體模型名稱的篩選結果。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-188">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="f4b0e-189">若要這麼做，請先確認這些必要條件，然後繼續執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-189">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="f4b0e-190">已啟用 WinRM。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-190">WinRM is enabled.</span></span>
- <span data-ttu-id="f4b0e-191">您想要註冊的裝置會在網路 (上使用，也就是說，它們並未中斷連線或關閉) 。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-191">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="f4b0e-192">請確定您擁有的網域認證參數具有在裝置上遠端執行的許可權。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-192">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="f4b0e-193">請確定 Windows 防火牆允許存取 WMI。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-193">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="f4b0e-194">若要這麼做，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-194">To do that, follow these steps:</span></span>
    1. <span data-ttu-id="f4b0e-195">開啟 [ **Windows Defender 防火牆**] 控制台，然後選取 [**允許透過 Windows defender 防火牆的應用程式或功能**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-195">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    2. <span data-ttu-id="f4b0e-196">找到**Windows Management Instrumentation (WMI) **在清單中，啟用 [**私人] 和 [公用**]，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-196">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="f4b0e-197">以系統管理權限開啟 PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-197">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="f4b0e-198">請執行下列其中*一個*腳本：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-198">Run *either one* of these scripts:</span></span>
```powershell
Install-script -name Get-MMDRegistrationInfo 
#example one – leverage Get-ADComputer to enumerate devices 
Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname>
```
```powershell 
#example two – target specific devices: 
Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
```
3. <span data-ttu-id="f4b0e-199">存取任何可能具有裝置專案的目錄。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-199">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="f4b0e-200">從*所有*目錄中移除每個裝置的專案，包括 Windows Server Active Directory 網域服務和 Azure Active directory。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-200">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="f4b0e-201">請注意，此移除動作可能需要數小時才能完成處理。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-201">Be aware that this removal could take a few hours to completely process.</span></span>
4. <span data-ttu-id="f4b0e-202">存取管理服務，其中可能有裝置的專案。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-202">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="f4b0e-203">從*所有*管理服務（包括 Microsoft Endpoint Configuration Manager、Microsoft Intune 及 Windows Autopilot）中移除每個裝置的專案。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-203">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="f4b0e-204">請注意，此移除動作可能需要數小時才能完成處理。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-204">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="f4b0e-205">現在您可以繼續[註冊裝置](#register-devices)。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-205">Now you can proceed to [register devices](#register-devices).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="f4b0e-206">手動 PowerShell script 方法</span><span class="sxs-lookup"><span data-stu-id="f4b0e-206">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="f4b0e-207">以系統管理權限開啟 PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-207">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="f4b0e-208">執行 `Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="f4b0e-208">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="f4b0e-209">執行 `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="f4b0e-209">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="f4b0e-210">合併雜湊資料。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-210">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="f4b0e-211">快閃磁碟機方法</span><span class="sxs-lookup"><span data-stu-id="f4b0e-211">Flash drive method</span></span>

1. <span data-ttu-id="f4b0e-212">在您要註冊的裝置以外的裝置上，插入 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-212">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="f4b0e-213">以系統管理權限開啟 PowerShell 提示字元。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-213">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="f4b0e-214">執行 `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="f4b0e-214">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="f4b0e-215">開啟您要註冊的裝置，但*請勿開始設定體驗*。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-215">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="f4b0e-216">如果您不小心開始設定體驗，則必須重設裝置或重新製作其映像。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-216">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="f4b0e-217">插入 USB 磁碟機，然後按 SHIFT + F10。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-217">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="f4b0e-218">以系統管理權限開啟 PowerShell 提示字元，然後執行 `cd <pathToUsb>`。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-218">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="f4b0e-219">執行 `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="f4b0e-219">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="f4b0e-220">執行 `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="f4b0e-220">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="f4b0e-221">移除 USB 磁碟機，然後執行 `shutdown -s -t 0` 以關閉裝置</span><span class="sxs-lookup"><span data-stu-id="f4b0e-221">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="f4b0e-222">合併雜湊資料。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-222">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="f4b0e-223">在您完成註冊前，請勿開啟您所註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-223">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="f4b0e-224">合併雜湊資料</span><span class="sxs-lookup"><span data-stu-id="f4b0e-224">Merge hash data</span></span>

<span data-ttu-id="f4b0e-225">如果您是由手動 PowerShell 或快閃記憶體磁片磁碟機方法收集硬體雜湊資料，您現在必須將 CSV 檔案中的資料組合成單一檔案，才能完成註冊。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-225">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="f4b0e-226">以下是讓註冊變輕鬆的範例 PowerShell 指令碼：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-226">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

<span data-ttu-id="f4b0e-227">將雜湊資料合併到一個 CSV 檔案中，您現在可以繼續[註冊裝置](#register-devices)。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-227">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices).</span></span>

### <a name="register-devices"></a><span data-ttu-id="f4b0e-228">註冊裝置</span><span class="sxs-lookup"><span data-stu-id="f4b0e-228">Register devices</span></span>

<span data-ttu-id="f4b0e-229">CSV 檔案必須採用可供註冊的特定格式。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-229">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="f4b0e-230">如果您在先前步驟中自行收集了資料，檔案應該已經是正確的格式。如果您是向供應商取得檔案，則可能需要調整格式。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-230">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="f4b0e-231">為了方便起見，您可以下載這個 CSV 檔案的[範本](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-231">For your convenience, you can download a [template](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.xlsx) for this CSV file.</span></span>

<span data-ttu-id="f4b0e-232">您的檔案必須包含**完全相同的欄標題**作為範例一 (製造商、型號等)，但您自己的資料適用於其他列。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-232">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="f4b0e-233">如果您使用範本，請在記事本這類的文字編輯工具中開啟範本，然後不妨將列 1 的所有資料維持原狀，只在列 2 以下輸入資料。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-233">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="f4b0e-234">如果您忘記變更任何範例資料，註冊將會失敗。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-234">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="f4b0e-235">使用管理入口網站註冊裝置</span><span class="sxs-lookup"><span data-stu-id="f4b0e-235">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="f4b0e-236">從 Microsoft Managed Desktop [Admin 入口網站](https://aka.ms/mmdportal)的左側流覽窗格中，選取 [**裝置**]。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-236">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="f4b0e-237">選取 [+ 註冊裝置]\*\*\*\*；飛入視窗隨即開啟：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-237">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="f4b0e-238">[![在選取 [註冊裝置] 之後飛入，並列出裝置與已指派使用者、序號、狀態、上次查看日期和年限等欄](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="f4b0e-238">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span></span>


[//]: # (事實並非如此。我們可以移除此注意事項 - 但現在暫且擱置，留待我們有機會討論。)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="f4b0e-240">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-240">Follow these steps:</span></span>

1. <span data-ttu-id="f4b0e-241">在 [檔案上傳]\*\*\*\* 中，提供您先前建立的 CSV 檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-241">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="f4b0e-242">或者，您可以新增 [訂單識別碼]\*\*\*\* 或 [購買識別碼]\*\*\*\*，以便自行追蹤。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-242">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="f4b0e-243">這些值沒有格式需求。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-243">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="f4b0e-244">選取 [註冊裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-244">Select **Register devices**.</span></span> <span data-ttu-id="f4b0e-245">系統會將裝置新增至 [裝置] 刀鋒視窗\*\*\*\* 上標示為 [註冊擱置]\*\*\*\* 的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-245">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="f4b0e-246">註冊通常需要不到 10 分鐘的時間，而註冊成功時，裝置將會顯示為 [使用者就緒]\*\*\*\*，標示其已準備就緒並等待終端使用者開始使用。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-246">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="f4b0e-247">您可以在主要 [Microsoft 受管理的電腦 - 裝置]\*\*\*\* 頁面上監視裝置註冊的進度。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-247">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="f4b0e-248">其回報的可能狀態包括：</span><span class="sxs-lookup"><span data-stu-id="f4b0e-248">Possible states reported there include:</span></span>

| <span data-ttu-id="f4b0e-249">狀態</span><span class="sxs-lookup"><span data-stu-id="f4b0e-249">State</span></span> | <span data-ttu-id="f4b0e-250">描述</span><span class="sxs-lookup"><span data-stu-id="f4b0e-250">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="f4b0e-251">註冊擱置</span><span class="sxs-lookup"><span data-stu-id="f4b0e-251">Registration pending</span></span> | <span data-ttu-id="f4b0e-252">尚未完成註冊。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-252">Registration is not done yet.</span></span> <span data-ttu-id="f4b0e-253">稍後再回頭檢查。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-253">Check back later.</span></span> |
| <span data-ttu-id="f4b0e-254">註冊失敗</span><span class="sxs-lookup"><span data-stu-id="f4b0e-254">Registration failed</span></span> | <span data-ttu-id="f4b0e-255">無法完成註冊。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-255">Registration could not be completed.</span></span> <span data-ttu-id="f4b0e-256">如需詳細資訊，請參閱[針對裝置註冊進行疑難排解](#troubleshooting-device-registration)。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-256">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="f4b0e-257">使用者就緒</span><span class="sxs-lookup"><span data-stu-id="f4b0e-257">Ready for user</span></span> | <span data-ttu-id="f4b0e-258">註冊成功，且裝置現在已準備好交付給使用者。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-258">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="f4b0e-259">Microsoft 受管理的電腦將會逐步引導使用者完成首次設定，因此您不需要再做任何進一步的準備。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-259">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="f4b0e-260">作用中</span><span class="sxs-lookup"><span data-stu-id="f4b0e-260">Active</span></span> | <span data-ttu-id="f4b0e-261">裝置已交付給終端使用者並已向您的租用戶註冊。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-261">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="f4b0e-262">這也表示使用者經常使用該裝置。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-262">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="f4b0e-263">非作用中</span><span class="sxs-lookup"><span data-stu-id="f4b0e-263">Inactive</span></span> | <span data-ttu-id="f4b0e-264">裝置已交付給終端使用者並已向您的租用戶註冊。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-264">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="f4b0e-265">不過，使用者最近尚未使用裝置 (在過去 7 天內)。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-265">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="f4b0e-266">針對裝置註冊進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="f4b0e-266">Troubleshooting device registration</span></span>

| <span data-ttu-id="f4b0e-267">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="f4b0e-267">Error message</span></span> | <span data-ttu-id="f4b0e-268">詳細資料</span><span class="sxs-lookup"><span data-stu-id="f4b0e-268">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="f4b0e-269">找不到裝置</span><span class="sxs-lookup"><span data-stu-id="f4b0e-269">Device not found</span></span> | <span data-ttu-id="f4b0e-270">我們無法註冊這個裝置，因為我們找不到與所提供的製造商、型號或序號相符的裝置。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-270">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="f4b0e-271">請與您的裝置供應商確認這些值。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-271">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="f4b0e-272">硬體雜湊無效</span><span class="sxs-lookup"><span data-stu-id="f4b0e-272">Hardware hash not valid</span></span> | <span data-ttu-id="f4b0e-273">您為這個裝置提供的硬體雜湊格式不正確。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-273">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="f4b0e-274">再次確認硬體雜湊，然後重新提交。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-274">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="f4b0e-275">裝置已經註冊</span><span class="sxs-lookup"><span data-stu-id="f4b0e-275">Device already registered</span></span> | <span data-ttu-id="f4b0e-276">此裝置已經註冊到您的組織。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-276">This device is already registered to your organization.</span></span> <span data-ttu-id="f4b0e-277">無需採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-277">No further action required.</span></span> |
| <span data-ttu-id="f4b0e-278">其他組織所宣告的裝置</span><span class="sxs-lookup"><span data-stu-id="f4b0e-278">Device claimed by another organization</span></span> | <span data-ttu-id="f4b0e-279">此裝置已經由其他組織所宣告。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-279">This device has already been claimed by another organization.</span></span> <span data-ttu-id="f4b0e-280">請洽詢您的裝置供應商。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-280">Check with your device supplier.</span></span> |
| <span data-ttu-id="f4b0e-281">未預期的錯誤</span><span class="sxs-lookup"><span data-stu-id="f4b0e-281">Unexpected error</span></span> | <span data-ttu-id="f4b0e-282">無法自動處理您的要求。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-282">Your request could not be automatically processed.</span></span> <span data-ttu-id="f4b0e-283">連絡客戶支援並提供要求識別碼：<requestId></span><span class="sxs-lookup"><span data-stu-id="f4b0e-283">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="f4b0e-284">檢查映像</span><span class="sxs-lookup"><span data-stu-id="f4b0e-284">Check the image</span></span>

<span data-ttu-id="f4b0e-285">如果您的裝置來自 Microsoft 受管理的電腦合作夥伴供應商，映射應是正確的。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-285">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="f4b0e-286">如果您想要的話，也歡迎您自行套用映像。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-286">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="f4b0e-287">若要開始使用，請連絡您的 Microsoft 代表，他們會將映像的位置及其套用步驟提供給您。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-287">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="f4b0e-288">交付裝置</span><span class="sxs-lookup"><span data-stu-id="f4b0e-288">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4b0e-289">將裝置交給使用者之前，請確認您已取得並套用[適合該使用者的授權](../get-ready/prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-289">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="f4b0e-290">如果已套用所有授權，您可以[讓使用者準備好使用裝置](get-started-devices.md)，然後使用者即可啟動裝置並繼續進行 Windows 設定體驗。</span><span class="sxs-lookup"><span data-stu-id="f4b0e-290">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









