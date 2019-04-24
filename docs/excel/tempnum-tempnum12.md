---
title: TempNum/TempNum12
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- TempNum
- TempNum12
keywords:
- tempnum12 函数 [excel 2007], TempNum 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 5b74d618-db3a-4d84-bd17-4fee7ae3b51e
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: cabd44ab828a2cfe22253e9aaf12abf7b7709d69
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310358"
---
# <a name="tempnumtempnum12"></a>TempNum/TempNum12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Framework library 函数, 该函数创建一个包含 Microsoft Excel 工作表编号 (IEEE 8 字节双精度型) 的临时**XLOPER**/ **XLOPER12** 。 
  
```cs
LPXLOPER TempNum(double d);
LPXLOPER12 TempNum12(double d);
```

## <a name="parameters"></a>参数

 _d_ (**双精度型**)
  
预期值。 请注意, 目前不支持 IEEE 子法线号码, 并将其舍入为零。 支持负无穷。
  
## <a name="return-value"></a>返回值

返回一个数值**xltypeNum** , 其中包含传入的值或零 (如果传入的值为 "sub normal")。 
  
## <a name="example"></a>示例

此示例使用**TempNum12**函数将参数传递给**xlfGetWorkspace**。
  
 `\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI TempNumExample(void)
{
   XLOPER12 xRes;
   Excel12f(xlfGetWorkspace, &xRes, 1, TempNum12(44));
   Excel12f(xlFree, 0, 1, (LPXLOPER12)&xRes);
   return 1;
}
```

## <a name="see-also"></a>另请参阅



[框架库中的函数](functions-in-the-framework-library.md)

