---
title: HYPERLINK 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251441
localization_priority: Normal
ms.assetid: 943636a6-e135-a626-7924-11e238156548
description: 导航到指定的地址，它可以是文件、UNC 或 URL 路径。
ms.openlocfilehash: 5e4952c3d56eff0cb1e6518928a7b8259f645046
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329944"
---
# <a name="hyperlink-function"></a>HYPERLINK 函数

导航到指定的地址，它可以是文件、UNC 或 URL 路径。
  
## <a name="syntax"></a>语法

HYPERLINK (" ** *address* ** "[，" ** *subaddress* ** "，" ** *extrainfo* ** "， ** *window* **，" ** *frame* ** "])  
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _address_ <br/> |必需  <br/> |**String** <br/> |完整路径或相对路径。  <br/> |
| _subaddress_ <br/> |可选  <br/> |**字符串** <br/> |指定地址中要链接到的位置。例如，如果地址是一个 Microsoft Visio 文件，则子地址可以是一个页名；如果是一个 Microsoft Excel 文件，则子地址可以是一个工作表或工作表内的某个区域；如果是一个 HTML 页的 URL，则子地址可以是一个定位点。  <br/> |
| _extrainfo_ <br/> |可选  <br/> |**字符串** <br/> |传递用于解析 URL 的信息，如图像映射的坐标。  <br/> |
| _window_ <br/> |可选  <br/> |**Boolean** <br/> |指定是否在新窗口中打开超链接。默认值为 FALSE。  <br/> |
| _frame_ <br/> |可选  <br/> |**字符串** <br/> | 指定当 Visio 作为 ActiveX 浏览器（如 Microsoft Internet Explorer 3.0 或更高版本）中的活动文档打开时，它所针对的框架的名称。默认值是一个空字符串。  <br/> |
   
## <a name="remarks"></a>备注

如果文档没有基础路径，则 Visio 将按照文档路径导航。如果文档尚未保存，则超链接为未定义。 
  
相对路径基于 **“Visio 属性”** 对话框中指定的 **“超链接基础”** 域。 
  
您可以使用 GOTOPAGE 函数来导航文档页。 
  
## <a name="example-1"></a>示例 1

 `HYPERLINK("C:\My Documents\Drawing1.vsdx")`
  
## <a name="example-2"></a>示例 2

 `HYPERLINK("\\Server\Share\Drawing1.vsdx")`
  
## <a name="example-3"></a>示例 3

 `HYPERLINK("https://www.microsoft.com")`
  
## <a name="example-4"></a>示例 4

 `HYPERLINK("..\data.xlsx","sheet1!A1")`
  

