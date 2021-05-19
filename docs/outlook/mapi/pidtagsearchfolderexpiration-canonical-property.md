---
title: PidTagSearchFolderExpiration 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSearchFolderExpiration
api_type:
- COM
ms.assetid: e5746090-c850-4e95-b1e7-a07e42c87179
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a119bb735f752719d292371d4dc43e72450b33c0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336468"
---
# <a name="pidtagsearchfolderexpiration-canonical-property"></a>PidTagSearchFolderExpiration 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含搜索文件夹容器过期的时间，应进行更新或重新创建。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_WB_SF_EXPIRATION  <br/> |
|标识符:  <br/> |0x683A  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |搜索  <br/> |
   
## <a name="remarks"></a>备注

此属性必须设置为自 1601 年 1 月 1 日午夜协调世界时 (UTC) 分钟数。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)
  
> 指定用于操作搜索文件夹列表配置的属性和操作。
    
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

