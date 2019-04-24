---
title: PidTagContainerFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContainerFlags
api_type:
- HeaderDef
ms.assetid: 66b8d333-227e-464d-8cf9-cd8a5ff15efb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c9c446097213e5b743a47ec32db17ec0afe63b78
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357545"
---
# <a name="pidtagcontainerflags-canonical-property"></a>PidTagContainerFlags 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含描述通讯簿容器的功能的标志的位掩码。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAINER_FLAGS  <br/> |
|标识符:  <br/> |0x3600  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>注解

可以为位掩码设置以下一个或多个标志:
  
AB_FIND_ON_OPEN 
  
> 显示一个对话框, 以便在显示容器的任何内容之前请求限制。 
    
AB_MODIFIABLE 
  
> 可以在容器中添加和删除条目。 此标志并不指示是否可以修改容器中的任何条目。
    
AB_RECIPIENTS 
  
> 容器可以保留收件人。 此标志并不指示是否有任何收件人实际存在于容器中, 或者是否可以添加或删除它们。 
    
AB_SUBCONTAINERS 
  
> 容器可以包含子容器。 此标志不指示是否有任何子容器实际存在于容器中, 以及是否可以添加或删除它们。 若要支持[IMAPIContainer:: GetHierarchyTable](imapicontainer-gethierarchytable.md), 容器必须设置 AB_SUBCONTAINERS。 
    
AB_UNMODIFIABLE 
  
> 无法在容器中添加或删除条目。 此标志并不指示是否可以修改容器中的任何条目。 
    
对于用于联机服务或与服务器的连接速度较慢的容器, 强烈建议使用 AB_FIND_ON_OPEN 标志。 在打开具有 AB_FIND_ON_OPEN 集的容器时, 会向用户显示 "**查找**" 对话框, 以限制显示的邮件用户。 即使限制邮件用户的部分规范, 也可以显著加快内容的显示速度。 
  
必须设置 AB_MODIFIABLE 或 AB_UNMODIFIABLE 标志。 可以设置这两个标志, 以指示容器不知道它是否可以修改, 例如, 如果修改取决于用户的访问权限。 在这种情况下, 客户端应用程序必须尝试调用并检查返回代码, 以确定容器的功能。 客户端通常首先检查 AB_MODIFIABLE。 如果设置了此设置, 则客户端会发出尝试修改容器并检查返回值的调用。 
  
AB_MODIFIABLE 标志并不指示可以向容器中添加哪些类型的条目。 若要确定这一点, 客户端应使用相应的[OpenProperty](imapiprop-openproperty.md)方法打开容器的**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。 打开**PR_CREATE_TEMPLATES**会导致容器的一次性表, 列出可在容器中创建的条目的类型。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源列表的属性和操作。
    
[[毫秒-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)
  
> 处理客户端与名称服务提供程序接口 (NSPI) 服务器的通信。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

