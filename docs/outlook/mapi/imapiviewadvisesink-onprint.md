---
title: IMAPIViewAdviseSinkOnPrint
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewAdviseSink.OnPrint
api_type:
- COM
ms.assetid: d16219a0-268c-428d-9f02-4f06eb5b6d7d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e66315042f8b5cd5aff0e4aa076588c9f312376a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328782"
---
# <a name="imapiviewadvisesinkonprint"></a>IMAPIViewAdviseSink::OnPrint

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将表单的打印状态通知给表单查看器。
  
```cpp
HRESULT OnPrint(
ULONG dwPageNumber,
HRESULT hrStatus
);
```

## <a name="parameters"></a>参数

 _dwPageNumber_
  
> 实时打印的最后一页的编号。
    
 _hrStatus_
  
> 实时一个 HRESULT 值, 指示打印作业的状态。 可能的值是：
    
S_FALSE 
  
> 打印作业已成功完成。
    
S_OK 
  
> 正在进行打印作业。
    
未能 
  
> 打印作业因故障而终止。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功。
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击对话框中的 "取消" 按钮。 
    
## <a name="remarks"></a>注解

表单对象在打印时调用**IMAPIViewAdviseSink:: OnPrint**方法, 以通知查看器打印进度。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果打印作业涉及多个页面, 则可以在打印每个页面后调用**OnPrint** 。 将_dwPageNumber_设置为当前正在打印的页面, 并将_hrStatus_设置为 S_OK。 打印作业完成后, 调用**OnPrint** , 并将_dwPageNumber_设置为打印的最后一页, _hrStatus_设置为 S_FALSE。 
  
有关表单通知的详细信息, 请参阅[发送和接收表单通知](sending-and-receiving-form-notifications.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)

