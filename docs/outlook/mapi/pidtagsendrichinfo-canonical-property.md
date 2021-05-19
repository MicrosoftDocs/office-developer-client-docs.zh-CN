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
ms.openlocfilehash: a7ad27d757d4ed6df58c597bf17d9e5412f83457
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342516"
---
# <a name="pidtagsendrichinfo-canonical-property"></a>PidTagSendRichInfo 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果收件人可以接收所有邮件内容（包括 RTF (RTF 格式) 对象链接和嵌入 OLE 对象） (TRUE) TRUE。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SEND_RICH_INFO  <br/> |
|标识符:  <br/> |0x3A40  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |地址  <br/> |
   
## <a name="remarks"></a>备注

建议通讯组列表和消息传递用户对象公开此属性。 
  
此属性指示发件人是否认为收件人已启用 MAPI。 
  
当此属性设置为 TRUE 时，传输和网关可以传输邮件的完整内容，包括 RTF 和 OLE 对象。 传输提供程序和网关应该使用传输中性封装格式 (TNEF) 来封装不是涉及的所有邮件系统本机的任何属性。 
  
当此属性设置为 FALSE 时，传输提供程序和网关可以随意丢弃其本机客户端无法使用的邮件内容。 例如，当客户端不支持 RTF 时，传输提供程序只能发送纯文本。 
  
未设置此属性时，默认行为由传输提供程序、邮件传输代理或网关 (MTA) 确定。 通讯簿提供程序不需要支持此属性。 例如，紧密耦合的通讯簿和传输提供程序可以选择发送 TNEF，但从不使用 RTF。 
  
客户端不应假定传输提供程序和网关将自行使用 TNEF。 一些支持 TNEF 的传输提供程序和网关会传输它，而不考虑此属性的值，但其他传输提供程序和网关拒绝构建或发送 TNEF（如果未设置为 TRUE）。 
  
> [!NOTE]
> 此属性的设置以及基于其值的决策基于每个收件人。 
  
默认情况下，MAPI 将值设置为 TRUE。 调用 [IAddrBook：：CreateOneOff](iaddrbook-createoneoff.md)的客户端或调用 [IMAPISupport：：CreateOneOff](imapisupport-createoneoff.md)的提供程序可以在 _ulFlags_ 参数中设置 **MAPI_SEND_NO_RICH_INFO** 位，这将导致 MAPI 将此属性设置为 FALSE。 用户界面创建的一次使用创建模板指定的值。 
  
当名称无法解析，但可以解释为 SMTP (Internet 地址时，调用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md)) 时，此属性设置为 FALSE。 要解释为 Internet 地址，显示名称条目的名称必须采用 X@Y。Z，例如"pete@pinecone.com"。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定电子邮件对象允许的属性和操作。
    
[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定到邮件对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagAttachDataObject 规范属性](pidtagattachdataobject-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

