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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ab51b939651bc3c121f357545969d26832a19d19
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389055"
---
# <a name="imapiformfactorylockserver"></a>IMAPIFormFactory::LockServer

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在内存中保留的打开的窗体服务器。
  
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
  
> [in]**true**递增锁数;否则为**false**。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
## <a name="remarks"></a>说明

表单查看器调用**IMAPIFormFactory::LockServer**方法可在内存中保留的打开的窗体服务器应用程序。 在内存中保留表单服务器能够改善性能时经常创建和发布表单。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

非常类似于[IClassFactory::LockServer](https://msdn.microsoft.com/library/ms682332%28v=VS.85%29.aspx)方法**IMAPIFormFactory::LockServer**方法。 实际上， **IMAPIFormFactory::LockServer**方法维护已调用的次数计数;只要该数量大于 0，该方法将防止从内存中卸载表单服务器。 您可以使用[CoLockObjectExternal](https://msdn.microsoft.com/library/ms680592%28VS.85%29.aspx)函数来实现这。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFormFactory : IUnknown](imapiformfactoryiunknown.md)

