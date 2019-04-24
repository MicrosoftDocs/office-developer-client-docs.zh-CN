---
title: 在 Office online Server 中的 Excel online 中配置 udf
manager: soliver
ms.date: 03/18/2016
ms.audience: ITPro
localization_priority: Normal
ms.assetid: 3e0ca274-e9cd-48a1-8cfc-9d5053738972
description: 在 Office online Server 中使用 Excel online 中的用户定义函数 (udf) 调用自定义函数。
ms.openlocfilehash: dbba60a62a1a4783b47c3f1fe40a118dd8ed0d6d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311058"
---
# <a name="configure-udfs-in-excel-online-in-office-online-server"></a>在 Office online Server 中的 Excel online 中配置 udf

在 Office online Server 中使用 Excel online 中的用户定义函数 (udf) 调用自定义函数。 
  
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
> Office Online Server 不支持位于网络共享上的 udf。 
  
## <a name="enable-udfs-on-office-online-server"></a>在 Office Online Server 上启用 udf 

当管理员使用[new-officewebappsfarm](https://technet.microsoft.com/en-us/library/jj219436.aspx) Windows PowerShell cmdlet 创建新的 Office Web Apps Server 场时, 默认情况下会禁用 UDF 程序集。 **ExcelUdfsAllowed** 标记的默认值为 false。 
  
若要启用 udf, 请在创建 office Web Apps server 服务器场后, 在 office Online Server 上运行以下 Windows PowerShell 命令。
  
`Set-OfficeWebAppsFarm - ExcelUdfsAllowed:$true`
  
## <a name="create-udf-definitions-on-office-online-server"></a>在 Office Online Server 上创建 UDF 定义

启用 UDF 之后，您需要为包含 UDF 的二进制文件创建一个定义。 若要在 Office Online Server 上为 UDF 二进制文件创建定义, 请使用**OfficeWebAppsExcelUserDefinedFunction** cmdlet。 此 cmdlet 包括下列参数： 
  
- **程序集**
    
- **AssemblyLocation**
    
- **Enable**（默认设置为 False） 
    
- **Description**
    
下列示例说明了如何创建 UDF 定义。
  
`New-OfficeWebAppsExcelUserDefinedFunction -Assembly c:\myudf.dll -AssemblyLocation LocalFile -Enable:$true -Description "My Server UDFs"`
  
`New-OfficeWebAppsExcelUserDefinedFunction -Assembly "CompanyName.Hierarchichal.MyUdfNamespace.MyUdfClassName.dll, Version=1.1.0.0, Culture=en, PublicKeyToken=e8123117d7ba9ae38" -AssemblyLocation GAC -Enable:$true -Description "My GAC Server UDFs"`
  
创建新的 UDF 引用之后，在服务器上运行 **iisreset** 以立即继续引用。 
  
## <a name="additional-office-online-server-udf-windows-powershell-commands"></a>其他 Office Online Server UDF Windows PowerShell 命令

使用以下 Windows PowerShell cmdlet 来处理 udf:
  
- **OfficeWebAppsExcelUserDefinedFunction**(无必需参数)-返回在 Office Online Server 上配置的 UDF 定义的列表。 
    
- **Set- OfficeWebAppsExcelUserDefinedFunction**（需要标识参数）- 设置现有 UDF 定义的属性。 
    
- **Remove-OfficeWebAppsExcelUserDefinedFunction**（需要标识参数）- 删除现有 UDF 定义。 
    
## <a name="udf-sample"></a>UDF 示例

以下文件提供使用 UDF 和 UDF 二进制的示例工作簿：
  
- [BooleanDataType](https://download.microsoft.com/download/6/7/F/67F724FD-1186-4209-BFF1-FBFD99E959D9/User%20Defined%20Function%20Assemblies/BooleanDataType.xlsx): 使用 UDF 的示例工作簿  
- [EcsUdfsCommonSet](https://www.microsoft.com/en-us/search/result.aspx?q=EcsUdfsCommonSet.dll): UDF 二进制 
    
## <a name="see-also"></a>另请参阅

- [配置 Excel Online 管理设置](https://docs.microsoft.com/officeonlineserver/configure-excel-online-administrative-settings)  
- [Office Online Server](https://docs.microsoft.com/officeonlineserver/office-online-server)
    

