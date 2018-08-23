---
title: PidTagAttachExtension 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachExtension
api_type:
- HeaderDef
ms.assetid: 667da30b-e11c-4040-aecf-bb35eed23722
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 71ad53880c400d924d73c903bd77f7b447a69d8b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577721"
---
# <a name="pidtagattachextension-canonical-property"></a>PidTagAttachExtension 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含指示附件的文档类型的文件扩展名。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_EXTENSION，PR_ATTACH_EXTENSION_A，PR_ATTACH_EXTENSION_W  <br/> |
|标识符：  <br/> |0x3703  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

由客户端应用程序提交次设置这些属性。 
  
转换邮件附件 （-路由转换） 时，消息系统使用**PR_ATTACH_EXTENSION**或启动应用程序基于收到的邮件中的附件。 发送方的客户端不提供这些属性的值，如果处理附件的邮件存储没有义务生成它。 接收的客户端**PR_ATTACH_EXTENSION**，应首先检查并如果它未提供，应分析文件扩展名的附件**PR_ATTACH_FILENAME** ([PidTagAttachFilename](pidtagattachfilename-canonical-property.md)) 或**PR_ATTACH_LONG_FILENAME**([PidTagAttachLongFilename](pidtagattachlongfilename-canonical-property.md)) 属性。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
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

