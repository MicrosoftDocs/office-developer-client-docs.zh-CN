---
title: PidTagScheduleInfoDontMailDelegates 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagScheduleInfoDontMailDelegates
api_type:
- COM
ms.assetid: e932966e-cb7a-4d8b-8f06-6406fce1b3e6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f5965d75e72cecf11216ae785632f7e830a98178
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330105"
---
# <a name="pidtagscheduleinfodontmaildelegates-canonical-property"></a>PidTagScheduleInfoDontMailDelegates 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果代理不想接收更新，则包含 TRUE。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SCHDINFO_DONT_MAIL_DELEGATES  <br/> |
|标识符:  <br/> |0x6843  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |忙/闲  <br/> |
   
## <a name="remarks"></a>备注

此属性必须在委托信息对象中设置。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXOPFFB]](https://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)
  
> 发布用户或资源的可用性。
    
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

