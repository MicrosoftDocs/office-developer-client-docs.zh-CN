---
title: IMAPIViewAdviseSinkOnSaved
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIViewAdviseSink.OnSaved
api_type:
- COM
ms.assetid: c327e31a-7b62-4e21-9b69-b27442f1eaca
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2ec78331fd013777f001d39bd7e978a67abb5342
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407604"
---
# <a name="imapiviewadvisesinkonsaved"></a>IMAPIViewAdviseSink::OnSaved

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通知表单查看器表单中的当前邮件已保存。
  
```cpp
HRESULT OnSaved( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    
## <a name="remarks"></a>说明

窗体对象在成功保存窗体中的当前邮件后调用**IMAPIViewAdviseSink:: OnSaved**方法。 这样做将允许查看者更新其窗口, 以反映对邮件的更改。 
  
有关表单通知的详细信息, 请参阅[发送和接收表单通知](sending-and-receiving-form-notifications.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIViewAdviseSink : IUnknown](imapiviewadvisesinkiunknown.md)

