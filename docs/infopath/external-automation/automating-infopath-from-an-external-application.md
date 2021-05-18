---
title: 从外部应用程序自动执行 InfoPath
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4d2248d9-ab20-bcaa-d75b-62876c5e95eb
description: Microsoft InfoPath 通过使用 Application 对象和 XDocuments 集合的方法通过 COM 和脚本编写的代码提供应用程序自动化。
ms.openlocfilehash: 7eccbca34b93aff7909de92eebc04d012d4dd97c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412665"
---
# <a name="automating-infopath-from-an-external-application"></a>从外部应用程序自动执行 InfoPath

Microsoft InfoPath 通过使用 **Application** 对象和 **XDocuments** 集合的方法通过 COM 和脚本编写的代码提供应用程序自动化。 
  
## <a name="overview-of-the-application-and-xdocument-objects"></a>Application 和 XDocument 对象概述

**Application** 对象包含以下用于自动化的方法： 
  
|**方法**|**说明**|
|:-----|:-----|
|**CacheSolution** <br/> |检查缓存中的 ，并在必要时从缓存的发布位置更新表单模板。  <br/> |
|**Quit** <br/> |退出Microsoft Office InfoPath 应用程序。  <br/> |
|**RegisterSolution** <br/> |安装 InfoPath Microsoft Office指定的表单模板。  <br/> |
|**UnregisterSolution** <br/> |卸载 InfoPath Microsoft Office指定的表单模板。  <br/> |
   
**XDocuments** 集合包含以下可用于外部自动化的方法： 
  
|**方法**|**说明**|
|:-----|:-----|
|**Close** 方法  <br/> |关闭 InfoPath Microsoft Office指定的表单。  <br/> |
|**New** 方法  <br/> |新建 InfoPath Microsoft Office表单。  <br/> |
|**NewFromSolution** 方法  <br/> |基于指定的表单Microsoft Office InfoPath 表单创建一表单模板。  <br/> |
|**NewFromSolutionWithData** 方法  <br/> |使用指定的 XML Microsoft Office创建一个新的 InfoPath 表单模板。  <br/> |
|**Open** 方法  <br/> |打开 InfoPath Microsoft Office指定的表单。  <br/> |
   
若要使用外部应用程序中的 **Application** 对象，请使用 **CreateObject** 函数和 InfoPath 应用程序 ("InfoPath.Application") 的 ProgID 来创建一个代表 InfoPath 应用程序的对象变量。 然后，可以使用 **XDocuments** 属性访问 **XDocuments** 集合并使用其方法打开或创建 InfoPath 表单。 以下示例演示了使用 Microsoft Visual Basic 6.0 或 Visual Basic for Applications (VBA 创建对 **Application**) 的引用： 
  
```vb
Dim objIP As Object 
 
Set objIP = CreateObject("InfoPath.Application") 
 
' Open an existing form 
objIP.XDocuments.Open ("C:\MyFolder\MyForm.xml") 
 
' Create a new form based on a form template 
objIP.XDocuments.NewFromSolution ("C:\MyFolder\MyForm.xsn") 

```

> [!NOTE]
> 由于 **CreateObject** 函数使用晚期绑定创建对象变量，因此自动语句完成功能在编辑器中Visual Basic可用。 有关正确的调用语法的信息，请参阅前面表格中的链接。 
  

