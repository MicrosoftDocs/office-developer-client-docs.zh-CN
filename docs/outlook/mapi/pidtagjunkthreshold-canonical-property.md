---
title: PidTagJunkThreshold 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagJunkThreshold
api_type:
- HeaderDef
ms.assetid: 8067e2b5-02df-4b96-8f66-509f5a48c8aa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 078dfcc7c24870cf95a2a4b2385c34fbeb64fac0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326850"
---
# <a name="pidtagjunkthreshold-canonical-property"></a>PidTagJunkThreshold 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
指示应如何将主动传入的邮件发送到"垃圾邮件"文件夹。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_JUNK_THRESHOLD  <br/> |
|标识符:  <br/> |0x6101  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |垃圾邮件  <br/> |
   
## <a name="remarks"></a>备注

此属性对应于高/低/无筛选器设置。 值"0xFFFFFFFF"表示不应应用垃圾邮件筛选，但是仍必须应用阻止列表。 值"0x80000000"表示所有邮件都是垃圾邮件，但来自受信任发件人列表发件人的邮件或发送到受信任收件人列表上的收件人的邮件除外。 其值如下所示：
  
|**值**|**说明**|
|:-----|:-----|
|0xFFFFFFFF  <br/> |无垃圾邮件筛选  <br/> |
|0x00000006  <br/> |低垃圾邮件筛选  <br/> |
|0x00000003  <br/> |高垃圾邮件筛选  <br/> |
|0x80000000  <br/> |仅受信任列表  <br/> |
   
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXCSPAM]](https://msdn.microsoft.com/library/522f8587-4aed-4cd6-831b-40bd87862189%28Office.15%29.aspx)
  
> 允许/阻止列表的处理和垃圾邮件的确定。
    
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

