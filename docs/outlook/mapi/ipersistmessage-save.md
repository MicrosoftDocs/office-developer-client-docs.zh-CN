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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fa3f1d6339000fcc53e0ee22dafec4362e65ca7f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309616"
---
# <a name="ipersistmessagesave"></a>IPersistMessage::Save

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将修改后的窗体保存回已加载或创建该窗体的邮件。
  
```cpp
HRESULT Save(
  LPMESSAGE pMessage,
  ULONG fSameAsLoad
);
```

## <a name="parameters"></a>参数

 _pMessage_
  
> [in]指向消息的指针。
    
 _fSameAsLoad_
  
> [in]若要指示  _pMessage_ 指向的邮件是加载或创建表单的邮件，则其为 TRUE;否则为 FALSE。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功保存表单。
    
## <a name="remarks"></a>备注

表单查看器调用 **IPersistMessage：：Save** 方法，将修改后的表单保存回加载或创建表单的邮件。 
  
 **只有在** 表单的状态为"正常"时，才应 [调用 Save。](normal-state.md) 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

不提交保存的更改;由调用方提交更改。 从不对属于窗体邮件的属性进行更改，Save 调用 **期间** 除外。 
  
如果  _fSameAsLoad_ 设置为 TRUE，您可以将更改保存到表单的现有邮件中。 如果  _fSameAsLoad_ 设置为 FALSE，则在执行保存之前，必须将原始邮件的所有属性复制到  _pMessage_ 指向的邮件中。 使用原始邮件的 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法复制属性。 
  
复制所有属性后，输入 [NoScribble](noscribble-state.md) 状态。 如果未发生错误，则返回S_OK。 否则，从失败操作返回错误。 
  
如果 **当窗体** 位于除 Normal 外的任何状态时调用 Save，则返回E_UNEXPECTED。 
  
有关保存存储对象的信息，请参阅 [有关 IPersistStorage](https://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx) 方法的文档。 
  
## <a name="see-also"></a>另请参阅



[IPersistMessage : IUnknown](ipersistmessageiunknown.md)


[表单状态](form-states.md)

