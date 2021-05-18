---
title: NSTServiceEntry
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 5ada6363-2406-4c0a-8326-a299a8bbefe1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 96c04a242c477204ea1447fb78c31d189eeac59a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280052"
---
# <a name="nstserviceentry"></a>NSTServiceEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 存储提供程序的邮件服务入口点函数，用于将基于 PST 的本地存储包装为 NST 存储。 
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|实现者：  <br/> |MAPI 提供程序  <br/> |
|调用者：  <br/> |MAPI  <br/> |
   
```cpp
HRESULT NSTServiceEntry( 
    HINSTANCE hInstance,   
    LPMALLOC lpMalloc, 
    LPMAPISUP lpMAPISup, 
    ULONG ulUIParam, 
    ULONG ulFlags, 
    ULONG ulContext, 
    ULONG cValues, 
    LPSPropValue lpProps, 
    LPPROVIDERADMIN lpProviderAdmin, 
    LPMAPIERROR FAR * lppMapiError 
);
```

## <a name="parameters"></a>参数

 **NSTServiceEntry** 使用 **[MSGSERVICEENTRY](msgserviceentry.md)** 函数原型。 有关其参数的信息，请参阅 **[MSGSERVICEENTRY。](msgserviceentry.md)** 
  
## <a name="return-values"></a>返回值

有关返回值的信息，请参阅 **[MSGSERVICEENTRY。](msgserviceentry.md)** 
  
## <a name="remarks"></a>备注

使用 **[GetProcAddress](https://msdn.microsoft.com/library/ms683212.aspx)** 在 msmapi32.dll 中查找此函数的地址时，请指定"NSTServiceEntry"作为过程名称。 
  
若要使用复制 API，MAPI 存储提供程序必须先通过调用 **[NSTServiceEntry](nstserviceentry.md)** 打开并包装基于 PST 的本地存储。 然后，提供程序可以使用 **[API、IOSTX](iostxiunknown.md)** 和 **[IPSTX](ipstxiunknown.md)** 的主要接口执行复制。 
  
以下备注适用于 NST 存储：
  
- 实现使用 **NSTServiceEntry** 的 MAPI 提供程序时，请不要在全局配置文件部分中存储任何信息。 全局配置文件部分由多个提供程序共享，并且此配置文件中存储的数据可以覆盖。 
    
- 只有具有现有修改时间戳的项才能在保存时更新其标记。 
    
- 保存项目时不会自动进行冲突检查。
    
-  保存项目时不会发生重复检测。 
    
-  表示服务器的缓存版本的文件附加有 。NST。 
    
- 若要获取指向全局配置文件节的指针，邮件服务使用 **pbNSTGlobalProfileSectionGuid** 调用支持对象中的 **[IMAPISupport：：OpenProfileSection，](imapisupport-openprofilesection.md)** 定义如下： 
    
  ```
  #define  pbNSTGlobalProfileSectionGuid "\x85\xED\x14\x23\x9D\xF7\x42\x66\x8B\xF2\xFB\xD4\xA5\x21\x29\x41"
  ```

- 在这种情况下，邮件服务的支持对象应确保 **IMAPISupport：：OpenProfileSection** 返回由默认配置文件部分中的 **[PR_SERVICE_UID](pidtagserviceuid-canonical-property.md)** 属性标识的配置文件节。 若要获取此配置文件部分，支持对象可以打开默认配置文件部分，检索 **PR_SERVICE_UID，** 将结果传递给 **IMAPISupport：：OpenProfileSection** 以检索正确的全局配置文件部分。 反过来，支持对象会向邮件服务返回指向此全局配置文件节的指针。 
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)

