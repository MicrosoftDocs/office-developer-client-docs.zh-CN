---
title: CONTAB_ENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 84251222-dac4-4f4d-97b9-aa0e2cd26c44
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 2c8661f24ed9555547446cf63fc08a3be7e6e941
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774682"
---
# <a name="contabentryid"></a>CONTAB_ENTRYID

  
  
**适用于**： Outlook 
  
包含联系人文件夹的条目 ID。
  
|||
|:-----|:-----|
|头文件：  <br/> |msomapiutil.h  <br/> |
   
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

## <a name="members"></a>成员

 **abFlags**
  
> 位掩码的标志，提供描述对象的信息。 有关详细信息，请参阅[ENTRYID](entryid.md)结构的**abFlags**字段的说明。 
    
 **muid**
  
> 标识的存储提供程序的 GUID。
    
 **ulVersion**
  
> **CONTAB_ENTRYID**结构的版本号。 必须设置为 CONTAB_VERSION。 
    
 **ulType**
  
> 一个代表联系人项 ID 类型的整数。 它必须是下列值之一：
    
|**名称**|**说明**|
|:-----|:-----|
|CONTAB_USER  <br/> |消息的用户对象。  <br/> |
|CONTAB_DISTLIST  <br/> |通讯组列表对象。  <br/> |
   
 **ulIndex**
  
> 到电子邮件属性子集的索引。
    
 **cbeid**
  
> 联系人消息与联系人通讯簿中的此条目关联的项标识符的大小。
    
 **abeid**
  
> 联系人消息与联系人通讯簿中的此条目关联的项标识符。
    
## <a name="remarks"></a>备注

联系人通讯簿通讯簿包含联系人文件夹中的电子邮件地址或传真号码的所有联系人项目。 每个联系人通讯簿中的项相关联的电子邮件地址或传真号码。 由于联系人项可以具有三个电子邮件地址和三个传真号码，可以通过在相应的联系人通讯簿中的最多为六个条目表示联系人项目。
  
联系人通讯簿旨在支持寻址到联系人文件夹中的联系人的电子邮件的用户。 Microsoft Outlook 2010 和 Microsoft Outlook 2013 支持的联系人通讯簿提供程序是 contab32.dll。
  
**CONTAB_ENTRYID**结构支持基础的 MAPI 联系人消息中出现的信息的子集。 它标识联系人邮件与关联的特定的联系人通讯簿条目。 
  
当**ulType**字段值设置为 CONTAB_DISTLIST 或 CONTAB_USER **cbeid**和**abeid**字段才有效。 如果**ulType**字段值设置为 CONTAB_ROOT、 CONTAB_SUBROOT 或 CONTAB_CONTAINER， [DIR_ENTRYID](dir_entryid.md)结构应改用。 
  
## <a name="see-also"></a>另请参阅



[DIR_ENTRYID](dir_entryid.md)


[MAPI 结构](mapi-structures.md)

