---
title: PidTagAttachMethod 规范属性
manager: soliver
ms.date: 9/7/2016
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachMethod
api_type:
- HeaderDef
ms.assetid: 32089213-ef7b-4152-84ab-b44e9911332b
description: 上次修改时间： 9 月 7，2016年
ms.openlocfilehash: 697f7e8045ca198c2c10b9396f19cb2d7ce8346e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583650"
---
# <a name="pidtagattachmethod-canonical-property"></a>PidTagAttachMethod 规范属性

 
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含一个 MAPI 定义的常数，表示可以访问附件的内容的方式。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_METHOD  <br/> |
|标识符：  <br/> |0x3705  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

此属性可以具有完全下列值之一：
  
NO_ATTACHMENT 
  
> 刚刚创建的附件。 
    
ATTACH_BY_VALUE 
  
> **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性包含附件数据。 
    
ATTACH_BY_REFERENCE 
  
> **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 或**PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) 属性包含标识有权访问公共文件附件形式向收件人的完全限定路径服务器。 
    
ATTACH_BY_REF_RESOLVE 
  
> **PR_ATTACH_PATHNAME**或**PR_ATTACH_LONG_PATHNAME**属性包含标识附件的完全限定路径。 
    
ATTACH_BY_REF_ONLY 
  
> **PR_ATTACH_PATHNAME**或**PR_ATTACH_LONG_PATHNAME**属性包含标识附件的完全限定路径。 
    
ATTACH_EMBEDDED_MSG 
  
> **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性包含支持**IMessage**接口的嵌入的对象。 
    
ATTACH_OLE 
  
> 附件是嵌入的 OLE 对象。
    
ATTACH_BY_WEBREFERENCE 
  
> 附件内容不在邮件中。 
    
在创建时，所有的 attachment 对象具有**NO_ATTACHMENT** **PR_ATTACH_METHOD**初始值。 
  
客户端应用程序和服务提供程序只需支持**ATTACH_BY_VALUE**值表示的附件方法。 其他附件方法是可选的。 消息存储不强制实施的**PR_ATTACH_METHOD**值和其他附件属性的值之间的任何一致性。 
  
对于完全限定路径，应使用**ATTACH_BY_REF_ONLY** **ATTACH_BY_REFERENCE**与建议都使用通用命名约定 (UNC) 名称。 与**ATTACH_BY_REF_RESOLVE**，绝对路径快，原因是 MAPI 后台处理程序将转换为**ATTACH_BY_VALUE**附件。 
  
如果设置**ATTACH_BY_REFERENCE** ， **PR_ATTACH_DATA_BIN**必须为空。 出站的网关可以通过将附件数据复制到**PR_ATTACH_DATA_BIN**属性打开到**ATTACH_BY_VALUE**附件**ATTACH_BY_REFERENCE**附件。 
  
如果设置**ATTACH_BY_REF_RESOLVE** ， **PR_ATTACH_DATA_BIN**必须为空。 当发送包含**ATTACH_BY_REF_RESOLVE**附件的邮件时，MAPI 后台处理程序会将附件数据复制到**ATTACH_BY_VALUE**附件。 此解决方案过程置于**PR_ATTACH_DATA_BIN**附件数据。 
  
如果设置**ATTACH_BY_REF_ONLY** ， **PR_ATTACH_DATA_BIN**必须为空，并且将在邮件系统从不解析附件参考 （英文）。 您想要发送的链接，但不是数据时，请使用此值。 
  
OLE 2.0 **IStorage**格式 OLE 对象时，数据是可通过**PR_ATTACH_DATA_OBJ**访问。 OLE 1.0 **OLESTREAM**格式 OLE 对象时，则可以为**IStream**可通过**PR_ATTACH_DATA_BIN**访问数据。 可以通过**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 值确定的 OLE 编码类型。 
  
OLE 接口和格式的详细信息，请参阅*OLE 程序员参考*。 
  
## <a name="remarks"></a>注解

**ATTACH_BY_WEBREFERENCE** **PR_ATTACH_METHOD**后，附件内容不在邮件中。 相反，则**PR_ATTACH_LONG_FILENAME**属性包含附件内容，联机存储的绝对 URL。 
  
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



[PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

