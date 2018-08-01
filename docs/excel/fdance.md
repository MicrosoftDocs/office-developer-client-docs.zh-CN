---
title: fDance
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- fDance
keywords:
- fdance 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 8c2f2d83-b7aa-456e-b473-a54897bc35ae
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: b7a2fbdf723d06dcf9b02789178d7d12d0515884
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773752"
---
# <a name="fdance"></a>fDance

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
示例用户定义直到用户按**ESC**更改所选单元格周围活动工作表上的命令。 当加载 GENERIC.xll 时，它会创建用户定义的菜单中，一般，通过其访问此命令。
  
```cs
int WINAPI fDance(void);
```

## <a name="parameters"></a>参数

函数没有参数。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

此函数始终返回 1。
  
## <a name="remarks"></a>说明

这是较长操作的示例。 有时，它调用函数[xlAbort](xlabort.md) 。 这会产生处理器 （与协作式多任务帮助），并检查用户是否已按**esc 键**以取消操作。 如果是这样，它会向用户提供有机会在取消中止。 
  
### <a name="example"></a>示例

请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。 
  
## <a name="see-also"></a>另请参阅



[通用 DLL 中的函数](functions-in-the-generic-dll.md)

