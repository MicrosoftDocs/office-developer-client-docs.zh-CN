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
  
返回名称的定义，该定义出现在名称管理器对话框的引用列中，当单击"公式"选项卡上"定义的名称"部分中的"名称管理器 **"** 时，将显示该列。 如果定义包含引用，则这些引用将给定为 R1C1 样式的引用。 使用 **xlfGetName** 检查由名称定义的值。 若要获取与定义对应的名称，请使用 [xlfGetDef](xlfgetdef.md)。
  
```cpp
Excel12(xlfGetName, LPXLOPER12 pxRes, 2, LPXLOPER12 pxNameText, LPXLOPER12 pxInfoType);
```

## <a name="parameters"></a>参数

_pxNameText_ (**xltypeStr**) 
  
可以是工作表上定义的名称;对活动工作簿上定义的名称的外部引用，例如 ;或对特定打开的工作簿上定义的名称的外部引用，  `"!Sales"` 例如，  `"[Book1]SHEET1!Sales"` 。  _pxNameText_ 还可以是隐藏名称。 
  
_pxInfoType_ (**xltypeBool)**
  
指定要返回有关名称的信息的类型。 如果 **为 FALSE** 或省略，则返回定义。 如果 **为 TRUE，** 则如果只为工作表定义名称，则返回 **TRUE;** 如果为整个工作簿定义名称，则返回 **FALSE。** 
  
## <a name="property-valuereturn-value"></a>属性值/返回值

_pxRes_ (**xltypeStr、xltypeBool** 或 **xltypeErr**) 
  
根据为  _pxInfoType_ 传递的值，返回指定名称 **(xltypeStr**) 或 **TRUE** 或 **FALSE** (**xltypeBool**) 。
  
## <a name="remarks"></a>备注

如果在 **"保护** 工作表"对话框中选中了"保护工作表和锁定单元格的内容"复选框以保护包含该名称的工作簿，**则 xlfGetName** 将返回 `#N/A` 错误值。 To see the **Protect Sheet** dialog box， click **Protect Sheet** in the **Changes** section of the **Review** tab. 
  
下表列出了调用 **xlfGetDef（** 使用指定的  _pxNameText_ 参数）返回的三个值示例。 
  
|**Excel**|**_pxNameText_**|**返回的值**|
|:-----|:-----|:-----|
|工作表上的名称 Sales 定义为数字 523。  <br/> |"Sales"  <br/> |"=523"  <br/> |
|活动工作表上的名称 Profit 定义为公式 =Sales-Costs。  <br/> |"!盈利"  <br/> |"=Sales-Costs"  <br/> |
|活动工作表上的名称 Database 定义为区域 A1：F500。  <br/> |"!Database"  <br/> |"=R1C1：R500C6"  <br/> |
   
## <a name="see-also"></a>另请参阅

- [xlfGetDef](xlfgetdef.md)
- [实用的基本 C API XLM 函数](essential-and-useful-c-api-xlm-functions.md)

