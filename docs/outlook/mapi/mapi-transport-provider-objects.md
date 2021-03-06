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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430355"
---
# <a name="mapi-transport-provider-objects"></a>MAPI 传输提供程序对象
  
**适用于**：Outlook 2013 | Outlook 2016 
  
除了由所有服务提供程序实现的标准提供程序和登录对象之外，需要传输提供程序来实现状态对象。 对于其他服务提供程序类型，实现 status 对象是可选的。 但是，MAPI 要求传输提供程序使用 MAPI。 支持从远程服务器下载邮件头的传输提供程序也实现文件夹和表。 
  
下图显示了传输提供程序可以使用其相应接口实现的每个对象。 此图还指示 MAPI 或客户端是对象的用户。
  
![传输提供程序实现的对象](media/amapi_66.gif "传输提供程序实现的对象")
  
## <a name="see-also"></a>另请参阅

- [MAPI 服务提供程序对象](mapi-service-provider-objects.md)

