---
title: PidTagComment 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagComment
api_type:
- HeaderDef
ms.assetid: 5750cf95-8581-43a7-a465-f4114b2939f2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7226996d85a1f919cfa54d588c04116dd2d24375
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336804"
---
# <a name="pidtagcomment-canonical-property"></a>PidTagComment 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含有关对象的用途或内容的注释。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_COMMENT、PR_COMMENT_A、PR_COMMENT_W  <br/> |
|标识符:  <br/> |0x3004  <br/> |
|数据类型：  <br/> |PT_UNICODE、PT_STRING8  <br/> |
|区域：  <br/> |常见  <br/> |
   
## <a name="remarks"></a>备注

字符串的内容由消息传递用户定义。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> 处理文件夹操作。
    
[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)
  
> 指定核心邮件存储对象的允许操作。
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源的列表的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidef.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为关联属性列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

