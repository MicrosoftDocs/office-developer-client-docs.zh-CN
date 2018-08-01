---
title: DIR_ENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9e055269-f3bf-4b64-8384-3cbc372c0b34
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2af9d529cb92e1040427eba69270908dcf4a5d9f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774803"
---
# <a name="direntryid"></a>DIR_ENTRYID

  
  
**适用于**： Outlook 
  
介绍目录条目 id 的属性。
  
|||
|:-----|:-----|
|头文件：  <br/> |entryid.h  <br/> |
   
```cpp
#pragma pack(4)
typedef struct _dir_entryid
{
    BYTE abFlags[4]; 
    MAPIUID muid; 
    ULONG ulVersion; 
    ULONG ulType; 
    MAPIUID muidID; 
}   DIR_ENTRYID, *LPDIR_ENTRYID; 
#pragma pack()
```

## <a name="members"></a>Members

 **abFlags**
  
> 位掩码的标志，提供描述对象的信息。 有关详细信息，请参阅[ENTRYID](entryid.md)结构的**abFlags**字段的说明。 
    
 **muid**
  
> 标识的存储提供程序的 GUID。
    
 **ulVersion**
  
> **DIR_ENTRYID**结构的版本号。 必须设置为 CONTAB_VERSION。 
    
 **ulType**
  
> 表示目录条目 ID 类型的整数。 它必须是下列值之一：
    
|**名称**|**说明**|
|:-----|:-----|
|CONTAB_ROOT  <br/> |MAPI 通讯簿根文件夹。  <br/> |
|CONTAB_SUBROOT  <br/> |MAPI 通讯簿对象的根文件夹中包含子文件夹。  <br/> |
|CONTAB_CONTAINER  <br/> |通讯簿容器对象。  <br/> |
   
 **muidID**
  
> 标识登录对象的 GUID。
    
## <a name="remarks"></a>说明

结构**DIR_ENTRYID**和[CONTAB_ENTRYID](contab_entryid.md)完全相同，除了**ulType**成员。 **UlType**成员的内容确定适合剩余字段的结构。 
  
## <a name="see-also"></a>另请参阅



[CONTAB_ENTRYID](contab_entryid.md)


[MAPI 结构](mapi-structures.md)

