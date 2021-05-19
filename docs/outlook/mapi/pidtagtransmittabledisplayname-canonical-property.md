---
title: PidTagTransmittableDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTransmittableDisplayName
api_type:
- COM
ms.assetid: aadd9086-b936-4067-bf7d-f54fc50e3c83
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e66fe8d3621c122ccc19bdde169f20f7d47a148d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331855"
---
# <a name="pidtagtransmittabledisplayname-canonical-property"></a>PidTagTransmittableDisplayName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含收件人的显示名称窗体中无法更改的安全窗体。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_TRANSMITABLE_DISPLAY_NAME、PR_TRANSMITABLE_DISPLAY_NAME_A、PR_TRANSMITABLE_DISPLAY_NAME_W  <br/> |
|标识符:  <br/> |0x3A20  <br/> |
|数据类型：  <br/> |PT_UNICODE、PT_STRING8  <br/> |
|区域：  <br/> |地址  <br/> |
   
## <a name="remarks"></a>备注

这些属性应该由所有通讯簿提供程序实现。 它们包含随邮件传输显示名称收件人邮箱的版本。 对于大多数通讯簿提供程序，这些属性具有与[PidTagDisplayName](pidtagdisplayname-canonical-property.md) PR_DISPLAY_NAME (相同的) 值。  没有安全密码的提供程序显示名称返回PT_ERROR MAPI 会显示名称名称周围添加引号来更改该名称。
  
客户端应用程序可以使用此属性防止更改或"欺骗"条目。 欺骗的一个示例是将 John Doe 作为 John (What a 一个) Doe。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
[[MS-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)
  
> 处理客户端与 NSPI 服务器的名称服务提供程序 (的通信) 。
    
[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理客户端和服务器之间数据传输的顺序和流。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

