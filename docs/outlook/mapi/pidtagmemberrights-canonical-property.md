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
ms.openlocfilehash: dcbf8a323f5178a5a2e39d0963dd19415ab835bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342692"
---
# <a name="pidtagmemberrights-canonical-property"></a>PidTagMemberRights 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一组位，指示此成员对文件夹或邮箱的权限。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MEMBER_RIGHTS  <br/> |
|标识符:  <br/> |0x6673  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |访问控制  <br/> |
   
## <a name="remarks"></a>备注

此属性由 [IExchangeModifyTable](iexchangemodifytableiunknown.md) 接口用来定义成员对文件夹的权限。 可以显示和修改这些权限。 以下值是为此属性定义权限。 
  
frightsReadAny
  
> 成员可以读取任何邮件。
    
frightsCreate
  
> 成员可以创建邮件。
    
frightsEditOwned
  
> 成员可以编辑用户拥有的任何邮件。
    
frightsDeleteOwned
  
> 成员可以删除用户拥有的任何邮件。
    
frightsEditAny
  
> 成员可以编辑任何邮件。
    
frightsDeleteAny
  
> 成员可以删除任何邮件。
    
frightsCreateSubfolder
  
> 成员可以创建文件夹的子文件夹。
    
frightsOwner
  
> 成员对文件夹拥有以前的所有权限。
    
frightsContact
  
> 成员可以将你的姓名显示为文件夹上的联系人。
    
frightsVisible
  
> 成员可以看到该文件夹存在。
    
rightsNone
  
> 成员对文件夹没有权限。
    
rightsReadOnly
  
> 成员可以读取文件夹中的任何邮件。
    
rightsReadWrite
  
> 成员可以读取和写入文件夹中的任何邮件。
    
rightsAll
  
> 成员对文件夹拥有以前的所有权限。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> 处理文件夹操作。
    
[[MS-OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)
  
> 处理对服务器上存储的文件夹权限列表的检索。
    
[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定用于连接邮箱和将邮箱配置为代理的方法，以及代表其他用户操作时与邮件和日历项目的交互的方法。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

