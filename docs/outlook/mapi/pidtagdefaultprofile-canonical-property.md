---
title: PidTagDefaultProfile 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDefaultProfile
api_type:
- HeaderDef
ms.assetid: 47f745a4-5a9c-42af-b076-a72548ef4d31
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8295ae6904f503ca831a00c1f35ac08596b5358c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428772"
---
# <a name="pidtagdefaultprofile-canonical-property"></a>PidTagDefaultProfile 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果邮件用户配置文件是 MAPI 的默认配置文件, 则该参数为 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DEFAULT_PROFILE  <br/> |
|标识符:  <br/> |0x3D04  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>说明

此属性不显示为任何对象的属性, 而只作为配置文件表中的一列。 客户端应用程序可以使用[IProfAdmin:: SetDefaultProfile](iprofadmin-setdefaultprofile.md)方法来指定默认配置文件。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagDefaultStore 规范属性](pidtagdefaultstore-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

