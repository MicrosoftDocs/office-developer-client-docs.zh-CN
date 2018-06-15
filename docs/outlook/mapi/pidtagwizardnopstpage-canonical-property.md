---
title: PidTagWizardNoPstPage 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagWizardNoPstPage
api_type:
- COM
ms.assetid: 1ac09578-892b-4c72-92f6-c2419ac2efe8
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b94e1f2d66f89d680cc738968342de0fbcee5cda
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19778539"
---
# <a name="pidtagwizardnopstpage-canonical-property"></a>PidTagWizardNoPstPage 规范属性

  
  
**适用于**： Outlook 
  
禁止在个人消息存储 (PST) 页配置文件向导时，此属性包含 TRUE。
  
|||
|:-----|:-----|
|关联的属性：  <br/> |PR_WIZARD_NO_PST_PAGE  <br/> |
|标识符:  <br/> |0x6700  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Exchange 管理  <br/> |
   
## <a name="remarks"></a>备注

调用基于[LAUNCHWIZARDENTRY](launchwizardentry.md)函数原型的函数时，服务提供商可以设置该属性。 此属性会通知配置文件向导提供程序不希望 PST 页上，在用户对话框显示。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[映射到 MAPI 名称的规范属性名称](mapping-canonical-property-names-to-mapi-names.md)
  
[MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

