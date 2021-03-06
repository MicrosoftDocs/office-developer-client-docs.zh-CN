---
title: PidTagSubfolders 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSubfolders
api_type:
- COM
ms.assetid: b456b07b-4d83-46bf-a305-4f322ea7dbd1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8de14542c0d2a4e6d95fb4258697b827f82b8d06
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339247"
---
# <a name="pidtagsubfolders-canonical-property"></a>PidTagSubfolders 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果文件夹包含子文件夹，则包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SUBFOLDERS  <br/> |
|标识符:  <br/> |0x360A  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 容器  <br/> |
   
## <a name="remarks"></a>备注

邮件存储必须针对所有文件夹提供此属性。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> 处理文件夹操作。
    
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

