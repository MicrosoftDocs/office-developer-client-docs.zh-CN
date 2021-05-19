---
title: 在 Office Online Server 中配置 Excel Online 中的 UDF
manager: lindalu
ms.date: 12/03/2019
ms.audience: ITPro
localization_priority: Normal
ms.assetid: 3e0ca274-e9cd-48a1-8cfc-9d5053738972
description: 使用用户定义的函数 (UDF) Excel Online Office Online Server调用自定义函数。
ms.openlocfilehash: e1b005079c03ae3028ba6bf9ee1156c6ae2eae80
ms.sourcegitcommit: 007aa2ceb4f569201c3f4372de5c83b6c61f8875
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102931"
---
# <a name="configure-udfs-in-excel-online-in-office-online-server"></a>在 Office Online Server 中配置 Excel Online 中的 UDF

使用用户定义的函数 (UDF) Excel Online Office Online Server调用自定义函数。 
  
Excel Online 中的用户自定义函数 (UDF) 允许您使用单元格中的公式调用以托管代码编写的自定义函数。您可以使用 UDF 执行以下操作：
  
- 调用自定义数学函数。
    
- 从自定义数据源获取数据并插入到工作表中。
    
- 调用 Web 服务。
    
您可以在以下两个位置之一安装 UDF 二进制文件：
  
- 本地目录。例如： 
    
    C:\UDFs\MySampleUdf.dll
    
- 全局程序集缓存。例如： 
    
    CompanyName.Hierarchichal.MyUdfNamespace.MyUdfClassName.dll, Version=1.1.0.0, Culture=en, PublicKeyToken=e8123117d7ba9ae38
    
引用在应用程序上创建 **New-OfficeWebAppsExcelUserDefinedFunction** 定义Office Online Server。 
  
> [!NOTE]
> Office Online Server不支持位于网络共享上的 UDF。 
  
## <a name="enable-udfs-on-office-online-server"></a>启用 UDF Office Online Server 

当管理员使用[New-OfficeWebAppsFarm](https://docs.microsoft.com/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps) Office cmdlet 创建新的 Web Apps Server Windows PowerShell时，UDF 程序集默认处于禁用状态。 **ExcelUdfsAllowed** 标记的默认值为 false。 
  
若要启用 UDF，Windows PowerShell Web Apps Server Office Online Server后，在 Office 运行以下命令。
  
`Set-OfficeWebAppsFarm - ExcelUdfsAllowed:$true`
  
## <a name="create-udf-definitions-on-office-online-server"></a>在项目上创建 UDF Office Online Server

启用 UDF 之后，您需要为包含 UDF 的二进制文件创建一个定义。 若要在应用程序上为 UDF 二进制文件创建Office Online Server，请使用 **New-OfficeWebAppsExcelUserDefinedFunction** cmdlet。 此 cmdlet 包括下列参数： 
  
- **程序集**
    
- **AssemblyLocation**
    
- **Enable**（默认设置为 False） 
    
- **说明**
    
下列示例说明了如何创建 UDF 定义。
  
`New-OfficeWebAppsExcelUserDefinedFunction -Assembly c:\myudf.dll -AssemblyLocation LocalFile -Enable:$true -Description "My Server UDFs"`
  
`New-OfficeWebAppsExcelUserDefinedFunction -Assembly "CompanyName.Hierarchichal.MyUdfNamespace.MyUdfClassName.dll, Version=1.1.0.0, Culture=en, PublicKeyToken=e8123117d7ba9ae38" -AssemblyLocation GAC -Enable:$true -Description "My GAC Server UDFs"`
  
创建新的 UDF 引用之后，在服务器上运行 **iisreset** 以立即继续引用。 
  
## <a name="additional-office-online-server-udf-windows-powershell-commands"></a>其他Office Online Server UDF Windows PowerShell命令

使用以下 cmdlet Windows PowerShell UDF：
  
- **Get-OfficeWebAppsExcelUserDefinedFunction** (没有必需参数) - 返回在 Office Online Server 上配置的 UDF 定义列表。 
    
- **Set- OfficeWebAppsExcelUserDefinedFunction**（需要标识参数）- 设置现有 UDF 定义的属性。 
    
- **Remove-OfficeWebAppsExcelUserDefinedFunction**（需要标识参数）- 删除现有 UDF 定义。 
    
## <a name="udf-sample"></a>UDF 示例

以下示例文件提供使用 UDF 和 UDF 二进制文件的示例工作簿：
  
- [BooleanDataType.xlsx： ](https://download.microsoft.com/download/6/7/F/67F724FD-1186-4209-BFF1-FBFD99E959D9/User%20Defined%20Function%20Assemblies/BooleanDataType.xlsx)使用 UDF 的示例工作簿  
    
## <a name="see-also"></a>另请参阅

- [配置 Excel Online 管理设置](https://docs.microsoft.com/officeonlineserver/configure-excel-online-administrative-settings)  
- [Office Online Server](https://docs.microsoft.com/officeonlineserver/office-online-server)
    

