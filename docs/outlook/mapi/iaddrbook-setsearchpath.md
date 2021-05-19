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
  
设置配置文件中用于名称解析过程的新搜索路径。 
  
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
  
> [in]指向用于保留 [搜索路径的 SRowSet](srowset.md) 结构的指针。 **SRowSet** 中每个 **aRow** 成员的第一个属性必须PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功设置搜索路径。
    
MAPI_E_MISSING_REQUIRED_COLUMN 
  
> **SRowSet** 结构中描述的容器之一 **不包括其** PR_ENTRYID 属性。 
    
## <a name="remarks"></a>备注

客户端和服务提供商调用 **SetSearchPath** 方法来保存对容器搜索顺序所做的更改，该搜索顺序用于使用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md) 方法解析名称。 搜索路径在会话的实例之间保存。 
  
客户端和提供程序不需要调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法来永久更改搜索路径。 
  
## <a name="see-also"></a>另请参阅



[IAddrBook::GetDefaultDir](iaddrbook-getdefaultdir.md)
  
[IAddrBook::GetPAB](iaddrbook-getpab.md)
  
[IAddrBook::GetSearchPath](iaddrbook-getsearchpath.md)
  
[PidTagContainerFlags 规范属性](pidtagcontainerflags-canonical-property.md)
  
[IAddrBook : IMAPIProp](iaddrbookimapiprop.md)

