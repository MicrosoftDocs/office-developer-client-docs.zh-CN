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
  
包含一组指示此成员在文件夹或邮箱中的权限的位。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_MEMBER_RIGHTS  <br/> |
|标识符:  <br/> |0x6673  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |访问控制  <br/> |
   
## <a name="remarks"></a>注解

[IExchangeModifyTable](iexchangemodifytableiunknown.md)接口使用此属性定义对文件夹上的成员的权限。 可以显示和修改这些权限。 以下值是为此属性定义的权限。 
  
frightsReadAny
  
> Member 可以读取任何邮件。
    
frightsCreate
  
> 成员可以创建邮件。
    
frightsEditOwned
  
> Member 可以编辑用户拥有的任何邮件。
    
frightsDeleteOwned
  
> Member 可删除用户拥有的任何邮件。
    
frightsEditAny
  
> Member 可以编辑任何邮件。
    
frightsDeleteAny
  
> Member 可以删除任何邮件。
    
frightsCreateSubfolder
  
> Member 可以为文件夹创建子文件夹。
    
frightsOwner
  
> 成员拥有对该文件夹的所有以前的权限。
    
frightsContact
  
> 成员可以让您的姓名显示为文件夹中的联系人。
    
frightsVisible
  
> 成员可查看该文件夹是否存在。
    
rightsNone
  
> 成员对该文件夹没有权限。
    
rightsReadOnly
  
> Member 可以读取文件夹中的任何邮件。
    
rightsReadWrite
  
> Member 可以对文件夹中的任何邮件进行读取和写入。
    
rightsAll
  
> 成员拥有对该文件夹的所有以前的权限。
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> 处理文件夹操作。
    
[[毫秒-OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)
  
> 处理存储在服务器上的文件夹权限列表的检索。
    
[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)
  
> 指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历项目代表另一个用户操作时与之进行交互的方法。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[IExchangeModifyTable : IUnknown](iexchangemodifytableiunknown.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

