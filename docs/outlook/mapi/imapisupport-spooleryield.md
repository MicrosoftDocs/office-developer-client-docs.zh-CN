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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409907"
---
# <a name="imapisupportspooleryield"></a>IMAPISupport::SpoolerYield

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将 CPU 控制权授予 MAPI 后台处理程序，以便它可以执行认为必要的任何任务。
  
```cpp
HRESULT SpoolerYield(
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 传输提供程序已成功释放 CPU。
    
MAPI_W_CANCEL_MESSAGE 
  
> 指示传输提供程序停止向尚未收到邮件的任何收件人传递邮件。
    
## <a name="remarks"></a>备注

**为传输提供程序支持对象实现 IMAPISupport：：SpoolerYield** 方法。 传输提供程序调用 **SpoolerYield** 以允许 MAPI 后台处理程序完成任何必要的处理。 
  
## <a name="notes-to-callers"></a>给调用方的说明

执行可以暂停的冗长操作时，请调用 **SpoolerYield。** 这允许前台应用程序在长时间操作（如通过繁忙网络传递至大型收件人列表）期间运行。 
  
如果 **SpoolerYield** 返回 MAPI_W_CANCEL_MESSAGE，则 MAPI 后台处理程序已确定不再发送该邮件。 如果MAPI_E_USER_CANCEL，请返回到调用过程并退出。 
  
有关向 MAPI 后台处理程序提供收益的信息，请参阅与 [MAPI 后台处理程序交互](interacting-with-the-mapi-spooler.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

