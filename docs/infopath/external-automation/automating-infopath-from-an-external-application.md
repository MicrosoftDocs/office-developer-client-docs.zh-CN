---
title: 从外部应用程序自动执行 InfoPath
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4d2248d9-ab20-bcaa-d75b-62876c5e95eb
description: Microsoft InfoPath 通过使用 application 对象和 XDocuments 集合的方法, 从使用 COM 和脚本编写的代码中提供应用程序自动化。
ms.openlocfilehash: 7eccbca34b93aff7909de92eebc04d012d4dd97c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412665"
---
# <a name="automating-infopath-from-an-external-application"></a>从外部应用程序自动执行 InfoPath

Microsoft InfoPath 通过使用**application**对象和**XDocuments**集合的方法, 从使用 COM 和脚本编写的代码中提供应用程序自动化。 
  
## <a name="overview-of-the-application-and-xdocument-objects"></a>Application 和 XDocument 对象概述

**Application**对象包含用于自动化的以下方法: 
  
|**方法**|**说明**|
|:-----|:-----|
|**CacheSolution** <br/> |检查缓存中的, 如有必要, 从表单模板的发布位置更新它。  <br/> |
|**Quit** <br/> |退出 Microsoft Office InfoPath 应用程序。  <br/> |
|**RegisterSolution** <br/> |安装指定的 Microsoft Office InfoPath 表单模板。  <br/> |
|**UnregisterSolution** <br/> |卸载指定的 Microsoft Office InfoPath 表单模板。  <br/> |
   
**XDocuments**集合包含可用于外部自动化的以下方法: 
  
|**方法**|**说明**|
|:-----|:-----|
|**Close** 方法  <br/> |关闭指定的 Microsoft Office InfoPath 表单。  <br/> |
|**New** 方法  <br/> |创建一个新的 Microsoft Office InfoPath 表单。  <br/> |
|**NewFromSolution** 方法  <br/> |基于指定的表单模板创建新的 Microsoft Office InfoPath 表单。  <br/> |
|**NewFromSolutionWithData** 方法  <br/> |使用指定的 XML 数据和表单模板创建新的 Microsoft Office InfoPath 表单。  <br/> |
|**Open** 方法  <br/> |打开指定的 Microsoft Office InfoPath 表单。  <br/> |
   
若要从外部应用程序使用**application**对象, 请将**CreateObject**函数与 InfoPath 应用程序的 ProgID ("InfoPath. 应用程序") 结合使用, 以创建代表 InfoPath 应用程序的对象变量。 然后, 可以使用**XDocuments**属性访问**XDocuments**集合并使用其方法打开或创建 InfoPath 表单。 下面的示例演示如何使用 Microsoft Visual basic 6.0 或 Visual basic for Applications (VBA) 编程语言创建对**Application**对象的引用: 
  
```vb
Dim objIP As Object 
 
Set objIP = CreateObject("InfoPath.Application") 
 
' Open an existing form 
objIP.XDocuments.Open ("C:\MyFolder\MyForm.xml") 
 
' Create a new form based on a form template 
objIP.XDocuments.NewFromSolution ("C:\MyFolder\MyForm.xsn") 

```

> [!NOTE]
> 由于**CreateObject**函数使用后期绑定创建对象变量, 因此在 Visual Basic 编辑器中, 自动语句完成将不可用。 有关正确的调用语法的信息, 请参阅上表中的链接。 
  

