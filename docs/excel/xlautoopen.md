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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: bf02f71458f2f4d8514f69a6b6f0921b5318303a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406645"
---
# <a name="xlautoopen"></a>xlAutoOpen

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
必须由每个有效的 XLL 实现和导出的回调函数。 **建议使用 xlAutoOpen** 函数注册 XLL 函数和命令、初始化数据结构、自定义用户界面等。 
  
```cs
int WINAPI xlAutoOpen(void);
```

## <a name="parameters"></a>参数

此函数无需使用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数的实现必须返回 1 (**int**)。
  
## <a name="remarks"></a>说明

Microsoft Excel **激活 XLL 时调用 xlAutoOpen。** 在下列情况下将激活 XLL： 
  
- 在会话会话的Excel，如果它在正常结束的上一Excel会话处于活动状态。
    
- 如果在会话期间加载Excel会话。
    
- 可以通过多种方式加载 XLL：
    
- 选择"**文件**"菜单上的"打开 (，其中 Excel 支持此方法加载 XLL) 。 
    
- 使用加载项管理器。
    
- 从另一个调用 [xlfRegister](xlfregister-form-1.md) 的 XLL 中，此 DLL 的名称作为唯一参数。 
    
- 从调用 [REGISTER](xlfregister-form-1.md) 的 XLM 宏工作表中，此 DLL 的名称作为唯一参数。 
    
- 如果在重新激活会话期间停用并重新激活Excel，则重新激活时将调用此函数。
    
### <a name="example"></a>示例

请参阅 文件和  `SAMPLES\EXAMPLE\EXAMPLE.C`  `SAMPLES\GENERIC\GENERIC.C` ，有关此函数的示例实现。
  
## <a name="see-also"></a>另请参阅



[xlAutoClose](xlautoclose.md)
  
[xlAutoRegister/xlAutoRegister12](xlautoregister-xlautoregister12.md)


[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)

