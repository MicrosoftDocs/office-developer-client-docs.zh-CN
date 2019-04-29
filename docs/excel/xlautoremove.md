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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: af8bd2d44883b1820be42b82d4fe4794fa29caab
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425475"
---
# <a name="xlautoremove"></a>xlAutoRemove

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
当用户使用外接程序管理器在 excel 会话期间停用 XLL 时, 由 Microsoft Excel 调用。 如果在已安装加载项的情况下 Excel 会话正常或异常关闭，则不会调用此函数。
  
此函数可用于显示一个自定义对话框, 告诉用户外接程序已停用, 或者读取或写入注册表, 例如。
  
Excel 不需要 XLL 即可实现和导出此函数。 
  
```cs
int WINAPI xlAutoRemove(void);
```

## <a name="parameters"></a>参数

此函数无需使用任何参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数的实现必须返回 1 (**int**)。
  
## <a name="remarks"></a>说明

如果您的 XLL 需要在加载项管理器删除任何任务时完成任何任务, 请使用此函数。
  
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

