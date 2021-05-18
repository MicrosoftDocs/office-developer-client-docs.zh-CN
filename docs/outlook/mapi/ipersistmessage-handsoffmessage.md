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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 84f0ca88403980ff9ea1c91821a8a3d7edae74fa
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309714"
---
# <a name="ipersistmessagehandsoffmessage"></a>IPersistMessage::HandsOffMessage

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
使表单释放其当前邮件。
  
```cpp
HRESULT HandsOffMessage( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件已成功释放。
    
## <a name="remarks"></a>备注

表单转换为两个 HandsOff 状态：
  
- [HandsOffAfterSave](handsoffaftersave-state.md)
    
- [HandsOffFromNormal](handsofffromnormal-state.md)
    
当表单位于上述任一状态时，表单正在永久存储。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

当表单位于 Normal 或 [NoScribble](noscribble-state.md)状态时，当表单调用 **IPersistMessage：：HandsOffMessage** 方法时，以递归方式对嵌入在当前邮件中的每封邮件调用 **HandsOffMessage，** 并在当前邮件中嵌入的每个 OLE 对象上递归调用 [](normal-state.md)[IPersistStorage：：HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d.aspx)方法。 然后释放当前邮件以及所有嵌入的邮件和 OLE 对象。 如果表单为"正常"状态，请转换为 HandsOffFromNormal 状态。 如果表单的状态为 NoScribble，请转换为 HandsOffAfterSave 状态。 成功转换后，调用邮件的 [IUnknown：：Release](https://msdn.microsoft.com/library/4b494c6f-f0ee-4c35-ae45-ed956f40dc7a%28Office.15%29.aspx) 方法并返回S_OK。 
  
当表单查看器在表单为任一 HandsOff 状态时调用 **HandsOffMessage** 时，返回E_UNEXPECTED。 
  
有关窗体的不同状态的信息，请参阅窗体 [状态](form-states.md)。 有关如何使用存储对象的 HandsOff 状态的信息，请参阅 [IPersistStorage：：HandsOffStorage](https://msdn.microsoft.com/library/1e5ef26f-d8e7-4fa6-bfc4-19dace35314d.aspx) 方法。 
  
## <a name="see-also"></a>另请参阅



[IPersistMessage : IUnknown](ipersistmessageiunknown.md)


[表单状态](form-states.md)

