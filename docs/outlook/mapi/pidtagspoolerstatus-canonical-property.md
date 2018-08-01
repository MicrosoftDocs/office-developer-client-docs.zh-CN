---
title: PidTagSpoolerStatus 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSpoolerStatus
api_type:
- COM
ms.assetid: a10d86fc-3a73-49dc-b974-ed852ec715e9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: df52f668e91b707c0436b394186b27fdbb3a5dbf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778443"
---
# <a name="pidtagspoolerstatus-canonical-property"></a>PidTagSpoolerStatus 规范属性

  
  
**适用于**： Outlook 
  
包含基于可供 MAPI 后台处理程序的信息消息的状态。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SPOOLER_STATUS  <br/> |
|标识符：  <br/> |0x0E10  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 非可传送  <br/> |
   
## <a name="remarks"></a>说明

此属性在消息对象上通过 MAPI 计算。
  
此属性仅入站邮件上的显示，并保留其他所有情况下。 表示一条消息，指示已传递给其最终位置或是否消息挂接提供程序可能已删除邮件重新路由它时。
  
客户端应用程序应永远不会将该属性。 入站邮件，客户端或服务提供程序可以调用此属性可以确定邮件状态[IMAPIProp::GetProps](imapiprop-getprops.md) 。 值 S_OK 指示邮件已成功递送到消息存储库。 值 MAPI_E_OBJECT_DELETED 指示邮件已被删除，永远不会被提交到存储区。 
  
消息存储提供程序应在邮件、 收件人表和传出队列表支持此属性。 客户端和提供程序应能够在传出队列表上设置列方法和 restrict 基于此属性。
  
## <a name="related-resources"></a>相关资源

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

