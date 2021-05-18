---
title: PidTagAttachRendering 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachRendering
api_type:
- HeaderDef
ms.assetid: 1f31f7f4-fbda-4337-95e5-5474dd1bf84a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 22d3e649641dbe688912ecece7fde73a555f4a88
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361094"
---
# <a name="pidtagattachrendering-canonical-property"></a>PidTagAttachRendering 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含一个 Microsoft Windows图元文件，其中包含附件的呈现信息。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_RENDERING  <br/> |
|标识符:  <br/> |0x3709  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>备注

此属性的目的是提供图标或其他十二点活字表示形式，可以在父邮件中的附件点显示。 此类表示形式通常包括附件的名称（如果有）和附件的性质，如Microsoft Office Word 文档。 客户端应用程序可以在消息的显示中使用此表示形式。 
  
对于附加的文件，此属性通常会显示该文件的图标。 
  
对于附加的邮件，通常不设置此属性。 需要呈现附加邮件的客户端应用程序应PR_MESSAGE_CLASS ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性， 调用 [IMAPIFormMgr：：ResolveMessageClass](imapiformmgr-resolvemessageclass.md)获取指向相应表单信息对象的指针，打开该对象上的 [IMAPIFormInfo](imapiforminfoimapiprop.md)接口，并使用 **GetProps** 检索 **PR_ICON** ( [PidTagIcon](pidtagicon-canonical-property.md)) 或 **PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性。 
  
对于嵌入的静态 OLE 对象，此属性包含一个 Microsoft Windows图元文件，该图元文件可用于在窗口中绘制附件表示形式。 
  
对于嵌入的动态 OLE 对象，客户端应该使用 OLE 数据生成呈现信息。 
  
在所有这些情况下，客户端应用程序都应了解此属性的大小通常为几百字节，并可能会截断附件表中的数据。 如果客户端希望从此属性呈现附件而不打开附件本身，则必须在表截断规则中工作。 有关详细信息，请参阅 [使用大列](working-with-large-columns.md)。 
  
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



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

