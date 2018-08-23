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
ms.openlocfilehash: e67cbb113899487f489ef7235d92d1adfcb76163
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22563637"
---
# <a name="pidtagresolvemethod-canonical-property"></a>PidTagResolveMethod 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含某个文件夹的冲突解决值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RESOLVE_METHOD  <br/> |
|标识符：  <br/> |0x3FE7  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>注解

此属性包含冲突解决消息的文件夹将指示如何解决冲突。 此属性不是必需的。 但是，如果设置，则之外以下标志不必须存在：
  
|||
|:-----|:-----|
|RESOLVE_METHOD_DEFAULT (0X00000000)  <br/> |冲突解决应生成消息。  <br/> |
|RESOLVE_METHOD_LAST_WRITER_WINS (0X00000001)  <br/> |用当前应用的更改覆盖目标邮件。  <br/> |
|RESOLVE_NO_CONFLICT_NOTIFICATION (0X00000002:UC)  <br/> |时生成冲突解决公用文件夹中的消息，则不发送冲突通知消息。  <br/> |
   
客户端或服务器一定不会产生冲突解决消息关联邮件。 通过使用**RESOLVE_METHOD_LAST_WRITER_WINS**语义，必须解决这些消息。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCSYNC]](http://msdn.microsoft.com/library/fd3e23ef-341a-4a8c-a0e9-6afecbb11c40%28Office.15%29.aspx)
  
> 同步服务器和客户端之间的消息对象数据的句柄。
    
[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 定义所使用的基本的数据结构中远程操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

