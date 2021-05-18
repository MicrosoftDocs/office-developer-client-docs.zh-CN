---
title: PidLidContactCharacterSet 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidContactCharacterSet
api_type:
- COM
ms.assetid: a167e199-a9b2-47f9-a90e-2abc7c29828c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0329147463db38fb8c547214788366444daed312
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319703"
---
# <a name="pidlidcontactcharacterset-canonical-property"></a>PidLidContactCharacterSet 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指定用于此联系人的字符集。
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidContactCharSet  <br/> |
|属性集：  <br/> |PSETID_Address  <br/> |
|LONG ID (的一) ：  <br/> |0x00008023  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |联系人  <br/> |
   
## <a name="remarks"></a>备注

应用程序可以使用此属性帮助为 **dispidFileUnder** ([PidLidFileUnder](pidlidfileunder-canonical-property.md)) 、dispidFileUnderList ([PidLidFileUnderList](pidlidfileunderlist-canonical-property.md)) 和 **dispidFileUnderId** ([PidLidFileUnderId](pidlidfileunderid-canonical-property.md)) 属性生成与字符集相关的选项列表。  如果属性的值为"0x00000000"或"0x00000001"，则应用程序应该将该属性视为未设置。
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关协议规范Exchange Server引用。
    
[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> 指定联系人和个人通讯组列表允许的属性和操作。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

