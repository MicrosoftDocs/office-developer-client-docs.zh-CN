---
title: PidTagProviderDllName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderDllName
api_type:
- COM
ms.assetid: 9ddb38eb-9a32-4dbe-b42c-6ea9db98acd2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 57fdc754ed4be29dbdd50a198707d8f39a14b3d4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286486"
---
# <a name="pidtagproviderdllname-canonical-property"></a>PidTagProviderDllName 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 MAPI 服务提供程序动态链接库的基本文件名 (DLL) 。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROVIDER_DLL_NAME、PR_PROVIDER_DLL_NAME_A、PR_PROVIDER_DLL_NAME_W  <br/> |
|标识符:  <br/> |0x300A  <br/> |
|数据类型：  <br/> |PT_STRING8、PT_UNICODE  <br/> |
|区域：  <br/> |MAPI common  <br/> |
   
## <a name="remarks"></a>备注

MAPI 使用 DLL 文件命名约定。 它将字符串 32 附加到基 DLL 名称以标识在 32 位平台上运行的版本。 例如，当MAPI.DLL名称时，MAPI 将构造名称MAPI32.DLL表示相应的 32 位版本的 DLL。
  
这些属性应指定基本名称。 MAPI 会在适当时追加字符串 32。 将字符串 32 作为此属性的一部分会导致错误。
  
## <a name="related-resources"></a>相关资源

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

