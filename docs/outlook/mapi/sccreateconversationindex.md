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
ms.openlocfilehash: 385660889c40e5f59dfc015ad92ce6a1398ab0cd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415654"
---
# <a name="sccreateconversationindex"></a>ScCreateConversationIndex

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示邮件在消息线程中属于何处。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]指向父对话索引中的字节的指针。 如果  _cbParent 为零，则此_ 参数可能为 NULL。 
    
 _lpcbIndex_
  
> [out]指向调用返回的新对话索引中的字节数的指针。 
    
 _lppbIndex_
  
> [out]指向指向调用返回的新对话索引的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    

