---
title: PidTagSendRichInfo 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSendRichInfo
api_type:
- COM
ms.assetid: e85fc766-197a-484f-b600-68cd28a052a2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a1db4ba7a70695b17631ca13f1728043be8164bd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575964"
---
# <a name="pidtagsendrichinfo-canonical-property"></a>PidTagSendRichInfo 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
如果收件人可以接收所有的消息内容，包括富文本格式 (RTF) 和对象链接与嵌入 (OLE) 对象，包含 TRUE。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SEND_RICH_INFO  <br/> |
|标识符：  <br/> |0x3A40  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Address  <br/> |
   
## <a name="remarks"></a>注解

建议通讯组列表和邮件用户对象公开此属性。 
  
此属性指示发件人是否考虑要启用了 MAPI 的收件人。 
  
此属性设置为 TRUE 时, 的传输和网关可以传输邮件，包括 RTF 和 OLE 对象的全部内容。 传输提供程序和网关应使用传输中性封装格式 (TNEF) 来封装不涉及的所有消息系统的本机任何属性。 
  
当此属性设置为 FALSE 时，则传输提供程序和网关可以自由地放弃其本机客户端不能使用的消息内容。 例如，当客户端不支持 RTF，传输提供程序可以发送纯文本。 
  
当未设置此属性时，由传输提供程序、 邮件传输代理 (MTA)，或网关实现确定默认行为。 通讯簿提供程序不需要支持此属性。 例如，可以选择紧密耦合的通讯簿和传输提供程序发送 TNEF 但从未使用 rtf 格式。 
  
客户端不应假定传输提供程序和网关将使用 TNEF 自己的计划。 某些传输提供程序和支持 TNEF 的网关传输而不考虑此属性的值，但其他人拒绝来构建或发送 TNEF，如果它未设置为 TRUE。 
  
> [!NOTE]
> 此属性，并基于及其值的决策的设置位于单独对每个收件人。 
  
默认情况下，MAPI 将值设置为 TRUE。 调用[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md)或调用[IMAPISupport::CreateOneOff](imapisupport-createoneoff.md)提供商的客户端可以设置**MAPI_SEND_NO_RICH_INFO**位_ulFlags_参数，这将导致 MAPI 将此属性设置为 FALSE。 One-offs 通过用户界面创建使用指定的创建模板的值。 
  
在调用[IAddrBook::ResolveName](iaddrbook-resolvename.md)方法时名称无法解析，但可以被解释为 Internet 地址 (SMTP)，此属性设置为 FALSE。 若要将其视为 Internet 地址，未解析的显示名称必须是项的格式 X@Y。Z，如"pete@pinecone.com"。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
[[MS OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定的属性和操作所允许的电子邮件消息对象。
    
[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件消息对象的约定。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagAttachDataObject 规范属性](pidtagattachdataobject-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

