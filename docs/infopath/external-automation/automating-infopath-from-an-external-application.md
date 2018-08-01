---
title: 从外部应用程序自动执行 InfoPath
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4d2248d9-ab20-bcaa-d75b-62876c5e95eb
description: Microsoft InfoPath 提供应用程序中使用的应用程序对象和 XDocuments 集合的方法使用 COM 和脚本编写的代码的自动化。
ms.openlocfilehash: 0e3fcc50ec11f5fc8791d37144767bf0398ccda7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773872"
---
# <a name="automating-infopath-from-an-external-application"></a>从外部应用程序自动执行 InfoPath

Microsoft InfoPath 提供应用程序中使用的**应用程序**对象和**XDocuments**集合的方法使用 COM 和脚本编写的代码的自动化。 
  
## <a name="overview-of-the-application-and-xdocument-objects"></a>应用程序和 XDocument 对象概述

**Application**对象包含用于自动化的以下方法： 
  
|**方法**|**说明**|
|:-----|:-----|
|**CacheSolution** <br/> |检查缓存中，如果需要，从表单模板的发布位置更新它。  <br/> |
|**Quit** <br/> |退出 Microsoft Office InfoPath 应用程序。  <br/> |
|**RegisterSolution** <br/> |安装指定的 Microsoft Office InfoPath 表单模板。  <br/> |
|**UnregisterSolution** <br/> |卸载指定的 Microsoft Office InfoPath 表单模板。  <br/> |
   
**XDocuments**集合包含可用于外部自动化的以下方法： 
  
|**方法**|**说明**|
|:-----|:-----|
|**Close** 方法  <br/> |关闭指定的 Microsoft Office InfoPath 表单。  <br/> |
|**New** 方法  <br/> |创建新的 Microsoft Office InfoPath 表单。  <br/> |
|**NewFromSolution** 方法  <br/> |创建基于指定的表单模板的新的 Microsoft Office InfoPath 表单。  <br/> |
|**NewFromSolutionWithData** 方法  <br/> |创建新的 Microsoft Office InfoPath 表单使用指定的 XML 数据和表单模板。  <br/> |
|**Open** 方法  <br/> |打开指定的 Microsoft Office InfoPath 表单。  <br/> |
   
若要使用的外部应用程序的**应用程序**对象，您使用**CreateObject**函数的 ProgID 的 InfoPath 应用程序 ("InfoPath.Application") 创建一个对象变量，代表 InfoPath 应用程序。 然后，您可以使用**XDocuments**属性来访问**XDocuments**集合，并使用其方法打开或创建 InfoPath 表单。 下面的示例演示了如何创建使用 Microsoft Visual Basic 6.0 或 Visual Basic for Applications (VBA) 编程语言的**应用程序**对象的引用： 
  
```vb
Dim objIP As Object 
 
Set objIP = CreateObject("InfoPath.Application") 
 
' Open an existing form 
objIP.XDocuments.Open ("C:\MyFolder\MyForm.xml") 
 
' Create a new form based on a form template 
objIP.XDocuments.NewFromSolution ("C:\MyFolder\MyForm.xsn") 

```

> [!NOTE]
> 由于**CreateObject**函数创建对象变量使用后期绑定，自动语句完成将不可用 Visual Basic 编辑器中。 请参阅有关正确的调用语法前面的表中的链接。 
  

