---
<span data-ttu-id="d207d-101">标题： Access 启动 TOCTitle 时隐藏功能区： Access 启动时隐藏功能区 <<<<<<< 标头 ms:assetid: f98bab58-8094-1c56-f70b-ced2e7849574 ms:mtpsurl: https://msdn.microsoft.com/library/Ff837012(v=office.15) ms:contentKeyID: 48548817 ms.date: 09/18/2015年 ===说明： 如何将加载自定义功能区隐藏所有 Access 2013 中的内置选项卡。</span><span class="sxs-lookup"><span data-stu-id="d207d-101">title: Hide the ribbon when Access starts TOCTitle: Hide the ribbon when Access starts <<<<<<< HEAD ms:assetid: f98bab58-8094-1c56-f70b-ced2e7849574 ms:mtpsurl: https://msdn.microsoft.com/library/Ff837012(v=office.15) ms:contentKeyID: 48548817 ms.date: 09/18/2015 ======= description: How to load a customized ribbon that hides all of the built-in tabs in Access 2013.</span></span>
<span data-ttu-id="d207d-102">ms:assetid: f98bab58-8094-1c56-f70b-ced2e7849574 ms:mtpsurl: https://msdn.microsoft.com/library/Ff837012(v=office.15) ms:contentKeyID: 48548817 ms.date: 10/16/2018</span><span class="sxs-lookup"><span data-stu-id="d207d-102">ms:assetid: f98bab58-8094-1c56-f70b-ced2e7849574 ms:mtpsurl: https://msdn.microsoft.com/library/Ff837012(v=office.15) ms:contentKeyID: 48548817 ms.date: 10/16/2018</span></span>
>>>>>>> <span data-ttu-id="d207d-103">主 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="d207d-103">master mtps_version: v=office.15</span></span>
---

# <a name="hide-the-ribbon-when-access-starts"></a><span data-ttu-id="d207d-104">在 Access 启动时隐藏功能区</span><span class="sxs-lookup"><span data-stu-id="d207d-104">Hide the ribbon when Access starts</span></span>

<span data-ttu-id="d207d-105">**适用于：** Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="d207d-105">**Applies to:** Access 2013 | Office 2013</span></span>

<span data-ttu-id="d207d-p102">默认情况下，Microsoft Access 不提供用于隐藏功能区的方法。本主题介绍如何加载可隐藏所有的内置选项卡的自定义功能区。</span><span class="sxs-lookup"><span data-stu-id="d207d-p102">By default, Microsoft Access does not provide a method for hiding the ribbon. This topic describes how to load a customized ribbon that hides all of the built-in tabs.</span></span>

<span data-ttu-id="d207d-108">要在 Access 启动时加载自定义的功能区，应将其设置存储在一个名为 **USysRibbons** 的表中。</span><span class="sxs-lookup"><span data-stu-id="d207d-108">To load the customized ribbon when Access starts, you should store its settings in a table named **USysRibbons**.</span></span>

<span data-ttu-id="d207d-109"><<<<<<< 标头，必须使用特定的列名称在功能区自定义项的顺序实现创建**USysRibbons**表。</span><span class="sxs-lookup"><span data-stu-id="d207d-109"><<<<<<< HEAD The **USysRibbons** table must be created using specific column names in order for the ribbon customizations to be implemented.</span></span> <span data-ttu-id="d207d-110">下表列出了创建 **USysRibbons** 表时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="d207d-110">The following table lists the settings to use when creating the **USysRibbons** table.</span></span>
<span data-ttu-id="d207d-111">=== 必须使用功能区自定义项的特定的列名称必须创建**USysRibbons**表。</span><span class="sxs-lookup"><span data-stu-id="d207d-111">======= The **USysRibbons** table must be created using specific column names for the ribbon customizations to be implemented.</span></span> 

