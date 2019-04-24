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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ef9f506c1a95fec86c7f092b0299198e6149d3ba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320151"
---
# <a name="iproxystoreobjectunwrapnoref"></a>IProxyStoreObject::UnwrapNoRef

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
获取一个指向已解开的 Internet 邮件访问协议 (IMAP) 存储对象的指针, 该对象提供对基础个人文件夹文件 (PST) 的访问权限, 而无需调用同步和下载项目。
  
```cpp
HRESULT IProxyStoreObject::UnwrapNoRef (     LPVOID *ppvObject ); 
```

## <a name="parameters"></a>参数

 _ppvObject_
  
> 排除指向已解包的[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)存储对象的指针。 
    
## <a name="return-values"></a>返回值

S_OK
  
- 调用成功, 并且在_ppvObject_中返回了指向已解包接口的指针。
    
## <a name="remarks"></a>注解

如果不先解包, 则访问存储区中的邮件可能会强制尝试下载整个邮件的同步。 使用已解开的存储允许在不触发下载的情况下访问当前状态的邮件。
  
由于**UnwrapNoRef**不会将此新指针的引用计数增加到已解包的 store 对象, 因此在成功调用**UnwrapNoRef**后, 应调用[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28v=VS.85%29.aspx)来维护引用计数。 
  
## <a name="see-also"></a>另请参阅



[IProxyStoreObject](iproxystoreobject.md)

