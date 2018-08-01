---
title: MAPI 地址簿提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ead51434-ae19-4c34-aa7a-bdeeccca5bd9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4bd64aadd5fc18ba79a8717a5c58df72cd3695ff
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776176"
---
# <a name="mapi-address-book-provider-overview"></a>MAPI 地址簿提供程序概述
  
**适用于**： Outlook 
  
通讯簿提供程序的句柄访问目录信息。 目录信息包括两种类型的邮件的收件人数据： 单个消息的用户和组的邮件用户通常在通讯组列表一起讨论。 根据收件人和通讯簿提供程序的类型，没有各种各样的可提供的信息。 例如，所有通讯簿提供程序都存储收件人的姓名、 地址和地址类型。
  
每个通讯簿提供程序将此数据组织使用一个或多个容器。 数量和结构的容器取决于通讯簿提供程序的实现。 例如，一个通讯簿提供程序可能使用单个容器保留的所有信息，另一个可能都使用一个包含子容器的顶级容器和第三个可以都使用多个顶级容器，每个保持子容器。 通讯簿容器层次结构可以很深;可用的子容器的数量没有限制。
  
下图显示了典型的 MAPI 通讯簿组织。
  
**通讯簿组织**
  
![通讯簿组织](media/amapi_04.gif "通讯簿组织")
  
MAPI 集成到一个通讯簿，由安装的通讯簿提供程序提供的所有信息演示统一客户端应用程序的视图。 集成的列表显示了显示每个安装的通讯簿提供程序的顶级容器。 大多数通讯簿提供程序在 MAPI 集成的通讯簿的最高级别中包含的顶级公开仅少数容器 （通常一到三个）。 例如，通讯簿提供程序可能会使可用"所有用户"和"本地用户"作为最高级别的两个容器。
  
客户端应用程序的用户都可以查看的通讯簿容器内容，并在某些情况下，修改的内容。 可以使用不同的访问级别，具体取决于通讯簿提供程序创建地址簿容器。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 功能和体系结构](mapi-features-and-architecture.md)

