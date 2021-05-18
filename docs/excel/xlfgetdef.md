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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 014db553156849d84bd07e0e416f8cb3fefb4e0b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421996"
---
# <a name="xlfgetdef"></a>xlfGetDef

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
以文本格式返回为工作簿中的特定区域、值或公式定义的名称。 在Excel中，此值显示在"名称管理器"对话框的"名称"列中，当您单击"公式"选项卡上"定义的名称"部分中的"名称管理器"时，**将显示该对话框**。 使用 **xlfGetDef** 获取与定义对应的名称。 若要获取名称的定义，请使用 [xlfGetName](xlfgetname.md)。
  
```cpp
Excel12(xlfGetDef, LPXLOPER12 pxRes, 3, LPXLOPER12 pxDefText, LPXLOPER12 pxDocumentText, LPXLOPER12 pxTypeNum);
```

## <a name="parameters"></a>参数

_pxDefText_ (**xltypeStr**) 
  
可以是您可以定义要引用的名称的任何内容，包括引用、值、对象或公式。
  
引用必须以 R1C1 样式提供，例如  `"R3C5"` 。 如果 _pxDefText_ 是值或公式，则不需要包括名称管理器对话框中"引用位置"列中 **显示的等号**。  如果  _pxDefText_ 存在多个名称 **，xlfGetDef** 将返回第一个名称。 如果没有名称与  _pxDefText_ 匹配 **，xlfGetDef** 将返回  `#NAME?` 错误值。 
  
_pxDocumentText_ (**xltypeStr**) 
  
指定  _pxDefText_ 位于的工作表。 如果  _省略 pxDocumentText，_ 则假定它是活动工作表。 
  
_pxTypeNum_ (**xltypeNum**) 
  
一个 1 到 3 个数字，用于指定返回的名称类型。
  
|**_pxTypeNum_**|**返回**|
|:-----|:-----|
|1 或省略  <br/> |仅普通名称。  <br/> |
|2  <br/> |仅隐藏名称。  <br/> |
|3  <br/> |所有名称。  <br/> |
   
## <a name="property-valuereturn-value"></a>属性值/返回值

 _pxRes_ (**xltypeStr** 或 **xltypeErr)**
  
返回与指定定义关联的名称。
  
## <a name="remarks"></a>备注

下表列出了使用指定参数调用 **xlfGetDef** 返回的四个值示例。 
  
|**中定义Excel**|**_pxDefText_**|**_pxDocumentText_**|**_pxTypeNum_**|**返回的值**|
|:-----|:-----|:-----|:-----|:-----|
|Sheet4 中的指定区域名为 Sales。  <br/> |"R2C2：R9C6"  <br/> |"Sheet4"  <br/> |\<省略\>  <br/> |"Sales"  <br/> |
|Sheet4 中的值 100 定义为 Constant。  <br/> |"100"  <br/> |"Sheet4"  <br/> |\<省略\>  <br/> |"Constant"  <br/> |
|Sheet4 中的指定公式名为 SumTotal。  <br/> |"SUM (R1C1：R10C1) "  <br/> |"Sheet4"  <br/> |\<省略\>  <br/> |"SumTotal"  <br/> |
|3 定义为活动工作表上的隐藏名称 Counter。  <br/> |"3"  <br/> |\<省略\>  <br/> |2  <br/> |"Counter"  <br/> |
   
## <a name="see-also"></a>另请参阅

- [xlfGetName](xlfgetname.md)
- [实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

