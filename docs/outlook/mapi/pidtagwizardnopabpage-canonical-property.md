---
title: PidTagWizardNoPabPage 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagWizardNoPabPage
api_type:
- COM
ms.assetid: 9cec22cd-798d-41f6-9ebd-c7354f2162c2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fc971be76dbaa83176f207411f9f125ffee386cf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424460"
---
# <a name="pidtagwizardnopabpage-canonical-property"></a>PidTagWizardNoPabPage 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果配置文件向导要禁止在 PAB 页中显示个人通讯簿， (TRUE) TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_WIZARD_NO_PAB_PAGE  <br/> |
|标识符:  <br/> |0x6701  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Exchange管理  <br/> |
   
## <a name="remarks"></a>备注

当基于 [LAUNCHWIZARDENTRY](launchwizardentry.md) 函数原型调用函数时，服务提供商可以设置此属性。 此属性告知配置文件向导提供程序不希望在用户对话框期间显示 PAB 页。 
  
## <a name="related-resources"></a>相关资源

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

