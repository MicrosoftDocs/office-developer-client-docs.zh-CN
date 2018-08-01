---
title: xlAutoRemove
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAutoRemove
keywords:
- xlautoremove 函数 [excel 2007]
localization_priority: Normal
ms.assetid: fff0de4d-605d-49e6-a5be-a000410c09d8
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 6e5daac21a6d89472a7d84a25e9aeaea56db1ae1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773843"
---
# <a name="xlautoremove"></a>xlAutoRemove

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
由 Microsoft Excel 每当用户将停用 XLL Excel 会话过程中使用加载项管理器调用。 Excel 关闭会话时，通常或异常，与安装的加载项时，不会调用此函数。
  
可以使用此函数，以显示自定义对话框告知用户的外接程序已停用，或进行读取或写入到注册表，例如。
  
Excel 不需要 XLL 实施和导出此函数。 
  
```cs
int WINAPI xlAutoRemove(void);
```

## <a name="parameters"></a>参数

此函数无需使用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数的实现必须返回 1 (**int**)。
  
## <a name="remarks"></a>说明

如果您 XLL 需要完成任何任务加载项管理器中删除时，请使用此函数。
  
## <a name="example"></a>示例

查看文件 `\SAMPLES\EXAMPLE\EXAMPLE.C` 和 `\SAMPLES\GENERIC\GENERIC.C`，了解此函数的示例实现。 以下代码来自 `\SAMPLES\EXAMPLE\EXAMPLE.C`。
  
```cs
int WINAPI xlAutoRemove(void)
{
/* Display a dialog box indicating that the XLL was successfully removed */
   Excel12f(xlcAlert, 0, 2,
      TempStr12(L"Thank you for removing Example.XLL!"),
      TempInt12(2));
   return 1;
}
```

## <a name="see-also"></a>另请参阅



[xlAutoAdd](xlautoadd.md)


[加载项管理器和 XLL 接口函数](add-in-manager-and-xll-interface-functions.md)

