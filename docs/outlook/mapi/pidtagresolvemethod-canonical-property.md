---
title: PidTagResolveMethod 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResolveMethod
api_type:
- COM
ms.assetid: 30d23c19-e0da-4511-9361-761153259216
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 14bb31ae9aebbb6441948b5756b426508107c9f0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331400"
---
# <a name="pidtagresolvemethod-canonical-property"></a>PidTagResolveMethod 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含文件夹的冲突解决值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RESOLVE_METHOD  <br/> |
|标识符:  <br/> |0x3FE7  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>备注

包含冲突解决邮件的文件夹上的此属性将指示如何解决冲突。 此属性不是必需的。 但是，如果已设置，则不得存在以下标志：
  
|||
|:-----|:-----|
|RESOLVE_METHOD_DEFAULT (0x00000000)   <br/> |应生成冲突解决消息。  <br/> |
|RESOLVE_METHOD_LAST_WRITER_WINS (0x00000001)   <br/> |使用当前更改覆盖目标邮件。  <br/> |
|RESOLVE_NO_CONFLICT_NOTIFICATION (0x00000002)   <br/> |在公用文件夹中生成冲突解决邮件时不发送冲突通知邮件。  <br/> |
   
客户端或服务器不得为关联邮件生成冲突解决消息。 必须使用语义解析 **这些RESOLVE_METHOD_LAST_WRITER_WINS消息** 。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXCSYNC]](https://msdn.microsoft.com/library/fd3e23ef-341a-4a8c-a0e9-6afecbb11c40%28Office.15%29.aspx)
  
> 处理在服务器和客户端之间同步邮件对象数据。
    
[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 定义远程操作中使用的基本数据结构。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

