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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8611249207811446ae47f056486ec498bf1e7eab
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426203"
---
# <a name="iaddrbooksetsearchpath"></a>IAddrBook::SetSearchPath

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在用于名称解析过程的配置文件中设置新的搜索路径。 
  
```cpp
HRESULT SetSearchPath(
  ULONG ulFlags,
  LPSRowSet lpSearchPath
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
 _lpSearchPath_
  
> 实时指向用于保存搜索路径的[SRowSet](srowset.md)结构的指针。 **SRowSet**中每个**aRow**成员的第一个属性必须为**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 成功设置了搜索路径。
    
MAPI_E_MISSING_REQUIRED_COLUMN 
  
> **SRowSet**结构中所述的一个容器不包含其**PR_ENTRYID**属性。 
    
## <a name="remarks"></a>说明

客户端和服务提供程序调用**SetSearchPath**方法, 以保存对用于使用[IAddrBook:: ResolveName](iaddrbook-resolvename.md)方法解析名称的容器搜索顺序所做的更改。 在会话实例之间保存搜索路径。 
  
客户端和提供程序无需调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法以使搜索路径更改永久。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook::GetDefaultDir](iaddrbook-getdefaultdir.md)
  
[IAddrBook::GetPAB](iaddrbook-getpab.md)
  
[IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)
  
[PidTagContainerFlags 规范属性](pidtagcontainerflags-canonical-property.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

