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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331505"
---
# <a name="imapisupportcompletemsg"></a>IMAPISupport::CompleteMsg

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对邮件执行后处理。 
  
```cpp
HRESULT CompleteMsg(
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _ulFlags_
  
> 实时保留必须为零。
    
 _cbEntryID_
  
> 实时条目标识符中由_lpEntryID_参数指向的字节数。 
    
 _lpEntryID_
  
> 实时指向要处理的邮件的条目标识符的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 后处理成功。
    
## <a name="remarks"></a>注解

为邮件存储提供程序支持对象实现了**IMAPISupport:: CompleteMsg**方法, 并且只能由与传输提供程序紧密结合的邮件存储提供程序调用。 紧密耦合的存储提供程序调用**IMAPISupport:: CompleteMsg**以指示 MAPI 后台处理程序后置处理邮件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

仅限呼叫**CompleteMsg**在与传输提供程序紧密结合时, 可以处理邮件的所有收件人, 并且存在以下情况之一: 
  
- 已对邮件进行预处理。
    
- 邮件需要 MAPI 后台处理程序进行后处理。
    
## <a name="see-also"></a>另请参阅



[IMAPISupport : IUnknown](imapisupportiunknown.md)

