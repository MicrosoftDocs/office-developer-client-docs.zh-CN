---
title: PidTagResponsibility 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResponsibility
api_type:
- COM
ms.assetid: 1e8ccef1-db0a-4230-9bd0-87540b53e890
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9dba26ab6948d7190521ff31a8732c4b058ab7c9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778231"
---
# <a name="pidtagresponsibility-canonical-property"></a>PidTagResponsibility 规范属性

  
  
**适用于**： Outlook 
  
包含 TRUE 如果某些传输提供程序已经接受邮件传递到此收件人和 FALSE，如果 MAPI 后台处理程序认为该传输提供程序应接受责任的责任。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RESPONSIBILITY  <br/> |
|标识符：  <br/> |0x0E0F  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 非可传送  <br/> |
   
## <a name="remarks"></a>说明

当 MAPI 后台处理程序提供的出站邮件到传输提供程序，通过[IXPLogon::SubmitMessage](ixplogon-submitmessage.md)，它将该属性设置为 FALSE 的所有收件人为其 MAPI 后台处理程序认为该传输提供程序负责，和 TRUE 所有其他收件人。 传输提供程序应尝试处理与**PR_RESPONSIBILITY**设置为 FALSE 的所有收件人。 成功发送，或最终发送给收件人，出现故障后传输提供程序应将此属性设置为 TRUE 源消息以指示它已接受该收件人的责任。 
  
如果在检查收件人后, 传输提供程序决定它无法或不应该处理，传输提供程序应保留**PR_RESPONSIBILITY**设置为 FALSE。 然后 MAPI 后台处理程序将查找另一个传输提供程序可以处理该收件人。 MAPI 后台处理程序的任何传输提供程序为其接受责任任何收件人最终会创建原件报告。 
  
如果传输提供程序尝试，并且无法将邮件传递，它应调用[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)方法，以指示为 MAPI 失败的原因，以便 MAPI 可以生成原件报告。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理顺序和客户端和服务器之间的数据传输的流。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagDeleteAfterSubmit 规范属性](pidtagdeleteaftersubmit-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

