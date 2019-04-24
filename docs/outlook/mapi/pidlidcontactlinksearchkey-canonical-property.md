---
title: PidLidContactLinkSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidContactLinkSearchKey
api_type:
- COM
ms.assetid: 82d21d38-a6c6-4e12-85b1-8158b2f5cce7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ea815631f63b5585a3f2705cfbd2639b8c655e6e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32319773"
---
# <a name="pidlidcontactlinksearchkey-canonical-property"></a>PidLidContactLinkSearchKey 规范属性

**适用于**：Outlook 2013 | Outlook 2016 
  
包含此邮件对象链接到的联系人的**SearchKeys**列表。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |dispidContactLinkSearchKey  <br/> |
|属性集:  <br/> |PSETID_Common  <br/> |
|长 ID (盖子):  <br/> |0x00008584  <br/> |
|数据类型：  <br/> |PT_BINARY  <br/> |
|区域：  <br/> |Contact  <br/> |
   
## <a name="remarks"></a>注解

|**长度 (字节数)**|**说明**|**注释**|
|:-----|:-----|:-----|
|双面  <br/> |ContactEntryCount  <br/> |无  <br/> |
|变量  <br/> |SearchKey 数据  <br/> |重复 ContactEntryCount 时间  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供属性集定义和对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
## <a name="see-also"></a>另请参阅

- [MAPI 属性](mapi-properties.md) 
- [MAPI 规范属性](mapi-canonical-properties.md)
- [将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
- [将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

