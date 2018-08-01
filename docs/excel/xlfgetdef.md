---
title: xlfGetDef
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
keywords:
- xlfgetdef
localization_priority: Normal
ms.assetid: 68f5edbd-9040-46d3-acd5-dd51ca82f6fa
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 030c4e501e8a9eb4b6ce29d7fe0e171324b50b5c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773861"
---
# <a name="xlfgetdef"></a>xlfGetDef

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
返回为文本，为特定区域、 值或公式工作簿中的定义的名称。 在 Excel 中，此值显示在**名称管理器**对话框中，单击**名称管理器**中使用**xlfGetDef** **公式**选项卡上**定义名称**部分获取时显示的**名称**列对应于定义的名称。 若要获取的名称定义，请使用[xlfGetName](xlfgetname.md)。
  
```cpp
Excel12(xlfGetDef, LPXLOPER12 pxRes, 3, LPXLOPER12 pxDefText, LPXLOPER12 pxDocumentText, LPXLOPER12 pxTypeNum);
```

## <a name="parameters"></a>参数

_pxDefText_(**xltypeStr**)
  
可以是任何您可以定义名称来引用，其中包括参考、 值、 对象或公式。
  
引用必须授予以 R1C1 样式，如`"R3C5"`。 如果值或公式， _pxDefText_ ，不需要包括在**名称管理器**对话框的**引用到**列中显示等号。 如果有多个名称_pxDefText_， **xlfGetDef**返回第一个名称。 如果没有名称匹配_pxDefText_， **xlfGetDef**返回`#NAME?`错误值。 
  
_pxDocumentText_(**xltypeStr**)
  
指定工作表的_pxDefText_位于。 如果省略_pxDocumentText_ ，则假定为活动工作表。 
  
_pxTypeNum_(**xltypeNum**)
  
介于 1 到 3 指定返回哪些类型的名称。
  
|**_pxTypeNum_**|**返回**|
|:-----|:-----|
|1 或省略  <br/> |普通的名称。  <br/> |
|2  <br/> |隐藏的名称。  <br/> |
|3  <br/> |所有名称。  <br/> |
   
## <a name="property-valuereturn-value"></a>属性值/返回值

 _pxRes_（**xltypeStr**或**xltypeErr**）
  
返回与指定的定义关联的名称。
  
## <a name="remarks"></a>说明

下表列出了通过调用**xlfGetDef**用指定的参数返回的值的四个示例。 
  
|**在 Excel 中定义的名称**|**_pxDefText_**|**_pxDocumentText_**|**_pxTypeNum_**|**返回值**|
|:-----|:-----|:-----|:-----|:-----|
|Sheet4 中的指定的范围名为 Sales。  <br/> |"R2C2:R9C6"  <br/> |"Sheet4"  <br/> |\<省略\>  <br/> |"Sales"  <br/> |
|Sheet4 中的值 100 被定义为常量。  <br/> |"100"  <br/> |"Sheet4"  <br/> |\<省略\>  <br/> |"常量"  <br/> |
|SumTotal 名为 Sheet4 中指定的公式。  <br/> |"SUM(R1C1:R10C1)"  <br/> |"Sheet4"  <br/> |\<省略\>  <br/> |"SumTotal"  <br/> |
|3 被定义为活动工作表上的隐藏名称计数器。  <br/> |"3"  <br/> |\<省略\>  <br/> |2  <br/> |"计数器"  <br/> |
   
## <a name="see-also"></a>另请参阅

- [xlfGetName](xlfgetname.md)
- [基本的有用 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

