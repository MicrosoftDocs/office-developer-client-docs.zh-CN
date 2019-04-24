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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e816af2ce60b4c06ae14f720cf7c36d58468d09d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350720"
---
# <a name="pidtagwizardnopstpage-canonical-property"></a>PidTagWizardNoPstPage 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果配置文件向导要禁止显示个人邮件存储 (PST) 页, 则此属性包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_WIZARD_NO_PST_PAGE  <br/> |
|标识符:  <br/> |0x6700  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Exchange 管理  <br/> |
   
## <a name="remarks"></a>注解

服务提供程序在调用基于[LAUNCHWIZARDENTRY](launchwizardentry.md)函数原型的函数时, 可以设置此属性。 此属性告知配置文件向导, 提供程序不希望在用户对话框期间显示 PST 页面。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

