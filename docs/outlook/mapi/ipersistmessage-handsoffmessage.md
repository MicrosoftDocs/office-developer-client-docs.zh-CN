---
title: IPersistMessageHandsOffMessage
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.HandsOffMessage
api_type:
- COM
ms.assetid: 0e56b21d-0a2e-4fe6-83f4-c9daab2f3055
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 2cd4c86dc45bca85632a3fadc9023c9ad25cfa37
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583027"
---
# <a name="ipersistmessagehandsoffmessage"></a>IPersistMessage::HandsOffMessage

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
使窗体释放其当前邮件。
  
```cpp
HRESULT HandsOffMessage( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件已成功发布。
    
## <a name="remarks"></a>注解

窗体过渡到两个 HandsOff 状态：
  
- [HandsOffAfterSave](handsoffaftersave-state.md)
    
- [HandsOffFromNormal](handsofffromnormal-state.md)
    
当窗体处于以下状态之一时，它是被永久存储的过程。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

当窗体处于[普通](normal-state.md)或[NoScribble](noscribble-state.md)状态时，窗体查看器调用**IPersistMessage::HandsOffMessage**方法时，对每封邮件以递归方式调用**HandsOffMessage**嵌入在当前消息和[IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d.aspx)当前消息中嵌入在每个 OLE 对象的方法。 然后释放所有嵌入的邮件当前消息和 OLE 对象。 如果您的窗体处于正常状态转换为 HandsOffFromNormal 状态。 如果您的窗体 NoScribble 状态，转换为 HandsOffAfterSave 状态。 成功转换之后, 调用消息的[IUnknown::Release](http://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx)方法，并返回 S_OK。 
  
当窗体查看器调用**HandsOffMessage** HandsOff 状态的某一窗体时，返回 E_UNEXPECTED。 
  
有关窗体的不同状态的详细信息，请参阅[窗体状态](form-states.md)。 有关如何使用存储对象的 HandsOff 状态的详细信息，请参阅[IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d.aspx)方法。 
  
## <a name="see-also"></a>另请参阅



[IPersistMessage : IUnknown](ipersistmessageiunknown.md)


[表单状态](form-states.md)

