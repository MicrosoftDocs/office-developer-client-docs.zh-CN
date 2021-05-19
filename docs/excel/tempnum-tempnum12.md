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
- tempnum12 函数 [excel 2007]，TempNum 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 5b74d618-db3a-4d84-bd17-4fee7ae3b51e
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: cabd44ab828a2cfe22253e9aaf12abf7b7709d69
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426630"
---
# <a name="tempnumtempnum12"></a>TempNum/TempNum12

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
创建临时 /  **XLOPER XLOPER12** 的框架库函数，其中包含 IEEE Microsoft Excel 8 字节 (的工作表) 。 
  
```cs
LPXLOPER TempNum(double d);
LPXLOPER12 TempNum12(double d);
```

## <a name="parameters"></a>参数

 _d_ (**double)**
  
预期值。 请注意，IEEE 次正常数字当前不受支持，并且四舍五入为零。 支持负无穷大。
  
## <a name="return-value"></a>返回值

返回一个 **数值 xltypeNum，** 如果传入的值是次正常值，则包含传入或零的值。 
  
## <a name="example"></a>示例

此示例使用 **TempNum12** 函数将参数传递给 **xlfGetWorkspace**。
  
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

