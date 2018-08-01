---
title: xlAutoOpen
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAutoOpen
keywords:
- xlautoopen 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 748cecb6-61d0-496b-a1a4-a73d22eb29e2
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: bf64841cbd75e25443abe5cfc7d3d7419757e245
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773826"
---
# <a name="xlautoopen"></a>xlAutoOpen

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
必须实现和每个有效 XLL 导出的回调函数。 **XlAutoOpen**函数是从何处到注册 XLL 函数和命令的建议的位置、 初始化数据结构、 自定义用户界面，等等。 
  
```cs
int WINAPI xlAutoOpen(void);
```

## <a name="parameters"></a>参数

此函数无需使用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数的实现必须返回 1 (**int**)。
  
## <a name="remarks"></a>说明

Microsoft Excel 每当激活 XLL 调用**xlAutoOpen** 。 XLL 激活在下列情况下： 
  
- 如果活动通常结束最后一个 Excel 会话中的 Excel 会话开头。
    
- 如果加载 Excel 会话过程中。
    
- 以下几种方式，可加载 XLL:
    
- 通过在**文件**菜单 （其中的 Excel 版本支持此方法的加载 xll （英文）） 中选择**打开**。 
    
- 使用加载项管理器。
    
- 从另一个 XLL 调用[xlfRegister](xlfregister-form-1.md)与此 DLL 作为唯一参数的名称。 
    
- 从 XLM 宏工作表的调用[注册](xlfregister-form-1.md)的此 DLL 名称作为唯一的参数。 
    
- 外接程序是停用和重新激活 Excel 会话期间，如果是在重新激活上调用此函数。
    
### <a name="example"></a>示例

请参阅文件`SAMPLES\EXAMPLE\EXAMPLE.C`和`SAMPLES\GENERIC\GENERIC.C`，和例如实现此函数。
  
## <a name="see-also"></a>另请参阅



[xlAutoClose](xlautoclose.md)
  
[xlAutoRegister/xlAutoRegister12](xlautoregister-xlautoregister12.md)


[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)

