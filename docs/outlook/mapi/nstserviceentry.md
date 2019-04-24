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
  
MAPI 存储提供程序的邮件服务入口点函数, 用于将基于 PST 的本地存储包装为 NST 存储。 
  
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

 **NSTServiceEntry**使用**[MSGSERVICEENTRY](msgserviceentry.md)** 函数原型。 有关其参数的信息, 请参阅**[MSGSERVICEENTRY](msgserviceentry.md)**。 
  
## <a name="return-values"></a>返回值

有关返回值的信息, 请参阅**[MSGSERVICEENTRY](msgserviceentry.md)**。 
  
## <a name="remarks"></a>注解

使用**[GetProcAddress](https://msdn.microsoft.com/library/ms683212.aspx)** 在 msmapi32 中查找此函数的地址时, 请将 "NSTServiceEntry" 指定为过程名称。 
  
若要使用复制 API, MAPI 存储提供程序必须先通过调用**[NSTServiceEntry](nstserviceentry.md)** 打开和包装基于 PST 的本地存储。 然后, 提供程序可以使用 API 的主要接口**[IOSTX](iostxiunknown.md)** 和**[IPSTX](ipstxiunknown.md)** 来执行复制。 
  
以下注释适用于 NST 存储:
  
- 在实现使用**NSTServiceEntry**的 MAPI 提供程序时, 请勿在全局配置文件部分中存储任何信息。 全局配置文件部分由多个提供程序共享, 并且可以覆盖存储在此配置文件中的数据。 
    
- 在保存时, 只有具有现有修改时间戳的项目会更新其图章。 
    
- 冲突-在保存项目时不会自动进行检查。
    
-  保存项目时不会进行重复检测。 
    
-  附加了表示服务器的缓存版本的文件。NST. 
    
- 若要获取指向 "全局配置文件" 部分的指针, 邮件服务将使用以下定义的**pbNSTGlobalProfileSectionGuid**在支持对象中调用**[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)** : 
    
  ```
  #define  pbNSTGlobalProfileSectionGuid "\x85\xED\x14\x23\x9D\xF7\x42\x66\x8B\xF2\xFB\xD4\xA5\x21\x29\x41"
  ```

- 在这种情况下, 邮件服务的支持对象应确保**IMAPISupport:: OpenProfileSection**返回由 "默认配置文件" 部分中的**[PR_SERVICE_UID](pidtagserviceuid-canonical-property.md)** 属性标识的 "配置文件" 部分。 若要获取此配置文件部分, 支持对象可以打开默认的配置文件部分, 检索**PR_SERVICE_UID**, 并将结果传递给**IMAPISupport:: OpenProfileSection**以检索正确的全局配置文件部分。 支持对象反过来又将指向此全局配置文件部分的指针返回到邮件服务。 
    
## <a name="see-also"></a>另请参阅



[关于复制 API](about-the-replication-api.md)

