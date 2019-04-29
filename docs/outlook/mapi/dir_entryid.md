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
ms.openlocfilehash: e7abcb2c86ff5cabe0b8f5664ec316244617ac09
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421233"
---
# <a name="direntryid"></a>DIR_ENTRYID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
介绍目录项 id 的属性。
  
|||
|:-----|:-----|
|标头文件：  <br/> |entryid  <br/> |
   
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
  
> 提供描述对象的信息的标志的位掩码。 有关详细信息, 请参阅[ENTRYID](entryid.md)结构的**abFlags**字段的说明。 
    
 **muid**
  
> 标识存储提供程序的 GUID。
    
 **ulVersion**
  
> **DIR_ENTRYID**结构的版本号。 必须设置为 CONTAB_VERSION。 
    
 **ulType**
  
> 表示目录项 ID 类型的整数。 它必须是下列值之一:
    
|**名称**|**说明**|
|:-----|:-----|
|CONTAB_ROOT  <br/> |MAPI 通讯簿的根文件夹。  <br/> |
|CONTAB_SUBROOT  <br/> |MAPI 通讯簿对象的根文件夹内包含一个子文件。  <br/> |
|CONTAB_CONTAINER  <br/> |通讯簿容器对象。  <br/> |
   
 **muidID**
  
> 标识登录对象的 GUID。
    
## <a name="remarks"></a>说明

除**ulType**成员之外, 结构**DIR_ENTRYID**和[CONTAB_ENTRYID](contab_entryid.md)相同。 **ulType**成员的内容确定哪种结构适用于其余字段。 
  
## <a name="see-also"></a>另请参阅



[CONTAB_ENTRYID](contab_entryid.md)


[MAPI 结构](mapi-structures.md)

