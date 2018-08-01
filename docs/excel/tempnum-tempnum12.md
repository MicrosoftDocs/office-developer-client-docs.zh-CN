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
- tempnum12 函数 [excel 2007，] TempNum 函数 [Excel 2007]
localization_priority: Normal
ms.assetid: 5b74d618-db3a-4d84-bd17-4fee7ae3b51e
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 5ebe58dba32c2cf0382bf0811713eaa0a5471dda
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773818"
---
# <a name="tempnumtempnum12"></a>TempNum/TempNum12

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
创建临时**XLOPER**的框架库函数/ **XLOPER12**包含 Microsoft Excel 工作表数目 (IEEE 8 字节 double)。 
  
```cs
LPXLOPER TempNum(double d);
LPXLOPER12 TempNum12(double d);
```

## <a name="parameters"></a>参数

 _d_ (**double**)
  
预期的值。 请注意，IEEE 子正常数字目前不支持四舍五入为零。 支持无穷大负数。
  
## <a name="return-value"></a>返回值

返回包含值的数值**xltypeNum**传入或零，如果已子正文中传递的值。 
  
## <a name="example"></a>示例

本示例使用**TempNum12**函数将参数传递给**xlfGetWorkspace**。
  
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

