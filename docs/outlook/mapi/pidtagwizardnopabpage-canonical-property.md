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
ms.openlocfilehash: cdb7dde4853188eb0621dc3c2f45c2dc713441d3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22570238"
---
# <a name="pidtagwizardnopabpage-canonical-property"></a>PidTagWizardNoPabPage 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
若要隐藏个人通讯簿 (PAB) 页配置文件向导时，此属性包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_WIZARD_NO_PAB_PAGE  <br/> |
|标识符：  <br/> |0x6701  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |Exchange 管理  <br/> |
   
## <a name="remarks"></a>注解

调用基于[LAUNCHWIZARDENTRY](launchwizardentry.md)函数原型的函数时，服务提供商可以设置该属性。 此属性会通知配置文件向导提供程序不希望 PAB 页后，可以在用户对话框显示。 
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含列为相关属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

