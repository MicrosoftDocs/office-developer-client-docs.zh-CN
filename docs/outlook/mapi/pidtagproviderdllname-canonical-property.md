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
ms.openlocfilehash: d75f22af3f8c9184da55ec57e08cf4db832ed174
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778080"
---
# <a name="pidtagproviderdllname-canonical-property"></a>PidTagProviderDllName 规范属性

  
  
**适用于**： Outlook 
  
包含基文件名的 MAPI 服务提供程序动态链接库 (DLL)。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_PROVIDER_DLL_NAME，PR_PROVIDER_DLL_NAME_A，PR_PROVIDER_DLL_NAME_W  <br/> |
|标识符：  <br/> |0x300A  <br/> |
|数据类型：  <br/> |PT_STRING8 PT_UNICODE  <br/> |
|区域：  <br/> |常见的 MAPI  <br/> |
   
## <a name="remarks"></a>说明

MAPI 使用 DLL 文件命名约定。 基文件名包含唯一标识 DLL 的最多包含 6 个字符。 MAPI 将字符串 32 追加到基的 DLL 名称，来确定在 32 位平台运行的版本。 例如，当 MAPI 的名称。指定 DLL，MAPI 构造 MAPI32 的名称。表示的 dll 的相应 32 位版本的 DLL。
  
这些属性应指定的基名称。 MAPI 将根据 32 字符串。 此属性将导致出错的一部分包括 32 的字符串。
  
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

