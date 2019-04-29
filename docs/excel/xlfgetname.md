---
title: xlfGetName
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
keywords:
- xlfgetname
localization_priority: Normal
ms.assetid: 65780435-aaa2-47af-b44f-07be7aa769ee
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: fdee0146ae2199097828e98abb96ffe43a64fc80
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436627"
---
# <a name="xlfgetname"></a>xlfGetName

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
返回名称显示在 "**名称管理器**" 对话框 (在 "**公式**" 选项卡上 "**定义的名称**" 部分中单击 "**名称管理器**" 时显示) 中的 "**引用**" 列中显示的名称定义。如果定义中包含引用, 则将它们作为 R1C1 样式的引用提供。 使用**xlfGetName**检查名称定义的值。 若要获取与定义对应的名称, 请使用[xlfGetDef](xlfgetdef.md)。
  
```cpp
Excel12(xlfGetName, LPXLOPER12 pxRes, 2, LPXLOPER12 pxNameText, LPXLOPER12 pxInfoType);
```

## <a name="parameters"></a>参数

_pxNameText_(**xltypeStr**)
  
可以是在工作表上定义的名称;对在活动工作簿上定义的名称的外部引用, 例如`"!Sales"`;或对在特定打开的工作簿上定义的名称的外部引用, 例如`"[Book1]SHEET1!Sales"`。  _pxNameText_也可以是一个隐藏的名称。 
  
_pxInfoType_(**xltypeBool**)
  
指定要返回的有关名称的信息类型。 如果**为 FALSE**或省略, 则返回定义。 如果**为 true**, 则如果只为工作表定义名称, 则返回**true** ; 如果为整个工作簿定义了名称, 则返回**FALSE** 。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

_pxRes_(**xltypeStr**、 **xltypeBool**或**xltypeErr**)
  
根据为_pxInfoType_传递的值, 返回指定名称 (**xltypeStr**) 的定义, 或者**TRUE**或**FALSE** (**xltypeBool**)。
  
## <a name="remarks"></a>说明

如果已在 "**保护工作表**" 对话框中选中 "**保护工作表和锁定的单元格内容**" 复选框, 以保护包含该名称的`#N/A`工作簿, 则**xlfGetName**将返回错误值。 若要查看**保护工作表**对话框, 请单击 "**审阅**" 选项卡的 "**更改**" 部分中的 "**保护工作表**"。 
  
下表列出了使用指定的_pxNameText_参数调用**xlfGetDef**时返回的值的三个示例。 
  
|**Excel 中的定义**|**_pxNameText_**|**返回的值**|
|:-----|:-----|:-----|
|工作表上的名称 Sales 定义为数字523。  <br/> |销售  <br/> |"= 523"  <br/> |
|活动工作表上的名称利润定义为公式 = Sales-成本。  <br/> |"!盈利  <br/> |"= 销售-成本"  <br/> |
|活动工作表上的名称数据库定义为区域 A1: F500。  <br/> |"!数据库  <br/> |"= R1C1: R500C6"  <br/> |
   
## <a name="see-also"></a>另请参阅

- [xlfGetDef](xlfgetdef.md)
- [实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

