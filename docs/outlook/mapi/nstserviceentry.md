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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392415"
---
# <a name="nstserviceentry"></a>NSTServiceEntry

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
消息服务入口点函数 MAPI 的存储提供程序作为 NST 存储环绕基于 PST 的本地存储区。 
  
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

 **NSTServiceEntry**使用**[MSGSERVICEENTRY](msgserviceentry.md)** 函数原型。 其参数信息，请参阅**[MSGSERVICEENTRY](msgserviceentry.md)**。 
  
## <a name="return-values"></a>返回值

返回值的信息，请参阅**[MSGSERVICEENTRY](msgserviceentry.md)**。 
  
## <a name="remarks"></a>说明

当使用**[GetProcAddress](https://msdn.microsoft.com/library/ms683212.aspx)** 查找 msmapi32.dll 中此函数的地址，指定"NSTServiceEntry"作为过程名称。 
  
若要使用复制 API，MAPI 存储提供程序必须首先打开并通过调用**[NSTServiceEntry](nstserviceentry.md)** 环绕基于 PST 的本地存储区。 提供程序然后可以使用 API、 **[IOSTX](iostxiunknown.md)** 和**[IPSTX](ipstxiunknown.md)** 的主要接口执行复制。 
  
下列说明适用于 NST 存储：
  
- 实现使用**NSTServiceEntry**MAPI 提供程序时，不要在全局配置文件部分中存储的任何信息。 由多个提供程序共享全局配置文件部分，可以覆盖此配置文件中存储的数据。 
    
- 仅当项目具有现有的修改时间戳获取其戳更新时对其进行保存。 
    
- 冲突检查不会发生自动保存项目时。
    
-  保存项目时，就不会发生重复检测。 
    
-  附加表示缓存的版本的服务器的文件。NST。 
    
- 若要获得一个指向全局配置文件部分，消息服务时，可调用**[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)** 支持对象使用**pbNSTGlobalProfileSectionGuid** ，按如下： 
    
  ```
  #define  pbNSTGlobalProfileSectionGuid "\x85\xED\x14\x23\x9D\xF7\x42\x66\x8B\xF2\xFB\xD4\xA5\x21\x29\x41"
  ```

- 在这种情况下，消息服务的支持对象应确保**IMAPISupport::OpenProfileSection**返回默认配置文件一节中的**[PR_SERVICE_UID](pidtagserviceuid-canonical-property.md)** 属性由配置文件一节。 若要获取此配置文件一节，支持对象可以打开默认配置文件部分，检索**PR_SERVICE_UID**，并将结果传递给**IMAPISupport::OpenProfileSection**检索正确的全局配置文件部分。 支持对象又返回到邮件服务全局配置文件本节指针。 
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)