<span data-ttu-id="d207d-112">下表列出了创建 **USysRibbons** 表时要使用的设置。</span><span class="sxs-lookup"><span data-stu-id="d207d-112">The following table lists the settings to use when creating the **USysRibbons** table.</span></span>
>>>>>>> <span data-ttu-id="d207d-113">master</span><span class="sxs-lookup"><span data-stu-id="d207d-113">master</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<span data-ttu-id="d207d-114"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="d207d-114"><<<<<<< HEAD</span></span>
<th><p><span data-ttu-id="d207d-115">列名称</span><span class="sxs-lookup"><span data-stu-id="d207d-115">Column Name</span></span></p></th>
<th><p><span data-ttu-id="d207d-116">数据类型</span><span class="sxs-lookup"><span data-stu-id="d207d-116">Data Type</span></span></p></th>
=======
<th><p><span data-ttu-id="d207d-117">列名称</span><span class="sxs-lookup"><span data-stu-id="d207d-117">Column name</span></span></p></th>
<th><p><span data-ttu-id="d207d-118">数据类型</span><span class="sxs-lookup"><span data-stu-id="d207d-118">Data type</span></span></p></th><span data-ttu-id="d207d-119">
>>>>>>>主控形状</span><span class="sxs-lookup"><span data-stu-id="d207d-119">
>>>>>>> master</span></span>
<th><p><span data-ttu-id="d207d-120">说明</span><span class="sxs-lookup"><span data-stu-id="d207d-120">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d207d-121"><strong>RibbonName</strong></span><span class="sxs-lookup"><span data-stu-id="d207d-121"><strong>RibbonName</strong></span></span></p></td>
<td><p><span data-ttu-id="d207d-122">Text</span><span class="sxs-lookup"><span data-stu-id="d207d-122">Text</span></span></p></td>
<td><p><span data-ttu-id="d207d-123">Contains the name of the custom ribbon to be associated with this customization.</span><span class="sxs-lookup"><span data-stu-id="d207d-123">Contains the name of the custom ribbon to be associated with this customization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d207d-124"><strong>RibbonXML</strong></span><span class="sxs-lookup"><span data-stu-id="d207d-124"><strong>RibbonXML</strong></span></span></p></td>
<td><p><span data-ttu-id="d207d-125">Memo</span><span class="sxs-lookup"><span data-stu-id="d207d-125">Memo</span></span></p></td>
<span data-ttu-id="d207d-126"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="d207d-126"><<<<<<< HEAD</span></span>
<td><p><span data-ttu-id="d207d-127">Contains the Ribbon Extensibility XML (RibbonX) that defines the ribbon customization.</span><span class="sxs-lookup"><span data-stu-id="d207d-127">Contains the Ribbon Extensibility XML (RibbonX) that defines the ribbon customization.</span></span></p></td>
=======
<td><p><span data-ttu-id="d207d-128">包含功能区扩展性 XML (RibbonX) 定义功能区自定义项。</span><span class="sxs-lookup"><span data-stu-id="d207d-128">Contains the ribbon extensibility XML (RibbonX) that defines the ribbon customization.</span></span></p></td><span data-ttu-id="d207d-129">
>>>>>>>主控形状</span><span class="sxs-lookup"><span data-stu-id="d207d-129">
>>>>>>> master</span></span>
</tr>
</tbody>
</table>

<span data-ttu-id="d207d-130"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="d207d-130"><<<<<<< HEAD</span></span>

<span data-ttu-id="d207d-131">下表列出了要存储在 **USysRibbons** 表中的功能区自定义设置。</span><span class="sxs-lookup"><span data-stu-id="d207d-131">The following table lists the ribbon customization settings to store in the **USysRibbons** table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d207d-132">列名</span><span class="sxs-lookup"><span data-stu-id="d207d-132">Column Name</span></span></p></th>
<th><p><span data-ttu-id="d207d-133">值</span><span class="sxs-lookup"><span data-stu-id="d207d-133">Value</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d207d-134"><strong>RibbonName</strong></span><span class="sxs-lookup"><span data-stu-id="d207d-134"><strong>RibbonName</strong></span></span></p></td>
<td><p><span data-ttu-id="d207d-135">HideTheRibbon</span><span class="sxs-lookup"><span data-stu-id="d207d-135">HideTheRibbon</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d207d-136"><strong>RibbonXML</strong></span><span class="sxs-lookup"><span data-stu-id="d207d-136"><strong>RibbonXML</strong></span></span></p></td>
<td><p><span data-ttu-id="d207d-137">&lt;CustomUI xmlns =&quot;https://schemas.microsoft.com/office/2006/01/CustomUI&quot;&gt; &lt;功能区 startFromScratch =&quot;true&quot;/&gt;&lt;/CustomUI&gt;</span><span class="sxs-lookup"><span data-stu-id="d207d-137">&lt;CustomUI xmlns=&quot;https://schemas.microsoft.com/office/2006/01/CustomUI&quot;&gt; &lt;ribbon startFromScratch=&quot;true&quot;/&gt;&lt;/CustomUI&gt;</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="applying-a-custom-ribbon-when-access-starts"></a><span data-ttu-id="d207d-138">在 Access 启动时应用自定义功能区</span><span class="sxs-lookup"><span data-stu-id="d207d-138">Applying a Custom Ribbon When Access Starts</span></span>
=======
<br/>

