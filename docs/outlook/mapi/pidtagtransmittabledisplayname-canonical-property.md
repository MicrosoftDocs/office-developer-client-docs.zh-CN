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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396881"
---
# <a name="pidtagtransmittabledisplayname-canonical-property"></a>PidTagTransmittableDisplayName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含不能更改安全窗体中的收件人的显示名称。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_TRANSMITABLE_DISPLAY_NAME，PR_TRANSMITABLE_DISPLAY_NAME_A，PR_TRANSMITABLE_DISPLAY_NAME_W  <br/> |
|标识符：  <br/> |0x3A20  <br/> |
|数据类型：  <br/> |PT_UNICODE PT_STRING8  <br/> |
|区域：  <br/> |Address  <br/> |
   
## <a name="remarks"></a>说明

应通过所有通讯簿提供程序实现这些属性。 它们包含传输邮件的收件人的显示名称的版本。 对于大多数通讯簿提供程序这些属性具有相同的值的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性。 没有返回 PT_ERROR 和 MAPI 更改的显示名称通过添加引号将名称括起来的安全的显示名称的提供程序。
  
客户端应用程序可以使用此属性，防止篡改或"假"的项。 欺骗的示例作为 (什么 Guy) John Doe 传输 John Doe。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供了相关的 Exchange Server 协议规范参考。
    
[[MS OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定的属性和用户、 联系人、 组和资源的操作列表。
    
[[MS NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)
  
> 处理与名称服务提供程序界面 (NSPI) 服务器的客户端的通信。
    
[[MS OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理顺序和客户端和服务器之间的数据传输的流。
    
[[MS OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件的对象。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

