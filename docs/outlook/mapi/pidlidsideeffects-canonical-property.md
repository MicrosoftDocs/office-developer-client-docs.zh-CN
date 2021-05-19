---
title: PidLidSideEffects 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSideEffects
api_type:
- COM
ms.assetid: 90d601d9-5eeb-40b6-885d-ccd8a95ae322
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2d57e6a195036ead9eb42666876e91a72f65eb8b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331295"
---
# <a name="pidlidsideeffects-canonical-property"></a>PidLidSideEffects 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
控制客户端在处理最终用户输入时如何处理消息对象。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidSideEffects  <br/> |
|属性集：  <br/> |PSETID_Common  <br/> |
|LONG ID (的一) ：  <br/> |0x00008510  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |运行时配置  <br/> |
   
## <a name="remarks"></a>备注

必须设置为位或零个或多个以下标志。
  
|**名称**|**值**|**说明**|
|:-----|:-----|:-----|
|seOpenToDelete  <br/> |0x0001  <br/> |删除邮件对象时，需要额外的处理。  <br/> |
|seNoFrame  <br/> |0x0008  <br/> |没有 UI 与 message 对象关联。  <br/> |
|seCoerceToInbox  <br/> |0x0010  <br/> |当使用 IPF 的 PR_CONTAINER_CLASS ([PidTagContainerClass](pidtagcontainerclass-canonical-property.md)) 移动或复制到文件夹对象时，需要对邮件对象进行其他处理。 注意"。  <br/> |
|seOpenTocopy  <br/> |0x0020  <br/> |复制到另一个文件夹时，需要对邮件对象进行其他处理。  <br/> |
|seOpenToMove  <br/> |0x0040  <br/> |移动到另一个文件夹时，需要对邮件对象进行其他处理。  <br/> |
|seOpenForCtxMenu  <br/> |0x0100  <br/> |向最终用户显示谓词时，需要对 message 对象进行其他处理。  <br/> |
|seCannotUndoDelete  <br/> |0x0400  <br/> |不能撤消删除操作，除非设置了"seOpenToDelete"，否则不能设置。  <br/> |
|seCannotUndoCopy  <br/> |0x0800  <br/> |不能撤消复制操作，除非设置了"seOpenTocopy"，否则不能设置。  <br/> |
|seCannotUndoMove  <br/> |0x1000  <br/> |不能撤消移动操作，除非设置了"seOpenToMove"，否则不能设置。  <br/> |
|seHasScript  <br/> |0x2000  <br/> |message 对象包含最终用户脚本。  <br/> |
|seOpenToPermDelete  <br/> |0x4000  <br/> |若要永久删除邮件对象，需要其他处理。  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议Exchange Server引用。
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> 指定约会、会议请求和响应邮件的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

