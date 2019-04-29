---
title: PidTagAssociatedSharingProvider 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 88a3356c-0b53-4401-8fcc-64071723c226
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 39d98972c22bd49549bf370ce1699b15cf1e27d2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408920"
---
# <a name="pidtagassociatedsharingprovider-canonical-property"></a>PidTagAssociatedSharingProvider 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确定是否将个人文件夹文件 (PST) 存储提供程序配置为 Microsoft SharePoint 2010 PST。
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_ASSOCIATED_SHARING_PROVIDER  <br/> |
|标识符:  <br/> |0x0EA00048  <br/> |
|数据类型：  <br/> |PT_CLSID  <br/> |
|区域：  <br/> |个人存储表 (.pst) 内部  <br/> |
   
## <a name="remarks"></a>说明

此属性指示是否为 Microsoft SharePoint 2010 配置了 PST。 如果该属性不存在, 则 pst 尚未配置为 Microsoft SharePoint 2010 PST。
  
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

