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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b43c1b96130052a05ac390f10f545a66fe72b7fe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428520"
---
# <a name="imapiviewadvisesinkonshutdown"></a>IMAPIViewAdviseSink::OnShutdown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通知表单查看器正在关闭表单。
  
```cpp
HRESULT OnShutdown( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 通知成功。
    
## <a name="remarks"></a>备注

有关表单通知详细信息，请参阅 [发送和接收表单通知](sending-and-receiving-form-notifications.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)

