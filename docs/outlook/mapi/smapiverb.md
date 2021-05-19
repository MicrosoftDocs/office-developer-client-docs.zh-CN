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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410957"
---
# <a name="smapiverb"></a>SMAPIVerb

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
描述 MAPI 动词。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform.h  <br/> |
   
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
  
> 表示传递给 [IMAPIForm：:D oVerb 谓词的代码](imapiform-doverb.md)。 标准动作在头文件 Exchform.h 中定义。
    
 **szVerbname**
  
> 在窗体菜单上显示动词的显示名称。
    
 **fuFlags**
  
> 动词标记。
    
 **grfAttribs**
  
> 动词动作的属性。 
    
 **ulFlags**
  
> 指示动词动词的用法格式显示名称。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 该显示名称采用 Unicode 格式。 如果未MAPI_UNICODE，则显示名称为 ANSI 格式。
    
## <a name="remarks"></a>备注

**SMAPIVerb** 结构在下列方法中作为参数传递： 
  
- [IMAPIFormContainer::ResolveMultipleMessageClasses](imapiformcontainer-resolvemultiplemessageclasses.md)
    
- [IMAPIFormMgr::ResolveMultipleMessageClasses](imapiformmgr-resolvemultiplemessageclasses.md)
    
## <a name="see-also"></a>另请参阅



[CbMessageClassArray](cbmessageclassarray.md)


[MAPI 结构](mapi-structures.md)

