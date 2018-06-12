---
title: IProxyStoreObjectUnwrapNoRef
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProxyStoreObject.UnwrapNoRef
api_type:
- COM
ms.assetid: 1122b6e0-e7e1-e68a-e090-435777343d04
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7c6c763e918947c423c5dae283b0d4ab2f880616
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776020"
---
# <a name="iproxystoreobjectunwrapnoref"></a>IProxyStoreObject::UnwrapNoRef

  
  
**适用于**： Outlook 
  
获取一个指向一个解包的 Internet 消息访问协议 (IMAP) 存储对象，提供对基础个人文件夹文件 (PST) 的访问而不调用同步和下载项目。
  
```cpp
HRESULT IProxyStoreObject::UnwrapNoRef (     LPVOID *ppvObject ); 
```

## <a name="parameters"></a>参数

 _ppvObject_
  
> [输出]指向[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)解包的存储对象。 
    
## <a name="return-values"></a>返回值

S_OK
  
- 调用成功，并且已在_ppvObject_返回指向解包接口的指针。
    
## <a name="remarks"></a>备注

第一个过程 IMAP 存储区，没有访问存储区中的一条消息可以强制尝试下载整个邮件的同步。 使用解包的存储而不会触发下载允许访问当前状态的消息。
  
由于**UnwrapNoRef**不会增加到解包的存储对象，此新指针的引用计数成功调用**UnwrapNoRef**后，您应调用[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28v=VS.85%29.aspx)维护引用计数。 
  
## <a name="see-also"></a>另请参阅



[IProxyStoreObject](iproxystoreobject.md)

