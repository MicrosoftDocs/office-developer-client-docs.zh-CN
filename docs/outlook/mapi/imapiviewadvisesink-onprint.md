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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: bf3eee43a70fbc4abf32b60379fc7b191bd9d513
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775727"
---
# <a name="imapiviewadvisesinkonprint"></a>IMAPIViewAdviseSink::OnPrint

  
  
**适用于**： Outlook 
  
通知窗体的打印状态的表单查看器。
  
```cpp
HRESULT OnPrint(
ULONG dwPageNumber,
HRESULT hrStatus
);
```

## <a name="parameters"></a>参数

 _dwPageNumber_
  
> [in]数的最后一页打印。
    
 _hrStatus_
  
> [in]指示打印作业的状态的 HRESULT 值。 可能的值是：
    
S_FALSE 
  
> 打印作业已成功完成。
    
S_OK 
  
> 打印作业正在运行。
    
失败 
  
> 打印作业已终止由于失败而导致。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功。
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击对话框中的取消按钮。 
    
## <a name="remarks"></a>说明

表单对象调用**IMAPIViewAdviseSink::OnPrint**方法时打印，告知打印进度的查看器。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果打印作业涉及多个页面，则可以呼叫**OnPrint**后每一页打印。 将_dwPageNumber_到当前打印页面和_hrStatus_设置为返回 S_OK。 打印作业完成时，呼叫与_dwPageNumber_ **OnPrint**设置到最后一页打印和_hrStatus_将设置为 S_FALSE。 
  
有关窗体通知的详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)

