---
title: MAPI 通讯簿提供程序概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ead51434-ae19-4c34-aa7a-bdeeccca5bd9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ee628f4b11cb174c05a16ca60c9ec830a0e9abbe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426539"
---
# <a name="mapi-address-book-provider-overview"></a>MAPI 通讯簿提供程序概述
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通讯簿提供程序处理对目录信息的访问。 目录信息包含两种类型的邮件收件人的数据：单个邮件用户和通讯组列表中通常一起寻址的邮件用户组。 根据收件人和通讯簿提供程序的类型，可以提供各种信息。 例如，所有通讯簿提供程序都存储收件人的姓名、地址和地址类型。
  
每个通讯簿提供程序都使用一个或多个容器来组织此数据。 容器的数量和结构取决于通讯簿提供程序的实现。 例如，一个通讯簿提供程序可能使用一个容器来保存所有信息，另一个地址簿提供程序可能使用一个包含子容器的顶级容器，第三个可能使用几个顶级容器，每个容器存放子容器。 通讯簿容器层次结构可能很深;对可以使用的子包含者的数量没有限制。
  
下图显示了典型的 MAPI 通讯簿组织。
  
**通讯簿组织**
  
![通讯簿组织](media/amapi_04.gif "通讯簿组织")
  
MAPI 将已安装通讯簿提供程序提供的所有信息集成到一个通讯簿中，为客户端应用程序提供统一视图。 集成列表显示由每个已安装的通讯簿提供程序显示的顶级容器。 大多数通讯簿提供程序仅公开几个容器 (一到三) 顶级容器，以包含在 MAPI 集成通讯簿的顶层中。 例如，通讯簿提供程序可能将"所有用户"和"本地用户"作为顶级的两个容器提供。
  
客户端应用程序的用户可以查看通讯簿容器的内容，在某些情况下还可以修改内容。 可以使用不同的访问级别创建通讯簿容器，具体取决于通讯簿提供程序。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 功能和体系结构](mapi-features-and-architecture.md)

