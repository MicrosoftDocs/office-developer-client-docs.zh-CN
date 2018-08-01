---
title: PidTagMemberRights 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMemberRights
api_type:
- HeaderDef
ms.assetid: 3e526b93-1f64-41ea-b43c-5b03fe1c56ed
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2ffc6973d2670402ec8095120eea3db02f529d0a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777847"
---
# <a name="pidtagmemberrights-canonical-property"></a>PidTagMemberRights 规范属性

  
  
**适用于**： Outlook 
  
包含一组所指示文件夹或邮箱上的此成员的权限的位。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MEMBER_RIGHTS  <br/> |
|标识符：  <br/> |0x6673  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |访问控制  <br/> |
   
## <a name="remarks"></a>说明

此属性由[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口用于在文件夹中定义的成员的权限。 可以显示和修改这些权限。 下面的值为此属性定义的权限。 
  
frightsReadAny
  
> 成员可以读取任何消息。
    
frightsCreate
  
> 成员可以创建邮件。
    
frightsEditOwned
  
> 成员可以编辑用户所拥有的任何消息。
    
frightsDeleteOwned
  
> 成员可以删除用户所拥有的任何消息。
    
frightsEditAny
  
> 成员可以编辑任何消息。
    
frightsDeleteAny
  
> 成员可以删除任何消息。
    
frightsCreateSubfolder
  
> 成员可以创建子文件夹。
    
frightsOwner
  
> 成员具有的文件夹的所有以前的权限。
    
frightsContact
  
> 成员可以具有您显示为的文件夹的联系人的姓名。
    
frightsVisible
  
> 成员都能看到该文件夹存在。
    
rightsNone
  
> 成员的文件夹没有权限。
    
rightsReadOnly
  
> 成员可以读取的文件夹中的任何消息。
    
rightsReadWrite
  
> 成员可以读取和写入到的文件夹中的任何消息。
    
rightsAll
  
> 成员具有的文件夹的所有以前的权限。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCFOLD]](http://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> 处理文件夹的操作。
    
[[MS OXCPERM]](http://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)
  
> 处理检索存储在服务器的文件夹的权限列表。
    
[[MS OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定连接到和配置为代理人，以及与邮件和日历项目交互的邮箱，当这些代表其他用户操作的方法。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

