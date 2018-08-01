---
title: 在 Office Online Server Preview 中配置 Excel Online 中的 UDF
manager: soliver
ms.date: 03/18/2016
ms.audience: ITPro
localization_priority: Normal
ms.assetid: 3e0ca274-e9cd-48a1-8cfc-9d5053738972
description: 在 Office Online Server Preview Excel Online 中使用用户定义函数 (Udf) 调用自定义函数。
ms.openlocfilehash: ae2d668ebd4a4df278a5c19e702de248b1749b84
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773628"
---
# <a name="configure-udfs-in-excel-online-in-office-online-server-preview"></a><span data-ttu-id="a3520-103">在 Office Online Server Preview 中配置 Excel Online 中的 UDF</span><span class="sxs-lookup"><span data-stu-id="a3520-103">Configure UDFs in Excel Online in Office Online Server Preview</span></span>

<span data-ttu-id="a3520-104">[本主题是预发行文档，可能会在将来版本中的更改。]在 Office Online Server Preview Excel Online 中使用用户定义函数 (Udf) 调用自定义函数。</span><span class="sxs-lookup"><span data-stu-id="a3520-104">[This topic is pre-release documentation and is subject to change in future releases.] Use user-defined functions (UDFs) in Excel Online in Office Online Server Preview to call custom functions.</span></span> 
  
<span data-ttu-id="a3520-p101">Excel Online 中的用户自定义函数 (UDF) 允许您使用单元格中的公式调用以托管代码编写的自定义函数。您可以使用 UDF 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a3520-p101">User-defined functions (UDFs) in Excel Online enable you to call custom functions written in managed code by using formulas in cells. You can use UDFs to:</span></span>
  
- <span data-ttu-id="a3520-107">调用自定义数学函数。</span><span class="sxs-lookup"><span data-stu-id="a3520-107">Call custom mathematical functions.</span></span>
    
- <span data-ttu-id="a3520-108">从自定义数据源获取数据并插入到工作表中。</span><span class="sxs-lookup"><span data-stu-id="a3520-108">Get data from custom data sources into worksheets.</span></span>
    
- <span data-ttu-id="a3520-109">调用 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="a3520-109">Call web services.</span></span>
    
<span data-ttu-id="a3520-110">您可以在以下两个位置之一安装 UDF 二进制文件：</span><span class="sxs-lookup"><span data-stu-id="a3520-110">You can install UDF binaries in one of two locations:</span></span>
  
- <span data-ttu-id="a3520-p102">本地目录。例如：</span><span class="sxs-lookup"><span data-stu-id="a3520-p102">A local directory. For example:</span></span> 
    
    <span data-ttu-id="a3520-113">C:\UDFs\MySampleUdf.dll</span><span class="sxs-lookup"><span data-stu-id="a3520-113">C:\UDFs\MySampleUdf.dll</span></span>
    
- <span data-ttu-id="a3520-p103">全局程序集缓存。例如：</span><span class="sxs-lookup"><span data-stu-id="a3520-p103">The global assembly cache. For example:</span></span> 
    
    <span data-ttu-id="a3520-116">CompanyName.Hierarchichal.MyUdfNamespace.MyUdfClassName.dll, Version=1.1.0.0, Culture=en, PublicKeyToken=e8123117d7ba9ae38</span><span class="sxs-lookup"><span data-stu-id="a3520-116">CompanyName.Hierarchichal.MyUdfNamespace.MyUdfClassName.dll, Version=1.1.0.0, Culture=en, PublicKeyToken=e8123117d7ba9ae38</span></span>
    
<span data-ttu-id="a3520-117">Office Online Server Preview 上创建一个**新建 OfficeWebAppsExcelUserDefinedFunction**定义时，可引用的位置。</span><span class="sxs-lookup"><span data-stu-id="a3520-117">Reference the location when you create a **New-OfficeWebAppsExcelUserDefinedFunction** definition on the Office Online Server Preview.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a3520-118">Office Online Server Preview 不支持位于网络共享上的 Udf。</span><span class="sxs-lookup"><span data-stu-id="a3520-118">Office Online Server Preview does not support UDFs located on network shares.</span></span> 
  
