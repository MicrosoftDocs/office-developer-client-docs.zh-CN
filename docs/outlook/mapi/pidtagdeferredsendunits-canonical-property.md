---
title: PidTagDeferredSendUnits 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDeferredSendUnits
api_type:
- HeaderDef
ms.assetid: 2386be9f-18c9-4949-a2aa-efc8e212801c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: becc076efe0f4f805eb2a8db071b70ad731ee256
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359904"
---
# <a name="pidtagdeferredsendunits-canonical-property"></a>PidTagDeferredSendUnits 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定**PR_DEFERRED_SEND_NUMBER** ([PidTagDeferredSendNumber](pidtagdeferredsendnumber-canonical-property.md)) 属性值应相乘的时间单位。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_DEFERRED_SEND_UNITS  <br/> |
|标识符:  <br/> |0x3FEC  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |MAPI 状态  <br/> |
   
## <a name="remarks"></a>注解

如果设置, 则此属性必须具有下列值之一:
  
|||
|:-----|:-----|
|**PidTagDeferredSendUnits** <br/> |说明  <br/> |
|0  <br/> |分钟, 例如, 60 秒  <br/> |
|1  <br/> |小时数, 例如60x60 秒  <br/> |
|双面  <br/> |天, 例如24x60x60 秒  <br/> |
|第三章  <br/> |周, 例如7x24x60x60 秒  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许用于电子邮件对象的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为替换名称的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

