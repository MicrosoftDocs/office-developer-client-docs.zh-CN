---
title: PidTagChildrensNames 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagChildrensNames
api_type:
- HeaderDef
ms.assetid: 5e09c078-b8e4-46ef-9ee7-e2ba937d53cf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 77c344d2561de1204d24cfcde91ada3f6d7c9a8f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336818"
---
# <a name="pidtagchildrensnames-canonical-property"></a>PidTagChildrensNames 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含子项名称的列表
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_CHILDRENS_NAMES、PR_CHILDRENS_NAMES_A、PR_CHILDRENS_NAMES_W  <br/> |
|标识符:  <br/> |0x3A58  <br/> |
|数据类型：  <br/> |PT_MV_UNICODE、PT_MV_STRING8  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>备注

这些属性由用户或用户的组织定义。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定联系人和个人通讯组列表对象允许的属性和操作。
    
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

