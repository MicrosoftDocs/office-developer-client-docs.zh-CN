---
title: IAddrBookSetSearchPath
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.SetSearchPath
api_type:
- COM
ms.assetid: fbff82de-77d3-411e-a30c-a37cefdd92fc
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1d486344ab20ef49488dbb911f3dd7000d64942e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571757"
---
# <a name="iaddrbooksetsearchpath"></a>IAddrBook::SetSearchPath

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
设置中的配置文件的名称解析过程使用新的搜索路径。 
  
```cpp
HRESULT SetSearchPath(
  ULONG ulFlags,
  LPSRowSet lpSearchPath
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpSearchPath_
  
> [in]指向用于保留搜索路径[SRowSet](srowset.md)结构的指针。 对于每个**aRow**成员**SRowSet**中的第一个属性必须**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置的搜索路径。
    
MAPI_E_MISSING_REQUIRED_COLUMN 
  
> 一个**SRowSet**结构中所述的容器不包括其**PR_ENTRYID**属性。 
    
## <a name="remarks"></a>注解

客户端和服务提供商调用**SetSearchPath**方法以保存所做的用于将名称解析使用[IAddrBook::ResolveName](iaddrbook-resolvename.md)方法的容器搜索顺序的更改。 会话的实例之间保存搜索路径。 
  
客户端和提供程序不需要调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法进行永久搜索路径更改。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook::GetDefaultDir](iaddrbook-getdefaultdir.md)
  
[IAddrBook::GetPAB](iaddrbook-getpab.md)
  
[IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)
  
[PidTagContainerFlags 规范属性](pidtagcontainerflags-canonical-property.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

