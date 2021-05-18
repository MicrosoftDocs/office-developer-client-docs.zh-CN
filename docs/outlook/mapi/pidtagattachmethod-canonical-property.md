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
description: 上次修改时间：2016 年 9 月 7 日
ms.openlocfilehash: b84549ab31c939b4e6115795916ebd3520a96dbd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327256"
---
# <a name="pidtagattachmethod-canonical-property"></a>PidTagAttachMethod 规范属性

 
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 MAPI 定义的常量，该常量代表可以访问附件内容的方式。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_METHOD  <br/> |
|标识符:  <br/> |0x3705  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>备注

此属性可以正好具有下列值之一：
  
NO_ATTACHMENT 
  
> 附件刚刚创建。 
    
ATTACH_BY_VALUE 
  
> [PidTagAttachDataBinary PR_ATTACH_DATA_BIN (PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 包含附件数据。  
    
ATTACH_BY_REFERENCE 
  
> PR_ATTACH_PATHNAME ([PidTagAttachPathname](pidtagattachpathname-canonical-property.md)) 或 **PR_ATTACH_LONG_PATHNAME** ([PidTagAttachLongPathname](pidtagattachlongpathname-canonical-property.md)) 属性包含一个完全限定的路径，该路径标识具有公用文件服务器访问权限的收件人的附件。  
    
ATTACH_BY_REF_RESOLVE 
  
> PR_ATTACH_PATHNAME 或 **PR_ATTACH_LONG_PATHNAME** 属性包含标识附件的完全限定路径。 
    
ATTACH_BY_REF_ONLY 
  
> PR_ATTACH_PATHNAME 或 **PR_ATTACH_LONG_PATHNAME** 属性包含标识附件的完全限定路径。 
    
ATTACH_EMBEDDED_MSG 
  
> The **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property contains an embedded object that supports the **IMessage** interface. 
    
ATTACH_OLE 
  
> 附件是一个嵌入的 OLE 对象。
    
ATTACH_BY_WEBREFERENCE 
  
> 附件内容不在邮件中。 
    
创建后，所有 attachment 对象的初始 **PR_ATTACH_METHOD值为****NO_ATTACHMENT**。 
  
客户端应用程序和服务提供商只需要支持由值表示的 attachment **ATTACH_BY_VALUE方法。** 其他附件方法是可选的。 邮件存储不会强制在 PR_ATTACH_METHOD **和其他附件** 属性的值之间保持一致。 
  
建议完全限定 (UNC) 名称的通用命名约定，该路径应该与 ATTACH_BY_REFERENCE **和****ATTACH_BY_REF_ONLY 一ATTACH_BY_REF_ONLY。** 使用 **ATTACH_BY_REF_RESOLVE，** 绝对路径速度更快，因为 MAPI 后台处理程序会将 **附件转换为** ATTACH_BY_VALUE。 
  
如果 **ATTACH_BY_REFERENCE，** 则 **PR_ATTACH_DATA_BIN** 必须为空。 出站网关可以通过将ATTACH_BY_REFERENCE数据复制到 ATTACH_BY_VALUE **属性，** 将邮件附件转换为 **PR_ATTACH_DATA_BIN附件。** 
  
如果 **ATTACH_BY_REF_RESOLVE，** 则 **PR_ATTACH_DATA_BIN** 必须为空。 发送包含附件附件ATTACH_BY_REF_RESOLVE，MAPI 后台处理程序将附件数据复制到一个 **ATTACH_BY_VALUE附件。**  此解决方案过程将附件 **数据PR_ATTACH_DATA_BIN。** 
  
如果 **ATTACH_BY_REF_ONLY，PR_ATTACH_DATA_BIN** 必须为空，并且邮件系统从不解析附件引用。 当你想要发送链接而不是数据时，请使用此值。 
  
当 OLE 对象采用 OLE 2.0 **IStorage** 格式时，可通过 PR_ATTACH_DATA_OBJ 访问 **数据**。 当 OLE 对象采用 OLE 1.0 **OLESTREAM** 格式时，可通过 **IStream PR_ATTACH_DATA_BIN访问数据**。 OLE 编码的类型可以通过[PidTagAttachTag PR_ATTACH_TAG (PidTagAttachTag](pidtagattachtag-canonical-property.md)) 确定。  
  
有关 OLE 接口和格式的信息，请参阅 *《OLE 程序员参考》。* 
  
## <a name="remarks"></a>备注

当 **PR_ATTACH_METHOD** 时 **ATTACH_BY_WEBREFERENCE，** 附件内容不在邮件中。 相反 **，PR_ATTACH_LONG_FILENAME** 属性包含指向联机存储的附件内容的绝对 URL。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagStoreSupportMask 规范属性](pidtagstoresupportmask-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