<span data-ttu-id="d207d-139">下表列出了要存储在 **USysRibbons** 表中的功能区自定义设置。</span><span class="sxs-lookup"><span data-stu-id="d207d-139">The following table lists the ribbon customization settings to store in the **USysRibbons** table.</span></span>

|<span data-ttu-id="d207d-140">列名称</span><span class="sxs-lookup"><span data-stu-id="d207d-140">Column name</span></span>|<span data-ttu-id="d207d-141">值</span><span class="sxs-lookup"><span data-stu-id="d207d-141">Value</span></span>|
|:----------|:----|
|<span data-ttu-id="d207d-142">**RibbonName**</span><span class="sxs-lookup"><span data-stu-id="d207d-142">**RibbonName**</span></span>|<span data-ttu-id="d207d-143">HideTheRibbon</span><span class="sxs-lookup"><span data-stu-id="d207d-143">HideTheRibbon</span></span>|
|<span data-ttu-id="d207d-144">**RibbonXML**</span><span class="sxs-lookup"><span data-stu-id="d207d-144">**RibbonXML**</span></span>|`<CustomUI xmlns="https://schemas.microsoft.com/office/2006/01/CustomUI"> <ribbon startFromScratch="true"/></CustomUI>`|


## <a name="apply-a-custom-ribbon-when-access-starts"></a><span data-ttu-id="d207d-145">在 Access 启动时应用自定义功能区</span><span class="sxs-lookup"><span data-stu-id="d207d-145">Apply a custom ribbon when Access starts</span></span>
>>>>>>> <span data-ttu-id="d207d-146">master</span><span class="sxs-lookup"><span data-stu-id="d207d-146">master</span></span>

<span data-ttu-id="d207d-147">若要应用自定义功能区以使它在应用程序启动时可用，请执行以下过程：</span><span class="sxs-lookup"><span data-stu-id="d207d-147">To apply a custom ribbon so that it is available when the application starts, use the following procedure:</span></span>

1.  <span data-ttu-id="d207d-148">按照前面描述的过程使自定义功能区可供应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="d207d-148">Follow the process described previously to make the customized ribbon available to the application.</span></span>

2.  <span data-ttu-id="d207d-149">关闭应用程序，然后重新启动它。</span><span class="sxs-lookup"><span data-stu-id="d207d-149">Close and then restart the application.</span></span>

<span data-ttu-id="d207d-150"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="d207d-150"><<<<<<< HEAD</span></span>
3.  <span data-ttu-id="d207d-151">单击**Microsoft Office 按钮**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") ，然后单击**Access 选项**。</span><span class="sxs-lookup"><span data-stu-id="d207d-151">Click the **Microsoft Office Button**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102") and then click **Access Options**.</span></span>

4.  <span data-ttu-id="d207d-152">单击 **"当前数据库"** 选项，然后在 **"功能区和工具栏选项"** 部分单击 **"功能区名称"** 列表并选择 **"HideTheRibbon"** 。</span><span class="sxs-lookup"><span data-stu-id="d207d-152">Click the **Current Database** option and then, in the **Ribbon and Toolbar Options** section, click the **Ribbon Name** list and select **HideTheRibbon**.</span></span>
=======
3.  <span data-ttu-id="d207d-153">选择**Microsoft Office 按钮**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102")，然后选择**访问选项**。</span><span class="sxs-lookup"><span data-stu-id="d207d-153">Choose the **Microsoft Office Button**![O12FileMenuButton\_ZA10077102](media/access-file-menu-button.gif "O12FileMenuButton_ZA10077102"), and then choose **Access Options**.</span></span>

4.  <span data-ttu-id="d207d-154">选择**当前数据库**选项，且然后，在**功能区和工具栏选项**部分中，选择**功能区名称**列表，然后选择**HideTheRibbon**。</span><span class="sxs-lookup"><span data-stu-id="d207d-154">Choose the **Current Database** option and then, in the **Ribbon and Toolbar Options** section, choose the **Ribbon Name** list and select **HideTheRibbon**.</span></span>
>>>>>>> <span data-ttu-id="d207d-155">master</span><span class="sxs-lookup"><span data-stu-id="d207d-155">master</span></span>

5.  <span data-ttu-id="d207d-156">关闭应用程序，然后重新启动它。</span><span class="sxs-lookup"><span data-stu-id="d207d-156">Close and then restart the application.</span></span>

> [!NOTE]
> <span data-ttu-id="d207d-157">[!注释] For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span><span class="sxs-lookup"><span data-stu-id="d207d-157">For more information about the ribbon UI in other Office applications, see [Overview of the Office Fluent Ribbon](https://docs.microsoft.com/office/vba/Library-Reference/Concepts/overview-of-the-office-fluent-ribbon).</span></span>


