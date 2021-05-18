---
title: PidTagBodyHtml 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagBodyHtml
api_type:
- HeaderDef
ms.assetid: 93b9215a-5900-411c-a0ae-6bba62cd5a1e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6ed59228ee06a1d3e362115a99bf4b859dfeb698
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359043"
---
# <a name="pidtagbodyhtml-canonical-property"></a>PidTagBodyHtml 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含超文本标记 (HTML) 版本的邮件文本。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_BODY_HTML、PR_BODY_HTML_A、PR_BODY_HTML_W  <br/> |
|标识符:  <br/> |0x1013  <br/> |
|数据类型：  <br/> |PT_UNICODE、PT_STRING8  <br/> |
|区域：  <br/> |常规消息  <br/> |
   
## <a name="remarks"></a>备注

这些属性包含的邮件文本与[PidTagBodyContentLocation](pidtagbodycontentlocation-canonical-property.md) PR_BODY_CONTENT_LOCATION (相同，) HTML 格式。  
  
支持 HTML 的邮件存储通过在其 STORE_HTML_OK [PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md) PR_STORE_SUPPORT_MASK (标记来指示) 。   
  
 **请注意****STORE_HTML_OK** Microsoft® Exchange 2000 Server 及更早版本中未定义 Mapidefs.h 版本。 如果 **STORE_HTML_OK** 未定义，请改为使用0x00010000值。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
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

