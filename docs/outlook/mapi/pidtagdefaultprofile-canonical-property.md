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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 6cd255c60987ec7a279e509aa2925a8029cce62e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777518"
---
# <a name="pidtagdefaultprofile-canonical-property"></a>PidTagDefaultProfile 规范属性

  
  
**适用于**： Outlook 
  
如果邮件的用户配置文件的 MAPI 默认配置文件，包含 TRUE。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_DEFAULT_PROFILE  <br/> |
|标识符:  <br/> |0x3D04  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>备注

此属性不显示任何对象的属性但只能作为 profile 表中的列。 客户端应用程序可以使用[IProfAdmin::SetDefaultProfile](iprofadmin-setdefaultprofile.md)方法指定的默认配置文件。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[PidTagDefaultStore 规范属性](pidtagdefaultstore-canonical-property.md)


[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

