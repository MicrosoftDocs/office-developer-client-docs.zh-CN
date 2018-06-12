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
# <a name="configure-udfs-in-excel-online-in-office-online-server-preview"></a>在 Office Online Server Preview 中配置 Excel Online 中的 UDF

[本主题是预发行文档，可能会在将来版本中的更改。]在 Office Online Server Preview Excel Online 中使用用户定义函数 (Udf) 调用自定义函数。 
  
Excel Online 中的用户自定义函数 (UDF) 允许您使用单元格中的公式调用以托管代码编写的自定义函数。您可以使用 UDF 执行以下操作：
  
- 调用自定义数学函数。
    
- 从自定义数据源获取数据并插入到工作表中。
    
- 调用 Web 服务。
    
您可以在以下两个位置之一安装 UDF 二进制文件：
  
- 本地目录。例如： 
    
    C:\UDFs\MySampleUdf.dll
    
- 全局程序集缓存。例如： 
    
    CompanyName.Hierarchichal.MyUdfNamespace.MyUdfClassName.dll, Version=1.1.0.0, Culture=en, PublicKeyToken=e8123117d7ba9ae38
    
Office Online Server Preview 上创建一个**新建 OfficeWebAppsExcelUserDefinedFunction**定义时，可引用的位置。 
  
> [!NOTE]
> Office Online Server Preview 不支持位于网络共享上的 Udf。 
  
## <a name="enable-udfs-on-office-online-server-preview"></a>启用在 Office Online Server Preview 的 Udf

当管理员使用[New-officewebappsfarm](https://technet.microsoft.com/en-us/library/jj219436.aspx) Windows PowerShell cmdlet 创建新的 Office Web Apps Server 服务器场时，默认情况下禁用 UDF 程序集。 **ExcelUdfsAllowed**标志的默认值为 false。 
  
若要启用 Udf，请在 Office Online Server Preview 上, 运行以下 Windows PowerShell 命令创建 Office Web Apps Server 服务器场之后。
  
`Set-OfficeWebAppsFarm - ExcelUdfsAllowed:$true`
  
## <a name="create-udf-definitions-on-office-online-server-preview"></a>在 Office Online Server Preview 上创建 UDF 定义

启用 Udf 后，您需要创建包含 Udf 的二进制文件的定义。 若要创建的 UDF 定义二进制 Office Online Server Preview 上，使用**新建 OfficeWebAppsExcelUserDefinedFunction** cmdlet。 此 cmdlet 包括以下参数： 
  
- **程序集**
    
- **程序集位置**
    
- **启用**（默认设置为 False） 
    
- **说明**
    
下列示例说明了如何创建 UDF 定义。
  
`New-OfficeWebAppsExcelUserDefinedFunction -Assembly c:\myudf.dll -AssemblyLocation LocalFile -Enable:$true -Description "My Server UDFs"`
  
`New-OfficeWebAppsExcelUserDefinedFunction -Assembly "CompanyName.Hierarchichal.MyUdfNamespace.MyUdfClassName.dll, Version=1.1.0.0, Culture=en, PublicKeyToken=e8123117d7ba9ae38" -AssemblyLocation GAC -Enable:$true -Description "My GAC Server UDFs"`
  
创建新的 UDF 引用后，立即拿引用在服务器上运行**iisreset** 。 
  
## <a name="additional-office-online-server-preview-udf-windows-powershell-commands"></a>其他 Office Online Server 预览 UDF Windows PowerShell 命令

使用以下 Windows PowerShell cmdlet 来处理 Udf:
  
- **Get OfficeWebAppsExcelUserDefinedFunction**（无需的参数）-返回 Office Online Server Preview 配置的 UDF 定义的列表。 
    
- **设置 OfficeWebAppsExcelUserDefinedFunction**（identity 参数所需）-设置现有 UDF 定义的属性。 
    
- **删除 OfficeWebAppsExcelUserDefinedFunction**（identity 参数所需）-删除现有的 UDF 定义。 
    
## <a name="udf-sample"></a>UDF 示例

以下文件提供使用 UDF 和 UDF 二进制的示例工作簿：
  
- [BooleanDataType.xlsx](http://download.microsoft.com/download/6/7/F/67F724FD-1186-4209-BFF1-FBFD99E959D9/User%20Defined%20Function%20Assemblies/BooleanDataType.xlsx) -使用 UDF 的示例工作簿  
- [EcsUdfsCommonSet.dll](http://download.microsoft.com/download/6/7/F/67F724FD-1186-4209-BFF1-FBFD99E959D9/User%20Defined%20Function%20Assemblies/EcsUdfsCommonSet.dll) -UDF 二进制文件 
    
## <a name="see-also"></a>另请参阅

- [配置 Excel Online 管理设置](https://technet.microsoft.com/en-us/library/jj219698%28v=office.16%29.aspx)  
- [Office Online Server Preview](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)
    

