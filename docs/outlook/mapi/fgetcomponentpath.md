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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fa39128ffaaaa3530b74a660c14971834a99561b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566346"
---
# <a name="fgetcomponentpath"></a>FGetComponentPath

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
返回专用 Mapi32.dll 的路径。
  
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
  
> [in]MSIComponentID 注册表项[Mapi32.dll 存根注册表 Settings](http://msdn.microsoft.com/en-us/library/dd162409.aspx)中所述。
    
 _szQualifier_
  
> [in][选择特定版本的 MAPI 到负载](how-to-choose-a-specific-version-of-mapi-to-load.md)中描述的 MSIApplicationLCID 或 MSIOfficeLCID 子项。 如果没有任何限定符，调用方可以传递**null** 。 
    
 _szDllPath_
  
> [in]指向专用 Mapi32.dll，已完整 MAPI 功能 （作为 Mapi32.dll 相同的导出） 的路径。
    
 _cchBufferSize_
  
> [in]_SzDllPath_，以字符为单位的大小。
    
 _fInstall_
  
> [in]告知 MAPI 安装私有 Mapi32.dll 组件，如果不存在。
    
## <a name="return-value"></a>返回值

 **true**
  
> 找到路径。
    
 **false**
  
> 找不到路径。
    
## <a name="remarks"></a>注解

当您需要获取专用 Mapi32.dll 的路径，请使用**FGetComponentPath**函数。 
  
## <a name="see-also"></a>另请参阅



[选择要加载的 MAPI 的特定版本](how-to-choose-a-specific-version-of-mapi-to-load.md)


[Mapi32.dll 存根注册表设置](http://msdn.microsoft.com/en-us/library/dd162409.aspx)

