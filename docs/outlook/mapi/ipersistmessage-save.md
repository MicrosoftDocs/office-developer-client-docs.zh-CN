---
title: IPersistMessageSave
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.Save
api_type:
- COM
ms.assetid: 17875c13-f55b-4538-ac6f-c020281c3175
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1a95989cea7ad5529eb73276b4c771e4900804b4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579898"
---
# <a name="ipersistmessagesave"></a>IPersistMessage::Save

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
将修订后的表单保存回其已加载或创建的邮件。
  
```cpp
HRESULT Save(
  LPMESSAGE pMessage,
  ULONG fSameAsLoad
);
```

## <a name="parameters"></a>参数

 _pMessage_
  
> [in]指向邮件的指针。
    
 _fSameAsLoad_
  
> [in]若要指示邮件指向_pMessage_是从中加载或创建; 窗体的邮件否则为返回 FALSE。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功保存表单。
    
## <a name="remarks"></a>注解

表单查看器调用**IPersistMessage::Save**方法将修订后的表单保存回其已加载或创建的邮件。 
  
 在窗体以[正常](normal-state.md)状态时应仅调用**保存**。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

未提交的已保存的更改;由呼叫者进行提交的更改。 从不对窗体的邮件，但属于**保存**呼叫期间的属性进行更改。 
  
如果_fSameAsLoad_设置为 TRUE，您可以将所做的更改保存到窗体的现有邮件。 如果_fSameAsLoad_设置为 FALSE，则必须向邮件所指的_pMessage_执行保存之前从原始邮件复制的所有属性。 使用原始消息的[IMAPIProp::CopyTo](imapiprop-copyto.md)方法复制的属性。 
  
复制的所有属性，都输入[NoScribble](noscribble-state.md)状态。 如果没有错误，则返回 S_OK。 从失败的操作，否则，返回错误。 
  
如果**保存**窗体处于普通之外的任何状态时调用，，返回 E_UNEXPECTED。 
  
有关保存存储对象的详细信息，请参阅[IPersistStorage](http://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx)方法的文档。 
  
## <a name="see-also"></a>另请参阅



[IPersistMessage : IUnknown](ipersistmessageiunknown.md)


[表单状态](form-states.md)

