---
title: fExit
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- fExit
keywords:
- fexit 函数 [excel 2007]
localization_priority: Normal
ms.assetid: d85685fa-df70-45bb-b629-a9d43b5cb926
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 3abb5cd68a45fbcd16665dbc4d492d764bbd315e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773739"
---
# <a name="fexit"></a>fExit

 **适用于**： Excel 2013 |Office 2013 |Visual Studio 
  
示例用户定义卸载 GENERIC.xll 的命令。 当加载 GENERIC.xll 时，它会创建用户定义的菜单中，一般，通过其访问此命令。 
  
```cs
int WINAPI fExit(void);
```

## <a name="parameters"></a>参数

函数没有参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数始终返回 1。
  
## <a name="remarks"></a>备注

这是一个用户启动例程，退出 GENERIC.xll 应避免只需调用`UNREGISTER("GENERIC.XLL")`在此函数。 即使它们注册其他地方 else，这会关闭注销此 DLL 中的所有功能。 相反，一次注销一个的功能。 
  
### <a name="example"></a>示例

请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。 
  
## <a name="see-also"></a>另请参阅



[泛型 DLL 中的函数](functions-in-the-generic-dll.md)

