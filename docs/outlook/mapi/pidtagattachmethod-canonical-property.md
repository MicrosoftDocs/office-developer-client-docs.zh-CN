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
description: 上次修改时间:07 年9月2016
ms.openlocfilehash: b84549ab31c939b4e6115795916ebd3520a96dbd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327256"
---
# <a name="pidtagattachmethod-canonical-property"></a>PidTagAttachMethod 规范属性

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 MAPI 定义的常量, 该常量代表可访问附件内容的方式。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_METHOD  <br/> |
|标识符:  <br/> |0x3705  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>注解

此属性可以具有下列值之一:
  
NO_ATTACHMENT 
  
> 附件刚刚创建。 
    
ATTACH_BY_VALUE 
  
> **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性包含附件数据。 
    
ATTACH_BY_REFERENCE 
  
> **PR_ATTACH_PATHNAME** ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 或**PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) 属性包含一个完全限定路径, 用于标识收件人可访问公用文件的附件服务器主板. 
    
ATTACH_BY_REF_RESOLVE 
  
> **PR_ATTACH_PATHNAME**或**PR_ATTACH_LONG_PATHNAME**属性包含标识附件的完全限定路径。 
    
ATTACH_BY_REF_ONLY 
  
> **PR_ATTACH_PATHNAME**或**PR_ATTACH_LONG_PATHNAME**属性包含标识附件的完全限定路径。 
    
ATTACH_EMBEDDED_MSG 
  
> **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性包含一个支持**IMessage**接口的嵌入对象。 
    
ATTACH_OLE 
  
> 附件是嵌入的 OLE 对象。
    
ATTACH_BY_WEBREFERENCE 
  
> 附件内容不在邮件中。 
    
创建后, 所有附件对象的初始**PR_ATTACH_METHOD**值均为**NO_ATTACHMENT**。 
  
客户端应用程序和服务提供程序只需支持**ATTACH_BY_VALUE**值所表示的附件方法。 其他附件方法是可选的。 邮件存储不强制**PR_ATTACH_METHOD**的值与其他附件属性的值之间的一致性。 
  
对于完全限定的路径, 建议使用通用命名约定 (UNC) 名称, 该名称应与**ATTACH_BY_REFERENCE**和**ATTACH_BY_REF_ONLY**一起使用。 使用**ATTACH_BY_REF_RESOLVE**, 绝对路径速度更快, 因为 MAPI 后台处理程序将附件转换为**ATTACH_BY_VALUE**。 
  
如果设置了**ATTACH_BY_REFERENCE** , 则**PR_ATTACH_DATA_BIN**必须为空。 出站网关可以通过将附件数据复制到**PR_ATTACH_DATA_BIN**属性, 将**ATTACH_BY_REFERENCE**附件转换为**ATTACH_BY_VALUE**附件。 
  
如果设置了**ATTACH_BY_REF_RESOLVE** , 则**PR_ATTACH_DATA_BIN**必须为空。 当发送包含**ATTACH_BY_REF_RESOLVE**附件的邮件时, MAPI 后台处理程序会将附件数据复制到**ATTACH_BY_VALUE**附件中。 此解析过程将附件数据放在**PR_ATTACH_DATA_BIN**中。 
  
如果设置了**ATTACH_BY_REF_ONLY** , 则**PR_ATTACH_DATA_BIN**必须为空, 并且邮件系统永远不会解析附件引用。 如果要发送链接, 而不是数据, 则使用此值。 
  
如果 ole 对象采用的是 ole 2.0 **IStorage**格式, 则可以通过**PR_ATTACH_DATA_OBJ**访问该数据。 如果 ole 对象采用的是 ole 1.0 **OLESTREAM**格式, 则可以通过**PR_ATTACH_DATA_BIN**作为**IStream**访问数据。 可以通过**PR_ATTACH_TAG** ([PidTagAttachTag](pidtagattachtag-canonical-property.md)) 值确定 OLE 编码的类型。 
  
有关 ole 接口和格式的详细信息, 请参阅*ole 程序员参考*。 
  
## <a name="remarks"></a>注解

当**PR_ATTACH_METHOD**为**ATTACH_BY_WEBREFERENCE**时, 附件内容不在邮件中。 相反, **PR_ATTACH_LONG_FILENAME**属性包含附件内容的绝对 URL, 该 URL 存储在联机状态。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

