---
title: PidTagEmsAbServer 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagEmsAbServer
api_type:
- HeaderDef
ms.assetid: de942619-2507-8fe0-bc81-f9da9ef7266f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fba49b052a51bd498f61fc115f630d08fc6c8926
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335795"
---
# <a name="pidtagemsabserver-canonical-property"></a>PidTagEmsAbServer 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定脱机方案中通讯簿容器的路径或通讯簿容器驻留在联机方案中的全局编录服务器的完全限定域名。
  
## 

|||
|:-----|:-----|
|相关属性：  <br/> |PR_EMS_AB_SERVER、PR_EMS_AB_SERVER_A、PR_EMS_AB_SERVER_W  <br/> |
|标识符:  <br/> |0xFFFE  <br/> |
|数据类型：  <br/> |PT_TSTRING  <br/> |
|区域：  <br/> |通讯簿  <br/> |
   
## <a name="remarks"></a>备注

此属性将属性类型重置为PT_UNICODE  Unicode 平台上使用符号编译时，此属性将重置为 PT_STRING8，当未使用符号编译时，此属性将重置为 `UNICODE`  `UNICODE` 属性类型。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义。
    
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

