---
title: 网关可映射属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3a51ee7e-d030-4f04-915b-ff8bd351207d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6f1a399cac2adbae66dabf9383540bb089424d17
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430474"
---
# <a name="gateway-mappable-properties"></a>网关可映射属性

**适用于**：Outlook 2013 | Outlook 2016 
  
网关可映射属性是从一个邮件域发送到另一个邮件域时可能需要转换的属性。 MAPI 的网关可映射属性使邮件包含需要网关以确保目标邮件系统正确使用它的信息。 尽管网关开发人员不需要提供此转换功能，但他们应该将网关可映射属性视为改进邮件内容处理的机会。
  
MAPI 指定五种类型的网关可映射属性：
  
- 可分辨名称 (DN)
    
- 显示名称
    
- 电子邮件类型
    
- 条目标识符
    
- 搜索键
    
这是一组与收件人、发件人、报告收件人、委派的发件人和收件人关联的寻址属性。 为了帮助客户端定义这些属性，以便网关专门处理它们，MAPI 使用命名属性和属性集指定命名约定。 存在五个属性集来保留命名属性，即需要映射的寻址属性。 每种类型的可映射属性都有一个属性集。 将保留这些命名寻址属性的属性集如下所示。
  
|**属性集**|**说明**|
|:-----|:-----|
|PS_ROUTING_DISPLAY_NAME  <br/> |包含用作显示名称的字符串属性。  <br/> |
|PS_ROUTING_EMAIL_ADDRESSES  <br/> |包含用作电子邮件地址的字符串属性。  <br/> |
|PS_ROUTING_ADDRTYPE  <br/> |包含用作电子邮件地址类型的字符串属性。  <br/> |
|PS_ROUTING_ENTRYID  <br/> |包含用作长期条目标识符的二进制属性。  <br/> |
|PS_ROUTING_SEARCH_KEY  <br/> |包含用作搜索键的二进制属性。  <br/> |
   

