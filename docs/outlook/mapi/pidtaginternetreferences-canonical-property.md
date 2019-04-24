---
title: PidTagInternetReferences 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagInternetReferences
api_type:
- HeaderDef
ms.assetid: 645fe61d-414a-455e-b034-db3cfd003b9d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 431a212b6e024d695fe2de084080996d8b1054d6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360408"
---
# <a name="pidtaginternetreferences-canonical-property"></a>PidTagInternetReferences 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含多用途 Internet 邮件扩展 (MIME) 邮件的引用标头字段的值。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_INTERNET_REFERENCES、PR_INTERNET_REFERENCES_A、PR_INTERNET_REFERENCES_W  <br/> |
|标识符:  <br/> |0x1039  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MIME  <br/> |
   
## <a name="remarks"></a>注解

若要生成引用头字段, 客户端必须将这些属性设置为所需的值。 MIME 编写器必须将这些属性的值复制到 "引用标题" 字段中。
  
若要设置这些属性的值, MIME 客户端必须将所需的值写入引用头字段。 MIME 读取器必须将 "引用头" 字段的值复制到这些属性中。 如果 MIME 读取器长度超过 64kb, 则它们可能会截断这些属性的值。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

