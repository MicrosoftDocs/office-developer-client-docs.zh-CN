---
title: CONTAB_ENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 84251222-dac4-4f4d-97b9-aa0e2cd26c44
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a2a204f76b62c8c6bc6d8a4e793c936a0184dc65
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424082"
---
# <a name="contabentryid"></a>CONTAB_ENTRYID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 "联系人" 文件夹的条目 ID。
  
|||
|:-----|:-----|
|标头文件：  <br/> |msomapiutil  <br/> |
   
```cpp
#pragma pack(4) 
typedef struct _contab_entryid
{
    BYTE abFlags[4];
    MAPIUID muid;
    ULONG ulVersion;
    ULONG ulType;
    ULONG ulIndex;
    ULONG cbeid;
    BYTE abeid[1];
}   CONTAB_ENTRYID, *LPCONTAB_ENTRYID;
#pragma pack() 
```

## <a name="members"></a>Members

 **abFlags**
  
> 提供描述对象的信息的标志的位掩码。 有关详细信息, 请参阅[ENTRYID](entryid.md)结构的**abFlags**字段的说明。 
    
 **muid**
  
> 标识存储提供程序的 GUID。
    
 **ulVersion**
  
> **CONTAB_ENTRYID**结构的版本号。 必须设置为 CONTAB_VERSION。 
    
 **ulType**
  
> 一个表示联系人条目 ID 类型的整数。 它必须是下列值之一:
    
|**名称**|**说明**|
|:-----|:-----|
|CONTAB_USER  <br/> |消息传递用户对象。  <br/> |
|CONTAB_DISTLIST  <br/> |通讯组列表对象。  <br/> |
   
 **ulIndex**
  
> 电子邮件属性子集的索引。
    
 **cbeid**
  
> 与联系人通讯簿中的此条目相关联的联系人邮件的条目标识符的大小。
    
 **abeid**
  
> 与联系人通讯簿中的此条目相关联的联系人邮件的条目标识符。
    
## <a name="remarks"></a>说明

联系人通讯簿是一个通讯簿, 其中包含 "联系人" 文件夹中具有电子邮件地址或传真号码的所有联系人项目。 联系人通讯簿中的每个条目都与电子邮件地址或传真号码相关联。 由于联系人项目最长可包含三个电子邮件地址和三个传真号码, 因此联系人项目可以在相应联系人通讯簿中的最大6个条目中表示。
  
联系人通讯簿的用途是支持用户为联系人文件夹中的联系人寻址电子邮件。 microsoft outlook 2010 和 microsoft outlook 2013 支持的联系人通讯簿提供程序为 contab32。
  
**CONTAB_ENTRYID**结构支持基础 MAPI 联系人消息中存在的信息的子集。 它标识与特定联系人通讯簿条目相关联的联系人消息。 
  
仅当**ulType**字段值设置为 CONTAB_DISTLIST 或 CONTAB_USER 时, **cbeid**和**abeid**字段才有效。 当**ulType**字段值设置为 CONTAB_ROOT、CONTAB_SUBROOT 或 CONTAB_CONTAINER 时, 应改为使用[DIR_ENTRYID](dir_entryid.md)结构。 
  
## <a name="see-also"></a>另请参阅



[DIR_ENTRYID](dir_entryid.md)


[MAPI 结构](mapi-structures.md)

