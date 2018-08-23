---
title: MAPI 传输提供程序对象
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 4f28fab8-2ce1-4398-a941-6d718c9bbd6a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: de0334ee9a90da38e472571314136195c84a7866
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592701"
---
# <a name="mapi-transport-provider-objects"></a>MAPI 传输提供程序对象
  
**适用于**： Outlook 2013 |Outlook 2016 
  
标准提供程序和所有服务提供程序都实现的登录对象中，除了传输提供程序实现所需状态对象。 对于其他服务提供程序类型，实现状态对象是可选的。 但是，MAPI 要求其传输提供程序。 支持下载邮件头从远程服务器的传输提供程序还实现文件夹和表。 
  
下图显示了每个传输提供程序可以实现与及其相应的接口的对象。 图还指示 MAPI 或客户端是否对象的用户。
  
![传输提供程序实现的对象](media/amapi_66.gif "传输提供程序实现的对象")
  
## <a name="see-also"></a>另请参阅

- [MAPI 服务提供商对象](mapi-service-provider-objects.md)

