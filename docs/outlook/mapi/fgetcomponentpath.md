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
  
返回专用路径Mapi32.dll。
  
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
  
> [in]存根注册表中介绍的 MSIComponentIDMapi32.dll[注册表设置。](https://msdn.microsoft.com/library/dd162409.aspx)
    
 _szQualifier_
  
> [in]"选择要加载的 MAPI 的特定版本"中介绍的 MSIApplicationLCID 或 MSIOfficeLCID [子项](how-to-choose-a-specific-version-of-mapi-to-load.md)。 如果没有限定符，则调用方可以传递 **null。** 
    
 _szDllPath_
  
> [in]专用应用程序的路径，Mapi32.dll具有完整 MAPI 功能 (导出与Mapi32.dll) 。
    
 _cchBufferSize_
  
> [in]  _szDllPath 的大小（_ 以字符表示）。
    
 _fInstall_
  
> [in]指示 MAPI 安装专用 Mapi32.dll组件（如果不存在）。
    
## <a name="return-value"></a>返回值

 **true**
  
> 找到路径。
    
 **false**
  
> 未找到路径。
    
## <a name="remarks"></a>备注

需要获取专用路径的路径时，请使用 **FGetComponentPath** Mapi32.dll。 
  
## <a name="see-also"></a>另请参阅



[选择要加载的 MAPI 的特定版本](how-to-choose-a-specific-version-of-mapi-to-load.md)


[Mapi32.dll存根注册表设置](https://msdn.microsoft.com/library/dd162409.aspx)

