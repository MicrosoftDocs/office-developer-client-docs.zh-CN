---
title: IMAPISupportSpoolerYield
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.SpoolerYield
api_type:
- COM
ms.assetid: f5c6ba8f-4ef5-4d60-b4e6-5b9160ec4e99
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f6cdebf82d8b84ada3d029865867c5192af90b0d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329035"
---
# <a name="imapisupportspooleryield"></a>IMAPISupport::SpoolerYield

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将 CPU 的控制提供给 MAPI 后台处理程序, 以便它可以执行必要的任何任务。
  
```cpp
HRESULT SpoolerYield(
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 保留必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 传输提供程序已成功释放 CPU。
    
MAPI_W_CANCEL_MESSAGE 
  
> 指示传输提供程序停止将邮件传递给尚未收到邮件的任何收件人。
    
## <a name="remarks"></a>注解

为传输提供程序支持对象实现了**IMAPISupport:: SpoolerYield**方法。 传输提供程序调用**SpoolerYield**以允许 MAPI 后台处理程序完成所需的任何处理。 
  
## <a name="notes-to-callers"></a>给调用方的说明

当执行可暂停的长操作时, 请调用**SpoolerYield** 。 这允许前台应用程序在长操作期间运行, 例如, 通过繁忙网络传递到大型收件人列表。 
  
如果**SpoolerYield**返回 MAPI_W_CANCEL_MESSAGE, 则 MAPI 后台处理程序已确定应不再发送该邮件。 将 MAPI_E_USER_CANCEL 返回到您的呼叫进程并退出 (如果可能)。 
  
有关向 mapi 后台处理程序生成的详细信息, 请参阅[与 mapi 后台处理程序交互](interacting-with-the-mapi-spooler.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