## <a name="enable-udfs-on-office-online-server-preview"></a><span data-ttu-id="a3520-119">启用在 Office Online Server Preview 的 Udf</span><span class="sxs-lookup"><span data-stu-id="a3520-119">Enable UDFs on Office Online Server Preview</span></span>

<span data-ttu-id="a3520-120">当管理员使用[New-officewebappsfarm](https://technet.microsoft.com/en-us/library/jj219436.aspx) Windows PowerShell cmdlet 创建新的 Office Web Apps Server 服务器场时，默认情况下禁用 UDF 程序集。</span><span class="sxs-lookup"><span data-stu-id="a3520-120">When an adminstrator creates a new Office Web Apps Server farm by using the [New-OfficeWebAppsFarm](https://technet.microsoft.com/en-us/library/jj219436.aspx) Windows PowerShell cmdlet, UDF assemblies are disabled by default.</span></span> <span data-ttu-id="a3520-121">**ExcelUdfsAllowed**标志的默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="a3520-121">The default value of the **ExcelUdfsAllowed** flag is false.</span></span> 
  
<span data-ttu-id="a3520-122">若要启用 Udf，请在 Office Online Server Preview 上, 运行以下 Windows PowerShell 命令创建 Office Web Apps Server 服务器场之后。</span><span class="sxs-lookup"><span data-stu-id="a3520-122">To enable UDFs, run the following Windows PowerShell command on the Office Online Server Preview, after the Office Web Apps Server farm has been created.</span></span>
  
`Set-OfficeWebAppsFarm - ExcelUdfsAllowed:$true`
  
## <a name="create-udf-definitions-on-office-online-server-preview"></a><span data-ttu-id="a3520-123">在 Office Online Server Preview 上创建 UDF 定义</span><span class="sxs-lookup"><span data-stu-id="a3520-123">Create UDF definitions on Office Online Server Preview</span></span>

<span data-ttu-id="a3520-124">启用 Udf 后，您需要创建包含 Udf 的二进制文件的定义。</span><span class="sxs-lookup"><span data-stu-id="a3520-124">After you enable UDFs, you need to create a definition for the binary that contains the UDFs.</span></span> <span data-ttu-id="a3520-125">若要创建的 UDF 定义二进制 Office Online Server Preview 上，使用**新建 OfficeWebAppsExcelUserDefinedFunction** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a3520-125">To create a definition for your UDF binary on the Office Online Server Preview, use the **New-OfficeWebAppsExcelUserDefinedFunction** cmdlet.</span></span> <span data-ttu-id="a3520-126">此 cmdlet 包括以下参数：</span><span class="sxs-lookup"><span data-stu-id="a3520-126">This cmdlet includes the following parameters:</span></span> 
  
- <span data-ttu-id="a3520-127">**程序集**</span><span class="sxs-lookup"><span data-stu-id="a3520-127">**Assembly**</span></span>
    
- <span data-ttu-id="a3520-128">**程序集位置**</span><span class="sxs-lookup"><span data-stu-id="a3520-128">**AssemblyLocation**</span></span>
    
- <span data-ttu-id="a3520-129">**Enable**（默认设置为 False）</span><span class="sxs-lookup"><span data-stu-id="a3520-129">**Enable** (set to False by default)</span></span> 
    
- <span data-ttu-id="a3520-130">**说明**</span><span class="sxs-lookup"><span data-stu-id="a3520-130">**Description**</span></span>
    
<span data-ttu-id="a3520-131">下列示例说明了如何创建 UDF 定义。</span><span class="sxs-lookup"><span data-stu-id="a3520-131">The following examples show how create the UDF definitions.</span></span>
  
`New-OfficeWebAppsExcelUserDefinedFunction -Assembly c:\myudf.dll -AssemblyLocation LocalFile -Enable:$true -Description "My Server UDFs"`
  
`New-OfficeWebAppsExcelUserDefinedFunction -Assembly "CompanyName.Hierarchichal.MyUdfNamespace.MyUdfClassName.dll, Version=1.1.0.0, Culture=en, PublicKeyToken=e8123117d7ba9ae38" -AssemblyLocation GAC -Enable:$true -Description "My GAC Server UDFs"`
  
<span data-ttu-id="a3520-132">创建新的 UDF 引用之后，在服务器上运行 **iisreset** 以立即继续引用。</span><span class="sxs-lookup"><span data-stu-id="a3520-132">After you create the new UDF reference, run **iisreset** on the server to pick up the reference immediately.</span></span> 
  
## <a name="additional-office-online-server-preview-udf-windows-powershell-commands"></a><span data-ttu-id="a3520-133">其他 Office Online Server 预览 UDF Windows PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="a3520-133">Additional Office Online Server Preview UDF Windows PowerShell commands</span></span>

<span data-ttu-id="a3520-134">使用以下 Windows PowerShell cmdlet 来处理 Udf:</span><span class="sxs-lookup"><span data-stu-id="a3520-134">Use the following Windows PowerShell cmdlets to work with UDFs:</span></span>
  
- <span data-ttu-id="a3520-135">**Get OfficeWebAppsExcelUserDefinedFunction**（无需的参数）-返回 Office Online Server Preview 配置的 UDF 定义的列表。</span><span class="sxs-lookup"><span data-stu-id="a3520-135">**Get-OfficeWebAppsExcelUserDefinedFunction** (no required parameters) - Returns a list of UDF definitions that are configured on the Office Online Server Preview.</span></span> 
    
- <span data-ttu-id="a3520-136">**Set- OfficeWebAppsExcelUserDefinedFunction**（需要标识参数）- 设置现有 UDF 定义的属性。</span><span class="sxs-lookup"><span data-stu-id="a3520-136">**Set- OfficeWebAppsExcelUserDefinedFunction** (Identity parameter required) - Sets properties on existing UDF definitions.</span></span> 
    
- <span data-ttu-id="a3520-137">**Remove-OfficeWebAppsExcelUserDefinedFunction**（需要标识参数）- 删除现有 UDF 定义。</span><span class="sxs-lookup"><span data-stu-id="a3520-137">**Remove-OfficeWebAppsExcelUserDefinedFunction** (Identity parameter required) - Removes existing UDF definitions.</span></span> 
    
## <a name="udf-sample"></a><span data-ttu-id="a3520-138">UDF 示例</span><span class="sxs-lookup"><span data-stu-id="a3520-138">UDF sample</span></span>

<span data-ttu-id="a3520-139">以下文件提供使用 UDF 和 UDF 二进制的示例工作簿：</span><span class="sxs-lookup"><span data-stu-id="a3520-139">The following files provide a sample workbook that uses a UDF and the UDF binary:</span></span>
  
- <span data-ttu-id="a3520-140">[BooleanDataType.xlsx](http://download.microsoft.com/download/6/7/F/67F724FD-1186-4209-BFF1-FBFD99E959D9/User%20Defined%20Function%20Assemblies/BooleanDataType.xlsx) -使用 UDF 的示例工作簿</span><span class="sxs-lookup"><span data-stu-id="a3520-140">[BooleanDataType.xlsx](http://download.microsoft.com/download/6/7/F/67F724FD-1186-4209-BFF1-FBFD99E959D9/User%20Defined%20Function%20Assemblies/BooleanDataType.xlsx) -- a sample workbook that uses a UDF</span></span>  
- <span data-ttu-id="a3520-141">[EcsUdfsCommonSet.dll](http://download.microsoft.com/download/6/7/F/67F724FD-1186-4209-BFF1-FBFD99E959D9/User%20Defined%20Function%20Assemblies/EcsUdfsCommonSet.dll) -UDF 二进制文件</span><span class="sxs-lookup"><span data-stu-id="a3520-141">[EcsUdfsCommonSet.dll](http://download.microsoft.com/download/6/7/F/67F724FD-1186-4209-BFF1-FBFD99E959D9/User%20Defined%20Function%20Assemblies/EcsUdfsCommonSet.dll) -- the UDF binary</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="a3520-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3520-142">See also</span></span>

- [<span data-ttu-id="a3520-143">配置 Excel Online 管理设置</span><span class="sxs-lookup"><span data-stu-id="a3520-143">Configure Excel Online administrative settings</span></span>](https://technet.microsoft.com/en-us/library/jj219698%28v=office.16%29.aspx)  
- [<span data-ttu-id="a3520-144">Office Online Server Preview</span><span class="sxs-lookup"><span data-stu-id="a3520-144">Office Online Server Preview</span></span>](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)
    

