---
title: IMAPIViewAdviseSinkOnShutdown
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewAdviseSink.OnShutdown
api_type:
- COM
ms.assetid: c9c3aecf-5e4b-407a-8ea1-6211b4c6e0a5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2a09731dbd0ba2c5d6c1055a7c5ed11097c5ef27
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775731"
---
# <a name="imapiviewadvisesinkonshutdown"></a>IMAPIViewAdviseSink::OnShutdown

  
  
**适用于**： Outlook 
  
通知表单查看器正在关闭窗体。
  
```cpp
HRESULT OnShutdown( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 通知已成功。
    
## <a name="remarks"></a>说明

有关窗体通知的详细信息，请参阅[发送和接收窗体通知](sending-and-receiving-form-notifications.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)

