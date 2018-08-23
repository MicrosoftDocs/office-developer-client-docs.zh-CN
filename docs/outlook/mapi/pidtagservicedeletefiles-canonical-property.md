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
ms.openlocfilehash: 236349a6b53eeb2f5c18c841c05cfb80a3fce824
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580220"
---
# <a name="pidtagservicedeletefiles-canonical-property"></a>PidTagServiceDeleteFiles 规范属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含文件名的要卸载邮件服务时删除的列表。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_SERVICE_DELETE_FILES，PR_SERVICE_DELETE_FILES_A，PR_SERVICE_DELETE_FILES_W  <br/> |
|标识符：  <br/> |0x3D10  <br/> |
|数据类型：  <br/> |PT_MV_STRING8 PT_MV_UNICODE  <br/> |
|区域：  <br/> |MAPI 配置文件  <br/> |
   
## <a name="remarks"></a>注解

使用控制面板卸载邮件服务时，将从计算机中删除这些属性中包含的列表中的文件名。 不包含在列表中支持多个邮件服务，任何 DLL 或其他邮件服务无法无意删除。
  
MAPI 仅适用于文件名，并在其他字符串传递给它，在 ANSI 字符集。 使用 OEM 字符集中的文件名的应用程序必须将其转换为 ANSI 调用 MAPI 之前。
  
## <a name="related-resources"></a>相关资源

### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为替代名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

