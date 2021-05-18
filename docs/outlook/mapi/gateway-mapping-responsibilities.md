---
title: 网关映射责任
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ac67bb83-e4f3-4c82-995b-c11a2a195e90
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 214d24bb0b0af525d5e2588c556c37cf720364a0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422752"
---
# <a name="gateway-mapping-responsibilities"></a>网关映射责任

**适用于**：Outlook 2013 | Outlook 2016 
  
当 MAPI 感知网关收到一条消息，其中包含指定包含网关可映射属性的特殊属性集之一中的命名属性时，网关应当将所有属性映射到目标邮件系统的协议。 尽管 MAPI 建议网关处理特殊属性集内的所有命名属性，但网关应只处理两个：电子邮件地址和地址类型。 由于电子邮件地址和地址类型属性直接影响邮件传输，因此网关支持这两个属性的映射至关重要。 因为搜索键由用户的地址类型和地址组成，所以如果可能，也应翻译它们。
  
不应经常处理条目标识符。 若要启用源自一个邮件系统的条目标识符到另一个邮件系统可使用的条目标识符的映射，网关必须能够使用这两个系统的格式。 由于大多数网关不知道条目标识符格式，因此条目标识符的转换很少见。
  
另一个不应频繁翻译的可映射属性是显示名称。 网关应存储显示名称并传输它们，但不一定转换它们。 
  

