---
title: xlfCaller
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlfCaller
keywords:
- xlfcaller 函数 [excel 2007]
localization_priority: Normal
ms.assetid: de4b119c-ae2e-4207-9783-8d5692a4d052
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: fb788375504cefab75fde9513147c1d54acdaa07
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405728"
---
# <a name="xlfcaller"></a>xlfCaller

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
返回有关单元格、单元格区域、菜单上的命令、工具栏上的工具或调用了当前正在运行的 DLL 命令或函数的对象的信息。
  
|**调用的代码**|**返回**|
|:-----|:-----|
|DLL  <br/> |注册 ID。  <br/> |
|单个单元格  <br/> |单个单元格引用。  <br/> |
|多单元格数组公式  <br/> |多单元格引用。  <br/> |
|条件格式表达式  <br/> |对应用了格式设置条件的单元格的引用。  <br/> |
|一个菜单  <br/> | 四元素单行数组:  <br/>  条形图 ID。  <br/>  菜单位置。  <br/>  子菜单位置。  <br/>  命令位置。  <br/> |
|一个工具栏  <br/> | 一个双元素单行数组:  <br/>  内置工具栏或自定义工具栏的工具栏名称的工具栏编号。  <br/>  工具栏上的位置。  <br/> |
|一个图形对象  <br/> |对象标识符 (对象名称)。  <br/> |
|与 xlcOnEnter 相关联的命令。ENTER、事件陷阱  <br/> |对所输入的一个或多个单元格的引用。  <br/> |
|与 xlcOnDoubleclick 相关联的命令。DOUBLECLICK, 事件陷阱。  <br/> |双击的单元格 (不一定是活动单元格)。  <br/> |
|Auto_Open、AutoClose、Auto_Activate 或 Auto_Deactivate 宏  <br/> |调用工作表的名称。  <br/> |
|未列出的其他方法  <br/> |#REF! 错误。  <br/> |
   
```cs
Excel12(xlfCaller, (LPXLOPER12) pxRes,0);
```

## <a name="property-valuereturn-value"></a>属性值/返回值

返回值是以下**XLOPER**/ **XLOPER12**数据类型之一: **xltypeRef**、 **xltypeSRef**、 **xltypeNum**、 **xltypeStr**、 **xltypeErr**或**xltypeMulti**。 由于其中三个类型都指向分配的内存, 因此**xlfCaller**的返回值应始终在对[xlFree 函数](xlfree.md)的调用中释放, 如果不再需要它。 
  
有关**XLOPERs**/ **XLOPER12s**的详细信息, 请参阅[Excel 中的内存管理](memory-management-in-excel.md)。
  
## <a name="remarks"></a>说明

此函数是唯一可从 DLL/XLL 工作表函数调用的非工作表函数。 其他 XLM 信息函数只能从命令或宏工作表等效函数中调用。
  
## <a name="example"></a>示例

 `\SAMPLES\EXAMPLE\EXAMPLE.C`. 此函数调用命令宏 (xlcSelect), 并且只有在从宏表中调用时才能正常工作。
  
```cs
short WINAPI CallerExample(void)
{
   XLOPER12 xRes;
   Excel12(xlfCaller, &xRes, 0);
   Excel12(xlcSelect, 0, 1, (LPXLOPER12)&xRes);
   Excel12(xlFree, 0, 1, (LPXLOPER12)&xRes);
   return 1;
}
```

## <a name="see-also"></a>另请参阅



[实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

