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
ms.openlocfilehash: bf02f71458f2f4d8514f69a6b6f0921b5318303a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310288"
---
# <a name="xlautoopen"></a>xlAutoOpen

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
必须由每个有效 XLL 实现和导出的回调函数。 在注册 XLL 函数和命令、初始化数据结构、自定义用户界面等的地方, 建议使用**xlAutoOpen**函数。 
  
```cs
int WINAPI xlAutoOpen(void);
```

## <a name="parameters"></a>参数

此函数无需使用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数的实现必须返回 1 (**int**)。
  
## <a name="remarks"></a>说明

每次激活 XLL 时, Microsoft Excel 都会调用**xlAutoOpen** 。 在下列情况下, 将激活 XLL: 
  
- 在 excel 会话开始时, 如果它在正常结束的最后一个 excel 会话中处于活动状态。
    
- 如果在 Excel 会话过程中加载。
    
- 可以通过以下几种方式加载 XLL:
    
- 通过选择 "**文件**" 菜单上的 "**打开**" (Excel 版本支持这种加载 xll 的方法)。 
    
- 使用加载项管理器。
    
- 使用此 DLL 的名称作为唯一参数调用[xlfRegister](xlfregister-form-1.md)的另一个 XLL。 
    
- 从以该 DLL 的名称作为唯一参数调用[REGISTER](xlfregister-form-1.md)的 XLM 宏工作表。 
    
- 如果外接程序在 Excel 会话期间停用并重新激活, 则会在重新激活时调用此函数。
    
### <a name="example"></a>示例

请参阅文件`SAMPLES\EXAMPLE\EXAMPLE.C`和`SAMPLES\GENERIC\GENERIC.C`, 以及此函数的示例实现。
  
## <a name="see-also"></a>另请参阅



[xlAutoClose](xlautoclose.md)
  
[xlAutoRegister/xlAutoRegister12](xlautoregister-xlautoregister12.md)


[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)

