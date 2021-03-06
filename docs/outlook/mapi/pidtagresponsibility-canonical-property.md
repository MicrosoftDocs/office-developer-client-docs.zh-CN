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
ms.openlocfilehash: 15bf61e71a2c230f7891c738661f839ecddb52e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330119"
---
# <a name="pidtagresponsibility-canonical-property"></a>PidTagResponsibility 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果某些传输提供程序已接受将邮件传送给此收件人的责任，则包含 TRUE;如果 MAPI 后台处理程序认为此传输提供程序应接受责任，则包含 FALSE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_RESPONSIBILITY  <br/> |
|标识符:  <br/> |0x0E0F  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 不可传输  <br/> |
   
## <a name="remarks"></a>备注

当 MAPI 后台处理程序通过 [IXPLogon：：SubmitMessage](ixplogon-submitmessage.md)向传输提供程序显示出站邮件时，它将 MAPI 后台处理程序认为其负责传输提供程序的所有收件人的此属性都为 FALSE，对于所有其他收件人，此属性为 TRUE。 传输提供程序应尝试处理所有收件人，PR_RESPONSIBILITY **设置为** FALSE。 成功向收件人发送或成功发送后，传输提供程序应在源邮件中将此属性设置为 TRUE，以指示其已接受该收件人的责任。 
  
如果在检查收件人之后，传输提供程序决定不能或不应处理该收件人，则传输提供程序应 **PR_RESPONSIBILITY设置为** FALSE。 然后，MAPI 后台处理程序将查找另一个可以处理该收件人的传输提供程序。 MAPI 后台处理程序最终会为任何传输提供程序不承担责任的收件人创建未送达报告。 
  
如果传输提供程序尝试传递邮件但失败，则它应调用 [IMAPISupport：：StatusRecips](imapisupport-statusrecips.md) 方法向 MAPI 指示失败的原因，以便 MAPI 可以生成未送达报告。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理客户端和服务器之间数据传输的顺序和流。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagDeleteAfterSubmit 规范属性](pidtagdeleteaftersubmit-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

