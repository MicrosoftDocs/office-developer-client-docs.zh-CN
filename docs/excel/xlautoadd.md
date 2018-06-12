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
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: ae0b4ae2d5f5fc58c3e18ffa9d79ec4128cb4639
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773825"
---
# <a name="xlautoadd"></a>xlAutoAdd

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
添加 Microsoft excel 每当用户激活 Excel 会话期间 XLL 使用加载项管理器。 Excel 启动和加载预安装的加载项时，不会调用此函数。
  
可以使用此函数以显示自定义对话框中，告知用户的外接程序已被激活，或要读取或写入注册表，例如检查许可信息。
  
Excel 不需要 XLL 实施和导出此函数。
  
```cs
int WINAPI xlAutoAdd(void);
```

## <a name="parameters"></a>参数

此函数不采用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数的实现应返回 1。 (**int**)。
  
## <a name="remarks"></a>备注

如果没有任何您 XLL 需要执行添加由加载项管理器时，请使用此函数。
  
## <a name="example"></a>示例

请参阅`\SAMPLES\EXAMPLE\EXAMPLE.C`和`\SAMPLES\GENERIC\GENERIC.C`，例如此函数的实现。 下面的代码是从`\SAMPLES\EXAMPLE\EXAMPLE.C`。
  
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

