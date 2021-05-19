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
  
包含描述通讯簿容器功能的标志的位掩码。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAINER_FLAGS  <br/> |
|标识符:  <br/> |0x3600  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>备注

可以为位掩码设置以下一个或多个标志：
  
AB_FIND_ON_OPEN 
  
> 显示一个对话框，在显示容器的任何内容之前请求限制。 
    
AB_MODIFIABLE 
  
> 条目可以添加到容器中，也可以从容器中删除。 此标志不指示是否可以修改容器中的任何条目。
    
AB_RECIPIENTS 
  
> 容器可以保留收件人。 此标志不指示容器中是否实际存在任何收件人，或者是否可以添加或删除这些收件人。 
    
AB_SUBCONTAINERS 
  
> 容器可以容纳子容器。 此标志不指示容器中是否实际存在任何子容器，也不指示是否可以添加或删除它们。 AB_SUBCONTAINERS必须设置为容器以支持 [IMAPIContainer：：GetHierarchyTable](imapicontainer-gethierarchytable.md)。 
    
AB_UNMODIFIABLE 
  
> 条目不能添加到容器中或无法从容器中删除。 此标志不指示是否可以修改容器中的任何条目。 
    
强烈建议AB_FIND_ON_OPEN联机服务或与服务器连接缓慢的容器使用此标志。 打开已设置AB_FIND_ON_OPEN容器时，会向用户显示"查找"对话框以限制显示的消息用户。 即使部分规范限制邮件用户，也可以极大地加快内容的显示速度。 
  
必须AB_MODIFIABLE或AB_UNMODIFIABLE标记。 可以设置这两个标志以指示容器不知道是否可以修改它，例如，如果修改取决于用户的访问权。 在这种情况下，客户端应用程序必须尝试调用并检查返回代码以确定容器的功能。 客户端通常首先检查AB_MODIFIABLE。 如果已设置，客户端将进行调用，尝试修改容器并检查返回值。 
  
the AB_MODIFIABLE flag does not indicate what types of entries can be added to the container. 若要确定这一点，客户端应该使用适当的[OpenProperty](imapiprop-openproperty.md)方法打开容器的PR_CREATE_TEMPLATES ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。 打开 **PR_CREATE_TEMPLATES** 会导致返回容器的一次表，其中列出了可在容器中创建的条目类型。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
[[MS-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)
  
> 处理客户端与 NSPI 服务器的名称服务提供程序 (的通信) 。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

