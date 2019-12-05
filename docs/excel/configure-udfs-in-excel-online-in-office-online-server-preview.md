---
title: 在 Office Online Server 中的 Excel Online 中配置 Udf
manager: lindalu
ms.date: 12/03/2019
ms.audience: ITPro
localization_priority: Normal
ms.assetid: 3e0ca274-e9cd-48a1-8cfc-9d5053738972
description: 在 Office Online Server 中使用 Excel Online 中的用户定义函数（Udf）调用自定义函数。
ms.openlocfilehash: 6e16ea753090b2fefca4ae15330f1a27d53da777
ms.sourcegitcommit: 37080eb0087261320e24e6f067e5f434a812b2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "39819355"
---
# <a name="configure-udfs-in-excel-online-in-office-online-server"></a>在 Office Online Server 中的 Excel Online 中配置 Udf

在 Office Online Server 中使用 Excel Online 中的用户定义函数（Udf）调用自定义函数。 
  
Excel Online 中的用户自定义函数 (UDF) 允许您使用单元格中的公式调用以托管代码编写的自定义函数。您可以使用 UDF 执行以下操作：
  
- 调用自定义数学函数。
    
- 从自定义数据源获取数据并插入到工作表中。
    
- 调用 Web 服务。
    
您可以在以下两个位置之一安装 UDF 二进制文件：
  
- 本地目录。例如： 
    
    C:\UDFs\MySampleUdf.dll
    
- 全局程序集缓存。例如： 
    
    CompanyName.Hierarchichal.MyUdfNamespace.MyUdfClassName.dll, Version=1.1.0.0, Culture=en, PublicKeyToken=e8123117d7ba9ae38
    
在 Office Online Server 上创建**新的 OfficeWebAppsExcelUserDefinedFunction**定义时引用位置。 
  
> [!NOTE]
> Office Online Server 不支持位于网络共享上的 Udf。 
  
## <a name="enable-udfs-on-office-online-server"></a>在 Office Online Server 上启用 Udf 

当管理员使用[New-officewebappsfarm](https://technet.microsoft.com/en-us/library/jj219436.aspx) Windows PowerShell cmdlet 创建新的 Office Web Apps Server 场时，默认情况下会禁用 UDF 程序集。 **ExcelUdfsAllowed** 标记的默认值为 false。 
  
若要启用 Udf，请在创建 Office Web Apps Server 服务器场后，在 Office Online Server 上运行以下 Windows PowerShell 命令。
  
`Set-OfficeWebAppsFarm - ExcelUdfsAllowed:$true`
  
## <a name="create-udf-definitions-on-office-online-server"></a>在 Office Online Server 上创建 UDF 定义

启用 UDF 之后，您需要为包含 UDF 的二进制文件创建一个定义。 若要在 Office Online Server 上为 UDF 二进制文件创建定义，请使用**OfficeWebAppsExcelUserDefinedFunction** cmdlet。 此 cmdlet 包括下列参数： 
  
- **程序集**
    
- **AssemblyLocation**
    
- **Enable**（默认设置为 False） 
    
- **说明**
    
下列示例说明了如何创建 UDF 定义。
  
`New-OfficeWebAppsExcelUserDefinedFunction -Assembly c:\myudf.dll -AssemblyLocation LocalFile -Enable:$true -Description "My Server UDFs"`
  
`New-OfficeWebAppsExcelUserDefinedFunction -Assembly "CompanyName.Hierarchichal.MyUdfNamespace.MyUdfClassName.dll, Version=1.1.0.0, Culture=en, PublicKeyToken=e8123117d7ba9ae38" -AssemblyLocation GAC -Enable:$true -Description "My GAC Server UDFs"`
  
创建新的 UDF 引用之后，在服务器上运行 **iisreset** 以立即继续引用。 
  
## <a name="additional-office-online-server-udf-windows-powershell-commands"></a>其他 Office Online Server UDF Windows PowerShell 命令

使用以下 Windows PowerShell cmdlet 来处理 Udf：
  
- **OfficeWebAppsExcelUserDefinedFunction** （无必需的参数）-返回在 Office Online Server 上配置的 UDF 定义的列表。 
    
- **Set- OfficeWebAppsExcelUserDefinedFunction**（需要标识参数）- 设置现有 UDF 定义的属性。 
    
- **Remove-OfficeWebAppsExcelUserDefinedFunction**（需要标识参数）- 删除现有 UDF 定义。 
    
## <a name="udf-sample"></a>UDF 示例

下面的示例文件提供了一个使用 UDF 和 UDF 二进制的示例工作簿：
  
- [BooleanDataType](https://download.microsoft.com/download/6/7/F/67F724FD-1186-4209-BFF1-FBFD99E959D9/User%20Defined%20Function%20Assemblies/BooleanDataType.xlsx)：使用 UDF 的示例工作簿  
    
## <a name="see-also"></a>另请参阅

- [配置 Excel Online 管理设置](https://docs.microsoft.com/officeonlineserver/configure-excel-online-administrative-settings)  
- [Office Online Server](https://docs.microsoft.com/officeonlineserver/office-online-serverr)
    

