---
title: xlDefineBinaryName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlDefineBinaryName
keywords:
- xldefinebinaryname 函数 [excel 2007]
localization_priority: Normal
ms.assetid: e3e8f91b-cc31-4f09-9941-f950ae96820a
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3c7fc4f6b6fc7179c1ca84043895273b2781f8b5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310211"
---
# <a name="xldefinebinaryname"></a>xlDefineBinaryName

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
用于为**xltypeBigData** **XLOPER**/ **XLOPER12**分配永久存储。 在工作簿中保存带有定义的二进制名称的数据, 并可随时通过名称访问这些数据。 有关详细信息, 请参阅[Excel XLL 开发的已知问题](known-issues-in-excel-xll-development.md)中的 "二进制名称作用域限制"。
  
```cs
Excel12(xlDefineBinaryName, 0, 2, LPXLOPER12 pxName, LPXLOPER12 pxData);
```

## <a name="parameters"></a>参数

 _pxName_(**xltypeStr**)
  
一个指定数据的名称的字符串。 该字符串遵循与定义的名称相同的命名限制。
  
 _pxData_(**xltypeBigData**)
  
用于指定要存储的数据的 Bigdata 结构。 调用此函数时, **bigdata**结构的**lpbData**成员应指向要为其定义名称的数据, 并且**cbData**成员应包含数据的长度 (以字节为单位)。 
  
如果未指定_pxData_参数 (**xltypeMissing**), 则将删除由_pxName_指定的命名分配。 
  
## <a name="see-also"></a>另请参阅



[xlGetBinaryName](xlgetbinaryname.md)


[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
[Excel XLL 开发中的已知问题](known-issues-in-excel-xll-development.md)

