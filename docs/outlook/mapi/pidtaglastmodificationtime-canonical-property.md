---
title: PidTagLastModificationTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLastModificationTime
api_type:
- HeaderDef
ms.assetid: a64e5300-6865-4588-8e1b-158cfd9c60c2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 653bdf26988c46be5f866cfbda331510c5a54afd
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575705"
---
# <a name="pidtaglastmodificationtime-canonical-property"></a>PidTagLastModificationTime 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含的日期和时间上次修改的对象或子对象。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |操作  <br/> |
|标识符：  <br/> |0x3008  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |消息时间  <br/> |
   
## <a name="remarks"></a>注解

此属性最初设置为相同的值的**PR_CREATION_TIME** ([PidTagCreationTime](pidtagcreationtime-canonical-property.md)) 属性。 附件子对象可将其更新根据需要通过复制由本地文件系统维护的上次修改时间。 客户端应用程序直到第一个呼叫[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法可以设置该属性。 此后提供程序应在每个**IMAPIProp::SaveChanges**呼叫期间更新**操作**。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 同步服务器和客户端之间的消息对象数据的句柄。
    
[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
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

