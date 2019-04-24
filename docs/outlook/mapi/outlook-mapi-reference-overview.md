---
title: Outlook MAPI 引用概述
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
api_type:
- COM
ms.assetid: 4c126d0c-d7c0-45c0-801c-c9f1e44c9db6
description: 上次修改时间：2013 年 2 月 1 日
localization_priority: Priority
ms.openlocfilehash: dc743824cf96800c32d4b4006ae86fbff0bd48a0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348494"
---
# <a name="outlook-mapi-reference-overview"></a>Outlook MAPI 引用概述

**适用于**：Outlook 2013 | Outlook 2016 
  
本主题概述了 Outlook 2013 MAPI 引用文档的相关信息。
  
## <a name="about-this-documentation"></a>关于本文档

本文档适用于 Microsoft Outlook 2013 中消息传送 API (MAPI) 的实现。 
  
在 Microsoft Office Outlook 2007 之前，MAPI 程序员引用是 Microsoft Exchange 文档的一部分。
  
> [!NOTE]
> 自 Microsoft Exchange Server 2007 起，Exchange 已不再强调 MAPI 的使用，因此对 Exchange 实现的支持有限。 
  
MAPI 的 Outlook 实现不同于 Microsoft Exchange 实现。 Outlook 实现适用于在客户端计算机上运行，并强调低延迟。 Exchange 实现适用于重视高可用性和较好的多线程处理能力的服务器。
  
本文档适用于在最终用户系统上运行的应用程序。 对于服务器应用程序，请使用 MAPI 的 Exchange 实现（如果适用），或使用当前的 Exchange API，例如 Exchange Web 服务。 有关 Exchange Web 服务的详细信息，请参阅 [Exchange Web 服务参考](https://msdn.microsoft.com/library/bb204119.aspx)。
  
可以编写同时适用于 MAPI 的 Outlook 或 Exchange 实现的应用程序。 例如，MFCMAPI 在任意一个平台上均运行良好。 这些实现有许多通用的功能，但也有一些显著和微妙的区别。 若旨在让应用程序适用于所有环境，则必须同时在这两个平台上仔细进行测试。 此测试需要两个系统，因为不支持同时在同一个操作系统安装上运行两个实现。
  
请注意，MAPI 适用于对 MAPI 存储中数据的低级别访问，或用于生成传输、消息存储或通讯簿提供程序。 由于 MAPI 绕过了 Outlook 的业务逻辑，因此在评估用于生成解决方案的 API 时，还应考虑 Outlook 对象模型的使用。 Outlook 对象模型的确封装 Outlook 业务逻辑，但不适合多线程代码、同步提供程序或 Windows 服务应用程序。
  
有关此版本的新增功能的相关信息，请参阅下列主题：
  
- [此版本的新增功能](what-s-new-in-this-edition.md)
    
- [此版本弃用的 API 元素](api-elements-deprecated-in-this-edition.md)
    
若刚开始开发 Outlook 的 MAPI 应用程序，请参阅下列主题：
  
- [选择用于开发 Outlook 2013 解决方案的 API 或技术](https://msdn.microsoft.com/library/jj900714.aspx)
    
- [常用头文件](commonly-used-header-files.md)
    
- [常用属性](commonly-used-properties.md)
    
- [常用对象](commonly-used-objects.md)
    
此参考的其他部分分为下列三种信息类型：
  
- [MAPI 示例](mapi-samples.md) - 将你转到许多代码示例，这些示例将演示如何使用各种 API 元素，以及如何实现简单的 MAPI 提供程序并创建 Outlook 项目。 
    
- [MAPI 概念](mapi-concepts.md) - 说明 MAPI 的概念和体系结构。 
    
- [MAPI 参考](mapi-reference.md) - 详细介绍 MAPI 的功能、界面、结构和属性。 
    
## <a name="see-also"></a>另请参阅

- [Outlook MAPI 引用入门](getting-started-with-the-outlook-mapi-reference.md)
- [MAPI 示例](mapi-samples.md)
- [MAPI 概念](mapi-concepts.md)

