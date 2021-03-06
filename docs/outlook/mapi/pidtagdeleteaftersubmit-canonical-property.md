---
title: PidTagDeleteAfterSubmit 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeleteAfterSubmit
api_type:
- HeaderDef
ms.assetid: ba69a557-120c-4b1e-bbb7-0e901e7d1ebf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2708d89e2572e8820de0b525b4f53ccd309ae2a0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359911"
---
# <a name="pidtagdeleteaftersubmit-canonical-property"></a>PidTagDeleteAfterSubmit 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果客户端应用程序希望 MAPI 在提交后删除关联的邮件，则包含 TRUE。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DELETE_AFTER_SUBMIT  <br/> |
|标识符:  <br/> |0x0E01  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 不可传输  <br/> |
   
## <a name="remarks"></a>备注

客户端应用程序使用此属性和 PR_SENTMAIL_ENTRYID  ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性来控制邮件提交后会发生什么情况。 应设置其中一个，但不能同时设置两者。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)
  
> 指定核心邮件存储对象的允许操作。
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定电子邮件对象允许的属性和操作。
    
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

