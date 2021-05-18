---
title: PidTagAssistant 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAssistant
api_type:
- HeaderDef
ms.assetid: 24892aff-5a98-4d61-b740-17f74f8ae95d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 855e40052cdeec0f3e12cb2fab8c808c5b715544
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327941"
---
# <a name="pidtagassistant-canonical-property"></a>PidTagAssistant 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含收件人的管理助理的名称。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ASSISTANT、PR_ASSISTANT_A、PR_ASSISTANT_W  <br/> |
|标识符:  <br/> |0x3A30  <br/> |
|数据类型：  <br/> |PT_UNICODE、PT_STRING8  <br/> |
|区域：  <br/> |地址  <br/> |
   
## <a name="remarks"></a>备注

这些属性为收件人提供标识和访问信息。 它们由收件人及其组织定义。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定联系人和个人通讯组列表对象允许的属性和操作。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagAssistantTelephoneNumber 规范属性](pidtagassistanttelephonenumber-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

