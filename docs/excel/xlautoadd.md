---
title: xlAutoAdd
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAutoAdd
keywords:
- xlautoadd 函数 [excel 2007]
localization_priority: Normal
ms.assetid: c69299af-a28a-44d9-be10-9c9fb92e21f2
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 9a38d5dafd30fda87dda5eadf8fa97ab6e6768a7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413757"
---
# <a name="xlautoadd"></a>xlAutoAdd

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
每当用户Microsoft Excel管理器在 Excel 会话期间激活 XLL 时，Add-In添加。 在启动和加载Excel加载项时，不会调用此函数。
  
此函数可用于显示一个自定义对话框，该对话框告知用户外接程序已激活，或者读取或写入注册表，或检查许可信息，例如。
  
Excel不需要 XLL 来实现和导出此函数。
  
```cs
int WINAPI xlAutoAdd(void);
```

## <a name="parameters"></a>参数

此函数无需使用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数的实现应返回 1。  (**int) 。**
  
## <a name="remarks"></a>备注

如果 XLL 在由 XLL 管理器添加时需要执行Add-In函数。
  
## <a name="example"></a>示例

有关  `\SAMPLES\EXAMPLE\EXAMPLE.C`  `\SAMPLES\GENERIC\GENERIC.C` 此函数的示例实现，请参阅 和 。 以下代码来自 `\SAMPLES\EXAMPLE\EXAMPLE.C`。
  
```cs
int WINAPI xlAutoAdd(void)
{
    XCHAR szBuf[255];
    wsprintfW((LPWSTR)szBuf, L"Thank you for adding Example.XLL\n"
            L"build date %hs, time %hs",__DATE__, __TIME__);
/* Display a dialog indicating that the XLL was successfully added */
    Excel12f(xlcAlert, 0, 2, TempStr12(szBuf), TempInt12(2));
    return 1;
}
```

## <a name="see-also"></a>另请参阅



[xlAutoRemove](xlautoremove.md)


[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)

