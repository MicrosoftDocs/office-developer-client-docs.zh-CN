---
title: SMAPIVerb
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMAPIVerb
api_type:
- COM
ms.assetid: 45066528-2447-4178-aaa3-7513ed0b3ba4
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 4d060d62deb685b4691846c2b8e48a82ae3195ea
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778845"
---
# <a name="smapiverb"></a>SMAPIVerb

  
  
**适用于**： Outlook 
  
描述 MAPI 动词。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
   
```cpp
typedef struct
{
  ULONG lVerb;
  LPSTR szVerbname;
  DWORD fuFlags;
  DWORD grfAttribs;
  ULONG ulFlags; /* Either 0 or MAPI_UNICODE */
} SMAPIVerb, FAR * LPMAPIVERB;

```

## <a name="members"></a>成员

 **lVerb**
  
> 表示传递给[IMAPIForm::DoVerb](imapiform-doverb.md)的动作代码。 标准谓词 Exchform.h 的头文件中定义。
    
 **szVerbname**
  
> 显示在窗体菜单上显示动作的名称。
    
 **fuFlags**
  
> 谓词的标志。
    
 **grfAttribs**
  
> 谓词的属性。 
    
 **ulFlags**
  
> 标志指示谓词的显示名称的格式。 可以设置以下标记：
    
MAPI_UNICODE 
  
> Unicode 格式的显示名称。 如果未设置 MAPI_UNICODE 标志的显示名称是 ANSI 格式。
    
## <a name="remarks"></a>备注

**SMAPIVerb**结构作为中的以下方法的参数传递： 
  
- [IMAPIFormContainer::ResolveMultipleMessageClasses](imapiformcontainer-resolvemultiplemessageclasses.md)
    
- [IMAPIFormMgr::ResolveMultipleMessageClasses](imapiformmgr-resolvemultiplemessageclasses.md)
    
## <a name="see-also"></a>另请参阅



[CbMessageClassArray](cbmessageclassarray.md)


[MAPI 结构](mapi-structures.md)

