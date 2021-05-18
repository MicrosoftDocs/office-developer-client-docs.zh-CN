---
title: PidLidTaskLastUser 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskLastUser
api_type:
- COM
ms.assetid: 914c55e9-cb36-46a4-b5ee-382413fa25f9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 76311a76001b122bdfd984b9dedc37c2ff878fc7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360443"
---
# <a name="pidlidtasklastuser-canonical-property"></a>PidLidTaskLastUser 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
命名作为任务所有者的最新用户。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidTaskLastUser  <br/> |
|属性集：  <br/> |PSETID_Task  <br/> |
|LONG ID (的一) ：  <br/> |0x00008122  <br/> |
|数据类型：  <br/> |PT_UNICODE  <br/> |
|区域：  <br/> |任务  <br/> |
   
## <a name="remarks"></a>备注

在客户端发送任务请求之前，它会将此属性设置为任务分配者的名称。 在客户端发送任务接受之前，它会将此属性设置为任务受理人的名称。 在客户端发送任务拒绝之前，它会将此属性设置为任务分配者的名称。
  
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

