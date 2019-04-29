---
title: PidTagProviderSubmitTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderSubmitTime
api_type:
- COM
ms.assetid: 9e5161d9-fefe-4a12-b7f7-5600f1d2e95b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c5e840250da7ba3b95150f2e83e1eb08b0c61ab5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409018"
---
# <a name="pidtagprovidersubmittime-canonical-property"></a>PidTagProviderSubmitTime 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含传输提供程序将邮件传递到其基础邮件系统的日期和时间。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROVIDER_SUBMIT_TIME  <br/> |
|标识符:  <br/> |0x0048  <br/> |
|数据类型：  <br/> |PT_SYSTIME  <br/> |
|区域：  <br/> |MAPI 信封  <br/> |
   
## <a name="remarks"></a>说明

此属性由传出传输提供程序在发送邮件时设置。
  
此属性对应于每封邮件一个 X 400 提交信封属性。 
  
## <a name="related-resources"></a>相关资源

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

