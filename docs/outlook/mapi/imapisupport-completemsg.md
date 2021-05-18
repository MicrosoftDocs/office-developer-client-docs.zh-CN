---
title: IMAPISupportCompleteMsg
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.CompleteMsg
api_type:
- COM
ms.assetid: e7932433-abe0-4341-95e0-91b37c848145
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e8c52d71ee47966be09c6c0806eceafae0c5ff5b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411188"
---
# <a name="imapisupportcompletemsg"></a>IMAPISupport::CompleteMsg

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对邮件执行后置处理。 
  
```cpp
HRESULT CompleteMsg(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> [in]保留;必须为零。
    
 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向要处理的邮件的条目标识符的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 后置处理成功。
    
## <a name="remarks"></a>备注

**IMAPISupport：：CompleteMsg** 方法针对邮件存储提供程序支持对象实现，并且仅由与传输提供程序紧密耦合的邮件存储提供程序调用。 紧密耦合存储提供程序调用 **IMAPISupport：：CompleteMsg** 以指示 MAPI 后台处理程序对消息进行后处理。 
  
## <a name="notes-to-callers"></a>给调用方的说明

只有在与传输提供程序紧密结合时，才能调用 **CompleteMsg，** 才能处理邮件的所有收件人，并且存在下列条件之一： 
  
- 邮件已预处理。
    
- 邮件需要 MAPI 后台处理程序进行后处理。
    
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

