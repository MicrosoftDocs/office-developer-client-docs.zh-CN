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
ms.openlocfilehash: a1df3ba8e57f1e91894b88d7e8a72feb681e13dc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777362"
---
# <a name="pidtagattachrendering-canonical-property"></a>PidTagAttachRendering 规范属性

  
  
**适用于**： Outlook 
  
包含附件的呈现信息与 Microsoft Windows 图元文件。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ATTACH_RENDERING  <br/> |
|标识符：  <br/> |0x3709  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |邮件附件  <br/> |
   
## <a name="remarks"></a>说明

此属性的用途是提供的图标或其他可在附件点父消息中显示的图形表示。 此类表示通常包括附件，如果有的名称和附件，如 Microsoft Office Word 文档的特性。 客户端应用程序可以在显示的邮件使用这种表示形式。 
  
附加文件，此属性通常描绘文件图标。 
  
对于附加消息，通常不设置此属性。 无需呈现附加的邮件客户端应用程序应获取其**PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) 属性，请指向相应的窗体信息对象的指针调用[IMAPIFormMgr::ResolveMessageClass](imapiformmgr-resolvemessageclass.md)打开[IMAPIFormInfo](imapiforminfoimapiprop.md)界面在该对象，并使用**GetProps**检索**PR_ICON** ([PidTagIcon](pidtagicon-canonical-property.md)) 或**PR_MINI_ICON** ([PidTagMiniIcon](pidtagminiicon-canonical-property.md)) 属性。 
  
静态 OLE 嵌入对象，此属性包含可用于在窗口中绘制的附件表示 Microsoft Windows 图元文件。 
  
对于嵌入动态 OLE 对象，客户应使用 OLE 数据生成呈现信息。 
  
在所有情况下，客户端应用程序应请注意，此属性通常是大小为多个几百个字节，受制截断附件表中。 如果希望此属性中的附件呈现而无需打开附件本身客户端，它必须工作表截断规则内。 有关详细信息，请参阅[处理大型列](working-with-large-columns.md)。 
  
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

