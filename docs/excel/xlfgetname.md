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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 63bfc6e94950a621c2367b2d35d25e3de48b344f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773840"
---
# <a name="xlfgetname"></a>xlfGetName

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
返回的**名称管理器**对话框中，单击**公式**选项卡**定义名称**部分中的**名称管理器**时显示**引用位置**列中显示名称的定义。如果定义中包含的引用，它们可作为 R1C1-样式引用。 使用**xlfGetName**检查由 name 定义的值。 若要获取对应于定义的名称，请使用[xlfGetDef](xlfgetdef.md)。
  
```cpp
Excel12(xlfGetName, LPXLOPER12 pxRes, 2, LPXLOPER12 pxNameText, LPXLOPER12 pxInfoType);
```

## <a name="parameters"></a>参数

_pxNameText_(**xltypeStr**)
  
可以名称定义了工作表;对活动工作簿，例如上, 定义的名称的外部引用`"!Sales"`;外部引用特定打开工作簿，例如，已定义的名称或`"[Book1]SHEET1!Sales"`。  _pxNameText_也可能是隐藏的名称。 
  
_pxInfoType_(**xltypeBool**)
  
指定要返回的有关名称的信息类型。 如果**FALSE**或省略，则返回的定义。 如果 **，则返回 TRUE**，则返回**TRUE**如果整个工作簿定义名称，如果为只工作表， **FALSE**定义名称。 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

_pxRes_（**xltypeStr**、 **xltypeBool**或**xltypeErr**）
  
根据为_pxInfoType_传递的值，将返回指定的名称 (**xltypeStr**)，或**TRUE**或**FALSE** (**xltypeBool**) 的定义。
  
## <a name="remarks"></a>说明

如果**保护工作表和锁定的单元格的内容**复选框已选择了**保护工作表**对话框中来保护包含名称的工作簿**xlfGetName**返回`#N/A`错误值。 若要查看**保护工作表**对话框中，单击**保护工作表**的**更改**部分的**审阅**选项卡。 
  
下表列出了通过调用**xlfGetDef**指定的_pxNameText_参数返回的值的三个示例。 
  
|**在 Excel 中的定义**|**_pxNameText_**|**返回值**|
|:-----|:-----|:-----|
|工作表上的名称销售被定义为 523 的号码。  <br/> |"Sales"  <br/> |"= 523"  <br/> |
|活动工作表的名称利润定义为公式 = 销售成本。  <br/> |"!利润"  <br/> |"= 销售成本"  <br/> |
|在活动工作表上的数据库名称定义为 A1:F500 的范围。  <br/> |"!数据库"  <br/> |"= R1C1:R500C6"  <br/> |
   
## <a name="see-also"></a>另请参阅

- [xlfGetDef](xlfgetdef.md)
- [基本的有用 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

