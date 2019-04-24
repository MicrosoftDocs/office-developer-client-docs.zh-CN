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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348655"
---
# <a name="itnefencoderecips"></a>ITnef::EncodeRecips

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在邮件的传输中性封装格式 (TNEF) 数据流中对邮件的收件人表的视图进行编码。
  
```cpp
HRESULT EncodeRecips(
  ULONG ulFlags,
  LPMAPITABLE lpRecipientTable
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
 _lpRecipientTable_
  
> 实时指向对其对视图进行编码的收件人表的指针。 _lpRecipientTable_参数可以为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的一个或一些值。
    
## <a name="remarks"></a>注解

传输提供程序、邮件存储提供程序和网关调用**ITnef:: EncodeRecips**方法来执行特定收件人表视图的 TNEF 编码。 例如, 如果提供程序或网关需要特定的列集、排序顺序或对收件人表的限制, 则 TNEF 编码非常有用。 
  
提供程序或网关传递要在_lpRecipientTable_参数中进行编码的表视图。 TNEF 实现使用给定的列集、排序顺序、限制和位置对收件人表使用给定的视图进行编码。 如果提供程序或网关在_lpRecipientTable_中传递了 NULL, TNEF 将从使用[IMessage:: GetRecipientTable](imessage-getrecipienttable.md)方法进行编码的邮件中获取收件人表, 并使用将表中的每一行处理到 TNEF 流中。表的当前设置。 
  
因此, 使用_lpRecipientTable_中的 NULL 调用**EncodeRecips**将对所有邮件收件人进行编码, 并且相当于在其_TNEF_PROP_INCLUDE_参数和 ulFlags 中调用[ITnef:: AddProps](itnef-addprops.md)方法和 PR_ 标记。 **MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性在其_lpPropList_参数中。 
  
请注意, 如果需要对特定收件人表视图进行编码, 则几乎不需要调用**EncodeRecips** 。 外部邮件系统几乎总是有处理可满足编码收件人列表的常见需求的收件人列表的功能;因此, 这些系统几乎不需要 TNEF 即可实现此目的。 
  
## <a name="see-also"></a>另请参阅



[IMessage::GetRecipientTable](imessage-getrecipienttable.md)
  
[ITnef::AddProps](itnef-addprops.md)
  
[PidTagMessageRecipients 规范属性](pidtagmessagerecipients-canonical-property.md)
  
[ITnef : IUnknown](itnefiunknown.md)

