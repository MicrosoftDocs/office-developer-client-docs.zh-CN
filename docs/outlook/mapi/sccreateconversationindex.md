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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351322"
---
# <a name="sccreateconversationindex"></a>ScCreateConversationIndex

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示邮件在邮件线索中的位置。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
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
  
> 实时父对话索引中的字节数。
    
 _lpbParent_
  
> 实时指向父对话索引中的字节的指针。 如果_cbParent_为零, 则此值可能为 NULL。 
    
 _lpcbIndex_
  
> 排除一个指针, 指向呼叫返回的新对话索引中的字节数。 
    
 _lppbIndex_
  
> 排除指向调用返回的新对话索引的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。
    

