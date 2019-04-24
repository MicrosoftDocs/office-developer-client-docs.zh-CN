---
title: MAPI 传输提供程序对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4f28fab8-2ce1-4398-a941-6d718c9bbd6a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3f05e5b4b45e18d580737d37250e183c4cead881
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357372"
---
# <a name="mapi-transport-provider-objects"></a>MAPI 传输提供程序对象
  
**适用于**：Outlook 2013 | Outlook 2016 
  
除了由所有服务提供程序实现的标准提供程序和登录对象之外, 传输提供程序还需要实现 status 对象。 对于其他服务提供程序类型, 实现 status 对象是可选的。 但是, MAPI 对于传输提供程序是必需的。 支持从远程服务器下载邮件头的传输提供程序也实现一个文件夹和一个表。 
  
下图显示了传输提供程序可通过其对应接口实现的每个对象。 此图还指示 MAPI 或客户端是否为对象的用户。
  
![传输提供程序实现的对象](media/amapi_66.gif "传输提供程序实现的对象")
  
## <a name="see-also"></a>另请参阅

- [MAPI 服务提供程序对象](mapi-service-provider-objects.md)

