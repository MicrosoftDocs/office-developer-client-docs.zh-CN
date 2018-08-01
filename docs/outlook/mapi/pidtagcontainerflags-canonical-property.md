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
ms.openlocfilehash: c13acd1c3b759602a5fbe07c21ca8b784e0fe4d1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777461"
---
# <a name="pidtagcontainerflags-canonical-property"></a>PidTagContainerFlags 规范属性

  
  
**适用于**： Outlook 
  
包含描述的通讯簿容器功能标志的位掩码。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CONTAINER_FLAGS  <br/> |
|标识符：  <br/> |0x3600  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>说明

可以为位掩码设置一个或多个以下标志：
  
AB_FIND_ON_OPEN 
  
> 显示一个对话框，以请求之前显示容器的任何内容的限制。 
    
AB_MODIFIABLE 
  
> 可以添加到并从容器中删除条目。 此标志不指示是否可以修改任何容器中的条目。
    
AB_RECIPIENTS 
  
> 容器可以包含收件人。 此标志并不表示任何收件人是否确实存在的容器中，或者可以是否添加或删除它们。 
    
AB_SUBCONTAINERS 
  
> 容器可以包含子容器。 此标志并不表示任何子容器是否确实存在的容器中，也可以是否添加或删除它们。 AB_SUBCONTAINERS 必须为要支持[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md)的容器。 
    
AB_UNMODIFIABLE 
  
> 无法添加到或从容器中删除条目。 此标志不指示是否可以修改任何容器中的条目。 
    
使用与在线服务或慢速连接到服务器的容器中的强烈建议 AB_FIND_ON_OPEN 标志。 容器打开已设置的 AB_FIND_ON_OPEN 时, 的**查找**对话框将显示向用户显示消息的用户限制。 即使部分规范限制的邮件的用户可以显著加快内容的显示。 
  
必须设置 AB_MODIFIABLE 或 AB_UNMODIFIABLE 标志。 可以设置这两个标志以指示容器不知道是否可以进行修改，例如，如果修改取决于用户的访问权限。 在这种情况下，客户端应用程序必须尝试呼叫，并检查返回代码来确定容器的功能。 通过检查 AB_MODIFIABLE 通常启动客户端。 如果设置，则客户端调用尝试修改容器并检查的返回值。 
  
AB_MODIFIABLE 标志并不表示哪些类型的条目可以添加到容器。 若要确定这一点，客户端应使用相应的[OpenProperty](imapiprop-openproperty.md)方法打开容器的**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。 打开**PR_CREATE_TEMPLATES**原因容器的一次性要返回的表列出可以容器中创建的项的类型。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
[[MS NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)
  
> 处理与名称服务提供程序界面 (NSPI) 服务器的客户端的通信。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

