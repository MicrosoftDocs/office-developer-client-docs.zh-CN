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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406169"
---
# <a name="imapiviewadvisesinkonprint"></a>IMAPIViewAdviseSink::OnPrint

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通知窗体查看者窗体的打印状态。
  
```cpp
HRESULT OnPrint(
ULONG dwPageNumber,
HRESULT hrStatus
);
```

## <a name="parameters"></a>参数

 _dwPageNumber_
  
> [in]打印的最后一页的页码。
    
 _hrStatus_
  
> [in]一个 HRESULT 值，指示打印作业的状态。 可能的值是：
    
S_FALSE 
  
> 打印作业已成功完成。
    
S_OK 
  
> 打印作业正在进行中。
    
FAILED 
  
> 打印作业由于失败而终止。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知成功。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消"按钮来取消操作。 
    
## <a name="remarks"></a>备注

Form 对象在打印时调用 **IMAPIViewAdviseSink：：OnPrint** 方法，以通知查看者打印进度。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果打印作业涉及多个页面，您可以在打印每个页面后调用 **OnPrint。** 将  _dwPageNumber_ 设置为当前正在打印的页面，将  _hrStatus_ 设置为S_OK。 打印作业完成后，调用 **OnPrint，** 将  _dwPageNumber_ 设置为打印的最后一页，  _将 hrStatus_ 设置为 S_FALSE。 
  
有关表单通知详细信息，请参阅 [发送和接收表单通知](sending-and-receiving-form-notifications.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)

