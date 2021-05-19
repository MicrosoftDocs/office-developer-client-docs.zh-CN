---
title: IMAPIFormFactoryLockServer
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormFactory.LockServer
api_type:
- COM
ms.assetid: b9bd389a-6975-41a2-a2f4-e501312e434b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ab51b939651bc3c121f357545969d26832a19d19
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342138"
---
# <a name="imapiformfactorylockserver"></a>IMAPIFormFactory::LockServer

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将打开的表单服务器保留到内存中。
  
```cpp
HRESULT LockServer(
  ULONG ulFlags,
  ULONG fLockServer
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _fLockServer_
  
> [in] **如果为 true，** 则增加锁定计数;否则为 **false**。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
## <a name="remarks"></a>备注

表单查看器调用 **IMAPIFormFactory：：LockServer** 方法来将打开的表单服务器应用程序保持在内存中。 在频繁创建和释放表单时，将窗体服务器保留到内存中可提高性能。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

**IMAPIFormFactory：：LockServer** 方法与 [IClassFactory：：LockServer](https://msdn.microsoft.com/library/ms682332%28v=VS.85%29.aspx)方法非常相似。 实质上 **，IMAPIFormFactory：：LockServer** 方法维护其调用次数的计数;只要该计数大于 0，该方法就可防止从内存中卸载表单服务器。 可以使用 [CoLockObjectExternal](https://msdn.microsoft.com/library/ms680592%28VS.85%29.aspx) 函数来实现这一点。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormFactory : IUnknown](imapiformfactoryiunknown.md)

