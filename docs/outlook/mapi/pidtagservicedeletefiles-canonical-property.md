---
title: PidTagServiceDeleteFiles 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceDeleteFiles
api_type:
- COM
ms.assetid: 9ec80a93-9e8f-46be-a1d4-7648aae47fec
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: da01385f83d9af9ad02eeb2fed08e3bc22d4df84
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436823"
---
# <a name="pidtagservicedeletefiles-canonical-property"></a>PidTagServiceDeleteFiles 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含在卸载邮件服务时要删除的文件名的列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SERVICE_DELETE_FILES、PR_SERVICE_DELETE_FILES_A、PR_SERVICE_DELETE_FILES_W  <br/> |
|标识符:  <br/> |0x3D10  <br/> |
|数据类型：  <br/> |PT_MV_STRING8、PT_MV_UNICODE  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>说明

使用 "控制面板" 卸载邮件服务时, 这些属性中包含的列表中的文件名将从计算机中删除。 请勿在列表中包含任何支持多个邮件服务的 DLL, 或者可能无意中删除了其他邮件服务。
  
MAPI 仅适用于文件名以及在 ANSI 字符集中传递给它的其他字符串。 使用 OEM 字符集中的文件名的应用程序必须先将其转换为 ANSI, 然后再调用 MAPI。
  
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

