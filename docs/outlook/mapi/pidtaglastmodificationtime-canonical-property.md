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
ms.openlocfilehash: dea709b457e28efef62718fc388621e01c4eb5bf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279707"
---
# <a name="pidtaglastmodificationtime-canonical-property"></a>PidTagLastModificationTime 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含上次修改对象或子对象时的日期和时间。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |操作  <br/> |
|标识符:  <br/> |0x3008  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |邮件时间  <br/> |
   
## <a name="remarks"></a>注解

此属性最初设置为与**PR_CREATION_TIME** ([PidTagCreationTime](pidtagcreationtime-canonical-property.md)) 属性相同的值。 通过复制由本机文件系统维护的上次修改时间, 附件子文件可根据需要进行更新。 在第一次调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法之前, 客户端应用程序可以设置此属性。 从随后, 提供程序应在每个**IMAPIProp:: SaveChanges**调用中更新**操作**。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理服务器和客户端之间的同步邮件对象数据。
    
[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源列表的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

