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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d8caa503e557d35e259db743505d39ea4809dbfd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437649"
---
# <a name="itnefencoderecips"></a>ITnef::EncodeRecips

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件收件人表的视图编码为Transport-Neutral封装格式 (TNEF) 流。
  
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
  
> [in]指向视图已编码的收件人表的指针。 _lpRecipientTable_ 参数可以是 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
## <a name="remarks"></a>备注

传输提供程序、邮件存储提供程序和网关调用 **ITnef：：EncodeRecips** 方法来对特定的收件人表视图执行 TNEF 编码。 TNEF 编码很有用，例如，如果提供程序或网关需要收件人表的特定列集、排序顺序或限制。 
  
提供程序或网关传递表视图以在  _lpRecipientTable_ 参数中编码。 TNEF 实现使用给定列集、排序顺序、限制和位置对给定视图的收件人表进行编码。 如果提供程序或网关在  _lpRecipientTable_ 中传递 NULL，则 TNEF 从使用 [IMessage：：GetRecipientTable](imessage-getrecipienttable.md) 方法编码的邮件获取收件人表，然后使用表的当前设置将表的每一行处理到 TNEF 流中。 
  
因此，在 _lpRecipientTable_ 中调用 NULL 的 **EncodeRecips** 会编码所有邮件收件人，并且等效于在其 _ulFlags_ 参数中调用具有 TNEF_PROP_INCLUDE 标志的 [ITnef：：AddProps](itnef-addprops.md)方法，以及其 _lpPropList_ 参数中的 **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性。 
  
请注意，除非要求对特定的收件人表视图进行编码，否则很少需要调用 **EncodeRecips。** 外消息系统几乎始终具有处理收件人列表所需的工具，这些收件人列表功能足够强大，足以满足对收件人列表进行编码的常见需求;因此，这些系统几乎永远不会需要 TNEF 来达到此目的。 
  
## <a name="see-also"></a>另请参阅



[IMessage::GetRecipientTable](imessage-getrecipienttable.md)
  
[ITnef::AddProps](itnef-addprops.md)
  
[PidTagMessageRecipients 规范属性](pidtagmessagerecipients-canonical-property.md)
  
[ITnef : IUnknown](itnefiunknown.md)

