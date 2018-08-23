---
title: ScCreateConversationIndex
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScCreateConversationIndex
api_type:
- COM
ms.assetid: 3ccfc15d-f3c6-4c7b-b1cc-855af66036de
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5ae0c9f123ade599ca9bc1d3bdea3e9c89cfbc16
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594149"
---
# <a name="sccreateconversationindex"></a>ScCreateConversationIndex

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
指示邮件线程中的消息所属的位置。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE ScCreateConversationIndex(
  ULONG cbParent,
  LPBYTE lpbParent,
  ULONG FAR* lpcbIndex,
  LPBYTE FAR * lppbIndex
);
```

## <a name="parameters"></a>参数

 _cbParent_
  
> [in]父对话索引中的字节数。
    
 _lpbParent_
  
> [in]指向父对话索引中的字节的指针。 如果_cbParent_为零，这可能是 NULL。 
    
 _lpcbIndex_
  
> [输出]为新的调用返回的对话索引中的字节数的指针。 
    
 _lppbIndex_
  
> [输出]为新的对话索引的调用返回指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    

