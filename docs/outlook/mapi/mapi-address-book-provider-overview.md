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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32298138"
---
# <a name="mapi-address-book-provider-overview"></a>MAPI 通讯簿提供程序概述
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通讯簿提供程序处理对目录信息的访问。 目录信息包含两种类型的邮件收件人的数据: 单个邮件传递用户和邮件传递用户组, 这些用户通常在通讯组列表中一起寻址。 根据收件人和通讯簿提供程序的类型, 有很多可供使用的信息。 例如, 所有通讯簿提供程序都存储收件人的姓名、地址和地址类型。
  
每个通讯簿提供程序使用一个或多个容器来组织此数据。 容器的数目和结构取决于通讯簿提供程序的实现。 例如, 一个通讯簿提供程序可能使用单个容器来保存所有信息, 另一个容器可能使用一个包含子容器的顶级容器, 第三个可能使用多个顶级容器, 每个容器容纳一个子容器。 通讯簿容器层次结构可以很深;对可以使用的子容器的数量没有限制。
  
下图显示了一个典型的 MAPI 通讯簿组织。
  
**通讯簿组织**
  
![通讯簿组织](media/amapi_04.gif "通讯簿组织")
  
MAPI 将安装的通讯簿提供程序提供的所有信息集成到一个通讯簿中, 从而向客户端应用程序呈现一个统一的视图。 集成列表显示每个已安装的通讯簿提供程序显示的顶级容器。 大多数通讯簿提供程序只公开了顶级的几个容器 (通常为一到三个), 以包含在 MAPI 集成通讯簿的顶层。 例如, 通讯簿提供程序可能会将可用的 "所有用户" 和 "本地用户" 用作顶层的两个容器。
  
客户端应用程序的用户可以查看通讯簿容器的内容, 在某些情况下, 可以修改内容。 可以使用不同的访问级别创建通讯簿容器, 具体取决于通讯簿提供程序。 
  
## <a name="see-also"></a>另请参阅

- [MAPI 功能和体系结构](mapi-features-and-architecture.md)

