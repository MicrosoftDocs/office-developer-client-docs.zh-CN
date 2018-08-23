---
title: ITnefEncodeRecips
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef.EncodeRecips
api_type:
- COM
ms.assetid: b3ce4b0e-4f48-4a7e-a30c-c4754bccb12c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6324dcc567aee48f190f8568c6c94b5ee87c731f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584562"
---
# <a name="itnefencoderecips"></a>ITnef::EncodeRecips

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
将编码消息的收件人的表中的邮件传输中性封装格式 (TNEF) 数据流的视图。
  
```cpp
HRESULT EncodeRecips(
  ULONG ulFlags,
  LPMAPITABLE lpRecipientTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _lpRecipientTable_
  
> [in]指向收件人为其编码视图的表的指针。 _LpRecipientTable_参数可以是 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期的值。
    
## <a name="remarks"></a>注解

传输提供程序、 消息存储提供程序，和网关呼叫**ITnef::EncodeRecips**方法执行 TNEF 编码特定收件人表视图。 TNEF 编码很有用，例如，如果提供程序或网关所需的特定列集、 排序顺序或限制的收件人的表。 
  
提供程序或网关传递编码_lpRecipientTable_参数中的表视图。 TNEF 实现进行编码收件人表与给定视图中，使用给定的列集、 排序顺序、 限制和位置。 如果提供程序或网关传入_lpRecipientTable_NULL，TNEF 从邮件正在编码使用[IMessage::GetRecipientTable](imessage-getrecipienttable.md)方法，获取收件人的表和通过使用到 TNEF 流处理每个表的行表的当前设置。 
  
_LpRecipientTable_中调用**EncodeRecips**具有 NULL 因此将编码所有邮件的收件人，并等效于调用其_ulFlags_参数和**PR_ TNEF_PROP_INCLUDE 标志[ITnef::AddProps](itnef-addprops.md)方法MESSAGE_RECIPIENTS**中其_lpPropList_参数 ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。 
  
请注意，很少需要调用**EncodeRecips** ，除非要求进行编码特定收件人表视图。 外部邮件系统始终具有用于处理了足以处理的编码收件人列表; 常见需求的收件人列表功能因此，这些系统几乎从不需要 TNEF 实现此目的。 
  
## <a name="see-also"></a>另请参阅



[IMessage::GetRecipientTable](imessage-getrecipienttable.md)
  
[ITnef::AddProps](itnef-addprops.md)
  
[PidTagMessageRecipients 规范属性](pidtagmessagerecipients-canonical-property.md)
  
[ITnef : IUnknown](itnefiunknown.md)

