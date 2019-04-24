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
  
将修订后的表单重新保存到从中加载或创建该表单的邮件中。
  
```cpp
HRESULT Save(
  LPMESSAGE pMessage,
  ULONG fSameAsLoad
);
```

## <a name="parameters"></a>参数

 _pMessage_
  
> 实时指向邮件的指针。
    
 _fSameAsLoad_
  
> 实时如果为 TRUE, 则指示由_pMessage_指向的邮件是从中加载或创建表单的邮件;否则为 FALSE。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 表单已成功保存。
    
## <a name="remarks"></a>注解

表单查看者调用**IPersistMessage:: save**方法将修订后的表单重新保存到从中加载或创建该表单的邮件中。 
  
 仅当表单处于[正常](normal-state.md)状态时才应调用**Save** 。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

不提交保存的更改;由调用方来提交更改。 永远不要对属于窗体消息的属性进行更改, 除非在**保存**调用过程中。 
  
如果将_fSameAsLoad_设置为 TRUE, 则可以保存对窗体的现有邮件所做的更改。 如果将_fSameAsLoad_设置为 FALSE, 则在执行保存之前, 必须将原始邮件中的所有属性复制到_pMessage_指向的邮件中。 使用原始邮件的[IMAPIProp:: CopyTo](imapiprop-copyto.md)方法复制属性。 
  
复制完所有属性后, 请输入[NoScribble](noscribble-state.md)状态。 如果没有出现任何错误, 则返回 S_OK。 否则, 返回失败操作中的错误。 
  
如果在窗体处于 "正常" 之外的任何状态时调用**Save** , 则返回 E_UNEXPECTED。 
  
有关保存存储对象的详细信息, 请参阅有关[IPersistStorage](https://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx)方法的文档。 
  
## <a name="see-also"></a>另请参阅



[IPersistMessage : IUnknown](ipersistmessageiunknown.md)


[表单状态](form-states.md)

