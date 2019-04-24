---
title: FGetComponentPath
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FGetComponentPath
api_type:
- COM
ms.assetid: 2a303458-3283-409a-bc3b-b891f3fcfc22
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3456d81935a0a94bc2158eefd321da968dda9983
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335208"
---
# <a name="fgetcomponentpath"></a>FGetComponentPath

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回私有 Mapi32 的路径。
  
```cpp
BOOL FGetComponentPath(
  LPCSTR szComponent,
  LPSTR szQualifier,
  LPSTR szDllPath,
  DWORD cchBufferSize,
  BOOL fInstall
);
```

## <a name="parameters"></a>参数

 _szComponent_
  
> 实时[Mapi32 存根 (Stub) 注册表设置](https://msdn.microsoft.com/library/dd162409.aspx)中所述的 MSIComponentID 注册表项。
    
 _szQualifier_
  
> 实时[选择要加载的 MAPI 的特定版本](how-to-choose-a-specific-version-of-mapi-to-load.md)中所述的 MSIApplicationLCID 或 MSIOfficeLCID 子项。 如果没有限定符, 调用方可以传递**null** 。 
    
 _szDllPath_
  
> 实时包含完整 MAPI 功能 (与 Mapi32 相同的导出) 的专用 Mapi32 的路径。
    
 _cchBufferSize_
  
> 实时_szDllPath_的大小, 以字符为单位。
    
 _fInstall_
  
> 实时通知 MAPI 安装私有 Mapi32 组件 (如果缺少)。
    
## <a name="return-value"></a>返回值

 **true**
  
> 找到路径。
    
 **该值**
  
> 找不到路径。
    
## <a name="remarks"></a>注解

当您需要获取专用 Mapi32 的路径时, 请使用**FGetComponentPath**函数。 
  
## <a name="see-also"></a>另请参阅



[选择要加载的 MAPI 的特定版本](how-to-choose-a-specific-version-of-mapi-to-load.md)


[Mapi32 存根注册表设置](https://msdn.microsoft.com/library/dd162409.aspx)

