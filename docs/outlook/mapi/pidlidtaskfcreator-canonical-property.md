---
title: PidLidTaskFCreator 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskFCreator
api_type:
- COM
ms.assetid: bb88750b-4773-4241-aa38-462a2634dbcb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dfb49fafcc2dc368e84786b526869e0447ccaf8c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303078"
---
# <a name="pidlidtaskfcreator-canonical-property"></a>PidLidTaskFCreator 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示任务最初是由当前用户或用户代理创建的，而不是通过处理任务请求创建的。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskFCreator  <br/> |
|属性集：  <br/> |PSETID_Task  <br/> |
|LONG ID (的一) ：  <br/> |0x0000811E  <br/> |
|数据类型：  <br/> |PT_BOOLEAN  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>备注

当用户创建任务时，客户端将此属性设置为 TRUE;如果任务由另一个用户分配，则此属性将设置为 FALSE。 如果该属性未设置，则假定值为 TRUE。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> 定义几个对象，这些对象对任务、任务分配和任务更新的电子等效项建模。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

