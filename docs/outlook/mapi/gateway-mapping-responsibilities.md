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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342796"
---
# <a name="gateway-mapping-responsibilities"></a>网关映射责任

**适用于**：Outlook 2013 | Outlook 2016 
  
当 MAPI 感知网关收到一封包含命名属性的邮件时, 如果指定了包含网关可映射属性的某个特殊属性集, 该网关应将所有属性映射到目标邮件系统的协议。 虽然 MAPI 建议在特殊属性集中处理所有命名属性, 但网关应仅处理两个: 电子邮件地址和地址类型。 由于电子邮件地址和地址类型属性直接影响邮件传输, 因此网关支持这两个属性的映射是非常重要的。 由于搜索关键字由用户的地址类型和地址组成, 因此还应转换它们 (如果可能)。
  
条目标识符不应经常处理。 若要使在一个邮件系统中出现的条目标识符映射到另一个邮件系统可用的条目标识符, 网关必须能够使用这两个系统的格式。 由于大多数网关都不知道条目标识符格式, 因此条目标识符的转换很少。
  
不希望频繁转换的另一个可映射属性是显示名称。 网关应存储显示名称并传输它们, 但不一定要进行转换。 
  

