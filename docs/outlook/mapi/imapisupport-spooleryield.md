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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d90f502e2cd7f97ac273ebecedbd0363097b1d60
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584952"
---
# <a name="imapisupportspooleryield"></a>IMAPISupport::SpoolerYield

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
到 MAPI 后台处理程序提供的 CPU 的控件，以便它可以执行它认为需要的任何任务。
  
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
  
> 传输提供程序成功发布 CPU。
    
MAPI_W_CANCEL_MESSAGE 
  
> 指示要停止邮件传递到尚未收到任何收件人的传输提供程序。
    
## <a name="remarks"></a>注解

对于传输提供程序支持对象实现**IMAPISupport::SpoolerYield**方法。 传输提供程序调用**SpoolerYield**以允许 MAPI 后台处理程序完成任何所需的处理。 
  
## <a name="notes-to-callers"></a>给调用方的说明

执行可暂停的冗长操作时，请调用**SpoolerYield** 。 这样，前景过程较长的操作，如传递到大型收件人列表跨繁忙的网络中运行的应用程序。 
  
如果**SpoolerYield**返回与 MAPI_W_CANCEL_MESSAGE，MAPI 后台处理程序已确定无法再发送邮件。 如果可能对您调用进程和退出，返回 MAPI_E_USER_CANCEL。 
  
有关转交给 MAPI 后台处理程序的详细信息，请参阅[使用 MAPI 后台处理程序的交互](interacting-with-the-mapi-spooler.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

