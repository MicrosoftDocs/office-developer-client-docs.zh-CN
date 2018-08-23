---
title: 开发 MAPI 通讯簿提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 821cc42d-eebb-4327-b2d4-594421a5c22c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 731ebf6f61db8e9f425d48ab63cb7b81035a41c1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584280"
---
# <a name="developing-a-mapi-address-book-provider"></a>开发 MAPI 通讯簿提供程序

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
通讯簿提供程序提供客户端应用程序，消息存储和传输提供程序，以及为 MAPI 的收件人信息。 到存储分栏称为容器层次结构组织收件人信息。 配置文件中的每个通讯簿分配一个或更多首要，或父级到 MAPI 通讯簿，所有地址中的收件人信息集成视图的容器会话中书籍提供程序。 它是通过 MAPI 通讯簿的客户端和其他服务提供商访问通讯簿提供程序的数据。
  
MAPI 生成通过集成的通讯簿：
  
1. 检索每个通讯簿提供程序的顶级容器。
    
2. 检索每个容器层次结构表。 
    
3. 将每个层次结构表复制到集成的层次结构表。 它是公开给客户端集成的层次结构表。 
    
MAPI 施加地址簿提供程序编写器几项的要求。 可能的功能的范围可以实现地址簿作者原样各种且灵活。 例如，您的提供商可以限制为提供特定类型的收件人信息的只读视图或实现一组完整的功能，甚至可能允许客户端或提供程序，以使对收件人数据添加或修改并实施搜索条件，用于定义自定义视图。 
  
提供程序的数据可以在文件、 数据库或远程服务器上本地驻留。 某些通讯簿提供程序是为了与特定的邮件系统，他人可以与任何邮件系统运行时与传输提供程序，紧密耦合工作。
  
MAPI 定义一个特殊类型的名为个人通讯簿或 PAB、 的实现单个可修改容器并可容纳从其他容器以及创建直接信息复制的收件人信息的通讯簿提供程序。 虽然任何通讯簿提供程序可以实现 PAB 并可以向一个配置文件添加多个 Pab，可以指定这些提供程序中的只有一个为 PAB 任何一个会话过程中运行。 
  

