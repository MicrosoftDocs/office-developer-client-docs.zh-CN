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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3ef284a2c036abb9eac10ecf33de4adbf61f3c54
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309483"
---
# <a name="smapiverb"></a>SMAPIVerb

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述 MAPI 谓词。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
   
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

## <a name="members"></a>Members

 **lVerb**
  
> 表示传递给 IMAPIForm 的谓词的代码[::D overb](imapiform-doverb.md)。 标准动作是在头文件 Exchform 中定义的。
    
 **szVerbname**
  
> 显示在 "表单" 菜单上的动作的显示名称。
    
 **fuFlags**
  
> 谓词的标志。
    
 **grfAttribs**
  
> 谓词的属性。 
    
 **ulFlags**
  
> 指示谓词的显示名称格式的标志。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 显示名称为 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则显示名称为 ANSI 格式。
    
## <a name="remarks"></a>注解

在以下方法中, **SMAPIVerb**结构作为参数传递: 
  
- [IMAPIFormContainer::ResolveMultipleMessageClasses](imapiformcontainer-resolvemultiplemessageclasses.md)
    
- [IMAPIFormMgr::ResolveMultipleMessageClasses](imapiformmgr-resolvemultiplemessageclasses.md)
    
## <a name="see-also"></a>另请参阅



[CbMessageClassArray](cbmessageclassarray.md)


[MAPI 结构](mapi-structures.md)

